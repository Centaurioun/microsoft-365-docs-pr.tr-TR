---
title: Microsoft 365 Defender’ı açın
description: Microsoft 365 Defender etkinleştirmeyi ve güvenlik olayınızı ve yanıtınızı tümleştirmeye başlamayı öğrenin.
keywords: kullanmaya başlama, Microsoft 365 Defender etkinleştirme, Microsoft 365 Defender, M365, güvenlik, veri konumu, gerekli izinler, lisans uygunluğu, ayarlar sayfası
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-getstarted
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fa1a47bb5a4a09c22649866bb6c5c6039dc2850
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895041"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender’ı açın

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md), önemli özellikleri Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender arasında tümleştirerek olay yanıt sürecinizi birleştirir Microsoft Defender for Cloud Apps ve Kimlik için Microsoft Defender. Bu birleşik deneyim, Microsoft 365 Defender portalında erişebileceğiniz güçlü özellikler ekler.

Microsoft 365 Defender, gerekli izinlere sahip uygun müşteriler Microsoft 365 Defender portalı ziyaret ettiğinde otomatik olarak açılır. Çeşitli önkoşulları ve Microsoft 365 Defender nasıl sağlandığı hakkında bilgi edinmek için bu makaleyi okuyun.

## <a name="check-license-eligibility-and-required-permissions"></a>Lisans uygunluğu ve gerekli izinleri denetleme

Microsoft 365 güvenlik ürününün lisansı genellikle ek lisanslama maliyeti olmadan Microsoft 365 Defender kullanmanızı sağlar. Microsoft 365 E5, E5 Güvenlik, A5 veya A5 Güvenlik lisansı ya da desteklenen tüm hizmetlere erişim sağlayan geçerli bir lisans birleşimi almanızı öneririz.

Ayrıntılı lisanslama bilgileri için [lisanslama gereksinimlerini okuyun](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Rolünüzü denetleyin

Microsoft 365 Defender açmak için aşağıdaki rollerden biri olmanız gerekir:

- Genel Yönetici
- Güvenlik Yöneticisi
- Güvenlik İşleci
- Genel Okuyucu
- Güvenlik Okuyucusu
- Uyumluluk Yöneticisi
- Uyumluluk Verileri Yöneticisi
- Uygulama Yöneticisi
- Bulut Uygulaması Yöneticisi

[Azure AD'da rollerinizi görüntüleme](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Desteklenen hizmetler

Microsoft 365 Defender, önceden dağıttığınız çeşitli desteklenen hizmetlerden verileri toplar. Yeni içgörüleri tanımlamak ve merkezi yanıt iş akışlarını mümkün kılmak için verileri merkezi olarak işleyip depolar. Bunu, tümleşik hizmetlerle ilişkili mevcut dağıtımları, ayarları veya verileri etkilemeden yapar.

En iyi korumayı elde etmek ve Microsoft 365 Defender iyileştirmek için ağınıza tüm geçerli desteklenen hizmetleri dağıtmanızı öneririz. Daha fazla bilgi için [desteklenen hizmetleri dağıtma hakkında bilgi edinin](deploy-supported-services.md).

## <a name="onboard-to-the-service"></a>Hizmete ekleme
Microsoft 365 Defender'a eklemek basittir. Ekleme işlemini başlatmak için gezinti **menüsünden Olaylar & uyarıları**, **Tehdit Avcılığı**, **İşlem merkezi** veya **Tehdit analizi** gibi herhangi bir öğeyi seçin. 

### <a name="data-center-location"></a>Veri merkezi konumu

Microsoft 365 Defender verileri [Uç Nokta için Microsoft Defender tarafından kullanılan aynı konumda](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) depolar ve işler. Uç Nokta için Microsoft Defender yoksa, etkin Microsoft 365 güvenlik hizmetlerinin konumuna bağlı olarak yeni bir veri merkezi konumu otomatik olarak seçilir. Seçili veri merkezi konumu ekranda gösterilir.

Farklı bir veri merkezi konumunda Microsoft 365 Defender sağlama hakkında Microsoft desteğine başvurmak için Microsoft 365 Defender portalında **Yardım mı gerekiyor?** öğesini seçin.

> [!NOTE]
> Geçmişte Uç Nokta için Microsoft Defender Bulut için Microsoft Defender aracılığıyla açıldığında Avrupa Birliği (AB) veri merkezlerinde otomatik olarak sağlandı. Microsoft 365 Defender, geçmişte Uç Nokta için Defender'ı bu şekilde sağlayan müşteriler için aynı AB veri merkezinde otomatik olarak sağlanır.

### <a name="confirm-that-the-service-is-on"></a>Hizmetin açık olduğunu onaylayın

Hizmet sağlandıktan sonra şunları ekler:

- [Olay yönetimi](incidents-overview.md)
- [Uyarı sırası](investigate-alerts.md)
- [Otomatik araştırma ve yanıtı](m365d-autoir.md) yönetmek için bir işlem merkezi
- [Gelişmiş avcılık](advanced-hunting-overview.md) özellikleri
- Tehdit analizi

:::image type="content" source="../../media/overview-incident.png" alt-text="Microsoft 365 Defender portalında Microsoft 365 Defender özellikleri içeren gezinti bölmesi" lightbox="../../media/overview-incident.png":::
*Olay yönetimi ve diğer özelliklerle Microsoft 365 Defender portalı*

### <a name="getting-microsoft-defender-for-identity-data"></a>Kimlik için Microsoft Defender verileri alma 
Microsoft Defender for Cloud Apps ile tümleştirmeyi etkinleştirmek için en az bir kez Microsoft Defender for Cloud Apps oturum açmanız gerekir.

## <a name="get-assistance"></a>Yardım alma

Microsoft 365 Defender açma hakkında en sık sorulan soruların yanıtlarını almak için [SSS bölümünü okuyun](m365d-enable-faq.md).

Microsoft destek personeli, kiracınızdaki hizmetin ve ilgili kaynakların sağlanmasına veya sağlamasını kaldırmaya yardımcı olabilir. Yardım için Microsoft 365 Defender portalında **Yardım mı gerekiyor?** öğesini seçin. Desteğe başvururken Microsoft 365 Defender bahsedin.

## <a name="related-topics"></a>İlgili konular

- [Sık sorulan sorular](m365d-enable-faq.md)
- [Lisanslama gereksinimleri ve diğer önkoşullar](prerequisites.md)
- [Desteklenen hizmetleri dağıtın](deploy-supported-services.md)
- [Microsoft 365 Defender genel bakış](microsoft-365-defender.md)
- [Uç Nokta için Microsoft Defender genel bakış](../defender-endpoint/microsoft-defender-endpoint.md)
- [Office 365 için Defender genel bakış](../office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps genel bakış](/cloud-app-security/what-is-cloud-app-security)
- [Kimlik için Microsoft Defender genel bakış](/azure-advanced-threat-protection/what-is-atp)
- [Veri depolamayı Uç Nokta için Microsoft Defender](../defender-endpoint/data-storage-privacy.md)
