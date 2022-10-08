---
title: Batch Update uyarı varlıkları API'si
description: Bu API'yi kullanarak toplu Uç Nokta için Microsoft Defender uyarılarını güncelleştirme hakkında bilgi edinin. Durum, belirleme, sınıflandırma ve assignedTo özelliklerini güncelleştirebilirsiniz.
keywords: api'ler, graf api'si, desteklenen API'ler, alma, uyarı, bilgi, kimlik
ms.service: microsoft-365-security
ms.subservice: mde
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 502d5a72fdde17a18f11cf9a3e20069a6664e677
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68153333"
---
# <a name="batch-update-alerts"></a>Grup güncelleştirme uyarıları

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API açıklaması

Mevcut [Uyarıların](alerts.md) bir toplu işleminin özelliklerini Güncelleştirmeler.

Özellikleri güncelleştirerek veya güncelleştirmeden **açıklama** gönderilebilir.

Güncelleştirilebilir özellikler şunlardır: `status`, `determination`ve `classification` `assignedTo`.

## <a name="limitations"></a>Sınırlamalar

1. API'de kullanılabilen uyarıları güncelleştirebilirsiniz. Daha fazla bilgi için bkz. [Uyarıları Listeleme](get-alerts.md) .
2. Bu API için hız sınırlamaları dakikada 10 çağrı ve saatte 500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü | Izni | İzin görünen adı
:---|:---|:---
Uygulama | Alert.ReadWrite.All | 'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı) | Alert.ReadWrite | 'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Uyarı araştırması' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının, cihaz grubu ayarlarına bağlı olarak uyarıyla ilişkilendirilmiş cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

## <a name="http-request"></a>HTTP isteği

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.
İçerik Türü | Dize | application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde, güncelleştirilecek uyarıların kimliklerini ve bu uyarılar için güncelleştirmek istediğiniz ilgili alanların değerlerini sağlayın.

İstek gövdesine dahil edilmeyen mevcut özellikler önceki değerlerini korur veya diğer özellik değerlerinde yapılan değişikliklere göre yeniden hesaplanır.

En iyi performans için değişmemiş mevcut değerleri eklememelisiniz.

Özellik | Tür | Açıklama
:---|:---|:---
alertId'ler | Liste&lt;Dizesi&gt;| Güncelleştirilecek uyarıların kimliklerinin listesi. **Gerekli**
Durum | Dize | Belirtilen uyarıların güncelleştirilmiş durumunu belirtir. Özellik değerleri şunlardır: 'New', 'InProgress' ve 'Resolved'.
Atanan | Dize | Belirtilen uyarıların sahibi
Sınıflandırma | Dize | Belirtilen uyarıların belirtimini belirtir. Özellik değerleri şunlardır: `TruePositive`, `Informational, expected activity`ve `FalsePositive`.
Belirlenmesi | Dize | Belirtilen uyarıların belirlenmesini belirtir. <p>Her sınıflandırma için olası belirleme değerleri şunlardır: <br><li> <b>Doğru pozitif</b>: `Multistage attack` (MultiStagedAttack), `Malicious user activity` (MaliciousUserActivity), `Compromised account` (CompromisedUser) – genel api'de sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Malware` (Kötü Amaçlı Yazılım), `Phishing` (Kimlik Avı), `Unwanted software` (İstenmeyenSoftware) ve `Other` (Diğer). <li> <b>Bilgilendirici, beklenen etkinlik:</b> `Security test` (SecurityTesting), `Line-of-business application` (LineOfBusinessApplication), `Confirmed activity` (ConfirmedUserActivity) - genel API'deki sabit listesi adını buna göre ve `Other` (Diğer) değiştirmeyi göz önünde bulundurun. <li>  <b>Hatalı pozitif:</b> `Not malicious` (Temiz) - genel API'deki sabit listesi adını uygun şekilde değiştirmeyi göz önünde bulundurun, `Not enough data to validate` (InsufficientData) ve `Other` (Diğer).
Yorum | Dize | Belirtilen uyarılara eklenecek açıklama.

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacaktır.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem boş yanıt gövdesiyle 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
