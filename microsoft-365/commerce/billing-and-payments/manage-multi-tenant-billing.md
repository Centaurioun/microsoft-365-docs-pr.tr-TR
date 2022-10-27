---
title: Microsoft 365 yönetim merkezi birden çok kiracı arasında faturalamayı yönetme
f1.keywords: NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
search.appverid: MET150
description: Microsoft 365 yönetim merkezi kiracılar arasında faturalama hesaplarını paylaşmak için çok kiracılı faturalama ilişkilerini kullanmayı öğrenin.
ms.date: 08/15/2022
ms.openlocfilehash: 03e0f16f8f457ef95b6161a15078ba5374027476
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720316"
---
# <a name="manage-billing-across-multiple-tenants-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi birden çok kiracı arasında faturalamayı yönetme

Diğer kiracılarla çok kiracılı faturalama ilişkileri oluşturarak kuruluşunuz için faturalama yönetimini basitleştirebilirsiniz. Çok kiracılı faturalama ilişkisi, kuruluşunuzun ödeme hesabını diğer kiracılarla güvenli bir şekilde paylaşmanıza olanak tanırken, faturalama verileriniz üzerinde denetimi de korumanızı sağlar. Farklı kiracılarda abonelikler oluşturabilir ve bu kiracılardaki kullanıcılara kuruluşunuzun ödeme hesabına erişim sağlayabilirsiniz. Bu ilişki, bu kiracılardaki kullanıcıların faturaları görüntüleme ve indirme veya lisansları yönetme gibi faturalama etkinlikleri gerçekleştirmesini sağlar.

> [!IMPORTANT]
> Bu makale yalnızca Microsoft Müşteri Sözleşmesi sahip kuruluş hesabı müşterileri için geçerlidir.

## <a name="before-you-begin"></a>Başlamadan önce

Bu makalede açıklanan görevleri yerine getirmek için ödeme hesabı sahibi olmanız gerekir. Daha fazla bilgi için bkz. [Microsoft ödeme hesaplarınızı anlama](../manage-billing-accounts.md).

## <a name="decide-which-billing-tenant-solution-is-right-for-your-organization"></a>Kuruluşunuz için hangi faturalama kiracı çözümünün doğru olduğuna karar verme

Kuruluşunuzun gereksinimlerine bağlı olarak, birden çok faturalama kiracısı ayarlamayı seçmek doğru yaklaşım olabilir. Aşağıdaki tabloda, kuruluşunuz için hangi yaklaşımın doğru olduğuna karar vermenize yardımcı olması için tek bir kiracı veya çok kiracılı yaklaşımın kullanılması karşılaştırılır.

| **Bu faturalama alanı için**   | **Aşağıdakiler durumunda tek kiracılı ödeme hesaplarını kullanmayı göz önünde bulundurun:**  | **Aşağıdakiler durumunda tek bir ödeme hesabını paylaşan birden çok kiracı kullanmayı göz önünde bulundurun:**  |
|-----------------------------|--------------------------------------------------------|------------------------------------------------------------------------------|
| **Faturalama**               | Farklı faturalama hesapları tarafından yapılan satın almaların her zaman farklı faturalarda olmasını istiyorsunuz.    | Farklı kiracılardaki kullanıcılar tarafından yapılan satın almaların, seçiminize bağlı olarak aynı veya farklı faturalarda olmasını istiyorsunuz.  |
| **Satın alma işlemlerinizi yönetme** | Aboneliklerin yalnızca satın alındıkları kiracıda oluşturulmasını istiyorsunuz.   | Bir kiracıda satın alınan aboneliklerin aynı ödeme hesabını paylaşan farklı bir kiracıda oluşturulmasını istiyorsunuz.  |
| **Sözleşmeler**              | Kendi kiracısında yer alan her ödeme hesabının Microsoft ile kendi sözleşmesini imzalamasını istiyorsunuz. Müşteri Bağlı Kuruluş Satın Alma Koşulları (CAPT), benzersiz kiracılardaki farklı faturalama hesapları arasında ortaklık sözleşmeleri tanımlayabilir.  | Sözleşmelerin tek bir ödeme hesabıyla imzalanmasını ve aynı sözleşmelerin ödeme hesabını paylaşan tüm kiracılar için geçerli olmasını istiyorsunuz. |
| **Fiyatlandırma ve indirimler**   | Bu hesaplar CAPT koşullarını paylaşmadığı sürece birden çok ödeme hesabı arasında indirimlerin paylaşılmasını istemezsiniz.  | Bir kullanıcının hangi kiracıda satın aldığına veya bir sözleşmenin paylaşılması nedeniyle aboneliklerin nerede oluşturulduğuna bakılmaksızın ödeme hesabına indirim uygulanmasını istiyorsunuz. |
| **Görünür -lük**              | Bir ödeme hesabındaki kullanıcıların farklı bir kiracıdakileri değil, yalnızca bu ödeme hesabındakileri görünür olmasını istiyorsunuz. Örneğin, kullanıcıların yalnızca maliyetleri ve faturaları görmesini, ürün satın almasını ve kendi kiracıları için ödemeleri izlemesini istersiniz. | Paylaşılan ödeme hesapları olan kullanıcıların, bulundukları kiracıdan bağımsız olarak ödeme hesabının aynı görünümüne sahip olmasını istiyorsunuz. |
| **Güvenlik**                | Ödeme hesabınıza erişimi olan tüm kullanıcıların kiracınızın güvenlik ilkelerini izlemesini istiyorsunuz.  | Ödeme hesabınızı paylaşmaya davet ettiğiniz kullanıcıların kendi kiracılarının güvenlik ilkelerini izlemesini istiyorsunuz. |

