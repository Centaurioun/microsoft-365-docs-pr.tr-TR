---
title: Adım 1. Uygulama Koruma İlkeleri Uygulama
ms.author: bcarter
author: brendacarter
f1.keywords:
- Intune App Protection policies
- APP
- mobile application management
- MAM
- set up mobile ap protection
manager: dougeby
audience: ITPro
ms.topic: article
description: Belirtilen kurumsal verilerin kopyalanıp diğer uygulamalara yapıştırılmasını önlemek için App Protection ilkeleri (APP) ile mobil uygulama korumasını yapılandırın.
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: 41281a2f8b0701b2a8f7522c0e771cb79d962b5b
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986146"
---
# <a name="step-1-implement-app-protection-policies"></a>Adım 1. Uygulama Koruma İlkeleri Uygulama

Bazen Mobil Uygulama Yönetimi (MAM) olarak da adlandırılan Uygulama Koruma ilkeleri (APP) Intune, bir cihazın kendisi yönetilmese bile şirket verilerini korur. Bu, kullanıcıların cihazlarını yönetime "kaydetmek" için isteksiz olabileceği iş yerinde kendi cihazını getir (BYO) ve kişisel cihazları etkinleştirmenizi sağlar. Uygulama Koruma ilkeleri, belirttiğiniz uygulamalardaki şirket verilerinin cihazdaki diğer uygulamalara kopyalanıp yapıştırılmamasını sağlar.

![Uygulama koruma ilkeleri oluşturma adımları](../media/devices/intune-app-steps.png#lightbox)

Bu çizimde:
- APP ile Intune, kuruluşunuzla kişisel verileriniz arasında bir duvar oluşturur. Uygulama koruma ilkeleri, verilerinize erişmesine izin verilen uygulamaları tanımlar.
- Kullanıcı kuruluş kimlik bilgileriyle oturum açarsa, Intune kuruluş verilerinizin kişisel uygulamalara kopyalanıp yapıştırılmasını önlemek ve bu verilere PIN erişimi gerektirmek için uygulama katmanında bir ilke uygular.
- Uygulama Koruma ilkesi oluşturduktan sonra, koşullu erişim ilkesiyle veri korumayı zorunlu kılmanız gerekir. 

Bu yapılandırma, kullanıcı deneyimini neredeyse hiç etkilemeden güvenlik duruşunuzu büyük ölçüde artırır.  Çalışanlar, Office ve Microsoft Teams gibi bildikleri ve sevdikleri uygulamaları kullanabilirken, kuruluşunuz da uygulamalar ve cihazlarda yer alan verileri koruyabilir.

Koruma gerektiren özel İş Kolu uygulamalarınız varsa, şu anda bu uygulamalarla APP'i etkinleştirmek için uygulama sarmalama aracını kullanabilirsiniz. Veya Intune Uygulama SDK'sını kullanarak tümleştirebilirsiniz. Uygulamanıza uygulama koruma ilkeleri uygulandığında, uygulama Intune tarafından yönetilebilir ve Intune tarafından yönetilen uygulama olarak tanınır. Intune kullanarak İş Kolu uygulamalarınızı koruma hakkında daha fazla bilgi için bkz. [uygulamaları Microsoft Intune ile mobil uygulama yönetimi için hazırlama](/mem/intune/developer/apps-prepare-mobile-application-management).

## <a name="configuring-mobile-app-protection"></a>Mobil uygulama korumasını yapılandırma

Bu kılavuz, önerilen [Sıfır Güven kimlik ve cihaz erişim ilkeleriyle](../security/office-365-security/microsoft-365-policies-configurations.md) sıkı bir şekilde koordine edilir. Intune'da Mobil Uygulama koruması ilkelerini oluşturduktan sonra, mobil uygulama korumasını zorunlu kılan Azure AD'da koşullu erişim ilkesini yapılandırmak için kimlik ekibinizle birlikte çalışın. 

Bu çizimde iki ilke vurgulanır (çizimin altındaki tabloda da açıklanmıştır).

[![kimlik ve cihaz erişim ilkelerini Sıfır Güven](../media/devices/identity-device-starting-point.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-starting-point.png)

Bu ilkeleri yapılandırmak için kimlik ve [cihaz erişim ilkeleri Sıfır Güven](../security/office-365-security/microsoft-365-policies-configurations.md) önerilen kılavuzu ve ayarları kullanın. Aşağıdaki tablo, bu ilkeleri Intune ve Azure AD yapılandırma yönergelerine doğrudan bağlanır.


|Adım  |İlkeler  |Daha fazla bilgi  |Lisanslama  |
|---------|---------|---------|---------|
|1   |  [Uygulama Koruma İlkeleri (APP) veri korumasını uygulama](../security/office-365-security/identity-access-policies.md#apply-app-data-protection-policies)       | Platform başına bir Intune Uygulama Koruması ilkesi (Windows, iOS/iPadOS, Android).        | Microsoft 365 E3 veya E5        |
|2     | [Onaylı uygulamalar ve uygulama koruması gerektirme ](../security/office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)       |  iOS, iPadOS veya Android kullanarak telefonlar ve tabletler için mobil uygulama korumasını zorlar.   |  Microsoft 365 E3 veya E5       |
| | | | |

## <a name="next-steps"></a>Sonraki adımlar

[2. Adım'a gidin. Cihazları Intune kaydetme](manage-devices-with-intune-enroll.md). 