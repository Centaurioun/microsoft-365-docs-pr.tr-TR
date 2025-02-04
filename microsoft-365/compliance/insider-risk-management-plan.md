---
title: İçeriden risk yönetimi planı
description: Kuruluşunuzda insider risk yönetimi ilkelerini kullanmayı planlamayı öğrenin.
keywords: Microsoft 365, Microsoft Purview, insider riski, risk yönetimi, uyumluluk
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 6c49afa544e72110ff6646fc68f6ea3da498547d
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68767672"
---
# <a name="plan-for-insider-risk-management"></a>İçeriden risk yönetimi planı

> [!IMPORTANT]
> Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Kuruluşunuzda [insider risk yönetimine](insider-risk-management.md) başlamadan önce, bilgi teknolojisi ve uyumluluk yönetimi ekipleriniz tarafından gözden geçirilmesi gereken önemli planlama etkinlikleri ve dikkat edilmesi gereken noktalar vardır. Aşağıdaki alanlarda dağıtımı ayrıntılı bir şekilde anlamak ve planlamak, iç risk yönetimi özelliklerini uygulama ve kullanımınızın sorunsuz bir şekilde ilerlemesini ve en iyi yöntemlerle uyumlu olmasını sağlamaya yardımcı olur. 

Daha fazla bilgi edinmek ve kuruluşunuzdaki riskli etkinlikleri ele almak için planlama sürecine genel bakış için bkz. [Insider risk yönetimi programı başlatma](https://download.microsoft.com/download/b/2/0/b208282a-2482-4986-ba07-15a9b9286df0/pwc-starting-an-insider-risk-management-program-with-pwc-and-microsoft.pdf).

Insider risk yönetimi iş akışının kuruluşunuzun kuruluşunuzun değerlerini, kültürünü ve kullanıcı deneyimini öncelik sırasına getirirken riskleri engellemesine, algılamasına ve içermesine nasıl yardımcı olabileceğini öğrenmek için aşağıdaki videoyu izleyin:


>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

Kuruluşunuzdaki kullanıcıların veri risklerini en aza indirmeye yardımcı olmak için insider risk yönetimi ve iletişim uyumluluğunun birlikte nasıl çalıştığına ilişkin [Microsoft Mechanics videosunu](https://www.youtube.com/watch?v=Ynkfu8OF0wQ) inceleyin.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="work-with-stakeholders-in-your-organization"></a>Kuruluşunuzdaki paydaşlarla çalışma

Şirket içi risk yönetimi uyarılarında ve olaylarında eylem gerçekleştirmeye yönelik işbirliği yapmak için kuruluşunuzdaki uygun paydaşları belirleyin. İlk planlama ve uçtan uca [şirket içi risk yönetimi iş akışı](insider-risk-management.md#workflow) dahil olmak üzere dikkate alınması önerilen bazı paydaşlar kuruluşunuzun aşağıdaki alanlarından kişilerdir:

- Bilgi teknolojisi
- Uyumluluk
- Gizlilik
- Güvenlik
- İnsan kaynakları
- Yasal

## <a name="determine-any-regional-compliance-requirements"></a>Bölgesel uyumluluk gereksinimlerini belirleme

Farklı coğrafi ve kuruluş alanlarında, kuruluşunuzun diğer alanlarından farklı uyumluluk ve gizlilik gereksinimleri olabilir. İç risk yönetimindeki uyumluluk ve gizlilik denetimlerini ve kuruluşunuzun farklı alanlarında nasıl kullanılmaları gerektiğini anlamalarını sağlamak için bu alanlardaki paydaşlarla birlikte çalışın. Bazı senaryolarda uyumluluk ve gizlilik gereksinimleri, bazı paydaşları bir kullanıcı veya yasal düzenleme veya alan için ilke gereksinimlerine göre araştırmalardan ve davalardan tanımlayan veya kısıtlayan ilkeler gerektirebilir.

Belirli bölgelerde, rollerde veya bölümlerdeki kullanıcıları kapsayan araştırmalarda belirli paydaşların yer almasına yönelik gereksinimleriniz varsa, farklı bölgeleri ve popülasyonları hedefleyen ayrı (aynı olsa bile) [şirket içi risk yönetimi ilkeleri](insider-risk-management-policies.md) uygulamak isteyebilirsiniz. Bu yapılandırma, doğru paydaşların rolleri ve bölgeleriyle ilgili servis taleplerini önceliklendirmelerini ve yönetmelerini kolaylaştırır. Araştırmacıların ve gözden geçirenlerin kullanıcılarla aynı dili konuştuğu bölgeler için süreçler ve ilkeler oluşturmayı düşünebilirsiniz. Bu da iç risk yönetimi uyarıları ve durumları için yükseltme sürecini kolaylaştırmaya yardımcı olabilir.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Gözden geçirme ve araştırma iş akışını planlama

Insider risk yönetimi ilkelerini ve uyarılarını nasıl yönetmek istediğinize bağlı olarak, farklı iç risk yönetimi özellikleri kümelerini yönetmek için kullanıcıları belirli rol gruplarına atamanız gerekir. Şirket içi risk yönetimi özelliklerinin farklı alanlarını yönetmek için farklı uyumluluk sorumluluklarına sahip kullanıcıları belirli rol gruplarına atama seçeneğiniz vardır. Ya da belirlenen yöneticiler, analistler, araştırmacılar ve izleyiciler için tüm kullanıcı hesaplarını Insider Risk Management rol grubuna atamaya karar vekleyebilirsiniz. Uyumluluk yönetimi gereksinimlerinize en uygun tek bir rol grubu veya birden çok rol grubu kullanın.

Insider risk yönetimiyle çalışırken aşağıdaki rol grubu seçeneklerinden ve çözüm eylemlerinden birini seçin:

|**Eylem**|**Insider Risk Management**|**Insider Risk Management Yönetici**|**İçeriden Risk Yönetimi Analistleri**|**İçeriden Risk Yönetimi Araştırmacıları**|**Insider Risk Management Denetçileri**|**Insider Risk Yönetimi Onaylayanları**|
|---|---|---|---|---|---|---|
|İlkeleri ve ayarları yapılandırma|Evet|Evet|Hayır|Hayır|Hayır|Hayır|
|Analiz içgörülerine erişme|Evet|Evet|Evet|Hayır|Hayır|Hayır|
|Uyarılara erişme ve uyarıları araştırma|Evet|Hayır|Evet|Evet|Hayır|Hayır|
|Olaylara erişme ve olayları araştırma|Evet|Hayır|Evet|Evet|Hayır|Hayır|
|İçerik Gezgini'ne erişme ve görüntüleme|Evet|Hayır|Hayır|Evet|Hayır|Hayır|
|Bildirim şablonlarını yapılandırma|Evet|Hayır|Evet|Evet|Hayır|Hayır|
|Denetim günlüklerini görüntüleme ve dışarı aktarma|Evet|Hayır|Hayır|Hayır|Evet|Hayır|
|Adli kanıt yakalamalarına erişme ve görüntüleme|Evet|Hayır|Hayır|Evet|Hayır|Hayır|
|Adli kanıt yakalama isteği oluşturma|Evet|Evet|Hayır|Hayır|Hayır|Hayır|
|İstekleri yakalamaya yönelik adli kanıtları onaylama|Evet|Hayır|Hayır|Hayır|Hayır|Evet|
|Cihaz durumu raporunu görüntüleme|Evet|Evet|Hayır|Hayır|Hayır|Hayır|

> [!IMPORTANT]
> *Insider Risk Management* veya *Insider Risk Management Yönetici* rol gruplarında her zaman en az bir kullanıcınız olduğundan emin olun (seçtiğiniz seçeneğe bağlı olarak), kuruluşunuzdan ayrılan belirli kullanıcılar için insider risk yönetimi yapılandırmanızın 'sıfır yönetici' senaryosuna girmemesini sağlayın.

Aşağıdaki rollerin üyeleri kullanıcıları insider risk yönetimi rol gruplarına atayabilir ve *Insider Risk Management Yönetici* rol grubuna dahil olan çözüm izinlerine sahip olabilir:

- Azure Active Directory *Genel Yöneticisi*
- Azure Active Directory *Uyumluluk Yöneticisi*
- Microsoft Purview uyumluluk portalı *Kuruluş Yönetimi*
- *Microsoft Purview uyumluluk portalı Uyumluluk Yöneticisi*

## <a name="understand-requirements-and-dependencies"></a>Gereksinimleri ve bağımlılıkları anlama

Insider risk yönetimi ilkelerini nasıl uygulamayı planladığınıza bağlı olarak, uygun Microsoft 365 lisanslama aboneliklerine sahip olmanız ve bazı çözüm önkoşullarını anlamanız ve planlamanız gerekir.

**Lisans:** Insider risk yönetimi, microsoft 365 lisanslama aboneliklerinin geniş bir yelpazesinin bir parçası olarak kullanılabilir. Ayrıntılar için [Insider risk yönetimi ile çalışmaya başlama](insider-risk-management-configure.md#subscriptions-and-licensing) makalesine bakın.

> [!IMPORTANT]
> Insider risk yönetimi şu anda coğrafi bölgelerde barındırılan kiracılarda ve Azure hizmet bağımlılıkları tarafından desteklenen ülkelerde kullanılabilir. Kuruluşunuzda insider risk yönetiminin desteklendiğini doğrulamak için bkz. [Ülkeye/bölgeye göre Azure bağımlılığı kullanılabilirliği](/troubleshoot/azure/general/dependency-availability-by-country).

Mevcut bir Microsoft 365 Kurumsal E5 planınız yoksa ve içeriden risk yönetimini denemek istiyorsanız, [microsoft 365'i](/office365/admin/try-or-buy-microsoft-365) mevcut aboneliğinize ekleyebilir veya E5 Microsoft 365 Kurumsal [deneme sürümüne kaydolabilirsiniz](https://www.microsoft.com/microsoft-365/enterprise).

**İlke şablonu gereksinimleri:** Seçtiğiniz ilke şablonuna bağlı olarak, kuruluşunuzda insider risk yönetimini yapılandırmadan önce aşağıdaki gereksinimleri anladığınızdan ve buna göre planlama yaptığınızdan emin olmanız gerekir:

- **Kullanıcılardan ayrılarak veri hırsızlığı** şablonunu kullanırken, kuruluşunuzdaki kullanıcıların istifa ve sonlandırma tarihi bilgilerini düzenli aralıklarla içeri aktarmak için bir Microsoft 365 İK bağlayıcısı yapılandırmanız gerekir. Microsoft 365 HR bağlayıcısını yapılandırmaya yönelik adım adım yönergeler için [İk bağlayıcısı ile verileri içeri aktarma](import-hr-data.md) makalesine bakın.
- **Veri sızıntıları** şablonunu kullanırken, kuruluşunuzdaki hassas bilgileri tanımlamak ve Yüksek Önem Derecesi DLP ilkesi uyarıları için içeriden risk uyarıları almak için en az bir Microsoft Purview Veri Kaybı Önleme (DLP) ilkesi yapılandırmanız gerekir. DLP ilkelerini yapılandırmaya yönelik adım adım yönergeler için [DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md) makalesine bakın.
- **Güvenlik ilkesi ihlali** şablonunu kullanırken, güvenlik ihlali uyarılarını içeri aktarmak için Defender Güvenlik Merkezi'nde insider risk yönetimi tümleştirmesi için Uç Nokta için Microsoft Defender etkinleştirmeniz gerekir. Uç Nokta için Defender tümleştirmesini insider risk yönetimiyle etkinleştirmeye yönelik adım adım yönergeler için bkz. [Uç Nokta için Microsoft Defender'de gelişmiş özellikleri yapılandırma](/windows/security/threat-protection/microsoft-defender-atp/advanced-features).
- **Riskli kullanıcı** şablonunu kullanırken, kuruluşunuzdaki kullanıcıların performans veya indirgeme durumu bilgilerini düzenli aralıklarla içeri aktarmak için bir Microsoft 365 İK bağlayıcısı yapılandırmanız gerekir. Microsoft 365 HR bağlayıcısını yapılandırmaya yönelik adım adım yönergeler için [İk bağlayıcısı ile verileri içeri aktarma](import-hr-data.md) makalesine bakın.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Üretim ortamında küçük bir kullanıcı grubuyla test edin

Bu çözümü üretim ortamınızda geniş bir şekilde etkinleştirmeden önce, kuruluşunuzda gerekli uyumluluk, gizlilik ve yasal incelemeler için yürütürken ilkeleri küçük bir dizi üretim kullanıcısı ile test etmeyi düşünmelisiniz. Test ortamında insider risk yönetimini değerlendirmek için, önceliklendirme ve işleme durumlarına yönelik uyarılar oluşturmak üzere sanal kullanıcı eylemleri ve diğer sinyaller oluşturmanız gerekir. Bu yaklaşım birçok kuruluş için pratik olmayabilir, bu nedenle üretim ortamındaki küçük bir kullanıcı grubuyla içeriden risk yönetimini test etmenizi öneririz.

Araç içinde gizliliği korumak için bu test sırasında kullanıcı görünen adlarını insider risk yönetim konsolunda anonimleştirmek için ilke ayarlarında anonimleştirme özelliğini etkin tutun. Bu ayar, ilke eşleşmeleri olan kullanıcıların gizliliğini korumaya yardımcı olur ve şirket içi risk uyarıları için veri araştırma ve analiz incelemelerinde nesnelliği artırmaya yardımcı olabilir.

Insider risk yönetimi ilkesini yapılandırdıktan hemen sonra herhangi bir uyarı görmüyorsanız, bu minimum risk eşiğinin henüz karşılanmadığı anlamına gelebilir. **İlkenin** tetiklendiğini ve beklendiği gibi çalıştığını doğrulamak ve kullanıcıların ilke kapsamında olup olmadığını görmek için Kullanıcılar sayfasını denetleyin.

## <a name="resources-for-stakeholders"></a>Paydaşlar için kaynaklar

Insider risk yönetimi belgelerini, kuruluşunuzdaki yönetim ve düzeltme iş akışınıza dahil olan paydaşlarla paylaşın:

- [İçeriden risk ilkeleri oluşturma ve yönetme](insider-risk-management-policies.md)
- [İçeriden risk etkinliklerini araştırma](insider-risk-management-activities.md)
- [İçeriden risk vakalarında eyleme geçme](insider-risk-management-cases.md)
- [Insider riski İçerik gezgini ile olay verilerini gözden geçirme](insider-risk-management-content-explorer.md)
- [İçeriden risk bildirimi şablonları oluşturma](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Başlamaya hazır mısınız?

Kuruluşunuz için insider risk yönetimini yapılandırmaya hazır mısınız? Aşağıdaki makaleleri gözden geçirmenizi öneririz:

- Genel ilke ayarlarını yapılandırmak için [insider risk yönetimi ayarlarını kullanmaya başlayın](insider-risk-management-settings.md).
- Önkoşulları yapılandırmak, ilkeler oluşturmak ve uyarıları almaya başlamak için [insider risk yönetimini kullanmaya başlayın](insider-risk-management-configure.md).
- Kuruluşunuzda adli kanıt yakalamayı yapılandırmaya yönelik adım adım yönergeler için [insider risk yönetimi adli kanıtlarını kullanmaya başlayın](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure).
