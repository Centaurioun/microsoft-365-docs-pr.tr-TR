---
title: Microsoft 365 Defender gelişmiş tehdit avcılığı şemasındaki veri tabloları
description: Tehdit avcılığı sorguları çalıştırabileceğiniz verileri anlamak için gelişmiş tehdit avcılığı şemasındaki tablolar hakkında bilgi edinin
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, veriler
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 2fb0ebc9b3bc095a7cf0eb76fe4440283e175b7f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639587"
---
# <a name="understand-the-advanced-hunting-schema"></a>Gelişmiş tehdit avcılığı şemasını anlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) şeması, cihazlar, uyarılar, kimlikler ve diğer varlık türleri hakkında olay bilgileri veya bilgi sağlayan birden çok tablodan oluşur. Birden çok tabloya yayılan sorguları etkili bir şekilde oluşturmak için gelişmiş tehdit avcılığı şemasındaki tabloları ve sütunları anlamanız gerekir.

<a name="get-schema-information-in-the-security-center"></a>

## <a name="get-schema-information"></a>Şema bilgilerini alma

Sorgu oluştururken, şemadaki her tablo hakkında hızla aşağıdaki bilgileri almak için yerleşik şema başvurularını kullanın:

- **Tablo açıklaması**: Tabloda yer alan verilerin türü ve bu verilerin kaynağı.
- **Sütunlar**— tablodaki tüm sütunlar.
- **Eylem türleri**— tablo tarafından desteklenen olay türlerini temsil eden sütundaki `ActionType` olası değerler. Bu bilgiler yalnızca olay bilgilerini içeren tablolar için sağlanır.
- **Örnek sorgu**; tablonun nasıl kullanılabilmesini sağlayan örnek sorgular.

### <a name="access-the-schema-reference"></a>Şema başvurusuna erişme
Şema başvurusuna hızla erişmek için, şema gösteriminde tablo adının yanındaki **Başvuruyu görüntüle** eylemini seçin. Tablo aramak için **Şema başvurusu'nu** da seçebilirsiniz.

:::image type="content" source="../../media/understand-schema-1.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Tehdit Avcılığı sayfasındaki Şema Başvurusu sayfası" lightbox="../../media/understand-schema-1.png":::

## <a name="learn-the-schema-tables"></a>Şema tablolarını öğrenme
Aşağıdaki başvuru şemadaki tüm tabloları listeler. Her tablo adı, o tablonun sütun adlarını açıklayan bir sayfaya bağlanır. Tablo ve sütun adları, gelişmiş tehdit avcılığı ekranındaki şema gösteriminin bir parçası olarak Bulut için Defender'da da listelenir.

| Tablo adı | Açıklama |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Uyarılarla ilişkili dosyalar, IP adresleri, URL'ler, kullanıcılar veya cihazlar |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender, Microsoft Defender for Cloud Apps ve Kimlik için Microsoft Defender uyarıları , önem derecesi bilgileri ve tehdit kategorisi dahil  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Office 365 ve diğer bulut uygulamaları ve hizmetlerindeki hesapları ve nesneleri içeren olaylar |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Microsoft Defender Virüsten Koruma ve açıklardan yararlanma koruması gibi güvenlik denetimleri tarafından tetiklenen olaylar da dahil olmak üzere birden çok olay türü |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Uç noktalarda sertifika doğrulama olaylarından alınan imzalı dosyaların sertifika bilgileri |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Dosya oluşturma, değiştirme ve diğer dosya sistemi olayları |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL yükleme olayları |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | İşletim sistemi bilgileri de dahil olmak üzere makine bilgileri |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Cihazlarda oturum açma işlemleri ve diğer kimlik doğrulama olayları |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Ağ bağlantısı ve ilgili olaylar |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Fiziksel bağdaştırıcılar, IP ve MAC adreslerinin yanı sıra bağlı ağlar ve etki alanları da dahil olmak üzere cihazların ağ özellikleri |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | İşlem oluşturma ve ilgili olaylar |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Kayıt defteri girdilerinin oluşturulması ve değiştirilmesi |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Cihazlardaki çeşitli güvenlik yapılandırmalarının durumunu gösteren değerlendirme olaylarını Microsoft Defender Güvenlik Açığı Yönetimi |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | cihazları değerlendirmek için Microsoft Defender Güvenlik Açığı Yönetimi tarafından kullanılan çeşitli güvenlik yapılandırmalarının bilgi bankası; çeşitli standartlara ve karşılaştırmalara yönelik eşlemeleri içerir  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Sürüm bilgileri ve destek sonu durumu da dahil olmak üzere cihazlarda yüklü yazılımların envanteri |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Cihazlarda bulunan yazılım güvenlik açıkları ve her güvenlik açığını gideren kullanılabilir güvenlik güncelleştirmelerinin listesi |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Açıklardan yararlanma kodunun genel kullanıma açık olup olmadığı da dahil olmak üzere genel olarak açıklanan güvenlik açıklarının bilgi bankası |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | E-postalara eklenen dosyalar hakkında bilgi |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | E-posta teslimi ve engelleyici olaylar da dahil olmak üzere Microsoft 365 e-posta olayları |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 e-postaları alıcı posta kutusuna teslim ettikten sonra teslim sonrası gerçekleşen güvenlik olayları |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | E-postalardaki URL'ler hakkında bilgi |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Active Directory (AD) çalıştıran bir şirket içi etki alanı denetleyicisini içeren olaylar. Bu tablo, etki alanı denetleyicisindeki kimlikle ilgili olayları ve sistem olaylarını kapsar. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory dahil olmak üzere çeşitli kaynaklardan gelen hesap bilgileri |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory ve Microsoft çevrimiçi hizmetler kimlik doğrulama olayları |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Kullanıcılar, gruplar, cihazlar ve etki alanları gibi Active Directory nesneleri için sorgular |

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında avlayın](advanced-hunting-query-emails-devices.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)
