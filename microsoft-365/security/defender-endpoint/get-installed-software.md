---
title: Yüklü yazılımı al
description: Belirli bir cihaz kimliğiyle ilgili yüklü yazılım koleksiyonunu alır.
keywords: apis, graph api, desteklenen API'ler, get, list, file, information, software inventory, installed software per device, threat & vulnerability management api, Uç Nokta için Microsoft Defender tvm api
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: dfc2ec8f9aa866338e0a615fb5d9adac1288f3ce
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520511"
---
# <a name="get-installed-software"></a>Yüklü yazılımı al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Belirli bir cihaz kimliğiyle ilgili yüklü yazılım koleksiyonunu alır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama |Software.Read.All|'Tehdit ve Güvenlik Açığı Yönetim Yazılımı bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Software.Read|'Tehdit ve Güvenlik Açığı Yönetim Yazılımı bilgilerini okuyun'

## <a name="http-request"></a>HTTP isteği

```http
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem gövdede yüklü yazılım bilgileriyle 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Defender Güvenlik Açığı Yönetimi yazılım envanteri](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
