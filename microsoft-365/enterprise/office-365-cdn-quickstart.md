---
title: Office 365 Content Delivery Network (CDN) Hızlı Başlangıcı
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/13/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) Hızlı Başlangıcı
ms.openlocfilehash: c94f8ae3e464f3fdfe9c95b352bc567e609f1d41
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198371"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network (CDN) Hızlı Başlangıcı

SharePoint Online sayfalarınız için daha iyi performans sağlamak amacıyla statik varlıkları (görüntüler, JavaScript, Stil Sayfaları, WOFF dosyaları) barındırmak için yerleşik **Office 365 Content Delivery Network'i (CDN)** kullanabilirsiniz. Office 365 CDN, statik varlıkları isteyen tarayıcılara daha yakın önbelleğe alarak performansı artırır ve bu da indirmeleri hızlandırmaya ve gecikme süresini azaltmaya yardımcı olur. Ayrıca Office 365 CDN, geliştirilmiş sıkıştırma ve HTTP kanal oluşturma için HTTP/2 protokollerini kullanır. Office 365 CDN hizmeti, SharePoint Online aboneliğinizin bir parçası olarak dahil edilir.

Daha ayrıntılı bilgi kılavuzu için bkz. [sharepoint online ile Office 365 content delivery network (CDN) kullanma](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>Office 365 CDN yalnızca üretim (dünya çapında) buluttaki kiracılar tarafından kullanılabilir. ABD Hükümeti, Çin ve Almanya bulutlarındaki kiracılar şu anda Office 365 CDN'yi desteklememektedir.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>CDN'de olmayan öğeleri tanımlamak için SharePoint için Sayfa Tanılama aracını kullanma

SharePoint Online sayfalarınızdaki CDN kaynağına eklenebilen varlıkları kolayca listelemek için SharePoint araç tarayıcısı uzantısı için **Sayfa Tanılama'yı** kullanabilirsiniz.

**SharePoint için Sayfa Tanılama aracı, hem SharePoint** Online modern portalını hem de klasik yayımlama sitesi sayfalarını analiz eden yeni Microsoft Edge (<https://www.microsoft.com/edge>) ve Chrome tarayıcıları için bir tarayıcı uzantısıdır. Araç, analiz edilen her sayfa için sayfanın tanımlı bir performans ölçütleri kümesine göre nasıl performans gösterdiğini gösteren bir rapor sağlar. SharePoint için Sayfa Tanılama aracını yüklemek ve hakkında bilgi edinmek için [SharePoint Online için Sayfa Tanılama aracını kullanma](./page-diagnostics-for-spo.md) sayfasını ziyaret edin.

SharePoint Online sayfasında SharePoint için Sayfa Tanılama aracını çalıştırdığınızda, CDN tarafından barındırılmayan varlıkların listesini görmek için **Tanılama Testleri** sekmesine tıklayabilirsiniz. Bu varlıklar, aşağıdaki ekran görüntüsünde gösterildiği gibi **Content Delivery Network (CDN) denetimi** başlığı altında listelenir.

![Sayfa tanılama.](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Sayfa Tanılama aracı yalnızca SharePoint Online için çalışır ve SharePoint sistem sayfasında kullanılamaz.

## <a name="cdn-overview"></a>CDN'ye Genel Bakış

Office 365 CDN, görüntüler ve javascript dosyaları gibi sık erişilen nesneleri yüksek hızlı bir genel ağ üzerinden dağıtarak, sayfa yükleme süresini azaltarak ve barındırılan nesnelere kullanıcıya mümkün olduğunca yakın erişim sağlayarak kullanıcıların performansını iyileştirmek için tasarlanmıştır. CDN varlıklarınızı _kaynak_ olarak adlandırılan bir konumdan getirir. Kaynak, URL ile erişilebilen bir SharePoint sitesi, belge kitaplığı veya klasör olabilir.

Office 365 CDN iki temel türe ayrılır:

- **Genel CDN** , JS (JavaScript), CSS (StyleSheets), Web Yazı Tipi Dosyası (WOFF, WOFF2) ve şirket logoları gibi özel olmayan görüntüler için kullanılacak şekilde tasarlanmıştır.
- **Özel CDN** görüntüler (PNG, JPG, JPEG vb.) için kullanılacak şekilde tasarlanmıştır.

Kuruluşunuz için hem genel hem de özel kaynaklardan birini seçebilirsiniz. Çoğu kuruluş ikisinin birleşimini uygulamayı seçecektir. Hem genel hem de özel seçenekler benzer performans kazançları sağlar, ancak her birinde benzersiz öznitelikler ve avantajlar vardır. Genel ve özel CDN kaynakları hakkında daha fazla bilgi için bkz. [Her kaynağın genel mi yoksa özel mi olacağını seçme](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Genel ve Özel CDN'yi varsayılan yapılandırmayla etkinleştirme
Kiracı CDN ayarlarında değişiklik yapmadan önce, kuruluşunuzun uyumluluk, güvenlik ve gizlilik ilkelerini karşıladığını doğrulamanız gerekir.

Daha ayrıntılı yapılandırma ayarları için veya CDN'yi zaten etkinleştirdiyseniz ve ek konumlar (çıkış noktaları) eklemek istiyorsanız, [sharepoint online yönetim kabuğunu kullanarak Office 365 CDN'yi ayarlama ve yapılandırma](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) bölümüne bakın

SharePoint Online Yönetim Kabuğu'nı kullanarak kiracınıza bağlanın:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Kuruluşunuzun varsayılan yapılandırmayla hem genel hem de özel çıkış noktalarını kullanmasını sağlamak için aşağıdaki komutu yazın:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Bu cmdlet'lerin çıkışı aşağıdaki gibi görünmelidir:

![Set-SPOTenantCdnEnabled çıkışı.](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint Online için Sayfa Tanılama aracını kullanma](./page-diagnostics-for-spo.md)

[SharePoint Online ile Office 365 Content Delivery Network'i (CDN) kullanma](use-microsoft-365-cdn-with-spo.md)

[İçerik Teslim Ağları](./content-delivery-networks.md)

[Network planning and performance tuning for Office 365](./network-planning-and-performance.md)

[SharePoint Performans Serisi - Office 365 CDN video serisi](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
