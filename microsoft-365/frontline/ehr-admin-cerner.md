---
title: Teams ile sanal randevular - Cerner EHR ile tümleştirme
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
description: Kuruluşunuzdaki sağlık sağlayıcılarının doğrudan Cerner EHR sisteminden Teams'deki hastalarla veya diğer sağlayıcılarla sanal randevular yürütmesini sağlamak için Teams EHR bağlayıcısını tümleştirmeyi öğrenin.
ms.openlocfilehash: 856447ac9036be5a707788e333892aba106800c7
ms.sourcegitcommit: 0c8934129b5ed147fb873fc3f4d201042c313571
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67333730"
---
# <a name="virtual-appointments-with-teams---integration-into-cerner-ehr"></a>Teams ile sanal randevular - Cerner EHR ile tümleştirme

Microsoft Teams Elektronik Sağlık Kaydı (EHR) bağlayıcısı, klinisyenlerin doğrudan Cerner EHR sisteminden bir sanal hasta randevusu başlatmasını veya Microsoft Teams'deki başka bir sağlayıcıya danışmasını kolaylaştırır. Microsoft 365 bulutu üzerinde oluşturulan Teams, HIPAA, HITECH sertifikası ve daha fazlası ile uyumluluğu destekleyen tek bir merkezdeki sohbet, video, ses ve sağlık araçlarıyla basit, güvenli işbirliği ve iletişim sağlar.

Teams'in iletişim ve işbirliği platformu, klinisyenlerin mümkün olan en iyi bakımı sağlamaya odaklanabilmeleri için parçalanmış sistemlerin dağınıklığından faydalanmalarını kolaylaştırır. Teams EHR bağlayıcısı ile şunları yapabilirsiniz:

- Tümleşik bir klinik iş akışı ile Cerner EHR sisteminizden Teams sanal randevuları gerçekleştirin.
- Hastaların e-posta veya SMS bildirimlerinden Teams sanal randevularına katılmasını sağlayın.
- EHR bağlantılı randevular için tüketim verileri raporlarını ve özelleştirilebilir Çağrı Kalitesi bilgilerini görüntüleyin.

Bu makalede, Teams EHR bağlayıcısının Cerner platformuyla tümleştirilmesi için nasıl ayarlanacağı ve yapılandırıldığı açıklanır. Ayrıca, Cerner EHR sisteminden Teams sanal randevuları deneyimine genel bir bakış sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Tümleştirmeyi etkinleştirmeden önce Cerner temsilcinizle konuştuğunuzdan ve Cerner tümleştirme kılavuzunuzu gözden geçirdiğinizden emin olun.

### <a name="prerequisites"></a>Önkoşullar

Teams EHR bağlayıcısını sağlık kuruluşunuzla tümleştirmeden önce aşağıdakilere sahip olmanız gerekir:

