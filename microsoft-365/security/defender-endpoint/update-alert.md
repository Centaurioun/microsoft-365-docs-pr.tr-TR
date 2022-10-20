---
title: Uyarı varlığı API'sini güncelleştirme
description: Bu API'yi kullanarak bir Uç Nokta için Microsoft Defender uyarısını güncelleştirmeyi öğrenin. Durum, belirleme, sınıflandırma ve assignedTo özelliklerini güncelleştirebilirsiniz.
keywords: api'ler, graf api'si, desteklenen API'ler, alma, uyarı, bilgi, kimlik
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
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 15835e73585a3a7c1cfc3531067cac34e8341a9a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644251"
---
# <a name="update-alert"></a>Uyarıyı güncelleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması
Mevcut [Uyarının](alerts.md) özelliklerini Güncelleştirmeler.

Özellikleri güncelleştirerek veya güncelleştirmeden **açıklama** gönderilebilir.

Güncelleştirilebilir özellikler şunlardır: `status`, `determination`, `classification`ve `assignedTo`.

## <a name="limitations"></a>Sınırlamalar

1. API'de kullanılabilen uyarıları güncelleştirebilirsiniz. Daha fazla bilgi için bkz. [Uyarıları Listeleme](get-alerts.md).
2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Alerts.ReadWrite.All|'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı)|Alert.ReadWrite|'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Uyarı araştırması' (Daha fazla bilgi için bkz. [Rol oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının, cihaz grubu ayarlarına göre uyarıyla ilişkilendirilmiş cihaza erişimi olmalıdır (Daha fazla bilgi için bkz. [Cihaz grupları oluşturma ve yönetme](machine-groups.md)
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

## <a name="http-request"></a>HTTP isteği

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde, güncelleştirilmesi gereken ilgili alanların değerlerini sağlayın.

İstek gövdesinde yer almayan mevcut özellikler önceki değerlerini korur veya diğer özellik değerlerinde yapılan değişikliklere göre yeniden hesaplanır.

En iyi performans için değişmemiş mevcut değerleri eklememelisiniz.

Özellik|Tür|Açıklama|
:---|:---|:---
Durum|Dize|Uyarının geçerli durumunu belirtir. Özellik değerleri şunlardır: 'New', 'InProgress' ve 'Resolved'.|
Atanan|Dize|Uyarının sahibi|
Sınıflandırma|Dize|Uyarının belirtimini belirtir. Özellik değerleri şunlardır: `TruePositive`, `Informational, expected activity`ve `FalsePositive`.|
Belirlenmesi|Dize|Uyarının belirlenmesini belirtir. <p>Her sınıflandırma için olası belirleme değerleri şunlardır: <br><li> <b>Doğru pozitif</b>: `Multistage attack` (MultiStagedAttack), `Malicious user activity` (MaliciousUserActivity), `Compromised account` (CompromisedUser) – genel api'de sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Malware` (Kötü Amaçlı Yazılım), `Phishing` (Kimlik Avı), `Unwanted software` (İstenmeyenSoftware) ve `Other` (Diğer). <li> <b>Bilgilendirici, beklenen etkinlik:</b> `Security test` (SecurityTesting), `Line-of-business application` (LineOfBusinessApplication), `Confirmed activity` (ConfirmedUserActivity) - genel API'deki sabit listesi adını buna göre ve `Other` (Diğer) değiştirmeyi göz önünde bulundurun. <li>  <b>Hatalı pozitif:</b> `Not malicious` (Temiz) - genel API'deki sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Not enough data to validate` (InsufficientData) ve `Other` (Diğer).|
Açıklama ekleme|Dize|Uyarıya eklenecek açıklama.|

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacaktır.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 Tamam döndürür ve güncelleştirilmiş özelliklere sahip yanıt gövdesindeki [uyarı](alerts.md) varlığı. Belirtilen kimlikle uyarı bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
