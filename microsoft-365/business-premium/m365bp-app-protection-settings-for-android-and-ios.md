---
title: Android veya iOS cihazlara yönelik uygulama koruma ayarlarını belirleme
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Android veya iOS cihazlarda uygulama yönetimi ilkesi oluşturmayı, düzenlemeyi veya silmeyi ve iş dosyalarını korumayı öğrenin.
ms.openlocfilehash: 60bc5b3b69eacf9573dd806734cb47355266d3a5
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66862186"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Android veya iOS cihazlara yönelik uygulama koruma ayarlarını belirleme

YouTube'da [Microsoft 365 küçük işletme yardımına](https://go.microsoft.com/fwlink/?linkid=2197659) göz atın.

Bu makale Microsoft 365 İş Ekstra için geçerlidir.

## <a name="watch-secure-office-apps-on-ios"></a>İzleyin: iOS'ta Office uygulamalarının güvenliğini sağlama

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2197828) bu videoya ve diğer videolara göz atın.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Mobil kullanıcıların oturum açmak için PIN veya parmak izi girmesini gerektiren ve ayrıca cihazlarında depolanan iş dosyalarını şifreleyen bir kullanıcı erişim ilkesi ayarlayabilirsiniz.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetici merkezi</a>'nde oturum açın.

2. **İlkeler'in** altında **İlke ekle'yi** seçin.

3. **İlke ekle** bölmesinde, **İlke adı'nın** altına bir ad girin ve **İlke türü** altında istediğiniz ilke türünü seçin.

4. **Cihazlar kaybolduğunda veya çalındığında iş dosyalarını koru'yu** açın ve ardından aşağıdaki üç ayarın açık olduğundan emin olun:
 
    - **Tüm kullanıcıları iş dosyalarını OneDrive İş üzerine kaydetmeye zorla**
  
    - **İş dosyalarını şifrele**

5. **Kullanıcıların Mobil cihazlarda Office dosyalarına nasıl erişeceklerini yönet'i** açın ve ayarların her öğe için açık veya ayarlanmış olduğundan emin olun.

6. **Bu uygulamalardaki dosyalar korunacak** bölümünde, mobil cihazlarda korumak istediğiniz Office uygulamalarını seçin.

7. **Bu ayarları kim alacak?** altında varsayılan olarak tüm kullanıcılar seçilir, ancak oluşturduğunuz güvenlik gruplarını seçmek için **Değiştir'i** seçebilirsiniz.

8. İlkeyi oluşturmayı tamamlamak için **Ekle'yi** seçin.

9. **İlke ekle** sayfasında **Kapat'ı** seçin.

10. Yönetim merkezi giriş sayfasında İlkeler'i seçip **İlkeler** sayfasında ilkenizi gözden geçirerek yeni ilkenizin eklendiğini onaylayın.

## <a name="create-an-app-management-policy"></a>Uygulama yönetimi ilkesi oluşturma

1. Şuradan yönetim merkezine gidin: <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Sol gezinti bölmesinde **Cihaz** \> **İlkeleri** \> **Ekle'yi** seçin.
  
3. **İlke ekle** bölmesinde bu ilke için benzersiz bir ad girin.

4. **İlke türü altında**, oluşturmak istediğiniz ilke kümesine bağlı olarak **Android** **için Uygulama Yönetimi'ni veya iOS için Uygulama Yönetimi'ni** seçin.

