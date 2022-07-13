---
title: İş için Microsoft Defender'de kurulum sihirbazını kullanma
description: İş için Defender, İş için Defender'ın ilk kez kullanıldığı bir sihirbazla kurulumu kolaylaştırır. Kurulum sihirbazının nasıl çalıştığını görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 0f37dd86cef388dfe183557ccf269810ef522445
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772443"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'da kurulum sihirbazını kullanma

İş için Defender, küçük ve orta ölçekli işletmelere zaman ve çaba kazandırmak için tasarlanmıştır. Örneğin, bir kurulum sihirbazıyla ilk kurulumu ve yapılandırmayı yapabilirsiniz. Kurulum sihirbazı, güvenlik ekibinize erişim verme, güvenlik ekibiniz için e-posta bildirimleri ayarlama ve şirketinizin Windows cihazlarını ekleme konusunda size yol gösterir.


> [!TIP]
> Kurulum sihirbazını kullanmak isteğe bağlıdır. Kurulum ve yapılandırma işlemi boyunca el ile çalışmayı seçebilirsiniz. Daha fazla bilgi için şu makalelere bakın:
> - [Sihirbazı kullanmazsam ne olur?](#what-happens-if-i-dont-use-the-wizard)
> - [İş için Defender'ı ayarlama ve yapılandırma](mdb-setup-configuration.md)

## <a name="how-to-start-the-setup-wizard"></a>Kurulum sihirbazını başlatma

Kurulum sihirbazı, şirketinizdeki biri Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) ilk kez oturum açtığında çalışacak şekilde tasarlanmıştır. 

Şirketiniz Microsoft 365 İş Ekstra kullanıyorsa, birisi **Endpoints** > **Cihaz envanterine** ilk kez gittiğinde İş için Defender kurulum sihirbazı çalıştırılır. 

Kurulum sihirbazı başlangıç ekranı aşağıdaki görüntüye benzer:

:::image type="content" source="media/mdb-wizard-start.png" alt-text="İş için Defender'ı ayarlamak için sihirbaz giriş ekranının ekran görüntüsü.":::

## <a name="the-setup-wizard-flow"></a>Kurulum sihirbazı akışı

> [!IMPORTANT]
> Kurulum sihirbazını çalıştırmak için genel yönetici olmanız gerekir. Şirketinizi Microsoft 365 veya İş için Defender'a kaydolan kişi varsayılan olarak genel yöneticidir.

Kurulum sihirbazı, İş için Defender'ı hızlı ve verimli bir şekilde ayarlamanıza ve yapılandırmanıza yardımcı olacak şekilde tasarlanmıştır. Sihirbaz aşağıdaki adımlarda size yol göstermelidir:

1. **Kullanıcı izinleri atayın**. Bu adımda, güvenlik ekibinize Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) erişim izni verirsiniz. Bu portal, sizin ve güvenlik ekibinizin güvenlik özelliklerinizi yöneteceğiniz, uyarıları görüntüleyebileceğiniz ve algılanan tehditler üzerinde gerekli eylemleri gerçekleştireceğiniz yerdir. Portal erişimi, belirli izinleri ima eden roller aracılığıyla verilir.

   İş için Defender'da güvenlik ekibinizin üyelerine aşağıdaki üç rolden biri atanabilir:<br/>
   
   - **Genel Yönetici**: Genel yönetici, Microsoft 365 kiracınızdaki tüm ayarları görüntüleyebilir ve düzenleyebilir. Genel yönetici, şirketinizin Microsoft 365 aboneliği için ilk kurulumu ve yapılandırmayı yapar. 
   - **Güvenlik Yöneticisi: Güvenlik** yöneticisi güvenlik ayarlarını görüntüleyebilir ve düzenleyebilir ve tehditler algılandığında eylem gerçekleştirebilir.
   - **Güvenlik Okuyucusu: Güvenlik** okuyucusu raporlardaki bilgileri görüntüleyebilir, ancak hiçbir güvenlik ayarlarını değiştiremez. 

   [Roller ve izinler hakkında daha fazla bilgi edinin](mdb-roles-permissions.md). 

2. **E-posta bildirimlerini ayarlayın**. Bu adımda, güvenlik ekibiniz için e-posta bildirimleri ayarlayabilirsiniz. Ardından, bir uyarı oluşturulduğunda veya yeni bir güvenlik açığı bulunduğunda, güvenlik ekibiniz masalarından uzakta olsalar bile bu uyarıyı kaçırmaz. [E-posta bildirimleri hakkında daha fazla bilgi edinin](mdb-email-notifications.md). 

