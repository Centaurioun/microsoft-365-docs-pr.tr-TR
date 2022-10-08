---
title: 6. Adım. Cihaz riskini ve güvenlik temel hatlarına uyumluluğu izleyin
ms.author: bcarter
author: brendacarter
f1.keywords:
- connect Intune to Defender
- monitor device risk
- monitor device compliance
- deploy security baselines
manager: dougeby
audience: ITPro
description: Uç Nokta için Defender'a Microsoft Intune bağlamayı ve erişim koşulu olarak cihaz riskini izlemeyi öğrenin.
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- deploy security baselines
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: a532477d25d0eb3de07af08033f13c7a8112454c
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986564"
---
# <a name="step-6-monitor-device-risk-and-compliance-to-security-baselines"></a>6. Adım. Cihaz riskini ve güvenlik temel hatlarına uyumluluğu izleyin

Kuruluşunuz Uç Nokta için Microsoft Defender dağıttıktan sonra, Microsoft Intune Uç Nokta için Defender ile tümleştirerek cihazlarınız hakkında daha fazla içgörü ve koruma elde edebilirsiniz. Mobil cihazlar için bu, erişim koşulu olarak cihaz riskini izleme özelliğini içerir. Windows cihazları için bu cihazların güvenlik temellerine uyumluluğunu izleyebilirsiniz. 

Uç Nokta için Microsoft Defender dağıtımı, ekleme uç noktalarını içerir. Uç noktaları eklemek için Intune kullandıysanız (önerilir), Microsoft Intune Zaten Uç Nokta için Defender'a bağlamışsınızdır. Uç Nokta için Defender'a uç noktaları eklemek için farklı bir yöntem kullandıysanız, [Intune ile Uç Nokta için Microsoft Defender](/mem/intune/protect/advanced-threat-protection-configure) arasında hizmet-hizmet bağlantısını ayarladığınızdan emin olmak için bkz. Intune'de Uç Nokta için Microsoft Defender yapılandırma. 


