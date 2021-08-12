---
title: Android veya iOS cihazlarda uygulama koruma ayarlarını doğrulama
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Android veya iOS cihazlarınıza Microsoft 365 İş Ekstra koruma ayarlarını doğrulamayı öğrenin.
ms.openlocfilehash: 1e11f8ed854d6b9579f901b772110775073c16ad2891d89dbcee0d3ab96e561f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53815391"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Android veya iOS cihazlarda uygulama koruma ayarlarını doğrulama

Android veya iOS cihazlarında uygulama koruma ayarlarını doğrulamak için aşağıdaki bölümlerde verilen yönergeleri izleyin.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Uygulama koruma ayarlarının kullanıcı cihazlarda çalış çalış çalışı kontrol edin

Uygulamaları korumak amacıyla [Android cihazları için uygulama yapılandırmalarını ayarlayın](app-protection-settings-for-android-and-ios.md) ve seçtiğiniz ayarların çalıştığını doğrulamak için aşağıdaki adımları izleyin. 
  
İlk olarak, ilkenin doğrulamayı yapacak olacağınız uygulama için geçerli olduğundan emin olun.
  
1. yönetim Microsoft 365 İş Ekstra , [İlkeleri](https://admin.microsoft.com)Düzenleme **ilkesi** \> **'ne gidin.**
    
2. Kurulum **sırasında oluşturduğunuz ayarlarda Android** için uygulama ilkesi'ne veya oluşturduğunuz başka bir ilkeye tıklayın ve örneğin, Android için zorunlu Outlook doğrulayın. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Office uygulamalarına erişim için PIN veya parmak izi isteme doğrulaması

**İlkeyi düzenle** bölmesinde **Office belgelerine erişim denetimi**'nin yanındaki **Düzenle**'yi seçin, **Kullanıcıların mobil cihazlardan Office dosyalarına erişimini yönet**'i genişletin ve **Office uygulamalarına erişim için PIN veya parmak izi iste** seçeneğinin **Açık** olduğundan emin olun.
  
![Uygulamalara erişmek için PIN veya parmak izi Office'in On olarak ayar olduğundan emin olun.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Kullanıcının Android cihazında Oturum Outlook açın ve kullanıcının kullanıcı kimlik bilgileriyle Microsoft 365 İş Ekstra açın.
    
2. Ayrıca bir PIN girmeniz veya parmak izi girmeniz de istenir.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Birkaç başarısız girişimden sonra PIN sıfırlama doğrulaması

İlkeyi düzenle **bölmesinde, Office** belgelerine erişim denetimi'nin yanındaki Düzenle'yi seçin, Kullanıcıların mobil cihazlarda **Office** dosyalarına nasıl erişeceklerini yönet'i genişletin ve Birkaç başarısız girişimden sonra **PIN'i** sıfırla'nın bir sayı olarak ayarlanmış olduğundan emin olun.   Bu varsayılan olarak 5'tir. 
  
1. Kullanıcının Android cihazında Oturum Outlook açın ve kullanıcının kullanıcı kimlik bilgileriyle Microsoft 365 İş Ekstra açın.
    
2. İlke tarafından belirtilen sayıda yanlış PIN girin. PIN Deneme Sınırına Ulaşıldı uyarılarını ve **PIN'i sıfırlamayı** sizen bir istem görüntüler. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. **PIN'i Sıfırla**'ya basın. Kullanıcının kimlik bilgileriyle oturum açmanız ve ardından yeni bir PIN Microsoft 365 İş Ekstra girmeniz istenir.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorlama doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Açık** olduğundan emin olun.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Kullanıcının Android cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Eki olan bir e-posta açın ve ekin bilgilerinin yanındaki aşağı ok simgesine dokunun.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Ekranın en **altında Cihaza** kaydedilem'i görürsünüz. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Şu anda Android için OneDrive İş'e kaydetme etkinleştirilmemiştir; dolayısıyla, yalnızca yerel olarak kaydetmenin engellendiğini görebilirsiniz. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office uygulamaları şu kadar süre boşta kalırsa kullanıcıların yeniden oturum açmasını isteme doğrulaması

İlkeyi düzenle **bölmesinde, Office** belgelerine erişim denetimi'nin yanındaki Düzenle'yi seçin, Kullanıcıların mobil cihazlarda **Office** dosyalarına nasıl erişeceklerini yönet 'i genişletin ve Office uygulamaları belirli bir süre boşta kaldıktan sonra kullanıcıların yeniden oturum açmasını gerekli hale gelecek şekilde ayarlayın.    Bu, varsayılan olarak 30 dakikadır. 
  
1. Kullanıcının Android cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Şimdi Outlook gelen kutusunu görüyor olmalısınız. Android cihazına en az 30 dakika (veya ilkede belirttiğinizden daha uzun bir süre) boyunca dokunmayın ve boşta beklemesini sağlayın. Cihaz büyük olasılıkla kararacaktır.
    
3. Android Outlook Yeniden Erişin.
    
4. E-postanıza yeniden erişmeden önce PIN'inizi Outlook istenir.
    
### <a name="validate-protect-work-files-with-encryption"></a>Şifreli çalışma dosyalarını koruma doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Şifreli çalışma dosyalarını koru** seçeneğinin **Açık**, **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Kapalı** olarak ayarlandığından emin olun.
  
1. Kullanıcının Android cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Birkaç resim dosyası eki içeren bir e-postayı açın.
    
3. Kaydetmek için ekin bilgilerinin yanındaki aşağı ok simgesine dokunun.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Outlook'un cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin vermeniz istenebilir. **İzin Ver**'e dokunun.
    
5. Ekranın en altında, **Cihaza Kaydet**'i seçin ve ardından **Galeri** uygulamasını açın. 
    
6. Listede şifrelenmiş bir fotoğraf (birden çok resim dosyası eki kaydettiyseniz daha fazla olabilir) görüyor olmalısınız. Resimler listesinde, ortasında beyaz bir dairenin içinde beyaz bir ünlem işareti bulunan gri bir kare olarak gösteriliyor olabilir.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Uygulama koruma ayarlarının kullanıcı cihazlarında çalışıp çalışmadığını denetleme

Uygulamaları korumak amacıyla [iOS cihazları için uygulama yapılandırmalarını ayarlayın](app-protection-settings-for-android-and-ios.md) ve seçtiğiniz ayarların çalıştığını doğrulamak için aşağıdaki adımları izleyin. 
  
İlk olarak, ilkenin doğrulamayı yapacak olacağınız uygulama için geçerli olduğundan emin olun.
  
1. yönetim Microsoft 365 İş Ekstra , [İlkeleri](https://admin.microsoft.com)Düzenleme **ilkesi** \> **'ne gidin.**
    
2. Kurulum **sırasında oluşturduğunuz ayarlarda iOS** için uygulama ilkesi'ne veya oluşturduğunuz başka bir ilkeye tıklayın ve örneğin, bu ilkenin Outlook doğrulayın. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Office uygulamalarına erişmek için PIN istemeyi doğrulama

**İlkeyi düzenle** bölmesinde **Office belgelerine erişim denetimi**'nin yanındaki **Düzenle**'yi seçin, **Kullanıcıların mobil cihazlardan Office dosyalarına erişimini yönet**'i genişletin ve **Office uygulamalarına erişim için PIN veya parmak izi iste** seçeneğinin **Açık** olduğundan emin olun.
  
![Uygulamalara erişmek için PIN veya parmak izi Office'in On olarak ayar olduğundan emin olun.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Kullanıcının iOS cihazında Oturum Outlook açın ve kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra açın.
    
2. Ayrıca bir PIN girmeniz veya parmak izi girmeniz de istenir.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Birkaç başarısız girişimden sonra PIN sıfırlama doğrulaması

İlkeyi düzenle **bölmesinde, Office** belgelerine erişim denetimi'nin yanındaki Düzenle'yi seçin, Kullanıcıların mobil cihazlarda **Office** dosyalarına nasıl erişeceklerini yönet'i genişletin ve Birkaç başarısız girişimden sonra **PIN'i** sıfırla'nın bir sayı olarak ayarlanmış olduğundan emin olun.   Bu varsayılan olarak 5'tir. 
  
1. Kullanıcının iOS cihazında Oturum Outlook açın ve kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra açın.
    
2. İlke tarafından belirtilen sayıda yanlış PIN girin. PIN Deneme Sınırına Ulaşıldı uyarılarını ve **PIN'i sıfırlamayı** sizen bir istem görüntüler. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. **Tamam**'a basın. Kullanıcının kimlik bilgileriyle oturum açmanız ve ardından yeni bir PIN Microsoft 365 İş Ekstra girmeniz istenir.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorlama doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Açık** olduğundan emin olun.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Kullanıcının iOS cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Ek içeren bir e-postayı açın ve eki açıp ekranın altındaki **Kaydet**'i seçin. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. OneDrive İş için yalnızca bir seçenek görüyor olmanız gerekir. Hesap Ekle'ye **dokunun ve** hesap **OneDrive İş'den** Hesap **Ekle Depolama** seçin. İstendiğinde, son Microsoft 365 İş Ekstra oturum açma bilgilerini sağlama. 
    
    **Kaydet**'e tıklayıp **OneDrive İş**'i seçin.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office uygulamaları belirli bir süre boyunca boşta kalırsa kullanıcının tekrardan oturum açmasını istemeyi doğrulama

İlkeyi düzenle **bölmesinde, Office** belgelerine erişim denetimi'nin yanındaki Düzenle'yi seçin, Kullanıcıların mobil cihazlarda **Office** dosyalarına nasıl erişeceklerini yönet 'i genişletin ve Office uygulamaları belirli bir süre boşta kaldıktan sonra kullanıcıların yeniden oturum açmasını gerekli hale gelecek şekilde ayarlayın.    Bu, varsayılan olarak 30 dakikadır. 
  
1. Kullanıcının iOS cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Şimdi Outlook gelen kutusunu görüyor olmanız gerekir. iOS cihazına en az 30 dakika (veya ilkede belirttiğinizden daha uzun bir süre) boyunca dokunmayın. Cihaz büyük olasılıkla kararır.
    
3. iOS Outlook Access e-postanıza yeniden erişin.
    
4. E-postanıza yeniden erişmeden önce PIN'inizi Outlook istenir.
    
### <a name="validate-protect-work-files-with-encryption"></a>Şifreli çalışma dosyalarını koruma doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Şifreli çalışma dosyalarını koru** seçeneğinin **Açık**, **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Kapalı** olarak ayarlandığından emin olun.
  
1. Kullanıcının iOS cihazında, Outlook'i açın, kullanıcının kimlik bilgileriyle Microsoft 365 İş Ekstra ve istenirse PIN girin.
    
2. Birkaç resim dosyası eki içeren bir e-postayı açın.
    
3. Eke dokunun ve sonrasında altındaki **Kaydet** seçeneğine dokunun. 
    
4. Giriş ekranından **Fotoğraflar** uygulamasını açın. Şifreli bir resmin (birden çok resim dosyası eki kaydettiyseniz daha fazla olabilir) kaydedildiğini, ancak şifrelenmiş olduğunu görürsünüz. 
    
---

