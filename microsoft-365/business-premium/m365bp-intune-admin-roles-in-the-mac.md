---
title: Microsoft 365 yönetim merkezi Intune yönetici rolleri hakkında
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection: ''
ms.custom: ''
description: Microsoft 365 yönetim merkezi, iş işlevlerine eşlenen ve belirli görevleri gerçekleştirme izinleri veren bazı Microsoft Intune rolleri yönetmenize olanak tanır.
ms.openlocfilehash: 6d3390a6c17de417e22a851ad3f227ebccc952d4
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67737796"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi yönetici rollerini Intune

Microsoft 365 veya Office 365 aboneliğiniz, <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> kullanarak kuruluşunuzdaki tüm kullanıcılara atayabileceğiniz bir dizi yönetici rolüyle birlikte gelir. Her bir yönetici rolü, işletme ile ilgili genel işlevlere yöneliktir ve kuruluşunuzdaki kişilere, yönetim merkezlerinde belirli görevler yapma izni verir. Bu roller, Intune yönetim merkezinde bulunan ve Intune özgü ek rolleri içeren tüm rollerin yalnızca bir alt kümesidir.

Belirli Intune rolleri eklemeden önce rollerin Azure AD atanması gerekir. Bu rolleri görmek için **Endpoint Manager > Kiracı yönetimi > Roller > Tüm roller >** öğesini seçin. Rolü aşağıdaki sayfalarda yönetebilirsiniz:

- Özellikler: Rolün adı, açıklaması, izinleri ve kapsam etiketleri.
- Atamalar: Hangi kullanıcıların hangi kullanıcılara veya cihazlara erişimi olduğunu tanımlayan rol atamalarının listesi. Bir rolün birden çok ataması olabilir ve bir kullanıcı birden çok atamada yer alabilir.

## <a name="about-roles-based-access-control-in-intune"></a>Intune'de rol tabanlı erişim denetimi hakkında

Rol tabanlı erişim denetimi (RBAC), kuruluşunuzun kaynaklarına kimlerin erişebileceğini ve bu kaynaklarla neler yapabileceklerini yönetmenize yardımcı olur. Intune kullanıcılarınıza roller atayarak, görebileceklerini ve değiştirebileceklerini sınırlayabilirsiniz. Hem yerleşik hem de özel roller vardır ve her rolün, kuruluşunuzda hangi kullanıcılara erişebileceğini veya değiştirebileceğini belirleyen bir dizi izni vardır. Aşağıdaki bilgiler, Intune'deki her iki rol türünü de kapsar.

Rol oluşturmak, düzenlemek veya atamak için hesabınızın Azure AD'de aşağıdaki izinlerden birine sahip olması gerekir:

- **Genel Yönetici**
- **Intune Hizmet Yöneticisi** (**Intune Yöneticisi** olarak da bilinir ancak yerleşik **Intune Rol Yöneticisi** rolüyle karıştırılmamalıdır.)

[Azure Active Directory rolleri ve RBAC](/azure/active-directory/roles/permissions-reference.md) hakkında daha fazla bilgi edinin.

## <a name="microsoft-intune-built-in-roles"></a>Yerleşik rolleri Microsoft Intune

Yerleşik roller, yaygın Intune senaryolarına göre önceden tanımlanmış kurallar kullanır. Alternatif olarak, özel roller sizin tarafınızdan kesin olarak tanımlanan kurallar üzerine oluşturulur. 

Atayabileceğiniz yerleşik roller şunlardır:

