---
title: Kampanyalar için Microsoft 365 kurulumuna genel bakış
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Kampanyalar veya diğer işletmeler için Microsoft 365 İş kurulumuna genel bakış
ms.openlocfilehash: 6ea72b060d97185dcd4607e911f087c8791916b1
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67739024"
---
# <a name="setup-for-microsoft-365-business-for-campaigns"></a>Kampanyalar için Microsoft 365 İş kurulumu

[Kampanyalar için Microsoft 365'e abone](get-microsoft-365-campaigns.md) olduktan sonra, sonraki adımınız her şeyi ayarlamaktır.

## <a name="before-you-begin"></a>Başlamadan önce

Kurulum işleminize başlamadan önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:

| Gereksinim | Açıklama |
|:---|:---|
| Abonelik | kampanyalar için Microsoft 365 İş Ekstra veya Microsoft 365 <br/><br/> Deneme sürümü başlatmak veya aboneliğinizi satın almak için aşağıdaki makalelere bakın: <br/>- [Microsoft 365 İş Ekstra alın](get-microsoft-365-business-premium.md)<br/>- [Kampanyalar için Microsoft 365'i edinin](get-microsoft-365-campaigns.md) |
| İzinler  | İlk kurulum işlemini tamamlamak için Genel Yönetici olmanız gerekir. [Yönetici rolleri hakkında daha fazla bilgi edinin](../admin/add-users/about-admin-roles.md). |
| Tarayıcı gereksinimleri | Microsoft Edge, Safari, Chrome veya Firefox. [Tarayıcı gereksinimleri hakkında daha fazla bilgi edinin](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources#coreui-heading-uyetipy).  |
| İşletim sistemleri (istemci) | **Windows**: Windows 11, Windows 10, Windows 8.1<br/>**macOS: macOS'un** en son üç sürümünden biri 
| İşletim sistemleri (sunucular) | Windows Server veya Linux Server <br/>- İş için Microsoft Defender sunucuları gerektirir (şu anda önizleme aşamasındadır)<br/>- Bkz. [İş için Microsoft Defender sunucuları alma (önizleme).](../security/defender-business/get-defender-business-servers.md)  |

> [!TIP]
> Microsoft 365, Office ve sistem gereksinimleri hakkında daha ayrıntılı bilgi için bkz. [Microsoft 365 ve Office Kaynakları](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).

## <a name="sign-in-to-microsoft-365-for-campaigns"></a>Kampanyalar için Microsoft 365'te oturum açma

Kampanyalar için Microsoft 365'e (veya Microsoft 365 İş Ekstra) kaydolduysanız, Microsoft 365 yöneticisi (Genel Yönetici olarak da adlandırılır) olarak belirlenirsiniz. Bu, oturum açmanızı ve sistemi başlatmanızı sağlar.

Oturum açma şu şekilde yapılır:

1. [Kampanyalar için Microsoft 365'e kaydolduğunda](m365-campaigns-sign-up.md) kullandığınız e-posta adresine gönderdiğimiz kullanıcı adını ve parolayı bulun.

2. Tarayıcıda konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank"><https://admin.microsoft.com></a>gidin.

3. Kullanıcı adınızı ve parolanızı yazın. **Oturum Aç**'ı seçin.

4. Sayfanın sağ üst kısmında **Denetimde Önizleme'yi** bulun. [Kampanyanız için Korumayı artırma](m365bp-security-overview.md) başlığında açıklanan tüm denetimleri kullanabilmek için **Önizleme açık'ı** seçin.

## <a name="how-your-staff-will-sign-in"></a>Personeliniz nasıl oturum açar?

Kampanyalar için Microsoft 365 (veya Microsoft 365 İş Ekstra) aboneliğinize eklenen kullanıcılar aşağıdaki adımları kullanarak oturum açabilir:

1. <a href="https://office.com" target="_blank"><https://Office.com></a> adımına gidin.

2. Hesabın kullanıcı adını ve parolasını kullanarak oturum açın. Kullanıcılar, kullanıcı olarak eklendiklerinde aldıkları e-postada bu bilgilere sahip olur. E-postayı bulamıyorsa bkz. [Kullanıcı davet e-postası almadı](../admin/simplified-signup/admin-invite-business-standard.md#i-shared-an-email-invite-but-the-user-didnt-receive-the-email).

> [!TIP]
> Personelinize oturum açma, Office uygulamalarını alma ve dosyaları kaydetme, kopyalama ve paylaşma konusunda yardım almak için [Çalışan hızlı kurulum kılavuzunun](../admin/setup/employee-quick-setup.md) bağlantısını sağlayın.

## <a name="customize-your-sign-in-page-with-a-privacy-and-consent-notice"></a>Gizlilik ve onay bildirimiyle oturum açma sayfanızı özelleştirme

İşletmeniz veya kampanyanız, oturum açma sayfanıza gizlilik ve onay bildirimi ekleyerek kolluk kuvvetlerinin çevrimiçi suçlulara karşı yasal ücretlendirme yapmasını kolaylaştırabilir.

Oturum açma sayfanızı markanızla özelleştirebilirsiniz. Ayrıca, kullanıcılarınızın oturum açmasına yardımcı olmak veya Microsoft 365 kaynaklarına erişim için yasal gereksinimlere veya kısıtlamalara işaret etmek için metin ekleyebilirsiniz.

## <a name="customize-the-text-on-your-sign-in-page"></a>Oturum açma sayfanızdaki metni özelleştirme

Oturum açma sayfasındaki özelleştirilebilir öğeleri güncelleştirmek için genel yönetici olmanız gerekir. Belirli yönergeler için [şirket markası ekleme makalesine](/azure/active-directory/fundamentals/customize-branding) bakın.

Güncelleştirebileceğiniz öğeler şunlardır:

- Oturum açma sayfası metni (gizlilik ve onay bildirimi eklemek için kolay bir yer)
- Oturum açma sayfası arka plan resmi
- Başlık logosu
- Kullanıcı adı ipucu

Gizlilik ve onay bildirimlerinin örnekleri için bkz. [Bilgisayarları Arama ve Ele Geçirme ve Cezai Araştırmalarda Elektronik Kanıt Alma](https://www.justice.gov/sites/default/files/criminal-ccips/legacy/2015/01/14/ssmanual2009.pdf) bölümünde Ek A.

## <a name="visual-guide-help-protect-yourself-and-your-campaign-from-digital-threats"></a>Görsel kılavuz: Kendinizi ve kampanyanızı dijital tehditlere karşı korumaya yardımcı olun

Personelinizin kampanyanızı siber tehditlere karşı koruma adımlarını öğrenmesine yardımcı olmak için şu indirilebilir kılavuzu kullanın:

[![Kampanya bilgi grafiğinizi koruma yardımınızın güvenliğini sağlamaya yönelik görüntü.](../media/M365-Campaigns-WhatCanUsersDoToSecure-358x201.png)](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pdf)

[PDF](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pdf) |  [Powerpoint](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pptx)

## <a name="next-objective"></a>Sonraki hedef

Güvenliği [artırmaya](m365bp-security-overview.md) devam edin.
