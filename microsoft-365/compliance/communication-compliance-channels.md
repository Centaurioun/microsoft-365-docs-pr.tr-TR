---
title: İletişim uyumluluğu ile kanal sinyallerini tespit etme
description: İletişim uyumluluğu ile kanal sinyallerini algılama hakkında daha fazla bilgi edinin.
keywords: Microsoft 365, Microsoft Purview, uyumluluk, iletişim uyumluluğu
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 17ac1b6ad7a590b2ae14e39cc3f978712b843ca2
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68767675"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>İletişim uyumluluğu ile kanal sinyallerini tespit etme

> [!IMPORTANT]
> Microsoft Purview İletişim Uyumluluğu, kuruluşların hassas veya gizli bilgiler, taciz veya tehdit dili ve yetişkin içeriğinin paylaşılması gibi mevzuat uyumluluğu ihlallerini (örneğin SEC veya FINRA) algılamasına yardımcı olacak araçlar sağlar. Tasarım gereği gizlilikle oluşturulan kullanıcı adları varsayılan olarak takma ad kullanılır, rol tabanlı erişim denetimleri yerleşiktir, araştırmacılar bir yönetici tarafından kabul edilir ve denetim günlükleri kullanıcı düzeyinde gizlilik sağlamaya yardımcı olur.

İletişim uyumluluk ilkeleriyle, aşağıdaki iletişim platformlarından bir veya daha fazlasında iletileri grup olarak veya tek başına kaynak olarak analiz etmeyi seçebilirsiniz. Bu platformlarda yakalanan özgün iletiler, kuruluşunuzun [saklama ve saklama ilkelerine](/microsoft-365/compliance/information-governance) uygun olarak özgün platform konumunda tutulur. İletişim uyumluluk ilkeleri tarafından analiz ve araştırma için kullanılan iletilerin kopyaları, kullanıcılar kuruluşunuzdan ayrılsa ve posta kutuları silinse bile, ilke olduğu sürece saklanır. bir iletişim ilkesi silindiğinde, ilkeyle ilişkili iletilerin kopyaları da silinir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="microsoft-teams"></a>Microsoft Teams

Hem genel hem de özel Microsoft Teams kanallarındaki sohbetler ve bireysel iletişimler analiz edilebilir. Kullanıcılar Microsoft Teams kapsamı seçiliyken bir iletişim uyumluluk ilkesine atandığında, kullanıcıların üye olduğu tüm Microsoft Teams'de kullanıcılara yönelik sohbet iletişimleri otomatik olarak algıılır. 

Microsoft Purview İletişim Uyumluluğu, önceden tanımlanmış ilke şablonları için Microsoft Teams kapsamını otomatik olarak içerir ve özel ilke şablonunda varsayılan olarak seçilir. İletişim uyumluluk ilkesi koşullarıyla eşleşen Teams sohbetlerinin işlenmesi 48 saat kadar sürebilir.