![Uç Nokta için Defender ve Microsoft Intune tümleştirme çizimi](../media/devices/devices-defender-for-endpoint-steps.png#lightbox)

Bu çizimde:
- Uç Nokta için Microsoft Defender, cihazlar için tehdit korumasının karmaşıklık düzeyini büyük ölçüde artırır. 
- Microsoft Intune, Uygulama Koruma İlkeleri ayarlamanıza ve cihazları yönetmenize (yapılandırma değişiklikleri dahil) olanak tanırken, Uç Nokta için Defender cihazlarınızı sürekli olarak tehditlere karşı izler ve saldırıları düzeltmek için otomatik eylem gerçekleştirebilir. 
- Uç Nokta için Defender'a cihaz eklemek için Intune kullanabilirsiniz. Bunu yaptığınızda, bu cihazların Microsoft Purview Endpoint veri kaybı önleme (Endpoint DLP) ile çalışmasını da sağlarsınız.

Bu makale şu adımları içerir:
- Cihaz riskini izleme
- Güvenlik temellerine uyumluluğu izleme

Uç Nokta için Defender henüz ayarlanmamışsa, [değerlendirme ve pilot ortamı ayarlamak](../security/defender/eval-defender-endpoint-overview.md) için tehdit koruması yöneticinizle birlikte çalışın. Bu makaledeki özellikleri denemek için pilot grupla çalışabilirsiniz.

## <a name="monitor-device-risk-as-a-condition-for-access"></a>Erişim koşulu olarak cihaz riskini izleme

Uç Nokta için Microsoft Defender dağıtıldığında tehdit riski sinyallerinden yararlanabilirsiniz. Bu, risk puanına göre cihazlara erişimi engellemenize olanak tanır. Microsoft, orta veya daha düşük risk puanına sahip cihazlara erişime izin vermenizi önerir.

Android ve iOS/iPadOS için tehdit sinyalleri Uygulama Koruma İlkeleriniz (APP) içinde kullanılabilir. Bunu yapılandırma hakkında bilgi için bkz. [Cihaz risk düzeyini ayarlamak için uygulama koruma ilkesi oluşturma ve atama](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level).

Tüm platformlar için mevcut cihaz uyumluluk ilkelerinde risk düzeyini ayarlayabilirsiniz. Bkz. [Koşullu erişim ilkesi oluşturma](/mem/intune/protect/advanced-threat-protection-configure#create-a-conditional-access-policy).

## <a name="deploy-security-baselines-and-monitor-compliance-to-these-settings"></a>Güvenlik temellerini dağıtma ve bu ayarlara uyumluluğu izleme

Şunlar için geçerlidir: Windows 10, Windows 11

[5. Adım makalesi. Yapılandırma profillerini dağıtın](manage-devices-with-intune-configuration-profiles.md), Windows 10 ve Windows 11 için kullanılabilen güvenlik temellerini kullanarak yapılandırma profillerini kullanmaya başlamanızı önerir. Uç Nokta için Microsoft Defender ayrıca uç nokta algılama ve yanıt (EDR) ayarları da dahil olmak üzere Uç Nokta için Defender yığınındaki tüm güvenlik denetimlerini iyileştirici ayarlar sağlayan güvenlik temelleri içerir. Bunlar Microsoft Intune kullanılarak da dağıtılır.

İdeal olarak, Uç Nokta için Defender'a eklenen cihazlar her iki taban çizgisine de dağıtılır: Başlangıçta Windows'un güvenliğini sağlamak için Windows Intune güvenlik temeli ve ardından Uç Nokta için Defender güvenlik denetimlerini en iyi şekilde yapılandırmak için üst katmanda yer alan Uç Nokta için Defender güvenlik temeli.

Riskler ve tehditlerle ilgili en son verilerden yararlanmak ve temeller geliştikçe çakışmaları en aza indirmek için, kullanıma sunuldukları anda her zaman temellerin en son sürümlerini tüm ürünlere uygulayın. 

Uç Nokta için Defender'ı kullanarak bu temellere uyumluluğu izleyebilirsiniz. 

![Güvenlik temellerine uyumluluğu izleme kartı](../media/devices/secconmgmt-baseline-card.png#lightbox)

Güvenlik temellerini dağıtmak ve bu ayarlara uyumluluğu izlemek için bu tablodaki adımları kullanın.


|Adım  |Açıklama  |
|---------|---------|
|1     |Temel kavramları gözden geçirin ve Uç Nokta için Microsoft Defender ve Windows Intune güvenlik temellerini karşılaştırın. <br><br>Önerileri öğrenmek için bkz. [Uç Nokta için Microsoft Defender güvenlik temeline uyumluluğu artırma](../security/defender-endpoint/configure-machines-security-baseline.md).<br><br>Kullanılabilir güvenlik temelleri listesini ve çakışmaları nasıl önleyeceklerini gözden geçirmek için bkz. [Intune'da Windows cihazlarını yapılandırmak ](/mem/intune/protect/security-baselines) için güvenlik temellerini kullanma.         |
|2     |  Intune için Windows güvenlik temeli ayarlarını dağıtın. 5. Adım'daki yönergeleri izlediyseniz bunu zaten başarmış olabilirsiniz [. Yapılandırma profillerini dağıtma](manage-devices-with-intune-configuration-profiles.md).        |
|3    |  Intune için Uç Nokta için Defender temel ayarlarını dağıtın. Profili oluşturmak ve temel sürümü seçmek için bkz. [Microsoft Intune güvenlik temeli profillerini yönetme](/mem/intune/protect/security-baselines-configure).<br><br>Buradaki yönergeleri de izleyebilirsiniz: [Uç Nokta için Microsoft Defender güvenlik temelini gözden geçirin ve atayın](../security/defender-endpoint/configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline).     |
|4     | Uç Nokta için Defender'da [cihaz yapılandırma yönetiminde Güvenlik temeli kartını](../security/defender-endpoint/configure-machines.md) gözden geçirin.          |


## <a name="next-steps"></a>Sonraki adımlar
[7. Adım'a gidin. Uç noktalarda bilgi koruma özellikleriyle DLP uygulayın](manage-devices-with-intune-dlp-mip.md).