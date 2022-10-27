---
title: Kullanıcıyı geri yükleme
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Kullanıcı hesabını sildikten sonraki 30 gün içinde hesabı ve tüm verileri geri yükleyebilirsiniz ve kullanıcı aynı hesapla oturum açabilir.
ms.openlocfilehash: 1515e6eb65c33ebeb68b0c47662be457d1dc9006
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721570"
---
# <a name="restore-a-user-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi bir kullanıcıyı geri yükleme
   
When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).
  
Birkaç ipucu:
  
- Hesaba atamak için lisansların kullanılabilir olduğundan emin olun.
    
- İşletmeniz Active Directory kullanıyorsa, kullanıcı hesabını geri yükleme yönergeleri için bkz. [Office 365'da silinen kullanıcı hesaplarının sorunlarını giderme](/office365/troubleshoot/active-directory/restore-deleted-user-accounts). 
    
## <a name="restore-one-or-more-user-accounts"></a>Bir veya daha fazla kullanıcı hesabını geri yükleme

Bu adımları gerçekleştirmek için Microsoft 365 genel yöneticisi veya kullanıcı yönetimi yöneticisi olmanız gerekir. 

1. Yönetim merkezinde **Kullanıcılar** <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Silinmiş kullanıcılar</a> \> sayfasına gidin.

2. **Silinmiş kullanıcılar** sayfasında, geri yüklemek istediğiniz kullanıcıların adlarını seçin ve ardından **Geri Yükle'yi** seçin.
    
3. Parolalarını ayarlamak için istemleri izleyin ve ardından **Geri Yükle'yi** seçin.
    
4. Kullanıcı başarıyla geri yüklendiyse **E-posta gönder ve kapat'ı** seçin. Ad çakışmasıyla veya ara sunucu adresi çakışmasıyla karşılaşırsanız, hesabınızı geri yüklemek için aşağıdaki yönergelere bakın.
    
Bir kullanıcıyı geri yükledikten sonra, parolasının değiştiğini bildirdiğinizden ve bu kullanıcıyı takip ettiğinizden emin olun.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Kullanıcı adı çakışması olan bir kullanıcıyı geri yükleme

Bir kullanıcı hesabını silip aynı kullanıcı adıyla yeni bir kullanıcı hesabı oluşturup (aynı kullanıcı için veya benzer adlı başka bir kullanıcı için) daha sonra silinmiş hesabı geri yüklemeye çalıştığınızda, kullanıcı adı çakışması olur.
  
To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.

1. Yönetim merkezinde **Kullanıcılar** <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Silinmiş kullanıcılar</a> \> sayfasına gidin.
  
2. **Silinmiş kullanıcılar** sayfasında, geri yüklemek istediğiniz kullanıcıların adlarını seçin ve ardından **Geri Yükle'yi** seçin.
    
    > [!NOTE]
    > If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time. 
  
3. Parolayı ayarlamak için istemleri izleyin ve **Geri Yükle'yi** seçin.
    
4. Hesabın geri yüklenmesiyle ilgili bir sorun olduğunu belirten bir ileti görüntülenir. Aşağıdakilerden birini yapın:
    
     - Geri yüklemeyi iptal edip geçerli etkin kullanıcıyı yeniden adlandırın. Daha sonra geri yüklemeyi yeniden deneyin.
    
     - VEYA, kullanıcı için yeni bir birincil e-posta adresi yazın ve **Geri Yükle'yi** seçin.
    
5. Sonuçları gözden geçirin ve **Kapat**'ı seçin.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Proxy adresi çakışması olan bir kullanıcıyı geri yükleme

A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.
  
Bunu yapmak için Microsoft 365'te [yönetici izinlerine](about-admin-roles.md) sahip olmanız gerekir. 

1. Yönetim merkezinde **Kullanıcılar** <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Silinmiş kullanıcılar</a> \> sayfasına gidin.

2. **Silinmiş kullanıcılar** sayfasında, geri yüklemek istediğiniz kullanıcıyı seçin ve **Geri yükle**'yi seçin. 
    
3. **Geri Yükle** sayfasında, parolayı ayarlamak için yönergeleri izleyin ve **Geri Yükle'yi** seçin. Çakışan proxy adresleri geri yüklediğiniz kullanıcıdan otomatik olarak kaldırılır.
    
4. Sonuçları gözden geçirin ve **Kapat**'ı seçin.

## <a name="related-content"></a>İlgili içerik

[Kullanıcı silme](delete-a-user.md) (makale)\
[Yönetici rolleri atama](assign-admin-roles.md) (video)\
[Kullanıcılara lisans atama](../manage/assign-licenses-to-users.md) (makale)
