---
title: Microsoft Purview Veri Yaşam Döngüsü Yönetimi hakkında bilgi edinin
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
description: Microsoft Purview Veri Yaşam Döngüsü Yönetimi ihtiyacınız olanı korumanıza ve silmenize nasıl yardımcı olduğunu öğrenin.
ms.openlocfilehash: 6252bb9824a534ffca5f295bf9f9c54816bcb320
ms.sourcegitcommit: a1c86e51f6fec7517356251c3b99b1a86705c8c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2022
ms.locfileid: "67336698"
---
# <a name="learn-about-data-lifecycle-management"></a>Veri yaşam döngüsü yönetimi hakkında bilgi edinme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft Purview Veri Yaşam Döngüsü Yönetimi (eski adıYla Microsoft Information Governance), saklamanız gereken içeriği saklamanız ve saklamadığınız içeriği silmeniz için size araçlar ve özellikler sağlar. 

İçerikleri tutmak ve silmek genellikle uyumluluk ve mevzuat gereksinimleri için gereklidir, ancak artık iş değeri olmayan içerikleri silmek de risk ve sorumluluğu yönetmenize yardımcı olur. Örneğin, saldırı yüzeyinizi azaltır.

## <a name="microsoft-365-features"></a>Microsoft 365 özellikleri

**Bekletme ilkeleri** , veri yaşam döngüsü yönetiminin temel taşıdır. Exchange, SharePoint, OneDrive, Teams ve Yammer içeren Microsoft 365 iş yükleri için bu ilkeleri kullanın. Bu hizmetlere yönelik içeriğin süresiz olarak mı, kullanıcılar tarafından düzenlenip silinmeyeceği belirli bir süre için mi tutulacaklarını yapılandırın. Veya ilkeyi, henüz silinmemişse, belirli bir süre sonra içeriği otomatik olarak kalıcı olarak silecek şekilde yapılandırabilirsiniz. Ayrıca bu iki eylemi alıkoyma ve silme işlemleri için birleştirebilirsiniz. Bu çok tipik bir yapılandırmadır. Örneğin, e-postayı üç yıl boyunca tutun ve ardından silin.

Bekletme ilkesi yapılandırırken, kuruluşunuzdaki tüm örnekleri (tüm posta kutuları ve tüm SharePoint siteleri gibi) veya tek tek örnekleri (yalnızca belirli departmanların veya bölgelerin posta kutuları veya yalnızca seçili SharePoint siteleri gibi) hedefleyebilirsiniz.

Yasal belgeler için daha uzun saklama süresi gibi tek tek e-postalar veya belgeler için özel durumlara ihtiyacınız varsa, bunu uygulamalarda yayımladığınız **bekletme etiketleriyle** yaparsınız; böylece kullanıcılar bunları uygulayabilir veya içeriği inceleyerek bunları otomatik olarak uygularsınız.

Bekletme ilkeleri ve bekletme etiketleri ve Microsoft 365'te bekletmenin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Bekletme ilkeleri ve bekletme etiketleri hakkında bilgi edinin](retention.md). 

> [!NOTE]
> İş, yasal veya mevzuat kaydı tutma gereksinimleri için yüksek değerli öğeleri yönetmeniz gerekiyorsa, veri yaşam döngüsü yönetimiyle bekletme etiketleri yerine [kayıt yönetimiyle](records-management.md) bekletme etiketlerini kullanın.

İhtiyacınız olanı korumanıza ve silmenize yardımcı olan diğer veri yaşam döngüsü yönetimi özellikleri:

- **Kullanıcılara** ek posta kutusu depolama alanı sağlamak için posta kutusu arşivleme ve 100 GB'tan fazla depolama alanı gerektiren posta kutuları için arşivlemeyi otomatik olarak genişletme. Varsayılan arşivleme ilkesi e-postayı otomatik olarak arşiv posta kutusuna taşır ve gerekirse bu ilkeyi özelleştirebilirsiniz. Posta kutusu arşivleme hakkında daha fazla bilgi için bkz. [Arşiv posta kutuları hakkında bilgi edinin](archive-mailboxes.md).
    
- Çalışanlar kuruluştan ayrıldıktan sonra posta kutusu içeriğini koruyan **etkin olmayan posta kutuları**. Etkin olmayan posta kutuları hakkında daha fazla bilgi için bkz. [Etkin olmayan posta kutuları hakkında bilgi edinin](inactive-mailboxes-in-office-365.md).

- Ağ yükleme veya sürücü gönderimi kullanarak **PST dosyaları için hizmeti içeri aktarabilirsiniz**. Daha fazla bilgi için bkz. [Kuruluşunuzun PST dosyalarını içeri aktarma hakkında bilgi edinin](importing-pst-files-to-office-365.md).

## <a name="exchange-legacy-features"></a>Exchange (eski) özellikleri

**Bekletme ilkeleri ve** mesajlaşma kayıtları yönetiminden (MRM) elde tutma etiketleri ve **günlük oluşturma kuralları** , Başlangıçta Klasik Exchange yönetim merkezinden yapılandırılabilen Exchange'in eski uyumluluk özellikleridir. Yeni [Exchange yönetim merkezine](/exchange/features-in-new-eac) getirilmemişlerdir.

Bu özellikleri henüz kullanmıyorsanız veya veri yaşam döngüsü yönetimi için Microsoft 365 özellikleri yerine bunları kullanmak için belirli bir iş gereksiniminiz varsa, bu eski uyumluluk özelliklerini kullanmanızı önermeyiz. Bunun yerine, verileri yerinde koruyan ve diğer Microsoft 365 hizmetlerinde ilkeleri destekleyen daha yeni Microsoft 365 özelliklerini kullanın.

Daha fazla bilgi için bkz. [Eski özellikler yerine bekletme ilkelerini ve bekletme etiketlerini kullanma](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features).


## <a name="deployment-guidance"></a>Dağıtım kılavuzu

Önerilen dağıtım yol haritası, lisans bilgileri, izinler, desteklenen senaryoların listesi ve son kullanıcı belgelerini içeren veri yaşam döngüsü yönetimine yönelik dağıtım kılavuzu için bkz. [Veri yaşam döngüsü yönetimini kullanmaya başlama](get-started-with-information-governance.md).

Verilerinizi korumak için dağıtım kılavuzu mu arıyorsunuz? Bkz [. Microsoft Purview ile bilgi koruma çözümü dağıtma](information-protection-solution.md).

