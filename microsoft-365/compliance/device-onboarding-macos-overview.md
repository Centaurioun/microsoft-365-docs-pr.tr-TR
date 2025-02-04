---
title: macOS cihazlarının Microsoft 365'e katılımına genel bakış
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MET150
description: macOS cihazlarını Uyumluluk çözümlerine ekleme hakkında bilgi edinin
ms.openlocfilehash: 9966ed77aac5935cabc2bc33b4738f35107610e4
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621783"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview"></a>macOS cihazlarının Microsoft 365'e katılımına genel bakış

MacOS cihazları, Intune veya JAMF Pro kullanılarak Microsoft Purview çözümlerine eklenebilir. Ekleme yordamları, kullandığınız yönetim çözümüne bağlı olarak farklılık gösterir. macOS cihazlarınız zaten Uç Nokta için Microsoft Defender (MDE) içine eklendiyse, daha az adım vardır. Sizin için uygun yordamlara bağlantılar için [sonraki adımlar](#next-steps) bölümüne bakın.

**Şunlar için geçerlidir:**

- [Uç nokta veri kaybı önleme (DLP)](./endpoint-dlp-learn-about.md)
- [İçeriden risk yönetimi](insider-risk-management.md)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Başlamadan önce

macOS cihazlarda Uç Nokta DLP'sini kullanmaya başlamadan önce (en son yayınlanan üç sürüm), şu makaleler hakkında bilgi sahibi olmanız gerekir:

- [Uç nokta veri kaybı önleme hakkında daha fazla bilgi edinme](endpoint-dlp-learn-about.md)
- [Uç noktada veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md)

DLP hakkında hiç bilginiz yoksa, bu makaleleri de tanımanız gerekir:

- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Veri kaybı önlemeyi planlama (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Veri kaybı önleme ilkesi referansı](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Insider Risk hakkında bilginiz yoksa, şu makaleler hakkında bilgi sahibi olmanız gerekir:

 - [İçeriden risk yönetimi](insider-risk-management.md)
 - [İçeriden risk yönetimi planı](insider-risk-management-plan.md#plan-for-insider-risk-management)

macOS cihazlarınız zaten Intune veya JAMF Pro aracılığıyla yönetilmelidir.
 
- Intune eklemek için bkz[. Dağıtım kılavuzu: Microsoft Intune'da macOS cihazlarını yönetme](/mem/intune/fundamentals/deployment-guide-platform-macos) ve [Mac'inizi Intune Şirket Portalı ile kaydetme](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- JAMF Pro'ya eklemek için bkz. [JAMF Pro yönetici kılavuzu](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) ve [Mac için JAMF Pro Yükleme ve Yapılandırma Kılavuzu](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
<!--- Install the v95+ Edge browser on your macOS devices--> 

### <a name="supported-browsers"></a>Desteklenen tarayıcılar

Uç nokta DLP macOS'ta bu tarayıcıları destekler (en son yayınlanan üç sürüm):

- Microsoft Edge (en son sürüm)
- Safari (en son sürüm, yalnızca macOS)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

## <a name="licensing-guidance"></a>Lisanslama kılavuzu

[Bilgi koruması için bkz. Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

## <a name="activities-that-can-be-audited-and-restricted-on-macos"></a>macOS üzerinde denetlenebilen ve kısıtlanabilir etkinlikler 

Bir macOS cihazı Microsoft Purview çözümlerine eklendikten sonra, veri kaybı önleme (DLP) ilkeleriyle bu eylemleri izleyebilir ve kısıtlayabilirsiniz.

**USB çıkarılabilir medyaya kopyalama** – bu eylem zorunlu kılındığında, korumalı dosyaların bir uç nokta cihazından USB çıkarılabilir medyaya kopyalanmasını veya taşınmasını engeller, uyarır veya denetler 

**Ağ paylaşımlarına kopyala** – bu eylem uygulandığında, korumalı dosyaların bir uç nokta cihazından herhangi bir ağ paylaşımına kopyalanmasını veya taşınmasını engeller, uyarır veya denetler 

**Yazdır** – bu eylem uygulandığında, korumalı dosyalar bir uç nokta cihazından yazdırıldığında engeller, uyarır veya denetler 

**Panoya kopyala** – bu eylem uygulandığında, bir uç nokta cihazında panoya kopyalanan korumalı dosyadaki verileri engeller, uyarır veya denetler 

**Buluta yükleme** – Bu eylem, genel ayarlardaki izin verilen/izin verilmeyen etki alanları listesine göre korumalı dosyaların bulut hizmetlerine yüklenmesi veya yüklenmesine izin verildiğinde engeller, uyarır veya denetler. Bu eylem uyaracak veya engelleyecek şekilde ayarlandığında, diğer tarayıcıların (Genel ayarlar altındaki izin verilmeyen tarayıcılar listesinde tanımlanır) dosyaya erişmesi engellenir. 

**İzin verilmeyen uygulamalar tarafından erişilir** – bu eylem zorunlu kılındığında, izin verilmeyen uygulamalar listesinde (Genel ayarlarda tanımlandığı gibi) bulunan uygulamaların bir uç nokta cihazındaki korumalı dosyalara erişmesini engeller. Örnek senaryolar 

## <a name="onboarding-devices-into-device-management"></a>Cihazları cihaz yönetimine ekleme

Cihazdaki hassas öğeleri izleyebilmeniz ve koruyabilmeniz için önce cihaz izlemeyi etkinleştirmeniz ve uç noktalarınızı eklemeniz gerekir. Bu eylemlerin ikisi de Microsoft Purview uyumluluk portalı yapılır.

Henüz eklenmemiş cihazları eklemek istediğinizde, uygun betiği indirir ve bu cihazlara dağıtırsınız. <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) **Ayarlar** sayfasını açın ve **Cihaz izlemeyi etkinleştir'i** seçin.

   > [!NOTE]
   > Cihaz eklemenin etkinleştirilmesi genellikle yaklaşık 60 saniye sürer ancak lütfen Microsoft desteğiyle etkileşime geçmeden önce 30 dakikaya kadar bekleyin.

2. Uyumluluk Merkezi ayarları sayfasını açın ve **macOS cihaz izlemeyi aç'ı** seçin.

## <a name="next-steps"></a>Sonraki adımlar

DLP algılayıcı telemetrisini almak ve veri kaybı önleme ilkelerini uygulamak için cihazların Microsoft Purview çözümlerine dahil edilmesi gerekir. 

Konu | Açıklama
:---|:---
|[Intune](device-onboarding-offboarding-macos-intune.md)|Intune aracılığıyla yönetilen macOS cihazları için
|[Uç Nokta için Microsoft Defender müşterileri için Intune](device-onboarding-offboarding-macos-intune-mde.md) |Intune aracılığıyla yönetilen ve bunlara Uç Nokta için Microsoft Defender (MDE) dağıtılmış macOS cihazları için
|[JAMF Pro](device-onboarding-offboarding-macos-jamfpro.md) | JAMF Pro aracılığıyla yönetilen macOS cihazları için
|[Uç Nokta için Microsoft Defender için JAMF Pro](device-onboarding-offboarding-macos-jamfpro-mde.md)|JAMF Pro aracılığıyla yönetilen ve bunlara Uç Nokta için Microsoft Defender (MDE) dağıtılmış macOS cihazları için


## <a name="related-topics"></a>İlgili konular

- [Uç noktada veri kaybı önlemeyi kullanma](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft uygulamaları genelinde DLP ilkesi ipuçları için Destek Matrisi](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
