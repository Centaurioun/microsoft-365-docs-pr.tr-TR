---
title: Katılım veya çıkarma bildirim kuralı oluşturun
description: Yerel bir ekleme veya çıkarma betiği kullanıldığında bildirim alın.
keywords: ekleme, çıkarma, yerel, betik, bildirim, kural
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 1ff70c961a8598465634525928b994e2e310c0ea
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68626083"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Yerel ekleme veya çıkarma betiği kullanıldığında bildirim kuralı oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Yerel bir ekleme veya çıkarma betiği kullanıldığında size bildirilmesi için bir bildirim kuralı oluşturun.

## <a name="before-you-begin"></a>Başlamadan önce

Şu erişime sahip olmanız gerekir:

- Power Automate (En azından kullanıcı başına plan). Daha fazla bilgi için bkz. [Power Automate fiyatlandırma sayfası](https://flow.microsoft.com/pricing/).
- Azure Tablosu veya SharePoint Listesi veya Kitaplığı / SQL DB.

## <a name="create-the-notification-flow"></a>Bildirim akışını oluşturma

1. [flow.microsoft.com'da](https://flow.microsoft.com/).

2. **Yeni > Zamanlandı - boş > Akışlarım'a** gidin.

   :::image type="content" source="images/new-flow.png" alt-text="Akış" lightbox="images/new-flow.png":::


3. Zamanlanmış akış oluşturma.
   1. Bir akış adı girin.
   2. Başlangıç ve saati belirtin.
   3. Sıklığı belirtin. Örneğin, 5 dakikada bir.

   :::image type="content" source="images/build-flow.png" alt-text="Bildirim akışı" lightbox="images/build-flow.png":::

4. Yeni bir eylem eklemek için + düğmesini seçin. Yeni eylem, Uç Nokta için Defender güvenlik merkezi cihazları API'sine yönelik bir HTTP isteği olacaktır. Ayrıca bunu kullanıma uygun "WDATP Bağlayıcısı" (eylem: "Makineler - Makinelerin listesini al") ile de değiştirebilirsiniz.

   :::image type="content" source="images/recurrence-add.png" alt-text="Yinelenme ve ekleme eylemi" lightbox="images/recurrence-add.png":::

5. Aşağıdaki HTTP alanlarını girin:

   - Yöntem: Cihaz listesini almak için bir değer olarak "GET".
   - URI: girin `https://api.securitycenter.microsoft.com/api/machines`.
   - Kimlik doğrulaması: "Active Directory OAuth" öğesini seçin.
   - Kiracı: Oturum açın https://portal.azure.com ve **Azure Active Directory > Uygulama Kayıtları'na** gidin ve Kiracı Kimliği değerini alın.
   - Seyirci: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - İstemci Kimliği: Uygulamasında oturum açın https://portal.azure.com ve **Azure Active Directory > Uygulama Kayıtları'na** gidin ve İstemci Kimliği değerini alın.
   - Kimlik Bilgisi Türü: "Gizli Dizi" öğesini seçin.
   - Gizli Dizi: **Azure Active Directory > Uygulama Kayıtları'nda** https://portal.azure.com oturum açın ve kiracı kimliği değerini alın.

    :::image type="content" source="images/http-conditions.png" alt-text="HTTP koşulları" lightbox="images/http-conditions.png":::

6. Yeni **eylem ekle'yi** seçip **Veri İşlemleri'ni** arayıp **JSON Ayrıştır'ı** seçerek yeni bir adım ekleyin.

   :::image type="content" source="images/data-operations.png" alt-text="Veri işlemleri girişi" lightbox="images/data-operations.png":::

7. **İçerik** alanına Gövde ekleyin.

   :::image type="content" source="images/parse-json.png" alt-text="JSON bölümünü ayrıştırma" lightbox="images/parse-json.png":::

8. **Şema oluşturmak için örnek yükü kullan** bağlantısını seçin.

   :::image type="content" source="images/parse-json-schema.png" alt-text="JSON'yi yük ile ayrıştırma" lightbox="images/parse-json-schema.png":::

9. Aşağıdaki JSON parçacığını kopyalayıp yapıştırın:

    ```json
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10. JSON çağrısından değerleri ayıklayın ve eklenen cihazın / olup olmadığını sharepoint listesinde örnek olarak denetleyin:

    - Evet ise, hiçbir bildirim tetiklenmeyecek
    - Hayır ise, eklenen yeni cihazları SharePoint listesine kaydeder ve Uç Nokta için Defender yöneticisine bir bildirim gönderilir

    :::image type="content" source="images/flow-apply.png" alt-text="Akışın her öğeye uygulanması" lightbox="images/flow-apply.png":::

    :::image type="content" source="images/apply-to-each.png" alt-text="Akışın Get items öğesine uygulanması" lightbox="images/apply-to-each.png":::

11. **Koşul'un** altında şu ifadeyi ekleyin: "length(body('Get_items')?[' value'])" yazın ve koşulu 0'a eşit olarak ayarlayın.

    :::image type="content" source="images/apply-to-each-value.png" alt-text="Akışın her koşula uygulanması" lightbox="images/apply-to-each-value.png":::
    :::image type="content" source="images/conditions-2.png" alt-text="Koşul-1" lightbox="images/conditions-2.png":::
    :::image type="content" source="images/condition3.png" alt-text="Koşul-2" lightbox="images/condition3.png":::
    :::image type="content" source="images/send-email.png" alt-text="E-posta gönder bölümü" lightbox="images/send-email.png":::

## <a name="alert-notification"></a>Uyarı bildirimi

Aşağıdaki resimde bir e-posta bildirimi örneği verilmiştir.

:::image type="content" source="images/alert-notification.png" alt-text="E-posta bildirim ekranı" lightbox="images/alert-notification.png":::

## <a name="tips"></a>Ipuç -ları

- Burada yalnızca lastSeen komutunu kullanarak filtreleyebilirsiniz:
  - Her 60 dakikada bir:
    - Son 7 gün içinde görülen tüm cihazları alın.

- Her cihaz için:
  - Son görülen özellik [-7 gün, -7 gün + 60 dakika] bir saatlik aralıktaysa -> Çıkarma olasılığı için uyarı.
  - İlk kez görüldüyse son bir saat içinde -ekleme için uyarı >.

Bu çözümde yinelenen uyarılarınız olmayacaktır: Çok sayıda cihazı olan kiracılar vardır. Tüm bu cihazları almak çok pahalı olabilir ve sayfalama gerektirebilir.

Bunu iki sorguya bölebilirsiniz:

1. Çıkarma için yalnızca OData $filter kullanarak bu aralığı kullanın ve yalnızca koşulların karşılanıp karşılanmadiğini bildirin.
2. Son bir saat içinde en son görülen tüm cihazları alın ve bunlar için ilk görülen özelliği kontrol edin (ilk görülen özellik son bir saat içindeyse, son görülen de orada olmalıdır).
