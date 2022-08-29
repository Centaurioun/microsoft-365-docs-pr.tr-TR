---
title: Power BI'a API bağlantısı Uç Nokta için Microsoft Defender
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender API'lerinin üzerinde bir Power Business Intelligence (BI) raporu oluşturun.
keywords: api'ler, desteklenen API'ler, Power BI, raporlar
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 086579f6923f59c12c5ef9f7494b539f24c19210
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328133"
---
# <a name="create-custom-reports-using-power-bi"></a>Power BI kullanarak özel raporlar oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Bu bölümde, Uç Nokta için Defender API'lerinin üzerinde bir Power BI raporu oluşturmayı öğreneceksiniz.

İlk örnekte Power BI'ın Gelişmiş Tehdit Avcılığı API'sine nasıl bağlanacakları, ikinci örnekte ise Makine Eylemleri veya Uyarılar gibi OData API'lerimize bağlantı gösterilmektedir.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Power BI'ı Gelişmiş Tehdit Avcılığı API'sine bağlama

- Microsoft Power BI'i açın.

- **Boş Veri** \> Al **Sorgu'ya** tıklayın.

  :::image type="content" source="images/power-bi-create-blank-query.png" alt-text="Veri Al menü öğesinin altındaki Boş Sorgu seçeneği" lightbox="images/power-bi-create-blank-query.png":::

- **Gelişmiş Düzenleyici'e** tıklayın.

  :::image type="content" source="images/power-bi-open-advanced-editor.png" alt-text="Gelişmiş Düzenleyici menü öğesi" lightbox="images/power-bi-open-advanced-editor.png":::

- Aşağıdakini kopyalayın ve düzenleyiciye yapıştırın:

```
    let
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table
```

- **Bitti'ye** tıklayın.

- **Kimlik Bilgilerini Düzenle'ye** tıklayın.

    :::image type="content" source="images/power-bi-edit-credentials.png" alt-text="Kimlik Bilgilerini Düzenle menü öğesi" lightbox="images/power-bi-edit-credentials.png":::
    

- **Kuruluş hesabı** \> **Oturum aç'ı** seçin.

    :::image type="content" source="images/power-bi-set-credentials-organizational.png" alt-text="Kuruluş hesabı menü öğesinde Oturum aç seçeneği" lightbox="images/power-bi-set-credentials-organizational.png":::

- Kimlik bilgilerinizi girin ve oturum açmak için bekleyin.

- **Bağlan'a** tıklayın.

    :::image type="content" source="images/power-bi-set-credentials-organizational-cont.png" alt-text="Kuruluş hesabı menü öğesindeki oturum açma onayı iletisi" lightbox="images/power-bi-set-credentials-organizational-cont.png":::

- Artık sorgunuzun sonuçları bir tablo olarak görünür ve üzerine görselleştirmeler oluşturmaya başlayabilirsiniz!

- İstediğiniz verileri almak için bu tabloyu çoğaltabilir, yeniden adlandırabilir ve içindeki Gelişmiş Tehdit Avcılığı sorgusunu düzenleyebilirsiniz.

## <a name="connect-power-bi-to-odata-apis"></a>Power BI'ı OData API'lerine bağlama

- Yukarıdaki örnekten tek fark düzenleyicinin içindeki sorgudur.

- Aşağıdakini kopyalayın ve kuruluşunuzdan tüm **Makine Eylemleri'ni** çekmek için düzenleyiciye yapıştırın:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source
```

- Aynı işlemi **Uyarılar** ve **Makineler** için de yapabilirsiniz.
- Sorgu filtreleri için OData sorgularını da kullanabilirsiniz. Bkz. [OData Sorgularını Kullanma](exposed-apis-odata-samples.md).

## <a name="power-bi-dashboard-samples-in-github"></a>GitHub'da Power BI pano örnekleri

Daha fazla bilgi için bkz. [Power BI rapor şablonları](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI).

## <a name="sample-reports"></a>Örnek raporlar

Uç Nokta için Microsoft Defender Power BI rapor örneklerini görüntüleyin. Daha fazla bilgi için bkz. [Kod örneklerine göz atma](/samples/browse/?products=mdatp).

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta API'leri için Defender](apis-intro.md)
- [Gelişmiş Avcılık API'si](run-advanced-query-api.md)
- [OData Sorgularını Kullanma](exposed-apis-odata-samples.md)
