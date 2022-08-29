---
title: Makine eylem API'lerini iptal etme
description: Zaten başlatılan bir makine eylemini iptal etmeyi öğrenin
keywords: api'ler, graf api'leri,
search.appverid: met150
ms.prod: m365-security
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d5736ee3374b182f1b22f1b728ac2378eb66b66d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331895"
---
# <a name="cancel-machine-action-api"></a>Makine eylem API'lerini iptal etme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/defender-endpoint)
- [Uç Nokta için Microsoft Defender Planı 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)

[!include[Prerelease information](../../includes/prerelease.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Henüz son durumunda olmayan (tamamlandı, iptal edildi, başarısız) zaten başlatılan bir makine eylemini iptal edin.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Kullanmaya başlama](apis-intro.md).

|İzin türü|Izni|İzin görünen adı|
|---|---|---|
|Uygulama|Machine.CollectForensics <br> Machine.Isolate <br> Machine.RestrictExecution <br> Machine.Scan <br> Machine.Offboard <br> Machine.StopAndQuarantine <br> Machine.LiveResponse|Adli tıp toplama <br>Makineyi izole et<br>Kod yürütmeyi kısıtlama<br>  Tarama makinesi<br>  Offboard makine<br> Durdur ve karantinaya al<br> Belirli bir makinede canlı yanıt çalıştırma|
|Temsilci (iş veya okul hesabı)|Machine.CollectForensics<br> Machine.Isolate  <br>Machine.RestrictExecution<br> Machine.Scan<br> Machine.Offboard<br> Machine.StopAndQuarantineMachine.LiveResponse|Adli tıp toplama<br> Makineyi izole et<br>  Kod yürütmeyi kısıtlama<br> Tarama makinesi<br>Offboard makine<br> Durdur ve karantinaya al<br> Belirli bir makinede canlı yanıt çalıştırma|

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel
```

## <a name="request-headers"></a>İstek üst bilgileri

|Name|Tür|Açıklama|
|---|---|---|
|Yetkilendirme|Dize|Taşıyıcı {token}. Gerekli.|
|İçerik Türü|Dize|application/json. Gerekli.|

## <a name="request-body"></a>İstek gövdesi

|Parametre|Tür|Açıklama|
|---|---|---|
|Açıklama ekleme|Dize|İptal eylemiyle ilişkilendirilecek açıklama.|

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem Makine Eylemi varlığıyla 200 tamam yanıt kodu döndürür. Belirtilen kimlikle makine eylemi varlığı bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```

```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a>İlgili konu

- [Makine eylem API'si alma](get-machineaction-object.md)
