---
title: Yaygın Microsoft 365 Defender REST API hata kodları
description: Yaygın Microsoft 365 Defender REST API hata kodları hakkında bilgi edinin
keywords: api, hata, kodlar, yaygın hatalar, Microsoft 365 Defender, API hata kodları
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 6aeed1afa77779de5d21bb0ecbdd34d5a4c7e0e0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482482"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Yaygın Microsoft 365 Defender REST API hata kodları

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Hata kodları, Microsoft 365 Defender API'lerinden herhangi birinde bir işlem tarafından döndürülebilir. Her hata yanıtı, sorunun çözülmesine yardımcı olabilecek bir hata iletisi içerir. Tablo bölümündeki hata iletisi sütunu bazı örnek iletiler sağlar. Gerçek iletilerin içeriği, yanıtı tetikleyen faktörlere göre değişir. Değişken içeriği tabloda açılı ayraçlarla gösterilir.

## <a name="error-codes"></a>Hata kodları

Hata kodu | HTTP durum kodu | İleti
-|-|-
BadRequest | BadRequest (400) | Genel Hatalı İstek hata iletisi.
ODataError | BadRequest (400) | Geçersiz OData URI sorgusu \<the specific error is specified\>.
InvalidInput | BadRequest (400) | Geçersiz giriş \<the invalid input\>.
InvalidRequestBody | BadRequest (400) | Geçersiz istek gövdesi.
InvalidHashValue | BadRequest (400) | Karma değer \<the invalid hash\> geçersiz.
InvalidDomainName | BadRequest (400) | Etki alanı adı \<the invalid domain\> geçersiz.
InvalidIpAddress | BadRequest (400) | IP adresi \<the invalid IP\> geçersiz.
InvalidUrl | BadRequest (400) | URL \<the invalid URL\> geçersiz.
MaximumBatchSizeExceeded | BadRequest (400) | Maksimum toplu iş boyutu aşıldı. Alındı: \<batch size received\>, allowed: {batch size allowed}.
MissingRequiredParameter | BadRequest (400) | Parametre \<the missing parameter\> eksik.
OsPlatformNotSupported | BadRequest (400) | İşletim Sistemi Platformu \<the client OS Platform\> bu eylem için desteklenmez.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> istemci sürümünde \<supported client version\> ve üzerinde desteklenir.
Yetki -siz | Yetkisiz (401) | Yetki -siz <br /><br />*Not: Genellikle geçersiz veya süresi dolmuş bir yetkilendirme üst bilgisinden kaynaklanır.*
Yasak | Yasak (403) | Yasak <br /><br />*Not: Geçerli belirteç ancak eylem için yeterli izin yok*.
DisabledFeature | Yasak (403) | Kiracı özelliği etkinleştirilmedi.
DisallowedOperation | Yasak (403) | \<the disallowed operation and the reason\>.
NotFound | Bulunamadı (404) | Genel Bulunamadı hata iletisi.
ResourceNotFound | Bulunamadı (404) | Kaynak \<the requested resource\> bulunamadı.
InternalServerError | İç Sunucu Hatası (500) | *Not: Hata iletisi yok, işlemi yeniden deneyin veya çözümlenmezse [Microsoft'a başvurun](../../admin/get-help-support.md)*

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

## <a name="body-parameters"></a>Gövde parametreleri

> [!IMPORTANT]
> Gövde parametreleri büyük/küçük harfe duyarlıdır.

*InvalidRequestBody* veya *MissingRequiredParameter* hatasıyla karşılaşırsanız, bunun nedeni yazım hatası olabilir. API belgelerini gözden geçirin ve gönderilen parametrelerin ilgili örnekle eşleşip eşleşmediğini denetleyin.

## <a name="tracking-id"></a>İzleme Kimliği

Her hata yanıtı, izleme için benzersiz bir kimlik parametresi içerir. Bu parametrenin özellik adı *hedeftir*. Bir hata hakkında bizimle iletişim kurarken, bu kimliği eklemek sorunun kök nedenini bulmamıza yardımcı olur.

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Desteklenen Microsoft 365 Defender API'leri](api-supported.md)
- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- [API sınırları ve lisanslama hakkında bilgi edinin](api-terms.md)
