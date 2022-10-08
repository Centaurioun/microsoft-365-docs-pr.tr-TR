---
title: Microsoft OneDrive LTI'yi Schoology LMS ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Schoology LMS için yeni Microsoft OneDrive Öğrenme Araçları Birlikte Çalışabilirlik Uygulaması ile ödevler oluşturun ve notlayın, kurs içeriğini derleyin ve dosyalar üzerinde gerçek zamanlı olarak işbirliği yapın.
ms.openlocfilehash: 20aa9c719f029ebec44f8d70e7734c28b91f030d
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68473071"
---
# <a name="integrate-microsoft-onedrive-lti-with-the-schoology-lms"></a>Microsoft OneDrive LTI'yi Schoology LMS ile tümleştirme

Bu kılavuz, Schoology LMS için OneDrive LTI uygulamasını kaydetmek için BT yöneticilerinin adımlarını sağlar.

Microsoft LTI'ye genel bakış için bkz. [Microsoft ürünlerini Öğrenme Yönetim Sisteminizle (LMS) tümleştirme](index.md).

Bu tümleştirmeyi gerçekleştiren kişi Schoology yöneticisi ve Microsoft 365 kiracısının yöneticisi olmalıdır.

## <a name="recommended-browser-settings"></a>Önerilen tarayıcı ayarları

- Microsoft OneDrive için tanımlama bilgilerine izin verilmelidir.
- Açılır pencereler Microsoft OneDrive için engellenmemelidir.

> [!NOTE]
> Chrome tarayıcı gizli modunda tanımlama bilgilerine varsayılan olarak izin verilmez ve buna izin verilmelidir.
>
> Microsoft OneDrive LTI, Microsoft Edge tarayıcısında özel modda çalışır. Tanımlama bilgilerini engellemediğinizden emin olun (varsayılan olarak izin verilir).

## <a name="register-a-new-microsoft-onedrive-lti-app-for-your-microsoft-365-tenant"></a>Microsoft 365 kiracınız için yeni bir Microsoft OneDrive LTI uygulaması kaydetme

1. Office 365 Genel Yönetici kimlik bilgilerini kullanarak [Microsoft OneDrive LTI Kayıt Portalı'na](https://onedrivelti.microsoft.com/admin) oturum açın.
1. **Yönetici Onay** düğmesini seçin ve izinleri kabul edin.
    1. Bu adım başarıyla tamamlanmazsa, aşağıdaki adım size bir hata verir ve hatayı aldıktan sonra bu adımı bir saat boyunca atamayabilirsiniz. Onay başarısız olursa Genel Yönetici olarak oturum açtığınızdan emin olun ve bu adımı yineleyin.
1. **Yeni LTI Kiracısı oluştur** düğmesini seçin.
1. **LTI Tüketici Platformu** listesinde **Schoology'yi** seçin.
1. **Schoology Temel URL'si** alanına Schoology temel URL'nizi (gibi) `https://testschool.schoology.com`girin.
1. **İleri** düğmesini seçin. **LTI 1.3 Uygulamasını Kaydet** sayfası yüklenir.

## <a name="deploy-the-onedrive-lti-app-in-schoology"></a>Schoology'de OneDrive LTI uygulamasını dağıtma

1. Uygulamaları yükleme ve yapılandırma erişimiyle Schoology örneğinizde yönetici olarak oturum açın.
1. Schoology'de **Microsoft OneDrive'ın** bu doğrudan bağlantısını açarak [**App Center'daki**](https://app.schoology.com/apps) [Microsoft OneDrive uygulamasına erişin](https://app.schoology.com/apps/profile/5910037138).
1. Yükleme işlemini başlatmak için **LTI 1.3 Uygulamasını Yükle** düğmesini seçin.
1. **Kabul ediyorum** düğmesini seçin.
1. Uygulamayla gerekli bilgileri paylaşmanız ve **Derin Bağlama**, **Adlar ve Roller**, **Atamalar ve Not Verme** gibi *LTI Avantajı hizmetlerine* erişimi onaylamanız istenir. **Devam** düğmesini seçin.
1. Bunun tüm kuruluşunuz için mi yoksa yalnızca sizin için mi yüklenmesi gerektiği sorulur. **Kuruluşa Ekle'yi** seçtiğinizde yapılandırmayı tamamlamak için **Kuruluş Uygulamaları** sayfasına yönlendirilirsiniz.
1. [**Kuruluş Uygulamaları listesinden**](https://app.schoology.com/apps/school_apps) **Microsoft OneDrive** uygulamasını bulun ve **Yapılandır** düğmesini seçin.
    1. Uygulama dağıtımınıza atanan **Dağıtım Kimliğini** kopyalayın.
        1. Bu kimlik **, Microsoft LMS Ağ Geçidi'nin** yapılandırma işleminde kullanılır.
1. [**Kuruluş Uygulamaları listesinden**](https://app.schoology.com/apps/school_apps) **Microsoft OneDrive** uygulamasını bulun ve **Yükle/Kaldır** düğmesini seçin.
    1. Uygulamayı tüm kurslar için yüklemek için **Tüm Kurslar** onay kutusunu seçin.
        1. Uygulamanın kursun tüm üyeleri tarafından kullanılabildiğinden emin olmak için **Yalnızca Kurs Yöneticileri** seçeneğini işaretlemeyin.

> [!NOTE]
> Uygulamayı tüm kurslar için yüklememeyi seçerseniz *, Kurs Yöneticilerinin* uygulamayı kendileri için yüklemeleri gerekir:
>
> 1. [Kuruluş Uygulamaları listesine](https://app.schoology.com/apps/school_apps) gidin, **Yükle/Kaldır** düğmesini seçin ve uygulamanın yükleneceği kursları seçin.
> 1. Alternatif olarak, kursun sol tarafındaki gezinti menüsünün alt kısmındaki **Uygulamalarınızı Yükleyin** bağlantısını ve ardından yüklenecek **Microsoft OneDrive** uygulamasını seçebilirler.
