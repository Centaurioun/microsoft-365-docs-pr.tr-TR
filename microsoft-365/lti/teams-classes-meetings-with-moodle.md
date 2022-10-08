---
title: Microsoft Teams sınıflarını ve toplantılarını Moodle ile tümleştirme
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
description: Moodle için Microsoft OneDrive Öğrenme Araçları Birlikte Çalışabilirliği ile Teams sınıflarını ve toplantılarını oluşturun ve yönetin.
ms.openlocfilehash: 4ee2d08a3f437679179e642725660dbf528236c2
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188735"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-moodle"></a>Microsoft Teams sınıflarını ve toplantılarını Moodle ile tümleştirme

Bu kılavuz, Hem Teams Sınıflarını hem de Teams Toplantıları LTI uygulamalarını Moodle'a kaydetmeye yönelik BT yöneticisi adımlarını sağlar.

Herhangi bir LMS için tüm LTI uygulamalarını yönetme hakkında ayrıntılı bilgi için bkz. [Herhangi bir LMS için Microsoft LMS Ağ Geçidi'ni yönetme](manage-microsoft-one-lti.md).

## <a name="prerequisites-before-set-up"></a>Ayarlamadan önce önkoşullar

Moodle ile Teams arasındaki tümleştirmenin düzgün çalışması için Moodle ve Teams'in birbirleriyle iletişim kuracak şekilde ayarlanması gerekir.

[Moodle eklentisini yükleme ve yapılandırma yönergelerini](moodle-plugin-configuration.md) izleyin.

## <a name="register-microsoft-teams-lti-for-use-in-moodle"></a>Microsoft Teams LTI'ı Moodle'da kullanmak üzere kaydetme

Bu tümleştirmeyi gerçekleştiren kişi moodle yöneticisi ve Microsoft 365 kiracı yöneticisi olmalıdır.

1. [Microsoft LMS Ağ Geçidi'ni](https://lti.microsoft.com/) ziyaret edin ve **Kayıt portalına git** düğmesini seçin.

2. Microsoft 365 yönetici hesabıyla oturum açın.

3. Oturum açtıktan sonra **Yeni kayıt ekle'yi** seçin.

4. Kaydolmak için **Teams Toplantıları LTI** veya **Teams Sınıfları LTI'yi** ve ardından **İleri'yi** seçin.

5. Kolayca tanımlanabilen bir **Kayıt** adı girin ve LMS platformu olarak **Moodle'ı** seçin. **İleri**'yi seçin.

6. Moodle sitenize eklenmesi gereken anahtarların listesi verilir.

7. Moodle'i başka bir sekmede açın. Microsoft LMS Ağ Geçidi sekmesini kapatmayın.

8. Moodle'da **Site yönetimi** > **Eklentileri** > **Etkinlik modülleri** > **Dış araçlar** > **Araçları yönet'e** gidin.

9. **Araçları yönet** sayfasında **bir aracı el ile yapılandır'ı** seçin.

10. **Araç ayarları'nın** altında **Microsoft Teams Sınıfları** gibi bir **Araç adı** girin. **LTI sürümü** için **LTI 1.3'i** seçin. **Ortak anahtar türü için** **Anahtar Kümesi URL'sini** seçin.

11. Ardından, **Microsoft LTI anahtarlarından** ilgili araç girişlerine anahtarları kopyalayın.
    1. Microsoft'un **Hedef bağlantı URL** anahtarı Moodle'ın **Araç URL'si** alanına gider.
    1. Microsoft'un **Açık Kimlik bağlantı URL** anahtarı Moodle's **Initiate login URL** alanına gider.
    1. Microsoft'un **Yeniden Yönlendirme URL** anahtarı Moodle'ın **Yeniden Yönlendirme URI'leri** alanına gider.

12. **Değişiklikleri kaydet'i** seçin.

13. Yeni araç artık Moodle'ın Araçları **yönet** sayfasının **Araçlar** bölümünde görünmelidir. **Araç yapılandırma ayrıntılarını** görüntülemek için liste simgesini seçin.

14. Microsoft LMS Ağ Geçidi sekmesine Geri dön. **LMS tarafından sağlanan kayıt anahtarları** adımına gitmek için **İleri'yi** seçin.

15. Moodle's **Tool yapılandırma ayrıntılarındaki** değerleri kopyalayıp Microsoft'un **LMS tarafından sağlanan kayıt anahtarları** adımına yapıştırın.

    Değerleri aşağıdaki gibi yapıştırın:

    | Moodle'da | Microsoft LTI kayıt portalında |
    | --------- | ------------------------------------ |
    | Platform Kimliği | Veren Kimliği URL'si |
    | İstemci Kimliği | İstemci Kimliği |
    | Dağıtım Kimliği | Dağıtım Kimliği |
    | Ortak anahtar kümesi URL'si | Anahtar Kümesi URL'si |
    | Erişim belirteci URL'si | Erişim belirteci URL'si |
    | Kimlik doğrulama isteği URL'si | Platform kimlik doğrulaması URL'si |

    >[!NOTE]
    > Ortak anahtar kümesi URL'sinin, Microsoft LMS Ağ Geçidi'nden kaynaklanan istekler için ağ ayarlarınız tarafından kısıtlanmadığından emin olun.

    **İleri**'yi seçin.

16. **Gözden geçir ve ekle** sayfasını gözden geçirin. Hata yoksa **Kaydet ve çık'ı** seçin. Kaydın başarılı olduğunu belirten bir ileti görmeniz gerekir.

Teams Sınıfları veya Teams Toplantıları LTI uygulamasının kaydını tamamladınız.

Diğer uygulamayı da eklemek isterseniz, 4. adımda diğer Teams LTI uygulamasını seçerek yukarıdaki adımları yineleyin.

### <a name="add-teams-lti-apps-to-educators-moodle-courses"></a>Eğitimcilerin Moodle kurslarına Teams LTI uygulamaları ekleme

Eğitimciler Teams LTI uygulamalarını kaydettikten sonra Teams Sınıfları uygulamasını ve Teams Toplantıları uygulamasını Moodle kurslarına ekleyebilir.

- [Teams Sınıfları uygulamasını eklemeye ilişkin eğitimci yönergeleri](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a).
- [Teams Toplantıları uygulamasını eklemeye ilişkin eğitimci yönergeleri](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76).

## <a name="technical-requirements-to-launch-teams-lti-apps"></a>Teams LTI uygulamalarını başlatmak için teknik gereksinimler

Teams LTI uygulamalarını Moodle'da başlatmak için karşılanması gereken birkaç teknik gereksinim vardır.

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
- [Moodle'da Sınıflar ve Toplantılar için Teams LTI uygulamaları](#add-teams-lti-apps-to-educators-moodle-courses).

### <a name="student-technical-requirements"></a>Öğrenci teknik gereksinimleri

- Moodle'da Sınıflar ve Toplantılar için Teams LTI uygulamaları.
  - Öğrencilerin Teams Sınıfları veya Toplantılar LTI uygulamalarını eklemek için herhangi bir işlem gerçekleştirmeleri gerekmez.
