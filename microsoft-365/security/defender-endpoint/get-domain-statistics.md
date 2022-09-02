---
title: Etki alanı istatistikleri API'lerini alma
description: Uç Nokta için Microsoft Defender'da verilen etki alanıyla ilgili istatistikleri almak için Etki alanı istatistikleri al API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, etki alanı, etki alanıyla ilgili cihazlar
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
ms.openlocfilehash: e4dc4137525f9f3019f98979ef33a219868ed15b
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523676"
---
# <a name="get-domain-statistics-api"></a>Etki alanı istatistikleri API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Verilen etki alanındaki istatistikleri alır.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.
2. için `lookbackhours` en yüksek değer 720 saattir (30 gün).

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Url. Tümünü Oku|'Okuma URL'leri'
Temsilci (iş veya okul hesabı)|Url. Tümünü Oku|'Okuma URL'leri'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>İstek üst bilgileri

Üstbilgi|Değer
:---|:---
Yetkilendirme|Taşıyıcı {token}. **Gerekli**.

## <a name="request-uri-parameters"></a>İstek URI parametreleri

Name|Tür|Açıklama
:---|:---|:---
lookBackHours|Int32|İstatistikleri almak için geri arama yaptığımız saatleri tanımlar. Varsayılan değer 30 gündür. **İsteğe bağlı**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılıysa ve etki alanı varsa - yanıt gövdesinde istatistik nesnesiyle 200 Tamam. Etki alanı yoksa - 0 olarak ayarlanmış bir yaygınlık ile 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