3. **Windows cihazlarını ekleme ve yapılandırma**. Bu adımda, şirketinizin Windows cihazlarını hızlı bir şekilde İş için Defender'a ekleyebilirsiniz. Cihazları hemen eklemek, bu cihazların ilk günden korunmasına yardımcı olur. 

   - **Zaten Microsoft Intune kullanıyorsanız** ve şirketinizde Intune kayıtlı cihazlar varsa, kayıtlı Windows cihazlarınızın bazıları veya tümü için [otomatik ekleme](#what-is-automatic-onboarding) kullanmak isteyip istemediğiniz sorulur. Otomatik ekleme, Intune ile İş için Defender arasında bir bağlantı kurar ve ardından Windows cihazlarını İş için Defender'a sorunsuz bir şekilde ekler. 
   - **Henüz Intune kullanmıyorsanız**[, cihazları İş için Defender'a ekleyebilirsiniz](mdb-onboard-devices.md). 
   
   [cihazları İş için Defender'a ekleme hakkında daha fazla bilgi edinin](mdb-onboard-devices.md).
   
4. **Güvenlik ilkelerinizi yapılandırın**. İş için Defender, şirketinizin cihazlarına uygulanabilecek yeni nesil koruma ve güvenlik duvarı koruması için varsayılan güvenlik ilkelerini içerir. Bu varsayılan ilkeler önerilen ayarları kullanır ve cihazlarınız için güçlü koruma sağlamak üzere tasarlanmıştır. Kendi güvenlik ilkelerinizi de oluşturabilirsiniz. Ayrıca, zaten Intune kullanıyorsanız, güvenlik ilkelerinizi yönetmek için Microsoft Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz.

   [Güvenlik ilkelerinizi ve ayarlarınızı görüntüleyin ve düzenleyin](mdb-configure-security-settings.md).

## <a name="what-is-automatic-onboarding"></a>Otomatik ekleme nedir?

Otomatik ekleme, Windows cihazlarını İş için Defender'a eklemenin basitleştirilmiş bir yoludur. Otomatik ekleme yalnızca Microsoft Intune zaten kayıtlı olan Windows cihazları için kullanılabilir. 

Kurulum sihirbazını kullanırken sistem, Windows cihazlarının Intune'a zaten kayıtlı olup olmadığını algılar. Bu cihazların tümü veya bazıları için otomatik ekleme kullanmak isteyip istemediğiniz sorulur. Tüm Windows cihazlarını aynı anda ekleyebilir veya başlamak için belirli cihazları seçebilir ve daha sonra daha fazla cihaz ekleyebilirsiniz. 

Diğer cihazları eklemek için bkz. [Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md).

> [!TIP]
> - "Tüm cihazlar kaydedildi" seçeneğini belirlemenizi öneririz. Bu şekilde, Windows cihazları daha sonra Intune kaydedildiğinde otomatik olarak İş için Defender'a eklenir. 
> - Endpoint Manager yönetim merkezinde güvenlik ilkelerini ve ayarlarını yönetiyorsanız cihazlarınızı, ilkelerinizi ve ayarlarınızı yönetmek için Microsoft 365 Defender portalına geçmenizi öneririz. Daha fazla bilgi edinmek için bkz. [Güvenlik ilkelerinin ve cihazların yönetileceği yeri seçme](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices).

## <a name="what-happens-if-i-dont-use-the-wizard"></a>Sihirbazı kullanmazsam ne olur?

Kurulum sihirbazını kullanmak isteğe bağlıdır. Sihirbazı kullanmamayı seçerseniz veya kurulum işleminiz tamamlanmadan önce sihirbaz kapatılırsa, kurulum ve yapılandırma işlemini kendiniz tamamlayabilirsiniz. 

Aşağıdaki adımları görmek için bkz. [İş için Defender'ı ayarlama ve yapılandırma](mdb-setup-configuration.md) :

1. Güvenlik ekibinizin Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) erişebilmesi ve kullanabilmesi için **[roller ve izinler atayın](mdb-roles-permissions.md)**.

2. Yeni uyarılar veya güvenlik açıklarıyla ilgili döngüde olmaları **[için güvenlik ekibiniz için e-posta bildirimleri ayarlayın](mdb-email-notifications.md)**.

3. **[Cihazları,](mdb-onboard-devices.md)** İş için Defender tarafından korunacak şekilde ekleme.

4. Yeni nesil koruma, güvenlik duvarı koruması ve web içeriği filtreleme gibi **[güvenlik ilkelerinizi yönetin](mdb-configure-security-settings.md)**.

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'a daha fazla cihaz ekleme](mdb-onboard-devices.md)
- [İş için Defender'da güvenlik ilkelerinizi ve ayarlarınızı görüntüleme ve düzenleme](mdb-configure-security-settings.md)