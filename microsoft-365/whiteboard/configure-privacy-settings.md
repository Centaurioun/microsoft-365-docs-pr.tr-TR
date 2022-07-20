---
title: Microsoft Whiteboard'da gizlilik ayarlarını yapılandırma
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Microsoft Whiteboard'da uyumluluk ve gizlilik ayarlarını yapılandırma hakkında bilgi edinin.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2708d3eda92f3d29ea9ad6ee15e518d32d93a22
ms.sourcegitcommit: 49c275f78664740988bbc4ca4b14d3ad758e1468
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66882794"
---
# <a name="configure-privacy-settings-in-microsoft-whiteboard"></a>Microsoft Whiteboard'da gizlilik ayarlarını yapılandırma

>[!NOTE]
> Siz veya kullanıcılarınız varsayılan gizlilik ayarları, isteğe bağlı bağlı deneyimler ve tanılama verilerinin nasıl toplandığı hakkında daha fazla bilgi edinmek istiyorsanız, bunları [Microsoft Whiteboard gizlilik ve uyumluluğuna](https://support.microsoft.com/office/privacy-and-compliance-ed9f0de9-71be-44c2-837d-e0f448660be1) yönlendirin.

Kuruluşunuzun Microsoft Whiteboard yöneticisiyseniz aşağıdakileri denetleyebilirsiniz:

- Kullanıcının cihazında çalışan Whiteboard istemci yazılımı hakkında toplanan ve Microsoft'a gönderilen tanılama verileri düzeyi.

- Beyaz Tahta'daki isteğe bağlı bağlı deneyimlerin kullanıcılarınız tarafından kullanılıp kullanılamadığı.

Tanılama verilerinin düzeyini yapılandırmak için yönetici hesabınızla [Microsoft 365 yönetim merkezi](/microsoft-365/admin/admin-overview/admin-center-overview?view=o365-worldwide) oturum açın. Yönetim merkezi giriş sayfasında Tüm **> Ayarlarını göster > Kuruluş ayarları > Whiteboard'a** gidin.

İsteğe bağlı bağlı deneyimlerin kullanılabilirliğini yapılandırmak için [Microsoft 365 Uygulamaları yönetim merkezindeki](https://config.office.com) [Office bulut ilkesi hizmetini](/deployoffice/admincenter/overview-office-cloud-policy-service) kullanın. Yönetici hesabınızla oturum açın ve **Özelleştirme > İlke Yönetimi'ne** gidin. Yapılandırmak istediğiniz ilkenin adı: **Office'te isteğe bağlı ek bağlı deneyimlerin kullanılmasına izin verin**.

## <a name="diagnostic-data-setting-for-your-organization"></a>Kuruluşunuz için tanılama verileri ayarı

Kuruluşunuzdaki cihazlarda çalışan Whiteboard istemci yazılımı hakkında toplanan ve Microsoft'a gönderilen tanılama verilerinin düzeyini seçebilirsiniz. Microsoft 365 yönetim merkezi ayarını değiştirmediğiniz sürece isteğe bağlı tanılama verileri Microsoft'a gönderilir. Bize isteğe bağlı tanılama verilerini göndermeyi seçerseniz, bu durum gerekli tanılama verilerini de içerir.

**Gerekli** veya **İsteğe Bağlı'ya** ek olarak **, Hiçbiri** seçeneği de vardır. Bu seçeneği belirlerseniz kullanıcının cihazında çalışan Whiteboard istemci yazılımıyla ilgili tanılama verileri Microsoft'a gönderilmez. Ancak bu seçenek, Microsoft'un Whiteboard kullanırken kullanıcılarınızın karşılaşabileceği sorunları algılama, tanılama ve düzeltme becerisini önemli ölçüde sınırlar.

Kurumsal kimlik bilgileriyle (bazen iş veya okul hesabı olarak da adlandırılır) Whiteboard'da oturum açtıklarında kullanıcılarınız cihazlarının tanılama veri düzeyini değiştiremez. Ancak Whiteboard'da kişisel outlook.com e-posta adresi gibi bir Microsoft hesabıyla oturum açtılarsa **, Ayarlar > Gizlilik ve güvenlik'e** giderek cihazlarında tanılama veri düzeyini değiştirebilirler.

## <a name="optional-connected-experiences-setting-for-your-organization"></a>Kuruluşunuz için isteğe bağlı bağlı deneyimler ayarı

Whiteboard'da isteğe bağlı bağlı deneyimlerin kullanıcılarınız için kullanılabilir olup olmayacağını seçebilirsiniz. Bu bağlı deneyimler, Microsoft 365 yönetim merkezi ayarını değiştirmediğiniz sürece kullanıcılarınız tarafından kullanılabilir. 

Bu bağlı deneyimler farklıdır, çünkü kuruluşunuzun Microsoft ile yapmış olduğu ticari anlaşma kapsamında değildir. İsteğe bağlı bağlı deneyimler Microsoft tarafından kullanıcılarınıza doğrudan sunulur ve [Çevrimiçi Hizmet Sözleşmesi](https://www.microsoft.com/licensing/product-licensing/products) yerine [Microsoft Hizmet Sözleşmesi](https://www.microsoft.com/servicesagreement)’ne tabidir.

Bu isteğe bağlı bağlı deneyimleri kullanıcılarınıza sunmayı seçseniz bile, kullanıcılarınız **Ayarlar > Gizlilik ve güvenlik'e** giderek bunları grup olarak kapatma seçeneğine sahiptir. Kullanıcılarınız, kişisel outlook.com e-posta adresi gibi bir Microsoft hesabıyla oturum açtıklarında değil, beyaz tahtada kurumsal kimlik bilgileriyle (bazen iş veya okul hesabı olarak da adlandırılır) oturum açtıklarında bu seçeneği kullanır.

## <a name="required-diagnostic-data-events-collected-by-whiteboard"></a>Whiteboard tarafından toplanan gerekli tanılama verileri olayları

Her olaydaki veri alanlarının listesi de dahil olmak üzere Whiteboard tarafından toplanan gerekli tanılama veri olayları aşağıda verilmiştir.

**Intentional.CanvasObject.Ink.DrawFirstStroke**

Toplanan ilk mürekkep Microsoft Whiteboard'daki bir panoya eklenir. Bu bilgiler, tahtaya mürekkep eklemeyle ilişkili hataları yakalamak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **Eylem** – mürekkep vuruşu türü
- **Kaynak** – mürekkep vuruşu için giriş yöntemi

**Intentional.SurfSide.ActivationProtocol.LoadFromUri**

Microsoft Whiteboard başka bir uygulama veya işlemden gelen bir çağrıyla başlatıldığında toplanır. Başka bir uygulama veya işlem tarafından düzgün bir şekilde çağrıldığında Whiteboard başlatılmazsa bu bilgilerin yakalanması kritik önem taşır. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **ApplicationExecutionState** – Etkinleştirme protokolü gerçekleştiğinde uygulamanın yürütme durumu
- **IsSignedIn** – kullanıcı kimlik doğrulama durumudur
- **Kind** – Whiteboard'un başlatıldığı uygulama veya işlem

**Intentional.Whiteboard.Init.DisplayWhiteboard**

Microsoft Whiteboard'un oturum başına bir istemcide ilk kez görüntülendiği zaman toplanır. Bu bilgiler başlatma sorunlarını yakalamak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **IsPrelaunched** – başlatma öncesi durumu
- **IsProtocolActivation** – uygulama başlatma türü

**Intentional.Whiteboard.Init.StartApp**

Önceki durum kilitlenmeden sona erdikten sonra Microsoft Whiteboard her başlatıldığında toplanır. Bu bilgiler kilitlenme sorunlarını yakalamak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **İlk Başlangıç** – uygulama istemcide ilk kez başlatıldı

**Intentional.Whiteboard.KeyCategory.UseCategory**

Microsoft Whiteboard'da bir özellik kullanıcı/oturum/beyaz tahta başına ilk kez (ve yalnızca ilk kez) kullanıldığında toplanır. Bu bilgiler, anahtar kategorilerin kullanıldığından emin olmak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **CategoryName** – Anahtar kategorisinin adı

**Intentional.Whiteboard.KeyFeature.UseFeature**

Microsoft Whiteboard'da bir özellik kullanıcı/oturum/beyaz tahta başına ilk kez (ve yalnızca ilk kez) kullanıldığında toplanır. Bu bilgiler, özelliklerin çağrıldığında ve kullanıldığından emin olmak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **FeatureName** – Anahtar özelliğinin adı

**Intentional.Whiteboard.SafeBoot.StartApp**

Önceki durum bir kilitlenmeyle sona erdikten sonra Microsoft Whiteboard her başlatıldığında toplanır. Bu bilgiler kilitlenme sorunlarını yakalamak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **İlk Başlangıç** – uygulama istemcide ilk kez başlatıldı

**Intentional.Whiteboard.Scrub.LoadSettings**

Microsoft Whiteboard her başlatıldığında toplanır. Bu bilgiler, kullanıcı tarafından yapılandırılan ayarlarla ilişkili hataları yakalamak için kritik öneme sahiptir. Microsoft, Microsoft Whiteboard'un beklendiği gibi çalıştığından emin olmak amacıyla sorunu tanılamak için bu verileri kullanıyor.

- **ActivePen** – kalem modu durumu
- **CollectFullTelemetryWithoutSignIn** – oturum açma etkinleştirmesi olmadan tam telemetri koleksiyonu
- **DefaultWhiteboardBackgroundColor** – varsayılan pano arka plan rengi
- **DefaultWhiteboardBackgroundPattern** – varsayılan pano arka plan deseni
- **FlightStatus** – uçuş durumu
- **InkToShape** – mürekkeple şekle etkinleştirme
- **InkToTable** – mürekkep-tablo etkinleştirme
- **SignInEnabled** – kullanıcı oturum açma etkinleştirmesi
- **SharingWithoutSignInEnabled** – paylaşım panosu etkinleştirmesi
- **ToolbarLocation** – ekranda varsayılan araç çubuğu konumu
- **TeamSettingsSource** – Teams ayarları etkinleştirme
