---
title: Yaygın Uç Nokta için Microsoft Defender API hataları
description: Açıklamalarla birlikte yaygın Uç Nokta için Microsoft Defender API hatalarının listesi.
keywords: API'ler, Uç Nokta için Microsoft Defender API'leri, hatalar, sorun giderme
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
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: a96aacfc4c2133b8aae436c97bfd438f2f478123
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68142449"
---
# <a name="common-rest-api-error-codes"></a>Yaygın REST API hata kodları



[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Aşağıdaki tabloda listelenen hata kodları, Uç Nokta için Microsoft Defender API'lerden herhangi birinde bir işlem tarafından döndürülebilir.
* Hata koduna ek olarak, her hata yanıtı sorunu çözmeye yardımcı olabilecek bir hata iletisi içerir.
* İleti, değiştirilebilen bir serbest metindir.
* Sayfanın en altında yanıt örneklerini bulabilirsiniz.

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Hata kodu|HTTP durum kodu|İleti
---|---|---
BadRequest|BadRequest (400)|Genel Hatalı İstek hata iletisi.
ODataError|BadRequest (400)|Geçersiz OData URI sorgusu (belirli bir hata belirtildi).
InvalidInput|BadRequest (400)|Geçersiz giriş {geçersiz giriş}.
InvalidRequestBody|BadRequest (400)|Geçersiz istek gövdesi.
InvalidHashValue|BadRequest (400)|{geçersiz karma} karma değeri geçersiz.
InvalidDomainName|BadRequest (400)|Etki alanı adı {geçersiz etki alanı} geçersiz.
InvalidIpAddress|BadRequest (400)|{geçersiz IP} IP adresi geçersiz.
InvalidUrl|BadRequest (400)|{geçersiz URL} URL'si geçersiz.
MaximumBatchSizeExceeded|BadRequest (400)|Maksimum toplu iş boyutu aşıldı. Alındı: {toplu iş boyutu alındı}, izin verildi: {batch size allowed}.
MissingRequiredParameter|BadRequest (400)|{the missing parameter} parametresi eksik.
OsPlatformNotSupported|BadRequest (400)|İşletim Sistemi Platformu {istemci işletim sistemi platformu}, bu eylem için desteklenmiyor.
ClientVersionNotSupported|BadRequest (400)|{İstenen eylem}, istemci sürümü {desteklenen istemci sürümü} ve üzerinde desteklenir.
Yetki -siz|Yetkisiz (401)|Yetkisiz (geçersiz veya süresi dolmuş yetkilendirme üst bilgisi).
Yasak|Yasak (403)|Yasak (geçerli belirteç ama eylem için yeterli izin yok).
DisabledFeature|Yasak (403)|Kiracı özelliği etkinleştirilmedi.
DisallowedOperation|Yasak (403)|{izin verilmeyen işlem ve nedeni}.
NotFound|Bulunamadı (404)|Genel Bulunamadı hata iletisi.
ResourceNotFound|Bulunamadı (404)|{İstenen kaynak} kaynağı bulunamadı.
InternalServerError|İç Sunucu Hatası (500)|(Hata iletisi yok, işlemi yeniden deneyin)
TooManyRequests|Çok Fazla İstek (429)|Yanıt, kota sınırına ulaşmayı istek sayısına veya CPU'ya göre temsil eder.

## <a name="body-parameters-are-case-sensitive"></a>Gövde parametreleri büyük/küçük harfe duyarlıdır

Gönderilen gövde parametreleri şu anda büyük/küçük harfe duyarlıdır.

**InvalidRequestBody** veya **MissingRequiredParameter** hatalarıyla karşılaşırsanız, bunun nedeni yanlış parametre büyük veya küçük harf olabilir.

API belgeleri sayfasını gözden geçirin ve gönderilen parametrelerin ilgili örnekle eşleşip eşleşmediğini denetleyin.

## <a name="correlation-request-id"></a>Bağıntı isteği kimliği

Her hata yanıtı, izleme için benzersiz bir kimlik parametresi içerir.

Bu parametrenin özellik adı "target" olur.

Bir hata hakkında bizimle iletişim kurarken, bu kimliği eklemek sorunun kök nedenini bulmanıza yardımcı olur.

## <a name="examples"></a>Örnekler

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
