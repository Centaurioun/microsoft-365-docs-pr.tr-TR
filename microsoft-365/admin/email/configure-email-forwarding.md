---
title: E-posta iletmeyi yapılandırma
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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Email iletme, Microsoft 365 kullanıcı posta kutusuna gönderilen e-posta iletilerini kuruluşunuzun içindeki veya dışındaki başka bir posta kutusuna iletmenizi sağlar.
ms.openlocfilehash: 74e261e8e99399879e64acccd7c6435b795e2388
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178239"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Microsoft 365'te e-posta iletmeyi yapılandırma

Bir kuruluşun yöneticisi olarak, kullanıcının posta kutusu için e-posta iletmeyi ayarlamak için şirket gereksinimleriniz olabilir. Email iletme, kullanıcının posta kutusuna gönderilen e-posta iletilerini kuruluşunuzun içindeki veya dışındaki başka bir kullanıcının posta kutusuna iletmenizi sağlar.

> [!IMPORTANT]
> Dış alıcılara otomatik iletmeyi denetlemek için giden istenmeyen posta filtresi ilkelerini kullanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft 365'te otomatik dış e-posta iletmeyi denetleme](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

> [!TIP]
> Bu konuda verilen adımlarla ilgili yardıma ihtiyacınız varsa[bir Microsoft küçük işletme uzmanıyla çalışmayı](https://go.microsoft.com/fwlink/?linkid=2186871) göz önünde bulundurun. İşletme Yardımı ile, işletmenizi büyütürken katılımdan gündelik kullanıma kadar her aşamada siz ve çalışanlarınız günün 24 saati küçük işletme uzmanlarına erişebilirsiniz.

## <a name="configure-email-forwarding"></a>E-posta iletmeyi yapılandırma

E-posta iletmeyi ayarlamadan önce aşağıdakileri not edin:

- Otomatik olarak iletilen iletilerin uzak etki alanındaki kişilere gönderilmesine izin verin. Ayrıntılar için bkz. [Uzak etki alanlarını yönetme](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) .

- E-posta iletmeyi ayarladıktan sonra, *yalnızca posta* kutusundan gönderilen **yeni** e-postalar iletilir.

- Email iletme için *kaynak* hesabın bir lisansı olması gerekir. Kullanıcı kuruluşunuzdan ayrıldığından e-posta iletmeyi ayarıyorsanız, başka bir seçenek de [posta kutusunu paylaşılan posta kutusuna dönüştürmektir](convert-user-mailbox-to-shared-mailbox.md). Bu şekilde birkaç kişi erişebilir. Ancak, paylaşılan posta kutusu 50 GB'ı aşamaz.

Bu adımları uygulamak için Microsoft 365'te Exchange yöneticisi veya Genel yönetici olmanız gerekir. Daha fazla bilgi için [Yönetici rolleri hakkında](../add-users/about-admin-roles.md) konusuna bakın.

::: moniker range="o365-worldwide"

1. Yönetim merkezinde **Kullanıcılar** \> **[Etkin kullanıcılar](https://go.microsoft.com/fwlink/p/?linkid=834822)** sayfasına gidin.

2. E-postasını iletmek istediğiniz kullanıcının adını seçin ve özellikler sayfasını açın.

3. **Posta** sekmesinde **E-posta iletmeyi yönet'i** seçin.

4. E-posta iletme sayfasında **, Bu posta kutusuna gönderilen tüm e-postaları ilet'i** seçin, iletme adresini girin ve iletilen e-postaların bir kopyasını saklamak isteyip istemediğinizi seçin. Bu seçeneği görmüyorsanız kullanıcı hesabına bir lisans atandığından emin olun. **Değişiklikleri kaydet'i** seçin.

    **Birden çok e-posta adresine iletmek için**, kullanıcıdan Outlook'ta adreslere iletecek bir kural ayarlamasını isteyebilirsiniz. 
    
    1.  **Outlook** > **Giriş** >**Kuralları'nı** açın > **Kuralları Yönet & Uyarıları** Seçin  
    1. **Yeni Kural'ı** > seçin, Listenin en altında bulunan **iletide kuralı uygula'yı seçin** ve **ardından İleri'ye** tıklayın.
    1. Sorulduğunda **Evet'e** tıklayın. Bu kural, aldığınız her iletiye uygulanır. 
    1. Sonraki listede eylemleri seçerek **kişilere veya ortak gruba yönlendirin** ve **daha fazla kural işlemeyi durdurun**
    1. Pencerenin alt kısmındaki altı çizili **kişiler veya ortak grup** tümceciğine tıklayın.
    1. **E-postayı iletecek e-posta adresini** Son alanına yazın ve **Tamam'a** tıklayın.
    1. **Son'u** seçin
    

     Ya da yönetim merkezinde [bir dağıtım grubu oluşturun](../setup/create-distribution-lists.md), [adresleri bu gruba ekleyin](add-user-or-contact-to-distribution-list.md) ve sonra bu makaledeki yönergeleri kullanarak iletmeyi DL'ye işaret etmek üzere ayarlayın.

5. İlettiğiniz e-postanın hesabını silmeyin veya lisansını kaldırmayın!  Bunu yaparsanız, e-posta iletme durdurulacaktır.

::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetim merkezinde **Kullanıcılar** \> **[Etkin kullanıcılar](https://go.microsoft.com/fwlink/p/?linkid=850628)** sayfasına gidin.

2. Özellikler sayfasını açmak için e-postasını iletmek istediğiniz kullanıcının adını seçin.

3. **Posta ayarları'nı** genişletin ve **Email iletme** bölümünde **Düzenle'yi** seçin.

4. E-posta iletme sayfasında iki durumlu düğmeyi **Açık** olarak ayarlayın, iletme adresini girin ve iletilen e-postaların bir kopyasını saklamak isteyip istemediğinizi seçin. Bu seçeneği görmüyorsanız kullanıcı hesabına bir lisans atandığından emin olun. **Kaydet**'i seçin.

   **Birden çok e-posta adresine iletmek için**, kullanıcıdan Outlook'ta adreslere iletecek bir kural ayarlamasını isteyebilirsiniz. Daha fazla bilgi edinmek için bkz. [İletileri otomatik olarak iletmek için kuralları kullanma](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Ya da yönetim merkezinde [bir dağıtım grubu oluşturun](../setup/create-distribution-lists.md), [adresleri bu gruba ekleyin](add-user-or-contact-to-distribution-list.md) ve sonra bu makaledeki yönergeleri kullanarak iletmeyi DL'ye işaret etmek üzere ayarlayın.

5. İlettiğiniz e-postanın hesabını silmeyin veya lisansını kaldırmayın! Bunu yaparsanız, e-posta iletme durdurulacaktır.

::: moniker-end

## <a name="related-content"></a>İlgili içerik 

[Paylaşılan posta kutusu oluşturma](../email/create-a-shared-mailbox.md) (makale)\
[Farklı bir adresten e-posta gönderme](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (makale)\
[Kullanıcı adını ve e-posta adresini değiştirme](../add-users/change-a-user-name-and-email-address.md) (makale)\
[Microsoft 365'te otomatik dış e-posta iletmeyi denetleme](/microsoft-365/security/office-365-security/external-email-forwarding) (makale)


