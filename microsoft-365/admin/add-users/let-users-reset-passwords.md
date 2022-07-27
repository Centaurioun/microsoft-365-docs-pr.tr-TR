---
title: Kullanıcıların kendi parolalarını sıfırlamasına izin verme
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Kullanıcıların self servis parola sıfırlama aracını kullanarak kendi parolalarını sıfırlamasına izin vermek için Microsoft 365 yönetim merkezi bir ilke ayarlamayı öğrenin.
ms.openlocfilehash: 917f04b7472204be4228d802975902c42ab8fce0
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037237"
---
# <a name="let-users-reset-their-own-passwords"></a>Kullanıcıların kendi parolalarını sıfırlamasına izin verme

YouTube'da [Microsoft 365 küçük işletme yardımına](https://go.microsoft.com/fwlink/?linkid=2197659) göz atın.

Microsoft 365 yöneticisi olarak, kullanıcıların [self servis parola sıfırlama aracını](https://go.microsoft.com/fwlink/p/?LinkId=522677) kullanmasına izin vekleyebilirsiniz, böylece bu kişilerin parolalarını sıfırlamanız gerekmez. İşiniz azalır!

> [!TIP]
> Bu konuda verilen adımlarla ilgili yardıma ihtiyacınız varsa[bir Microsoft küçük işletme uzmanıyla çalışmayı](https://go.microsoft.com/fwlink/?linkid=2186871) göz önünde bulundurun. İşletme Yardımı ile, işletmenizi büyütürken katılımdan gündelik kullanıma kadar her aşamada siz ve çalışanlarınız günün 24 saati küçük işletme uzmanlarına erişebilirsiniz.
 
## <a name="watch-let-users-reset-their-own-passwords"></a>İzleyin: Kullanıcıların kendi parolalarını sıfırlamasına izin verme

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198214) bu videoya ve diğer videolara göz atın.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

1. Microsoft 365 yönetim merkezi sol gezinti bölmesinde **Ayarlar** > **Kuruluş ayarları'nı** ve ardından <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Güvenlik & gizlilik'i**</a> seçin.
1. **Self servis parola sıfırlama'nın** altında **, self servis parola sıfırlamayı açmak için Azure portal git'i** seçin.
1. Sol gezinti bölmesinde **Kullanıcılar'ı** seçin ve ardından **Kullanıcılar - tüm kullanıcılar** sayfasında **Parola sıfırlama'yı** seçin.
1. Self servis parola sıfırlamayı etkinleştirmek için **Tümü'ne** ve ardından **Kaydet'e** tıklayın.
1. Sol gezinti bölmesinde **Kimlik doğrulama yöntemleri'ni** seçin, **sıfırlamak için gereken yöntem sayısı'nı** ve **kullanıcıların kullanabilecekleri istenen Yöntemler'i** ve ardından **Kaydet'i** seçin. 

Bu videoyu faydalı bulduysanız, [küçük işletmelere ve Microsoft 365’i ilk kez kullananlara yönelik eğitim serisinin tamamına göz atın](../../business-video/index.yml).
 
## <a name="before-you-begin"></a>Başlamadan önce
  
- Microsoft 365 iş, eğitim veya kar amacı gütmeyen ücretli planlarla bulut kullanıcıları için **ücretsiz** self servis parola sıfırlaması alırsınız. Microsoft 365 deneme sürümüyle çalışmaz.

- Azure kullanır. Bu adımları izlediğinizde, Azure'da bu özelliği otomatik olarak **ücretsiz** alırsınız. Diğer Azure özelliklerini kullanmazsanız, self servis parola sıfırlama özelliğini açmanın sizin için hiçbir maliyeti yoktur.

- **Şirket içi Active Directory'yi kullanıyorsanız** yukarıdaki iki nokta sizin için geçerli değildir. Onun yerine, bu özelliği ayarlayabilirsiniz ancak **bunun için ücretli bir Azure AD Premium aboneliği gerekir**.

Bu makale, bir işletme, okul veya kar amacı gütmeyen kuruluş için parola süre sonu ilkesi belirleyen kişilere yöneliktir. Bu adımları tamamlamak için Microsoft 365 yönetici hesabınızla oturum açmanız gerekir. [Yönetici hesabı nedir?] (Microsoft 365 yönetim merkezi Genel Bakış](.. /admin-overview/admin-center-overview.md)

Bu adımları gerçekleştirmek için [genel yönetici veya parola yöneticisi](about-admin-roles.md) olmanız gerekir.

## <a name="steps-let-people-reset-their-own-passwords"></a>Adımlar: kişilerin kendi parolalarını sıfırlamasına izin verme

Bu adımlar, işletmenizdeki herkes için self servis parola sıfırlamayı açar.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Yönetim merkezinde</a> **Ayarlar** > **Kuruluş ayarları** sayfasına gidin.

2. **Kuruluş ayarları** sayfasının üst kısmında **Güvenlik & Gizlilik** sekmesini seçin.
  
3. **Self servis Parola Sıfırlama'yı** seçin.

4. **Self servis parola sıfırlama'nın** altında **, self servis parola sıfırlamayı açmak için Azure portal git'i** seçin.

5. **Özellikler** sayfasında **Tümü'ne** tıklayarak işletmenizdeki herkes için etkinleştirin ve ardından **Kaydet'i** seçin.

6. Sol gezinti bölmesinde **Kimlik doğrulama yöntemleri'ni** seçin, **sıfırlamak için gereken yöntem sayısı'nı** ve **kullanıcıların kullanabilecekleri istenen Yöntemler'i** ve ardından **Kaydet'i** seçin. 
  
7. Kullanıcılarınız oturum açtıklarında, gelecekte parolalarını sıfırlamalarına yardımcı olacak ek kişi bilgilerini girmeleri istenir.

## <a name="related-content"></a>İlgili içerik

[Kuruluşunuz için parola süre sonu ilkesini ayarlama](../manage/set-password-expiration-policy.md) (makale)\
[Tek bir kullanıcının parolasını hiçbir zaman sona ermeyecek şekilde ayarlama](set-password-to-never-expire.md) (makale)\
[Microsoft 365 İş eğitim videoları](../../business-video/index.yml) (bağlantı sayfası)
