---
title: Kuruluşunuzdan kullanıcı silme
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
- scotvorg
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Microsoft 365 kullanıcı hesabını silmeyi, kullanıcının e-postası ve OneDrive içeriğiyle ne yapacağınızı ve ürün lisansını koruyup korumayacağınızı öğrenin.
ms.openlocfilehash: 1eb9354352f81ff3934b2bb5a0b7d2af4c69a581
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68192761"
---
# <a name="delete-a-user-from-your-organization"></a>Kuruluşunuzdan kullanıcı silme
  
**İş yerinde veya okulda kullandığınız *kendi* Microsoft 365 kullanıcı hesabınızı nasıl sileceğinizi mi arıyorsunuz? Bu adımları sizin yerinize gerçekleştirmek için iş veya üniversitenizdeki teknik desteğe başvurun.**

## <a name="before-you-begin"></a>Başlamadan önce

- Yalnızca işletme veya okul için [Microsoft 365 genel yönetici](about-admin-roles.md) veya Kullanıcı yönetimi izinlerine sahip kişiler kullanıcı hesaplarını silebilir.
- Kullanıcının verileri kalıcı olarak silinmeden önce hesabı [geri yüklemek](restore-user.md) için 30 gününüz vardır.
- Kullanıcının OneDrive verilerini saklamak istiyorsanız, verileri farklı bir konuma taşıyın. Hatta hesabı sildikten sonra verileri 30 güne kadar taşıyabilirsiniz. Bkz. [Eski bir kullanıcının verilerine erişim ve verileri yedekleme](get-access-to-and-back-up-a-former-user-s-data.md). SharePoint dosyalarını taşımanız gerekmez; bunlara erişmeye devam edersiniz.
- If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
- Office 365 Kurumsal E3 gibi bir Kurumsal aboneliğiniz varsa, silinen bir kullanıcı hesabının posta kutusu verilerini *etkin olmayan posta kutusuna* dönüştürerek koruyabilirsiniz. Daha fazla bilgi için bkz. [Exchange Online'da etkin olmayan posta kutularını yönetme](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Genel yönetici: Kullanıcı silme, kullanıcının lisansı için ödeme yapmayı bırakma ve kullanıcının e-postasıyla ve OneDrive içeriğiyle ne yapılacağına karar verme

Genel yöneticiyseniz, bir kullanıcıyı sildiğinizde başka bir kullanıcının sildiğiniz kullanıcının e-postasına erişmesini sağlayabilir ve sildiğiniz kullanıcının OneDrive içeriğiyle ne yapılacağına karar verebilirsiniz.

### <a name="things-to-consider"></a>Göz önüne alınacak noktalar

Başlamadan önce, kullanıcının e-postası ve OneDrive içeriği ile ne yapmak istediğinizi düşünün ve lisansı elinizde tutma ya da ödemeyi bırakma konusunda bir karar verin.
  
|Öğe | Açıklama |
|:-----|:-----|
|Ürün lisansları  <br/> |You can remove the license from the user and remove it from your subscriptions to stop paying for that license. If you select this option, the license will be removed automatically from your subscriptions.  <br/><br/> Lisansı bir iş ortağı aracılığıyla ya da toplu lisanslama üzerinden satın aldıysanız **kaldıramazsınız**. Yıllık plan için ödeme yapıyorsanız veya faturalama döneminin ortasındaysanız, taahhüdünüz tamamlanana kadar lisansı aboneliğinizden kaldıramazsınız.  <br/> |
|OneDrive içeriği  <br/> |Kullanıcı, dosyalarını OneDrive'a kaydettiyse, başka bir kullanıcıya bu dosyalar için erişim verebilirsiniz.  <br/><br/> Saklamak istediğiniz dosyaları, OneDrive dosyaları için ayarlanan bekletme süresi içinde taşımanız gerekir. **Varsayılan olarak, bekletme süresi 30 gündür.** Kullanıcıları sildikten sonra dosyaları saklama süresi içinde taşımıyorsanız, silinen kullanıcının OneDrive'ı site koleksiyonu geri dönüşüm kutusuna taşınır ve burada 93 gün boyunca tutulur. Bu süre boyunca kullanıcılar artık OneDrive'daki paylaşılan içeriğe erişemeyecektir. OneDrive'ı geri yüklemek için PowerShell'i kullanmanız gerekir. Bilgi için bkz. [Silinen OneDrive'ı geri yükleme](/onedrive/restore-deleted-onedrive).<br/><br/> Silinen hesapların OneDrive dosyalarını bekletebildiğiniz gün sayısını artırmak için bkz [Silinen kullanıcılar için OneDrive bekletme süresini ayarlama](/onedrive/set-retention).  <br/><br/> **Önemli!** Silinen kullanıcı SharePoint ve OneDrive'dan dosya indirmek için kişisel bir bilgisayar kullandıysa, bilgisayarında depoladıkları dosyaları temizlemenin bir yolu yoktur. Kullanıcı, OneDrive'dan eşitlenen tüm dosyalara erişmeye devam eder.           |
|E-posta  <br/> | Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox. The new mailbox owner can then access the mailbox and monitor for new email. You'll also have the following options:  <br/>  <br/>Görünen adı değiştirme - **Etkin kullanıcılar** listesinde paylaşılan posta kutusunu kolayca tanımlayacak şekilde görünen adı değiştirmenizi öneririz.  <br/>  <br/>  Otomatik yanıtları açma - Sizin için kibar bir otomatik yanıt hazırladık. Kuruluşunuzdaki kişilere ve kuruluşunuzun dışındaki kişilere farklı otomatik yanıtlar gönderebilirsiniz. <br/> <br/> PowerShell kullanarak [mevcut takvim izinlerini kaldırın](/powershell/module/exchange/remove-mailboxfolderpermission?view=exchange-ps). <br/> <br/> Diğer adları temizleme - Diğer adlar, kullanıcıların ek e-posta adresleridir. Bazı kuruluşlarda diğer adlar kullanılmaz; diğer adlarınız yoksa burada herhangi bir şey yapmanız gerekmez. Kullanıcının diğer adları varsa, bu e-posta adreslerini yeniden kullanabilmeniz için bunları kaldırmanızı öneririz. Aksi takdirde, silinen posta kutularının saklama süresi geçene kadar bu e-posta adreslerini yeniden kullanamazsınız. Varsayılan olarak, silinen bir posta kutusu 30 gün boyunca kurtarılabilir. Daha fazla bilgi için bkz. [Exchange Online'da kullanıcı posta kutularını silme veya geri yükleme](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |İşletmeniz, Azure AD ile eşitlenen **Active Directory** kullanıyorsa, kullanıcı hesabını Active Directory'den silmeniz gerekir. Bunu Office 365 üzerinden yapamazsınız. Yönergeler için bkz. [Kullanıcı Hesabını Silme](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Kullanmaya başlayın

Kılavuzlu deneyim, bir kullanıcıyı silme adımlarını incelediğinden, şu şekilde kullanmaya başlarsınız.

::: moniker range="o365-worldwide"

1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.

::: moniker-end

2. Silmek istediğiniz kullanıcıyı seçin ve ardından **Kullanıcıyı sil'i** seçin.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Kullanıcı yönetimi yöneticisi: Office 365'ten bir veya daha fazla kullanıcı silme

> [!IMPORTANT]
> Paylaşılan posta [kutusuna dönüştürdüyseniz](../email/convert-user-mailbox-to-shared-mailbox.md) veya hesapta e-posta iletmeyi ayarladıysanız kullanıcının hesabını silmeyin. Bu işlevlerin yine de hesaba ihtiyacı vardır. Paylaşılan posta kutusu için lisans gerekmez. Hesabı paylaşılan bir posta kutusuna dönüştürdüyseniz [lisans için ödeme yapmayı durdurabilirsiniz](#stop-paying-for-the-license). Hesapta e-posta iletmeyi ayarladıysanız lisansı kaldıramazsınız. Bunun yapılması e-posta iletmeyi durdurur ve posta kutusunu devre dışı bırakır.
  
::: moniker range="o365-worldwide"

1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.  

::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.

::: moniker-end

2. Silmek istediğiniz kullanıcıların adlarını seçin, üç noktayı (diğer eylemler) ve ardından  **Kullanıcıyı sil'i** seçin.

   Kullanıcının hesabını silseniz de **lisans için ödemeniz devam ediyor**. Lisans için ödeme yapmayı durdurmak için sonraki yordama bakın.  Veya lisansı başka bir kullanıcıya atayabilirsiniz. Bir kişiye otomatik olarak atanamaz.

### <a name="stop-paying-for-the-license"></a>Lisans için ödemeyi durdurma

Lisans sayısını azaltmak, yalnızca genel yönetici veya faturalama yöneticisi tarafından gerçekleştirilebilecek ayrı bir adımdır.
  
::: moniker range="o365-worldwide"

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ürünleriniz</a> sayfasına gidin.
::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetim merkezinde **Faturalama** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ürünleriniz</a> sayfasına gidin.
::: moniker-end

2. **Ürünler** sekmesinde, lisanslarını kaldırmak istediğiniz aboneliği seçin.

3. Abonelik ayrıntıları sayfasında **Lisansları kaldır'ı** seçin.

4. **Lisansları kaldır** bölmesindeki **Yeni miktar'ın** altında, **Toplam lisanslar** kutusuna bu abonelik için istediğiniz toplam lisans sayısını girin. Örneğin, 100 lisansınız varsa ve bunların beşini kaldırmak istiyorsanız 95 girin.

5. **Kaydet**'i seçin.

Daha sonra işletmenize başka bir kişi ekleme adımlarını uyguladığınızda, tek bir adımla aynı anda lisans satın almanız istenir!

## <a name="delete-many-users-at-the-same-time"></a>Aynı anda birkaç kullanıcı silme

Bkz. [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.

## <a name="fix-issues-with-deleting-a-user"></a>Bir kullanıcıyı silerken oluşan sorunları düzeltme

Kullanıcıların bir kullanıcıyı silerken karşılaştığı en yaygın sorunlar şunlardır:
  
- **"Kullanıcı silinemiyor. Lütfen daha sonra yeniden deneyin." satırlarının bulunduğu bir hata iletisi alıyorsunuz.** Hesabın üzerinde e-posta iletmenin ayarlanıp ayarlanmadığını veya paylaşılan posta kutusuna dönüştürüldüğünü bir kez daha denetleyin. Her iki durum da bu hataya neden olur. E-posta iletme ayarlandıysa veya paylaşılan posta kutusuna dönüştürüldüyse hesabı silmeyin.

- **Kullanıcı silmek için uygun izinleriniz yok**. Yalnızca [Microsoft 365 genel yöneticisi veya kullanıcı yönetimi yöneticisi](about-admin-roles.md) olan kişiler kullanıcıları silebilir. Bu kişiler genelde okulunuzdaki veya işletmenizdeki teknik destek sorumlularıdır.

- **Kullanıcıları sildiniz ancak adları genel adres defterinde görünmeye devam ediyor**. İşletme Active Directory kullanıyorsa, bu durum ortaya çıkar. Kullanıcı hesabını Active Directory'den silmeniz gerekir. Yönergeler için bkz [. Kullanıcı Hesabını Silme.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Microsoft 365'i bilgisayarınızdan silmek istiyor musunuz? [Aboneliğinizi iptal etme'ye](../../commerce/subscriptions/cancel-your-subscription.md) gidin.**

## <a name="related-content"></a>İlgili içerik

[Kullanıcıyı geri yükleme](restore-user.md) (makale)\
[Posta kutusunu kalıcı olarak silme](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (makale)\
[eski çalışanı Office 365 kaldırma](remove-former-employee.md) (makale)\
[Office 365 yeni çalışan ekleme](add-new-employee.md) (makale)\
[Kullanıcı Hesabını Silme](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): İşletmeniz Azure AD ile eşitlenen **Active Directory** kullanıyorsa bu yönergeleri kullanın. Bunu Office 365 üzerinden yapamazsınız. (makale)
