---
title: Moodle LMS eklentilerini ayarlama ve yapılandırma
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Moodle LMS eklentilerini ayarlayıp yapılandırarak Moodle ve Microsoft Teams'i tümleştirmeye hazır olun.
ms.openlocfilehash: b1188878c8d0af5041bf25bb566dc0707f4e5ad4
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66862567"
---
# <a name="set-up-the-moodle-lms-plugins"></a>Moodle LMS eklentilerini ayarlama

Bu makalede, Moodle LMS eklentilerini Microsoft Teams'i Moodle deneyiminize dahil etmek için yüklemeyi ve yapılandırmayı öğreneceksiniz.

## <a name="prerequisites"></a>Önkoşullar

Microsoft Teams ile çalışmak için yüklü bir Moodle ayarlamak için önkoşullar şunlardır:

* Moodle yöneticisi kimlik bilgileri.
* yönetici kimlik bilgilerini Azure AD.
* Yeni kaynaklar oluşturabileceğiniz bir Azure aboneliği.

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Microsoft 365 Moodle Eklentilerini Yükleme

Microsoft Teams ile Moodle tümleştirmesi, açık kaynak [Microsoft 365 Moodle eklentileri kümesi](https://moodle.org/plugins/browse.php?list=set&id=72) tarafından desteklenir.

### <a name="requisite-applications-and-plugins"></a>Gerekli uygulamalar ve eklentiler

Aşağıdaki öğeleri indirip yükleyin:

1. [Moodle'un güncel kararlı bir sürümü](https://download.moodle.org/releases/latest/).

    > [!IMPORTANT]
    > Mevcut bir Moodle siteniz yoksa [Azure'da Moodle](https://github.com/azure/moodle) deposuna gidin ve bir Moodle örneğini hızla dağıtın ve gereksinimlerinize göre özelleştirin.

1. Moodle [OpenID Connect'i](https://moodle.org/plugins/auth_oidc) ve [Microsoft 365 Tümleştirme](https://moodle.org/plugins/local_o365) eklentilerini indirip yerel bilgisayarınıza kaydedin.

    > [!NOTE]
    > Teams tümleştirmesi için OpenID Connect ve Microsoft 365 Tümleştirme eklentilerini yüklemek gerekir.
    >
    > Ayrıca [, Microsoft 365 Teams Teması](https://moodle.org/plugins/theme_boost_o365teams) eklentisini yüklemenizi öneririz.

### <a name="microsoft-365-moodle-plugins"></a>Microsoft 365 Moodle eklentileri

#### <a name="install-plugins"></a>Eklentileri yükleme

1. Eklentileri indirin, ayıklayın ve karşılık gelen klasörlerine yükleyin.
    * OpenID Connect eklentisini (auth_oidc) **oidc** adlı bir klasöre ayıklayın ve Moodle belge kökünüzün **kimlik doğrulama** klasörüne yükleyin.
    * Microsoft 365 Tümleştirme eklentisini (local_o365) **o365** adlı bir klasöre ayıklayın ve Moodle belge kökünüzün **yerel** klasörüne yükleyin.
1. Moodle sitenizde yönetici olarak oturum açın ve **Site yönetimi'ni** seçin.
1. Yüklenecek yeni eklentilerin algılanması üzerine Moodle sizi yeni eklentileri yükleme sayfasına yönlendirmelidir. Bu olmazsa, **Site yönetimi** sayfasında **Genel** sekmesinde **Bildirimler'i** seçin; bu eylem eklentilerin yüklenmesini tetiklemelidir.
1. Yeni eklentiler yüklendikten sonra Moodle, yüklü eklentilerden gelen tüm yeni yapılandırmaların yer alır. Varsayılan ayarları uygulayarak bu sayfayı güvenle atlayabilirsiniz. Eklentiler aşağıdaki adımlarda yapılandırılacaktır.

## <a name="2-enable-the-openid-connect-authentication-plugin"></a>2. OpenID Connect kimlik doğrulama eklentisini etkinleştirin

Moodle eklentilerinin Microsoft hizmetleriyle iletişim kurabilmesi için OpenID Connect kimlik doğrulama eklentisinin açılması ve yapılandırılması gerekir.

1. **Site Yönetimi** > **Eklentileri** > **Kimlik Doğrulaması'na** gidin ve **Kimlik Doğrulamasını Yönet'i** seçin.
1. **OpenID Connect** kimlik doğrulama eklentisini bulun ve açmak için *göz simgesini* seçin.
1. **Yetkilendirme** ve **Belirteç** uç noktalarını **doğrulamak için eklenti** ayarları'nı seçin.
    1. Varsayılan değerler şu şekilde olmalıdır:
        1. Yetkilendirme uç noktası: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Belirteç uç noktası: ``https://login.microsoftonline.com/common/oauth2/token``.
1. **Yeniden Yönlendirme URI'sini** daha sonra kullanmak üzere kaydedin.

    > [!NOTE]
    > Tüm Moodle kullanıcılarının kimlik doğrulama yöntemi olarak OpenID Connect kimlik doğrulama eklentisine bağlanması gerekmez; Ancak diğer kimlik doğrulama yöntemlerini kullanıyorlarsa, Teams tümleştirmesindeki Teams sahipliğini ve üyeliğini eşitleme gibi belirli özellikleri kullanabilmeleri için Moodle hesaplarının ilgili Microsoft hesaplarına *bağlı* olması gerekir.

## <a name="3-configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>3. Microsoft 365 eklentileri ile Microsoft hizmetleri arasındaki bağlantıyı yapılandırın

Birlikte çalışabilmeleri için önce Microsoft 365 eklentileri ve Microsoft hizmetleri arasındaki bağlantıyı yapılandırmanız gerekir.

> [!NOTE]
> Tümleştirmeyi yapılandırırken, işlem boyunca bu sayfa kümesine dönmeniz gerektiğinden Microsoft 365 Moodle Tümleştirme yapılandırma sayfanızı ayrı bir tarayıcı sekmesinde açık tutun.

### <a name="the-teams-for-moodle-set-up-process"></a>Moodle için Teams kurulum işlemi

1. Azure uygulaması oluşturma
    1. **Site Yönetimi** >  Eklentileri **Yerel eklentiler'e** >  gidin ve **Microsoft 365 Tümleştirmesi'ne** tıklayın. Bu işlem Microsoft 365 Tümleştirme yapılandırma sayfasını açar.

    1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Kurulum** sekmesini seçin.

    1. **PowerShell Betiğini İndir** düğmesini seçin ve yerel bilgisayarınıza ZIP klasörü olarak kaydedin.

        > [!NOTE]
        > Betiği çalıştırmak, Microsoft 365 kiracısında gerekli yanıt URL'lerini ve izinlerini ayarlayan, gerekli izinleri veren ve `AppID` `Key`döndüren yeni bir Azure AD uygulaması oluşturur.
        >
        > PowerShell betiği yalnızca Windows işletim sistemlerinde çalışır.

    1. Zip dosyasından PowerShell betiğini aşağıdaki gibi hazırlayın:
        1. Dosyayı indirip ayıklayın `Moodle-AzureAD-Powershell.zip` .
        1. Ayıklanan klasörü açın.
        1. Dosyaya sağ tıklayın ve **Özellikler'i**`Moodle-AzureAD-Script.ps1` seçin.
        1. Özellikler penceresi **Genel** sekmesinin altında, pencerenin en altında bulunan **Güvenlik** özniteliğinin yanındaki onay kutusunu seçin`Unblock`.
        1. **Tamam**'ı seçin.
        1. Dizin yolunu ayıklanan klasöre kopyalayın.

    1. PowerShell'i yönetici olarak çalıştırın:
        1. Windows'da **Başlat'ı** seçin.
        1. `PowerShell` yazın.
        1. **Windows PowerShell** sağ tıklayın.
        1. **Yönetici Olarak Çalıştır'ı** seçin.

    1. Dizinin yolunun nerede `.../...` olduğunu yazarak `cd .../.../Moodle-AzureAD-Powershell` sıkıştırması açılmış dizine gidin.

    1. PowerShell betiğini yürütür:
        1. girin `./Moodle-AzureAD-Script.ps1`.
        1. sorulduğunda, açılır pencerede Microsoft 365 yönetici hesabınızda oturum açın.
        1. sorulduğunda, Azure AD Uygulamasının adını (örneğin, Moodle veya Moodle eklentileri) girin.
        1. sorulduğunda Moodle sunucunuzun URL'sini girin.
        1. sorulduğunda, OpenID Connect kimlik doğrulama eklentisi yapılandırma sayfasından kopyalanan yanıt URL'sini girin. Bu temelde Moodle sitenizin URL'si ve ardından `\auth\oidc\`.
        1. İşlemdeki bir açılır pencerede Microsoft 365 hesabınızda yeniden oturum açmanız istenebilir. Bu, kuruluşunuz için uygulamaya eklenen izinler için yönetici onayı sağlamaktır.
        1. Betik yürütmeyi tamamladığında, betik tarafından oluşturulan **Uygulama Kimliğini (`AppID`)** ve **Uygulama Anahtarını(`Key`)** kopyalayın ve kaydedin.

1. Moodle'da Azure uygulama ayrıntılarını ayarlama
    1. OpenID Connect kimlik doğrulama eklentisi yapılandırma sayfasına dönün.
    1. `AppID` Değeri **Uygulama Kimliği** kutusuna, `Key` değeri **anahtar** kutusuna yapıştırın ve ardından **Değişiklikleri kaydet'i** seçin.

1. Microsoft eklentileri ile Microsoft hizmetleri arasındaki bağlantıyı yapılandırma
    1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Kurulum** sekmesini seçin.
    1. **Bağlantı yöntemini seçin bölümünde** **Uygulama erişimi'ni** ve ardından **Değişiklikleri kaydet'i** yeniden seçin.
    1. Sayfa yenilendikten sonra, **onay Yönetici ek bilgiler &** başka bir yeni bölüm görebilirsiniz.
        1. **İzin Yönetici Sağla** bağlantısını seçin, Microsoft 365 Genel Yönetici kimlik bilgilerinizi girin ve ardından izinleri vermek için **Kabul Et'i** seçin.
        1. **Azure AD Kiracı** alanının yanında **Algıla** düğmesini seçin.
        1. **OneDrive İş URL'sinin** yanındaki **Algıla** düğmesini seçin.
        1. Alanlar dolduruldıktan sonra **Değişiklikleri kaydet** düğmesini yeniden seçin.

    1. Yüklemeyi doğrulamak için **Güncelleştir** düğmesini seçin. Bu aşamada hata bildirilirse, Bu, Microsoft eklentilerinin Microsoft Graph API'leri aracılığıyla Microsoft sunucusuyla iletişim kurabileceği anlamına gelir.

1. Kullanıcı ve kurs eşitlemesini yapılandırma
    1. Moodle sunucunuzla Azure AD arasında kullanıcıları eşitleyin. Ortamınıza bağlı olarak, bu aşamada farklı seçenekler belirleyebilirsiniz. Başlamak için: 
        1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Eşitleme Ayarları** sekmesini seçin.

        1. **Kullanıcıları Azure AD ile eşitle** ayarında ortamınıza uygulanan onay kutularını seçin. Aşağıdaki seçenekleri belirlemeniz gerekir:  
            ✔ Azure AD'deki kullanıcılar için Moodle'da hesaplar oluşturun.
           ✔ Azure AD'deki kullanıcılar için Moodle'daki tüm hesapları güncelleştirin.

        1. **Kullanıcı Oluşturma Kısıtlaması** bölümünde, Moodle ile eşitlenen Azure AD kullanıcıları sınırlamak için bir filtre ayarlayabilirsiniz.

        > [!NOTE]
        > Kullanıcı eşitlemesini açmak gerekli değildir; ancak Moodle kullanıcılarını Microsoft 365 hesaplarına bağlamayı çok daha kolay hale getirir.
        >
        > Kullanıcı eşitlemesi, Kullanıcıları zamanlanmış **Azure AD görevle eşitle** çalıştırılarak gerçekleştirilir.

    1. **Kurs Eşitleme** bölümünde, mevcut Moodle kurslarınızın bazıları veya tümü için Teams'in otomatik olarak oluşturulmasını açmak için **Kurs eşitleme özelleştirme** seçeneğini belirleyebilirsiniz.

        > [!NOTE]
        > Kurs eşitleme, **Moodle kurslarını Microsoft Teams'e** eşitle zamanlanmış görevi çalıştırılarak gerçekleştirilir.

    1. Değişiklikleri kaydedin.

    1. Eşitleme yapılandırmasını doğrulamak için zamanlanmış görevleri ilk kez el ile çalıştırmanız gerekir. **Site yönetimi** > **Sunucu** > **Görevleri** > **Zamanlanmış görevler'e** gidin.

        1. Aşağı kaydırın ve **Kullanıcıları Azure AD ile eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
            1. Bu, kullanıcı eşitleme seçeneklerine göre Azure AD kullanıcıları Moodle sitenize eşitler.
        1. Ardından **Moodle kurslarını Microsoft Teams ile Eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
            1. Bu görev, eşitleme seçeneği açık durumdayken tüm Moodle kursları için Gruplar oluşturur ve kursta bir **Ekip sahibi** bulunabiliyorsa Teams'i de oluşturur.
            1. Görev ayrıca kursa kayıtlı Moodle kullanıcılarını Teams'e sahip veya üye olarak eşitler.
                1. Ekip **sahibi** ,
                    1. bir Microsoft 365 hesabına bağlı ve
                    2. ve kursuna kayıtlıdır
                    3. `local/o365:teamowner` kurs bağlamında yeteneğine sahiptir.
                1. Benzer şekilde, Ekip **üyesi** bir Moodle kullanıcısıdır ve
                    1. bir Microsoft 365 hesabına bağlı ve
                    2. ve kursuna kayıtlıdır
                    3. `local/o365:teamember` kurs bağlamında yeteneğine sahiptir.
                1. Varsayılan *Öğretmen* rolü özelliğine `local/o365:teamowner` sahiptir ve varsayılan *Öğrenci* rolü de `local/o365:teammember` bu özelliğe sahiptir.

    > [!NOTE]
    > Zamanlanan görevler, sık çalıştırılacak şekilde yapılandırılması gereken [Moodle Cron](https://docs.moodle.org/400/en/Cron) tarafından tetiklenir. Zamanlanan her görevin özelleştirilebilen varsayılan bir zamanlaması olabilir.
    >
    > * **Kullanıcıları Azure AD ile eşitle** görevinin varsayılan zamanlaması dakikada birdir.
    > * **Moodle kurslarını Microsoft Teams'e eşitle** görevinin varsayılan zamanlaması, Moodle sunucusu varsayılan saat diliminde her gün saat 01:00'dedir.

Eklentiler yüklenip yapılandırıldıktan sonra şunları yapabilirsiniz:

* [Moodle Yardımcısı Botu'nu Azure'a dağıtma](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
* [Teams sınıflarına Moodle sekmeleri ekleyin](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
* [Teams sınıflarını ve toplantılarını Moodle LMS'ye ekleyin](teams-classes-meetings-with-moodle.md).

## <a name="extra-moodle-plugin-documentation"></a>Ek Moodle eklentisi belgeleri

Moodle'ın Microsoft 365 tümleştirme kılavuzlarını ve sürüm notlarını gözden geçirmek isterseniz şu kaynaklara bakın:

* [Moodle Docs ile ilgili Microsoft 365 tümleştirme belgeleri](https://docs.moodle.org/400/en/Microsoft_365).
