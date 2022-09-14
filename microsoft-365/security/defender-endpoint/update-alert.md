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
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: d397d17214f4a8ee4c58ef66ed7b8c0c37c287eb
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686669"
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

Özellik|Tür|Açıklama
:---|:---|:---
Durum|Dize|Uyarının geçerli durumunu belirtir. Özellik değerleri şunlardır: 'New', 'InProgress' ve 'Resolved'.
Atanan|Dize|Uyarının sahibi
Sınıflandırma|Dize|Uyarının belirtimini belirtir. Özellik değerleri şunlardır: 'Unknown', 'FalsePositive', 'TruePositive'.
Belirlenmesi|Dize|Uyarının belirlenmesini belirtir. Özellik değerleri şunlardır: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'İstenmeyenSoftware', 'Diğer'
Açıklama ekleme|Dize|Uyarıya eklenecek açıklama.

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacak.

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
