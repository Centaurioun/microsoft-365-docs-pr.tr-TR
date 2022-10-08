---
title: Microsoft 365 Lighthouse'daki yenilikler
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP' ler) için her ay Microsoft 365 Lighthouse eklenen, değiştirilen ve düzeltilmiş olanlara bakın.
ms.openlocfilehash: 65fba4d7cdef2b1afc8935f6833e10e04dee616f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68197051"
---
# <a name="whats-new-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'daki yenilikler

[Microsoft 365 Lighthouse](m365-lighthouse-overview.md) sürekli olarak yeni özellikler ekliyor, öğrendiğimiz sorunları düzeltiyoruz ve geri bildiriminize göre değişiklikler yapıyoruz. Ne üzerinde çalıştığımızı keşfetmek için bu makaleyi gözden geçirin.

> [!NOTE]
> Bazı özellikler müşterilerimiz için farklı hızlarda kullanıma sunulur. Henüz bir özellik görmüyorsanız, yakında görmeniz gerekir.

## <a name="september-2022"></a>Eylül 2022

### <a name="fully-automated-setup-of-microsoft-defender-for-business"></a>İş için Microsoft Defender tam otomatik kurulumu

İş için Microsoft Defender ile müşteri kiracılarınızı ayarlamanıza yardımcı olan varsayılan taban çizgisine tam otomatik bir adım ekledik. Bu adım, kiracınızı İş için Microsoft Defender için otomatik olarak sağlar ve İş için Microsoft Defender Intune kayıtlı cihazları otomatik olarak ekler.

### <a name="capability-to-filter-the-multifactor-authentication-mfa-list-to-show-relevant-user-accounts"></a>Çok Faktörlü Kimlik Doğrulaması (MFA) listesini ilgili kullanıcı hesaplarını gösterecek şekilde filtreleme özelliği

Çok Faktörlü Kimlik Doğrulaması sayfası artık kullanıcı hesabı listesini hesap türüne göre (örneğin Yönetici, Üye veya Konuk) filtrelemeyi destekliyor. Hizmet hesapları veya acil durum erişim hesapları gibi diğer hesapları da listeden dışlayabilirsiniz. Bu işleve erişmek için **Kullanıcılar** > **Çok Faktörlü kimlik doğrulaması'na** gidin, kiracı ayrıntıları bölmesini açmak için listeden bir kiracı seçin ve ardından **MFA için kayıtlı olmayan kullanıcılar** sekmesini seçin. Bu filtreleme ve dışlama özellikleri, ilgili kullanıcı hesaplarına odaklanmanıza yardımcı olur. 

### <a name="capability-to-act-on-security-incidents-and-alerts"></a>Güvenlik olayları ve uyarıları üzerinde işlem yapma özelliği

Artık **Cihaz güvenliği** >  Olaylar ve uyarılar sayfasında gösterilen olaylar **ve uyarılar** üzerinde işlem yapabilirsiniz. Şu anda desteklenen eylemler arasında olayı veya uyarıyı kendinize atamak ya da olayı ya da uyarıyı çözümlemek yer alır. 

## <a name="august-2022"></a>Ağustos 2022

### <a name="view-and-manage-inactive-user-accounts"></a>Etkin olmayan kullanıcı hesaplarını görüntüleme ve yönetme 

Microsoft 365 Lighthouse artık yönetilen kiracılarınızdaki tüm etkin olmayan kullanıcı hesaplarının listesini sağlar. Listeye erişmek için, Microsoft 365 Lighthouse sol gezinti bölmesinden **Etkin Olmayan Kullanıcılar'ı**  >  seçin. Hala etkin olan ancak son altı ay içinde kullanılmayan hesapları izlemek ve temizlemek için bu listeyi kullanarak güvenlik risklerini azaltabilirsiniz. 

### <a name="microsoft-edge-policy-deployment"></a>Microsoft Edge ilke dağıtımı   

