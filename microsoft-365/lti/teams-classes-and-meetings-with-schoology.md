---
title: Microsoft Teams toplantılarını Schoology Learning ile tümleştirme
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
description: PowerSchool Unified Classroom® Schoology Learning için Microsoft Öğrenme Araçları Birlikte Çalışabilirliği (LTI) ile Teams toplantıları oluşturun ve yönetin.
ms.openlocfilehash: 9fb0d513f3f6cc4148006abb01473d12210fbfbb
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804608"
---
# <a name="integrate-microsoft-teams-meetings-with-schoology-learning"></a>Microsoft Teams toplantılarını Schoology Learning ile tümleştirme

Bu kılavuz, PowerSchool Unified Classroom® Schoology Learning'de Teams Toplantıları LTI uygulamasını kaydetmeye yönelik BT yöneticisi adımlarını sağlar.

Microsoft LTI'ye genel bakış için bkz. [Microsoft ürünlerini Öğrenme Yönetim Sisteminizle (LMS) tümleştirme](index.md).

> [!NOTE]
> Bu tümleştirmeyi gerçekleştiren kişi Schoology Learning yöneticisi olmalıdır. Ancak Schoology Learning **Uygulama Merkezi'ne** erişimi olan Schoology Learning kullanıcıları, Microsoft Teams Toplantıları LTI uygulamasını da yükleyebilir.

## <a name="deploy-the-teams-meetings-lti-app-in-schoology-learning"></a>Schoology Learning'de Teams Toplantıları LTI uygulamasını dağıtma

1. Schoology Learning örneğinizde uygulama yükleme ve yapılandırma erişimi olan bir yönetici olarak oturum açın.
1. Schoology Learning'de **Microsoft Teams Toplantıları'nın** bu doğrudan bağlantısını açarak [**App Center'daki**](https://app.schoology.com/apps) [Microsoft Teams Toplantıları uygulamasına erişin](https://app.schoology.com/apps/profile/6017478062).
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