## <a name="what-are-the-types-of-tenants-in-a-multi-tenant-billing-relationship"></a>Çok kiracılı faturalama ilişkisindeki kiracı türleri nelerdir?

Çok kiracılı faturalama senaryosunda iki tür kiracı vardır:

1. **Birincil faturalama kiracısı**— Birincil faturalama kiracısı, faturalama hesabı ayarlanırken kullanılan kiracıdır. Varsayılan olarak, tüm abonelikler bu kiracıda satın alınmaktadır ve yalnızca bu kiracıdaki kullanıcılar ödeme hesabına erişebilir.
2. **İlişkili faturalama kiracısı— İlişkili** faturalama kiracısı, birincil faturalama kiracınızın ödeme hesabına bağlı bir kiracıdır. Bu kiracılar, ödeme hesabınızı kullanarak abonelik satın alabilir veya abonelikleri sizden kabul edebilir. Ayrıca, ilişkili bir faturalama kiracısında kullanıcılara ödeme hesabı rolleri de atayabilirsiniz.

## <a name="what-access-settings-are-available-for-associated-billing-tenants"></a>İlişkili faturalama kiracıları için hangi erişim ayarları kullanılabilir?

Ödeme hesabınıza ilişkili bir faturalama kiracısı eklediğinizde, aşağıdaki erişim ayarlarından birini veya her ikisini de etkinleştirebilirsiniz.

- **Sağlama,** ilişkili faturalama kiracılarında aboneliklerin oluşturulmasına olanak tanır.
- **Faturalama yönetimi** , faturalama hesabı sahiplerinin ilişkili bir faturalama kiracısında kullanıcılara rol atamasına olanak sağlayarak faturalama bilgilerine erişmelerine ve satın alma kararları almalarına izin verir.

## <a name="add-an-associated-billing-tenant"></a>İlişkili faturalama kiracısı ekleme

