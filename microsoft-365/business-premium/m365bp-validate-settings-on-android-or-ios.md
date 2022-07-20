---
title: Android veya iOS cihazlarda uygulama koruma ayarlarını doğrulama
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: medium
ms.date: 07/19/2022
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
description: Android veya iOS cihazlarınızda Microsoft 365 İş Ekstra uygulama koruma ayarlarını doğrulamayı öğrenin. Uygulamalarınız için güvenlik ayarlarının yapılması, mobil uygulamalarınızdaki ve cihazlarınızdaki dosyaları her türlü güvenlik tehdidine karşı korumak için kritik öneme sahiptir.
ms.openlocfilehash: 36a67f999cb9b4476f3757daa6033e6409b49c1a
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893825"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Android veya iOS cihazlarda uygulama koruma ayarlarını doğrulama


Android veya iOS cihazlarda uygulama koruma ayarlarını doğrulamak için aşağıdaki bölümlerde yer alan yönergeleri izleyin.
  
## <a name="android"></a>[Android](#tab/Android)  

### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Uygulama koruma ayarlarının kullanıcı cihazlarında çalışıp çalışmadığını denetleyin

Uygulamaları korumak [için Android veya iOS cihazları için uygulama koruma ayarlarını ayarladıktan](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md) sonra, seçtiğiniz ayarları doğrulamak için bu adımları izleyebilirsiniz.
  
İlk olarak, ilkenin doğruladığınız uygulamaya uygulandığından emin olun.
  
