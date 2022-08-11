---
title: İş için Microsoft Defender deneme playbook'u
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.date: 08/10/2022
ms.prod: m365-security
ms.technology: mdb
search.appverid:
- MOE150
- MET150
description: Bu playbook ile İş için Defender denemenizden en iyi şekilde geçin. Hızlı bir şekilde ayarlayın ve yeni güvenlik özelliklerinizi kullanmaya başlayın.
ms.custom: trial-playbook
ms.openlocfilehash: 3b588dba1ee1a3df5719ece9c2db50e76acf36b2
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309493"
---
# <a name="trial-playbook-microsoft-defender-for-business"></a>Deneme playbook'u: İş için Microsoft Defender

**İş için Defender deneme playbook'una hoş geldiniz!**

Bu playbook, 30 günlük ücretsiz denemenizden en iyi şekilde yararlanabilirsiniz. İş için Defender'ın güvenliğinizi geleneksel virüsten korumadan yeni nesil koruma, uç nokta algılama ve yanıt ve Tehdit ve Güvenlik Açığı Yönetimi yükseltmeye nasıl yardımcı olabileceğini öğrenmek için Microsoft Defender ekibinin bu makaledeki önerilerini kullanın.

## <a name="what-is-defender-for-business"></a>İş için Defender nedir?

İş için Defender, özellikle 300'e kadar çalışanı olan küçük ve orta ölçekli işletmeler için tasarlanmış yeni bir uç nokta güvenlik çözümüdür. Bu uç nokta güvenlik çözümüyle, kuruluşunuzun cihazları fidye yazılımlarına, kötü amaçlı yazılımlara, kimlik avına ve diğer tehditlere karşı iyi korunur.

:::image type="content" source="media/mdb-offering-overview.png" alt-text="İş için Defender özellikleri ve özellikleri.":::

**Başlayalım!**

## <a name="set-up-your-trial"></a>Deneme sürümünüzü ayarlama

Deneme aboneliğinizi şu şekilde ayarlayabilirsiniz:

