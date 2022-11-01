---
title: İş için Microsoft Defender deneme kullanım kılavuzu
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.collection:
- m365-security
- tier1
ms.localizationpriority: high
ms.date: 10/07/2022
ms.service: microsoft-365-security
ms.subservice: mdb
search.appverid:
- MOE150
- MET150
description: Bu kılavuzla İş için Defender denemenizden en iyi şekilde emin olun. Hızlı bir şekilde ayarlayın ve yeni güvenlik özelliklerinizi kullanmaya başlayın.
ms.custom: trial-playbook
ms.openlocfilehash: edcc5cebcce868cd11806d0a14cc33dd87f6f4fa
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804125"
---
# <a name="trial-user-guide-microsoft-defender-for-business"></a>Deneme kullanım kılavuzu: İş için Microsoft Defender

**İş için Defender deneme kullanım kılavuzuna hoş geldiniz!**

Bu kılavuz, ücretsiz denemenizin temel özelliklerini ayarlamanıza ve kullanmanıza yardımcı olur. Microsoft Defender ekibinin bu makaledeki önerileri kullanarak, İş için Defender'ın güvenliğinizi geleneksel virüsten korumadan yeni nesil koruma, uç nokta algılama ve yanıt ve güvenlik açığı yönetimine yükseltmeye nasıl yardımcı olabileceğini öğrenin.

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
> **Kurulum sihirbazını kullanmak isteğe bağlıdır.** (Bkz. [Sihirbazı kullanmazsam ne olur?](mdb-use-wizard.md#what-happens-if-i-dont-use-the-wizard)). Sihirbazı kullanmamayı seçerseniz veya kurulum işleminiz tamamlanmadan önce sihirbaz kapatılırsa, kurulum ve yapılandırma işlemini kendiniz tamamlayabilirsiniz. Bkz [. 4. Adım: İş için Defender'ı ayarlama ve yapılandırma](#step-4-set-up-and-configure-defender-for-business).

1. **[Kullanıcı izinleri atayın](mdb-roles-permissions.md#view-or-edit-role-assignments)**. Güvenlik ekibinize Microsoft 365 Defender portalına erişim izni verin.

2. Güvenlik ekibiniz için **[e-posta bildirimleri ayarlayın](mdb-email-notifications.md#view-and-edit-email-notifications)**.

3. **[Windows cihazlarını ekleme ve yapılandırma](mdb-onboard-devices.md)**. Cihazları hemen ekleme, bu cihazların ilk günden korunmasına yardımcı olur.

   > [!NOTE]
   > Kurulum sihirbazını kullandığınızda, sistem zaten Intune kayıtlı Windows cihazlarınız olup olmadığını algılar. Bu cihazların tümü veya bazıları için otomatik ekleme kullanmak isteyip istemediğiniz sorulur. Tüm Windows cihazlarını bir kerede ekleyebilir veya ilk başta belirli cihazları seçip daha sonra daha fazla cihaz ekleyebilirsiniz. [Otomatik ekleme hakkında daha fazla bilgi edinin](mdb-use-wizard.md#what-is-automatic-onboarding).

   Diğer cihazları eklemek için bkz [. 4. Adım: İş için Defender'ı ayarlama ve yapılandırma](#step-4-set-up-and-configure-defender-for-business).

4. **[Güvenlik ilkelerinizi görüntüleyin ve düzenleyin](mdb-configure-security-settings.md)**. İş için Defender, şirketinizin cihazlarına uygulanabilecek yeni nesil koruma ve güvenlik duvarı koruması için varsayılan güvenlik ilkelerini içerir. Önceden yapılandırılmış bu güvenlik ilkeleri önerilen ayarları kullanır, böylece cihazlarınız İş için Defender'a eklenir eklenmez korunursunuz. Ayrıca ilkeleri düzenleyebilir veya yeni ilkeler oluşturabilirsiniz.

### <a name="step-4-set-up-and-configure-defender-for-business"></a>4. Adım: İş için Defender'ı ayarlama ve yapılandırma

Kurulum sihirbazını kullanmamayı seçerseniz, İş için Defender'ın [genel kurulum ve yapılandırma işlemini](mdb-setup-configuration.md#the-setup-and-configuration-process) gösteren aşağıdaki diyagrama bakın.

[:::image type="content" source="media/mdb-setup-process-2.png" alt-text="İş için Defender için kurulum ve yapılandırma işlemi.":::](mdb-setup-configuration.md)

Kurulum sihirbazını kullandıysanız ancak Windows dışı cihazlar gibi daha fazla cihaz eklemeniz gerekiyorsa, aşağıdaki yordamda doğrudan [4. adıma](mdb-onboard-devices.md) gidin:

1. İş için **[Defender'ı yapılandırma ve kullanma gereksinimlerini gözden geçirin](mdb-requirements.md)**.

2. Microsoft 365 Defender portalında **[roller ve izinler atayın](mdb-roles-permissions.md)**.

   - [İş için Defender'daki roller hakkında bilgi edinin](mdb-roles-permissions.md#roles-in-defender-for-business). 
   - [Güvenlik ekibiniz için rol atamalarını görüntüleyin veya düzenleyin](mdb-roles-permissions.md#view-or-edit-role-assignments).

3. Güvenlik ekibiniz için **[e-posta bildirimleri ayarlayın](mdb-email-notifications.md)**.

   - [E-posta bildirimi türleri hakkında bilgi edinin](mdb-email-notifications.md#types-of-email-notifications).
   - [E-posta bildirim ayarlarını görüntüleyin ve düzenleyin](mdb-email-notifications.md#view-and-edit-email-notifications).

4. **[Cihazları ekleme](mdb-onboard-devices.md)**. Windows ve Mac istemcilerini eklemek için yerel bir betik kullanabilirsiniz.

5. **[Güvenlik ilkelerinizi görüntüleyin ve yapılandırın](mdb-configure-security-settings.md)**. Şirketinizin cihazlarını İş için Defender'a ekledikten sonra, sonraki adım güvenlik ilkelerinizi ve ayarlarınızı görüntülemek ve düzenlemektir. 

İş için Defender, önerilen ayarları kullanan önceden yapılandırılmış güvenlik ilkeleri içerir. Ancak ayarları iş gereksinimlerinize uyacak şekilde düzenleyebilirsiniz.

Gözden geçirilip yapılandırılan güvenlik ilkeleri şunlardır:

- Şirketinizin cihazları için virüsten koruma ve kötü amaçlı yazılımdan korumayı belirleyen [yeni nesil koruma ilkeleri](mdb-configure-security-settings.md#view-or-edit-your-next-generation-protection-policies)
- Şirketinizin cihazlarına hangi ağ trafiğinin akışına izin verileceğini belirleyen [güvenlik duvarı koruması ve kuralları](mdb-configure-security-settings.md#view-or-edit-your-firewall-policies-and-custom-rules)
- [Kişilerin](mdb-configure-security-settings.md#set-up-web-content-filtering)yetişkinlere yönelik içerik veya yasal sorumluluk gibi kategorilere göre belirli web sitelerini (URL' ler) ziyaret etmesini engelleyen web içeriği filtreleme
- Blok modunda otomatik araştırma ve yanıt ile uç nokta algılama ve yanıt (EDR) gibi [gelişmiş özellikler](mdb-configure-security-settings.md#review-settings-for-advanced-features)

## <a name="start-using-defender-for-business"></a>İş için Defender'ı kullanmaya başlama

Önümüzdeki 30 gün boyunca, ürün ekibinden deneyebileceğiniz önemli özelliklerle ilgili yönergeler aşağıda verilmiştir:

1. [Microsoft Defender Güvenlik Açığı Yönetimi panonuzu kullanın](#1-use-the-defender-vulnerability-management-dashboard). 

2. [Algılanan tehditleri görüntüleyin ve yanıt verin](#2-view-and-respond-to-detected-threats).

3. [Güvenlik ilkelerini gözden geçirin](#3-review-security-policies).

4. [Devam eden güvenlik yönetimine hazırlanın](#4-prepare-for-ongoing-security-management).

5. [Belge Bırakma Arka Kapı öğreticisini deneyin](#5-try-the-document-drops-backdoor-tutorial).

### <a name="1-use-the-defender-vulnerability-management-dashboard"></a>1. Defender Güvenlik Açığı Yönetimi panosunu kullanma

İş için Defender, güvenlik ekibinize zaman ve çaba kazandırmak için tasarlanmış bir Defender Güvenlik Açığı Yönetimi panosu içerir. [Defender Güvenlik Açığı Yönetimi panonuzu kullanmayı](mdb-view-tvm-dashboard.md) öğrenin.

- Kuruluşunuzdaki cihazlarla ilişkili pozlama puanınızı görüntüleyin.
- Cihazlarla adres engelli iletişimler gibi en önemli güvenlik önerilerinizi görüntüleyin, güvenlik duvarı korumasını açın veya Virüsten Koruma tanımlarını Microsoft Defender güncelleştirin.
- Karantinaya gönderilen dosyalar veya cihazlarda bulunan güvenlik açıkları gibi düzeltme etkinliklerini görüntüleyin.

### <a name="2-view-and-respond-to-detected-threats"></a>2. Algılanan tehditleri görüntüleme ve yanıtlama

Tehditler algılandığında ve uyarılar tetiklendiğinde olaylar oluşturulur. Kuruluşunuzun güvenlik ekibi olayları Microsoft 365 Defender portalında görüntüleyebilir ve yönetebilir. [Algılanan tehditleri görüntülemeyi ve yanıtlamayı](mdb-view-manage-incidents.md) öğrenin. 

- [Olayları görüntüleyin ve yönetin](mdb-view-manage-incidents.md).
- [Tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md).
- [İşlem Merkezi'nde aracılık eylemlerini gözden geçirin](mdb-review-remediation-actions.md).
- [Raporları görüntüleyin ve kullanın](mdb-reports.md).

### <a name="3-review-security-policies"></a>3. Güvenlik ilkelerini gözden geçirin

İş için Defender'da güvenlik ayarları cihazlara uygulanan ilkeler aracılığıyla yapılandırılır. İş için Defender, şirketinizin cihazlarını eklendikleri anda korumaya yardımcı olmak, kuruluşunuzu kimlik, cihaz, uygulama ve belge güvenliği tehditlerine karşı korumaya yardımcı olmak için önceden yapılandırılmış ilkeler içerir. 

[Güvenlik ilkelerini gözden geçirmeyi](mdb-view-edit-create-policies.md) öğrenin.

### <a name="4-prepare-for-ongoing-security-management"></a>4. Devam eden güvenlik yönetimine hazırlanma

Bir cihazda tehdit algılama, yeni cihazlar ekleme ve kuruluşa katılan veya ayrılan çalışanlar gibi yeni güvenlik olayları, güvenliği yönetmenizi gerektirir. İş için Defender'da cihaz güvenliğini yönetmenin birçok yolu vardır.

- Risk düzeylerini, maruz kalma düzeylerini ve sistem durumunu görmek için [eklenen cihazların listesini görüntüleyin](mdb-manage-devices.md#view-the-list-of-onboarded-devices).
- Tehdit algılamaları olan [bir cihazda işlem yapın](mdb-manage-devices.md#take-action-on-a-device-that-has-threat-detections).
- [İş için Defender'a bir cihaz ekleme](mdb-manage-devices.md#onboard-a-device).
- [İş için Defender'dan bir cihazı kullanıma alın](mdb-manage-devices.md#offboard-a-device).

### <a name="5-try-the-document-drops-backdoor-tutorial"></a>5. Belge Bırakma Arka Kapı öğreticisini deneyin

Bir öğreticiyi deneyerek İş için Defender'ın nasıl çalıştığını hızla görün.

Bir test cihazına dosya tabanlı kötü amaçlı yazılım getiren bir saldırının benzetimini yapmak. Öğreticide simülasyon dosyasının nasıl kullanılacağı ve Microsoft 365 Defender portalında nelerin izleyebileceğiniz açıklanır.

>[!NOTE]
> Bu öğretici, Test cihazınıza Microsoft Word'un yüklenmesini gerektirir.

Öğreticiye erişmek için aşağıdakileri yapın:

1. [Microsoft 365 Defender portalına](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesindeki **Uç Noktalar'ın** altında **Öğreticiler'i** seçin.

3. **Belge Bırakma Arka Kapı'yı** seçin.

## <a name="additional-resources"></a>Ek kaynaklar

- [İş için Defender'a genel bakış](mdb-overview.md)
- [İş için Defender'da öğreticiler ve simülasyonlar](mdb-tutorials.md)
- [Video: Küçük & Orta Ölçekli İşletmeler için Enterprise-Grade Koruması](https://youtu.be/umhUNzMqZto)
- [İş için Defender'ı edinin](get-defender-business.md)