Başlamadan önce, davet etmek istediğiniz kiracının kiracı kimliğine veya birincil etki alanı adına sahip olduğunuzdan emin olun. Daha fazla bilgi için bkz. [Kiracı kimliği veya etki alanı adı bulma](https://aka.ms/findtenantiddomain).

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faturalama hesapları</a> sayfasına gidin.
2. Birincil faturalama kiracısı olarak kullanmak istediğiniz ödeme hesabının adını seçin.
3. Ödeme hesabı ayrıntıları sayfasında **İlişkili faturalama kiracıları** sekmesini ve ardından **İlişkili faturalama kiracısı ekle'yi** seçin.
4. **İlişkili faturalama kiracısı** **ekle** bölmesinde kiracı kimliğini veya etki alanı adını girin ve ardından kiracı için kolay bir ad girin.
5. **Erişim ayarları** bölümünde **Sağlama** ve **Faturalama yönetimi** seçeneklerinden birini veya her ikisini birden seçin.
6. Kullanıcı görünürlüğü deyiminin yanındaki kutuyu okuyun ve seçin.
7. **Kiracı ekle'yi** seçin.

**Sağlama** erişimi ayarı açıksa, ilişkili faturalama kiracısının genel yöneticisine göndermeniz için benzersiz bir bağlantı oluşturulur. Abonelikleri kiracılarına taşıyabilmeniz için önce isteği kabul etmeleri gerekir.

## <a name="assign-roles-to-users-from-the-associated-billing-tenant-optional"></a>İlişkili faturalama kiracısından kullanıcılara roller atama (isteğe bağlı)

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faturalama hesapları</a> sayfasına gidin.
2. Rolleri atamak için ödeme hesabının adını seçin.
3. Ödeme hesabı ayrıntıları sayfasında **Faturalama hesabı rolleri** sekmesini ve ardından **Rol ata'yı seçin.**
4. **Rol ata** bölmesinde ilişkili faturalama kiracısını arayın, bir rol seçin ve rol atamak istediğiniz kullanıcıların e-posta adresini girin.
5. **Ata'yı seçin.**

Kullanıcı, rol atama isteğini gözden geçirmek için bir bağlantı içeren bir e-posta alır. Rolü kabul ettikten sonra ödeme hesabınıza erişebilirler. Ödeme hesabı rolleri hakkında bilgi için bkz. [Microsoft ödeme hesaplarınızı anlama](../manage-billing-accounts.md).

> [!IMPORTANT]
> Ödeme hesabında rolü olan herhangi bir kullanıcı, bu ödeme hesabına erişimi olan tüm kiracılardaki tüm kullanıcıları görebilir. Örneğin, birincil faturalama kiracısı Contoso.com ve ödeme hesabı sahibi ilişkili faturalama kiracısı olarak Fabrikam.com eklerse ve ardından Katarina'yı ödeme hesabı sahibi olarak eklerse, Katarina hem Contoso.com hem de Fabrikam.com ödeme hesabına erişimi olan tüm kullanıcıları görebilir.

## <a name="move-subscriptions-to-an-associated-billing-tenant-optional"></a>Abonelikleri ilişkili faturalama kiracısına taşıma (isteğe bağlı)

abonelikleri ilişkili faturalama kiracısına taşıyabilmeniz için önce ilişkili faturalama kiracısının genel yöneticisinin birincil faturalama kiracısından sağlama isteğini kabul etmesi gerekir.

> [!IMPORTANT]
> Aboneliği yalnızca abonelikteki tüm lisanslar kullanılabilir durumdaysa ilişkili bir faturalama kiracısına taşıyabilirsiniz. Herhangi bir lisans atanmışsa, aboneliği taşıyamazsınız.

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ürünleriniz</a> sayfasına gidin.
2. İlişkili faturalama kiracısına taşımak istediğiniz ürünün adını seçin.
3. Ürün ayrıntıları sayfasındaki **Tüm aboneliklerden atanan lisanslar** bölümünde **Başka bir kiracıya taşı'yı** seçin.
4. **Aboneliği farklı bir kiracıya taşı** bölmesinde bir kiracı adı arayın veya listeden bir kiracı seçin, ardından **Aboneliği** **taşı'yı** seçin.

## <a name="remove-an-associated-billing-tenant"></a>İlişkili faturalama kiracısını kaldırma

İlişkili faturalama kiracısını kaldırmak kalıcı bir eylemdir ve geri alınamaz. Faturalama hesabınızda roller atanmış olan tüm kiracı kullanıcıları için Erişim kaldırılır ve artık abonelikleri kiracıya taşıyamayasınız. Zaten taşınmış olan abonelikler kiracıda kalır ve ödeme hesabınıza faturalandırılır.

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faturalama hesapları</a> sayfasına gidin.
2. Birincil faturalama kiracısı olan ödeme hesabının adını seçin.
3. Ödeme hesabı ayrıntıları sayfasında **İlişkili faturalama kiracıları** sekmesini seçin.
4. Kaldırmak istediğiniz ilişkili faturalama kiracısını seçin.
5. İlişkili faturalama kiracısı bölmesinde **Erişimi kaldır'ı seçin.**
6. **Sağlama ve faturalama yönetimi** **erişimini** kaldır bölmesinde **Erişimi kaldır'ı seçin.**
7. Onay iletişim kutusunda **Evet'i** seçin.

## <a name="accept-or-decline-an-invitation-for-provisioning-access-to-your-associated-billing-tenant"></a>İlişkili faturalama kiracınıza erişim sağlama davetini kabul etme veya reddetme

İlişkili bir faturalama kiracısının genel yöneticisi olarak, kiracınızda abonelik oluşturmak için ödeme hesabı sahibinden gelen bir isteği kabul edebilir veya reddedebilirsiniz. Ödeme hesabı sahibi kiracınızı ilişkili bir faturalama kiracısı olarak eklediğinde ve **Sağlama** erişimi ayarını etkinleştirdiğinde, daveti kabul etmek veya reddetmek için ödeme hesabı sahibinden bir bağlantı alırsınız.

1. Ödeme hesabı sahibi tarafından paylaşılan bağlantıyı seçin.
2. **İlişkili faturalama kiracısı olma daveti** sayfasında **Kabul Et** veya **Reddet'i** seçin.

> [!NOTE]
> Daha sonra **Sağlama** erişimini iptal etmeye karar verirseniz, aynı bağlantıyı kullanabilirsiniz.

## <a name="related-articles"></a>İlgili makaleler

[Microsoft ödeme hesaplarınızı anlama](../manage-billing-accounts.md) (makale)\
[Faturalama profillerini anlama](manage-billing-profiles.md) (makale)