5. **Cihazlar kaybolduğunda veya çalındığında iş dosyalarını koru'yu** ve **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceklerini yönetin'i** genişletin. Ayarları istediğiniz gibi yapılandırın. **Kullanıcıların mobil cihazlarda Office dosyalarına nasıl erişeceklerini yönetme** varsayılan olarak **Kapalıdır** , ancak bunu **Açık** duruma getirin ve varsayılan değerleri kabul edin. Daha fazla bilgi için bkz [. Kullanılabilir ayarlar](#available-settings).

    Varsayılan ayara dönmek için her zaman **Varsayılan ayarları geri yükle** bağlantısını kullanabilirsiniz.

:::image type="content" source="Media/m365bp-add-policy.png" alt-text="Uygulama yönetimi ile bir ilke oluşturun.":::
  
6. Next decide **Who will get these settings?** Varsayılan **Tüm Kullanıcılar** güvenlik grubunu kullanmak istemiyorsanız **Değiştir'i** seçin, bu ayarları \> alan güvenlik gruplarını **seçin Seç'i seçin**.

7. Son olarak, **Bitti**'yi seçerek ilkeyi kaydedin ve cihazlarınıza atayın.

## <a name="edit-an-app-management-policy"></a>Uygulama yönetimi ilkesini düzenleme

1. **İlkeler** kartında **İlkeyi düzenle'yi** seçin.

2. **İlkeyi düzenle** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

3. İlkedeki değerleri değiştirmek için her ayarın yanında bulunan **Düzenle**'yi seçin. Bir değeri değiştirdiğinizde, bu değer ilkeye otomatik olarak kaydedilir.

4. İşiniz bittiğinde **İlkeyi düzenle** bölmesini kapatın.

## <a name="delete-an-app-management-policy"></a>Uygulama yönetimi ilkesini silme

1. **İlkeler** sayfasında bir ilke seçin ve ardından **Sil'i seçin**.

2. **İlkeyi sil** bölmesinde, seçtiğiniz ilkeyi veya ilkeleri silmek için **Onayla'yı** seçin. 

## <a name="available-settings"></a>Kullanılabilir ayarlar

Aşağıdaki tablolarda, cihazlardaki iş dosyalarını korumak için kullanılabilen ayarlar ve kullanıcıların mobil cihazlarından Office dosyalarına nasıl erişeceklerini denetleye ayarlar hakkında ayrıntılı bilgi verilmektedir.
  
 Daha fazla bilgi için bkz. [Microsoft 365 İş Ekstra koruma özellikleri Intune ayarlarıyla nasıl eşleştirilir](m365bp-map-protection-features-to-intune-settings.md)? 
  
### <a name="settings-that-protect-work-files"></a>İş dosyalarını koruyan ayarlar

Bir kullanıcının cihazı kaybolursa veya çalınırsa, iş dosyalarını korumak için aşağıdaki ayarlar kullanılabilir:


|Ayar  |Açıklama  |
|:-----|:-----|
|İş dosyalarını şu kadar gün sonra etkin olmayan cihazdan sil  |Bir cihaz burada belirttiğiniz gün sayısı için kullanılmazsa, cihazda depolanan tüm iş dosyaları otomatik olarak silinir.  |
|Tüm kullanıcıları iş dosyalarını OneDrive İş üzerine kaydetmeye zorla  |Bu ayar **Açık** ise, iş dosyaları için tek kullanılabilir kaydetme konumu OneDrive İş.  |
|İş dosyalarını şifrele  |İş dosyalarınızın şifreleme ile korunması için bu ayarı **Açık** tutun. Cihaz kaybolsa veya çalınsa bile, şirket verilerinizi kimse okuyamıyor.  |

### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Kullanıcıların Office dosyalarına mobil cihazlardan erişimini denetleyen ayarlar

Kullanıcıların Office iş dosyalarına erişimini yönetmek için şu ayarlar kullanılabilir:

|Ayar  |Açıklama  |
|:-----|:-----|
|Office uygulamalarına erişirken PIN veya parmak izi iste  |Bu ayar **Açık** ise, kullanıcıların mobil cihazlarında Office uygulamalarını kullanabilmeleri için önce kullanıcı adları ve parolalarına ek olarak başka bir kimlik doğrulama biçimi sağlamaları gerekir.|
|Belirli sayıda başarısız oturum açma girişimi yapıldığında PIN'i sıfırla  |Yetkisiz bir kullanıcının PIN'i rastgele tahmin etmesini engellemek için belirlediğiniz sayıda yanlış giriş yapılırsa PIN sıfırlanır.  |
|Office uygulamaları belirli bir süre boyunca boşta kalırsa kullanıcıların yeniden oturum açmasını iste  |Bu ayar, bir kullanıcının yeniden oturum açması istenmeden önce ne kadar süre boşta olabileceğini belirler.  |
|Jailbreak uygulanmış veya kök erişim izni verilmiş cihazlardan iş dosyalarına erişilmesini engelle  |Akıllı kullanıcılar, bir cihaza jailbreak uygulamış veya kök erişim izni sağlamış olabilir. Bu, işletim sisteminin kullanıcı tarafından değiştirilebileceği ve dolayısıyla, cihazın kötü amaçlı yazılımlara karşı daha savunmasız hale gelebileceği anlamına gelir. Bu ayar **Açık** olduğunda böyle cihazlar engellenir.    |
|Kullanıcıların Office uygulamalarından kişisel uygulamalara içerik kopyalamasına izin verme  |Bu duruma varsayılan olarak izin verilir, ancak bu ayar **Açık** olduğunda kullanıcı bir iş dosyasındaki bilgileri kişisel bir dosyaya aktarabilir. Ayar **Kapalı** durumdaysa, kullanıcı iş hesabındaki bilgileri kişisel bir uygulamaya veya kişisel hesaba kopyalayamaz.  |

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)