|Yönetici rolü     |Bu role kim atanmalıdır?  |
|---------|---------|
|**Uygulama yöneticisi**     |   Uygulama yöneticisi rolünü mobil uygulamalar için uygulama yaşam döngüsünü yöneten, ilkeyle yönetilen uygulamaları yapılandıran ve cihaz bilgilerini ve yapılandırma profillerini görüntüleyen kullanıcılara atayın.  |
|**Yardım masası operatörü**     |   Kullanıcılara ve cihazlara uygulama ve ilke atayan kullanıcılara yardım masası operatörü rolünü atayın. |
|**Intune rol yöneticisi**    |   Intune rol yöneticisini, diğer yöneticilere Intune izinleri atayabilen ve özel ve yerleşik Intune rollerini yönetebilen kullanıcılara atayın.   |
|**İlke ve profil yöneticisi**     |   Uyumluluk ilkesini, yapılandırma profillerini ve Apple kaydını yöneten kullanıcılara ilke ve profil yöneticisi rolünü atayın.   |
|**Salt okunur işleç**     |   Salt okunur işleç rolünü yalnızca kullanıcıları, cihazları, kayıt ayrıntılarını ve yapılandırmaları görüntüleyebilen kullanıcılara atayın.   |
|**Okul yöneticisi**     |   Eğitim için Intune'da Windows 10-11 ve iOS cihazlarını, uygulamalarını ve yapılandırmalarını yönetmek için kullanıcılara tam erişim için okul yöneticisi rolünü atayın.   |
|**Cloud PC Yöneticisi**     |   Cloud PC Yöneticisi, Cloud PC dikey penceresinde bulunan tüm Cloud PC özelliklerine okuma ve yazma erişimine sahiptir.   |
|**Bulut BILGISAYAR Okuyucusu**     |   Cloud PC Reader, Cloud PC dikey penceresinde bulunan tüm Cloud PC özelliklerine okuma erişimine sahiptir.   |

## <a name="microsoft-intune-custom-roles"></a>Özel rolleri Microsoft Intune

Intune belirli bir iş işlevi için gerekli izinleri içeren özel roller oluşturabilirsiniz. Örneğin, bir BT departmanı grubu uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa, tüm bu izinleri tek bir özel rolde birlikte ekleyebilirsiniz. Özel bir rol oluşturduktan sonra, bu rolü bu izinlere ihtiyaç duyan tüm kullanıcılara atayabilirsiniz.

Yerleşik rollerde olduğu gibi rol oluşturmak, düzenlemek veya atamak için hesabınızın Azure AD'da aşağıdaki izinlerden birine sahip olması gerekir:

- **Genel Yönetici**
- **Intune Hizmet Yöneticisi** (**Intune Yöneticisi** olarak da bilinir ancak yerleşik **Intune Rol Yöneticisi** rolüyle karıştırılmamalıdır.)

Özel rol oluşturmak için:

1. Microsoft Endpoint Manager yönetim merkezinde **Kiracı yönetimi > Roller > Oluştur > Tüm roller'i** seçin.

1. **Temel Bilgiler** sayfasında, yeni rol için bir ad ve açıklama girin ve **İleri'yi** seçin.

1. **İzinler** sayfasında, bu rolle kullanmak istediğiniz izinleri seçin.

1. **Kapsam (Etiketler)** sayfasında bu rolün etiketlerini seçin. Bu rol bir kullanıcıya atandığında, bu kullanıcı da bu etiketlere sahip kaynaklara erişebilir. **İleri**'yi seçin.

1. **Gözden Geçir + oluştur** sayfasında, işiniz bittiğinde, **Oluştur**'u seçin. Yeni rol **, Intune rolleri - Tüm roller** dikey penceresindeki listede görüntülenir.

Rolü kopyalamak için:

1. Microsoft Endpoint Manager yönetim merkezinde **Kiracı yönetimi > Roller > Tüm roller'i seçin >** **Yinelenen** > listedeki bir rolün onay kutusunu seçin.

1. **Temel Bilgiler** sayfasında bir ad girin. Benzersiz bir ad kullandığınızdan emin olun.

1. Özgün roldeki tüm izinler ve kapsam etiketleri zaten seçili olacaktır. Daha sonra yinelenen rolün **Adı, Açıklaması, İzinleri ve Kapsamı (Etiketler)** değiştirebilirsiniz.

1. İstediğiniz tüm değişiklikleri yaptıktan sonra gözden geçir ve oluştur sayfasına ulaşmak için İleri'yi seçin. **Oluştur**’u seçin.

> [!Note]
>Intune yönetebilmek için atanmış bir Intune lisansınız olmalıdır. Alternatif olarak, **Lisanssız yöneticilere erişime izin ver** ayarını **Evet** olarak ayarlayarak lisanslı olmayan kullanıcıların Intune yönetmesine izin vekleyebilirsiniz.

## <a name="how-to-assign-a-role"></a>Rol atama

Intune bir kullanıcıya yerleşik veya özel rol atayabilirsiniz. Rol oluşturmak, düzenlemek veya atamak için hesabınızın Azure AD'de aşağıdaki izinlerden birine sahip olması gerekir:

