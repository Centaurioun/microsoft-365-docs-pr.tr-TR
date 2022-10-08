---
title: Microsoft Teams sınıflarını ve toplantılarını Open LMS ile tümleştirme
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
description: Açık LMS için Microsoft Öğrenme Araçları Birlikte Çalışabilirliği ile Teams sınıflarını ve toplantılarını oluşturun ve yönetin.
ms.openlocfilehash: 034aa9924798b7e284665713e6d8fe2809c1e70f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203826"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-open-lms"></a>Microsoft Teams sınıflarını ve toplantılarını Open LMS ile tümleştirme

Bu kılavuz, Hem Teams Sınıflarını hem de Teams Toplantıları LTI uygulamalarını Açık LMS'ye kaydetmeye yönelik BT yöneticisi adımlarını sağlar.

Herhangi bir LMS için tüm LTI uygulamalarını yönetme hakkında ayrıntılı bilgi için bkz. [Herhangi bir LMS için Microsoft LMS Ağ Geçidi'ni yönetme](manage-microsoft-one-lti.md).

## <a name="prerequisites-before-set-up"></a>Ayarlamadan önce önkoşullar

Open LMS ile Teams arasındaki tümleştirmenin düzgün çalışması için Open LMS ve Teams'in birbirleriyle iletişim kuracak şekilde ayarlanması gerekir.

[Moodle LMS eklentilerini yükleme ve yapılandırma yönergelerini](open-lms-plugin-configuration.md) izleyin.

## <a name="register-microsoft-teams-lti-for-use-in-open-lms"></a>Microsoft Teams LTI'sini Açık LMS'de kullanmak üzere kaydetme

> [!IMPORTANT]
> Bu tümleştirmeyi gerçekleştiren kişi Açık LMS yöneticisi ve Microsoft 365 kiracı yöneticisi olmalıdır.

1. [Microsoft LMS Ağ Geçidi'ni](https://lti.microsoft.com/) ziyaret edin ve **Kayıt portalına git** düğmesini seçin.

2. Microsoft 365 yönetici hesabıyla oturum açın.

3. Oturum açtıktan sonra **Yeni kayıt ekle'yi** seçin.

4. Kaydolmak için **Teams Toplantıları LTI** veya **Teams Sınıfları LTI'yi** ve ardından **İleri'yi** seçin.

5. Kolayca tanımlanabilen bir **Kayıt** adı girin ve **LMS platformu olarak LMS'yi Aç'ı** seçin. **İleri**'yi seçin.

6. Size Açık LMS sitenize eklenmesi gereken anahtarların listesi verilir.

7. LMS'i başka bir sekmede açın. Microsoft LMS Ağ Geçidi sekmesini kapatmayın.

8. Açık LMS'de **Site yönetimi** > **Eklentileri** > **Etkinlik modülleri** > **Dış araçlar** > **Araçları yönet'e** gidin.

9. **Araçları yönet** sayfasında **bir aracı el ile yapılandır'ı** seçin.

10. **Araç ayarları'nın** altında **Microsoft Teams Sınıfları** gibi bir **Araç adı** girin. **LTI sürümü** için **LTI 1.3'i** seçin. **Ortak anahtar türü için** **Anahtar Kümesi URL'sini** seçin.

11. Ardından, **Anahtarları Microsoft LTI anahtarlarından** ilgili araç girişlerine kopyalayın.
    1. Microsoft'un **Hedef bağlantı URL** anahtarı, Açık LMS'nin **Araç URL'si** alanına gider.
    1. Microsoft'un **Açık Kimlik bağlantı URL** anahtarı, Open LMS'nin **Oturum açma URL'sini başlat** alanına gider.
    1. Microsoft'un **Yeniden Yönlendirme URL** anahtarı, Open LMS'nin **Yeniden Yönlendirme URI'leri** alanına gider.

12. **Değişiklikleri kaydet'i** seçin.

13. Yeni araç artık LMS'nin **Araçları** **Yönet** sayfasını açmanın Araçlar bölümünde görünmelidir. **Araç yapılandırma ayrıntılarını** görüntülemek için liste simgesini seçin.

14. Microsoft LMS Ağ Geçidi sekmesine Geri dön. **LMS tarafından sağlanan kayıt anahtarları** adımına gitmek için **İleri'yi** seçin.

15. LMS'nin **Araç yapılandırma ayrıntılarını** aç'taki değerleri kopyalayıp Microsoft'un **LMS tarafından sağlanan kayıt anahtarları** adımına yapıştırın.

    Değerleri aşağıdaki gibi yapıştırın:

    | Açık LMS'de | Microsoft LTI kayıt portalında |
    | --------- | ------------------------------------ |
    | Platform Kimliği | Veren Kimliği URL'si |
    | İstemci Kimliği | İstemci Kimliği |
    | Dağıtım Kimliği | Dağıtım Kimliği |
    | Ortak anahtar kümesi URL'si | Anahtar Kümesi URL'si |
    | Erişim belirteci URL'si | Erişim belirteci URL'si |
    | Kimlik doğrulama isteği URL'si | Platform kimlik doğrulaması URL'si |

    **İleri**'yi seçin.

16. **Gözden geçir ve ekle** sayfasını gözden geçirin. Hata yoksa **Kaydet ve çık'ı** seçin. Kaydın başarılı olduğunu belirten bir ileti görmeniz gerekir.

Teams Sınıfları veya Teams Toplantıları LTI uygulamasının kaydını tamamladınız.

Diğer uygulamayı da eklemek isterseniz, 4. adımda diğer Teams LTI uygulamasını seçerek yukarıdaki adımları yineleyin.

### <a name="add-teams-lti-apps-to-educators-open-lms-courses"></a>Eğitimcilerin Açık LMS kurslarına Teams LTI uygulamaları ekleme

Eğitimciler Teams LTI uygulamalarını kaydettikten sonra Teams Sınıfları uygulamasını ve Teams Toplantıları uygulamasını Açık LMS kurslarına ekleyebilir.

- [Teams Sınıfları uygulamasını eklemeye ilişkin eğitimci yönergeleri](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a).
- [Teams Toplantıları uygulamasını eklemeye ilişkin eğitimci yönergeleri](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76).

## <a name="technical-requirements-to-launch-teams-lti-apps"></a>Teams LTI uygulamalarını başlatmak için teknik gereksinimler

Teams LTI uygulamalarını Open LMS'de başlatmak için karşılanması gereken birkaç teknik gereksinim vardır.

> [!NOTE]
> BT yöneticileri ve eğitimciler LTI uygulamalarını LTI uygulamaları kayıt portalına kaydedebilir.

### <a name="it-admin-technical-requirements"></a>BT yöneticisi teknik gereksinimleri

- Moodle sürüm 3.10 veya üzerini kullanın.
- Moodle sürüm 3.10 veya üzeri için en son Microsoft O365 eklentisini indirin.
- LTI uygulamalarını kaydetmek için LTI uygulamaları kayıt portalına erişin.
  - Kayıt bir masaüstü cihazında tamamlanmış olmalıdır.
- Microsoft Edge, Google Chrome, Safari veya Mozilla Firefox'un en son sürümünü indirin.

### <a name="educator-technical-requirements"></a>Eğitimci teknik gereksinimleri

- BT yöneticisi uygulamaları kaydetmediyse LTI uygulamalarını kaydetmek için LTI uygulamaları kayıt portalına erişin.
  - Kayıt bir masaüstü cihazında tamamlanmış olmalıdır.
- Microsoft Edge, Google Chrome, Safari veya Mozilla Firefox'un en son sürümünü indirin.
- [Açık LMS'de Sınıflar ve Toplantılar için Teams LTI uygulamaları](#add-teams-lti-apps-to-educators-open-lms-courses).

### <a name="student-technical-requirements"></a>Öğrenci teknik gereksinimleri

- Açık LMS'de Sınıflar ve Toplantılar için Teams LTI uygulamaları.
  - Öğrencilerin Teams Sınıfları veya Toplantılar LTI uygulamalarını eklemek için herhangi bir işlem gerçekleştirmeleri gerekmez.
