---
title: Ön cephe çalışanları için mobil cihazları yönetme
author: lanachin
ms.author: v-lanachin
ms.reviewer: mabolan
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
ms.localizationpriority: high
search.appverid: MET150
description: Kuruluşunuzdaki ön cephe çalışanları için mobil cihazları yönetmeye genel bir bakış edinin.
ms.collection:
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: bac87e202ebf656f8da6986738e42f847b8e098a
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68563262"
---
# <a name="manage-mobile-devices-for-frontline-workers"></a>Ön cephe çalışanları için mobil cihazları yönetme

## <a name="overview"></a>Genel bakış

Her sektörde ön cephe çalışanları, iş gücünün büyük bir segmentini oluşturur. Ön çalışan rolleri arasında perakende iş ortakları, fabrika çalışanları, saha ve servis teknisyenleri, sağlık personeli ve daha birçok rol yer alır.

İş gücü büyük ölçüde mobil ve genellikle vardiya tabanlı olduğundan, ön cephe çalışanlarının kullandığı cihazları yönetmek temel öneme sahip bir konudur. Dikkate alınması gereken bazı sorular:

- Çalışanlar şirkete ait cihazları mı yoksa kendi kişisel cihazlarını mı kullanıyor?
- Şirkete ait cihazlar çalışanlar arasında paylaşılıyor mu yoksa bir kişiye mi atanıyor?
- Çalışanlar cihazları evlerine mi alıyor yoksa iş yerinde mi bırakıyor?

İster paylaşılan cihazlar ister çalışanların kendi cihazları olsun, iş gücünüz için cihazları yönetmek için güvenli ve uyumlu bir temel ayarlamak önemlidir. Bu makale, şirket verilerini korurken iş gücünüzü güçlendirmeye yardımcı olmak için yaygın ön çalışan cihaz senaryolarına ve yönetim özelliklerine genel bir bakış sağlar.

## <a name="my-staff"></a>Personelim

Azure Active Directory'deki (Azure AD) [Personelim](/azure/active-directory/roles/my-staff-configure) özelliğiyle, genel kullanıcı yönetimi görevlerini Personelim portalı aracılığıyla ön cephe yöneticilerine devredebilirsiniz. Ön cephe yöneticileri, istekleri yardım masasına, operasyonlara veya BT'ye yönlendirmek zorunda kalmadan doğrudan mağaza veya fabrika katından parola sıfırlama gerçekleştirebilir veya ön hat çalışanları için telefon numaralarını yönetebilir.

Personelim ayrıca ön cephe yöneticilerinin ekip üyelerinin telefon numaralarını SMS oturum açma için kaydetmesine de olanak tanır. Kuruluşunuzda [SMS tabanlı kimlik doğrulaması](/azure/active-directory/authentication/howto-authentication-sms-signin) etkinleştirildiyse, ön hat çalışanları yalnızca telefon numaralarını ve SMS ile gönderilen tek seferlik geçiş kodunu kullanarak Teams'de ve diğer uygulamalarda oturum açabilir. Bu, ön çalışanlar için oturum açmayı basit, güvenli ve hızlı hale getirir.

## <a name="shared-devices"></a>Paylaşılan cihazlar

Birçok ön cephe çalışanı, iş yapmak için paylaşılan mobil cihazları kullanır. Paylaşılan cihazlar, görevler, vardiyalar veya konumlar arasında çalışanlar arasında paylaşılan şirkete ait cihazlardır.

Aşağıda tipik bir senaryo örneği verilmiştır. Bir kuruluşun, tüm çalışanlar arasında paylaşılacak şarj beşiklerinde bir cihaz havuzu vardır. Vardiyanın başlangıcında bir çalışan havuzdan bir cihaz alır ve Teams'de ve rolü için gerekli olan diğer iş uygulamalarında oturum açar. Vardiyalarının sonunda oturumu kapatıp cihazı havuza geri döndürürler. Aynı vardiyada bile çalışan, bir görevi tamamladığında veya öğle yemeği için çıkış yaparken bir cihazı geri döndürebilir ve sonra geri döndüğünde farklı bir cihaz alabilir.

