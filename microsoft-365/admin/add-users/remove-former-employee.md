---
title: Eski çalışanı kaldırma - Genel Bakış
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- adminvideo
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
description: Eski bir çalışanın oturum açmaması, kuruluş verilerinin güvenliğini sağlamaması ve diğer çalışanların e-posta ve OneDrive verilerine erişmesine izin vermemesi için Microsoft 365 erişimini engelleyin.
ms.openlocfilehash: 4b1367e636966c772845ea575ccc86ba1d8c5f1a
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721702"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Genel bakış: Eski bir çalışanı ve güvenli verileri kaldırma

YouTube'da [Microsoft 365 küçük işletme yardımına](https://go.microsoft.com/fwlink/?linkid=2197659) göz atın.

Sık sık aldığımız bir soru şudur: "Bir çalışan kuruluşumdan ayrıldığında verilerin güvenliğini sağlamak ve erişimi korumak için ne yapmalıyım?" Bu makale serisinde, bu kullanıcıların Microsoft 365'te oturum açamamalarını sağlamak için Microsoft 365'e erişimi nasıl engelleyebileceğiniz, kuruluş verilerinin güvenliğini sağlamak için atılması gereken adımlar ve diğer çalışanların e-posta ve OneDrive verilerine erişmesine nasıl izin verebileceğiniz açıklanır.

> [!TIP]
> Bu konuda verilen adımlarla ilgili yardıma ihtiyacınız varsa[bir Microsoft küçük işletme uzmanıyla çalışmayı](https://go.microsoft.com/fwlink/?linkid=2186871) göz önünde bulundurun. İşletme Yardımı ile, işletmenizi büyütürken katılımdan gündelik kullanıma kadar her aşamada siz ve çalışanlarınız günün 24 saati küçük işletme uzmanlarına erişebilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Bu çözümdeki adımları tamamlamak için genel yönetici olmanız gerekir.

Bu serideki adımları tamamlamak için bu Microsoft 365 özelliklerini ve özelliklerini kullanırsınız.

|Ürün veya bileşen|Yetenek veya özellik|
|---|---|
|Microsoft 365 yönetici merkezi|Posta kutusunu dönüştürme, e-postayı iletme, erişimi iptal etme, kullanıcıyı kaldırma |
|Exchange yönetim merkezi|Kullanıcıyı engelle, e-posta erişimini engelle, cihazı temizle |
|OneDrive ve SharePoint |Diğer kullanıcılara erişim verme |
|Outlook|Pst dosyalarını içeri aktarma, posta kutusu ekleme |
|Active Directory|Karma ortamlarda kullanıcıları kaldırma |


## <a name="solution-remove-a-former-employee"></a>Çözüm: Eski çalışanı kaldırma

> [!IMPORTANT]
> Bu çözümdeki adımları numaralandırmış olsak da ve tam sırayı kullanarak çözümü tamamlamanıza gerek olmasa da, adımları bu şekilde gerçekleştirmenizi öneririz.

:::image type="content" source="../../media/delete-user-account.png" alt-text="Ekran görüntüsü: Kuruluşunuzdan eski bir çalışanı kaldırma adımları":::

<br>

****

|Adım|Neden yapılmalı|
|---|---|
|[1. Adım - Eski bir çalışanın oturum açmasını engelleme ve Microsoft 365 hizmetlerine erişimi engelleme](remove-former-employee-step-1.md)|Bu, eski çalışanınızın Microsoft 365'te oturum açmasını engeller ve kişinin Microsoft 365 hizmetlerine erişmesini engeller.|
|[2. Adım - Eski çalışanın posta kutusunun içeriğini kaydetme](remove-former-employee-step-2.md)|Bu, çalışanın işini devralacak olan kişi veya dava varsa yararlıdır.|
|[3. Adım - Eski bir çalışanın mobil cihazını silme ve engelleme](remove-former-employee-step-3.md)|Telefondan veya tabletten iş verilerinizi kaldırır.|
|[4. Adım - Eski çalışanın e-postasını başka bir çalışana iletme veya paylaşılan posta kutusuna dönüştürme](remove-former-employee-step-4.md)|This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.|
|[5. Adım - Başka bir çalışana OneDrive ve Outlook verilerine erişim verme](remove-former-employee-step-5.md)|Kullanıcının yalnızca lisansını iptal eder ancak hesabını silmezseniz kullanıcının OneDrive'da bulunan içeriğine, 30 gün geçtikten sonra bile erişebilirsiniz. <p> Hesabı silmeden önce, başka bir kullanıcıya OneDrive ve Outlook erişimi vermelisiniz. Bir çalışanın hesabını sildikten sonra, OneDrive ve Outlook'taki içerik **30** gün boyunca saklanır. Ancak bu 30 gün boyunca kullanıcının hesabını geri yükleyebilir ve içeriğine erişebilirsiniz. Kullanıcının hesabını geri yüklerseniz, OneDrive ve Outlook içeriği 30 gün sonra bile sizin için erişilebilir kalır.| 
|[6. Adım - Eski bir çalışandan Microsoft 365 lisansını kaldırma ve silme](remove-former-employee-step-6.md)|When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. <p> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.|
|[7. Adım - Eski çalışanın kullanıcı hesabını silme](remove-former-employee-step-7.md)|Bu işlem hesabı yönetim merkezinizden kaldırır. Ortamı temiz tutmanızı sağlar.|

## <a name="watch-delete-a-user"></a>İzleyin: Kullanıcıyı silme

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198203) bu videoya ve diğer videolara göz atın.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

Bir çalışan şirketten ayrıldığında, bu çalışanı İş için Microsoft 365'ten kaldırmanız gerekir. Bunu yapmadan önce, şirket dosyalarına erişmelerini engellemeniz, oluşturdukları belgeleri korumanız ve bir kullanıcıyı kaldırmayla ilişkili diğer birkaç yönetici görevini gerçekleştirmeniz gerekir.

1. Yönetim merkezinde **Kullanıcılar'ı ve** **ardından Etkin kullanıcılar'ı** seçin.
1. Kaldırmak istediğiniz kullanıcıyı seçin ve ardından **Kullanıcıyı sil'i** seçin.
1. Lisansını kaldırmak için kutuyu işaretleyin ve e-posta diğer adlarını kaldırmak için kutuyu işaretleyin.
1. Başka bir kullanıcıya eski çalışanın e-postasına erişim vermek için kutuyu işaretleyin ve **Kullanıcı seç'i seçip e-posta seçeneklerini ayarlayın**.
1. İlişkili e-posta diğer adlarını kaldırmak için diğer adlarının yanındaki **X'i** seçin.
1. Paylaşılan posta kutusu bilgilerini gözden geçirin ve **Son'u** seçin.
1. Seçeneklerinizin doğru ayarlandığını onaylayın ve **Ata ve dönüştür'ü** seçin.
1. Sonuçlarınızı gözden geçirin ve **Kapat'ı** seçin.

Bir kullanıcıyı kaldırdıktan sonra hesabını geri yüklemek için en fazla 30 gününüz olur.
## <a name="related-content"></a>İlgili içerik

[Kullanıcıyı geri yükleme](restore-user.md) (makale)\
[Microsoft 365'e yeni bir çalışan ekleme](add-new-employee.md) (makale)\
[Kullanıcılara lisans atama](../manage/assign-licenses-to-users.md) (makale)\
[Remove-CalendarEvents](/powershell/module/exchange/remove-calendarevents)\
[Kullanıcılardan lisans atamalarını kaldırma](../manage/remove-licenses-from-users.md) (makale)
