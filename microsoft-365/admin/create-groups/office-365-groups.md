---
title: Yöneticiler için Microsoft 365 Grupları genel bakış
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Grupları ile, bir grup kişiye paylaşılan kaynak koleksiyonuna erişim vererek Microsoft 365 genelinde ekip çalışmasını yönlendirebilirsiniz.
ms.openlocfilehash: 4e0668ea1204dd9aa3fd9891574f3fe17a1b5e15
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084179"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Yöneticiler için Microsoft 365 Grupları genel bakış

Microsoft 365 Grupları, Microsoft 365'te tüm ekip çalışmasını yönlendiren temel üyelik hizmetidir. Microsoft 365 Grupları ile, bir grup kişiye paylaşılan kaynaklar koleksiyonuna erişim verebilirsiniz. Bu kaynaklar şunlardır:

- Paylaşılan bir Outlook gelen kutusu
- Paylaşılan takvim
- SharePoint belge kitaplığı
- A Planner
- OneNote not defteri
- Power BI
- Yammer (grup Yammer'dan oluşturulduysa)
- Ekip (grup Teams'den oluşturulduysa)
- Yol haritası (Web için Project'iniz varsa)
- Stream

Bir Microsoft 365 grubuyla, bu kaynakların her birine el ile izin atamanız gerekmez. Kişileri gruba eklemek, onlara otomatik olarak ihtiyaç duydukları izinleri verir.

Grup [oluşturmayı belirli bir kişi kümesiyle sınırlamadığınız sürece herhangi bir kullanıcı grup](../../solutions/manage-creation-of-groups.md) oluşturabilir. Grup oluşturmayı sınırlandırırsanız, grup oluşturamayan kullanıcılar SharePoint siteleri, Planlayıcılar, ekipler, Outlook grup takvimleri, Akış grupları, Yammer grupları, OneDrive'da Paylaşılan kitaplıklar veya paylaşılan Power BI çalışma alanları oluşturamaz. Bu hizmetler, bunları oluşturan kişilerin grup oluşturabilmesini gerektirir. Kullanıcılar, grubun üyesi olmaları koşuluyla Planner'da görev oluşturma veya Teams sohbetini kullanma gibi grup etkinliklerine katılmaya devam edebilir.

Gruplar aşağıdaki rollere sahiptir:

- **Sahipler** - Grup sahipleri üyeleri ekleyebilir veya kaldırabilir ve paylaşılan gelen kutusundan konuşmaları silme veya grupla ilgili farklı ayarları değiştirme gibi benzersiz izinlere sahip olabilir. Grup sahipleri grubu yeniden adlandırabilir, açıklamayı veya resmi güncelleştirebilir ve daha fazlasını yapabilir.
- **Üyeler** - Üyeler gruptaki her şeye erişebilir, ancak grup ayarlarını değiştiremez. Varsayılan olarak grup üyeleri konukları grubunuzla katılmaları için davet edebilir, ancak [bu ayarı denetleyebilirsiniz](manage-guest-access-in-groups.md).
- **Konuklar** - Grup konukları, kuruluşunuzun dışından gelen üyelerdir.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Microsoft 365 yönetim merkezi</a> grupları yalnızca genel yöneticiler, kullanıcı yöneticileri ve grup yöneticileri oluşturabilir ve yönetebilir. Yönetici temsilcisi olamazsınız (örneğin, başka birinin adına yönetici olan bir danışman).

Yönetici olarak şunları yapabilirsiniz:

- [Kimlerin grup oluşturabileceğini belirtme](../../solutions/manage-creation-of-groups.md)
- [Kuruluşunuzdaki gruplar için adlandırma ilkesi oluşturma](../../solutions/groups-naming-policy.md)
- [Grup oluştururken hangi etki alanının kullanılacağını seçme](../../solutions/choose-domain-to-create-groups.md)
- [Gruplara konuk erişimini yönetme](manage-guest-access-in-groups.md)
- [Silinen bir grubu kurtarma](restore-deleted-group.md) (silme işleminden sonra 30 gün içinde)

Microsoft 365 gruplarınızın yaşam döngüsünü yönetmek için daha otomatik bir yol tercih ediyorsanız, grupları belirli bir zaman aralığında sona erdirmek için süre sonu ilkelerini kullanabilirsiniz. Grubun sahipleri, grubun sona erme tarihinden 30, 15 ve 1 gün önce bir e-posta alır ve gerekirse grubu yenilemelerine olanak tanır. Bkz. [Microsoft 365 grup Süre Sonu İlkesi](../../solutions/microsoft-365-groups-expiration-policy.md).

Gruplarınızı Microsoft 365 yönetim merkezi veya [PowerShell kullanarak](../../enterprise/manage-microsoft-365-groups-with-powershell.md) yönetebilirsiniz.

Büyük bir şirket veya kuruluş gibi birçok kullanıcınız varsa, çeşitli amaçlarla grup oluşturan birçok kullanıcınız olabilir. En iyi yöntemler [için Microsoft 365 gruplarında idare planı'nın](../../solutions/collaboration-governance-overview.md) gözden geçirilmesini kesinlikle öneririz.

## <a name="group-limits"></a>Grup sınırları

Microsoft 365 Grupları için aşağıdaki sınırlar geçerlidir:

|Maksimum...|Değer|
|:---------|:----|
|Grup başına sahipler|100|
|Bir kullanıcının oluşturabileceği gruplar|250|
|Bir yöneticinin oluşturabileceği gruplar|Varsayılan kiracı sınırı 500 K'ye kadar|
|Üye sayısı|1.000'den fazla, ancak grup konuşmalarını eşzamanlı olarak yalnızca 1.000 erişebilir. <br>Kullanıcılar, Outlook'taki büyük gruplarda takvime ve konuşmalara erişirken gecikmeler yaşayabilir.|
|Bir kullanıcının üye olabileceği Grup sayısı|7,000|
|Dosya depolama|Abone olan kullanıcı başına 1 Terabayt + 10 GB + satın alınan diğer depolama alanları. Sınırsız miktarda ek depolama alanı satın alabilirsiniz.|
|Grup Posta Kutusu boyutu|50 GB|

Bir kuruluşun sahip olabileceği varsayılan en fazla Microsoft 365 grubu sayısı 500.000'dir. Varsayılan sınırın ötesine geçmek için Microsoft Desteği ile iletişime geçmeniz gerekir. Microsoft 365 Grupları sınırları hakkında daha fazla bilgi için yardım [Yönetici Microsoft 365 Grupları bölümüne bakın](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Grup kullanımı hakkında eyleme dönüştürülebilir bilgilere sahip olduğunuzda Microsoft 365 gruplarınızı yönetmek daha etkilidir. Microsoft 365 yönetim merkezi depolama kullanımını, kaç etkin grubunuz olduğunu ve kullanıcıların grupları nasıl kullandığını görmenizi sağlayan bir raporlama aracı vardır. Daha fazla bilgi için bkz. [Yönetim merkezinde Microsoft 365 Raporları](../activity-reports/office-365-groups.md) .

## <a name="sensitivity-labels"></a>Duyarlılık etiketleri

Kuruluşunuzdaki kullanıcıların bir Microsoft 365 grubu oluştururken ayarlayabileceğiniz duyarlılık etiketleri oluşturabilirsiniz. Duyarlılık etiketleriyle şunları yapılandırabilirsiniz: 

- Gizlilik (genel veya özel)
- Dış kullanıcılara erişim
- Yönetilmeyen cihaz erişimi

Örneğin, *Çok Gizli* adlı bir etiket oluşturabilir ve bu etiketle oluşturulan tüm grupların özel olacağını ve dış kullanıcılara izin vermeyeceğini belirtebilirsiniz. Kuruluşunuzdaki kullanıcılar grup oluşturma sırasında bu etiketi seçtiğinde, grup özel olarak ayarlanır ve grup üyelerinin gruba dış kullanıcı eklemesine izin verilmez.

> [!IMPORTANT]
> Şu anda sınıflandırma etiketleri kullanıyorsanız, duyarlılık etiketleri etkinleştirildikten sonra grup oluşturan kullanıcılar artık bu etiketleri kullanamayacaktır. 

Duyarlılık etiketleri oluşturma, yönetme ve kullanma hakkında bilgi için bkz. [Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../../compliance/sensitivity-labels-teams-groups-sites.md).

## <a name="which-microsoft-365-plans-include-groups"></a>Hangi Microsoft 365 planları grupları içerir?

Exchange Online ve SharePoint Online'a sahip tüm Microsoft 365 abonelikleri grupları destekler. Buna business essentials ve business premium planları ile Kurumsal E1, E3 ve E5 planları dahildir. Grup, grubu oluşturan kişinin lisansını alır (grubun "düzenleyicisi" olarak da bilinir). Düzenleyici, grubun sahip olmasını istediğiniz özellikler için uygun lisansa sahip olduğu sürece bu lisans gruba iletilecektir.

> [!NOTE]
> Microsoft 365 hizmet aileleri ve planları hakkında daha fazla bilgi için bkz. [Microsoft 365 plan seçenekleri](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Yalnızca Exchange planınız varsa, Outlook'ta grupların paylaşılan gelen kutusunu ve paylaşılan takvim özelliklerini almaya devam edebilirsiniz, ancak belge kitaplığını, Planner'ı veya diğer özellikleri almazsınız.

Microsoft 365 grupları Azure Active Directory ile çalışır. Elde ettiğiniz grup özellikleri, sahip olduğunuz Azure Active Directory aboneliğine ve grubun düzenleyicisine hangi lisansların atandığına bağlıdır.

> [!IMPORTANT]
> Tüm grup özellikleri için, Azure AD Premium aboneliğiniz varsa, kullanıcılar kendilerine atanmış bir AAD P1 lisansı olup olmadığına bakılmaksızın gruba katılabilir. Lisanslama zorunlu tutulmaz.
> Belirli aralıklarla hangi kullanıcıların lisansının eksik olduğunu ve lisans gereksinimleriyle uyumlu olması için bu kullanıcılara atanmış bir kullanıcı olması gerektiğini bildiren kullanım raporları oluştururuz. Örneğin, bir kullanıcının lisansı olmadığını ve adlandırma ilkesinin zorunlu olduğu bir gruba eklendiğini varsayalım. Rapor sizin için lisansa ihtiyaç duyduğuna işaret eder.

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Grupları hakkında bilgi edinin](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (makale)\
[Dağıtım listelerini Microsoft 365 Grupları](../manage/upgrade-distribution-lists.md) yükseltme (makale)\
[PowerShell ile Microsoft 365 Grupları yönetme](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (makale)\
[SharePoint Online Sınırları](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (makale)\
[grupları ve kanalları Microsoft Stream'de düzenleme](/stream/groups-channels-organization) (makale)
