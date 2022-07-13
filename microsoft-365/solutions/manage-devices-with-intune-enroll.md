---
title: Adım 2. Intune ile cihazları yönetime kaydetme
ms.author: bcarter
author: brendacarter
f1.keywords:
- enroll devices into management
- enroll devices to Intune
- Intune mobile device platforms
manager: dougeby
audience: ITPro
description: Intune ve Autopilot kullanarak cihazları yönetime kaydederek üzerinde çalışan uygulamaların uyumlu olduğundan emin olun ve kurumsal veri sızıntılarını önleyin.
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: 6a5fb754b8d2cea38473de888d2d927dd4bd9de9
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749275"
---
# <a name="step-2-enroll-devices-to-intune"></a>Adım 2. Cihazları Intune kaydetme

Uç noktanın güvenliğini sağlamanın çeşitli yolları vardır. Bu terim genellikle cihazlar, uygulamalar ve kullanıcı kimliği gibi birleştirilmiş varlığa başvurmak için kullanılır. Güvenlik ilkelerinin yalnızca uygulamalarda değil, cihazın kendisinde de tutarlı ve güvenilir bir şekilde uygulanması gerekir. Cihazı Intune kaydetmek ve Azure Active Directory gibi bir bulut kimliği sağlayıcısına kaydolmak harika bir başlangıçtır.

Bir cihaz ister kişisel KCG cihazı ister şirkete ait ve tam olarak yönetilen bir cihaz olsun, yalnızca sağlıklı ve uyumlu cihazlara izin vermek için kuruluşunuzun kaynaklarına erişen uç noktaların görünürlüğünün olması iyi olur. Bu, uç noktalarda çalışan mobil ve masaüstü uygulamalarının sistem durumunu ve güvenilirliğini içerir. Bu uygulamaların iyi durumda ve uyumlu olduğundan ve şirket verilerinin kötü amaçlı veya yanlışlıkla tüketici uygulamalarına veya hizmetlerine sızmasını engellediğinden emin olmak istiyorsunuz.

Cihaz kayıt işlemi kullanıcı, cihaz ve Microsoft Intune hizmeti arasında bir ilişki kurar. Tek başına hizmet olarak Microsoft Intune kullanmak, Windows bilgisayarlarını, macOS'u ve en popüler mobil cihaz platformlarını yönetmek için tek bir web tabanlı yönetim konsolu kullanmanıza olanak tanır.

Bu makalede cihazları Intune kaydetme yöntemleri önerilir. Bu yöntemler ve her birinin nasıl dağıtılacağı hakkında daha fazla bilgi için bkz[. Dağıtım kılavuzu: Cihazları Microsoft Intune kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment).

