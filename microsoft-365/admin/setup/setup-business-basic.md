---
title: Microsoft 365 İş Temel’i ayarlama
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- VSBFY23
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Microsoft 365 İş Temel aboneliğinizi ayarlamayı öğrenin.
ms.openlocfilehash: 8114e41a4a69c98843f711ee7d8c8ff598405052
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734109"
---
# <a name="set-up-microsoft-365-business-basic"></a>Microsoft 365 İş Temel’i ayarlama

## <a name="watch-set-up-microsoft-365-business-basic"></a>İzleyin: Microsoft 365 İş Temel ayarlama

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Bu videoyu faydalı bulduysanız, [küçük işletmelere ve Microsoft 365’i ilk kez kullananlara yönelik eğitim serisinin tamamına göz atın](../../business-video/index.yml).

## <a name="add-an-existing-domain-to-your-microsoft-365-business-basic-subscription"></a>Microsoft 365 İş Temel aboneliğinize mevcut bir etki alanı ekleme

Microsoft 365 İş Temel satın aldığınızda, sahip olduğunuz bir etki alanını kullanma veya kayıt sırasında bir etki alanı satın alma seçeneğiniz vardır.

- Kaydolduğunda yeni bir etki alanı satın aldıysanız, etki alanınız ayarlanmıştır ve [Kullanıcı ekle ve lisans ata'ya](#add-users-and-assign-licenses) geçebilirsiniz.

 ::: moniker range="o365-worldwide"

1. konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. Şuradan yönetim merkezine gidin: <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end

2. Sihirbazı başlatmak **için Kuruluma git'i** seçin.

3. **Etki alanı ekle** adımında, kullanmak istediğiniz etki alanı adını girin (contoso.com gibi).

    > [!IMPORTANT]
    > Kayıt sırasında bir etki alanı satın aldıysanız, burada **Etki alanı ekle** adımını görmezsiniz. Bunun yerine [Kullanıcı ekle'ye](#add-users-and-assign-licenses) gidin.

4. Etki alanının sahibi olduğunuzu doğrulayan [Office 365 için herhangi bir DNS barındırma sağlayıcısında DNS kayıtları oluşturma](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) sihirbazındaki adımları izleyin. Etki alanı konağınızı biliyorsanız bkz. [Microsoft 365'e etki alanı ekleme](/microsoft-365/admin/setup/add-domain).

    Barındırma sağlayıcınız GoDaddy veya [etki alanı bağlantısı](/office365/admin/get-help-with-domains/domain-connect) etkinleştirilmiş başka bir konaksa işlem kolaydır ve otomatik olarak oturum açmanız ve Microsoft'un sizin adınıza kimlik doğrulaması yapmasına izin vermeniz istenir.

    ![GoDaddy Erişimi Onayla sayfasında Yetki ver'i seçin.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Kullanıcı ekleme ve lisans atama

Sihirbaza kullanıcı ekleyebilirsiniz, ancak [daha sonra yönetim merkezinde de kullanıcı ekleyebilirsiniz](../add-users/add-users.md) .

Sihirbaza eklediğiniz tüm kullanıcılara otomatik olarak bir Microsoft 365 İş Temel lisansı atanır.

1. Microsoft 365 İş Temel aboneliğinizde mevcut kullanıcılar varsa (örneğin, Azure AD Connect kullandıysanız), onlara şimdi lisans atama seçeneğine sahip olursunuz. Bu kullanıcılara da lisans ekleyerek işleme devam edin.

2. Kullanıcıları ekledikten sonra, eklediğiniz yeni kullanıcılarla kimlik bilgilerini paylaşma seçeneğine de sahip olursunuz. Bunları yazdırabilir, e-posta ile gönderebilir veya indirebilirsiniz.

## <a name="connect-your-domain"></a>Etki alanınızı bağlama

> [!NOTE]
> .onmicrosoft etki alanını kullanmayı seçtiyseniz veya kullanıcıları ayarlamak için Connect Azure AD kullandıysanız, bu adımı görmezsiniz.
  
Hizmetleri ayarlamak için DNS ana bilgisayarınızda veya etki alanı kayıt şirketinizde bazı kayıtları güncelleştirmeniz gerekir.
  
1. Kurulum sihirbazı, genellikle kayıt şirketinizi algılar ve kayıt şirketinin web sitesinde NS kayıtlarınızı güncelleştirmek için adım adım yönergelere ulaşabileceğiniz bir bağlantı verir. Ayarlamıyorsa, [herhangi bir etki alanı kayıt şirketiyle Office 365 ayarlamak için ad sunucularını değiştirin](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Dns kayıtlarınız varsa (örneğin, var olan bir web sitesi) ancak DNS ana bilgisayarınız [etki alanı bağlantısı](/office365/admin/get-help-with-domains/domain-connect) için etkinleştirildiyse **, Benim için kayıt ekle'yi** seçin. **çevrimiçi hizmetler seçin** sayfasında tüm varsayılanları kabul edin ve **İleri'yi** seçin ve DNS barındırma sağlayıcınızın sayfasında **Yetki ver'i** seçin.
    - Diğer DNS ana bilgisayarlarıyla (etki alanı bağlantısı için etkinleştirilmemiş) mevcut DNS kayıtlarınız varsa, mevcut hizmetlerin bağlı kalmasını sağlamak için kendi DNS kayıtlarınızı yönetmek istersiniz. Daha fazla bilgi için bkz. [etki alanı temelleri](/office365/admin/get-help-with-domains/dns-basics) .

2. Sihirbazdaki adımları izleyin; e-posta ve diğer hizmetler sizin için ayarlanır.

    Kaydolma işlemi tamamlandığında, yönetim merkezine yönlendirilirsiniz; burada kullanıcı ekleyebilir ve lisans atayabilirsiniz. İlk kurulumu tamamladıktan sonra, aboneliklerinizle birlikte gelen hizmetleri ayarlamaya ve yapılandırmaya devam etmek için yönetim merkezindeki **Kurulum** sayfasını kullanabilirsiniz.

    Kurulum sihirbazı ve yönetim merkezi **Kurulum** sayfası hakkında daha fazla bilgi için bkz. [Kurulum sihirbazı ile Kurulum sayfası arasındaki fark](o365-setup-wizard-and-setup-page.md).

## <a name="watch-set-up-business-email-with-a-new-domain"></a>İzleyin: Yeni bir etki alanıyla iş e-postası ayarlama

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA]

## <a name="steps-set-up-business-email-with-a-new-domain"></a>Adımlar: Yeni bir etki alanıyla iş e-postası ayarlama

1. Microsoft 365 İş Standart kaydolma sayfasındaki **Nasıl oturum açacağınız** **sayfasından Yeni iş e-posta hesabı oluştur (gelişmiş)'** i seçin.

2. Yeni bir etki alanı satın almak ve kullanmak istediğiniz etki alanı adını (contoso.com gibi) girmek için adımları izleyin. Etki alanınızı satın almayı tamamladıktan sonra [kullanıcı ve lisans ekleyebilir ve](../add-users/add-users.md) Office uygulamalarınızı yönetim merkezine yükleyebilirsiniz.

## <a name="finish-setting-up"></a>Ayarlamayı bitir

Outlook, Teams, OneDrive ve web sitenizi ayarlamak için aşağıdaki adımları izleyin.

### <a name="step-set-up-outlook-for-email"></a>Adım: E-posta için Outlook'u ayarlama

1. Windows Başlat menüsünde Outlook'u arayın ve seçin.

    (Mac kullanıyorsanız araç çubuğundan Outlook'u açın veya Finder'ı kullanarak bulun.)

    Outlook'u yeni yüklediyseniz, Hoş Geldiniz sayfasında **İleri'yi** seçin.

2. **Dosya** \> **Bilgileri** \> **Hesap Ekle'yi** seçin.

3. Microsoft e-posta adresinizi girin ve **Bağlan'ı** seçin.

## <a name="watch-set-up-outlook-for-email"></a>İzleyin: E-posta için Outlook'u ayarlama

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Daha fazla bilgi için bkz. [E-posta için Outlook'u ayarlama](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>E-posta içe aktarma

Outlook'u başka bir e-posta hesabıyla kullanıyorsanız, önceki e-postanızı, takviminizi ve kişilerinizi yeni Microsoft hesabınıza aktarabilirsiniz.
  
1. **Eski e-postanızı dışarı aktarma**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.

    **Dosyaya Aktar'ı** seçin ve ardından Outlook Veri Dosyanızı (.pst) ve alt klasörleri dışarı aktarmak için adımları izleyin.

2. **Eski e-postanızı içeri aktarma**

    Outlook'ta **Dosya** \> **Aç &amp; Dışarı Aktarma** \> **İçeri/Dışarı Aktarma'yı** yeniden seçin.

    Bu kez **, Başka bir programdan veya dosyadan içeri aktar'ı** seçin ve eski e-postanızı dışarı aktarırken oluşturduğunuz yedekleme dosyasını içeri aktarmak için adımları izleyin.

## <a name="watch-import-and-redirect-email"></a>İzleyin: E-postayı içeri aktarma ve yeniden yönlendirme

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Daha fazla bilgi için [bkz. Outlook ile e-postayı içeri aktarma](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

Herkesin e-postasını içeri aktarmak için <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezini</a> de kullanabilirsiniz. Daha fazla bilgi için bkz. [Birden çok e-posta hesabını geçirme](/Exchange/mailbox-migration/mailbox-migration).

## <a name="set-up-microsoft-teams-and-onedrive-for-business"></a>Microsoft Teams ve OneDrive İş'i ayarlama

Görev çubuğunuzdaki OneDrive bulut simgesini seçin ve dosyalarınızı yeni OneDrive İş klasörünüze taşımak için adımları izleyin. Microsoft Teams'i ayarlamak için **İleri'yi** seçin.

1. Microsoft Teams'i açın, profil simgenizi seçin ve ardından **İş veya okul hesabı ekle'yi** seçin. Teams'e yeni hesabınızı eklemek için adımları izleyin.

## <a name="use-a-public-website"></a>Genel web sitesi kullanma

Microsoft 365, işletmeniz için genel bir web sitesi içermez. Bir iş ortağı ayarlamak istiyorsanız GoDaddy veya WIX gibi bir Microsoft iş ortağı kullanmayı göz önünde bulundurun.
  
1. Yönetim merkezinden **Kaynaklar'a** gidin ve **Genel web sitesi'ni** seçin.

2. Seçeneklerden birinin altında **Daha fazla bilgi edinin'i** seçin ve bir web sitesi iş ortağına kaydolun ve sitenizi ayarlamak ve tasarlamak için araçlarını kullanın.

## <a name="watch-create-your-business-website"></a>İzleyin: İş web sitenizi oluşturma

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="invite-users-to-join-your-subscription-and-organization"></a>Kullanıcıları aboneliğinize ve kuruluşunuza katılmaya davet etme

Kuruluşunuzu ayarladıktan sonra, diğer kullanıcıları Microsoft 365 iş aboneliğinize katılmaya davet edebilirsiniz. Aboneliğin tüm özelliklerine erişim elde ederler.

[Kullanıcıları aboneliğime davet etme](../simplified-signup/admin-invite-business-standard.md)

Kullanıcılarınıza kuruluşunuza ve aboneliğinize katılmak için aşağıdaki makalelerde yer alan adımları uygulayabileceklerini bildirin.

- [E-posta daveti kabul etme](../simplified-signup/user-invite-business-standard.md)

- [Outlook, Yahoo, Gmail veya başka bir hesap kullanarak e-posta daveti kabul etme (Kullanıcı)](../simplified-signup/user-invite-msa-nodomain-join.md)

## <a name="related-topics"></a>İlgili konular

[Verileri Microsoft 365 İş Standart aboneliğime geçirme](../simplified-signup/migrate-data-business-standard.md)