Varsayılan taban çizgisine bir Microsoft Edge ilke dağıtım görevi ekledik. Bu dağıtım görevi, kimlik avına ve kötü amaçlı yazılımlara karşı yerleşik koruma içeren Edge güvenlik ayarlarıyla müşteri kiracınızın tarayıcılarının güvenliğini sağlamanızı sağlar. Microsoft Edge'in, Windows 10 veya sonraki sürümleri çalıştıran cihazlara sahip küçük ve orta ölçekli işletmeler için Google Chromium'dan daha güvenli olduğu kanıtlanmıştır.

Daha fazla bilgi için bkz. [İşletmeniz için Microsoft Edge güvenliği](/deployedge/ms-edge-security-for-business).

## <a name="july-2022"></a>Temmuz 2022

### <a name="enhanced-baseline-deployment"></a>Gelişmiş temel dağıtım

Microsoft 365 Lighthouse artık aşağıdakiler sayesinde tüm yönetilen kiracılarınıza taban çizgisi dağıtımını daha hızlı ve kolay hale getirir:

- Atanan her görevin durumunu otomatik olarak algılama ve raporlama
- Durum raporlamasını birleştirme ve dağıtım durumunu belirleyen mantığı basitleştirme
- Hangi görevlerin tamamlandığı ve hangi görevlerin dikkat etmeniz gerektiğini raporlama
- Geçerli görevler için kullanıcı düzeyinde dağıtım durumunu raporlama
- Kiracının içinden mevcut yapılandırmaları algılama ve bunları taban çizgisiyle karşılaştırma
- Kapatılan görevlerle ilgili ayrıntıları sağlama
- Atanan görevi tamamlamak için ek lisanslamanın gerekli olduğu yeri belirleme

## <a name="june-2022"></a>Haziran 2022

### <a name="support-for-microsoft-365-e5-customers"></a>Microsoft 365 E5 müşterileri için destek

Microsoft 365 E5 müşterileri Microsoft 365 Lighthouse eklemenizi sağlamak için ekleme gereksinimlerimizi değiştirdik. Microsoft 365 Lighthouse'nin ekleme için desteklediği genişletilmiş lisans listesi Microsoft 365 İş Ekstra, Microsoft 365 E3, Microsoft 365 E5, İş için Microsoft Defender ve İş için Windows 365. Bu lisanslardan en az birine sahip olan müşteriler, temsilci erişim izinleri gereksinimlerini karşılar ve Microsoft 365 Lighthouse'de yönetilebilen lisanslı kullanıcı sayısı üst sınırını aşmaz.  

Gereksinimlerin tam listesi için bkz[. Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md).

### <a name="microsoft-defender-for-business-integration"></a>İş için Microsoft Defender tümleştirmesi

Microsoft 365 Lighthouse artık İş için Microsoft Defender ile tümleştirerek İş için Microsoft Defender sahip tüm müşteri kiracılarınız için ilgili içgörüler ve yönetim özellikleri sunar. İş için Microsoft Defender eklenen müşteri cihazlarının listesini görmek için Microsoft 365 Lighthouse sol gezinti bölmesinde **Cihazlar'ı** seçin. Müşteri kiracılarınızda bayrak eklenmiş olayların ve uyarıların listesini görmek için **Cihazlar** > **Cihaz Güvenliği'ne** gidin ve **Olaylar ve uyarılar** sekmesini seçin.  

Ayrıca, müşteri kiracılarınız için İş için Microsoft Defender ayarlamanıza yardımcı olması için varsayılan taban çizgisine bir adım ekledik. Bu adımı görmek için, Microsoft 365 Lighthouse sol gezinti bölmesinde **Temeller'i** seçin veya müşteri kiracılarınızdan herhangi birinin dağıtım planını görüntüleyin.

### <a name="status-of-quarantined-email-messages"></a>Karantinaya alınan e-posta iletilerinin durumu

