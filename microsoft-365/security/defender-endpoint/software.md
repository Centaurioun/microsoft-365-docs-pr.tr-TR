---
title: Yazılım yöntemleri ve özellikleri
description: En son uyarıları alır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: b59d7d8f243483debcdeeea2ad4037ebf2cd1b15
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621438"
---
# <a name="software-resource-type"></a>Yazılım kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Yöntemler

<br>

****

|Yöntem|Dönüş Türü|Açıklama|
|---|---|---|
|[Yazılımı listele](get-software.md)|Yazılım koleksiyonu|Kurumsal yazılım envanterini listeleme|
|[Yazılımı kimlikle al](get-software-by-id.md)|Yazılım|Belirli bir yazılımı yazılım kimliğine göre alma|
|[Yazılım sürüm dağıtımını listele](get-software-ver-distribution.md)|Dağıtım koleksiyonu|Yazılım kimliğine göre yazılım sürümü dağıtımlarını listeleme|
|[Yazılıma göre makineleri listele](get-machines-by-software.md)|MachineRef koleksiyonu|Yazılım kimliğiyle ilişkili cihazların listesini alma|
|[Yazılıma göre güvenlik açıklarını listele](get-vuln-by-software.md)|[Güvenlik açığı](vulnerability.md) koleksiyonu|Yazılım kimliğiyle ilişkili güvenlik açıklarının listesini alma|
|[Eksik KB'leri al](get-missing-kbs-software.md)|KB koleksiyonu|Yazılım kimliğiyle ilişkili eksik KB'lerin listesini alma|
|

## <a name="properties"></a>Özellikler

<br>

****

|Özellik|Tür|Açıklama|
|---|---|---|
|Kimliği|Dize|Yazılım Kimliği|
|Name|Dize|Yazılım adı|
|Satıcı|Dize|Yazılım yayımcısı adı|
|Zayıf|Uzun|Bulunan güvenlik açıklarının sayısı|
|publicExploit|Boole|Bazı güvenlik açıkları için genel açıklardan yararlanma mevcut|
|activeAlert|Boole|Etkin uyarı bu yazılımla ilişkilendirilir|
|exposedMachines|Uzun|Kullanıma sunulan cihaz sayısı|
|impactScore|Çift|Bu yazılımın maruz kalma puanı etkisi|
|