Teams özel sohbet ve özel kanallar için iletişim uyumluluk ilkeleri [Paylaşılan Kanallar'ı](/MicrosoftTeams/shared-channels) ve modern ek analizini destekler. Teams'de Paylaşılan Kanallar desteği otomatik olarak işlenir ve ek iletişim uyumluluk yapılandırması değişiklikleri gerektirmez. Aşağıdaki tabloda Teams kanallarını gruplar ve kullanıcılarla paylaşırken iletişim uyumluluğu davranışı özetlenmiştir:

|**Senaryo**|**İletişim uyumluluğu davranışı**|
|:-----------|:------------------------------------|
| **Kanalı bir iç ekiple paylaşma** | İletişim uyumluluk ilkeleri, kapsam içi kullanıcılar ve paylaşılan kanaldaki tüm iletiler için geçerlidir |
| **Dış ekiple kanal paylaşma** | İletişim uyumluluk ilkeleri, iç kuruluş için paylaşılan kanaldaki dahili kapsam içi kullanıcılar ve iletiler için geçerlidir |

Modern ekler, Teams iletilerine dahil edilen [OneDrive](/onedrive/plan-onedrive-enterprise#modern-attachments) veya [SharePoint](/sharepoint/dev/solution-guidance/modern-experience-customizations) sitelerinden alınan dosyalardır. Otomatik işleme ve etkin iletişim uyumluluk ilkesi koşulları ve sınıflandırıcılarla olası eşleşmeler için bu eklerden metin otomatik olarak ayıklanır. Modern ek algılama ve işleme için gerekli ek yapılandırma yoktur. Metin yalnızca ileti gönderildiğinde ilke koşullarıyla eşleşen ekler için ayıklanır. İlke eşleşmesi olan iletilere yönelik ekler için, ekin bir ilke eşleşmesi de olsa metin ayıklanmamıştır.

Modern ek analizi aşağıdaki dosya türleri için desteklenir:

- Microsoft Word (.docx)
- Microsoft Excel (.xlsx)
- Microsoft PowerPoint (.pptx)
- Metin (.txt)
- Taşınabilir Belge Biçimi (.pdf)

Modern ekler için ayıklanan metin, ilke panosunun **Beklemede** sekmesindeki ilişkili iletiye eklenir. Ek için ayıklanan metin, ek dosya adı (ve biçim uzantısı) ve .txt uzantısı olarak adlandırılır. Örneğin, *ContosoBusinessPlan.docx* adlı ek için ayıklanan metin, ilke panosunun **Beklemede** sekmesinde *ContosoBusinessPlan.docx.txt* olarak görünür.

*Kaynak* ve *Düz metin* görünümlerindeki ayrıntıları görüntülemek için ayıklanan ek metnini seçin. Gözden geçirdikten sonra, komut çubuğu denetimlerini kullanarak ek metnini çözümleyebilir veya üzerinde işlem yapabilirsiniz. Ayrıca, iletişim uyumluluğu gözden geçirme işleminin dışında gözden geçirmek üzere eki indirme seçeneğiniz de vardır.

Teams'de bireysel kullanıcı sohbetlerini ve kanal iletişimlerini denetlemek için aşağıdaki grup yönetimi yapılandırmalarını kullanın:

- **Teams sohbetleri için:** İletişim uyumluluk ilkesine tek tek kullanıcılar atayın veya bir [dağıtım grubu](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) atayın. Bu ayar, bire bir veya bire çok kullanıcı/sohbet ilişkileri içindir.
- **Teams kanal iletişimleri için:** Analiz etmek istediğiniz ve belirli bir kullanıcıyı içeren her Microsoft Teams kanalını veya Microsoft 365 grubunu iletişim uyumluluk ilkesine atayın. Aynı kullanıcıyı diğer Microsoft Teams kanallarına veya Microsoft 365 gruplarına eklerseniz, bu yeni kanalları ve grupları iletişim uyumluluk ilkesine eklediğinizden emin olun. Kanalın herhangi bir üyesi bir ilke içinde denetimli bir kullanıcıysa ve *Gelen* yönü bir ilkede yapılandırılmışsa, kanal içinde gönderilen tüm iletiler gözden geçirilebilir ve olası ilke eşleşmeleri (kanaldaki kullanıcılar için bile açıkça denetlenmeyenler için). Örneğin, A Kullanıcısı bir kanalın sahibi veya üyesidir. B ve C Kullanıcısı aynı kanalın üyeleridir ve yalnızca A Kullanıcısını denetleyen uygunsuz olabilecek içerik ilkesiyle eşleşen dili kullanır. Kullanıcı B ve C Kullanıcısı, uygunsuz olabilecek içerik ilkesinde doğrudan denetlenmeseler bile kanal içindeki konuşmalar için ilke eşleşmeleri oluşturur. B Kullanıcısı ile C Kullanıcısı arasında kanalın dışında olan ve A Kullanıcısı içeren Teams konuşmaları, A Kullanıcısı'nı içeren uygunsuz olabilecek içerik ilkesine tabi olmaz. Kanalın diğer üyeleri açıkça denetlendiğinde kanal üyelerini denetimden çıkarmak için, ilgili iletişim uyumluluk ilkesinde *Gelen* iletişim yönü ayarını kapatın.
- **Karma e-posta ortamlarıyla Teams sohbetleri için**: İletişim uyumluluğu, Şirket içi Exchange dağıtımına veya Microsoft Teams'i etkinleştirmiş bir dış e-posta sağlayıcısına sahip kuruluşlar için sohbet iletilerini algılayabilir. Şirket içi veya dış posta kutuları olan kullanıcılar için bir dağıtım grubu oluşturmanız gerekir. İletişim uyumluluk ilkesi oluştururken, bu dağıtım grubunu ilke sihirbazında **Denetimli kullanıcılar ve gruplar** seçimi olarak atayacaksınız. Bulut tabanlı depolamayı etkinleştirme gereksinimleri ve sınırlamaları ve şirket içi kullanıcılar için Teams desteği hakkında daha fazla bilgi için bkz. [Şirket içi kullanıcılar için Teams sohbet verilerini arama](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users).

## <a name="exchange"></a>Exchange

Microsoft 365 veya Office 365 aboneliğinizin bir parçası olarak Microsoft Exchange Online'da barındırılan posta kutularının tümü ileti analizi için uygundur. İletişim uyumluluk ilkesi koşullarıyla eşleşen Exchange e-posta iletilerinin ve eklerinin işlenmesi yaklaşık 24 saat sürebilir. İletişim uyumluluğu için desteklenen ek türleri [, Exchange posta akışı kuralı içerik denetimleri için desteklenen dosya türleriyle aynıdır](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

## <a name="yammer"></a>Yammer

Microsoft Yammer topluluklarındaki özel iletiler, genel konuşmalar ve ilişkili ekler de analiz edilebilir. Kullanıcılar, yammer'ı tanımlı bir kanal olarak içeren bir iletişim uyumluluk ilkesine eklendiğinde, kullanıcının üyesi olduğu tüm Yammer toplulukları arasındaki iletişimler analize dahil edilir. İletişim uyumluluk ilkesi koşullarıyla eşleşen Yammer sohbetlerinin ve eklerinin işlenmesi 24 saat kadar sürebilir. 

Yammer iletişimlerini ve eklerini algılamak için iletişim uyumluluk ilkeleri için Yammer [Yerel Modda](/yammer/configure-your-yammer-network/overview-native-mode) yapılandırılmalıdır. Yerel Modda, tüm Yammer kullanıcıları Azure Active Directory'de (AAD), tüm gruplar Office 365 Gruplar'dır ve tüm dosyalar SharePoint Online'da depolanır.

## <a name="third-party-sources"></a>Üçüncü taraf kaynaklar

[Instant Bloomberg](/microsoft-365/compliance/archive-instant-bloomberg-data), [Slack](/microsoft-365/compliance/archive-slack-data), [Zoom](/microsoft-365/compliance/archive-zoommeetings-data), SMS gibi üçüncü taraf kaynaklardan Microsoft 365 kuruluşunuzdaki tüm posta kutularına aktarılan verilerin iletişimlerini analiz edebilirsiniz. İletişim uyumluluğunda desteklenen bağlayıcıların tam listesi için bkz. [Üçüncü taraf verileri için bağlayıcılar hakkında bilgi edinin](/microsoft-365/compliance/archiving-third-party-data).

Bağlayıcıyı bir iletişim uyumluluk ilkesine atayabilmeniz için önce Microsoft 365 kuruluşunuz için bir [üçüncü taraf](/microsoft-365/compliance/archiving-third-party-data) bağlayıcı yapılandırmanız gerekir. İletişim uyumluluk ilkesi sihirbazının **Üçüncü Taraf Kaynaklar** bölümü yalnızca şu anda yapılandırılmış olan üçüncü taraf bağlayıcılarını görüntüler.
