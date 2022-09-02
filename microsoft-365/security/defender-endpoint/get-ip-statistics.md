---
title: IP istatistikleri API'lerini alma
description: Uç Nokta için Microsoft Defender kullanarak IP'niz için en son istatistikleri alın.
keywords: api'ler, graf api'leri, desteklenen API'ler, get, ip, istatistikler, yaygınlık
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
ms.openlocfilehash: e3b8826f2e64d339f617fb23d555d4a4f804c3ff
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522289"
---
# <a name="get-ip-statistics-api"></a>IP istatistikleri API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması
Verilen IP'nin istatistiklerini alır.

## <a name="limitations"></a>Sınırlamalar
1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.
2. Lookbackhours için Maksimum Değer 720 Saat(30days) olur.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Ip.Read.All|'IP adresi profillerini okuma'
Temsilci (iş veya okul hesabı)|Ip.Read.All|'IP adresi profillerini okuma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-uri-parameters"></a>İstek URI parametreleri

Name|Tür|Açıklama
:---|:---|:---
lookBackHours|Int32|İstatistikleri almak için geri arama yaptığımız saatleri tanımlar. Varsayılan değer 30 gündür. **İsteğe bağlı**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı ve ip varsa - gövdede istatistiksel verilerle 200 Tamam. IP geçerli ancak yok - organizationPrevalence 0, IP geçersiz - HTTP 400.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```

|Name|Açıklama|
|---|---|
|Kuruluş yaygınlığı|bu IP'ye ağ bağlantısı açan cihazların ayrı sayısı.|
|Kuruluş ilk kez görüldü|bu IP için kuruluştaki ilk bağlantı.|
|Kuruluş en son görüldü|kuruluştaki bu IP için son bağlantı.|

> [!NOTE]
> Bu istatistik bilgileri son 30 güne ait verileri temel alır.
