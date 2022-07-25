---
title: Microsoft Teams sınıflarını ve toplantılarını LTI uygulamalarını Desire2Learn Brightspace LMS ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Desire2Learn (D2L) Brightspace LMS için Microsoft Öğrenme Araçları Birlikte Çalışabilirliği (LTI) ile Teams sınıflarını ve toplantılarını oluşturun ve yönetin.
ms.openlocfilehash: c3d551fcdc866c08437564addb1cd3cb9b144a75
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989528"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-lti-apps-within-desire2learn-brightspace-lms"></a>Microsoft Teams sınıflarını ve toplantılarını LTI uygulamalarını Desire2Learn Brightspace LMS ile tümleştirme

Bu kılavuz, Desire2Learn (D2L) Brightspace LMS için hem Teams Sınıflarını hem de Teams Toplantıları LTI uygulamalarını kaydetmeye yönelik BT yöneticisi adımlarını sağlar.

Herhangi bir LMS için tüm LTI uygulamalarını yönetme hakkında ayrıntılı bilgi için bkz. [Herhangi bir LMS için Microsoft LMS Ağ Geçidi'ni yönetme](manage-microsoft-one-lti.md).

Teams LTI uygulamalarını ve Brightspace'i tümleştirmenin temel adımları şunlardır:

1. [Tümleştirme öncesi önkoşullar](#prerequisites-before-integration).
1. [Microsoft LTI'ı Brightspace'te kullanmak üzere kaydedin](#register-microsoft-teams-lti-for-use-in-brightspace).
1. [Microsoft LTI uygulamalarını Brightspace'e dağıtın](#deploy-the-microsoft-lti-apps-to-brightspace).
1. [Eğitimcilerin Brightspace'ine Teams LTI uygulama bağlantıları ekleyin](#add-teams-lti-app-links-to-educators-brightspace).

## <a name="prerequisites-before-integration"></a>Tümleştirme öncesi önkoşullar

D2L Brightspace ile Teams arasındaki tümleştirmenin düzgün çalışması için Brightspace ve Teams'in birbirleriyle iletişim kuracak şekilde ayarlanması gerekir.

1. Teams Sınıflarının çalışması için **Brightspace Kurs Bağlayıcısı'nın** doğru şekilde yüklenmiş ve yapılandırılmış olması gerekir. [Bağlayıcıyı Brightspace hesabınıza yüklemek için bu adımları](https://community.brightspace.com/s/article/Getting-started-with-Brightspace-Course-Connector-for-Microsoft-Teams) izleyin.

   > [!NOTE]
   > Teams LTI araçlarıyla uyumluluğu sağlamak için bağlayıcıyı ayarlarken **Tümleştirme türü** için **Sınıf Ekibi'ni** seçin.

2. Teams Toplantıları kurs bağlayıcısı olmadan çalışır. Ancak Tüm **sınıfı ekle** gibi bazı özellikler kullanılamaz. Teams Toplantıları LTI uygulaması için **Brightspace Kurs Bağlayıcısı'nı** yüklemenizi öneririz.

## <a name="register-microsoft-teams-lti-for-use-in-brightspace"></a>Microsoft Teams LTI'ı Brightspace'te kullanmak üzere kaydetme

1. [Microsoft LMS Ağ Geçidi'ni](https://lti.microsoft.com/) ziyaret edin ve **Kayıt Portalına Git** düğmesini seçin.

2. *Microsoft 365 yönetici hesabıyla oturum* açın.

3. Oturum açtıktan sonra **Yeni kayıt ekle'yi** seçin.

4. Kaydolmak için **Teams Toplantıları LTI** veya **Teams Sınıfları LTI'yi** ve ardından **İleri'yi** seçin.

5. Kolayca tanımlanabilir bir **Kayıt** adı girin ve LMS platformu olarak **D2L Brightspace'i** seçin. **İleri**'yi seçin.

6. Size Brightspace LMS sitenize eklenmesi gereken anahtarların listesi verilir.

7. Brightspace sitesini başka bir sekmede açın. Microsoft LMS Ağ Geçidi sekmesini kapatmayın.

8. Brightspace sitesinde **Yönetici** >  **Değerlendirmeyi Yönet'e** gidin ve **LTI Avantajı'nı** ve ardından **Aracı Kaydet'i** seçin.

9. **Standart kayıt'ı** seçin ve **Anahtarları Microsoft LTI anahtarlarından** ilgili araç girişlerine kopyalayın.
    1. Microsoft'un **Hedef bağlantı URL** anahtarı Brightspace'in **Hedef Bağlantı URI'si** alanına gider.
    1. Microsoft'un **Açık Kimlik bağlantı URL'si** anahtarı Brightspace'in **OpenID Connect Oturum Açma URL'si** alanına gider.
    1. Microsoft'un **Yeniden Yönlendirme URL'si** anahtarı Brightspace'in **Yeniden Yönlendirme URL'leri** alanına gider.

10. **Etki alanı** alanına girin`https://teams.microsoft.com`.

11. **Kaydet** düğmesini seçin.

12. Kalıcı olarak Brightspace kayıt ayrıntıları görüntülenir. Bu değerlerin Microsoft LMS Ağ Geçidi'ne eklenmesi gerekir.

13. **Microsoft LMS ağ geçidi** sekmesinde **LMS tarafından sağlanan kayıt anahtarları'nı** seçin.

14. Brightspace'in yapılandırma ayrıntılarındaki değerleri kopyalayıp Microsoft'un **LMS tarafından sağlanan kayıt anahtarları** adımına yapıştırın.

    Değerleri aşağıdaki gibi yapıştırın:

    | Brightspace'te                         | Microsoft LTI kayıt portalında |
    | -------------------------------------- | ------------------------------------ |
    | Veren                                 | Veren Kimliği URL'si                        |
    | İstemci Kimliği                              | İstemci Kimliği                            |
    | Brightspace Anahtar Kümesi URL'si                 | Anahtar Kümesi URL'si                           |
    | OpenID Connect Kimlik Doğrulama Uç Noktası | Platform kimlik doğrulaması URL'si          |

    **İleri**'yi seçin.

15. **Gözden geçir ve ekle** sayfasını gözden geçirin. Hata yoksa **Kaydet ve çık'ı** seçin. Kaydın başarılı olduğunu belirten bir ileti görmeniz gerekir.

Teams Sınıfları veya Teams Toplantıları LTI uygulamasının kaydını tamamladınız.

Diğer uygulamayı da eklemek isterseniz, 4. adımda diğer Teams LTI uygulamasını seçerek yukarıdaki adımları yineleyin.

## <a name="deploy-the-microsoft-lti-apps-to-brightspace"></a>Microsoft LTI uygulamalarını Brightspace'e dağıtma

Microsoft LTI uygulamalarınızı kaydettikten sonra uygulamaları Brightspace sitenize dağıtmanız gerekir.

Yeni dağıtım oluşturma yordamı aşağıdadır:

1. Brightspace sitesinde, oluşturduğunuz aracı seçin.
2. Bir dağıtım adı girin.
3. **Sınıf listesi** ve **Anonim** dışındaki tüm güvenlik ayarlarını seçin.
4. Yapılandırma ayarlarını yapmayın.
5. **Dağıtım Oluştur'u** seçin.

Yeni LTI uygulamasını kullanmak istediğiniz **Kuruluş Birimlerini** seçin. **Kök kuruluşu** seçin veya tek tek kuruluş birimi alt öğelerini seçin.

## <a name="add-teams-lti-app-links-to-educators-brightspace"></a>Eğitimcilerin Brightspace'ine Teams LTI uygulama bağlantıları ekleme

Dağıtım oluşturduktan sonra yeni bir bağlantı oluşturacaksınız. Bu bağlantı, eğitimcilerin Brightspace deneyimine Microsoft LTI uygulamasını ekleyecektir.

1. Brightspace sitesinde, oluşturduğunuz dağıtımı seçin.
2. Ekranı aşağı kaydırın ve **Bağlantıları Görüntüle'yi** seçin.
3. **Yeni bağlantı'ya tıklayın**.
4. Şu gerekli ayrıntıları doldurun:
    1. *Microsoft LMS ağ geçidindeki* **Yeniden Yönlendirme URL'sini** **URL** alanına yapıştırın. Bu URL'ye ağ geçidindeki kayıt görüntülenerek erişilebilir.
    1. Türü **Temel Başlatma** olarak ayarlayın.
5. **Kaydet ve Kapat'ı** seçin.

Eğitimci artık Microsoft LTI uygulamasını Brightspace **Mevcut İçerik** açılan listesinden seçerek ekleyebilir.
