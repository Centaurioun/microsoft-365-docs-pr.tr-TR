---
title: Gelişmiş tehdit avcılığı şeması başvurusu
description: Tehdit avcılığı sorguları çalıştırabileceğiniz verileri anlamak için gelişmiş tehdit avcılığı şemasındaki tablolar hakkında bilgi edinin.
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, mdatp, microsoft defender atp, uç nokta için microsoft defender, wdatp arama, sorgu, telemetri, şema başvurusu, kusto, tablo, veriler
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.subservice: mde
ms.openlocfilehash: d53f0cb437a79e4a6841293833dd0f76c014154d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679745"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de gelişmiş tehdit avcılığı şemasını anlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şeması, cihazlar ve diğer varlıklar hakkında olay bilgileri veya bilgiler sağlayan birden çok tablodan oluşur. Birden çok tabloya yayılan sorguları etkili bir şekilde oluşturmak için gelişmiş tehdit avcılığı şemasındaki tabloları ve sütunları anlamanız gerekir.

## <a name="get-schema-information-in-the-defender-for-cloud"></a>Bulut için Defender'da şema bilgilerini alma

Sorgu oluştururken, şemadaki her tablo hakkında hızla aşağıdaki bilgileri almak için yerleşik şema başvurularını kullanın:

- **Tablo açıklaması**: Tabloda yer alan verilerin türü ve bu verilerin kaynağı.
- **Sütunlar**: Tablodaki tüm sütunlar.
- **Eylem türleri**: Tablo tarafından desteklenen olay türlerini temsil eden sütundaki `ActionType` olası değerler. Bu değerler yalnızca olay bilgilerini içeren tablolar için sağlanır.
- **Örnek sorgu**: Tablonun nasıl kullanılabilmesini sağlayan örnek sorgular.

### <a name="access-the-schema-reference"></a>Şema başvurusuna erişme

Şema başvurusuna hızla erişmek için, şema gösteriminde tablo adının yanındaki **Başvuruyu görüntüle** eylemini seçin. Tablo aramak için **Şema başvurusu'nu** da seçebilirsiniz.

:::image type="content" source="images/ah-reference.png" alt-text="Gelişmiş avcılık sayfası" lightbox="images/ah-reference.png":::

## <a name="learn-the-schema-tables"></a>Şema tablolarını öğrenme

Aşağıdaki başvuruda gelişmiş tehdit avcılığı şemasındaki tüm tablolar listelenmiştir. Her tablo adı, o tablonun sütun adlarını açıklayan bir sayfaya bağlanır.

Tablo ve sütun adları, gelişmiş tehdit avcılığı ekranındaki şema gösteriminde Microsoft 365 Defender portalında da listelenir.

<br>

****

|Tablo adı|Açıklama|
|---|---|
|**[CihazUyarıEtkinlikleri](advanced-hunting-devicealertevents-table.md)**|Microsoft 365 Defender uyarıları |
|**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**|İşletim sistemi bilgileri de dahil olmak üzere cihaz bilgileri|
|**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**|Bağdaştırıcılar, IP ve MAC adreslerinin yanı sıra bağlı ağlar ve etki alanları da dahil olmak üzere cihazların ağ özellikleri|
|**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**|İşlem oluşturma ve ilgili olaylar|
|**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**|Ağ bağlantısı ve ilgili olaylar|
|**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**|Dosya oluşturma, değiştirme ve diğer dosya sistemi olayları|
|**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**|Kayıt defteri girdilerinin oluşturulması ve değiştirilmesi|
|**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**|Oturum açma işlemleri ve diğer kimlik doğrulama olayları|
|**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**|DLL yükleme olayları|
|**[DeviceEvents](advanced-hunting-deviceevents-table.md)**|Microsoft Defender Virüsten Koruma ve açıklardan yararlanma koruması gibi güvenlik denetimleri tarafından tetiklenen olaylar da dahil olmak üzere birden çok olay türü|
|**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**|Uç noktalarda sertifika doğrulama olaylarından alınan imzalı dosyaların sertifika bilgileri|
|**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**|Sürüm bilgileri ve destek sonu durumu da dahil olmak üzere cihazlarda yüklü yazılımların envanteri|
|**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**|Cihazlarda bulunan yazılım güvenlik açıkları ve her güvenlik açığını gideren kullanılabilir güvenlik güncelleştirmelerinin listesi|
|**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**|Açıklardan yararlanma kodunun genel kullanıma açık olup olmadığı da dahil olmak üzere genel olarak açıklanan güvenlik açıklarının bilgi bankası|
|**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**|Cihazlardaki çeşitli güvenlik yapılandırmalarının durumunu gösteren değerlendirme olaylarını Microsoft Defender Güvenlik Açığı Yönetimi|
|**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**|Defender Güvenlik Açığı Yönetimi tarafından cihazları değerlendirmek için kullanılan çeşitli güvenlik yapılandırmalarının bilgi bankası; çeşitli standartlara ve kıyaslamalara eşlemeler içerir|
|

> [!TIP]
> Uç Nokta, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve Defender verilerini kullanarak tehditleri avlamak için Microsoft 365 Defender [gelişmiş avcılığı](/microsoft-365/security/defender/advanced-hunting-overview) kullanın Kimlik için Microsoft Defender. [Microsoft 365 Defender açın](/microsoft-365/security/defender/m365d-enable).

Gelişmiş avcılık iş akışlarınızı Uç Nokta için Microsoft Defender'den Microsoft 365 Defender taşıma hakkında daha fazla bilgi için [bkz. Gelişmiş avcılık sorgularını Uç Nokta için Microsoft Defender geçirme](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
- [Özel algılamalara genel bakış](overview-custom-detections.md)
- [Gelişmiş tehdit avcılığı veri şeması değişiklikleri](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
