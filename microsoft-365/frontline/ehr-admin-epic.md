---
title: Teams ile sanal randevular - Epic EHR ile tümleştirme
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ansantam
description: Kuruluşunuzdaki sağlık sağlayıcılarının doğrudan Epic EHR sisteminden Teams'deki hastalarla veya diğer sağlayıcılarla sanal randevular yürütmesini sağlamak için Teams EHR bağlayıcısını tümleştirmeyi öğrenin.
ms.openlocfilehash: 0d3a4818b327171a03506425d1fbd849eeafdd88
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824833"
---
# <a name="virtual-appointments-with-teams---integration-into-epic-ehr"></a>Teams ile sanal randevular - Epic EHR ile tümleştirme

Microsoft Teams Elektronik Sağlık Kaydı (EHR) bağlayıcısı, klinisyenlerin doğrudan Epic EHR sisteminden Microsoft Teams'de sanal hasta randevusu veya başka bir sağlayıcıyla danışma başlatmasını kolaylaştırır. Microsoft 365 bulutu üzerinde oluşturulan Teams, HIPAA, HITECH sertifikası ve daha fazlası ile uyumluluğu destekleyen tek bir merkezdeki sohbet, video, ses ve sağlık araçlarıyla basit, güvenli işbirliği ve iletişim sağlar.

Teams'in iletişim ve işbirliği platformu, klinisyenlerin mümkün olan en iyi bakımı sağlamaya odaklanabilmeleri için parçalanmış sistemlerin dağınıklığından faydalanmalarını kolaylaştırır. Teams EHR bağlayıcısı ile şunları yapabilirsiniz:

- Tümleşik bir klinik iş akışıyla Epic EHR sisteminizden Teams sanal randevularını başlatın.
- Hastaların hasta portalından veya SMS aracılığıyla Teams sanal randevularına katılmasını sağlayın.
- Çok katılımcılı, grup ziyaretleri ve yorumlayıcı hizmetleri gibi diğer senaryoları destekleyin.
- Katılımcılar bağlandığında kaydetmek, bağlantıyı kesmek ve otomatik denetim ile kayıt tutma özelliğini etkinleştirmek için Teams sanal randevuları hakkındaki meta verileri EHR sistemine geri yazın.
- EHR bağlantılı randevular için tüketim verileri raporlarını ve özelleştirilebilir Çağrı Kalitesi bilgilerini görüntüleyin.

Bu makalede Teams EHR bağlayıcısını sağlık kuruluşunuzdaki Epic platformuyla tümleştirecek şekilde ayarlama ve yapılandırma işlemleri açıklanmaktadır. Ayrıca, Epic EHR sisteminden Teams sanal randevuları deneyimine genel bir bakış sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

Başlamadan önce tümleştirmeye hazırlanmak için yapmanız gereken birkaç şey vardır.

### <a name="get-familiar-with-the-integration-process"></a>Tümleştirme işlemini tanıma

Tümleştirme işleminin genelini anlamak için aşağıdaki bilgileri gözden geçirin.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Genel tümleştirme işlemindeki adımları özetleyen görüntü.":::