Paylaşılan cihazlar benzersiz güvenlik güçlükleri sunar. Örneğin, çalışanlar aynı cihazdaki diğer kişilerin kullanımına sunulmaması gereken şirket veya müşteri verilerine erişebilir.

Bu bölüm, ön cephe çalışanları için paylaşılan cihazları yönetmeye yönelik özelliklere genel bir bakış sağlar.

### <a name="shared-device-mode"></a>Paylaşılan cihaz modu

[Paylaşılan cihaz modu](/azure/active-directory/develop/msal-shared-devices), cihazları çalışanlar tarafından paylaşılacak şekilde yapılandırmanızı sağlayan bir Azure AD özelliğidir. Bu özellik, Microsoft Teams ve paylaşılan cihaz modunu destekleyen diğer tüm uygulamalar için çoklu oturum açmayı (SSO) ve cihaz genelinde oturumu kapatmayı etkinleştirir. Microsoft Kimlik Doğrulama Kitaplığı'nı (MSAL) kullanarak bu özelliği iş kolu (LOB) uygulamalarınızla tümleştirebilirsiniz.

Örnek olarak Teams'i kullanarak paylaşılan cihaz modunun nasıl çalıştığı aşağıda açıklanmaktadır. Bir çalışan vardiyasının başlangıcında Teams'de oturum açtığında, cihazda paylaşılan cihaz modunu destekleyen diğer tüm uygulamalarda otomatik olarak oturum açar. Vardiyalarının sonunda Teams oturumunu kapattığında, paylaşılan cihaz modunu destekleyen diğer tüm uygulamalardan genel olarak oturumu kapatılmış olur. Oturumu kapatıldıktan sonra, çalışanın Teams'deki verilerine ve şirket verilerine (içinde barındırılan uygulamalar dahil) ve paylaşılan cihaz modunu destekleyen diğer tüm uygulamalara artık erişilemiyor. Cihaz bir sonraki çalışan için hazır ve güvenli bir şekilde teslim edilebilir.

