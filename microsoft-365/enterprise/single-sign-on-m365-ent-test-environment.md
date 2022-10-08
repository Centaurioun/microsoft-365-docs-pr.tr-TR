---
title: Microsoft 365 test ortamınız için Sorunsuz Çoklu Oturum Açma Azure AD
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Özet: Microsoft 365 test ortamınız için Sorunsuz Çoklu Oturum Açma Azure AD yapılandırın ve test edin.'
ms.openlocfilehash: 47fd4209a271875a1ae046a7315eda5ada6b7edf
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190935"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Microsoft 365 test ortamınız için Sorunsuz Çoklu Oturum Açma Azure AD

*Bu Test Laboratuvarı Kılavuzu hem kurumsal hem de Office 365 Kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Azure AD Sorunsuz Tek Sign-On (Sorunsuz SSO), kuruluş ağına bağlı bilgisayarlarında veya cihazlarında bulunan kullanıcılarda otomatik olarak oturum açar. Azure AD Sorunsuz SSO, kullanıcılara ek şirket içi bileşenlere gerek kalmadan bulut tabanlı uygulamalara kolay erişim sağlar.

Bu makalede, Azure AD Sorunsuz SSO için Microsoft 365 test ortamınızı yapılandırma adımları açıklanmaktadır.

Sorunsuz Azure AD SSO'nun ayarlanması iki aşamadan oluşur:
- [1. Aşama: Microsoft 365 test ortamınız için parola karması eşitlemesini yapılandırma](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2. Aşama: Sorunsuz Azure AD SSO için APP1'de Azure AD Bağlanmayı Yapılandırma](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 kurumsal Test Laboratuvarı Kılavuzu yığınındaki tüm makalelere yönelik görsel bir harita için [, Kurumsal Test Laboratuvarı Kılavuz Yığını için Microsoft 365'e](../downloads/Microsoft365EnterpriseTLGStack.pdf) gidin.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1. Aşama: Microsoft 365 test ortamınız için parola karması eşitlemesini yapılandırma

[Microsoft 365 için parola karması eşitlemesi](password-hash-sync-m365-ent-test-environment.md) yönergelerini izleyin. 

Sonuçta elde edilen yapılandırmanız şöyle görünür:
  
![Parola karması eşitleme testi ortamı ile sanal kuruluş.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Bu yapılandırma şunlardan oluşur:
  
- Microsoft 365 E5 deneme sürümü veya ücretli abonelik.
- Azure sanal ağının alt ağındaki DC1, APP1 ve CLIENT1 sanal makinelerinden oluşan, internete bağlı basitleştirilmiş bir kuruluş intraneti.
- Azure AD Connect, TESTLAB Active Directory Domain Services (AD DS) etki alanını Microsoft 365 aboneliğinizin Azure AD kiracısıyla düzenli aralıklarla eşitlemek için APP1 üzerinde çalışır.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>2. Aşama: Sorunsuz Azure AD SSO için APP1'de Azure AD Bağlanmayı Yapılandırma

Bu aşamada, sorunsuz Azure AD SSO için APP1'de Azure AD Bağlan'ı yapılandırın ve çalıştığını doğrulayın.

### <a name="configure-azure-ad-connect-on-app1"></a>APP1'de Azure AD Bağlan'ı yapılandırma

1. [Azure portal](https://portal.azure.com) genel yönetici hesabınızla oturum açın ve ARDıNDAN TESTLAB\User1 hesabıyla APP1'e bağlanın.

2. APP1 masaüstünden Bağlan'ı Azure AD çalıştırın.

3. **Hoş Geldiniz sayfasında** **Yapılandır'ı** seçin.

4. **Ek görevler** sayfasında **Kullanıcı oturumunu değiştir'i ve ardından İleri'yi** seçin.

5. **Azure AD bağlan** sayfasında genel yönetici hesabı kimlik bilgilerinizi girin ve **İleri'yi** seçin.

6. **Kullanıcı oturum açma** sayfasında **Çoklu oturum açmayı etkinleştir'i ve ardından İleri'yi** seçin.

7. **Çoklu oturum açmayı etkinleştir** sayfasında **Kimlik bilgilerini girin'i** seçin.

8. **Windows Güvenliği** iletişim kutusunda **user1 ve user1** hesabının parolasını girin, **Tamam'ı** ve ardından **İleri'yi** seçin.

9. **Yapılandırmaya Hazır** sayfasında **Yapılandır'ı** seçin.

10. **Yapılandırma tamamlandı** sayfasında **Çıkış'ı** seçin.

11. Azure portal sol bölmede **Azure Active Directory** >  **Azure AD Bağlan'ı** seçin. **Sorunsuz çoklu oturum açma** özelliğinin **Etkin** olarak göründüğünü doğrulayın.

Ardından, user1@testlab ile aboneliğinizde oturum açma özelliğini test edin <strong>.</strong>\<*your public domain*> Kullanıcı1 hesabının kullanıcı adı.

1. APP1'de Internet Explorer'dan ayarlar simgesini ve ardından **İnternet Seçenekleri'ni** seçin.
 
2. **İnternet Seçenekleri'nde** **Güvenlik** sekmesini seçin.

3. **Yerel intranet'i** ve ardından **Siteler'i** seçin.

4. **Yerel intranet'te** **Gelişmiş'i** seçin.

5. **Bu web sitesini bölgeye ekle bölümünde** **https <span>://</span>autologon.microsoftazuread-sso.com** girin, **Ekle** > **Kapat** > **Tamam'ı** >  seçin.

6. Bu kez farklı bir hesap belirterek oturumu kapatın ve yeniden oturum açın.

7. Oturum açmanız istendiğinde <strong>user1@testlab belirtin.</strong>\<*your public domain*> adını seçin ve **ardından İleri'yi** seçin. Parola istenmeden Kullanıcı1 olarak başarıyla oturum açmanız gerekir. Bu, sorunsuz Azure AD SSO'nun çalıştığını kanıtlar.

User1'in TESTLAB AD DS etki alanı için etki alanı yöneticisi izinleri olmasına rağmen, Azure AD için genel yönetici olmadığını fark edin. Bu nedenle, **seçenek olarak Yönetici** simgesini görmezsiniz.

Elde edilen yapılandırmanız şunlardır:

![Doğrudan kimlik doğrulama testi ortamına sahip sanal kuruluş.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Bu yapılandırma şunlardan oluşur:

- DNS etki alanı testlab'ine sahip Microsoft 365 E5 deneme sürümü veya ücretli abonelikler.\<*your domain name*> Kayıtlı.
- Azure sanal ağının alt ağındaki DC1, APP1 ve CLIENT1 sanal makinelerinden oluşan, internete bağlı basitleştirilmiş bir kuruluş intraneti.
- Azure AD Connect, Microsoft 365 aboneliğinizin Azure AD kiracısından TESTLAB AD DS etki alanına hesap ve grup listesini eşitlemek için APP1'de çalışır.
- Azure AD Sorunsuz SSO etkinleştirildiğinden, sanal intranetteki bilgisayarlar kullanıcı hesabı parolası belirtmeden Microsoft 365 bulut kaynaklarında oturum açabilir.

## <a name="next-step"></a>Sonraki adım

Test ortamınızdaki ek [kimlik](m365-enterprise-test-lab-guides.md#identity) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

[Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)