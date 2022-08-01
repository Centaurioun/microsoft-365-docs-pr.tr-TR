---
title: Veri yönetimi çözümü dağıtma
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365solution-overview
- m365solution-mig
- m365initiative-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Uyumluluk veya mevzuat gereksinimleri için verilerinizi yönetmek üzere kuruluşunuz için Microsoft Purview'u dağıtmaya yönelik açıklayıcı kılavuz.
ms.openlocfilehash: 90832541bf202f062b44c1ec375fb20d3db654c3
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106021"
---
# <a name="deploy-a-data-governance-solution-with-microsoft-purview"></a>Microsoft Purview ile veri idaresi çözümü dağıtma

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Uyumluluk veya mevzuat gereksinimleri için Microsoft 365 verilerinizi yönetmek için **Microsoft Purview Veri Yaşam Döngüsü Yönetimi** (eski adıYla Microsoft Information Governance) ve **Microsoft Purview Kayıt Yönetimi** kullanın.

![Microsoft Purview ile veri idaresi çözümü dağıtma adımlarına genel bakış](../media/data-governance-solution-overview.png)

Çok bulutlu ve hizmet olarak yazılım (SaaS) dahil olmak üzere veri varlığınız genelinde verileri eşleyen ve yöneten veri idaresi için [Microsoft Purview Veri Eşlemesi, Microsoft Purview Veri Kataloğu ve Microsoft Purview Data Estate Analizler](/azure/purview/overview).

Veri koruma çözümü için bkz. [Microsoft Purview ile bilgi koruma çözümü dağıtma](information-protection-solution.md).

## <a name="licensing"></a>Lisanslama

Lisanslama gereksinimlerinizi ve seçeneklerinizi anlamak için, microsoft 365'te sunulan güvenlik & uyumluluğu kılavuzunun [Microsoft Purview Veri Yaşam Döngüsü Yönetimi & Microsoft Purview Kayıt Yönetimi](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management) özellik düzeyi lisans gereksinimleri bölümüne bakın.

## <a name="keep-what-you-need-and-delete-what-you-dont"></a>İhtiyacınız olanı tutun ve istemediğinizi silin

![Veri yaşam döngüsü yönetimi çözümü için adımlar](../media/data-lifecycle-management-solution.png)

Microsoft Purview Veri Yaşam Döngüsü Yönetimi **(eski** adıYla Microsoft Information Governance) kullanarak ihtiyacınız olanları koruyun ve silmeyin.

|Adım|Açıklama|Daha fazla bilgi|
|:---|:----------|:---------------|
|1| Microsoft 365 hizmetlerinde saklama ve silme işlemlerinin nasıl çalıştığını anlama. <br /><br /> Bekletme ilkelerini ve bekletme etiketlerini nasıl kullanabileceğinizi anladıktan sonra, bekletme ilkesi gerektiren iş yüklerinizi ve özel durumlar için bekletme etiketleri oluşturmanız gerekip gerekmediğini belirleyin. | [Bekletme ilkeleri ve bekletme etiketleri hakkında bilgi edinin](retention.md)|
|2| Özel durumlar için bekletme ilkeleri ve gerekirse bekletme etiketleri oluşturun. <br /><br /> En yaygın kullanılan bekletme ilkeleri Exchange, SharePoint, Teams, Microsoft 365 Grupları ve Yammer'dır. Belgeler ve e-postalar için özel durumlar yapılandırabilirsiniz. | [Saklama ilkeleri oluşturma](create-retention-policies.md) <p> [Özel durumlarınız için bekletme etiketleri oluşturma ve uygulama](create-retention-labels-information-governance.md)|
|3| Posta kutularını yönetme. <br /><br /> Arşivleme ve otomatik arşivleme için posta kutularını etkinleştirin, e-postalar arşiv posta kutusuna taşındığında özelleştirmeniz gerekip gerekmediğini düşünün ve kullanıcılar kuruluştan ayrıldığında posta kutularını devre dışı bırakın.| [Arşiv posta kutularını etkinleştirme](enable-archive-mailboxes.md) <p> [Otomatik genişleyen arşivlemeyi etkinleştirme](enable-autoexpanding-archiving.md) <p> [Etkin olmayan posta kutuları oluşturma ve yönetme](create-and-manage-inactive-mailboxes.md)|
|4| PST dosyalarını çevrimiçi posta kutularına aktar.  <br /><br /> Yönetmek istediğiniz verileri içeren PST dosyalarınız varsa, ağ yükleme veya sürücü gönderimi kullanarak bunları içeri aktarabilirsiniz.| [Kuruluşunuzun PST dosyalarını içeri aktarmak için ağ karşıya yükleme özelliğini kullanma](use-network-upload-to-import-pst-files.md) <p> [Kuruluşunuzun PST dosyalarını içeri aktarmak için sürücü gönderimini kullanma](use-drive-shipping-to-import-pst-files-to-office-365.md)|

