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
ms.openlocfilehash: a543653410d2b9330c0ea2c5e3e717918506ae2b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687207"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Çok coğrafi bir ortamda kullanıcı deneyimi

Kullanıcılarınızın OneDrive Multi-Geo yapılandırmasında göreceği şeyler şunlardır:

## <a name="exchange-mailbox"></a>Exchange posta kutusu

Kullanıcının Exchange posta kutusu tercih ettiği veri konumuna sağlanır ve PDL'leri değişirse otomatik olarak yeniden konumlandırılır. Kullanıcılar Outlook'u kullanabilir ve çok coğrafi ortamda kullanıcı deneyiminde değişiklik olmadan normal Web üzerinde Outlook.

## <a name="hub-sites"></a>Merkez siteleri

SharePoint Hub siteleri, çalışanların içerik bulma ve etkileşimini geliştirirken projelerin, departmanların veya bölgelerin eksiksiz ve tutarlı bir gösterimini oluşturur. Çok coğrafi bir ortamda, merkez sitesinin coğrafi konumu ne olursa olsun uydu konumlarındaki siteler kolayca bir merkez sitesiyle ilişkilendirilebilir. Kullanıcılar, sitelerin coğrafi konumuna bakılmaksızın tek bir arama deneyimi aracılığıyla hub'da arama yapabilir ve sonuç alabilir.

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 uygulama başlatıcısı

Uygulama başlatıcı çok coğrafi özelliklidir ve her kutucuğu iş yükünün uygun coğrafi konumuna yönlendirir. SharePoint ve OneDrive kutucukları, kullanıcıyı kullanıcının sağlanan coğrafi konumuna karşılık gelen konuma işaret eder. Bu, kullanıcının merkezi konumda bir OneDrive'ı olduğu, SharePoint kutucuğu tarafından merkezi konumda SP Home'a işaret edeceği ancak grup sitesinin PDL'sine karşılık gelen konumda sağlanacağı anlamına gelir. 

## <a name="office-applications"></a>Office uygulamaları

Word, Excel ve PowerPoint gibi Office uygulamaları, oturum açtığında her kullanıcı için doğru OneDrive coğrafi konumunu otomatik olarak algılar. Kullanıcıların OneDrive veya SharePoint siteleri için coğrafi olarak özel URL'yi girmeleri gerekmez.

## <a name="onedrive-sync-app"></a>OneDrive eşitleme uygulaması

OneDrive eşitleme uygulaması (sürüm 17.3.6943.0625 ve üzeri), kullanıcı için doğru OneDrive coğrafi konumunu otomatik olarak algılar. Eşitleme uygulaması desteği, coğrafi konumlarından bağımsız olarak grup tabanlı siteleri eşitleme özelliğini içerir. Groove eşitleme istemcisi çoklu coğrafi bölge için desteklenmez. 

## <a name="onedrive-location"></a>OneDrive konumu

Kullanıcılar tercih ettikleri veri konumlarında OneDrive'larını sağlar. Kullanıcı yanlış coğrafi konum içeren bir OneDrive URL'sine (önceki bir coğrafi konumdan yer işareti gibi) giderse, otomatik olarak uygun coğrafi konumdaki OneDrive'a yönlendirilir.

## <a name="onedrive-ios-and-android"></a>OneDrive iOS ve Android 

OneDrive iOS ve Android mobil uygulamaları, coğrafi konumlarından bağımsız olarak sizinle paylaşılan OneDrive dosyalarınızı ve dosyalarınızı gösterir. OneDrive mobil uygulamalarından yapılan aramalarda tüm coğrafi konumlardan ilgili sonuçlar gösterilir. Bu uygulamaların en son sürümünü indirin.

