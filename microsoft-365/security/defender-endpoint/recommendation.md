---
title: Öneri yöntemleri ve özellikleri
description: En son uyarıları alır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
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
ms.openlocfilehash: ad1864850b8953be424836b270349821d6fe3783
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632612"
---
# <a name="recommendation-resource-type"></a>Öneri kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Yöntemler

<br>

****

|Yöntem|Dönüş Türü|Açıklama|
|---|---|---|
|[Tüm önerileri listele](get-all-recommendations.md)|Öneri koleksiyonu|Kuruluşu etkileyen tüm güvenlik önerilerinin listesini alır|
|[Kimlikle öneri al](get-recommendation-by-id.md)|Öneri|Güvenlik önerisini kimliğine göre alır|
|[Öneri yazılımı alma](list-recommendation-software.md)|[Yazılım](software.md)|Belirli bir yazılımla ilgili güvenlik önerisini alır|
|[Öneri cihazları alma](get-recommendation-machines.md)|MachineRef koleksiyonu|Güvenlik önerisiyle ilişkili cihazların listesini alır|
|[Öneri güvenlik açıklarını alma](get-recommendation-vulnerabilities.md)|[Güvenlik açığı](vulnerability.md) koleksiyonu|Güvenlik önerisiyle ilişkili güvenlik açıklarının listesini alır|
|

## <a name="properties"></a>Özellikler

<br>

****

|Özellik|Tür|Açıklama|
|---|---|---|
|Kimliği|Dize|Öneri Kimliği|
|Productname|Dize|İlgili yazılım adı|
|recommendationName|Dize|Öneri adı|
|Zayıf|Uzun|Bulunan güvenlik açıklarının sayısı|
|Satıcı|Dize|İlgili satıcı adı|
|recommendedVersion|Dize|Önerilen sürüm|
|önerilenProgram|Dize|Önerilen program|
|önerilenVendor|Dize|Önerilen satıcı|
|recommendationCategory|Dize|Öneri kategorisi. Olası değerler şunlardır: "Hesaplar", "Uygulama", "Ağ", "İşletim Sistemi", "SecurityControls"|
|Alt kategori|Dize|Öneri alt kategorisi|
|severityScore|Çift|Yapılandırmanın kuruluşun Cihazlar için Microsoft Güvenli Puanına olası etkisi (1-10)|
|publicExploit|Boole|Genel güvenlik açığından yararlanma kullanılabilir|
|activeAlert|Boole|Etkin uyarı bu öneriyle ilişkilendirilir|
|associatedThreats|Dize koleksiyonu|Tehdit analizi raporu bu öneriyle ilişkilendirilir|
|remediationType|Dize|Düzeltme türü. Olası değerler şunlardır: "ConfigurationChange","Update","Upgrade","Uninstall"|
|Durum|Enum|Öneri özel durum durumu. Olası değerler şunlardır: "Etkin" ve "Özel Durum"|
|configScoreImpact|Çift|Cihazlar için Microsoft Güvenli Puanı etkisi|
|exposureImpact|Çift|Maruz kalma puanı etkisi|
|totalMachineCount|Uzun|Yüklü cihaz sayısı|
|exposedMachinesCount|Uzun|Güvenlik açıklarına maruz kalan yüklü cihaz sayısı|
|nonProductivityImpactedAssets|Uzun|Etkilenmeyen cihaz sayısı|
|relatedComponent|Dize|İlgili yazılım bileşeni|
|
