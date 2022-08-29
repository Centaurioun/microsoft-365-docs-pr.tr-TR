---
title: Microsoft OneDrive LTI'yi Desire2Learn Brightspace ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection: m365initiative-edu
ms.localizationpriority: medium
description: Yeni Desire2Learn Brightspace için Microsoft OneDrive Öğrenme Araçları Birlikte Çalışabilirliği ile ödevler oluşturun ve notlayın, kurs içeriğini derleyin ve dosyalar üzerinde gerçek zamanlı olarak işbirliği yapın.
ms.openlocfilehash: 922e722011a979e8486ad9d01a7dc9c4cd0bf626
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67389470"
---
# <a name="integrate-microsoft-onedrive-lti-with-desire2learn-brightspace"></a>Microsoft OneDrive LTI'yi Desire2Learn Brightspace ile tümleştirme

Bu kılavuz, Desire2Learn (D2L) Brightspace LMS için OneDrive LTI uygulamasını kaydetmek için BT yöneticilerinin adımlarını sağlar.

Microsoft LTI'ye genel bakış için bkz. [Microsoft ürünlerini Öğrenme Yönetim Sisteminizle (LMS) tümleştirme](index.md).

OneDrive LTI uygulamasını ekleme adımları şunlardır:

1. [1. Adım: Yeni Microsoft OneDrive LTI uygulamasını ekleyin](#step-1-add-the-new-microsoft-onedrive-lti-app).
1. [2. Adım: Kullanıcıların Brightspace deneyiminde LTI uygulamasını dağıtın](#step-2-deploy-the-lti-app-in-users-brightspace-experience).
1. [3. Adım: Eski OneDrive uygulamasını kapatın](#step-3-turn-off-the-older-onedrive-app).
1. [4. Adım: Hızlı Bağlantılar etkinlik çubuğunda yeni OneDrive LTI uygulamasını açın](#step-4-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar-optional) (isteğe bağlı).

> [!IMPORTANT]
> Bu tümleştirmeyi gerçekleştiren kişi Brightspace yöneticisi ve Microsoft 365 kiracısının yöneticisi olmalıdır.
>
> LTI 1.3 ayarlarının kaynak belgeleri [LTI Avantajı - Yönetici Kılavuzu'nda](https://community.brightspace.com/s/article/LTI-Advantage-Administrator-Guide) bulunur.

## <a name="step-1-add-the-new-microsoft-onedrive-lti-app"></a>1. Adım: Yeni Microsoft OneDrive LTI uygulamasını ekleme

### <a name="register-a-new-microsoft-onedrive-lti-app"></a>Yeni bir Microsoft OneDrive LTI uygulaması kaydetme

1. [Microsoft OneDrive LTI Kayıt Portalı'na giriş](https://onedrivelti.microsoft.com/admin) yapın.
1. **Yönetici Onay** düğmesini seçin ve izinleri kabul edin.
    1. Bu adım gerçekleştirilmezse, aşağıdaki adım size bir hata verir ve hatayı aldıktan sonra bu adımı bir saat boyunca gerçekleştiremezsiniz.
1. **Yeni LTI Kiracısı oluştur** düğmesini seçin.
1. **LTI Tüketici Platformu** listesinde **D2L Brightspace'i** seçin.
1. **D2L Brightspace Temel URL'si** alanına Brightspace temel URL'nizi (gibi) `https://testschool.brightspace.com`girin.
1. **İleri** düğmesini seçin. **LTI 1.3 Uygulamasını Kaydet** sayfası yüklenir.
    1. Sonraki adım kümesini tamamlarken bu sayfayı kendi sekmesinde açık tutun.

### <a name="add-microsoft-lti-registration-details-to-brightspace"></a>Microsoft LTI kayıt ayrıntılarını Brightspace'e ekleme

1. Yeni bir sekmede, yeni Microsoft LTI uygulamasını kaydetmek için Brightspace yönetici sitenizi açın.
1. **Yönetici** >  **Genişletilebilirliği Yönet'e** gidin ve **LTI Avantajı'nı** seçin.
1. **Uygulamayı Kaydet'i** seçin.
1. Uygulamanızı **standart** olarak kaydedin.
1. Uygulama için gibi `OneDrive LTI`bir ad girin.
1. GIBI LTI uygulamasını `https://onedrivelti.microsoft.com`kaydettiğiniz URL'nin etki alanını girin.
1. Microsoft LTI Kayıt Portalı'nda verilen ayrıntıları kullanarak **Yeniden Yönlendirme URL'sini**, **OpenID Connect Oturum Açma URL'sini** ve **Keyset URL'sini** kopyalayıp Brightspace'e yapıştırın.
    1. Microsoft'un **Yeniden Yönlendirme URL'sini** Brightspace'in **ToolOIDCLaunchRedirectUri** alanına yapıştırın.
    1. Microsoft'un **OpenID Connect Oturum Açma URL'sini** Brightspace'in **OIDCLoginInitiationUri** alanına yapıştırın.
    1. Microsoft'un **Anahtar Kümesi URL'sini** Brightspace'in **ToolPublicJwksUri** alanına yapıştırın.
1. **Derin Bağlama** uzantısını seçin.
1. **Kaydet'i** seçin.
1. Size Brightspace kayıt ayrıntıları gösterilir.
    1. Sonraki adım kümesini tamamlarken bu sayfayı kendi sekmesinde açık tutun.

### <a name="add-brightspace-lti-registration-details-to-the-microsoft-lti-registration-portal"></a>Brightspace LTI kayıt ayrıntılarını Microsoft LTI Kayıt Portalı'na ekleme

Uygulama Brightspace'e kaydedildikten sonra, Değerleri Brightspace'in kayıt portalından Microsoft'un LTI kayıt portalına kopyalayın.

1. Microsoft'un **Kayıt LTI 1.3 Uygulaması** sayfasının açık sekmenize geri dönün.
1. Brightspace kayıt ayrıntılarını kopyalayın ve Microsoft'un LTI Kayıt Portalına yapıştırın.
    1. Brightspace'in **Veren'ini** Microsoft'un **LTI Vereni** alanına yapıştırın.
    2. Brightspace'in **OpenID Connect Kimlik Doğrulama Uç Noktasını** Microsoft'un **LTI Yetkilendirme URL'si** alanına yapıştırın.
    3. Brightspace'in **Brightspace Anahtar Kümesi URL'sini** Microsoft'un **LTI Genel Jwks URL'si** alanına yapıştırın.
    4. Brightspace'in **Brightspace OAuth2 Erişim Belirteci URL'sini** Microsoft'un **LTI Erişim Belirteci URL'si** alanına yapıştırın.
    5. Brightspace'in **İstemci Kimliğini** Microsoft'un **LTI İstemci Kimliği** alanına yapıştırın.
1. **İleri** düğmesini seçin.
1. **Kaydet** düğmesini seçin.
1. *LTI tüketicisi başarıyla oluşturuldu iletisi.* Görünür.
1. Giriş sayfasındaki **LTI Kiracılarını Görüntüle** düğmesini seçerek kayıt ayrıntılarınızı gözden geçirin.

## <a name="step-2-deploy-the-lti-app-in-users-brightspace-experience"></a>2. Adım: Kullanıcıların Brightspace deneyiminde LTI uygulamasını dağıtma

Microsoft OneDrive LTI ve Brightspace bağlandıktan sonra Kullanıcıların Brightspace deneyiminde OneDrive LTI uygulamasını dağıtmanız gerekir.

1. Brightspace yönetici sitenizde oturum açın.
1. Oluşturduğunuz LTI uygulamasını seçin.
1. Dağıtıma bir ad girin.
1. **Sınıf listesi** ve **Anonim** dışındaki tüm güvenlik ayarlarını seçin.
1. Yapılandırma ayarlarını yapmayın.
1. **Dağıtım Oluştur'u** seçin.
1. Yeni LTI uygulamasını kullanmak istediğiniz kuruluş birimlerini seçin. Herkesi dahil etmek için kök kuruluşu seçebilir veya tek tek kuruluş birimlerini seçebilirsiniz.

### <a name="create-links-to-the-onedrive-lti-app-in-users-brightspace-experience"></a>Kullanıcıların Brightspace deneyiminde OneDrive LTI uygulamasına bağlantılar oluşturma

1. Brightspace yönetici sitenizde oturum açın.
1. Oluşturduğunuz Brightspace OneDrive LTI uygulamasını seçin. Dağıtım ayrıntıları görüntülenir.
1. **Bağlantıları Görüntüle'yi** seçin.
1. **Bağlantı oluştur'u** seçin.
1. Bağlantı için bir ad girin.
1. **Yeniden Yönlendirme URL'sini URL** alanına yapıştırın.
1. **Tür'leri** **Derin Bağlantı Hızlı Bağlantısı** olarak ayarlayın.
1. **Kaydet ve Kapat** düğmesini seçin.

OneDrive LTI uygulaması artık Brightspace'te **Mevcut İçeriği** ve **Hızlı Bağlantıları** Ekle'de gösterilir. Bağlantıda OneDrive *bulut* simgesi yerine genel bir *bağlantı* simgesi gösterilir. Ayrıca başlık, uygulamanın LTI bağlantı ayarlarında sağlanan adı yansıtır.

## <a name="step-3-turn-off-the-older-onedrive-app"></a>3. Adım: Eski OneDrive uygulamasını kapatma

OneDrive LTI uygulaması artık kullanıcılar tarafından kullanılabilir, ancak eski OneDrive uygulamasının artık kapatılması gerekir.

1. Brightspace yönetici portalınızda oturum açın.
1. **Yönetici** >  **Config Değişken Tarayıcısı'na** gidin
1. **d2l.3rdParty.OneDrive.EnableOneDrivePicker** adlı değişkeni bulun ve değeri **kapalı** olarak ayarlayın.

## <a name="step-4-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar-optional"></a>4. Adım: Hızlı Bağlantılar etkinlik çubuğunda yeni OneDrive LTI uygulamasını açma (isteğe bağlı)

OneDrive LTI uygulamasını Brightspace'in etkinlik çubuğuna eklemek için LTI uygulamasının **bağlantı kimliğine** bir kuruluş birimi **Yapılandırma Değişkeni** ayarlayın.

OneDrive LTI uygulamasının etkinlik çubuğunda görünmesini istediğiniz her kuruluş kimliği (veya üst kuruluş kimliği) için bu adımları tekrarlamanız gerekir.

### <a name="collect-the-link-ids"></a>Bağlantı Kimliklerini Toplama

1. Brightspace yönetici portalınızda oturum açın.
1. Sayfanın en altındaki **Yönetici** >  **External Öğrenme Araçları** > **LTI Avantajı Dağıtımları** > **Görünüm Bağlantıları'na** gidin.
1. Doğru bağlantıya gidin ve ardından farenizi tarayıcının üst kısmındaki URL'ye getirin.
    1. Örneğin, `https://example.desire2learn.com/d2l/le/ltiadvantage/deployments/3bfcc0b7-2fb6-4ffe-b353-95b520d4bae6/links/details/25988`.
1. URL'de finalden `/` sonraki basamakları kopyalayın.
    1. Örneğin, yukarıdaki URL'yi kullanarak kopyalayın `25988`.

### <a name="update-the-config-variables"></a>Yapılandırma Değişkenlerini Güncelleştirme

1. Brightspace yönetici portalında **Yönetici** >  **Config Değişken Tarayıcısı'na** gidin.
1. **3rdparty.microsoft.onedriveLTI.linkId** adlı değişkeni bulun ve kopyalanan URL'yi OneDrive LTI'sinin görünmesi gereken kuruluş birimlerinin **bağlantı kimliği** alanına yapıştırın.
    1. Bu değer bir sayıdır.

## <a name="common-questions-concerning-the-onedrive-lti-app"></a>OneDrive LTI uygulamasıyla ilgili sık sorulan sorular

### <a name="does-the-new-onedrive-lti-filepicker-support-personal-accounts"></a>Yeni OneDrive LTI FilePicker kişisel hesapları destekliyor mu?

Evet, kişisel hesapların dosyaları karşıya yüklemek için OneDrive'ı açmasına izin verilir. Uygulamada OneDrive LTI kayıt portalında birden çok uçtan bir uçtan diğerine izin vermek veya izin vermemek için bir onay kutusu vardır. İşaretlenirse kişisel hesaplara izin verilir.

### <a name="does-the-filepicker-support-multiple-languages"></a>FilePicker birden çok dili destekliyor mu?

OneDrive LTI FilePicker, LMS'den geçirilen LTI dil ayarı parametresine ve kullanılacak dili belirlemek için tarayıcı ayarını (yedek olarak) (eski isteğe bağlı bir talep olduğundan) arar.