Bu çözümdeki özellikler hakkında daha fazla bilgi edinmek için bkz. [Veri yaşam döngüsü yönetimi hakkında bilgi edinin](information-governance.md).

## <a name="manage-high-value-items"></a>Yüksek değerli öğeleri yönetme

![Kayıt yönetimi çözümü için adımlar](../media/records-management-solution.png)

kuruluşunuzun iş, yasal veya mevzuat kaydı tutma gereksinimleri için yüksek değerli öğelerini yönetmek için **Microsoft Purview Kayıt Yönetimi** kullanın.

|Adım|Açıklama|Daha fazla bilgi|
|:---|:----------|:---------------|
|1| Kayıt yönetimi çözümünü anlama. <br /><br /> Daha esnek yapılandırma seçenekleriyle bekletme etiketlerini kullanın ve gerektiğinde öğeleri kayıt olarak bildirin. | [Kayıt yönetimi hakkında daha fazla bilgi edinme](records-management.md)|
|2| Bekletme zamanlamalarınızı yönetmek için dosya planını kullanın. <br /><br /> Dosya planı, bekletme etiketlerini etkileşimli olarak oluşturmanıza veya toplu olarak içeri aktarmanıza ve analiz için dışarı aktarmanıza olanak tanır. Dosya planıyla oluşturduğunuz etiketler, iş veya mevzuat gereksinimlerini belirlemenize ve izlemenize yardımcı olacak ek yönetim bilgilerini destekler. | [Bekletme etiketleri oluşturmak ve yönetmek için dosya planını kullanma](file-plan-manager.md)|
|3| Bekletme etiketlerinizi uygulayın. <br /><br /> Bekletme etiketleriniz el ile veya uygulamalarda otomatik olarak yayımlanabilir ve uygulanabilir ya da hassas bilgilere, anahtar sözcüklere veya aranabilir özelliklere, eğitilebilir sınıflandırıcılara veya bulut eklerine göre otomatik olarak uygulanabilir. |[Bekletme etiketlerini yayımlama ve uygulamalarda uygulama](create-apply-retention-labels.md) <p> [İçeriğe otomatik olarak bekletme etiketi uygulama](apply-retention-labels-automatically.md)|
|4| Verilerin kalıcı olarak silinmesini yönetin. <br /><br /> Verilerin eğilimi olarak bilinen içerik kalıcı olarak silinmeden önce el ile gözden geçirilmesini gerektirebilir ve kayıtlar için ayrıştırma kanıtı sağlayabilirsiniz. |[İçerik eğilimini yönetme](disposition.md)|

> [!TIP]
> Kayıt yönetimi tarafından desteklenen ek [yapılandırmalar için yaygın senaryoların](get-started-with-records-management.md#common-scenarios) listesini gözden geçirin.

Bu çözümdeki özellikler hakkında daha fazla bilgi edinmek için bkz. [Kayıt yönetimi hakkında bilgi edinin](records-management.md).

## <a name="training-resources"></a>Eğitim kaynakları

Danışmanlar ve yöneticiler için öğrenme modülleri:

- [Microsoft Purview'da bilgi koruma ve veri yaşam döngüsü yönetimine giriş](/learn/modules/m365-compliance-information-governance)
- [Microsoft Purview'da veri yaşam döngüsünü yönetme](/learn/modules/m365-compliance-information-govern-information/)
- [Microsoft Purview'da kayıtları yönetme](/learn/modules/m365-compliance-information-manage-records/)

Bu çözümler dağıtıldığında kullanıcıları desteklemeye yönelik belgeler için [veri yaşam döngüsü yönetimi](get-started-with-information-governance.md#end-user-documentation) ve [kayıt yönetimi](get-started-with-records-management.md#end-user-documentation) için son kullanıcı belgeleri bölümlerine bakın.