Daha fazla bilgi için bkz. [iOS'ta OneDrive'ı](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) [kullanma ve Android için OneDrive'ı kullanma](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) .

## <a name="onedrive-mobile-client"></a>OneDrive Mobil İstemcisi 

OneDrive Mobil İstemcisi çok coğrafi olarak bilgilidir ve tüm coğrafi konumlardaki ilgili içeriği ve sonuçları görüntüler.

## <a name="search"></a>Arama

Her coğrafi konumun kendi arama dizini ve Arama Merkezi vardır. Kullanıcı arama yaparken, sorgu tüm coğrafi konumlara gönderilir ve döndürülen sonuçlar birleştirilir ve sonra kullanıcının birleşik sonuçlar alması için derecelendirilir. Kullanıcılar, coğrafi konumlarından bağımsız olarak tüm coğrafi konumlardan sonuçlar alır. Bkz[. Belirli OneDrive Multi-Geo için Aramayı Yapılandırma](configure-search-for-multi-geo.md).

Aşağıdaki arama istemcileri desteklenir:

-   OneDrive

-   Doğan

-   SharePoint Giriş

-   Arama Merkezi

-   SharePoint Arama API'sini kullanan özel arama uygulamaları

## <a name="sharepoint-home"></a>SharePoint Giriş 

SharePoint Multi-Geo'da, SharePoint giriş sayfanız kullanıcının OneDrive konumuna göre belirlendiği konumda barındırılır. Örneğin: Kullanıcının OneDrive'ı Avrupa uydu konumunda barındırıldıysa, SharePoint Giriş Sayfası Avrupa'dan işlenir. SharePoint giriş sayfası, coğrafi konumu ne olursa olsun kullanıcıyla ilgili tüm içeriği içerir. 

**Takip Edilen Siteler, Sitelerden Haberler, Son Kullanılan Siteler, Sık Kullanılan Siteler ve Önerilen siteler**

Bu bileşenlerin tümü, kullanıcının söz konusu içeriğe yönelik izinleri olduğu sürece içeriğin barındırıldığı coğrafi konumdan bağımsız olarak kullanıcıya gösterilir. 

**Özellik Bağlantıları**

Yöneticiler SharePoint girişindeki Öne çıkan bağlantıları her coğrafi konuma uygun şekilde yapılandırabilir. Bu, yöneticinin her bölge için SP Giriş'te bölgedeki kullanıcılara uygun bağlantıları öne yapmasına olanak tanır. 

## <a name="sharepoint-mobile-client"></a>SharePoint Mobile İstemcisi

SharePoint Mobile İstemcisi çok coğrafi olarak bilgilidir ve tüm coğrafi konumlardaki ilgili içeriği ve sonuçları görüntüler.

## <a name="sharing"></a>Paylaşım

Kişiler Seçici deneyimi, coğrafi konumlarından bağımsız olarak tüm kullanıcıları gösterir. Bu, kullanıcının aynı coğrafi bölgede veya kiracınızın diğer coğrafi konumlarında başka bir kullanıcıyla paylaşmasına olanak tanır. Farklı coğrafi konumlardaki içerikler kullanıcının OneDrive, Word, Excel, PowerPoint ve Office.com Benimle **Paylaşılan** görünümünde gösterilir ve hangi coğrafi konumda barındırıldığına bakılmaksızın Tek Sign-On deneyimiyle erişilebilir.

## <a name="teams-experience"></a>Teams Deneyimi

Teams çok coğrafi bir hizmettir. Kullanıcının coğrafi konumu ne olursa olsun OneDrive dosyaları ve son görüntülenen dosyalar gösterilir. @ bahsetmeleri tüm coğrafi konumlardaki kullanıcılarla çalışır.

## <a name="user-profiles"></a>Kullanıcı profilleri

Kullanıcı profili bilgileri, kullanıcının coğrafi konumunda ana bilgidir. Bir kullanıcı seçerken, kullanıcı için uygun coğrafi konuma yönlendirilirsiniz ve burada profil ayrıntılarının tamamını görürsünüz.

Delve kapalıysa SharePoint'te çok coğrafi olarak farkında olmayan klasik profil deneyimini görürsünüz.


