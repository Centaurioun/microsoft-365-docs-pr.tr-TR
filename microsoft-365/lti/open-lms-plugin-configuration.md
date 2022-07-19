---
title: Open LMS için Moodle eklentisini ayarlama ve yapılandırma
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
description: Moodle eklentisini ayarlayıp yapılandırarak One LMS ve Microsoft Teams'i tümleştirmeye hazır olun.
ms.openlocfilehash: e59d9298d61060f4d898e773cc5800d32e86bebf
ms.sourcegitcommit: f181e110cdb983788a86f30d5bb018e53c83e64d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66861901"
---
# <a name="set-up-and-configure-the-moodle-plugin"></a>Moodle eklentisini ayarlama ve yapılandırma

Bu makalede, Moodle eklentisini Microsoft Teams'i Açık LMS deneyiminizle bir araya getirmek için yüklemeyi ve yapılandırmayı öğreneceksiniz.

## <a name="prerequisites"></a>Önkoşullar

Moodle eklentisini yüklemek için önkoşullar şunlardır:

* Moodle yöneticisi kimlik bilgileri.
* Microsoft Azure Active Directory (Azure AD) yönetici kimlik bilgileri.
* Yeni kaynaklar oluşturabileceğiniz bir Azure aboneliği.

## <a name="1-install-the-microsoft-365-moodle-plugin"></a>1. Microsoft 365 Moodle Eklentisini Yükleyin

Microsoft Teams'de açık LMS tümleştirmesi, açık kaynak [Microsoft 365 Moodle eklenti kümesi](https://moodle.org/plugins/browse.php?list=set&id=72) tarafından desteklenir.

### <a name="requisite-applications-and-plugins"></a>Gerekli uygulamalar ve eklentiler

Microsoft 365 Moodle eklentisi yüklemesine devam etmeden önce aşağıdaki öğeleri yükleyin ve indirin:

