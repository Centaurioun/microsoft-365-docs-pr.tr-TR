---
title: Microsoft OneDrive LTI'yi Desire2Learn Brightspace ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
ms.collection: m365initiative-edu
ms.localizationpriority: medium
description: Yeni Desire2Learn Brightspace için Microsoft OneDrive Öğrenme Araçları Birlikte Çalışabilirliği ile ödevler oluşturun ve notlayın, kurs içeriğini derleyin ve dosyalar üzerinde gerçek zamanlı olarak işbirliği yapın.
ms.openlocfilehash: d01a934d134ceb8b62658d81f0d6500c467f82b4
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768511"
---
# <a name="integrate-microsoft-onedrive-lti-with-desire2learn-brightspace"></a>Microsoft OneDrive LTI'yi Desire2Learn Brightspace ile tümleştirme

Bu kılavuz, Desire2Learn (D2L) Brightspace LMS için OneDrive LTI uygulamasını kaydetmek için BT yöneticilerinin adımlarını sağlar.

Microsoft LTI'ye genel bakış için bkz. [Microsoft ürünlerini Öğrenme Yönetim Sisteminizle (LMS) tümleştirme](index.md).

OneDrive LTI uygulamasını ekleme adımları şunlardır:

1. [1. Adım: Yeni Microsoft OneDrive LTI uygulamasını ekleyin](#step-1-add-the-new-microsoft-onedrive-lti-app).
1. [2. Adım: Kullanıcıların Brightspace deneyiminde LTI uygulamasını dağıtın](#step-2-deploy-the-lti-app-in-users-brightspace-experience).
1. [3. Adım: Hızlı Bağlantılar Etkinlik Çubuğu'nda yeni OneDrive LTI uygulamasını açın](#step-3-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar).

> [!NOTE]
> Bu tümleştirmeyi gerçekleştiren kişi Brightspace yöneticisi ve Microsoft 365 kiracısının yöneticisi olmalıdır.
>
> LTI 1.3 ayarlarının kaynak belgeleri [LTI Avantajı - Yönetici Kılavuzu'nda](https://community.brightspace.com/s/article/LTI-Advantage-Administrator-Guide) bulunur.

## <a name="step-1-add-the-new-microsoft-onedrive-lti-app"></a>1. Adım: Yeni Microsoft OneDrive LTI uygulamasını ekleme

### <a name="register-a-new-microsoft-onedrive-lti-app"></a>Yeni bir Microsoft OneDrive LTI uygulaması kaydetme

1. [Microsoft OneDrive LTI Kayıt Portalı'na giriş](https://onedrivelti.microsoft.com/admin) yapın.
1. **Yönetici Onay** düğmesini seçin ve izinleri kabul edin.

   > [!IMPORTANT]
   > **Yönetici Onayı** kabul edilirse, sonraki adım size bir hata verir ve devam etmeden önce bir saat beklemeniz gerekir.

1. **Yeni LTI Kiracısı oluştur** düğmesini seçin.
1. **LTI Tüketici Platformu** listesinde **D2L Brightspace'i** seçin.
1. **D2L Brightspace Temel URL'si** alanına Brightspace temel URL'nizi (gibi) `https://myschool.brightspace.com`girin.
1. **İleri** düğmesini seçin. **LTI 1.3 Uygulamasını Kaydet** sayfası yüklenir. \
   Sonraki adım kümesini tamamlarken bu sayfayı kendi sekmesinde açık tutun. Gerekli değerler sonraki adımlarda oluşturulacaktır.

### <a name="add-microsoft-lti-app-to-brightspace"></a>Microsoft LTI uygulamasını Brightspace'e ekleme

1. Yeni bir tarayıcı sekmesinde, OneDrive LTI uygulamasını eklemek istediğiniz kuruluşun *Yönetici* veya *Süper Yönetici* hesabıyla Brightspace LMS'nizde oturum açın.
1. **Yönetici Araçları'na** erişmek için sağ üst kısımdaki dişli simgesini seçin.
1. **Kuruluşla İlgili** kategorisinde **Genişletilebilirliği Yönet'i** bulun. \
   URL şu örneğe benzer olmalıdır: `https://<yourbrightspacedomain>/d2l/le/ltiadvantage/registrations/home`.
1. Üst kısımdaki **LTI Avantajı** sekmesini ve ardından **Araç Kaydet'i** seçin.
1. **Araç kayıt türü** için **Standart** radyo düğmesini seçin.
1. Uygulama için gibi `Microsoft OneDrive LTI App`bir ad girin.
1. **Etki alanı** alanına girin`https://onedrivelti.microsoft.com`.
1. Diğer gerekli değerleri kopyalamak için Microsoft OneDrive LTI Kayıt Portalı ile tarayıcı sekmesine gidin:
    1. `ToolOIDCLaunchRedirectUri` Değeri **Yeniden Yönlendirme URL'leri** alanına yapıştırın.
       >[!IMPORTANT]
       >Bu **Yeniden Yönlendirme URL'si** değerini sonraki adımlarda kullanacaksınız.
    1. ''OIDCLoginInitiationUri' değerini **OpenID Connect Oturum Açma URL'si** alanına yapıştırın.
    1. `ToolPublicJwksUri` Değeri **Anahtar Kümesi URL'si** alanına yapıştırın.
1. **Uzantılar'ın** altında **Derin Bağlantı** onay kutusunu seçin.
1. Sayfanın en altındaki **Kaydet** düğmesini seçin. \
   Brightspace uygulama kayıt ayrıntıları görüntülenir. Sonraki adım kümesini tamamlarken bu sayfayı kendi sekmesinde açık tutun.

### <a name="add-brightspace-lti-platform-registration-details-to-the-microsoft-onedrive-lti-registration-portal"></a>Brightspace LTI Platformu kayıt ayrıntılarını Microsoft OneDrive LTI Kayıt Portalı'na ekleme

Uygulama Brightspace'e kaydedildikten sonra, Değerleri Brightspace'in kayıt portalından Microsoft'un LTI Kayıt Portalı'na kopyalayacaksınız.

1. Microsoft'un OneDrive LTI Kayıt Portalı sayfasının açık tarayıcı sekmenize geri dönün.
1. Gerekli Brightspace uygulama kayıt ayrıntıları sayfasını kopyalayıp Microsoft'un LTI Kayıt Portalı'na yapıştırın.
    1. Brightspace'in **Veren** değerini Microsoft'un **LTI Veren** alanına yapıştırın.
    2. Brightspace'in **OpenID Connect Kimlik Doğrulama Uç Noktası** değerini Microsoft'un **LTI Yetkilendirme URL'si** alanına yapıştırın.
    3. Brightspace'in **Brightspace Anahtar Kümesi URL** değerini Microsoft'un **LTI Genel Jwks URL** alanına yapıştırın.
    4. Brightspace'in **Brightspace OAuth2 Erişim Belirteci URL'si** değerini Microsoft'un **LTI Erişim Belirteci URL'si** alanına yapıştırın.
    5. Brightspace'in **İstemci Kimliği** değerini Microsoft'un **LTI İstemci Kimliği** alanına yapıştırın.
1. **Sonraki** > **Kaydet'i** seçin. \
   *LTI tüketicinin başarıyla oluşturulduğunu* belirten bir ileti görüntülenir. \
   İsteğe bağlı: Giriş sayfasındaki **LTI Kiracılarını Görüntüle** düğmesini seçerek kayıt ayrıntılarını gözden geçirebilirsiniz.

## <a name="step-2-deploy-the-lti-app-in-users-brightspace-experience"></a>2. Adım: Kullanıcıların Brightspace deneyiminde LTI uygulamasını dağıtma

Microsoft OneDrive LTI ve Brightspace bağlandıktan sonra Kullanıcıların Brightspace deneyiminde OneDrive LTI uygulamasını dağıtmanız gerekir.

1. Brightspace yönetici deneyiminizin yer aldığı sekmede **Yönetici Araçlar** > **Genişletilebilirliği** >  Yönet **LTI Avantajı'na** gidin ve LTI Avantajı uygulamalar listesini görüntüleyin.
1. Önceki adımda oluşturduğunuz LTI Avantajı uygulamasının adını seçin.
1. Sayfanın en altına kaydırın ve **Dağıtımları Görüntüle** bağlantısını seçin. \
   URL şu örneğe benzer olmalıdır: `https://<yourbrightspacedomain>/d2l/le/ltiadvantage/deployments/home`
1. **Yeni Dağıtım'ı** seçin.
1. Uygulamayı, Brightspace uygulama kaydını oluştururken girdiğiniz adla (gibi) `Microsoft OneDrive LTI App`seçin.
1. Bu dağıtım için gibi `Microsoft OneDrive Deployment`bir dağıtım adı girin.
1. **Uzantılar** bölümünde **Derin Bağlama'yı** seçin.
1. **Sınıf Listesi** ve **Anonim** dışındaki tüm güvenlik ayarları onay kutularını seçin.
1. Hiçbir yapılandırma ayarı, değiştirme parametresi veya müşteri parametresi seçmeyin.
1. **Kuruluş Birimleri Ekle'yi** seçin ve yeni LTI uygulamasını kullanmak istediğiniz kuruluş birimlerini seçin.  \
   Şunu seçebilirsiniz:
   - **Kök kuruluş** ve herkesi dahil etmek için **Tüm alt öğeler** seçeneği.
   - Yalnızca bu birimleri içerecek bireysel kuruluş birimleri.
   - **Seçenekler** sütunundaki radyo düğmelerini kullanan **tüm alt** birimler.
1. **Dağıtım Oluştur'u** seçin. \
   Yeni dağıtımınız listede görüntülenir. Bu sekme seçeneğini bırakın ve sonraki adımlarla devam edin.

### <a name="create-links-to-the-onedrive-lti-app-in-brightspace"></a>Brightspace'te OneDrive LTI uygulamasına bağlantılar oluşturma

Bu adım, Kullanıcıların OneDrive dosyalarını eklemeyi seçtiği Brightspace LMS menülerine OneDrive LTI uygulamasını ekler.

1. Brightspace yönetici deneyiminizin yer aldığı sekmede **Yönetici Araçlar** > **Genişletilebilirliği** >  Yönet **LTI Avantajı'na** gidin ve LTI Avantajı uygulamalar listesini görüntüleyin.
1. Oluşturduğunuz LTI Avantajı uygulamasının adını seçin.
1. Sayfanın en altına kaydırın ve **Dağıtımları Görüntüle** bağlantısını seçin.
1. Önceki adımda oluşturduğunuz dağıtımın adını seçin.
1. Sayfanın en altına kaydırın ve **Bağlantıları Görüntüle'yi** seçin.

#### <a name="create-a-deep-linking-quicklink-for-the-app-that-will-appear-in-the-quicklinks-menu"></a>**Hızlı** Bağlantılar menüsünde görünecek uygulama için **Derin Bağlantı Hızlı Bağlantısı** oluşturma

1. **Bağlantıları Görüntüle** sayfasında **Yeni Bağlantı'yı** seçin.
1. Bağlantı için gibi `Microsoft OneDrive`bir ad girin. \
   Bu ad kullanıcılara Brightspace deneyimlerinde görünür.
1. **Yeniden Yönlendirme URL'sini URL** alanına yapıştırın. \
   Bu, Microsoft'un OneDrive LTI Kayıt Portalı'nda listelenen `ToolOIDCLaunchRedirectUri` önceki adımlarda kullanılan **Yeniden Yönlendirme URL'si** ile aynıdır.
1. **Tür'leri** **Derin Bağlantı Hızlı Bağlantısı** olarak ayarlayın.
1. **+Müşteri Parametresi Ekle'yi** seçin ve **Ad** alanı ve `linkSelection` **Değer** alanı için girin`launchType`.
1. **Kaydet ve Kapat** düğmesini seçin.

#### <a name="create-a-deep-linking-insert-stuff-link-for-the-app-that-will-appear-in-the-insert-stuff-menu"></a>Öğe **Ekle** menüsünde görünecek uygulama için **Ayrıntılı Bağlantı Öğeleri Ekle** bağlantısı oluşturma

1. **Bağlantıları Görüntüle** sayfasında **Yeni Bağlantı'yı** seçin.
1. Bağlantı için gibi `Microsoft OneDrive`bir ad girin. \
   Bu ad kullanıcılara Brightspace deneyimlerinde görünür.
1. **Yeniden Yönlendirme URL'sini URL** alanına yapıştırın. \
   Bu, Microsoft'un OneDrive LTI Kayıt Portalı'nda listelenen `ToolOIDCLaunchRedirectUri` önceki adımlarda kullanılan **Yeniden Yönlendirme URL'si** ile aynıdır.
1. **Tür'leri** **Derin Bağlantı Ekleme Öğeleri** olarak ayarlayın.
1. **Kaydet ve Kapat** düğmesini seçin.

## <a name="step-3-turn-on-the-new-onedrive-lti-app-on-the-quicklinks-activity-bar"></a>3. Adım: Hızlı Bağlantılar Etkinlik Çubuğu'nda yeni OneDrive LTI uygulamasını açma

OneDrive LTI uygulaması artık kullanıcılar tarafından kullanılabilir, ancak eski OneDrive uygulamasının artık kapatılması gerekir.

1. Brightspace yönetici portalınızda oturum açın.
1. **Yönetici** >  **Config Değişken Tarayıcısı'na** gidin
1. **d2l.3rdParty.OneDrive.EnableOneDrivePicker** adlı değişkeni bulun ve değeri **kapalı** olarak ayarlayın.

OneDrive LTI uygulamasını hızlı erişim için Brightspace'in etkinlik çubuğuna eklemek için LTI uygulamasının bağlantı kimliğine bir kuruluş birimi **Yapılandırma Değişkeni** ayarlamanız gerekir.

> [!NOTE]
> OneDrive LTI uygulamasının etkinlik çubuğunda görünmesini istediğiniz her kuruluş kimliği (veya üst kuruluş kimliği) için bu adımları tekrarlamanız gerekir.

### <a name="collect-the-link-id"></a>Bağlantı Kimliğini Toplama

1. Brightspace'te Yönetici veya Süper Yönetici olarak oturum açın.
1. Sağ üstteki dişli simgesini seçerek **Yönetici Araçları'na** gidin.
1. **LTI Avantajı Dağıtımları** listesini görüntülemek için **Genişletilebilirliği Yönet'i** seçin.
1. Oluşturduğunuz LTI Avantajı uygulamasının adını seçin.
1. Sayfanın en altına kaydırın ve **Dağıtımları Görüntüle'yi** seçin.
1. Oluşturduğunuz uygulama dağıtımının adını seçin.
1. Sayfayı aşağı kaydırarak sayfanın en altına gelin ve **Bağlantıları Görüntüle'yi** seçin.
1. **Derin Bağlantı Hızlı Bağlantı** türüne sahip bağlantının adını seçin.
1. Farenizi tarayıcınızdaki URL adres çubuğuna taşıyın.
1. URL'deki son `/` rakamdan sonra sayısal basamakları kopyalayın. \
   Örneğin, bağlantı URL'si ise `https://example.desire2learn.com/d2l/le/ltiadvantage/deployments/3bfcc0b7-2fb6-4ffe-b353-95b520d4bae6/links/details/259`sayısal değeri kopyalayın `259` .

### <a name="update-the-config-variables"></a>Yapılandırma Değişkenlerini Güncelleştirme

1. Brightspace yönetici portalında sağ üst dişli simgesini seçerek **Yönetici Araçları'na** gidin.
1. **Yapılandırma Değişkeni Tarayıcısı'nı** seçin.
1. Sol taraftaki **Tüm Değişkenler** menüsünde **3.Party** > **Microsoft** >'a gidin ve **OneDriveLTI'yi** seçin. \
   Değişken adını `3rdparty.microsoft.onedriveLTI.linkId` sağ bölmede görmeniz gerekir.
1. **LinkId değişkeninin** adını seçin.
1. **LinkId yapılandırma** ekranında **Değer Ekle'yi** seçerek bir **Kuruluş Birimi** seçin ve daha önce topladığınız sayısal **Bağlantı Kimliği** değerini yapıştırın.  \
   **Quicklinks Etkinlik Çubuğu'nu** kullanmak istediğiniz her Kuruluş Birimi için bunu tekrarlamanız gerekir.
1. Bu ayarın eklediğiniz alt kuruluş türlerine uygulanmasını sağlamak için, **Basamaklı Kuruluş Birimi Türleri'ni** düzenleyebilir ve ayarların hangi türlerin ve hangi sırayla uygulanacağını seçebilirsiniz.

OneDrive LTI uygulaması artık Brightspace'teki **Mevcut İçerik Ekle**, **Hızlı Bağlantılar** ve **Öğe Ekle** menülerinde gösterilir.

Kullanıcılar OneDrive bulut simgesi yerine genel bir bağlantı simgesi görür. Menüde gösterilen ad, uygulamanın LTI bağlantı ayarlarında sağlanan ad olacaktır.

Bu bağlantılar istenildiği gibi kapatılabilir ve açılabilir ve yapılandırmaya göre belirli Kuruluş ve girintilere hedeflenebilir.

Brightspace'te uygulamaları yapılandırma hakkında daha fazla bilgi için [Brightspace Yardımı](https://documentation.brightspace.com) sayfasını ziyaret edin.

## <a name="common-questions-concerning-the-onedrive-lti-app"></a>OneDrive LTI uygulamasıyla ilgili sık sorulan sorular

### <a name="does-the-new-onedrive-lti-filepicker-support-personal-accounts"></a>Yeni OneDrive LTI FilePicker kişisel hesapları destekliyor mu?

Evet, kişisel hesapların dosyaları karşıya yüklemek için OneDrive'ı açmasına izin verilir. OneDrive LTI Kayıt Portalı'nda uygulamada birden çok makn aya izin vermek veya izin vermemek için bir onay kutusu vardır. İşaretlenirse kişisel hesaplara izin verilir.

### <a name="does-the-filepicker-support-multiple-languages"></a>FilePicker birden çok dili destekliyor mu?

OneDrive LTI FilePicker, LMS'den geçirilen LTI dil ayarı parametresine ve kullanılacak dili belirlemek için tarayıcı ayarını (yedek olarak) (eski isteğe bağlı bir talep olduğundan) arar.
