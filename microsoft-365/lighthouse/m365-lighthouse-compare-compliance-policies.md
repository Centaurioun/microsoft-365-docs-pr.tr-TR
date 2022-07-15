---
title: Microsoft 365 Lighthouse'de cihaz uyumluluk ilkesi ayarlarını karşılaştırma
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için cihaz uyumluluk ilkesi ayarlarını karşılaştırmayı öğrenin.
ms.openlocfilehash: 0a0c5127a86832637a16449e06c3df70299b49a3
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822911"
---
# <a name="compare-device-compliance-policy-settings-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'de cihaz uyumluluk ilkesi ayarlarını karşılaştırma

Microsoft 365 Lighthouse, kiracılarınız genelinde uyumluluk ilkelerini tek bir görünümde görüntülemenizi sağlar. İlkeleri karşılaştırarak kiracılarınız arasında güvenlik ve standartlaştırmayı yönlendirebilirsiniz. Yapılandırılmış ayarları (yapılandırılmamış kalan ayarların yerine), yapılandırmalarında farklılık gösteren ayarları veya eşleşen ayarları görmek için görünümleri filtreleyebilirsiniz. Ayrıca, ilkeler arasında nasıl karşılaştırdıklarını görmek için belirli ayarları da arayabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Cihazların Microsoft Intune lisansı olduğundan ve Microsoft Endpoint Manager'a (MEM) kayıtlı olduğundan emin olun.

## <a name="compare-policy-settings"></a>İlke ayarlarını karşılaştırma

1. Lighthouse'un sol gezinti bölmesinde **Cihazlar Cihaz** > **Uyumluluğu'nu** seçin.

2. **İlkeler** sekmesini seçin.

3. **Filtreler** açılan listesinden bir işletim sistemi veya platform seçin.

   > [!NOTE]
   > İlkeleri yalnızca aynı işletim sistemi veya platformla karşılaştırabilirsiniz.

4. Filtrelenmiş listeden karşılaştırmak istediğiniz en fazla üç ilkeyi seçin.

5. **Karşılaştır'ı** seçin.

**Farklı ayarlar**, **Eşleşen Ayarlar** veya **Yapılandırılan ayarlar'ı** görmek için sonuçları filtreleyebilirsiniz.

## <a name="configure-a-policy-setting"></a>İlke ayarını yapılandırma

1. Lighthouse'un sol gezinti bölmesinde **Cihazlar Cihaz** > **Uyumluluğu'nu** seçin.

2. **İlkeler** sekmesini seçin.

3. Listeden bir ilke adı seçin.

4. İlke ayrıntıları bölmesinde **Bu ilkeyi Microsoft Endpoint Manager'de görüntüle'yi** seçin.

5. MEM'de ilke ayarlarını gerektiği gibi düzenleyin.

## <a name="next-steps"></a>Sonraki adımlar

İlke ayarlamaları yaparken, değişikliklerinizi geçerli temel ayarlarınıza göre değerlendirdiğinizden emin olun. Daha fazla bilgi için bkz. [Standart kiracı yapılandırmalarını dağıtmak için temelleri kullanmaya genel bakış](m365-lighthouse-deploy-standard-tenant-configurations-overview.md).

## <a name="related-content"></a>İlgili içerik

[Intune'da cihaz kaydı nedir?](/mem/intune/enrollment/device-enrollment) (makale)  
[Intune ile yönettiğiniz cihazlar için kurallar ayarlamak için uyumluluk ilkelerini kullanma](/mem/intune/protect/device-compliance-get-started) (makale)  
[Standart kiracı yapılandırmalarını dağıtmak için Microsoft 365 Lighthouse temellerini kullanmaya genel bakış](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (makale)