![Cihazları yönetme adımları](../media/devices/intune-mdm-steps-1.png#lightbox)

Her platform için kayıt seçeneklerinin bu resimli sürümüyle birlikte bu makaledeki kılavuzu kullanın. 

[![Platforma göre Intune kayıt seçeneklerinin görsel gösterimi](../media/devices/msft-intune-enrollment-options-thumb-landscape.png)](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.pdf) <br/> [PDF](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.pdf) | [Visio](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.vsdx) <br/> Haziran 2022'de güncelleştirildi



## <a name="windows-enrollment"></a>Windows kaydı
Windows 10 ve Windows 11 cihazları kaydetmek için çeşitli seçenekler vardır. En yaygın yöntemler şunlardır:

- Azure Active Directory (Azure AD) Katılımı - Cihazı Azure Active Directory ile birleştirir ve kullanıcıların Azure AD kimlik bilgileriyle Windows'ta oturum açmasını sağlar. Otomatik Kayıt etkinse cihaz otomatik olarak Intune kaydedilir. Otomatik kaydın avantajı, kullanıcı için tek adımlı bir işlemdir. Aksi takdirde, yalnızca MDM kaydı aracılığıyla ayrı olarak kaydolmaları ve kimlik bilgilerini yeniden kullanmaları gerekir. Kullanıcılar ilk Windows OOBE sırasında veya Ayarlar'dan bu şekilde kaydoldu. Cihaz, Intune'da şirkete ait bir cihaz olarak işaretlenir.
- Autopilot - Azure AD Katılmayı otomatikleştirir ve şirkete ait yeni cihazları Intune kaydeder. Bu yöntem ilk çalıştırma deneyimini basitleştirir ve cihazlara özel işletim sistemi görüntüleri uygulama gereksinimini ortadan kaldırır. Yöneticiler Autopilot cihazlarını yönetmek için Intune kullandığında, kaydolduktan sonra ilkeleri, profilleri, uygulamaları ve daha fazlasını yönetebilir. Dört tür Autopilot dağıtımı vardır: Self-Deploying Modu (bilgi noktaları, dijital oturum açma veya paylaşılan cihaz için), Kullanıcı Odaklı Mod (geleneksel kullanıcılar için), Önceden sağlanan dağıtım için Windows Autopilot, iş ortaklarının veya BT personelinin Windows 10 veya Windows 11 çalıştıran bir bilgisayarı önceden sağlamasını sağlar  tam olarak yapılandırılmış ve iş için hazır olacak şekilde ve mevcut cihazlar için Autopilot, Windows'un en son sürümünü mevcut cihazlarınıza kolayca dağıtmanıza olanak tanır.

KCG Windows cihazlarını kaydetme dahil olmak üzere ek seçenekler için bkz. [Windows cihazlarını Microsoft Intune'a kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment-windows).

## <a name="ios-and-ipados-enrollment"></a>iOS ve iPadOS kaydı

Kullanıcıya ait (KCG) cihazlar için kullanıcıların kişisel cihazlarını Intune kaydetmesine izin vererek aşağıdaki yöntemlerden birini kullanabilirsiniz.
- Cihaz kaydı, tipik KCG kaydı olarak düşünebilirsiniz. Yöneticilere çok çeşitli yönetim seçenekleri sağlar.
- Kullanıcı kaydı, yöneticilere cihaz yönetimi seçeneklerinin bir alt kümesini sağlayan daha kolay bir kayıt işlemidir. Bu özellik şu anda önizleme aşamasındadır.

Kullanıcıları için cihaz satın alan kuruluşlar için Intune aşağıdaki iOS/iPadOS şirkete ait cihaz kayıt yöntemlerini destekler:
- Apple'ın Otomatik Cihaz Kaydı (ADE)
- Apple School Manager
- Apple Configurator Kurulum Yardımcısı kaydı
- Apple Configurator doğrudan kaydı

Daha fazla bilgi için bkz[. iOS ve iPadOS cihazlarını Microsoft Intune kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados).

## <a name="android-enrollment"></a>Android kaydı 

Cihazın türüne, desteklemek istediğiniz kayıt türüne ve kullandığınız Android sürümüne ve hatta üreticiye (özellikle Samsung) bağlı olarak Android Kaydı için çeşitli seçenekler vardır. Çoğu kuruluş, özellikle KCG senaryolarında son kullanıcıları için Android Work profillerini kullanır. 

Android iş profiliyle, son kullanıcının bilgileri veri kapsayıcılarının yanı sıra iş ve kişisel kullanım için ayrı uygulamalarla ayrı ayrı ayrılır. Bu, kullanıcıların kendi verilerinin gizliliğini ve şirket verilerinin güvenliğini korurken cihazlarını kaydetmeleri için ideal bir yoldur. 

Ancak kuruluşunuz Android cihazları sağlıyorsa, tam olarak yönetilen (Kullanıcı Benzşimi) veya ayrılmış (Kullanıcı Benzitesi olmayan) cihaz olarak adlandırılan cihazı kullanmayı seçebilirsiniz.

Android kaydı hakkında daha fazla bilgi edinmek için bkz[. Android cihazlarını Microsoft Intune kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment-android).

## <a name="macos-enrollment"></a>macOS kaydı

macOS kaydı, birçok BT kuruluşu için zor bir konu olabilir. Kullanıcılarınızın çoğu Mac kullanıcısı olmadığı sürece bu tür cihazları büyük ölçüde yönetemeyebilirsiniz. Az sayıda macOS kullanıcınız varsa Yalnızca Kayıt Intune öneririz. Çok sayıda macOS kullanıcınız varsa Intune + Jamf kaydı kullanmanızı öneririz.  
- Intune Yalnızca kayıt — Bu, macOS cihazlarının temel yönetimi içindir. Diğer kullanıcı tabanlı kayıt seçeneklerinin çoğu gibi el ile gerçekleştirilen bir işlem gerektirir. Ancak az sayıda Mac cihazınız varsa bu, yalnızca bu birkaç kullanıcı için otomatik bir altyapının tamamını ayarlamaktan daha kolay olabilir. Yalnızca Intune kayıtla sertifikalar, parola yapılandırmaları ve uygulamalar gibi öğeleri dağıtabilirsiniz. Ayrıca uyumluluk ilkelerini yapılandırabilir ve Koşullu Erişimin yanı sıra şifrelemeyi ve cihaz temizlemeyi zorunlu kılma özelliğini de kullanabilirsiniz. 
- Intune ve Jamf kaydı — Koşullu Erişim için Jamf + Intune ile Mac yönetimi için en derin desteği arayanlar için, Koşullu Erişim'i etkinleştirmek için Jamf'in kapsamlı Mac yönetim özelliklerini Intune uyumluluğuyla birleştiren harika bir çözüme sahibiz. Bu senaryoda jamf ile cihazı tam olarak yönetirken daha fazla güvenlik için Jamf'ten bu sinyalleri alabiliyorsunuz.

macOS kaydı hakkında daha fazla bilgi için bkz[. macOS cihazlarını Microsoft Intune kaydetme](/mem/intune/fundamentals/deployment-guide-enrollment-macos).

## <a name="next-steps"></a>Sonraki adımlar

3. Adım'a gidin[. Intune olan cihazlar için uyumluluk ilkeleri ayarlayın](manage-devices-with-intune-compliance-policies.md).

