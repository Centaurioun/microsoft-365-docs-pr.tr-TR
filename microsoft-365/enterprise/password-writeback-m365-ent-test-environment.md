---
title: Microsoft 365 test ortamınız için parola geri yazma
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/22/2019
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
description: 'Özet: Microsoft 365 test ortamınız için parola geri yazmayı yapılandırın.'
ms.openlocfilehash: e089d77ba85f0735b5d6532f6a7f0a50804b883e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185303"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 test ortamınız için parola geri yazma

*Bu Test Laboratuvarı Kılavuzu yalnızca kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Kullanıcılar parola geri yazma özelliğini kullanarak parolalarını Azure Active Directory (Azure AD) aracılığıyla güncelleştirebilir ve bu da yerel Active Directory Domain Services (AD DS) için çoğaltılır. Parola geri yazma ile, kullanıcıların özgün kullanıcı hesaplarının depolandığı şirket içi AD DS aracılığıyla parolalarını güncelleştirmeleri gerekmez. Bu, şirket içi ağlarına uzaktan erişim bağlantısı olmayan dolaşıma veya uzak kullanıcılara yardımcı olur.

Bu makalede, Microsoft 365 test ortamınızı parola geri yazma için yapılandırma işlemi açıklanır.

Test ortamınızı parola geri yazma için yapılandırmak iki aşamayı içerir:
- [1. Aşama: Microsoft 365 test ortamınız için parola karması eşitlemesini yapılandırma](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [2. Aşama: TESTLAB AD DS etki alanı için parola geri yazmayı etkinleştirme](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 kurumsal Test Laboratuvarı Kılavuzu yığınındaki tüm makalelere yönelik görsel bir harita için [, Kurumsal Test Laboratuvarı Kılavuz Yığını için Microsoft 365'e](../downloads/Microsoft365EnterpriseTLGStack.pdf) gidin.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>1. Aşama: Microsoft 365 test ortamınız için parola karması eşitlemesini yapılandırma

İlk olarak [, parola karması eşitlemesindeki](password-hash-sync-m365-ent-test-environment.md) yönergeleri izleyin. Sonuçta elde edilen yapılandırmanız şöyle görünür:
  
![Parola karması eşitleme testi ortamı ile sanal kuruluş.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Bu yapılandırma şunlardan oluşur:
  
- Microsoft 365 E5 deneme sürümü veya ücretli abonelik.
- Azure sanal ağının alt ağındaki DC1, APP1 ve CLIENT1 sanal makinelerinden oluşan, internete bağlı basitleştirilmiş bir kuruluş intraneti.
- Azure AD Connect, TESTLAB AD DS etki alanını Microsoft 365 aboneliğinizin Azure AD kiracısına eşitlemek için APP1 üzerinde çalışır.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>2. Aşama: TESTLAB AD DS etki alanı için parola geri yazmayı etkinleştirme

İlk olarak, Kullanıcı 1 hesabını genel yönetici rolüyle yapılandırın.

1. [Microsoft 365 yönetim merkezi](https://portal.microsoft.com) genel yönetici hesabınızla oturum açın.

2. **Etkin kullanıcılar'ı** seçin.
 
3. **Etkin kullanıcılar** sayfasında **user1** hesabını seçin

4. **kullanıcı1** bölmesinde **Roller'in** yanındaki **Düzenle'yi** seçin.

5. **Kullanıcı1 için kullanıcı rollerini düzenle** bölmesinde **Genel yönetici,Kaydet'i** ve ardından **Kapat'ı** seçin.

Ardından, TestLAB AD DS etki alanındaki diğer kullanıcılar adına parolaları değiştirmesine izin veren güvenlik ayarlarıyla Kullanıcı 1 hesabını yapılandırın.

1. [Azure portal](https://portal.azure.com) genel yönetici hesabınızla oturum açın ve ARDıNDAN TESTLAB\User1 hesabıyla APP1'e bağlanın.

2. APP1'in masaüstünden **Başlat'ı** seçin, **etkin** yazın ve **Active Directory Kullanıcıları ve Bilgisayarları'ı** seçin.

3. Menü çubuğunda **Görünüm'ü** seçin. **Gelişmiş özellikler** etkinleştirilmediyse etkinleştirmek için bu özelliği seçin.

4. Ağaç bölmesinde etki alanınızı seçip basılı tutun (veya sağ tıklayın), **Özellikler'i** seçin ve ardından **Güvenlik** sekmesini seçin.

5. **Gelişmiş'i** seçin.

6. **İzinler** sekmesinde **Ekle'yi** seçin.

7. **Sorumlu seçin'i** seçin, **Kullanıcı1** yazın ve **ardından Tamam'ı** seçin.

8. **Uygulanacağı yer** bölümünde **Alt Kullanıcı nesneleri'ne** tıklayın.

9. **İzinler'in** altında aşağıdakileri seçin:

    - **Parolayı değiştirme**
    - **Parolayı sıfırlayın**

10. **Özellikler'in** altında aşağıdakileri seçin:
    - **LockoutTime yazma**
    - **pwdLastSet yazma**

11. Değişiklikleri kaydetmek için **Üç kez Tamam'ı** seçin.

12. **Active Directory Kullanıcıları ve Bilgisayarları** kapatın.

Ardından, parola geri yazma için APP1'de Azure AD Bağlan'ı yapılandırın.

1. Gerekirse, TESTLAB\User1 hesabıyla APP1'e bağlanın.

2. APP1'in masaüstünden **Bağlan'Azure AD** çift tıklayın.

3. **Hoş Geldiniz sayfasında** **Yapılandır'ı** seçin.

4. **Ek görevler** sayfasında **Eşitleme seçeneklerini özelleştir'i** ve ardından **İleri'yi** seçin.

5. **Azure AD bağlan** sayfasında genel yönetici hesabı kimlik bilgilerinizi girin ve **İleri'yi** seçin.

6. **Dizinleri bağla** ve **Etki alanı/OU filtreleme** sayfalarında **İleri'yi** seçin.

7. **İsteğe bağlı özellikler** sayfasında **Parola geri yazma'yı** ve ardından **İleri'yi** seçin.

8. **Yapılandırmaya hazır** sayfasında **Yapılandır'ı** seçin ve işlemin tamamlanmasını bekleyin.

9. Yapılandırmanın bitişini gördüğünüzde **Çıkış'ı** seçin.

Artık sanal intranetinizin sanal ağına bağlı olmayan bilgisayarlardaki kullanıcılar için parola geri yazmayı test etmeye hazırsınız.

Sonuçta elde edilen yapılandırmanız şöyle görünür:

![Doğrudan kimlik doğrulama testi ortamına sahip sanal kuruluş.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Bu yapılandırma şunlardan oluşur:

- DNS etki alanı TESTLAB ile Microsoft 365 E5 deneme veya ücretli abonelikler.\<*your domain name*> Kayıtlı.
- Azure sanal ağının alt ağındaki DC1, APP1 ve CLIENT1 sanal makinelerinden oluşan, internete bağlı basitleştirilmiş bir kuruluş intraneti.
- Azure AD Connect, Microsoft 365 aboneliğinizin Azure AD kiracısından TESTLAB AD DS etki alanına hesap ve grup listesini eşitlemek için APP1'de çalışır.
- Parola geri yazma etkinleştirildiğinden, kullanıcılar basitleştirilmiş intranete bağlanmak zorunda kalmadan Azure AD aracılığıyla parolalarını değiştirebilir.

## <a name="next-step"></a>Sonraki adım

Test ortamınızdaki ek [kimlik](m365-enterprise-test-lab-guides.md#identity) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

[Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)