Yönetilen kiracılarınız için e-posta karantina verilerine yeni işlevler ekledik. Microsoft 365 Lighthouse sol gezinti bölmesinde **Veri koruması'nı** seçerek erişilebilen bu özellik, müşteri kiracılarınız genelinde karantinaya alınan e-posta iletilerinin durumunu görünür hale getirmenizi sağlar. Eylem gerektirebilecek tüm kiracıları önceliklendirmenize yardımcı olmak için toplam karantina birimlerine ilişkin birleştirilmiş bilgileri ve her yönetilen kiracı için ayrıntılı bilgileri görebilirsiniz.

### <a name="increase-in-maximum-license-limit"></a>En yüksek lisans sınırında artış

Müşteri ekleme için maksimum lisans sınırını bir kez daha artırarak Microsoft 365 Lighthouse'de daha fazla müşterinizi yönetmeyi mümkün hale getiriyoruz. 2500'e kadar kullanıcı lisansına sahip müşteriler artık Microsoft 365 Lighthouse eklenebilir. Gelecek Microsoft 365 Lighthouse sürümlerde bu gereksinimi değerlendirmeye devam edeceğiz. 

Daha fazla bilgi için bkz[. Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md).

## <a name="may-2022"></a>Mayıs 2022

### <a name="redesigned-left-navigation-pane"></a>Yeniden tasarlanan sol gezinti bölmesi

Sol gezinti bölmesine yeni bir görünüm Microsoft 365 Lighthouse verdik. Riskli kullanıcılar, Cihaz uyumluluğu ve Tehdit yönetimi gibi ilgili alt düğümleri gösterecek şekilde genişleyen Kiracılar, Kullanıcılar ve Cihazlar gibi üst düzey düğümlere sahip şık bir tasarım göreceksiniz. Bu gezinti modeli, diğer Microsoft 365 yönetim merkezleri tarafından kullanılan modelle uyumlu hale getirir.

### <a name="enriched-user-details-pane"></a>Zenginleştirilmiş kullanıcı ayrıntıları bölmesi

Daha fazla kullanıcı bilgisi ve kullanıcıları daha iyi yönetmek için gerçekleştirebileceğiniz daha fazla eylem eklemek için kullanıcı ayrıntıları bölmesini yeniden tasarladık. Artık Microsoft 365 yönetim merkezi kullanıcı ayrıntıları bölmesiyle aynı genel görünüme sahiptir. Microsoft 365 Lighthouse'daki kullanıcı ayrıntıları bölmesine erişmek için sol gezinti bölmesinde **Kullanıcılar'ı** seçin ve ardından **Kullanıcıları ara** veya **Riskli kullanıcılar'ı** seçin. Ayrıntılar bölmesini açmak için herhangi bir kullanıcıyı seçin.

## <a name="april-2022"></a>Nisan 2022

### <a name="delegated-access-type-and-roles-on-tenants-page"></a>Kiracılar sayfasında temsilci erişim türü ve rolleri

**Kiracılar** sayfasını, **Temsilci** erişim sütunu altında müşteri başına Yönetilen Hizmet Sağlayıcısı'nın (MSP) temsilci erişim türünü (Yok, DAP, GDAP veya Her İkisi DAP & GDAP) listelenecek şekilde güncelleştirdik. Ayrıca oturum açmış bir kullanıcının müşteri başına DAP ve GDAP rollerini listeleyen **Rolleriniz** adlı yeni bir sütun ekledik. **Kiracılar** sayfasında yapılan bu iki geliştirme, MSP teknisyenlerinin her müşteri için hangi tür temsilci yönetim izinlerinin kullanılabilir olduğunu ve onlara açıkça hangi temsilci rollerinin verildiğini anlamasını kolaylaştırır.

