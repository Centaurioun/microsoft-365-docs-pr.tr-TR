---
title: Çok coğrafi bir ortamda kullanıcı deneyimi
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: Microsoft 365 için çok coğrafi bir ortamda SharePoint, OneDrive ve Exchange kullanıcı deneyimi hakkında bilgi edinin.
ms.openlocfilehash: fa4c108a8f7d97820d9f66bb00f23f19e138588b
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804980"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Multi-Geo ortamında kullanıcı deneyimi

Kullanıcılarınızın OneDrive İş Multi-Geo yapılandırmasında göreceği şeyler şunlardır:

## <a name="exchange-online-mailbox"></a>Exchange Online posta kutusu

Kullanıcının Exchange Online posta kutusu tercih ettiği veri konumuna sağlanır ve PDL'leri değişirse otomatik olarak yeniden konumlandırılır. Kullanıcılar, Multi-Geo ortamında kullanıcı deneyiminde değişiklik olmadan Outlook'u kullanabilir ve normal şekilde Web üzerinde Outlook.

## <a name="hub-sites"></a>Merkez siteleri

SharePoint Online Hub siteleri, çalışanların içerik bulma ve etkileşimini geliştirirken projelerin, departmanların veya bölgelerin eksiksiz ve tutarlı bir gösterimini oluşturur. Multi-Geo ortamında, merkez sitesinin _Coğrafya_ konumu ne olursa olsun uydu konumlarındaki siteler kolayca bir merkez sitesiyle ilişkilendirilebilir. Kullanıcılar, sitelerin coğrafi konumuna bakılmaksızın tek bir arama deneyimi aracılığıyla hub'da arama yapabilir ve sonuç alabilir.

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 uygulama başlatıcısı

Uygulama başlatıcı çok coğrafi özelliklidir ve her kutucuğu iş yükünün uygun coğrafi konumuna yönlendirir. SharePoint Online ve OneDrive İş kutucukları, kullanıcıyı kullanıcının sağlanan coğrafi konumuna karşılık gelen konuma işaret eder. Bu, kullanıcının merkezi konumda bir OneDrive İş olduğu, SharePoint Online kutucuğu tarafından merkezi konumda SP Home'a işaret edeceği ancak grup sitesinin PDL'sine karşılık gelen konumda sağlanacağı anlamına gelir. 

## <a name="office-applications"></a>Office uygulamaları

Microsoft Word, Excel ve PowerPoint gibi Office uygulamaları, oturum açtıklarında her kullanıcı için doğru OneDrive İş coğrafi konumu otomatik olarak algılar. Kullanıcıların OneDrive İş veya SharePoint Online siteleri için coğrafi url'yi girmesi gerekmez.

## <a name="onedrive-for-business-sync-app"></a>Eşitleme uygulamasını OneDrive İş

OneDrive İş eşitleme uygulaması (sürüm 17.3.6943.0625 ve üzeri), kullanıcı için doğru OneDrive _Coğrafya_ konumunu otomatik olarak algılar. Eşitleme uygulaması desteği, _Coğrafya_ konumlarından bağımsız olarak grup tabanlı siteleri eşitleme özelliğini içerir. Groove eşitleme istemcisi Multi-Geo için desteklenmez. 

## <a name="onedrive-for-business-location"></a>OneDrive İş konumu

Kullanıcıların tercih ettikleri veri konumunda OneDrive İş sağlanacaktır. Kullanıcı yanlış bir _Coğrafya_ konumu (önceki coğrafi konumdaki yer işareti gibi) içeren bir OneDrive İş URL'sine giderse, otomatik olarak uygun coğrafi konumdaki OneDrive İş yönlendirilir.

## <a name="onedrive-for-business-ios-and-android"></a>iOS ve Android'i OneDrive İş 

OneDrive iOS ve Android mobil uygulamaları _, Coğrafya_ konumlarından bağımsız olarak sizinle paylaşılan OneDrive İş dosyalarınızı ve dosyalarınızı gösterir. OneDrive İş mobil uygulamalarında yapılan aramalarda tüm _Coğrafya_ konumlarından ilgili sonuçlar gösterilir. Bu uygulamaların en son sürümünü indirin.