- **Genel Yönetici**
- **Intune Hizmet Yöneticisi** (**Intune Yöneticisi** olarak da bilinir ancak yerleşik **Intune Rol Yöneticisi** rolüyle karıştırılmamalıdır.)

1. Microsoft Endpoint Manager yönetim merkezinde **Kiracı yönetimi > Roller > Tüm roller'i** seçin.

1. **Endpoint Manager rolleri - Tüm roller** dikey penceresinde, > Atamaları > + Ata'yı atamak istediğiniz yerleşik rolü seçin.

1. **Temel Bilgiler** sayfasında, bir Atama adı ve isteğe bağlı Atama açıklaması girin ve **İleri'yi** seçin.

1. **Yönetici Grupları** sayfasında, izin vermek istediğiniz kullanıcıyı içeren grubu seçin. **İleri**'yi seçin.

1. **Kapsam (Gruplar)** sayfasında, yukarıdaki üyenin yönetmesine izin verilecek kullanıcıları ve cihazları içeren bir grup seçin. Ayrıca tüm kullanıcıları veya tüm cihazları seçme seçeneğiniz de vardır. **İleri**'yi seçin.

> [!Note]
> **Tüm kullanıcılar** ve **Tüm cihazlar**, Azure Active Directory (Azure AD) güvenlik grupları değil Intune **sanal** gruplardır. Sonuç olarak, **Kapsam (Gruplar)** ataması amacıyla bunları Azure AD güvenlik gruplarının ebeveyni olarak kullanamazsınız. **Kapsam (Gruplar)** atamaları için hem **Tüm kullanıcılara** hem de **Tüm cihazlara** ve belirli Azure AD güvenlik gruplarına ihtiyacınız varsa, bunları ayrı atamalarla ayrı olarak eklemeniz gerekir. Aksi takdirde, bir rol için Kapsam (Gruplar) ataması **Tüm Kullanıcılar** olarak ayarlanmış olsa bile, bu roldeki yöneticinin belirli Azure AD kullanıcı gruplarına erişimi olmaz. Azure AD güvenlik grupları için iç içe yerleştirme desteklenir.

6. **Kapsam (Etiketler)** sayfasında, bu rol atamasının uygulanacağı etiketleri seçin. **İleri**'yi seçin.

7. **Gözden Geçir + Oluştur** sayfasında, işiniz bittiğinde **Oluştur'u** seçin. Yeni atama, atama listesinde görüntülenir.

> [!Note]
> Kapsam grupları oluşturduğunuzda ve bir kapsam etiketi atadığınızda, yalnızca rol atamanızın Kapsam (Gruplar) içinde listelenen grupları hedefleyebilirsiniz.

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft İş ortakları için temsilci yönetim

Bir Microsoft iş ortağıyla çalışıyorsanız, iş ortağınız için yönetici rolleri atayabilirsiniz. İş ortağınız da sizin şirketinizdeki ya da kendi şirketindeki kullanıcılara yönetici rolleri atayabilir. Örneğin, çevrimiçi kuruluşunuzu sizin için ayarlayıp yönetiyorlarsa, bunu yapmalarını isteyebilirsiniz.
  
Bir iş ortağı şu rolleri atayabilir: 
  
- İş Ortağı Merkezi aracılığıyla çok faktörlü kimlik doğrulamasını yönetmek dışında genel yöneticiye eşdeğer ayrıcalıklara sahip tam yönetim.

- Yardım masası yöneticisiyle eşdeğer ayrıcalıklara sahip sınırlı yönetim.

İş ortağının kullanıcılara bu rolleri atamadan önce, iş ortağını hesabınıza yönetici temsilcisi olarak eklemeniz gerekir. Bu süreç yetkili bir iş ortağı tarafından başlatılır. İş ortağı, kendisine yönetici temsilcisi olarak hareket etme izni vermek isteyip istemediğinizi sormak için size bir e-posta gönderir. Yönergeler için bkz. [İş ortağı ilişkilerini yetkilendirme veya kaldırma](../admin/misc/add-partner.md).
  
## <a name="related-content"></a>İlgili içerik

[Microsoft 365 yönetici rolleri hakkında](../admin/add-users/about-admin-roles.md) (makale)\
[Yönetici rollerini atama](../admin/add-users/assign-admin-roles.md) (makale)\
[Microsoft 365 yönetim merkezi etkinlik raporları](../admin/activity-reports/activity-reports.md) (makale)
