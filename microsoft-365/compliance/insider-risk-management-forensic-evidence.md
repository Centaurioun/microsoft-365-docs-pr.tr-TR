---
title: Insider risk yönetimi adli kanıtı (önizleme) hakkında bilgi edinin
description: Microsoft Purview'da insider risk yönetimi adli kanıtı hakkında bilgi edinin. Adli kanıt, kullanıcının eylemlerinin risk oluşturup oluşturmadığını ve bir güvenlik olayına yol açıp açmadığını saptamaya yardımcı olmak için yakalanan kullanıcı etkinliğini görüntülemeye yönelik bir araştırma aracıdır.
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 5bc3f1863fa2e49bc6cc98aca1c9be38b07ec582
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68815231"
---
# <a name="learn-about-insider-risk-management-forensic-evidence-preview"></a>Insider risk yönetimi adli kanıtı (önizleme) hakkında bilgi edinin

>[!IMPORTANT]
>Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Güvenlikle ilgili olabilecek kullanıcı etkinlikleriyle ilgili daha iyi içgörüler elde etmek için adli araştırmalar sırasında güvenlik ekipleri için görsel bağlama sahip olmak çok önemlidir. Özelleştirilebilir olay tetikleyicileri ve yerleşik kullanıcı gizliliği koruma denetimleriyle adli kanıt, kuruluşunuzun hassas verilerin yetkisiz veri sızdırması gibi olası veri risklerini daha iyi azaltmasına, anlamasına ve yanıtlamasına yardımcı olmak için cihazlar arasında özelleştirilebilir görsel etkinlik yakalamaya olanak tanır. Hangi riskli olayların adli kanıt yakalamak için en yüksek öncelik olduğu, hangi verilerin en hassas olduğu ve adli yakalama etkinleştirildiğinde kullanıcılara bildirilip bildirilmediği dahil olmak üzere kuruluşunuz için doğru ilkeleri ayarlarsınız. Adli kanıt yakalama varsayılan olarak kapalıdır ve ilke oluşturma için çift yetkilendirme gerekir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="feature-capabilities"></a>Özellik özellikleri

- **Görsel yakalama** , kuruluşların güvenlikle ilgili önemli kullanıcı etkinliklerinin kliplerini yakalamasını sağlayarak daha güvenli veya uyumlu görünürlük sağlar ve kuruluş gereksinimlerini karşılar.
- Yakalama özelliğinin etkinleştirilmesi için birden çok onay düzeyi aracılığıyla **korunan kullanıcı gizliliği**.
- **Özelleştirilebilir tetikleyiciler ve yakalama seçenekleri** , güvenlik ekiplerinin olaylara (örneğin, *Bir kullanıcı 'SecretResearchPlans.docx' indirdikten sonra 5 dakika önce ve 10 dakika sonra yakalama*) veya sürekli yakalama gereksinimlerine dayalı olarak gereksinimlerini karşılamak için adli kanıt ayarlayabileceği anlamına gelir.
- **Kullanıcı merkezli ilke hedefleme,** güvenlik ve uyumluluk ekiplerinin daha iyi bağlamsal içgörüler için cihaza değil kullanıcıya göre etkinliğe odaklanabileceği anlamına gelir.
- **Güçlü rol tabanlı erişim denetimleri (RBAC),** adli klipleri ayarlama ve gözden geçirme özelliğinin sıkı bir şekilde denetlendiği ve yalnızca kuruluştaki doğru izinlere sahip kişiler tarafından kullanılabildiği anlamına gelir.
- **Mevcut insider risk yönetimi özellikleriyle derin tümleştirme**, daha kolay ekleme ve insider risk yönetimi yöneticileri için daha tanıdık iş akışları ve güvenilir bir tek platform yaklaşımı sağlar.

## <a name="device-and-configuration-requirements"></a>Cihaz ve yapılandırma gereksinimleri

Aşağıdaki tablolarda, insider risk yönetimi adli kanıtını kullanmak için desteklenen minimum gereksinimler yer alır.

### <a name="supported-platforms"></a>Desteklenen platformlar

|**İşletim sistemi**|**Sku**|**Işlemci**|
|:----------|:-------|:-------------------|
| Windows 10 | Enterprise | 64 bit (Intel veya AMD) |
| Windows 11 | Enterprise | 64 bit (Intel veya AMD) |

### <a name="physical-devices"></a>Fiziksel cihazlar

|**Donanım**|**En düşük gereksinim**|
|:----------|:-------------------------------|
| Ram | En az 8 GB (istemci kullanımı için en az 2 GB kullanılabilir olmalıdır) |
| CPU işlemcisi | Intel i5 veya üzeri ve AMD Ryzen 5 veya üzeri |
| Grafik kartı | WDDM 1.0 veya üzeri bir sürücüyle (şu anda yalnızca tümleşik grafik kartları desteklenmektedir) DirectX 11 veya üzeri ile uyumludur|
| Disk alanı | En az 10 GB disk depolama alanı |
| Görüntü | En düşük ekran çözünürlüğü 1920 x 1080 | 

### <a name="hyper-v-and-virtual-machines"></a>Hyper-V ve sanal makineler

|**Donanım**|**En düşük gereksinim**|
|:----------|:-------------------------------|
| Ram | En az 16 GB (istemci kullanımı için en az 2 GB kullanılabilir olmalıdır) |
| CPU işlemcisi | Her vCPU işlemcisi için en az iki vCPU işlemci ve en az dört çekirdek |
| Disk alanı | En az 10 GB disk depolama alanı |
| Görüntü | En düşük ekran çözünürlüğü 1920 x 1080 | 