Daha fazla bilgi için bkz. [iOS'ta OneDrive'ı](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) [kullanma ve Android için OneDrive'ı kullanma](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) .

## <a name="onedrive-for-business-mobile-client"></a>mobil istemci OneDrive İş 

OneDrive İş Mobil İstemcisi Multi-Geo özelliklidir ve tüm _Coğrafya_ konumlarından ilgili içeriği ve sonuçları görüntüler.

## <a name="search"></a>Arama

Her _Coğrafya_ konumunun kendi arama dizini ve Arama Merkezi vardır. Bir kullanıcı arama yaparken, sorgu tüm _Coğrafya_ konumlarına gönderilir ve döndürülen sonuçlar birleştirilir ve sonra kullanıcının birleşik sonuçlar alması için derecelendirilir. Kullanıcılar, kendi _Coğrafya_ konumlarından bağımsız olarak tüm _Coğrafya_ konumlarından sonuçlar alır. Ayrıntılar için bkz. [OneDrive İş Multi-Geo için Aramayı Yapılandırma](configure-search-for-multi-geo.md).

Aşağıdaki arama istemcileri desteklenir:

-   OneDrive İş

-   Office Delve

-   SharePoint Online Giriş

-   Arama Merkezi

-   SharePoint Arama API'sini kullanan özel arama uygulamaları

## <a name="sharepoint-online-home"></a>SharePoint Online Giriş 

SharePoint Online Multi-Geo'da, SharePoint Online giriş sayfanız kullanıcının OneDrive İş konumuna göre belirlendiği konumda barındırılır. Örneğin: Kullanıcının OneDrive İş Avrupa uydu konumunda barındırıldıysa, SharePoint Online Giriş Sayfası Avrupa'dan işlenir. SharePoint Online giriş sayfası _, Coğrafya_ konumundan bağımsız olarak kullanıcıyla ilgili tüm içeriği içerir. 

**Takip Edilen Siteler, Sitelerden Haberler, Son Kullanılan Siteler, Sık Kullanılan Siteler ve Önerilen siteler**

Bu bileşenlerin tümü, söz konusu içeriğe yönelik izinlere sahip olduğu sürece içeriğin barındırıldığı _Coğrafya_ konumundan bağımsız olarak kullanıcı için gösterilir. 

**Özellik Bağlantıları**

Yöneticiler SharePoint Online girişindeki Öne Çıkan bağlantıları her _Coğrafya_ konumuna uygun olarak yapılandırabilir. Bu, yöneticinin her bölge için SP Giriş'te bölgedeki kullanıcılara uygun bağlantıları öne yapmasına olanak tanır. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobile İstemcisi

SharePoint Mobile İstemcisi çok coğrafi olarak bilgilidir ve tüm coğrafi konumlardaki ilgili içeriği ve sonuçları görüntüler.

## <a name="sharing"></a>Paylaşım

Kişiler Seçici deneyimi _, Coğrafya_ konumlarından bağımsız olarak tüm kullanıcıları gösterir. Bu, kullanıcının aynı coğrafi bölgede veya _Kiracınızın_ _Coğrafya_ konumlarından herhangi birinde başka bir kullanıcıyla paylaşmasına olanak tanır. Farklı _Coğrafya_ konumlarındaki içerikler kullanıcının OneDrive İş, Word, Excel, PowerPoint ve Office.com **Benimle Paylaşılan** görünümünde gösterilir ve hangi _Coğrafya_ konumunda barındırıldığına bakılmaksızın Tek Sign-On deneyimiyle erişilebilir.

## <a name="microsoft-teams-experience"></a>Microsoft Teams Deneyimi

Microsoft Teams bir Multi-Geo hizmetidir. OneDrive İş dosyaları ve son görüntülenen dosyalar, kullanıcının _Coğrafya_ konumundan bağımsız olarak gösterilir. @ bahsetmeleri tüm _Coğrafya_ konumlarından kullanıcılarla çalışır.

## <a name="user-profiles"></a>Kullanıcı profilleri

Kullanıcı profili bilgileri, kullanıcının _Coğrafya_ konumunda ana kaynak olarak bulunur. Bir kullanıcı seçerken, kullanıcı için uygun _Coğrafya_ konumuna yönlendirilirsiniz ve burada profil ayrıntılarının tamamını görürsünüz.

Office Delve kapalıysa SharePoint Online'da Klasik profil deneyimini görürsünüz ve bu deneyim Multi-Geo'ya duyarlı değildir.