- Healthcare için Microsoft Bulut'a etkin bir abonelik veya Microsoft Teams EHR bağlayıcısı tek başına aboneliği teklifi.
- Kullanıcılar, Teams toplantılarını içeren uygun bir Microsoft 365 veya Office 365 lisansına sahiptir.
- Teams, sağlık kuruluşunuzda benimsenip kullanılır.
- Kuruluşunuzda [Teams yönetim merkezine](https://admin.teams.microsoft.com) erişimi olan bir Microsoft 365 genel yöneticisi olan bir kişi tanımladı.
- Sistemleriniz Teams için tüm [yazılım ve tarayıcı gereksinimlerini karşılar](/microsoftteams/hardware-requirements-for-the-teams-app) .
- Cerner sürümü Kasım 2018 veya üzeri

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR bağlayıcısını ayarlama

Bağlayıcı kurulumu şunları gerektirir:

- [EHR bağlayıcı yapılandırma portalını başlatma](#launch-the-ehr-connector-configuration-portal)
- [Yapılandırma bilgilerini girin](#enter-configuration-information)
- [SMS bildirimlerini etkinleştirme (isteğe bağlı)](#enable-sms-notifications-optional)
- [Yapılandırmayı gözden geçirme ve bitirme](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Bu adımların kuruluşunuzdaki Microsoft 365 genel yöneticisi tarafından tamamlanması gerekir.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR bağlayıcı yapılandırma portalını başlatma

Başlamak için Microsoft 365 yöneticiniz [EHR bağlayıcı yapılandırma portalını](https://ehrconnector.teams.microsoft.com) başlatır ve Microsoft kimlik bilgilerini kullanarak oturum açar.

Microsoft 365 yöneticiniz tümleştirmeyi test etmek için tek bir departman veya birden çok bölüm yapılandırabilir. Yapılandırma portalında test ve üretim URL'sini yapılandırın. Üretim ortamına geçmeden önce Cerner test ortamından tümleştirmeyi test etmeye özen gösterin.

### <a name="enter-configuration-information"></a>Yapılandırma bilgilerini girin

Ardından, tümleştirmeyi ayarlamak için Microsoft 365 yöneticiniz Cerner'dan Hızlı Sistem Durumu Birlikte Çalışabilirlik Kaynakları (FHIR) temel URL'sini ekler ve ortamı belirtir. Kuruluşunuzun gereksinimlerine ve test etmek istediğiniz ortamlara bağlı olarak gerektiği kadar FHIR temel URL'sini yapılandırın.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Teams EHR bağlayıcı yapılandırma portalının Yapılandırma bilgileri sayfasının ekran görüntüsü." lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR temel URL'si, sunucu FHIR API uç noktanıza karşılık gelen statik bir adrestir. Örnek URL'si şeklindedir `https://lamnahealthcare.com/fhir/auth/connect-ocurprd-oauth/api/FHDST`.

- Test ve üretim ortamları için tümleştirmeyi ayarlayabilirsiniz. İlk kurulum için üretim ortamına geçmeden önce bağlayıcıyı bir test ortamından yapılandırmanızı öneririz.

FHIR temel URL'si doğrulandıktan ve ortam seçildikten sonra **Bitti'yi** seçin. Ardından, gerektiğinde diğer ortamlar için daha fazla FHIR temel URL'sini ekleyin.

Sonraki adıma geçmek için **İleri'yi** seçin.

### <a name="enable-sms-notifications-optional"></a>SMS bildirimlerini etkinleştirme (isteğe bağlı)

Kuruluşunuz Microsoft'un hastalarınız için SMS bildirimlerini yönetmesini istiyorsa bu adımı tamamlayın. SMS bildirimlerini etkinleştirdiğinizde, hastalarınız zamanlanmış randevular için onay ve anımsatıcı iletileri alır.

SMS bildirimlerini etkinleştirmek için Microsoft 365 yöneticiniz aşağıdakileri yapar:

1. SMS bildirimleri sayfasında, aşağıdakiler için her iki onay onay kutusunu da seçin:

    - Microsoft'un kuruluşunuz adına hastalara SMS bildirimleri göndermesine izin verin.
    - Katılımcıların SMS mesajları göndermeye ve almaya onay verdiğinizden emin olduğunuzu onaylayın.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Onay onay kutularını ve telefon numarası oluşturma seçeneğini gösteren SMS bildirimleri sayfasının ekran görüntüsü." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. **Telefon numaralarınız'ın** altında **Yeni telefon numarası oluştur'a** seçerek kuruluşunuz için bir telefon numarası oluşturun. Bunu yapmak, yeni bir telefon numarası isteme ve oluşturma işlemini başlatır. Bu işlemin tamamlanması 2 dakika kadar sürebilir.

    Telefon numarası oluşturulduktan sonra ekranda görüntülenir. Bu numara, hastalarınıza SMS onayları ve anımsatıcılar göndermek için kullanılacaktır. Sayı sağlandı ancak henüz FHIR temel URL'sine bağlı değil. Bunu bir sonraki adımda yapacaksınız.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Oluşturulan telefon numarasının bir örneğini gösteren ekran görüntüsü." lightbox="media/ehr-admin-cerner-phone-number.png":::

    **Bitti'yi** ve ardından **İleri'yi** seçin.

1. Telefon numarasını FHIR temel URL'sine bağlamak için **SMS yapılandırması** bölümündeki **Telefon numarası'nın** altında numarayı seçin. Sms bildirimlerini etkinleştirmek istediğiniz her FHIR temel URL'si için bunu yapın.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Telefon numarasını FHIR temel URL'sine bağlamayı gösteren ekran görüntüsü." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Bağlayıcıyı ilk kez yapılandırıyorsanız, önceki adımda girilen FHIR temel URL'sini görürsünüz. Aynı telefon numarası birden çok FHIR temel URL'sine bağlanabilir, bu da hastaların farklı kuruluşlar ve/veya departmanlar için aynı telefon numarasından SMS bildirimleri alacağı anlamına gelir.

     **İleri**'yi seçin.

### <a name="review-and-finish-the-configuration"></a>Yapılandırmayı gözden geçirme ve bitirme

Hasta ve sağlayıcı lansmanı için tümleştirme kayıtları sunulur. Bu kayıtlar Cerner'da sanal randevu yapılandırmasını tamamlamak için gereklidir. Daha fazla bilgi için bkz. Teams Telehealth Tümleştirme kılavuzu Cerner-Microsoft.

> [!NOTE]
> Microsoft 365 yöneticiniz, tümleştirme kayıtlarını görüntülemek ve gerekirse yapılandırma ayarlarını değiştirmek için herhangi bir zamanda yapılandırma portalında oturum açabilir.

## <a name="launch-teams-virtual-appointments"></a>Teams sanal randevularını başlatma

EHR bağlayıcısı adımlarını ve Cerner yapılandırma adımlarını tamamladıktan sonra, kuruluşunuz Teams ile görüntülü randevuları desteklemeye hazırdır.

### <a name="virtual-appointments-prerequisites"></a>Sanal randevu önkoşulları

- Sistemlerinizin Teams için tüm [yazılım ve tarayıcı gereksinimlerini karşılaması](/microsoftteams/hardware-requirements-for-the-teams-app) gerekir.
- Cerner kuruluşu ile Microsoft 365 kuruluşunuz arasındaki tümleştirme kurulumunu tamamladınız.

### <a name="provider-experience"></a>Sağlayıcı deneyimi

Kuruluşunuzdaki sağlık sağlayıcıları, PowerChart portalından Teams'i kullanarak randevulara katılabilir. Sağlayıcının Teams seçeneğinin kullanılabilir olduğu hasta panosuna gitmeniz gerekir.

Buradan sağlayıcı randevu bilgilerini görüntüleyebilir, randevulara katılabilir ve toplantı bağlantısını gönderebilir. Tek seferlik oturum açma işleminin ardından sağlayıcı doğrudan Teams'deki sanal randevuya alınır.

Sağlayıcı deneyiminin temel özellikleri:

- Sağlayıcılar, desteklenen tarayıcıları veya Teams uygulamasını kullanarak randevulara katılabilir.
- Sağlayıcılar ekran paylaşımı, özel arka plan ve kayıt dahil olmak üzere desteklenen tüm Teams toplantı özelliklerini kullanabilir.
- Sağlayıcılar, PowerChart'ta belirli bir randevu için randevuya bağlanan hastaların gerçek zamanlı güncelleştirmelerini görebilir.
- Sağlayıcı bilgileri randevu sırasında hastalar tarafından görülemez.

> [!NOTE]
> Toplantı sohbetine girilen ve tıbbi kayıtların sürekliliği veya saklama amacıyla gerekli olan tüm bilgiler sağlık hizmeti sağlayıcısı tarafından indirilmeli, kopyalanmalı ve not alınmalıdır. Sohbet, yasal bir tıbbi kayıt veya belirlenmiş bir kayıt kümesi oluşturmaz. Sohbetten gelen iletiler, Microsoft Teams yöneticisi tarafından oluşturulan ayarlara göre depolanır.

### <a name="patient-experience"></a>Hasta deneyimi

Bağlayıcı, SMS metin iletisindeki bir bağlantı aracılığıyla randevulara katılan hastaları destekler. Randevu sırasında, hastalar SMS kısa mesajındaki bağlantıya dokunarak randevu başlatabilir.

Hasta deneyiminin temel özellikleri

- Hastalar [, Teams uygulamasını yüklemek zorunda kalmadan masaüstü ve mobil cihazlardaki modern web tarayıcılarından randevulara](browser-join.md) katılabilir.
- Hastalar tek tıklamayla randevulara katılabilir ve başka bir hesap veya oturum açma gerekmez.
- Hastaların bir Microsoft hesabı oluşturması veya ziyaret başlatmak için oturum açması gerekmez.
- Hastalar sağlayıcı katılana ve kabul edene kadar bir lobiye yerleştirilir.
- Hastalar randevuya katılmadan önce lobide video ve mikrofonlarını test edebilir.

## <a name="get-insight-into-virtual-appointments-usage"></a>Sanal randevu kullanımı hakkında içgörü alma

Microsoft Teams yönetim merkezindeki [Sanal Ziyaretler kullanım raporu](virtual-visits-usage-report.md) , yöneticilere kuruluşunuzdaki Teams sanal randevuları etkinliğine genel bir bakış sağlar. Rapor, EHR sisteminizden gerçekleştirilen Teams EHR ile tümleşik toplantılar da dahil olmak üzere sanal randevular için ayrıntılı analizler gösterir.

Lobi bekleme süresi ve randevu süresi gibi önemli ölçümleri görüntüleyebilirsiniz. Daha iyi iş sonuçları sunmak üzere sanal randevuları iyileştirmenize yardımcı olmak üzere kullanım eğilimleri hakkında içgörü elde etmek için bu bilgileri kullanın.

## <a name="privacy-and-location-of-data"></a>Verilerin gizliliği ve konumu

TEAMS'in EHR sistemleriyle tümleştirmesi, tümleştirme ve sanal randevu akışları sırasında kullanılan ve depolanan veri miktarını iyileştirir. Çözüm, Teams'in genel gizlilik ve veri yönetimi ilkelerine ve Teams Gizliliği'nde açıklanan yönergelere uyar.

Teams EHR bağlayıcısı, EHR sisteminden tanımlanabilen kişisel verileri veya hastaların veya sağlık sağlayıcılarının sağlık kayıtlarını depolamaz veya aktarmaz. EHR bağlayıcısının depoladığı tek veri, TEAMS toplantı kurulumu sırasında kullanılan EHR kullanıcısının benzersiz kimliğidir.

EHR kullanıcısının benzersiz kimliği, [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations) bölümünde açıklanan üç coğrafi bölgeden birinde depolanır. Toplantı katılımcıları tarafından Teams'de paylaşılan tüm sohbetler, kayıtlar ve diğer veriler mevcut depolama ilkelerine göre depolanır. Teams'deki verilerin konumu hakkında daha fazla bilgi edinmek için bkz. [Teams'de verilerin konumu](/microsoftteams/location-of-data-in-teams).

## <a name="related-articles"></a>İlgili makaleler

- [Teams Sanal Ziyaretleri kullanım raporu](virtual-visits-usage-report.md)
- [Teams EHR bağlayıcısı Sanal Randevular raporu](ehr-connector-report.md)
- [Sağlık kuruluşları için Teams'i kullanmaya başlama](teams-in-hc.md)