> [!IMPORTANT]
> Minimum gereksinimler karşılanmazsa, kullanıcılar büyük olasılıkla Microsoft Purview istemci sorunlarıyla karşılaşabilir ve adli kayıtların kalitesi güvenilir olmayabilir.

## <a name="capturing-options"></a>Yakalama seçenekleri

[Olayların, genel göstergelerin ve ilke göstergelerinin tetiklenmesi,](/microsoft-365/compliance/insider-risk-management-settings#indicators) adli kanıt ilkeleri de dahil olmak üzere tüm iç risk yönetimi ilkelerinde önemli bir rol oynar. Olayları tetikleme, kullanıcıların şirket içi risk yönetimi ilkelerinde değerlendirme kapsamına alınıp alınmadığını belirleyen kullanıcı eylemleridir. Genel ayarlar göstergeleri, insider risk yönetimi tarafından hangi etkinliklerin toplandığını belirlemek için kullanılır. İlke göstergeleri kapsam içi bir kullanıcının risk puanını belirlemek için kullanılır.

Kuruluşunuzun adli kanıt yapılandırmaya nasıl karar vermesine bağlı olarak iki yakalama seçeneği vardır:

- **Belirli etkinlikler**: Bu ilke seçeneği, etkinliği yalnızca tetikleyen bir olay onaylanan bir kullanıcıyı adli kanıt ilkesi kapsamına getirdiğinde ve kullanıcı için ilke göstergesi koşulları algılandığında yakalar. Örneğin, adli kanıt yakalama için onaylanan bir kullanıcı, adli kanıt ilkesi kapsamına alınır ve kullanıcı verileri kişisel bulut depolama hizmetlerine veya taşınabilir depolama cihazlarına kopyalar. Yakalamanın kapsamı yalnızca kullanıcı verileri kişisel bulut depolama hizmetine veya taşınabilir depolama cihazına kopyalarken yapılandırılan zaman dilimiyle belirlenir. Bu seçenek için yakalamalar **, Uyarılar** panosundaki **Adli kanıt (önizleme)** sekmesinde gözden geçirilebilir.
- **Tüm etkinlikler**: Bu ilke seçeneği, kullanıcılar tarafından gerçekleştirilen tüm etkinlikleri yakalar. Buna fare hareketi, tuş vuruşları ve insider risk göstergeleri tarafından tanımlanan tüm etkinlikler dahildir. Örneğin, kuruluşunuzun, güvenlik olayına yol açabilecek riskli olabilecek etkinliklere etkin bir şekilde katılan onaylı bir kullanıcının etkinliklerini yakalamaya yönelik zamana duyarlı bir ihtiyacı vardır. İlke göstergeleri, bir uyarının ilke tarafından oluşturulması için eşiğe ulaşmamış olabilir ve riskli olabilecek etkinlik belgelenmeyebilir. Sürekli yakalama yardımı riskli olabilecek etkinliklerin kaçırılmasını veya algılanmamasını önler. Bu seçenek için yakalamalar **, Kullanıcı etkinlik raporları** **(önizleme) panosundaki Adli kanıt (önizleme)** sekmesinde gözden geçirilebilir.

>[!IMPORTANT]
>Adli kanıt klipleri, yakalandıktan 120 gün sonra veya önizleme döneminin sonunda (hangisi daha erkense) silinir. Adli kanıt kliplerini silinmeden önce indirebilir veya aktarabilirsiniz.

## <a name="workflow"></a>Iş akışı

Küçük resim yakalama içeren uyarıları algılama, araştırma ve düzeltmeye yönelik genel iş akışı, diğer iç risk yönetimi ilkeleriyle [aynı temel adımları](/microsoft-365/compliance/insider-risk-management#workflow) izler. Ancak, kuruluşunuzda yapılandırıldığında adli kanıtlar için bazı önemli farklılıklar vardır:

- **Yakalamaya tabi kullanıcıların açık yakalama istekleri ve onayları olmalıdır**: Bu, diğer şirket içi risk yönetimi ilkelerini yapılandırmanın bir parçası olarak dahil edilmeyen ek bir işlemdir. *Insider Risk Management* veya *Insider Risk Management Yöneticileri* rol gruplarına atanan kullanıcıların, kuruluşunuzdaki herhangi bir kullanıcı herhangi bir küçük resim yakalama seçeneğine uygun olmadan önce *Insider Risk Yönetimi Onaylayanları* rol grubuna atanan kullanıcılara bir istek göndermesi gerekir. Örneğin, bu gereksinim, şirket içi risk yönetimi yöneticilerinizin herhangi bir kullanıcı için yakalama etkinleştirilmeden önce belirlenen yasal veya insan kaynakları personelinizden açık onay alması gereken kuruluş senaryolarını desteklemeye yardımcı olur.
- **Cihazların eklenip Microsoft Purview istemcisinin yüklü olması gerekir**: Adli kanıtlar uygun kullanıcılar için yakalanan klipleri toplayıp depolamadan önce cihazlarının Microsoft Purview uyumluluk portalı eklenmelidir. Ayrıca, her cihazda Microsoft Purview İstemcisi yüklü olmalıdır. Bu önkoşullar hem çevrimiçi hem de çevrimdışı cihaz yakalama desteği sağlar.

## <a name="ready-to-get-started"></a>Başlamaya hazır mısınız?

- Kuruluşunuzda adli kanıt yakalamayı yapılandırmaya yönelik adım adım yönergeler için bkz. [Insider risk yönetimi adli](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) kanıtlarını kullanmaya başlama.
- Önkoşulları yapılandırmak, ilke oluşturmak ve uyarıları almaya başlamak için bkz. [Insider risk yönetimini](/microsoft-365/compliance/insider-risk-management-configure) kullanmaya başlama.