Daha fazla bilgi için bkz. [Microsoft 365 Lighthouse'da izinlere genel bakış](m365-lighthouse-overview-of-permissions.md).

## <a name="march-2022"></a>Mart 2022

### <a name="windows-365-business-integration-and-management-actions"></a>Tümleştirme ve yönetim eylemlerini Windows 365 Business

Kullanıcı geri bildirimlerine dayanarak Windows 365 Business Microsoft 365 Lighthouse ile tümleştirdik. Bu tümleştirme, müşterilerinizin tüm Bulut bilgisayarlarını tek bir konumdan yönetmenize ve izlemenize yardımcı olur. 

Microsoft 365 Lighthouse'da Windows 365 Business Bulut bilgisayarlarıyla tümleştirmeye ek olarak, artık aşağıdaki yönetim eylemlerini gerçekleştirebilirsiniz:

- Yeniden başlatma
- Yeniden sağlama
- Yeniden Adlandırma
 
Yeni özellikler hakkında daha fazla bilgi edinmek için [Microsoft 365 Lighthouse'daki Windows 365 (Bulut Bilgisayarlar) sayfasına genel bakış bölümüne](m365-lighthouse-win365-page-overview.md) bakın.

### <a name="microsoft-365-lighthouse-partner-amendment"></a>Microsoft 365 Lighthouse iş ortağı değişikliği

Microsoft 365 Lighthouse Genel Kullanılabilirlik aşamasında olduğuna göre, geçerli iş ortaklarımızın güncelleştirilmiş bir Microsoft 365 Lighthouse iş ortağı değişikliği imzalamasını istiyoruz. Önizleme döneminde kaydolan tüm Microsoft 365 Lighthouse iş ortaklarının bu yeni sözleşmeyi önümüzdeki haftalarda tamamlamaları istenir. Tamamlama, iş ortağı kiracısında Genel Yönetici hakları gerektirir ve Microsoft 365 Lighthouse portalına erişmeye devam etmek için 90 gün içinde tamamlanması gerekir.

## <a name="february-2022"></a>Şubat 2022

### <a name="granular-delegated-access-permissions-gdap-roles"></a>Ayrıntılı TemsilciLi Erişim İzinleri (GDAP) rolleri

Microsoft 365 Lighthouse artık MSP'lerin Ayrıntılı Temsilcili Yönetici Ayrıcalıkları (GDAP) rollerini kullanma yeteneğine sahip. En son güncelleştirmeyle, MSP'ler teknisyenleri için Microsoft 365 Lighthouse en az ayrıcalık erişim ilkesini sağlayan GDAP rollerinden yararlanabilir. Bu özellik, her teknisyenin çalışabileceği müşteri verileri ve ayarları üzerinde ayrıntılı denetimler sağlayarak Yönetici Aracısı'nın Temsilci Erişim İzinleri (DAP) rolünün geniş izinlerindeki riskleri azaltır.

Microsoft 365 Lighthouse'da GDAP hakkında daha fazla bilgi edinmek için bkz[. Microsoft 365 Lighthouse portal güvenliğini yapılandırma](m365-lighthouse-configure-portal-security.md).

### <a name="capability-to-notify-users-to-act-on-noncompliant-devices"></a>Uyumsuz cihazlarda işlem yapmalarını kullanıcılara bildirme özelliği

Cihaz uyumluluk temeli adımının bir parçası olarak, bir müşteri kiracısında kullanıcılara uyumsuz cihazlarda işlem yapmalarını bildirme özelliğini ekledik. Bu değişiklikle, herhangi bir müşteri kiracısı için cihaz uyumluluk dağıtım adımını uyguladıktan sonra, bu kiracıda oluşturulan cihaz uyumluluk ilkesi, cihazları uyumsuz hale geldiğinde kullanıcılara cihazı yeniden uyumlu hale getirmek için uygun eylemi gerçekleştirmelerini anımsatan bir bildirim gönderir.

### <a name="deployment-validation-and-reporting"></a>Dağıtım doğrulama ve raporlama

Microsoft 365 Lighthouse artık Koşullu Erişim ilkeleriyle dağıtım adımları için kiracı yapılandırmalarını test edebilir.  

Bu yeni işlevsellik, yönettiğiniz müşteri kiracıları içindeki mevcut ilkeleri algılar ve bunları dağıtım planınızla karşılaştırır. Microsoft 365 Lighthouse daha sonra, hangi dağıtım işlemlerinin zaten tamamlandığını, hangilerinin ele alınması gerektiğini ve dağıtım planı tarafından belirlenen ayarların eşit, eksik veya mevcut ilkelerde yer alan ayarlarla çakışan ayarları anlamanıza yardımcı olmak için dağıtım adımları ve dağıtım adımı işlemleri için durum belirlemeleri sağlar. Bu bilgilerin bilinmesi ilke çakışmalarını daha hızlı, daha kolay ve daha etkili bir şekilde tanımlamayı, önceliklendirmeyi ve çözmeyi sağlar.

### <a name="deployment-step-to-configure-microsoft-defender-firewall"></a>Microsoft Defender Güvenlik Duvarı'nı yapılandırmak için dağıtım adımı

Microsoft 365 Lighthouse, Microsoft Defender Güvenlik Duvarı dağıtımını yapılandır adımını varsayılan temeline eklemiştir. Bu adım, MSP'lerin Windows 10 (ve üzeri) cihazlar için varsayılan güvenlik duvarı yapılandırması aracılığıyla müşteri kiracı cihazlarının güvenliğini sağlamasını sağlar. Microsoft Defender Güvenlik Duvarı, müşteri kiracı cihazlarına veya dışına gelen yetkisiz ağ trafiğini engeller ve ağ güvenlik tehditleri riskini azaltır. Microsoft Defender Güvenlik Duvarı Kuralları özelliği şu anda geliştiriliyor.

Microsoft Defender Güvenlik Duvarı, Windows 10 (ve üzeri) cihazlarda varsayılan olarak açıktır. Müşteri kiracınızda bu yapılandırma yoksa şu adımları izleyin:

1. Microsoft 365 Lighthouse'deki **Kiracılar** sayfasında, kiracının **Genel Bakış** sayfasını açmak için müşteri kiracısını seçin.
2. **Dağıtım Planı** sekmesini seçin.
3. Dağıtım adımları listesinden **Microsoft Defender Güvenlik Duvarını Yapılandır'ı** seçin.
4. Bu yapılandırmayı müşteri kiracısına dağıtmak için **Gözden geçir ve dağıt'ı** seçin. 

### <a name="increase-in-maximum-license-limit"></a>En yüksek lisans sınırında artış

Müşteri ekleme için maksimum lisans sınırını artırarak Microsoft 365 Lighthouse'de daha fazla müşterinizi yönetmeyi mümkün hale getiriyoruz. En fazla 1000 kullanıcı lisansına sahip müşteriler artık Microsoft 365 Lighthouse eklenebilir. Gelecek Microsoft 365 Lighthouse sürümlerde bu gereksinimi değerlendirmeye devam edeceğiz.

Daha fazla bilgi için bkz[. Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md).

### <a name="support-for-advisor-customers"></a>Danışman müşteriler için destek

Danışman ilişkileri olan mevcut müşteri kiracılarının Microsoft 365 Lighthouse eklemesine izin vermek için ekleme gereksinimlerimizi değiştirdik. Hem kurumsal bayi hem de danışman sözleşmelerine sahip müşteriler, temsilci erişim izinlerinin gereksinimlerini karşılıyorsa, gerekli lisanslara sahipse ve kullanıcı sayısı üst sınırını aşmadıysa artık Microsoft 365 Lighthouse kabul edilebilir.

Daha fazla bilgi için bkz[. Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md).

## <a name="january-2022"></a>Ocak 2022

### <a name="capability-to-view-audit-logs-in-microsoft-365-lighthouse"></a>denetim günlüklerini Microsoft 365 Lighthouse görüntüleme özelliği

Microsoft 365 Lighthouse artık denetim günlüklerini görüntüleme özelliğini içerir. Düzeltme, destek süreci ve güvenlik araştırması için yanlış yapılandırmaları ve riskli eylemleri bulmak, çalışanları eğitmek ve uyumluluk ve denetim gereksinimlerini karşılamak için geçmiş eylemleri gözden geçirebilirsiniz. En son güncelleştirmeyle şunları yapabilirsiniz:

- Hangi müşteri kiracısında, ne zaman değiştirildiği ve kimin değiştirdiği dahil olmak üzere Microsoft 365 Lighthouse içinde gerçekleştirilen tüm eylemleri görmek için denetim günlüklerini görüntüleyin.
- Belirli bilgileri bulmak için denetim günlüklerini arayın ve filtreleyin.
- Günlükleri dışarı aktararak analiz edebilir ve saklayabilirsiniz.
 
Microsoft 365 Lighthouse sol gezinti bölmesinde **Denetim günlükleri'ni** seçin. İsterseniz, [doğrudan Denetim günlükleri sayfasına giderek](https://lighthouse.microsoft.com/#blade/Microsoft_Intune_MTM/Audit.ReactView) kontrol edin.

## <a name="november-2021"></a>Kasım 2021

### <a name="microsoft-365-services-usage-data"></a>Microsoft 365 hizmetleri kullanım verileri

Artık microsoft 365 hizmetlerinin kullanım verilerini Microsoft 365 Lighthouse içinden görüntüleyebilirsiniz. Müşterilerin Microsoft 365 hizmetlerini nasıl kullandığını anlamak, BT yatırımlarından en iyi şekilde yararlanmalarına yardımcı olmak için kritik öneme sahiptir. Müşterilerinizin çeşitli üretkenlik, güvenlik ve uyumluluk hizmetleriyle ilgili bilgileri görüntülemek için birden çok kaynak kullanmak yerine Microsoft 365 Lighthouse bunları tek bir basit ve güçlü görünümde toplar.  

Bu içgörüler, kullanıcılarının etkin olarak hangi hizmetleri kullandığını ve güvenliklerini veya üretkenliğini artırma fırsatlarının nerede olabileceğini anlamalarına yardımcı olmak için sizi güçlendirerek müşteri etkileşimlerinizi bilgilendirmenize ve müşterilerinize daha fazla değer sunmanıza yardımcı olabilir. 

Daha fazla bilgi için Microsoft 365 Lighthouse[: Microsoft 365 hizmetleri kullanımı bölümündeki Kiracılar sayfasına genel bakış bölümüne bakın](m365-lighthouse-tenants-page-overview.md#microsoft-365-services-usage-section).

### <a name="exchange-online-protection-and-microsoft-365-defender-for-office-365-default-baseline-step"></a>Varsayılan Office 365 temel adım için Exchange Online Protection ve Microsoft 365 Defender

Exchange Online Protection (EOP) ve Office 365 için Microsoft Defender (MDO) için Güvenlik İlkeleri'ni etkinleştirme yönergelerini içerecek şekilde varsayılan taban çizgisine yeni bir adım ekledik. EOP ve MDO, e-postaları kullanıcının karantinasına veya gereksiz posta klasörüne göndererek kullanıcıların istenmeyen posta, kimlik avı ve kötü amaçlı yazılım e-postalarından korunmasına yardımcı olur (çok yakında). Dağıtım planı, EOP ve MDO kurulumunda size yol gösterir ve sonraki müşteri kiracı dağıtım planı gözden geçirmeniz sırasında güvenlik duruşunuzu daha da genişletir.

### <a name="default-tenant-tags"></a>Varsayılan kiracı etiketleri

Artık Kiracılar sayfasındaki **Etiketleri yönet** bölmesinden belirli kiracı **etiketlerini** *varsayılan* olarak belirleyebilirsiniz; bu nedenle Microsoft 365 Lighthouse bir sonraki oturum açışınızda, tüm görünümleriniz ve içgörüleriniz varsayılan olarak yalnızca varsayılan etikete sahip kiracıları gösterecek şekilde filtrelenir. Varsayılan etiketler, yüksek öncelikli müşteri kiracıları için içgörülere odaklanmanıza yardımcı olabilir.

## <a name="october-2021"></a>Ekim 2021

### <a name="capability-to-filter-by-multiple-tenant-tags"></a>Birden çok kiracı etiketine göre filtreleme özelliği

Artık verileri aynı anda birden çok kiracı etiketine göre filtrelemek mümkündür. Bu işlev, ilgili müşteri kiracılarını göstermek için Microsoft 365 Lighthouse'da bulunan mevcut görünümleri ve içgörüleri daha kolay filtrelemenize yardımcı olabilir.

### <a name="capability-to-assign-baseline-configurations-to-specific-azure-active-directory-groups"></a>Belirli Azure Active Directory gruplarına temel yapılandırma atama özelliği

müşteri kiracılarınızın belirli Azure Active Directory (Azure AD) gruplarına temel yapılandırmaları Microsoft 365 Lighthouse içinden atama özelliğini ekledik. Herhangi bir dağıtım adımı sayfasında, dahil etmek veya hariç tutmak istediğiniz belirli Azure AD gruplarına göz atın ve seçin ve ardından yapılandırmaları müşteri kiracınıza dağıtın.

### <a name="improvements-to-risky-users-page"></a>Riskli kullanıcılar sayfasında iyileştirmeler

Artık Microsoft 365 Lighthouse içinden kullanıcının riskinin nedenlerini kolayca görüntüleyebilir ve anlayabilirsiniz. Microsoft 365 Lighthouse sol gezinti bölmesinde **Kullanıcılar'ı** ve ardından **Riskli kullanıcılar** sekmesini seçin. Herhangi bir kullanıcının Ayrıntılar sütununda **Risk algılamalarını görüntüle'yi** seçin. Buradan, riskin ayrıntılarını gözden geçirebilir ve ardından **Kullanıcının güvenliğinin aşıldığını onayla** veya **Kullanıcı riskini kapat'ı** seçebilirsiniz. Riskli **kullanıcılar** sayfasından aynı anda birden çok kullanıcı için riski onaylayabilir veya kapatabilirsiniz. Parola sıfırlama bir seçenek olmadığında veya etkilenen kullanıcının artık risk altında olmadığına inanıyorsanız kullanıcının riskini kapatma özelliği yararlı olabilir.

### <a name="capability-to-provide-feedback-on-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse hakkında geri bildirim sağlama özelliği

Geri bildiriminiz bizim için önemlidir ve önemlidir. Bu nedenle, zaman zaman (ayda bir kereden fazla) geri bildirim sağlamanız istenmeyecek yeni geri bildirim işlevleri ekledik. Ayrıca, Microsoft 365 Lighthouse sağ üst köşesindeki geri bildirim simgesini seçerek istediğiniz zaman geri bildirim sağlayabilirsiniz.

## <a name="september-2021"></a>Eylül 2021

### <a name="tenant-filter-changes"></a>Kiracı filtresi değişiklikleri

kiracıları ve etiketleri Microsoft 365 Lighthouse herhangi bir sayfadan hızla görüntülemenize ve yönetmenize yardımcı olmak için kiracı filtreleme deneyiminde bazı değişiklikler yaptık. Herhangi bir sayfanın üst kısmındaki **Kiracılar** filtresini seçin ve ardından filtrelemek istediğiniz kiracıya veya etiket adına göz atın veya girin.

## <a name="august-2021"></a>Ağustos 2021

### <a name="in-product-email-workflows-to-communicate-with-users"></a>Kullanıcılarla iletişim kurmak için ürün içi e-posta iş akışları 

Müşteri kiracılarınızdaki kullanıcılarla gerçekleştirmeleri gereken eylemler hakkında iletişim kurmanızı kolaylaştırdık. Çok faktörlü kimlik doğrulaması (MFA) veya self servis parola sıfırlama için kayıtlı olmayan kullanıcılar listesinden, artık bir veya daha fazla kullanıcı seçebilir ve indirilebilir bir e-posta şablonu kullanarak onlara bir e-posta iletisi gönderebilirsiniz.

### <a name="capability-to-take-action-on-noncompliant-devices"></a>Uyumsuz cihazlarda eylem gerçekleştirme özelliği

Birden çok müşteri kiracısı arasında bir veya daha fazla cihazı eşitleme veya yeniden başlatma özelliği ekledik. Bu işlev, müşterilerinizin cihazlarının riskten korunmasına yardımcı olur. Bu işlevi kullanıma almak için, Microsoft 365 Lighthouse sol gezinti bölmesinde **Cihazlar'ı** seçin ve ardından **Cihazlar** sekmesini seçin. Cihazlar listesinin üst kısmındaki **Eşitle** ve **Yeniden Başlat** seçeneklerini arayın. Bu seçeneklere herhangi bir cihazın cihaz ayrıntıları bölmesinden de erişebilirsiniz.

### <a name="capability-to-monitor-and-manage-windows-365-cloud-pcs"></a>Windows 365 Bulut bilgisayarlarını izleme ve yönetme özelliği

Şirket içi bağlantıları izleme ve tüm müşteri kiracılarınızda Windows 365 Bulut bilgisayarları sağlama ve yönetme özelliği ekledik. Yeni **Windows 365** sayfası, kiracılarınızın tüm Bulut bilgisayarları hakkında tek bir konumda ayrıntılı bilgi sağlar. 

### <a name="support-for-microsoft-365-e3-customers"></a>Microsoft 365 E3 müşterileri için destek

Microsoft 365 E3 müşterileri Microsoft 365 Lighthouse eklemenizi sağlamak için ekleme gereksinimlerimizi değiştirdik. Microsoft 365 Lighthouse'de yönetilmeye hak kazanmak için her müşterinin aşağıdaki gereksinimleri karşılaması gerekir:

- Müşteri kiracısını yönetebilmek için MSP için temsilci erişimi ayarlanmış olmalıdır
- En az bir Microsoft 365 İş Ekstra veya Microsoft 365 E3 lisansı olmalıdır
- En fazla 500 lisanslı kullanıcı olmalıdır

Gereksinimler hakkında daha fazla bilgi için bkz[. Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md).

## <a name="june-2021"></a>Haziran 2021

### <a name="capability-to-add-custom-tags-to-customer-tenants"></a>Müşteri kiracılarına özel etiketler ekleme özelliği

Artık Microsoft 365 Lighthouse'de yönettiğiniz müşteri kiracılarına özel etiketler oluşturabilir ve uygulayabilirsiniz. Kiracılarınızı düzenlemenize yardımcı olması için bu etiketleri kullanın veya ilgili müşteri kiracı kümelerine yönelik içgörüleri göstermek üzere kiracı listenizi daha kolay filtrelemek için bu etiketleri kullanın. 

### <a name="baselines-to-standardize-your-customer-tenant-deployments"></a>Müşteri kiracı dağıtımlarınızı standart hale getirmek için temeller

Yeni temeller özelliğiyle artık müşteri kiracılarındaki kullanıcıların, cihazların ve verilerin güvenliğini sağlamaya yardımcı olmak için standart yapılandırmalar dağıtabilirsiniz. Varsayılan temel şu anda aşağıdaki dağıtım adımlarını içerir (yakında daha fazlası olacak): 

- Yöneticiler için MFA gerektir 
- Kullanıcılar için MFA gerektir 
- Eski Kimlik Doğrulamasını Engelle 
- Windows Cihazlarını Microsoft Endpoint Manager'ye Kaydetme – Azure AD Katılma 
- Windows cihazları için Defender AV ilkesini yapılandırma 
- Windows cihazları için Uyumluluk İlkesi'ni yapılandırma 

Bu dağıtım adımlarını uygulamak için Microsoft 365 lighthouse'un sol gezinti bölmesinde **Kiracılar'ı** seçin, kiracı listesinden bir kiracı seçin ve ardından **Dağıtım planı** sekmesini seçin. 

## <a name="may-2021"></a>Mayıs 2021

### <a name="enhancements-to-tenants-page"></a>Kiracılar sayfasındaki geliştirmeler

**Kiracılar sayfasında aşağıdaki iyileştirmeleri** yaptık:

- Sayfanın en üstüne soruna göre toplam sayıların listesi eklendi 
- Kısıtlama ayrıntılarını görmek için kiracı listesinin **Durum** sütunundaki bir durumun üzerine gelme özelliği sağlandı 
- Durum etiketleri iyileştirildi