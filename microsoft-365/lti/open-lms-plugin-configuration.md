---
title: Open LMS için Moodle LMS eklentilerini ayarlama ve yapılandırma
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Moodle LMS eklentilerini ayarlayıp yapılandırarak Open LMS ve Microsoft Teams'i tümleştirmeye hazır olun.
ms.openlocfilehash: b0b02648b570548af993e414bdbe56eddbe21f88
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167307"
---
# <a name="set-up-and-configure-the-moodle-lms-plugins-for-open-lms"></a>Open LMS için Moodle LMS eklentilerini ayarlama ve yapılandırma

Bu makalede, Microsoft Teams'i Open LMS deneyiminizle tümleştirmek için Moodle LMS eklentilerini yüklemeyi ve yapılandırmayı öğreneceksiniz.

## <a name="prerequisites"></a>Önkoşullar

Yüklü bir Open LMS'yi Microsoft Teams ile çalışacak şekilde ayarlamak ve yapılandırmak için:

- [Moodle OpenID Connect'in](https://moodle.org/plugins/auth_oidc) ve [Microsoft 365 tümleştirme](https://moodle.org/plugins/local_o365) eklentilerinin etkin olduğunu doğrulayın.

## <a name="configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>Microsoft 365 eklentileri ve Microsoft hizmetleri arasındaki bağlantıyı yapılandırma

Birlikte çalışabilmeleri için önce Microsoft 365 eklentileri ve Microsoft hizmetleri arasındaki bağlantıyı yapılandırmanız gerekir.

> [!NOTE]
> Tümleştirmeyi yapılandırırken, işlem boyunca bu sayfalara dönmeniz gerekeceği için Microsoft 365 tümleştirme yapılandırma sayfanızı ayrı bir tarayıcı sekmesinde açık tutun.

### <a name="enable-the-openid-connect-authentication-plugin"></a>OpenID Connect kimlik doğrulama eklentisini etkinleştirme

Moodle eklentilerinin Microsoft hizmetleriyle iletişim kurabilmesi için OpenID Connect kimlik doğrulama eklentisinin açılması ve yapılandırılması gerekir.

1. **Site Yönetimi** > **Eklentileri** > **Kimlik Doğrulaması'na** gidin ve **Kimlik Doğrulamasını Yönet'i** seçin.
1. **OpenID Connect** kimlik doğrulama eklentisini bulun ve açmak için *göz simgesini* seçin.
1. **Yetkilendirme** ve **Belirteç** uç noktalarını **doğrulamak için eklenti** ayarları'nı seçin.
    1. Varsayılan değerler şu şekilde olmalıdır:
        1. Yetkilendirme uç noktası: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. Belirteç uç noktası: ``https://login.microsoftonline.com/common/oauth2/token``.
1. **Yeniden Yönlendirme URI'sini** daha sonra kullanmak üzere kaydedin.

> [!NOTE]
> Tüm Open LMS kullanıcılarının kimlik doğrulama yöntemi olarak OpenID Connect kimlik doğrulama eklentisini kullanması gerekmez; Ancak, diğer kimlik doğrulama yöntemlerini kullanıyorlarsa, Teams tümleştirmesindeki Teams sahipliğini ve üyeliğini eşitleme gibi belirli özellikleri kullanabilmeleri için Önce Açık LMS hesaplarının ilgili Microsoft hesaplarına *bağlı* olması gerekir.

### <a name="requisites"></a>Koşullar

PowerShell betiğini kullanarak Open LMS'yi Azure AD uygulama olarak kaydedin. Betik aşağıdaki öğeleri sağlar:

- Microsoft 365 Moodle eklentileri tarafından kullanılan Microsoft 365 kiracınız için yeni bir Azure AD uygulaması.
- Microsoft 365 kiracınız için uygulama, sağlanan uygulama için gerekli yanıt URL'lerini ve izinlerini ayarlar ve ve `Key`döndürür`AppID`.
- Windows olmayan işletim sistemlerinde, Open LMS örneğinizi Azure'a kaydetmek için yalnızca el ile gerçekleştirilen işlemi izlemeniz gerekir. Ayrıntılar için aşağıdaki *Önemli* uyarı bölümüne bakın.

> [!IMPORTANT]
> Open LMS örneğinizi el ile kaydetme hakkında daha fazla bilgi için bkz. [Open LMS örneğinizi uygulama olarak kaydetme](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration).
>
> Uygulamanızı kaydettikten sonra tüm Azure uygulama izinlerinin uygulandığını doğrulayın. Daha fazla bilgi için bkz. [Azure uygulama izinleri](https://docs.moodle.org/400/en/Microsoft_365#Azure_app_permissions).

### <a name="register-application-in-azure-using-powershell"></a>PowerShell kullanarak uygulamayı Azure'a kaydetme

#### <a name="step-1-create-azure-app"></a>1. Adım: Azure uygulaması oluşturma

1. **Site Yönetimi** >  Eklentileri **Yerel eklentiler'e** >  gidin ve **Microsoft 365 Tümleştirmesi'ne** tıklayın. Bu işlem Microsoft 365 Tümleştirme yapılandırma sayfasını açar.

1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Kurulum** sekmesini seçin.

1. **PowerShell Betiğini İndir** düğmesini seçin ve yerel bilgisayarınıza ZIP klasörü olarak kaydedin.

    > [!NOTE]
    > Betiği çalıştırmak, Microsoft 365 kiracısında gerekli yanıt URL'lerini ve izinlerini ayarlayan, gerekli izinleri veren ve `AppID` `Key`döndüren yeni bir Azure AD uygulaması oluşturur.
    >
    > Betik, Windows olmayan işletim sistemlerinde PowerShell'de çalışmaz.

1. Zip dosyasından PowerShell betiğini aşağıdaki gibi hazırlayın:
    1. Dosyayı indirip ayıklayın `Moodle-AzureAD-Powershell.zip` .
    1. Ayıklanan klasörü açın.
    1. Dosyaya sağ tıklayın ve **Özellikler'i**`Moodle-AzureAD-Script.ps1` seçin.
    1. Özellikler penceresi **Genel** sekmesinin altında, pencerenin en altında bulunan **Güvenlik** özniteliğinin yanındaki onay kutusunu seçin`Unblock`.
    1. **Tamam**'ı seçin.
    1. Dizin yolunu ayıklanan klasöre kopyalayın.

1. PowerShell'i yönetici olarak çalıştırın:
    1. Windows'ta başlangıç menüsünü açın.
    1. `PowerShell` yazın.
    1. **Windows PowerShell** sağ tıklayın.
    1. **Yönetici Olarak Çalıştır'ı** seçin.

1. Dizinin yolunun nerede `.../...` olduğunu yazarak `cd .../.../Moodle-AzureAD-Powershell` sıkıştırması açılmış dizine gidin.

1. PowerShell betiğini yürütür:
    1. girin `./Moodle-AzureAD-Script.ps1`.
    1. sorulduğunda, açılır pencerede Microsoft 365 yönetici hesabınızda oturum açın.
    1. İstendiğinde, Azure AD Uygulamasının adını girin. Örneğin, LMS, Moodle veya Moodle eklentilerini açın.
    1. İstendiğinde, Açık LMS sunucunuzun URL'sini girin.
    1. sorulduğunda, OpenID Connect kimlik doğrulama eklentisi yapılandırma sayfasından kopyalanan yanıt URL'sini girin. Bu, Açık LMS sitenizin URL'sini ve `\auth\oidc\`ardından öğesini gösterir.
    1. İşlemdeki bir açılır pencerede Microsoft 365 hesabınızda yeniden oturum açmanız istenebilir. Bu, kuruluşunuz için uygulamaya eklenen izinler için yönetici onayı sağlamaktır.
    1. Betik yürütmeyi tamamladığında, betik tarafından oluşturulan **Uygulama Kimliğini (`AppID`)** ve **Uygulama Anahtarını(`Key`)** kopyalayın ve kaydedin.

#### <a name="step-2-set-azure-app-details-in-openid-connect"></a>2. Adım: OpenID Connect'te Azure uygulama ayrıntılarını ayarlama

1. OpenID Connect kimlik doğrulama eklentisi yapılandırma sayfasına dönün.
1. `AppID` Değeri **Uygulama Kimliği** kutusuna, `Key` değeri **anahtar** kutusuna yapıştırın ve ardından **Değişiklikleri kaydet'i** seçin.

#### <a name="step-3-configure-connection-between-microsoft-plugins-and-microsoft-services"></a>3. Adım: Microsoft eklentileri ile Microsoft hizmetleri arasındaki bağlantıyı yapılandırma

1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Kurulum** sekmesini seçin.
1. **Bağlantı yöntemini seçin bölümünde** **Uygulama erişimi'ni** ve ardından **Değişiklikleri kaydet'i** yeniden seçin.
1. Sayfa yenilendikten sonra, **onay Yönetici ek bilgiler &** başka bir yeni bölüm görebilirsiniz.
    1. **İzin Yönetici Sağla** bağlantısını seçin, Microsoft 365 Genel Yönetici kimlik bilgilerinizi girin ve ardından izinleri vermek için **Kabul Et'i** seçin.
    1. **Azure AD Kiracı** alanının yanında **Algıla** düğmesini seçin.
    1. **OneDrive İş URL'sinin** yanındaki **Algıla** düğmesini seçin.
    1. Alanlar dolduruldıktan sonra **Değişiklikleri kaydet** düğmesini yeniden seçin.
1. Yüklemeyi doğrulamak için **Güncelleştir** düğmesini seçin. Bu aşamada hata bildirilirse, Bu, Microsoft eklentilerinin Microsoft Graph API'leri aracılığıyla Microsoft sunucusuyla iletişim kurabileceği anlamına gelir.

#### <a name="step-4-configure-user-and-course-synchronization"></a>4. Adım: Kullanıcı ve kurs eşitlemesini yapılandırma

1. Open LMS sunucunuzla Azure AD arasında kullanıcıları eşitleyin. Ortamınıza bağlı olarak, bu aşamada farklı seçenekler belirleyebilirsiniz. Başlamak için: 

    1. Microsoft 365 Tümleştirme yapılandırması sayfasında **Eşitleme Ayarları** sekmesini seçin.

    1. **Kullanıcıları Azure AD ile eşitle** ayarında ortamınıza uygulanan onay kutularını seçin. Aşağıdaki seçenekleri belirlemeniz gerekir:  
        ✔ Azure AD'deki kullanıcılar için Açık LMS'de hesaplar oluşturun.
       ✔ Azure AD'daki kullanıcılar için Open LMS'deki tüm hesapları güncelleştirin.

    1. **Kullanıcı Oluşturma Kısıtlaması** bölümünde, Açık LMS ile eşitlenen Azure AD kullanıcıları sınırlamak için bir filtre ayarlayabilirsiniz.

        > [!NOTE]
        > Kullanıcı eşitlemesini etkinleştirmek kesinlikle gerekli değildir; Ancak, Open LMS kullanıcılarını Microsoft 365 hesaplarına bağlamayı çok daha kolay hale getirir.
        >
        > Kullanıcı eşitlemesi, Kullanıcıları zamanlanmış **Azure AD görevle eşitle** çalıştırılarak gerçekleştirilir.

1. **Kurs Eşitleme** bölümünde, mevcut Açık LMS kurslarınızın bazıları veya tümü için Teams'in otomatik olarak oluşturulmasını sağlamak için **Kurs eşitleme özelleştirme** seçeneğini belirleyebilirsiniz.

    > [!NOTE]
    > Kurs eşitleme, **Moodle kurslarını Microsoft Teams'e** eşitle zamanlanmış görevi çalıştırılarak gerçekleştirilir.

1. Değişiklikleri kaydedin.

1. Eşitleme yapılandırmasını doğrulamak için zamanlanmış görevleri ilk kez el ile çalıştırmanız gerekir. **Site yönetimi** > **Sunucu** > **Görevleri** > **Zamanlanmış görevler'e** gidin.

    1. Aşağı kaydırın ve **Kullanıcıları Azure AD ile eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
        1. Bu, kullanıcı eşitleme seçeneklerine göre Azure AD kullanıcıları Open LMS sitenize eşitler.
    1. Ardından **Moodle kurslarını Microsoft Teams ile Eşitle** görevini bulun ve **Şimdi çalıştır'ı** seçin.
        1. Bu görev, eşitleme seçeneğinin açık olduğu tüm Açık LMS kursları için gruplar ve kursta bir **Ekip sahibi** bulunabiliyorsa Teams oluşturur.
        1. Bu görev ayrıca kursa kayıtlı Open LMS kullanıcılarını Teams'e sahip veya üye olarak eşitler.
            1. Ekip **sahibi** , aşağıdaki ölçütlerin tümünü karşılayan açık bir LMS kullanıcısıdır:
                1. bir Microsoft 365 hesabına bağlıdır.
                2. kursa kayıtlıdır.
                3. `local/o365:teamowner` kurs bağlamında yeteneğine sahiptir.
            1. Benzer şekilde, Ekip **üyesi** aşağıdaki ölçütlerin tümünü karşılayan açık bir LMS kullanıcısıdır:
                1. bir Microsoft 365 hesabına bağlıdır.
                2. kursa kayıtlıdır.
                3. `local/o365:teamember` kurs bağlamında yeteneğine sahiptir.
            1. Varsayılan *Öğretmen* rolü özelliğine `local/o365:teamowner` sahiptir ve varsayılan *Öğrenci* rolü de `local/o365:teammember` bu özelliğe sahiptir.

> [!NOTE]
> Zamanlanan görevler, sık çalıştırılacak şekilde yapılandırılması gereken [Moodle Cron](https://docs.moodle.org/400/en/Cron) tarafından tetiklenir. Zamanlanan her görevin varsayılan bir zamanlaması olabilir ve özelleştirilebilir.
>
> - **Kullanıcıları Azure AD ile eşitle** görevinin varsayılan zamanlaması dakikada birdir.
> - **Moodle kurslarını Microsoft Teams'e eşitle** görevinin varsayılan zamanlaması her gün saat 01:00'de Açık LMS sunucusu varsayılan saat dilimindedir.

Eklentiler yüklenip yapılandırıldıktan sonra şunları yapabilirsiniz:

- [Open LMS'ye Teams sınıfları ve toplantıları ekleyin](open-lms-teams-classes-and-meetings.md).
- [Moodle Yardımcısı Botu'nu Azure'a dağıtma](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure).
- [Teams sınıflarına Moodle sekmeleri ekleyin](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app).

## <a name="extra-moodle-plugin-documentation"></a>Ek Moodle eklentisi belgeleri

LMS'yi açma Microsoft 365 tümleştirme kılavuzlarını ve sürüm notlarını gözden geçirmek isterseniz şu kaynaklara bakın:

- [Moodle Docs ile ilgili Microsoft 365 tümleştirme belgeleri](https://docs.moodle.org/400/en/Microsoft_365).
