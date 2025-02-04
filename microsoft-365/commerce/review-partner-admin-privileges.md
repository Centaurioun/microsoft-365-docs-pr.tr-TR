---
title: İş ortağı yönetim ayrıcalıklarını gözden geçirme
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- empty
search.appverid: MET150
description: Sahip oldukları yönetici ayrıcalıklarını belirlemek için Microsoft sertifikalı çözüm sağlayıcıları (iş ortakları) listenizi gözden geçirmeyi ve bu ayrıcalıkları kaldırmayı öğrenin.
ms.date: 12/03/2021
ms.openlocfilehash: 67cafa9ebac7f641de43f0debab733d89a8b1853
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718314"
---
# <a name="review-microsoft-certified-cloud-solution-provider-partner-administrative-privileges"></a>Microsoft sertifikalı bulut çözümü sağlayıcısı iş ortağı yönetim ayrıcalıklarını gözden geçirin

Microsoft sertifikalı bir bulut çözümü sağlayıcınız (bayi iş ortağı) varsa, kendisine atanan yönetici ayrıcalıkları (DAP) için üç aylık bir gözden geçirme gerçekleştirmenizi öneririz. Kuruluşunuzun bu iş ortağının kuruluşunuzun verilerine erişmesini ve sizin adınıza satın almalar yapmasını istediğinden emin olun.

> [!IMPORTANT]
> Genel yönetici izinlerini içeren DAP'nin herhangi bir iş ortağına verilmesi güvenlik riski doğurabilir. Çok fazla Genel yöneticiye sahip olmak da bir güvenlik riskidir. [Temsilci ayrıcalıklarını hedefleyen son etkinlikler hakkında daha fazla bilgi edinin](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/).

Kurumsal bayi iş ortağından bir DAP sözleşmesini kabul ettikten sonra, kuruluşunuz için genel yönetici rolünü çalışanlarına atayabilirler. Genel yönetici rolü, iş ortağının çalışanlarına çalışanlarınızın kişisel verilerine ve diğer hassas bilgilere erişmesini sağlar. Ayrıca aşağıdaki eylemler gibi kiracı genelinde eylemler gerçekleştirme izni de verir:

- Kullanıcı parolalarını değiştirme
- E-posta hesaplarıyla kullanıcı ekleme
- Kuruluşunuzla ilişkili web etki alanlarını ekleme ve yönetme

DAP etkinleştirildiğinde, iş ortağınızın ekleyebileceği Genel yönetici sayısı üzerinde denetim sahibi olmazsınız. Hesabınıza yalnızca iş ortağı DAP (Genel yönetici) erişimi verebilir veya reddedebilirsiniz.

## <a name="review-and-remove-roles-from-partners"></a>İş ortaklarının rollerini gözden geçirme ve kaldırma

1. Microsoft 365 yönetim merkezi **Ayarlar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">İş Ortağı ilişkileri</a> sayfasına gidin. DAP'lı iş ortaklarının **Roller** sütununda **Genel Yönetici** listelenir.
2. Bir iş ortağından Genel yönetici rolünü kaldırmak için kaldırmak istediğiniz iş ortağının adını bulun.
3. **İlişki Türü** olarak **Bayi'nin** bulunduğu satırı seçin.
4. İş ortağı ayrıntıları sayfasında **Rolleri kaldır'ı** ve ardından **Evet'i** seçin.

> [!NOTE]
>
> - Bir iş ortağından DAP'ı (Genel yönetici rolü) kaldırırsanız, gelecekteki hizmet teslimi hakkında görüşmek için bu kişiyle iletişime geçmenizi öneririz. Örneğin, daha düşük ayrıcalıklara sahip bir kullanıcı hesabı oluşturabilir ve bu hesap bilgilerini iş ortağınızla paylaşabilirsiniz. [Kullanıcı ekleme](../admin/add-users/add-users.md) ve [yönetici rolleri atama](../admin/add-users/assign-admin-roles.md) hakkında daha fazla bilgi edinin.
> - Genel yönetici rolü kaldırılmış olsa bile iş ortağı sizin adınıza satın alma işlemleri yapabilir. İş Ortağı Merkezi'nde bu özelliği kaldırmasını istemek için iş ortağına başvurmanızı öneririz.

## <a name="related-content"></a>İlgili içerik

[İş ortağı ilişkilerini yönetme](manage-partners.md) (makale)\
[Yönetici rolleri hakkında](../admin/add-users/about-admin-roles.md) (makale)\
[Azure AD yönetici ayrıcalıkları](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad) (makale)
