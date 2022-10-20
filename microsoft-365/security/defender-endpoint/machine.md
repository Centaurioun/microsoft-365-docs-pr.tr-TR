---
title: Makine kaynak türü
description: Uç Nokta için Microsoft Defender'de Makine kaynak türünün yöntemleri ve özellikleri hakkında bilgi edinin.
keywords: api'ler, desteklenen API'ler, alma, makineler
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
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 45adfa1f023cfd32947f5b090535cc0ebc3ccbee
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68624147"
---
# <a name="machine-resource-type"></a>Makine kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Yöntemler

|Yöntem|Dönüş Türü|Açıklama|
|---|---|---|
|[Makineleri listele](get-machines.md)|[makine](machine.md) koleksiyonu|Kuruluştaki [makine](machine.md) varlıklarının listesi.|
|[Makine alma](get-machine-by-id.md)|[Makine](machine.md)|Kimliğine göre [bir makine](machine.md) edinin.|
|[Kullanıcılara oturum açma](get-machine-log-on-users.md)|[kullanıcı](user.md) koleksiyonu|[Makinede](machine.md) oturum açan [Kullanıcı](user.md) kümesini alın.|
|[İlgili uyarıları alma](get-machine-related-alerts.md)|[uyarı](alerts.md) koleksiyonu|[Makinede](machine.md) tetiklenen [uyarı](alerts.md) varlıkları kümesini alın.|
|[Yüklü yazılımı al](get-installed-software.md)|[yazılım](software.md) koleksiyonu|Belirli bir makine kimliğiyle ilgili yüklü yazılım koleksiyonunu alır.|
|[Keşfedilen güvenlik açıklarını al](get-discovered-vulnerabilities.md)|[güvenlik açığı](vulnerability.md) koleksiyonu|Belirli bir makine kimliğiyle ilgili bulunan güvenlik açıkları koleksiyonunu alır.|
|[Güvenlik önerileri al](get-security-recommendations.md)|[öneri](recommendation.md) koleksiyonu|Belirli bir makine kimliğiyle ilgili güvenlik önerileri koleksiyonunu alır.|
|[Makine etiketlerini ekle veya kaldır](add-or-remove-machine-tags.md)|[Makine](machine.md)|Belirli bir makineye etiket ekleyin veya kaldırın.|
|[IP'ye göre makineleri bul](find-machines-by-ip.md)|[makine](machine.md) koleksiyonu|IP ile görülen makineleri bulun.|
|[Makineleri etikete göre bul](find-machines-by-tag.md)|[makine](machine.md) koleksiyonu|[Makineleri Etikete](machine-tags.md) göre bulun.|
|[Eksik KB'leri al](get-missing-kbs-machine.md)|KB koleksiyonu|Makine kimliğiyle ilişkili eksik KB'lerin listesini alma|
|[Cihaz değerini ayarla](set-device-value.md)|[makine](machine.md) koleksiyonu|[Bir cihazın değerini](tvm-assign-device-value.md) ayarlayın.|
|[Makineyi güncelleştir](update-machine-method.md)|[makine](machine.md) koleksiyonu|Makinenin güncelleştirme durumunu alma.|

## <a name="properties"></a>Özellikler

|Özellik|Tür|Açıklama|
|---|---|---|
|Kimliği|Dize|[makine](machine.md) kimliği.|
|computerDnsName|Dize|[makine](machine.md) tam adı.|
|firstSeen|Datetimeoffset|[makinenin](machine.md) Uç Nokta için Microsoft Defender tarafından gözlemlendiği ilk tarih ve saat.|
|lastSeen|Datetimeoffset|Son alınan tam cihaz raporunun saati ve tarihi. Bir cihaz genellikle 24 saatte bir tam rapor gönderir.|
|osPlatform|Dize|İşletim sistemi platformu.|
|onboardingstatus|Dize|Makine ekleme durumu. Olası değerler şunlardır: "onboarded", "CanBeOnboarded", "Unsupported", and "InsufficientInfo".|
|osProcessor|Dize|İşletim sistemi işlemcisi. Bunun yerine osArchitecture özelliğini kullanın.|
|Sürüm|Dize|İşletim sistemi Sürümü.|
|osBuild|Boş değer atanabilir uzun|İşletim sistemi derleme numarası.|
|lastIpAddress|Dize|[Makinedeki](machine.md) yerel NIC'de son IP.|
|lastExternalIpAddress|Dize|[Makinenin](machine.md) İnternet'e erişildiği son IP.|
|healthStatus|Enum|[makine](machine.md) sistem durumu. Olası değerler şunlardır: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" ve "Unknown".|
|rbacGroupName|Dize|Makine grubu Adı.|
|rbacGroupId|Dize|Makine grubu kimliği.|
|riskScore|Null Atanabilir Sabit Listesi|risk puanı Uç Nokta için Microsoft Defender tarafından değerlendirildi. Olası değerler şunlardır: 'Yok', 'Bilgilendirici', 'Düşük', 'Orta' ve 'Yüksek'.|
|aadDeviceId|Null atanabilir gösterim Guid'i|AAD Cihaz Kimliği ( [makine](machine.md) AAD'ye Katılmış olduğunda).|
|machineTags|Dize koleksiyonu|[Makine](machine.md) etiketleri kümesi.|
|exposureLevel|Null Atanabilir Sabit Listesi|Uç Nokta için Microsoft Defender tarafından değerlendirilen maruz kalma düzeyi. Olası değerler şunlardır: 'Yok', 'Düşük', 'Orta' ve 'Yüksek'.|
|deviceValue|Null Atanabilir Sabit Listesi|[Cihazın değeri](tvm-assign-device-value.md). Olası değerler şunlardır: 'Normal', 'Düşük' ve 'Yüksek'.|
|ipAddresses|IpAddress koleksiyonu|***IpAddress*** nesneleri kümesi. Bkz. [Makine alma API'si](get-machines.md).|
|osArchitecture|Dize|İşletim sistemi mimarisi. Olası değerler şunlardır: "32 bit", "64 bit". osProcessor yerine bu özelliği kullanın.|