Microsoft [Authenticator uygulamasını](https://support.microsoft.com/account-billing/how-to-use-the-microsoft-authenticator-app-9783c865-0308-42fb-a519-8cf666fe0acc) yükleyip paylaşılan modu açarak bir cihazı paylaşılacak şekilde hazırlamak için Microsoft Endpoint Manager'da Microsoft Intune gibi bir mobil cihaz yönetimi (MDM) çözümü kullanırsınız. Teams ve paylaşılan cihaz modunu destekleyen diğer tüm uygulamalar, cihazdaki kullanıcıları yönetmek için paylaşılan mod ayarını kullanır. Kullandığınız MDM çözümü, oturumu kapattığınızda bir cihaz temizleme işlemi de gerçekleştirmelidir.

Paylaşılan cihaz modu şu anda Android cihazlarda desteklenmektedir. Başlamanıza yardımcı olacak bazı kaynaklar aşağıdadır.

#### <a name="enroll-android-devices-into-shared-device-mode"></a>Android cihazları paylaşılan cihaz moduna kaydetme

Intune kullanarak Android cihazları yönetmek ve paylaşılan cihaz moduna kaydetmek için cihazların Android işletim sistemi sürüm 8.0 veya üzerini çalıştırıyor olması ve Google Mobile Services (GMS) bağlantısına sahip olması gerekir. Daha fazla bilgi için şu makalelere bakın:

- [Android Kurumsal ayrılmış cihazlar için Intune kaydı ayarlama](/mem/intune/enrollment/android-kiosk-enroll)
- [Android Kurumsal ayrılmış cihazlarını Azure AD paylaşılan cihaz moduna kaydetme](https://techcommunity.microsoft.com/t5/intune-customer-success/enroll-android-enterprise-dedicated-devices-into-azure-ad-shared/ba-p/1820093)

Microsoft Managed Home Screen uygulamasını dağıtarak kullanıcılara Intune kayıtlı Android ayrılmış cihazlarında deneyimi uyarlamayı da seçebilirsiniz. Managed Home Screen, onaylanan diğer uygulamaların üzerinde çalışması için başlatıcı görevi görür ve cihazları özelleştirmenize ve çalışanların erişebileceklerini kısıtlamanıza olanak tanır. Örneğin, uygulamaların giriş ekranında nasıl görüneceğini tanımlayabilir, şirket logonuzu ekleyebilir, özel duvar kağıdını ayarlayabilir ve çalışanların oturum PIN'i ayarlamasına izin vekleyebilirsiniz. Hatta oturum kapatmayı, belirtilen bir etkinlik dışı süre sonunda otomatik olarak gerçekleşecek şekilde yapılandırabilirsiniz.  Daha fazla bilgi için şu makalelere bakın:

- [Android Kurumsal için Microsoft Managed Home Screen uygulamasını yapılandırma](/mem/intune/apps/app-configuration-managed-home-screen-app)
- [Çok uygulamalı bilgi noktası modunda ayrılmış cihazlarda Microsoft Managed Home Screen ayarlama](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-managed-home-screen-on-dedicated-devices/ba-p/1388060)

#### <a name="for-developers-creating-apps-for-shared-device-mode"></a>Paylaşılan cihaz modu için uygulama oluşturan geliştiriciler için

Geliştiriciyseniz, uygulamanızı paylaşılan cihaz moduyla tümleştirme hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Android cihazlar için paylaşılan cihaz modu](/azure/active-directory/develop/msal-android-shared-devices)
- [iOS cihazları için paylaşılan cihaz modu](/azure/active-directory/develop/msal-ios-shared-devices)

## <a name="personal-devices-byod"></a>Kişisel cihazlar (KCG)

Bazı kuruluşlar, ön cephe çalışanlarının Teams'e ve diğer iş uygulamalarına erişmek için kendi mobil cihazlarını kullandığı kendi cihazını getir (KCG) modelini kullanır. Kişisel cihazlarda erişimi ve uyumluluğu yönetmenin bazı yollarına genel bir bakış aşağıdadır.

### <a name="enroll-android-and-ios-personal-devices"></a>Android ve iOS kişisel cihazlarını kaydetme

Şirkete ait cihazlarınıza ek olarak, kullanıcıların kişisel cihazlarını Intune yönetime [kaydedebilirsiniz](/mem/intune/enrollment/device-enrollment). KCG kaydı için Microsoft Endpoint Manager yönetim merkezine cihaz kullanıcıları ekler, kayıt deneyimlerini yapılandırıp Intune ilkeleri ayarlarsınız. Kullanıcılar, kendi cihazlarında yüklü olan Intune Şirket Portalı uygulamasında kendilerinin kaydını tamamlar.

Bazı durumlarda, kullanıcılar kişisel cihazlarını yönetime kaydetmekte isteksiz olabilir. Cihaz kaydı bir seçenek değilse, mobil uygulama yönetimi (MAM) yaklaşımını seçebilir ve şirket verileri içeren uygulamaları yönetmek için [uygulama koruma ilkelerini](/mem/intune/apps/app-protection-policies) kullanabilirsiniz. Örneğin, şirket verilerinin cihazdaki kişisel uygulamalara kopyalanmasını önlemek için Teams ve Office mobil uygulamalarına uygulama koruma ilkeleri uygulayabilirsiniz.

Daha fazla bilgi edinmek için Intune [planlama kılavuzundaki "Kişisel cihazlar ve Kuruluşa ait cihazlar"](/mem/intune/fundamentals/intune-planning-guide#personal-devices-vs-organization-owned-devices) bölümüne ve [Dağıtım kılavuzu: Cihazları Microsoft Intune kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment) bölümüne bakın.

## <a name="related-articles"></a>İlgili makaleler

- [Ön çalışan yönetimi](/azure/active-directory/fundamentals/frontline-worker-management)