1. [Kullanıcı ekleyin ve lisans atayın](#step-1-add-users-and-assign-licenses).
2. [Microsoft 365 Defender portalını ziyaret edin](#step-2-visit-the-microsoft-365-defender-portal).
3. [Kurulum sihirbazını kullanın](#step-3-use-the-setup-wizard-in-defender-for-business-recommended).
4. [İş için Defender'ı ayarlayın ve yapılandırın](#step-4-set-up-and-configure-defender-for-business).

### <a name="step-1-add-users-and-assign-licenses"></a>1. Adım: Kullanıcı ekleme ve lisans atama

İş için Defender'a kaydoldıktan sonra, ilk adım **[kullanıcı eklemek ve lisans atamaktır](mdb-add-users.md)**.

> [!NOTE]
> Bu görevi gerçekleştirmek için genel yönetici olmanız gerekir. Şirketinizi Microsoft 365 veya İş için Defender'a kaydolan kişi varsayılan olarak genel yöneticidir. [Roller ve izinler hakkında daha fazla bilgi edinin](mdb-roles-permissions.md).

### <a name="step-2-visit-the-microsoft-365-defender-portal"></a>2. Adım: Microsoft 365 Defender portalını ziyaret edin
 
Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com)), İş için Defender'ı kullandığınız ve yönettiğiniz tek durak mağazadır. Başlamanıza yardımcı olacak açıklama balonları, ilgili bilgileri ortaya çıkartan kartlar ve çeşitli özelliklere ve özelliklere kolay erişim sağlayan bir gezinti çubuğu içerir.

- **[Microsoft 365 Defender portalını ziyaret edin](mdb-get-started.md)**.
- Olaylarınıza erişmek, raporları görüntülemek ve güvenlik ilkelerinizle ayarlarınızı yönetmek için ekranın sol tarafındaki **[gezinti çubuğunu keşfedin](mdb-get-started.md#the-navigation-bar)**.

### <a name="step-3-use-the-setup-wizard-in-defender-for-business-recommended"></a>3. Adım: İş için Defender'da kurulum sihirbazını kullanma (önerilir)

İş için Defender, küçük ve orta ölçekli işletmelere zaman ve çaba kazandırmak için tasarlanmıştır. İlk kurulumu ve yapılandırmayı bir kurulum sihirbazı aracılığıyla yapabilirsiniz. Kurulum sihirbazı, güvenlik ekibinize erişim izni vermenizi, güvenlik ekibiniz için e-posta bildirimlerini ayarlamanıza ve şirketinizin Windows cihazlarını eklemenize yardımcı olur. **[Kurulum sihirbazını kullanın](mdb-use-wizard.md)**.

> [!NOTE]
> Kurulum sihirbazını yalnızca bir kez kullanabilirsiniz.

#### <a name="setup-wizard-flow-what-to-expect"></a>Kurulum sihirbazı akışı: bekleyebileceğinizler

> [!TIP]
> **Kurulum sihirbazını kullanmak isteğe bağlıdır.** (Bkz. [Sihirbazı kullanmazsam ne olur?](mdb-use-wizard.md#what-happens-if-i-dont-use-the-wizard)) Sihirbazı kullanmamayı seçerseniz veya kurulum işleminiz tamamlanmadan önce sihirbaz kapatılırsa, kurulum ve yapılandırma işlemini kendiniz tamamlayabilirsiniz. Bkz. [4. Adım](#step-4-set-up-and-configure-defender-for-business). 

1. **[Kullanıcı izinleri atayın](mdb-roles-permissions.md#view-or-edit-role-assignments)**. Güvenlik ekibinize Microsoft 365 Defender portalına erişim izni verin.

2. Güvenlik ekibiniz için **[e-posta bildirimleri ayarlayın](mdb-email-notifications.md#view-and-edit-email-notifications)**.

3. **[Windows cihazlarını ekleme ve yapılandırma](mdb-onboard-devices.md)**. Cihazları hemen ekleme, bu cihazların ilk günden korunmasına yardımcı olur.

   > [!NOTE]
   > Kurulum sihirbazını kullandığınızda, sistem zaten Intune kayıtlı Windows cihazlarınız olup olmadığını algılar. Bu cihazların tümü veya bazıları için otomatik ekleme kullanmak isteyip istemediğiniz sorulur. Tüm Windows cihazlarını bir kerede ekleyebilir veya ilk başta belirli cihazları seçip daha sonra daha fazla cihaz ekleyebilirsiniz. [Otomatik ekleme hakkında daha fazla bilgi edinin](mdb-use-wizard.md#what-is-automatic-onboarding).
   
   Diğer cihazları eklemek için [4. adıma](#step-4-set-up-and-configure-defender-for-business) bakın.

4.  **[Güvenlik ilkelerinizi görüntüleyin ve düzenleyin](mdb-configure-security-settings.md)**. İş için Defender, şirketinizin cihazlarına uygulanabilecek yeni nesil koruma ve güvenlik duvarı koruması için varsayılan güvenlik ilkelerini içerir. Önceden yapılandırılmış bu güvenlik ilkeleri önerilen ayarları kullanır, böylece cihazlarınız İş için Defender'a eklenir eklenmez korunursunuz. Ayrıca ilkeleri düzenleyebilir veya yeni ilkeler oluşturabilirsiniz.

### <a name="step-4-set-up-and-configure-defender-for-business"></a>4. Adım: İş için Defender'ı ayarlama ve yapılandırma

Kurulum sihirbazını kullanmamayı seçerseniz, İş için Defender'ın [genel kurulum ve yapılandırma işlemini](mdb-setup-configuration.md#the-setup-and-configuration-process) gösteren aşağıdaki diyagrama bakın.

[:::image type="content" source="media/mdb-setup-process-2.png" alt-text="İş için Defender için kurulum ve yapılandırma işlemi.":::](mdb-setup-configuration.md)

Kurulum sihirbazını kullandıysanız ancak Windows dışı cihazlar gibi daha fazla cihaz eklemeniz gerekiyorsa, aşağıdaki yordamda doğrudan 4. adıma gidin:

1. İş için **[Defender'ı yapılandırma ve kullanma gereksinimlerini gözden geçirin](mdb-requirements.md)**. 

2. Microsoft 365 Defender portalında **[roller ve izinler atayın](mdb-roles-permissions.md)**.

   - [İş için Defender'daki roller hakkında bilgi edinin](mdb-roles-permissions.md#roles-in-defender-for-business). 
   - [Güvenlik ekibiniz için rol atamalarını görüntüleyin veya düzenleyin](mdb-roles-permissions.md#view-or-edit-role-assignments).

3. Güvenlik ekibiniz için **[e-posta bildirimleri ayarlayın](mdb-email-notifications.md)**.

   - [E-posta bildirimi türleri hakkında bilgi edinin](mdb-email-notifications.md#types-of-email-notifications).
   - [E-posta bildirim ayarlarını görüntüleyin ve düzenleyin](mdb-email-notifications.md#view-and-edit-email-notifications).

4. **[Cihazları ekleme](mdb-onboard-devices.md)**. İş için Defender ile, şirketinizin cihazlarını eklemek için aralarından seçim yapabileceğiniz çeşitli seçenekler vardır. İlk olarak, eklemek istediğiniz işletim sistemini seçin.

   | Cihaz türü | Ekleme yöntemleri |
   |:---|:---|
   | [Windows istemcileri](mdb-onboard-devices.md) | Windows istemci cihazlarını İş için Defender'a eklemek için aşağıdaki seçeneklerden birini belirleyin:<ul><li>Yerel betik (cihazları Microsoft 365 Defender portalında el ile ekleme için)</li><li>grup ilkesi (zaten grup ilkesi kullanıyorsanız ve bu yöntemi tercih ediyorsanız)</li><li>Microsoft Intune (zaten Intune kullanıyorsanız ve kullanmaya devam etmek istiyorsanız)</li></ul> |
   | [Mac](mdb-onboard-devices.md) | Mac'i eklemek için aşağıdaki seçeneklerden birini belirleyin:<ul><li>Mac için yerel betik (*önerilir*)</li><li>Mac için Microsoft Intune </li></ul><p>Mac'i eklemek için yerel bir betik kullanmanızı öneririz. [Intune'da Mac cihazları için kayıt ayarlayabilirsiniz](/mem/intune/enrollment/macos-enroll) ancak yerel betik, Mac'i İş için Defender'a eklemek için en basit yöntemdir. |
   | Windows Server ve Linux sunucuları | *Windows Server veya Linux Server örneğini ekleme özelliği şu anda önizleme aşamasındadır ve ek lisans gerektirir*. Daha fazla bilgi edinmek için aşağıdaki makalelere bakın: <ul><li>[İş için Defender gereksinimleri](mdb-requirements.md)</li><li>[Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md)</li></ul> |
   | [Mobil cihazlar](mdb-onboard-devices.md) | Android ve iOS/iPadOS cihazları gibi mobil cihazları eklemek için Microsoft Intune kullanın. Bu cihazları Intune kaydetme konusunda yardım almak için aşağıdaki kaynaklara bakın:<ul><li>[Android cihazları kaydetme](/mem/intune/enrollment/android-enroll)</li><li>[iOS veya iPadOS cihazlarını kaydetme](/mem/intune/enrollment/ios-enroll)</li></ul> |

5. **[Güvenlik ilkelerinizi görüntüleyin ve yapılandırın](mdb-configure-security-settings.md)**. Şirketinizin cihazlarını İş için Defender'a ekledikten sonra, sonraki adım güvenlik ilkelerinizi ve ayarlarınızı görüntülemek ve düzenlemektir. İş için Defender, önerilen ayarları kullanan önceden yapılandırılmış güvenlik ilkeleri içerir. Ancak ayarları iş gereksinimlerinize uyacak şekilde düzenleyebilirsiniz.

   | Eylem | Açıklama |
   |:---|:---|
   | [Güvenlik ilkelerinizi ve cihazlarınızı yöneteceğiniz yeri seçin](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices). | [Basitleştirilmiş yapılandırma işlemini](mdb-simplified-configuration.md) seçerseniz güvenlik ilkelerinizi Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) görüntüleyebilir ve yönetebilirsiniz. Ancak bu seçenekle sınırlı değilsiniz. [Intune](/mem/intune/protect/) kullanıyorsanız, güvenlik ilkelerinizi ve cihazlarınızı yönetmek için Microsoft Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz. |
   | [Yeni nesil koruma ilkelerinizi görüntüleyin veya düzenleyin](mdb-configure-security-settings.md#view-or-edit-your-next-generation-protection-policies). | Yeni nesil koruma ayarları gerçek zamanlı koruma, ilk bakışta blok, ağ koruması, istenmeyebilecek uygulamalarda yapılacak eylemler ve virüsten koruma zamanlanmış taramaları içerir.  |
   | [Güvenlik duvarı ilkelerinizi görüntüleyin veya düzenleyin](mdb-configure-security-settings.md#view-or-edit-your-firewall-policies-and-custom-rules). | Güvenlik duvarı koruması, şirketinizin cihazlarına hangi ağ trafiğinin akışına izin verileceğini belirler. [Özel kurallar](mdb-custom-rules-firewall.md) , güvenlik duvarı ilkelerinizin özel durumlarını tanımlamak için kullanılabilir. |
   | [Web içeriği filtrelemeyi ayarlayın](mdb-configure-security-settings.md#set-up-web-content-filtering). | Web içeriği filtrelemesi, güvenlik ekibinizin web sitelerine erişimi yetişkin içeriği, yüksek bant genişliği, yasal sorumluluk, boş zaman veya kategorilere ayrılmamış gibi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. |
   | [Gelişmiş özellikler için ayarları gözden geçirin](mdb-configure-security-settings.md#review-settings-for-advanced-features). | İş için Defender'da güvenlik özellikleri önerilen ayarlar için önceden yapılandırılmıştır. Ayarları iş gereksinimlerinize uyacak şekilde gözden geçirebilir ve düzenleyebilirsiniz. <br/><br/>Gelişmiş özelliklerin ayarlarına erişmek için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler'e** gidin. |
   | Microsoft 365 Defender portalında [diğer ayarları görüntüleyin ve düzenleyin](mdb-configure-security-settings.md#access-your-settings-in-the-microsoft-365-defender-portal). | Cihazlara uygulanan güvenlik ilkelerine ek olarak, İş için Defender'da görüntüleyebileceğiniz ve düzenleyebileceğiniz başka ayarlar da vardır. Örneğin, kullanılacak saat dilimini belirtirsiniz ve cihazları ekleyebilir (veya devre dışı bırakabilirsiniz). |

## <a name="start-using-defender-for-business"></a>İş için Defender'ı kullanmaya başlama

Sonraki 30 gün içinde, aşağıdaki bölümlerde açıklandığı gibi yeni güvenlik özelliklerinizi denemenizi öneririz:

- [Tehdit & Güvenlik Açığı Yönetimi panonuzu kullanma](#use-the-threat--vulnerability-management-dashboard) 
- [Algılanan tehditleri görüntüleme ve tehditlere karşılık verme](#view-and-respond-to-detected-threats)
- [Güvenlik ilkelerini gözden geçirme](#review-security-policies)
- [Devam eden güvenlik yönetimine hazırlanma](#prepare-for-ongoing-security-management)

### <a name="use-the-threat--vulnerability-management-dashboard"></a>Tehdit & Güvenlik Açığı Yönetimi panosunu kullanma

İş için Defender, güvenlik ekibinize zaman ve çaba kazandırmak için tasarlanmış bir Tehdit & Güvenlik Açığı Yönetimi panosu içerir. [Tehdit & Güvenlik Açığı Yönetimi panonuzu kullanın](mdb-view-tvm-dashboard.md).

- Kuruluşunuzdaki cihazlarla ilişkili pozlama puanınızı görüntüleyin.
- Cihazlarla adres bozukluğu olan iletişimler gibi en önemli güvenlik önerilerinizi görüntüleyin, güvenlik duvarı korumasını açın veya Microsoft Defender Virüsten Koruma tanımlarını güncelleştirin.
- Karantinaya gönderilen dosyalar veya cihazlarda bulunan güvenlik açıkları gibi düzeltme etkinliklerini görüntüleyin.

### <a name="view-and-respond-to-detected-threats"></a>Algılanan tehditleri görüntüleme ve tehditlere karşılık verme

Tehditler algılandığında ve uyarılar tetiklendiğinde olaylar oluşturulur. Kuruluşunuzun güvenlik ekibi olayları Microsoft 365 Defender portalında görüntüleyebilir ve yönetebilir. [Algılanan tehditleri görüntüleyin ve yanıt verin](mdb-view-manage-incidents.md). 

- [Olayları görüntüleyin ve yönetin](mdb-view-manage-incidents.md).
- [Tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md).
- [İşlem Merkezi'nde aracılık eylemlerini gözden geçirin](mdb-review-remediation-actions.md).
- [Raporları görüntüleyin ve kullanın](mdb-reports.md).

### <a name="review-security-policies"></a>Güvenlik ilkelerini gözden geçirme

İş için Defender'da güvenlik ayarları cihazlara uygulanan ilkeler aracılığıyla yapılandırılır. İş için Defender, şirketinizin cihazlarını eklendikleri anda korumaya yardımcı olmak, kuruluşunuzu kimlik, cihaz, uygulama ve belge güvenliği tehditlerine karşı korumaya yardımcı olmak için önceden yapılandırılmış ilkeler içerir. [Güvenlik ilkelerini gözden geçirin](mdb-view-edit-create-policies.md).

- [Varsayılan ilkeleriniz hakkında bilgi edinin](mdb-view-edit-create-policies.md#default-policies-in-defender-for-business).
- [Mevcut ilkelerinizi görüntüleyin](mdb-view-edit-create-policies.md#view-your-existing-policies).
- [İlke sırasını anlama](mdb-policy-order.md). 
- [Yeni nesil yapılandırma ayarlarını anlama](mdb-next-gen-configuration-settings.md).
- [Varsayılan güvenlik duvarı ayarlarınızı gözden geçirin](mdb-firewall.md#default-firewall-settings-in-defender-for-business).
- [Yapılandırabileceğiniz güvenlik duvarı ayarlarını anlama](mdb-firewall.md#firewall-settings-you-can-configure-in-defender-for-business).
- [Web içeriği filtrelemeyi ayarlayın](mdb-configure-security-settings.md#set-up-web-content-filtering). Web içeriği filtreleme, güvenlik ekibinizin web sitelerine erişimi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. Varsayılan olarak açık değildir, bu nedenle kuruluşunuz için bu özelliği istiyorsanız ayarlamanız gerekir.
  
### <a name="prepare-for-ongoing-security-management"></a>Devam eden güvenlik yönetimine hazırlanma

Bir cihazda tehdit algılama, yeni cihazlar ekleme ve kuruluşa katılan veya ayrılan çalışanlar gibi yeni güvenlik olayları, güvenliği yönetmenizi gerektirir. İş için Defender'da cihaz güvenliğini yönetmenin birçok yolu vardır.

- Risk düzeylerini, maruz kalma düzeylerini ve sistem durumunu görmek için [eklenen cihazların listesini görüntüleyin](mdb-manage-devices.md#view-the-list-of-onboarded-devices).
- Tehdit algılamaları olan [bir cihazda işlem yapın](mdb-manage-devices.md#take-action-on-a-device-that-has-threat-detections).
- [İş için Defender'a bir cihaz ekleme](mdb-manage-devices.md#onboard-a-device).
- [İş için Defender'dan bir cihazı kullanıma alın](mdb-manage-devices.md#offboard-a-device).

## <a name="additional-resources"></a>Ek kaynaklar

- [İş için Defender'a genel bakış](mdb-overview.md)
- [İş için Defender'da öğreticiler ve simülasyonlar](mdb-tutorials.md)
- [Video: Küçük & Orta Ölçekli İşletmeler için Enterprise-Grade Koruması](https://youtu.be/umhUNzMqZto)
- [İş için Defender'ı edinin](get-defender-business.md)
