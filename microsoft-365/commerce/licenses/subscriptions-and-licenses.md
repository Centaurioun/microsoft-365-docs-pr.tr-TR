---
title: İş için Microsoft 365'teki abonelikleri ve lisansları anlama
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: Aldığınız uygulamalar ve hizmetler, İş için Microsoft 365 Uygulamaları gibi satın aldığınız Microsoft 365 ürününe bağlıdır.
ms.date: 05/12/2022
ms.openlocfilehash: e2494fd52ea7edcab4a68ca69e024b0561aa1d5f
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730875"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>İş için Microsoft 365'teki abonelikleri ve lisansları anlama

İş için Microsoft 365 aboneliği satın aldığınızda, yinelenen olarak ödeme yaptığınız bir dizi uygulama ve hizmet için kaydolabilirsiniz. Aboneliğinizin bir parçası olarak aldığınız uygulamalar ve hizmetler, İş için Microsoft 365 Uygulamaları veya Microsoft 365 İş Standart gibi satın aldığınız ürüne bağlıdır. [Küçük ve orta ölçekli işletmeler için Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-all-microsoft-365-business-products) sayfasında her ürünle birlikte gelenleri görebilirsiniz.

Abonelik satın alırken, kuruluşunuzdaki kişi sayısına bağlı olarak ihtiyacınız olan lisans sayısını belirtirsiniz. Abonelik satın aldıktan sonra, kuruluşunuzdaki kişiler için hesaplar oluşturur ve ardından her kişiye bir lisans atarsınız. Kuruluş gereksinimleriniz değiştikçe, yeni kişileri barındırmak için daha fazla lisans satın alabilir veya birisi kuruluşunuzdan ayrıldığında diğer kullanıcılara lisansları yeniden atayabilirsiniz.

Birden fazla aboneliğiniz varsa, her abonelik için farklı kişilere lisans atayabilirsiniz. Örneğin, bir Microsoft 365 İş Standart aboneliğinin parçası olarak tüm kullanıcılarınızı tüm Microsoft 365 uygulamalarına ve hizmetlerine atayabilirsiniz. Ayrıca, kullanıcıların bir alt kümesini ayrı bir Visio aboneliği aracılığıyla Visio Online'a atayabilirsiniz.

## <a name="how-many-devices-can-people-install-office-on"></a>Kişiler Office'i kaç cihaza yükleyebilir?

Aboneliğiniz aşağıdaki ürünlerden herhangi birini içeriyorsa, her kişi Office'i en fazla beş pc veya Mac bilgisayara, beş tablete ve beş telefona yükleyebilir.

:::row:::
   :::column span="":::
        - İş için Microsoft 365 Uygulamaları - Kurumlar için Microsoft 365 Uygulamaları - Microsoft 365 İş Standart - Microsoft 365 İş Ekstra - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>Birine lisans atadığınızda ne olur?

Aşağıdaki tabloda birine lisans atadığınızda otomatik olarak nelerin gerçekleştiği listelenir:
  
|Aboneliğe bu hizmet dahilse|Bu işlem otomatik olarak yapılır|
|---|---|
|Exchange Online|O kişi için bir posta kutusu oluşturulur. <br/> Bu görevin tamamlanması için SLA hakkında bilgi edinmek için bkz. ["Ayarlanıyor..." Microsoft 365 yönetim merkezi iletileri](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).|
|SharePoint Online|Kişiye varsayılan SharePoint Online ekip sitesi üzerinde düzenleme izinleri atanır.|
|Microsoft Teams|Kişinin lisansla ilişkili özelliklere erişimi vardır.|
|Kurumlar için Microsoft 365 Uygulamaları ve İş için Microsoft 365 Uygulamaları|Kişi Office uygulamalarını en fazla beş Mac bilgisayara veya bilgisayara, beş tablete ve beş akıllı telefona indirebilir.|

## <a name="understand-licenses-for-non-user-mailboxes"></a>Kullanıcıya ait olmayan posta kutularına yönelik lisansları anlama

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Paylaşılan posta kutusu oluşturma](../../admin/email/create-a-shared-mailbox.md)
- [Paylaşılan posta kutusundan lisans kaldırma](../../admin/email/remove-license-from-shared-mailbox.md)
- Diğer tüm Microsoft 365 planları için [Exchange Online paylaşılan Posta Kutuları](/exchange/collaboration-exo/shared-mailboxes).

## <a name="who-can-assign-licenses"></a>Kimler lisans atayabilir?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|Yönetici rolü|Lisans atama|Lisansın atamasını kaldırma|Daha fazla lisans satın alma|Hesabı silme|
|---|:---:|:---:|:---:|:---:|
|Faturalama yöneticisi|Hayır|Hayır|Evet|Hayır|
|Genel yönetici|Evet|Evet|Evet|Evet|
|Lisans yöneticisi|Evet|Evet|Hayır|Hayır|
|Hizmet Desteği yöneticisi|Hayır|Hayır|Hayır|Hayır|
|Kullanıcı yöneticisi|Evet|Evet|Hayır|Evet|

## <a name="related-content"></a>İlgili içerik

[İş aboneliğinizin lisanslarını satın alma veya kaldırma](buy-licenses.md) (makale)\
[Kullanıcılara lisans atama](../../admin/manage/assign-licenses-to-users.md) (makale)\
[Kullanıcılardan lisans atamalarını kaldırma](../../admin/manage/remove-licenses-from-users.md) (makale)\
[Paylaşılan posta kutusundan lisans kaldırma](../../admin/email/remove-license-from-shared-mailbox.md) (makale)
