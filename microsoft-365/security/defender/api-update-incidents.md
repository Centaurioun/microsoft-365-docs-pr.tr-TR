---
title: Olay API'sini güncelleştirme
description: Microsoft 365 Defender API kullanarak olayları güncelleştirme hakkında bilgi edinin
keywords: update, api, incident
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 37460a3d0f0f67ee907b8e7b214f859dc60e8dfe
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066860"
---
# <a name="update-incidents-api"></a>Güvenlik olayları API'sini güncelleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="api-description"></a>API açıklaması

Mevcut olayın özelliklerini Güncelleştirmeler. Güncelleştirilebilir özellikler şunlardır: `status`, `determination`, `classification`, `assignedTo`, `tags`, ve `comments`.

### <a name="quotas-resource-allocation-and-other-constraints"></a>Kotalar, kaynak ayırma ve diğer kısıtlamalar

1. Azaltma eşiğine ulaşmadan önce dakikada en fazla 50 veya saatte 1500 çağrı yapabilirsiniz.
2. Özelliğini yalnızca TruePositive olarak ayarlanmışsa `classification` ayarlayabilirsiniz`determination`.

İsteğiniz kısıtlanırsa bir `429` yanıt kodu döndürür. Yanıt gövdesi, yeni çağrılar yapmaya başlayabileceğiniz zamanı belirtir.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Microsoft 365 Defender API'lerine erişme](api-access.md).

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Incident.ReadWrite.All|Tüm olayları okuma ve yazma
Temsilci (iş veya okul hesabı)|Incident.ReadWrite|Olayları okuma ve yazma

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken, kullanıcının portalda olayı güncelleştirme iznine sahip olması gerekir.

## <a name="http-request"></a>HTTP isteği

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde, güncelleştirilmesi gereken alanların değerlerini sağlayın. İstek gövdesinde yer almayan mevcut özellikler, ilgili değerlerde yapılan değişiklikler nedeniyle yeniden hesaplanmaları gerekmediği sürece değerlerini korur. En iyi performans için değişmemiş mevcut değerleri atlamalısınız.

Özellik|Tür|Açıklama
---|---|---
Durum|Enum|Olayın geçerli durumunu belirtir. Olası değerler şunlardır: `Active`, `Resolved`ve `Redirected`.
Atanan|Dize|Olayın sahibi.
Sınıflandırma|Enum|Olayın belirtimi. Olası değerler şunlardır: `TruePositive`, `Informational, expected activity`ve `FalsePositive`.
Belirlenmesi|Enum|Olayın belirlenmesini belirtir. <p>Her sınıflandırma için olası belirleme değerleri şunlardır: <br><li> <b>Doğru pozitif</b>: `Multistage attack` (MultiStagedAttack), `Malicious user activity` (MaliciousUserActivity), `Compromised account` (CompromisedUser) – genel api'de sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Malware` (Kötü Amaçlı Yazılım), `Phishing` (Kimlik Avı), `Unwanted software` (İstenmeyenSoftware) ve `Other` (Diğer). <li> <b>Bilgilendirici, beklenen etkinlik:</b> `Security test` (SecurityTesting), `Line-of-business application` (LineOfBusinessApplication), `Confirmed activity` (ConfirmedUserActivity) - genel API'deki sabit listesi adını buna göre ve `Other` (Diğer) değiştirmeyi göz önünde bulundurun. <li>  <b>Hatalı pozitif:</b> `Not malicious` (Temiz) - genel API'deki sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Not enough data to validate` (InsufficientData) ve `Other` (Diğer).
Etiketler|dize listesi|Olay etiketlerinin listesi.
Yorum|Dize|Olaya eklenecek açıklama.

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacaktır.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem döndürür `200 OK`. Yanıt gövdesi, güncelleştirilmiş özelliklere sahip olay varlığını içerir. Belirtilen kimlikle bir olay bulunamazsa, yöntemi döndürür `404 Not Found`.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiş.

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

### <a name="response-example"></a>Yanıt örneği

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- [API sınırları ve lisanslama hakkında bilgi edinin](api-terms.md)
- [Hata kodlarını anlama](api-error-codes.md)
- [Olay API'leri](api-incident.md)
- [Olayları listeleyin](api-list-incidents.md)
- [Olaylara genel bakış](incidents-overview.md)