1. [Moodle'un güncel kararlı bir sürümü](https://download.moodle.org/releases/latest/).
1. Moodle [OpenID Connect'i](https://moodle.org/plugins/auth_oidc) ve [Microsoft 365 Tümleştirme](https://moodle.org/plugins/local_o365) eklentilerini indirip yerel bilgisayarınıza kaydedin.

    > [!NOTE]
    > Teams tümleştirmesi için OpenID Connect ve Microsoft 365 Tümleştirme eklentilerini yüklemek gerekir.
    >
    > [Microsoft 365 Teams Teması](https://moodle.org/plugins/theme_boost_o365teams) eklentisi önerilir.

### <a name="microsoft-365-moodle-plugins"></a>Microsoft 365 Moodle eklentileri

#### <a name="install-plugins"></a>Eklentileri yükleme

1. Eklentileri indirin, ayıklayın ve karşılık gelen klasörlerine yükleyin. Örneğin, OpenID Connect eklentisini (auth_oidc) **oidc** adlı bir klasöre ayıklayın ve Moodle belge kökünüzün **kimlik doğrulama** klasörüne yükleyin.
2. Moodle sitenizde yönetici olarak oturum açın ve **Site yönetimi'ni** seçin.
3. Yüklenecek yeni eklentilerin algılanması üzerine Moodle sizi yeni eklentileri yükleme sayfasına yönlendirmelidir. Bu olmazsa, **Site yönetimi** sayfasında **Genel** sekmesinde **Bildirimler'i** seçin çünkü bu, eklentilerin yüklenmesini tetiklemelidir.

    > [!IMPORTANT]
    >
    > * Süreç boyunca bu sayfa kümesine dönmeniz gerektiğinden, Microsoft 365 Moodle Eklentileri yapılandırma sayfanızı ayrı bir tarayıcı sekmesinde açık tutun.  
    >
    > * Mevcut bir Moodle siteniz yoksa [Azure'da Moodle](https://github.com/azure/moodle) deposuna gidin ve bir Moodle örneğini hızla dağıtın ve gereksinimlerinize göre özelleştirin.

#### <a name="enable-the-openid-connect-authentication-plugin"></a>OpenID Connect kimlik doğrulama eklentisini etkinleştirme

1. **Site Yönetimi** > **Eklentileri** > **Kimlik Doğrulaması'na** gidin ve **Kimlik Doğrulamasını Yönet'i** seçin.
1. **OpenID Connect** kimlik doğrulama eklentisini bulun ve etkinleştirmek için *göz simgesini* seçin.
1. **Yetkilendirme** ve **Belirteç** uç noktalarını **doğrulamak için eklenti** ayarları'nı seçin.
    1. Varsayılan değerler şu şekilde olmalıdır:
        1. Yetkilendirme uç noktası: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Belirteç uç noktası: ``https://login.microsoftonline.com/common/oauth2/token``.
1. **Yeniden Yönlendirme URI'sini** daha sonra kullanmak üzere kaydedin.

## <a name="2-configure-the-connection-between-the-microsoft-365-plugins-and-azure-ad"></a>2. Microsoft 365 eklentileri ile Azure AD arasındaki bağlantıyı yapılandırın

Microsoft 365 eklentileri ile Azure AD arasındaki bağlantıyı yapılandırmanız gerekir.

### <a name="requisites"></a>Koşullar

PowerShell betiğini kullanarak Moodle'ı Azure AD uygulama olarak kaydedin. Betik aşağıdaki öğeleri sağlar:

* Microsoft 365 Moodle Eklentileri tarafından kullanılan Microsoft 365 kiracınız için yeni bir Azure AD uygulaması.
* Microsoft 365 kiracınız için uygulama, sağlanan uygulama için gerekli yanıt URL'lerini ve izinlerini ayarlar ve ve `Key`döndürür`AppID`.

Moodle sunucu sitenizi Azure AD ile yapılandırmak için Oluşturulan `AppID` ve `Key` Microsoft 365 Moodle Eklentileri kurulum sayfanızda kullanın.

> [!IMPORTANT]
> Moodle örneğinizi el ile kaydetme hakkında daha fazla bilgi için bkz. [Moodle örneğinizi uygulama olarak kaydetme](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration).

### <a name="teams-for-open-lms-setup-process"></a>Açık LMS için Teams kurulum işlemi

1. Microsoft 365 Tümleştirme eklentileri sayfasında **Kurulum** sekmesini seçin.

1. **PowerShell Betiğini İndir** düğmesini seçin ve yerel bilgisayarınıza ZIP klasörü olarak kaydedin.

1. Zip dosyasından PowerShell betiğini aşağıdaki gibi hazırlayın:

    1. Dosyayı indirip ayıklayın `Moodle-AzureAD-Powershell.zip` .
    1. Ayıklanan klasörü açın.
    1. Dosyaya sağ tıklayın ve **Özellikler'i**`Moodle-AzureAD-Script.ps1` seçin.
    1. Özellikler penceresi **Genel** sekmesinin altında, pencerenin en altında bulunan **Güvenlik** özniteliğinin yanındaki onay kutusunu seçin`Unblock`.
    1. **Tamam**'ı seçin.
    1. Dizin yolunu ayıklanan klasöre kopyalayın.

1. PowerShell'i yönetici olarak çalıştırın:

    1. Başlat'ı seçin.
    1. PowerShell yazın.
    1. **Windows PowerShell** sağ tıklayın.
    1. **Yönetici Olarak Çalıştır'ı** seçin.

1. Dizinin yolunun nerede `.../...` olduğunu yazarak `cd .../.../Moodle-AzureAD-Powershell` sıkıştırması açılmış dizine gidin.

1. PowerShell betiğini yürütür:

    1. girin `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    1. girin `./Moodle-AzureAD-Script.ps1`.
    1. Açılır pencerede Microsoft 365 yönetici hesabınızda oturum açın.
    1. Moodle veya Moodle eklentileri gibi Azure AD Uygulamasının adını girin.
    1. Moodle sunucunuzun URL'sini girin.
    1. Betik tarafından oluşturulan **Uygulama Kimliğini (`AppID`)** ve **Uygulama Anahtarını(`Key`)** kopyalayın ve kaydedin.

1. Eklenti yönetim sayfası olan **Site yönetimi** > **Eklentileri** > **Kimlik Doğrulaması** > **OpenID Connect'e** dönün.

1. `AppID` Değeri **Uygulama Kimliği** kutusuna, `Key` değeri **anahtar** kutusuna yapıştırın ve ardından **Değişiklikleri kaydet'i** seçin.

1. **Site yönetimi** >  Eklentileri **Yerel eklentiler'e** >  gidin ve **Microsoft 365 Tümleştirme'yi** seçin.

1. **Bağlantı yöntemini seçin bölümünde** **Uygulama erişimi'ni** ve ardından **Değişiklikleri kaydet'i** yeniden seçin.

1. Sayfa yenilendikten sonra, **onay Yönetici ek bilgiler &** başka bir yeni bölüm görebilirsiniz.
    1. **İzin Yönetici Sağla** bağlantısını seçin, Microsoft 365 Genel Yönetici kimlik bilgilerinizi girin ve ardından izinleri vermek için **Kabul Et'i** seçin.
    1. **Azure AD Kiracı** alanının yanında **Algıla** düğmesini seçin.
    1. **OneDrive İş URL'sinin** yanındaki **Algıla** düğmesini seçin.
    1. Alanlar dolduruldıktan sonra **Değişiklikleri kaydet** düğmesini yeniden seçin.

1. Yüklemeyi doğrulamak için **Güncelleştir** düğmesini ve ardından **Değişiklikleri kaydet'i** seçin.

1. Moodle sunucunuzla Azure AD arasında kullanıcıları eşitleyin. Ortamınıza bağlı olarak, bu aşamada farklı seçenekler belirleyebilirsiniz. Başlamak için: 
    1. **Eşitleme Ayarları sekmesine** geçin.

    1. **Kullanıcıları Azure AD ile eşitle** bölümünde ortamınıza uygulanan onay kutularını seçin. Aşağıdaki seçenekleri belirlemeniz gerekir:  

        ✔ Azure AD'deki kullanıcılar için Açık LMS'de hesaplar oluşturun.

        ✔ Azure AD'daki kullanıcılar için Open LMS'deki tüm hesapları güncelleştirin.

    1. **Kullanıcı Oluşturma Kısıtlaması** bölümünde, Açık LMS ile eşitlenen Azure AD kullanıcıları sınırlamak için bir filtre ayarlayabilirsiniz.
    1. **Kurs Eşitleme** bölümünde, Mevcut Açık LMS kurslarınızın bazıları veya tümü için Gruplar ve Teams'in otomatik olarak oluşturulmasını sağlamak için **Kurs eşitleme özelleştirme** seçeneğini belirleyebilirsiniz.

1. [Cron](https://docs.moodle.org/400/en/Cron) görevlerini doğrulamak ve bunları ilk kez el ile çalıştırmak için **Site yönetimi** > **Sunucu** > **Görevleri** > **Zamanlanmış görevler'e** gidin.

    1. Aşağı kaydırın ve **Kullanıcıları Azure AD ile eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
        1. Bu işlem, Azure AD kullanıcıyı Açık LMS sitenizle eşitler.
    1. Ardından **Moodle kurslarını Microsoft Teams ile Eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
        1. Bu görev, bir sahip bulunursa gruplar ve Teams oluşturur.
        1. Kullanıcının `local/o365:teamowner` kurs bağlamında yeteneği varsa, kullanıcı bir ekip sahibidir. Kullanıcının `local/o365:teammember` kurs bağlamında yeteneği varsa, kullanıcı bir ekip üyesidir.  
        1. Varsayılan *Öğretmen* rolü özelliğine `local/o365:teamowner` sahiptir ve varsayılan *Öğrenci* rolü de `local/o365:teammember` bu özelliğe sahiptir.

    > [!NOTE]
    > Moodle [Cron](https://docs.moodle.org/400/en/Scheduled_tasks) görev zamanlamasına göre çalışır. Varsayılan zamanlama, sunucunuzun yerel saat diliminde günde bir kez saat 01:00'dir. Ancak, her şeyi eşitlenmiş durumda tutmak için cron daha sık çalıştırılmalıdır.

1. **Site yönetimi** > **Eklentileri****Yerel eklentiler** >  > **Microsoft 365 Tümleştirme** > **Ekipleri Ayarları** sekmesine gidin.

1. Teams tümleştirmesinin çalışması için gerekli tüm yapılandırmaları güncelleştirecek **Olan Moodle ayarlarını denetle** düğmesini seçin.

Eklentiler yüklenip yapılandırıldıktan sonra şunları yapabilirsiniz:

* [Moodle Yardımcısı Botu'nu Azure'a dağıtma](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
* [Teams sınıflarına Moodle sekmeleri ekleyin](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).
* [Open LMS'ye Teams sınıfları ve toplantıları ekleyin](open-lms-teams-classes-and-meetings.md).

## <a name="extra-moodle-plugin-documentation"></a>Ek Moodle eklentisi belgeleri

LMS'yi açma Microsoft 365 tümleştirme kılavuzlarını ve sürüm notlarını gözden geçirmek isterseniz şu kaynaklara bakın:

* [Moodle Docs ile ilgili Microsoft 365 tümleştirme belgeleri](https://docs.moodle.org/400/en/Microsoft_365).