1. Microsoft 365 İş Ekstra [yönetim merkezinde](https://admin.microsoft.com) **İlkeleri** \> **Düzenleme ilkesi'ne** gidin.

2. Kurulum sırasında oluşturduğunuz ayarlar **için Android için Uygulama ilkesi'ni** veya oluşturduğunuz başka bir ilkeyi seçin ve örneğin Outlook için uygulandığını doğrulayın. 

    ![Bu ilkenin dosyaları koruduğu tüm uygulamaları gösteren ekran görüntüsü.](../business-premium/media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Office uygulamalarına erişim için PIN veya parmak izi isteme doğrulaması

**İlkeyi düzenle** bölmesinde **Office belgelerine erişim denetimi**'nin yanındaki **Düzenle**'yi seçin, **Kullanıcıların mobil cihazlardan Office dosyalarına erişimini yönet**'i genişletin ve **Office uygulamalarına erişim için PIN veya parmak izi iste** seçeneğinin **Açık** olduğundan emin olun.
  
![Office uygulamalarına erişmek için PIN veya parmak izi iste seçeneğinin Açık olarak ayarlandığından emin olun.](../business-premium/media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Kullanıcının Android cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın.

2. Ayrıca PIN girmeniz veya parmak izi kullanmanız istenir.

    ![Enter a PIN on your Android device to access Office apps.](../business-premium/media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Birkaç başarısız girişimden sonra PIN sıfırlama doğrulaması

**İlkeyi düzenle** bölmesinde **, Office belgeleri erişim denetiminin** yanındaki **Düzenle'yi** seçin, **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet'i** genişletin ve **başarısız deneme sayısından sonra PIN'i sıfırla seçeneğinin** bir sayı olarak ayarlandığından emin olun. Bu, varsayılan olarak 5'tir. 
  
1. Kullanıcının Android cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın.

2. İlke tarafından belirtilen sayıda yanlış PIN girin. PIN'i sıfırlamak için **PIN Deneme Sınırına Ulaşıldı** ifadesini belirten bir istem görürsünüz. 

    ![Çok fazla yanlış PIN denemesi yaptıktan sonra PIN'inizi sıfırlamanız gerektiğini gösteren ekran görüntüsü.](../business-premium/media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. **PIN'i Sıfırla**'ya basın. Kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açmanız istenir ve ardından yeni bir PIN ayarlamanız gerekir.

### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorlama doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Açık** olduğundan emin olun.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../business-premium/media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Kullanıcının Android cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

2. Eki olan bir e-posta açın ve ekin bilgilerinin yanındaki aşağı ok simgesine dokunun.

    ![Tap the down arrow next to an attachment to try to save it.](../business-premium/media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Ekranın alt kısmında **Cihaza kaydedilemiyor** ifadesini görürsünüz. 

    ![Warning text that indicates cannot save a file locally to an Android.](../business-premium/media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Şu anda Android için OneDrive İş'e kaydetme etkinleştirilmemiştir; dolayısıyla, yalnızca yerel olarak kaydetmenin engellendiğini görebilirsiniz. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office uygulamaları şu kadar süre boşta kalırsa kullanıcıların yeniden oturum açmasını isteme doğrulaması

**İlkeyi düzenle** bölmesinde **, Office belgeleri erişim denetiminin** yanındaki **Düzenle'yi** seçin, **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet'i** genişletin ve **Office uygulamaları boşta kaldığında kullanıcıların yeniden oturum açmasını gerektir** seçeneğinin birkaç dakika olarak ayarlandığından emin olun. Bu, varsayılan olarak 30 dakikadır. 
  
1. Kullanıcının Android cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

1. Şimdi Outlook gelen kutusunu görüyor olmalısınız. Android cihazına en az 30 dakika (veya ilkede belirttiğinizden daha uzun bir süre) boyunca dokunmayın ve boşta beklemesini sağlayın. Cihaz büyük olasılıkla kararacaktır.

1. Android cihazda Outlook'a yeniden erişin.

1. Outlook'a yeniden erişebilmeniz için pin kodunuzu girmeniz istenir.

### <a name="validate-protect-work-files-with-encryption"></a>Şifreli çalışma dosyalarını koruma doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Şifreli çalışma dosyalarını koru** seçeneğinin **Açık**, **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Kapalı** olarak ayarlandığından emin olun.
  
1. Kullanıcının Android cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

1. Birkaç resim dosyası eki içeren bir e-posta açın.

1. Kaydetmek için ekin bilgilerinin yanındaki aşağı ok simgesine dokunun.

    ![Tap the down arrow to save the figure file to the Android device.](../business-premium/media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
1. Outlook'un cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin vermeniz istenebilir. **İzin Ver**'e dokunun.

1. Ekranın en altında, **Cihaza Kaydet**'i seçin ve ardından **Galeri** uygulamasını açın.

1. Listede şifrelenmiş bir fotoğraf (birden çok resim dosyası eki kaydettiyseniz daha fazla olabilir) görüyor olmalısınız. Resimler listesinde, ortasında beyaz bir dairenin içinde beyaz bir ünlem işareti bulunan gri bir kare olarak gösteriliyor olabilir.

    ![An encrypted image file in the Gallery app.](../business-premium/media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
### <a name="ios"></a>[iOS](#tab/iOS)

## <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Uygulama koruma ayarlarının kullanıcı cihazlarında çalışıp çalışmadığını denetleme

Uygulamaları korumak amacıyla [iOS cihazları için uygulama yapılandırmalarını ayarlayın](../business-premium/m365bp-protection-settings-for-windows-10-devices.md) ve seçtiğiniz ayarların çalıştığını doğrulamak için aşağıdaki adımları izleyin. 
  
İlk olarak, ilkenin doğruladığınız uygulamaya uygulandığından emin olun.
  
1. Microsoft 365 İş Ekstra [yönetim merkezinde](https://admin.microsoft.com) **İlkeleri** \> **Düzenleme ilkesi'ne** gidin.

1. Kurulum sırasında oluşturduğunuz ayarlar **için iOS için Uygulama ilkesi'ni** veya oluşturduğunuz başka bir ilkeyi seçin ve örneğin Outlook için uygulandığını doğrulayın. 

    ![Bu ilkenin dosyaları koruduğu tüm uygulamaları gösteren ekran görüntüsü.](../business-premium/media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Office uygulamalarına erişmek için PIN istemeyi doğrulama

**İlkeyi düzenle** bölmesinde **Office belgelerine erişim denetimi**'nin yanındaki **Düzenle**'yi seçin, **Kullanıcıların mobil cihazlardan Office dosyalarına erişimini yönet**'i genişletin ve **Office uygulamalarına erişim için PIN veya parmak izi iste** seçeneğinin **Açık** olduğundan emin olun.
  
![Office uygulamalarına erişmek için PIN veya parmak izi iste seçeneğinin Açık olarak ayarlandığından emin olun.](../business-premium/media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Kullanıcının iOS cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın.

1. Ayrıca PIN girmeniz veya parmak izi kullanmanız istenir.

    ![Enter a PIN on your IOS device to access Office apps.](../business-premium/media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Birkaç başarısız girişimden sonra PIN sıfırlama doğrulaması

**İlkeyi düzenle** bölmesinde **, Office belgeleri erişim denetiminin** yanındaki **Düzenle'yi** seçin, **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet'i** genişletin ve **başarısız deneme sayısından sonra PIN'i sıfırla seçeneğinin** bir sayı olarak ayarlandığından emin olun. Bu, varsayılan olarak 5'tir.
  
1. Kullanıcının iOS cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın.

1. İlke tarafından belirtilen sayıda yanlış PIN girin. PIN'i sıfırlamak için **PIN Deneme Sınırına Ulaşıldı** ifadesini belirten bir istem görürsünüz.

    ![Çok fazla yanlış denemeden sonra PIN sıfırlama uyarısı ekran görüntüsü.](../business-premium/media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
1. **Tamam**'a basın. Kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açmanız istenir ve ardından yeni bir PIN ayarlamanız gerekir.

### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorlama doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Açık** olduğundan emin olun.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../business-premium/media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Kullanıcının iOS cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

1. Ek içeren bir e-postayı açın ve eki açıp ekranın altındaki **Kaydet**'i seçin. 

    ![Tap the Save option after you open an attachment to try to save it.](../business-premium/media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
1. OneDrive İş için yalnızca bir seçenek görüyor olmanız gerekir. Aksi takdirde **Hesap Ekle'ye** dokunun ve **Depolama Hesabı Ekle** **ekranından OneDrive İş** seçin. İstendiğinde oturum açmak için son kullanıcının Microsoft 365 İş Ekstra sağlayın.

    **Kaydet**'e tıklayıp **OneDrive İş**'i seçin.

### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Office uygulamaları belirli bir süre boyunca boşta kalırsa kullanıcının tekrardan oturum açmasını istemeyi doğrulama

**İlkeyi düzenle** bölmesinde **, Office belgeleri erişim denetiminin** yanındaki **Düzenle'yi** seçin, **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet'i** genişletin ve **Office uygulamaları boşta kaldığında kullanıcıların yeniden oturum açmasını gerektir** seçeneğinin birkaç dakika olarak ayarlandığından emin olun. Bu, varsayılan olarak 30 dakikadır.
  
1. Kullanıcının iOS cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

1. Şimdi Outlook gelen kutusunu görüyor olmanız gerekir. iOS cihazına en az 30 dakika (veya ilkede belirttiğinizden daha uzun bir süre) boyunca dokunmayın. Cihaz büyük olasılıkla kararır.

1. iOS cihazında Outlook'a yeniden erişin.

1. Outlook'a yeniden erişebilmeniz için pin kodunuzu girmeniz istenir.

### <a name="validate-protect-work-files-with-encryption"></a>Şifreli çalışma dosyalarını koruma doğrulaması

**İlkeyi düzenle** bölmesinde **Kaybolmuş veya çalınmış cihaz koruması**'nın yanındaki **Düzenle**'yi seçin, **Cihaz kaybolursa veya çalınırsa çalışma dosyalarını koru**'yu genişletin ve **Şifreli çalışma dosyalarını koru** seçeneğinin **Açık**, **Kullanıcıları, tüm çalışma dosyalarını OneDrive İş'e kaydetmeye zorla** seçeneğinin **Kapalı** olarak ayarlandığından emin olun.
  
1. Kullanıcının iOS cihazında Outlook'u açın ve kullanıcının Microsoft 365 İş Ekstra kimlik bilgileriyle oturum açın ve istenirse bir PIN girin.

1. Birkaç resim dosyası eki içeren bir e-posta açın.

1. Eke dokunun ve sonrasında altındaki **Kaydet** seçeneğine dokunun. 

1. Giriş ekranından **Fotoğraflar** uygulamasını açın. Şifreli bir resmin (birden çok resim dosyası eki kaydettiyseniz daha fazla olabilir) kaydedildiğini, ancak şifrelenmiş olduğunu görürsünüz. 

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)