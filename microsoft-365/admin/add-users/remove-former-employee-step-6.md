---
title: 6. Adım - Eski bir çalışandan Microsoft 365 lisansını kaldırma ve silme
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: Eski bir çalışanın Microsoft 365 lisansını kaldırabilir ve aboneliğinizden silebilir veya lisansı başka bir kullanıcıya atayabilirsiniz.
ms.openlocfilehash: c990493402054569c3dae866526a89348a0d9850
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721658"
---
# <a name="step-6---remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>6. Adım - Eski bir çalışandan Microsoft 365 lisansını kaldırma ve silme

Birisi kuruluşunuzdan ayrıldıktan sonra lisans için ödeme yapmak istemiyorsanız, microsoft 365 lisansını kaldırmanız ve ardından aboneliğinizden silmeniz gerekir. Silmezseniz başka bir kullanıcıya lisans atayabilirsiniz.

Posta kutusuna uyumluluk veya yasal nedenlerle eBulma izinleri verilmiş yetkili kişiler tarafından erişilmesi gerekiyorsa, Exchange Online Plan 2 lisansına (veya Exchange Online Arşivleme sahip Exchange Online Plan 1 lisansına) atanması gerekir  eklenti lisansı) seçerek saklamanın silinmeden önce posta kutusuna uygulanabilmesini sağlar. Kullanıcı hesabı silindikten sonra, kullanıcı hesabıyla ilişkili tüm Exchange Online lisansları yeni bir kullanıcıya atanabilecektir.
  
Lisansı kaldırdığınızda, bu kullanıcının tüm verileri 30 gün süreyle tutulur. Verilere [erişebilir](get-access-to-and-back-up-a-former-user-s-data.md) veya kullanıcı geri dönerse hesabı [geri yükleyebilirsiniz](restore-user.md). 30 gün sonra, kullanıcının tüm verileri (SharePoint Online'da depolanan belgeler hariç) Microsoft 365'ten kalıcı olarak silinir ve kurtarılamaz.

1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.
2. Engellemek istediğiniz çalışanın adını seçin ve ardından **Lisanslar ve Uygulamalar** sekmesini seçin.
3. Kaldırmak istediğiniz lisansların onay kutularını temizleyin ve değişiklikleri **kaydet'i** seçin.

Başka bir kişiyi işe **alana kadar ödediğiniz lisans sayısını azaltmak için** aşağıdaki adımları uygulayın:

1. Yönetim merkezinde <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ürünlerinizi</a> **Faturalama** \> sayfasına gidin ve **Ürünler** sekmesini seçin.
2. Lisansları kaldırmak istediğiniz aboneliği seçin.
3. Ayrıntılar sayfasında **Lisansları kaldır'ı** seçin.
4. **Lisansları kaldır** bölmesindeki Yeni miktar'ın altında, **Toplam lisanslar** kutusuna bu abonelik için istediğiniz toplam lisans sayısını girin. Örneğin, 25 lisansınız varsa ve bunlardan birini kaldırmak istiyorsanız 24 girin.
5. **Kaydet**'i seçin.

İşletmenize [başka bir kişi eklediğinizde](add-users.md) , tek bir adımla aynı anda lisans satın almanız istenir!

İşletmeler için Microsoft 365 kullanıcı lisanslarını yönetme hakkında daha fazla bilgi için bkz. [İş için Microsoft 365'te kullanıcılara lisans atama ve İş için Microsoft](../manage/assign-licenses-to-users.md) [365'teki kullanıcılardan lisans atamasını kaldırma](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Silinen çalışan hesabının Skype Kurumsal üzerindeki etkisi

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Kuruluşunuzdaki kişilere arama iletmeyi ayarlama

Sonlandırılan çalışanın telefon numarası için arama iletmeyi ayarlamanız gerekiyorsa, arama ilkeleri altındaki arama iletme ayarı, gelen aramaların diğer kullanıcılara iletilebileceği veya aynı anda başka bir kişiyi çaldırabileceği iletmeyi ayarlayabilir. Daha fazla bilgi için bkz [. Microsoft Teams'de ilkeleri çağırma](/microsoftteams/teams-calling-policy).