| &nbsp; |Uygulama erişimi isteme|Uygulama etkinleştirme|Bağlayıcı yapılandırması|Epic yapılandırması|Test|
|--------|---------|---------|---------|---------|---------|
| **Süre** | Yaklaşık 12-24 saat| Yaklaşık 24 saat | Yaklaşık 1-3 gün | Yaklaşık 1-3 gün | &nbsp; |
| **Eylem**| [Teams uygulamasına erişim isteğinde bulunursunuz](#request-access-to-the-teams-app).  | Ortak ve özel anahtar sertifikası oluşturup bunları Epic'e yükleyeceğiz. | EHR bağlayıcı yapılandırma portalında yapılandırma adımlarını tamamlarsınız.  | Epic'te FDI kayıtlarını yapılandırmak için Epic teknik uzmanınızla birlikte çalışıyorsunuz.| Test ortamınızda testi tamamlarsınız. |
| **Sonuç**| Kuruluşunuzu test için yetkilendiriliyoruz. | Epic, ortak anahtar sertifikasını eşitler. | Epic yapılandırması için FDI kayıtları alırsınız. | Yapılandırma tamamlandı. Teste hazır. | Akışların tam doğrulaması ve üretime geçme kararı. |


### <a name="request-access-to-the-teams-app"></a>Teams uygulamasına erişim isteme

Teams uygulamasına erişim istemeniz gerekir.

1. [Epic App Orchard marketinde](https://apporchard.epic.com/Gallery?id=16793) Teams uygulamasını indirme isteğinde bulunabilirsiniz. Bunu yapmak, Epic'ten Microsoft EHR bağlayıcı ekibine bir istek tetikler.
1. İsteğinizi yaptıktan sonra [TeamsForHealthcare@service.microsoft.com'a](mailto:teamsforhealthcare@service.microsoft.com) kuruluşunuzun adı, kiracı kimliği ve Epic teknik kişinizin e-posta adresini içeren bir e-posta gönderin.
1. Microsoft EHR bağlayıcısı ekibi, etkinleştirme onayıyla e-postanıza yanıt verir.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Epic-Microsoft Teams Telehealth Tümleştirme kılavuzunu gözden geçirin

[Epic-Microsoft Teams Telehealth Tümleştirme Kılavuzu'nu](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) Epic teknik uzmanınızla birlikte gözden geçirin. Tüm önkoşulların karşılandığından emin olun.

## <a name="prerequisites"></a>Önkoşullar

- Healthcare için Microsoft Bulut'a etkin bir abonelik veya tek başına Microsoft Teams EHR bağlayıcısı aboneliği teklifi (yalnızca üretim EHR ortamında test ederken uygulanır).
- Epic sürümü Kasım 2018 veya üzeri.
- Kullanıcılar, Teams toplantılarını içeren uygun bir Microsoft 365 veya Office 365 lisansına sahiptir.
- Teams, sağlık kuruluşunuzda benimsenip kullanılır.
- Sistemleriniz Teams için tüm [yazılım ve tarayıcı gereksinimlerini karşılar](/microsoftteams/hardware-requirements-for-the-teams-app) .

> [!IMPORTANT]
> Tümleştirme öncesi adımları tamamladığınızdan ve tümleştirmeye geçmeden önce tüm önkoşulların karşılandığından emin olun.

Tümleştirme adımları kuruluşunuzdaki aşağıdaki kişiler tarafından gerçekleştirilir:

- **Microsoft 365 genel yöneticisi**: Tümleştirmeden sorumlu ana kişi. Yönetici bağlayıcıyı yapılandırabilir, SMS'i etkinleştirir (gerekirse) ve yapılandırmayı onaylayacak Epic müşteri analistini ekler.
- **Epic müşteri analisti**: Kuruluşunuzda Epic'te oturum açma kimlik bilgileri olan bir kişi. Yönetici tarafından girilen yapılandırma ayarlarını onaylar ve yapılandırma kayıtlarını Epic'e sağlar.

Microsoft 365 yöneticisi ve Epic müşteri analisti aynı kişi olabilir.

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR bağlayıcısını ayarlama

Bağlayıcı kurulumu şunları gerektirir:

- [EHR bağlayıcı yapılandırma portalını başlatma](#launch-the-ehr-connector-configuration-portal)
- [Yapılandırma bilgilerini girin](#enter-configuration-information)
- [SMS bildirimlerini etkinleştirme (isteğe bağlı)](#enable-sms-notifications-optional)
- [Yapılandırmayı onaylama veya görüntüleme](#approve-or-view-the-configuration)
- [Yapılandırmayı gözden geçirme ve bitirme](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR bağlayıcı yapılandırma portalını başlatma

Başlamak için Microsoft 365 yöneticiniz [EHR bağlayıcı yapılandırma portalını](https://ehrconnector.teams.microsoft.com) başlatır ve Microsoft 365 kimlik bilgilerini kullanarak oturum açar.

Microsoft 365 yöneticiniz tümleştirmeyi test etmek için tek bir kuruluş veya birden çok kuruluş yapılandırabilir. Yapılandırma portalında test ve üretim URL'sini yapılandırın. Üretime geçmeden önce Epic test ortamından tümleştirmeyi test etmeye özen gösterin.

> [!NOTE]
> Microsoft 365 yöneticiniz ve Epic müşteri analistiniz yapılandırma portalındaki tümleştirme adımlarını tamamlamalıdır. Epic yapılandırma adımları için kuruluşunuza atanan Epic teknik uzmanına başvurun.

### <a name="enter-configuration-information"></a>Yapılandırma bilgilerini girin

Ardından, tümleştirmeyi ayarlamak için Microsoft 365 yöneticiniz aşağıdakileri yapar:

1. Epic teknik uzmanınızdan Hızlı Sağlık Birlikte Çalışabilirlik Kaynakları (FHIR) temel URL'sini ekler ve ortamı belirtir. Kuruluşunuzun gereksinimlerine ve test etmek istediğiniz ortamlara bağlı olarak gerektiği kadar FHIR temel URL'sini yapılandırın.

    - FHIR temel URL'si, sunucu FHIR API uç noktanıza karşılık gelen statik bir adrestir. Örnek URL'si şeklindedir `https://lamnahealthcare.com/fhir/auth/connect-ocurprd-oauth/api/FHDST`.

    - Test ve üretim ortamları için tümleştirmeyi ayarlayabilirsiniz. İlk kurulum için üretim ortamına geçmeden önce bağlayıcıyı bir test ortamından yapılandırmanızı öneririz.

1. Daha sonraki bir adımda yapılandırmayı onaylayacak Olan Epic müşteri analistinin kullanıcı adını ekler.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Eklenen onaylayanı gösteren Yapılandırma sayfasının ekran görüntüsü." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>SMS bildirimlerini etkinleştirme (isteğe bağlı)

> [!NOTE]
> SMS bildirimleri şu anda yalnızca Birleşik Devletler kullanılabilir. Bu özelliği Teams'in gelecek sürümlerinde diğer bölgelerde kullanılabilir hale getirmek için çalışıyoruz ve kullanılabilir olduğunda bu makaleyi güncelleştireceğiz.

Kuruluşunuz Microsoft'un hastalarınız için SMS bildirimlerini yönetmesini istiyorsa bu adımı tamamlayın. SMS bildirimlerini etkinleştirdiğinizde, hastalarınız zamanlanmış randevular için onay ve anımsatıcı iletileri alır.

SMS bildirimlerini etkinleştirmek için Microsoft 365 yöneticiniz aşağıdakileri yapar:

1. SMS bildirimleri sayfasında, aşağıdakiler için her iki onay onay kutusunu da seçin:

    - Microsoft'un kuruluşunuz adına hastalara SMS bildirimleri göndermesine izin verin.
    - Katılımcıların SMS mesajları göndermeye ve almaya onay verdiğinizden emin olduğunuzu onaylayın.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Onay onay kutularını ve telefon numarası oluşturma seçeneğini gösteren SMS bildirimleri sayfasının ekran görüntüsü." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. **Telefon numaralarınız'ın** altında **Yeni telefon numarası oluştur'a** seçerek kuruluşunuz için bir telefon numarası oluşturun. Bunu yapmak, yeni bir telefon numarası isteme ve oluşturma işlemini başlatır. Bu işlemin tamamlanması 2 dakika kadar sürebilir.

    Telefon numarası oluşturulduktan sonra ekranda görüntülenir. Bu numara, hastalarınıza SMS onayları ve anımsatıcılar göndermek için kullanılacaktır. Sayı sağlandı ancak henüz FHIR temel URL'sine bağlı değil. Bunu bir sonraki adımda yapacaksınız.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Oluşturulan telefon numarasının bir örneğini gösteren ekran görüntüsü." lightbox="media/ehr-connector-epic-phone-number.png":::

    **Bitti'yi** ve ardından **İleri'yi** seçin.

1. Telefon numarasını FHIR temel URL'sine bağlamak için **SMS yapılandırması** bölümündeki **Telefon numarası'nın** altında numarayı seçin. Sms bildirimlerini etkinleştirmek istediğiniz her FHIR temel URL'si için bunu yapın.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Telefon numarasını FHIR temel URL'sine bağlamayı gösteren ekran görüntüsü." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Bağlayıcıyı ilk kez yapılandırıyorsanız, önceki adımda girilen FHIR temel URL'sini görürsünüz. Aynı telefon numarası birden çok FHIR temel URL'sine bağlanabilir, bu da hastaların farklı kuruluşlar ve/veya departmanlar için aynı telefon numarasından SMS bildirimleri alacağı anlamına gelir.

1. Hastalarınıza gönderilecek SMS bildirim türlerini ayarlamak için her FHIR temel URL'sinin yanındaki SMS **kurulumu'nu** seçin.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="SMS kurulum ayarlarını gösteren ekran görüntüsü." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **Onay SMS'i**: EHR sisteminde randevu zamanlandığında, güncelleştirildiğinde veya iptal edildiğinde hastalara bildirimler gönderilir.
    - **Anımsatıcı SMS**: Belirttiğiniz zaman aralığına ve randevunun planlanan saatine göre hastalara bildirimler gönderilir.

    **Kaydet**'i seçin.

1. Ortak anahtar sertifikasını karşıya yüklemek için **Sertifikayı karşıya yükle'yi** seçin. Her ortam için Base64 kodlamalı (yalnızca ortak anahtar) .cer sertifikasını karşıya yüklemeniz gerekir.

    SMS bildirimleri göndermek için randevu bilgilerini almak için ortak anahtar sertifikası gereklidir. Sertifika, gelen bilgilerin geçerli bir kaynaktan geldiğini doğrulamak için gereklidir.

    Bağlayıcı SMS anımsatıcıları göndermek için kullanıldığında, randevular Epic'te oluşturulduğunda hastanın telefon numarası Epic tarafından HL7v2 yükünde gönderilir. Bu numaralar, kuruluşunuzun coğrafyasında her randevu için depolanır ve randevu gerçekleşene kadar saklanır. HL7v2 iletilerini yapılandırma hakkında daha fazla bilgi edinmek için [bkz. Epic-Microsoft Teams Telehealth Tümleştirme Kılavuzu](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    **İleri**'yi seçin.

> [!NOTE]
> Microsoft 365 yöneticiniz herhangi bir zamanda SMS ayarlarından herhangi birini güncelleştirebilir. Ayarların değiştirilmesinin SMS hizmetinin durmasına neden olabileceğini unutmayın. SMS raporlarını görüntüleme hakkında daha fazla bilgi için bkz. [Teams EHR bağlayıcısı Sanal Randevular raporu](ehr-connector-report.md).

### <a name="approve-or-view-the-configuration"></a>Yapılandırmayı onaylama veya görüntüleme

Kuruluşunuzda onaylayan olarak eklenen Epic müşteri analisti [EHR bağlayıcısı yapılandırma portalını](https://ehrconnector.teams.microsoft.com) başlatır ve Microsoft 365 kimlik bilgilerini kullanarak oturum açar. Doğrulama başarılı olduktan sonra onaylayandan Epic kuruluşunu doğrulamak için Epic kimlik bilgilerini kullanarak oturum açması istenir.

> [!Note]
> Microsoft 365 yöneticisi ve Epic müşteri analisti aynı kişiyse erişiminizi doğrulamak için Epic'te oturum açmanız gerekir. Epic oturum açma yalnızca FHIR temel URL'nizi doğrulamak için kullanılır. Microsoft bu oturum açma ile kimlik bilgilerini depolamaz veya EHR verilerine erişmez.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Oturum açma ve onaylama seçeneğini gösteren Yapılandırmayı Onayla veya Görüntüle sayfasının ekran görüntüsü." lightbox="media/ehr-connector-epic-login-approve.png":::

Epic'te başarılı bir şekilde oturum açıldıktan sonra Epic müşteri analistinin yapılandırmayı onaylaması **gerekir** . Yapılandırma doğru değilse, Microsoft 365 yöneticiniz yapılandırma portalında oturum açabilir ve ayarları değiştirebilir.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Onayla veya Yapılandırmayı Görüntüle sayfasının Onayla seçeneğini gösteren ekran görüntüsü." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Yapılandırmayı gözden geçirme ve bitirme

Yapılandırma bilgileri Epic yöneticisi tarafından onaylandığında hasta ve sağlayıcı başlatma için tümleştirme kayıtları sunulur. Tümleştirme kayıtları şunlardır:

- Hasta ve sağlayıcı kayıtları
- Doğrudan SMS kaydı
- SMS yapılandırma kaydı
- Cihaz testi yapılandırma kaydı

Cihaz testi için bağlam belirteci hasta tümleştirme kaydında bulunabilir. Epic'te sanal randevu yapılandırmasını tamamlamak için Epic müşteri analistinin bu kayıtları Epic'e sağlaması gerekir. Daha fazla bilgi için bkz. [Epic-Microsoft Teams Telehealth Tümleştirme Kılavuzu](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> Microsoft 365 veya Epic müşteri analisti, gerektiğinde tümleştirme kayıtlarını görüntülemek ve kuruluş yapılandırmasını değiştirmek için yapılandırma portalında oturum açabilir.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Tümleştirme bilgilerini gösteren Gözden Geçir ve Bitir sayfasının ekran görüntüsü." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> Epic müşteri analisti, Microsoft 365 yöneticisi tarafından yapılandırılan her FHIR temel URL'si için onay işlemini tamamlamalıdır.

## <a name="launch-teams-virtual-appointments"></a>Teams sanal randevularını başlatma

EHR bağlayıcısı adımlarını ve Epic yapılandırmasını tamamladıktan sonra, kuruluşunuz Teams ile görüntülü randevuları desteklemeye hazırdır.

### <a name="virtual-appointments-prerequisites"></a>Sanal randevu önkoşulları

- Sistemlerinizin Teams için tüm [yazılım ve tarayıcı gereksinimlerini karşılaması](/microsoftteams/hardware-requirements-for-the-teams-app) gerekir.

- Epic kuruluşu ile Microsoft 365 kuruluşunuz arasındaki tümleştirme kurulumunu tamamladınız.

### <a name="provider-experience"></a>Sağlayıcı deneyimi

Kuruluşunuzdan sağlık sağlayıcıları, Epic sağlayıcı uygulamalarından (Hyperspace, Haiku, Canto) Teams'i kullanarak randevulara katılabilir. **Sanal ziyaret başlat** düğmesi sağlayıcı akışına eklenir.

  ![Hastayla sanal randevu sağlayıcısı deneyimi.](media/ehc-provider-experience-6.png)

Sağlayıcı deneyiminin temel özellikleri:

- Sağlayıcılar, desteklenen tarayıcıları veya Teams uygulamasını kullanarak randevulara katılabilir.

- Sağlayıcılar, bir randevuya ilk kez katılırken Microsoft 365 hesaplarıyla bir kerelik oturum açmalıdır.

- Tek seferlik oturum açma işleminin ardından sağlayıcı doğrudan Teams'deki sanal randevuya alınır. (Sağlayıcının Teams'de oturum açması gerekir).

- Sağlayıcılar belirli bir randevu için bağlanan ve bağlantıyı kesen katılımcıların gerçek zamanlı güncelleştirmelerini görebilir. Sağlayıcılar hastanın bir randevuya ne zaman bağlı olduğunu görebilir.

> [!NOTE]
> Toplantı sohbetine girilen ve tıbbi kayıtların sürekliliği veya saklama amacıyla gerekli olan tüm bilgiler sağlık hizmeti sağlayıcısı tarafından indirilmeli, kopyalanmalı ve not alınmalıdır. Sohbet, yasal bir tıbbi kayıt veya belirlenmiş bir kayıt kümesi oluşturmaz. Sohbetten gelen iletiler, Microsoft Teams yöneticisi tarafından oluşturulan ayarlara göre depolanır.

### <a name="patient-experience"></a>Hasta deneyimi

Bağlayıcı, SMS kısa mesaj, MyChart web ve mobil cihazlardaki bir bağlantı aracılığıyla randevulara katılan hastaları destekler. Randevu sırasında, hastalar Sanal **ziyaret** başlat düğmesini kullanarak veya SMS metin iletisindeki bağlantıya dokunarak MyChart'tan randevuya başlayabilir.

  ![Sanal randevu için hasta deneyimi.](media/ehc-virtual-visit-5.png)

Hasta deneyiminin temel özellikleri:

- Hastalar [, Teams uygulamasını yüklemek zorunda kalmadan masaüstü ve mobil cihazlardaki modern web tarayıcılarından randevulara](browser-join.md) katılabilir.
- Hastalar bir randevuya katılmadan önce cihaz donanımlarını ve bağlantılarını test edebilir.

    :::image type="content" source="media/ehr-admin-epic-device-test.png" alt-text="Cihaz testi özelliklerini gösteren mobil cihaz görüntüleri." lightbox="media/ehr-admin-epic-device-test.png":::
  
    Cihaz testi özellikleri:

  - Hastalar hoparlörlerini, mikrofonlarını, kameralarını ve bağlantılarını test edebilir.
  - Hastalar, yapılandırmalarını tam olarak doğrulamak için bir test çağrısını tamamlayabilir.
  - Cihaz testinin sonuçları EHR sistemine geri gönderilebilir.

- Hastalar tek tıklamayla randevulara katılabilir ve başka bir hesap veya oturum açma gerekmez.

- Hastaların bir Microsoft hesabı oluşturması veya randevu başlatmak için oturum açması gerekmez.

- Hastalar sağlayıcı katılana ve kabul edene kadar bir lobiye yerleştirilir.

- Hastalar randevuya katılmadan önce lobide video ve mikrofonlarını test edebilir.

> [!Note]
> Epic, MyChart, Haiku ve Canto, Epic Systems Corporation'ın ticari markalarıdır.

## <a name="get-insight-into-virtual-appointments-usage"></a>Sanal randevu kullanımı hakkında içgörü alma

Microsoft Teams yönetim merkezindeki [Sanal Ziyaretler kullanım raporu](virtual-visits-usage-report.md) , yöneticilere kuruluşunuzdaki Teams sanal randevuları etkinliğine genel bir bakış sağlar. Rapor, EHR sisteminizden gerçekleştirilen Teams EHR ile tümleşik toplantılar da dahil olmak üzere sanal randevular için ayrıntılı analizler gösterir.

Lobi bekleme süresi ve randevu süresi gibi önemli ölçümleri görüntüleyebilirsiniz. Daha iyi iş sonuçları sunmak üzere sanal randevuları iyileştirmenize yardımcı olmak üzere kullanım eğilimleri hakkında içgörü elde etmek için bu bilgileri kullanın.

### <a name="privacy-and-location-of-data"></a>Verilerin gizliliği ve konumu

TEAMS'in EHR sistemleriyle tümleştirmesi, tümleştirme ve sanal randevu akışları sırasında kullanılan ve depolanan veri miktarını iyileştirir. Çözüm, Teams'in genel gizlilik ve veri yönetimi ilkelerine ve Teams Gizliliği'nde açıklanan yönergelere uyar.

Teams EHR bağlayıcısı, EHR sisteminden tanımlanabilen kişisel verileri veya hastaların veya sağlık sağlayıcılarının sağlık kayıtlarını depolamaz veya aktarmaz. EHR bağlayıcısı tarafından depolanan tek veri, Teams toplantı kurulumu sırasında kullanılan EHR kullanıcısının benzersiz kimliğidir.

EHR kullanıcısının benzersiz kimliği, [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations) bölümünde açıklanan üç coğrafi bölgeden birinde depolanır. Toplantı katılımcıları tarafından Teams'de paylaşılan tüm sohbetler, kayıtlar ve diğer veriler mevcut depolama ilkelerine göre depolanır. Teams'deki verilerin konumu hakkında daha fazla bilgi edinmek için bkz. [Teams'de verilerin konumu](/microsoftteams/location-of-data-in-teams).

## <a name="related-articles"></a>İlgili makaleler

- [Teams Sanal Ziyaretleri kullanım raporu](virtual-visits-usage-report.md)
- [Teams EHR bağlayıcısı Sanal Randevular raporu](ehr-connector-report.md)
- [Sağlık kuruluşları için Teams'i kullanmaya başlama](teams-in-hc.md)
