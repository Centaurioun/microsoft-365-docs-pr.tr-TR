---
title: Gösterge kaynak türü
description: Varlık ayrıntılarını belirtin ve Uç Nokta için Microsoft Defender kullanarak göstergenin süre sonunu tanımlayın.
keywords: api'ler, desteklenen api'ler, get, TiIndicator, Indicator, recent
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 0cc1df14f60088efe72a48bea5a755ea375cd7e7
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635137"
---
# <a name="indicator-resource-type"></a>Gösterge kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- Portalda ilgili [Göstergeler sayfasına](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) bakın.

Yöntem|Dönüş Türü|Açıklama
:---|:---|:---
[Göstergeleri Listele](get-ti-indicators-collection.md)|[Göstergesi](ti-indicator.md) Koleksiyon|[Liste Göstergesi](ti-indicator.md) varlıkları.
[Göstergeyi Gönder](post-ti-indicator.md)|[Göstergesi](ti-indicator.md)|[Gösterge](ti-indicator.md) varlığını gönderin veya güncelleştirin.
[göstergeleri içeri aktarma](import-ti-indicators.md)|[Göstergesi](ti-indicator.md) Koleksiyon|[Gösterge varlıklarını](ti-indicator.md) gönderin veya güncelleştirin.
[Göstergeyi Sil](delete-ti-indicator-by-id.md)|İçerik Yok|[Gösterge](ti-indicator.md) varlığını siler.

## <a name="properties"></a>Özellikler

Özellik|Tür|Açıklama
:---|:---|:---
Kimliği|Dize|[Gösterge](ti-indicator.md) varlığının kimliği.
indicatorValue|Dize|[Göstergenin](ti-indicator.md) değeri.
indicatorType|Enum|Göstergenin türü. Olası değerler şunlardır: "FileSha1", "FileSha256", "FileMd5", "CertificateThumbprint", "IpAddress", "DomainName" ve "Url".
Uygulama|Dize|Göstergeyle ilişkili uygulama.
Eylem|Enum|Gösterge kuruluşta bulunursa gerçekleştirilecek eylem. Olası değerler şunlardır: "Warn", "Block", "Audit", "Alert", "AlertAndBlock", "BlockAndRemediate" ve "Allowed".
|externalID|Dize|Müşterinin özel bağıntı isteğinde gönderebileceği kimlik.|
Sourcetype|Enum|Kullanıcı tarafından oluşturulan Göstergenin (örneğin portaldan), API aracılığıyla otomatik uygulama kullanılarak gönderilmesi durumunda "AadApp" olması durumunda "Kullanıcı".
createdBySource|Dize|Göstergeyi gönderen kullanıcının/uygulamanın adı.
Createdby|Dize|Göstergeyi gönderen kullanıcının/uygulamanın benzersiz kimliği.
lastUpdatedBy|Dize|Göstergeyi son güncelleştiren kullanıcının/uygulamanın kimliği.
creationTimeDateTimeUtc|Datetimeoffset|Göstergenin oluşturulduğu tarih ve saat.
expirationTime|Datetimeoffset|Göstergenin sona erme zamanı.
lastUpdateTime|Datetimeoffset|Göstergenin son güncelleştirilişi.
Önem|Enum|Göstergenin önem derecesi. olası değerler şunlardır: "Bilgilendirici", "Düşük", "Orta" ve "Yüksek".
Başlık|Dize|Gösterge başlığı.
Açıklama|Dize|Göstergenin açıklaması.
recommendedActions|Dize|Gösterge için önerilen eylemler.
rbacGroupNames|Dizelerin listesi|Göstergenin açık ve etkin olduğu RBAC cihaz grubu adları. Tüm cihazlara açık olması durumunda boş liste.
rbacGroupIds|Dizelerin listesi|Göstergenin kullanıma sunulduğu ve etkin olduğu RBAC cihaz grubu kimliği. Tüm cihazlara açık olması durumunda boş liste.
generateAlert|Enum|Uyarı oluşturma gerekliyse **True****, bu** gösterge uyarı oluşturmamalıdır.

## <a name="indicator-types"></a>Gösterge Türleri

API tarafından desteklenen gösterge eylem türleri şunlardır:

- Izin verilen
- Denetim
- Engelle
- BlockAndRemediate
- Uyar (yalnızca Cloud Apps için Defender)

Yanıt eylem türlerinin açıklaması hakkında daha fazla bilgi için bkz. [Gösterge oluşturma](manage-indicators.md).

> [!Note]
>
> Önceki yanıt eylemleri (AlertAndBlock ve Alert) Ocak 2022'ye kadar desteklenecektir. Bu tarihten sonra, tüm müşterilerin yukarıda listelenen eylem türlerinden birini kullanması gerekir.

## <a name="json-representation"></a>Json gösterimi

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
