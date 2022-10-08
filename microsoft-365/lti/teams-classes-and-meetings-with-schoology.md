---
title: Microsoft Teams toplantılarını Schoology LMS ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
ms.collection:
- M365-modern-desktop
- m365initiative-edu
ms.localizationpriority: medium
description: Schoology LMS için Microsoft Öğrenme Araçları Birlikte Çalışabilirliği (LTI) ile Teams toplantıları oluşturun ve yönetin.
ms.openlocfilehash: 9a2aaf2780bfa79324b7292e0383e595cec2e0f1
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68471870"
---
# <a name="integrate-microsoft-teams-meetings-with-schoology-lms"></a>Microsoft Teams toplantılarını Schoology LMS ile tümleştirme

Bu kılavuz, Teams Toplantıları LTI uygulamasını Schoology'ye kaydetmeye yönelik BT yöneticisi adımlarını sağlar.

Microsoft LTI'ye genel bakış için bkz. [Microsoft ürünlerini Öğrenme Yönetim Sisteminizle (LMS) tümleştirme](index.md).

> [!NOTE]
> Bu tümleştirmeyi gerçekleştiren kişi Schoology yöneticisi olmalıdır. Ancak Schoology **App Center'a** erişimi olan Schoology kullanıcıları Microsoft Teams Toplantıları LTI uygulamasını da yükleyebilir.

## <a name="deploy-the-teams-meetings-lti-app-in-schoology"></a>Schoology'de Teams Toplantıları LTI uygulamasını dağıtma

1. Uygulamaları yükleme ve yapılandırma erişimiyle Schoology örneğinizde yönetici olarak oturum açın.
1. Schoology'de **Microsoft Teams Toplantıları'nın** bu doğrudan bağlantısını açarak [**App**](https://app.schoology.com/apps) [Center'daki Microsoft Teams Toplantıları uygulamasına erişin](https://app.schoology.com/apps/profile/6017478062).
1. Yükleme işlemini başlatmak için **LTI 1.3 Uygulamasını Yükle** düğmesini seçin.
1. **Kabul ediyorum** düğmesini seçin.
1. Bu uygulamanın tüm kuruluşunuz için mi yoksa yalnızca sizin için mi yüklenmesi gerektiği sorulur. **Kuruluşa Ekle'yi** seçtiğinizde yapılandırmayı tamamlamak için **Kuruluş Uygulamaları** sayfasına yönlendirilirsiniz.
1. [**Kuruluş Uygulamaları listesinden**](https://app.schoology.com/apps/school_apps) **Microsoft Teams Toplantıları** uygulamasını bulun ve **Yapılandır** düğmesini seçin.
    1. Uygulama dağıtımınıza atanan **Dağıtım Kimliğini** kopyalayın.
        1. Bu kimlik **, Microsoft LMS Ağ Geçidi** yapılandırma işleminde kullanılacaktır.
1. [**Kuruluş Uygulamaları listesinden**](https://app.schoology.com/apps/school_apps) **Microsoft Teams Toplantıları** uygulamasını bulun ve **Yükle/Kaldır** düğmesini seçin.
    1. Uygulamayı tüm kullanıcılar için yüklemek için **Tüm Kullanıcılar** onay kutusunu seçin.
        1. Yalnızca kuruluşunuzdaki Öğretmenler, öğrenciler veya sistem yöneticileri gibi Microsoft Teams'e erişimi olacak rolleri seçin.
    1. Uygulamayı tüm kurslar için yüklemek için **Tüm Kurslar** onay kutusunu seçin.
        1. Uygulamanın kursun tüm üyeleri tarafından kullanılabildiğinden emin olmak için **Yalnızca Kurs Yöneticileri** seçeneğini işaretlemeyin.
    1. Uygulamayı tüm gruplar için yüklemek için **Tüm Gruplar** onay kutusunu seçin.

> [!NOTE]
> Uygulamayı tüm kurslar için yüklememeyi seçerseniz *, Kurs Yöneticilerinin* uygulamayı kendileri için yüklemeleri gerekir:
>
> 1. [Kuruluş Uygulamaları listesine](https://app.schoology.com/apps/school_apps) gidin, **Yükle/Kaldır** düğmesini seçin ve uygulamanın yükleneceği kursları seçin.
> 1. Alternatif olarak, kursun sol tarafındaki gezinti menüsünün alt kısmındaki **Uygulamanızı Yükleyin** bağlantısını ve ardından yüklenecek **Microsoft Teams Toplantıları** uygulamasını seçebilirler.
