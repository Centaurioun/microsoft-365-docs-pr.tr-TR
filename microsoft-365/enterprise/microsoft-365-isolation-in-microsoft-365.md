---
title: Microsoft 365'te yalıtım ve Access Control
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: "Özet: Microsoft 365'in çeşitli uygulamalarındaki yalıtım ve erişim denetiminin açıklaması."
ms.openlocfilehash: b85e61f8fc47fa0dd613ee0f054db6df4028f8d9
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68186645"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Microsoft 365'te yalıtım ve Access Control

Azure Active Directory (Azure AD) ve Microsoft 365 onlarca hizmet, yüzlerce varlık, binlerce ilişki ve on binlerce özniteliği içeren son derece karmaşık bir veri modeli kullanır. Yüksek düzeyde, Azure AD ve hizmet dizinleri, durum tabanlı çoğaltma protokollerini kullanarak eşitlenmiş durumda tutulan kiracıların ve alıcıların kapsayıcılarıdır. Azure AD içinde tutulan dizin bilgilerine ek olarak, hizmet iş yüklerinin her birinin kendi dizin hizmetleri altyapısı vardır.
 
![Microsoft 365 kiracı veri eşitlemesi.](../media/office-365-isolation-tenant-data-sync.png)

Bu modelde tek bir dizin veri kaynağı yoktur. Belirli sistemler tek tek veri parçalarına sahiptir, ancak tüm verileri tek bir sistem tutmaz. Microsoft 365 hizmetleri, bu veri modelindeki Azure AD işbirliğine sahiptir. Azure AD, paylaşılan veriler için genellikle her hizmet tarafından kullanılan küçük ve statik veriler olan "doğruluk sistemidir". Microsoft 365 ve Azure AD içinde kullanılan federasyon modeli, verilerin paylaşılan görünümünü sağlar.

Microsoft 365 hem fiziksel depolamayı hem de Azure bulut depolamayı kullanır. Exchange Online (Exchange Online Protection dahil) ve Skype Kurumsal müşteri verileri için kendi depolama alanını kullanır. SharePoint Online hem SQL Server depolamayı hem de Azure Depolama'yı kullandığından, müşteri verilerinin depolama düzeyinde fazladan yalıtıma ihtiyacı vardır.

## <a name="exchange-online"></a>Exchange Online

Exchange Online, müşteri verilerini posta kutuları içinde depolar. Posta kutuları, posta kutusu veritabanları olarak adlandırılan Genişletilebilir Depolama Altyapısı (ESE) veritabanlarında barındırılır. Buna kullanıcı posta kutuları, bağlı posta kutuları, paylaşılan posta kutuları ve ortak klasör posta kutuları dahildir. Kullanıcı posta kutuları, konuşma geçmişleri gibi kaydedilmiş Skype Kurumsal içeriği içerir.

Kullanıcı posta kutusu içeriği şunları içerir:

- E-postalar ve e-posta ekleri
- Takvim ve serbest/meşgul bilgileri
- Kişiler
- Görevler
- Notlar
- Gruplar
- Çıkarım verileri

Exchange Online içindeki her posta kutusu veritabanı, birden çok kiracıdan gelen posta kutularını içerir. Yetkilendirme kodu, kiracı da dahil olmak üzere her posta kutusunun güvenliğini sağlar. Varsayılan olarak, posta kutusuna yalnızca atanan kullanıcının erişimi vardır. Posta kutusunun güvenliğini sağlayan erişim denetimi listesi (ACL), kiracı düzeyinde Azure AD tarafından kimliği doğrulanmış bir kimlik içerir. Her kiracının posta kutuları, kiracının kimlik doğrulama sağlayıcısında kimliği doğrulanmış kimliklerle sınırlıdır ve bu kimlikler yalnızca bu kiracıdaki kullanıcıları içerir. A kiracısında içerik, A kiracısı tarafından açıkça onaylanmadığı sürece B kiracısında bulunan kullanıcılar tarafından hiçbir şekilde alınamaz.

## <a name="skype-for-business"></a>Skype Kurumsal

Skype Kurumsal verileri çeşitli yerlerde depolar:

- Bağlantı uç noktalarını, kiracı kimliklerini, arama planlarını, dolaşım ayarlarını, iletişim durumu, kişi listelerini vb. içeren kullanıcı ve hesap bilgileri, Skype Kurumsal Active Directory sunucularında ve çeşitli Skype Kurumsal veritabanı sunucularında depolanır. Kişi listeleri, kullanıcı her iki ürün için de etkinleştirildiyse kullanıcının Exchange Online posta kutusunda veya kullanıcı etkinleştirilmediyse Skype Kurumsal sunucularda depolanır. Skype Kurumsal veritabanı sunucuları kiracı başına bölümlenmez, ancak rol tabanlı erişim denetimi (RBAC) aracılığıyla verilerin çok kiracılı yalıtımı uygulanır.
- Toplantı içeriği ve karşıya yüklenen veriler Dağıtılmış Dosya Sistemi (DFS) paylaşımlarında depolanır. Bu içerik, etkinleştirilirse Exchange Online içinde de arşivlenebilir. DFS paylaşımları kiracı başına bölümlenmez. içeriğin güvenliği ACL'lerle sağlanır ve çok kiracılılık RBAC aracılığıyla zorlanır.
- Arama geçmişi, anlık ileti oturumları, uygulama paylaşımı, anlık ileti geçmişi gibi etkinlik geçmişi olan arama ayrıntı kayıtları da Exchange Online depolanabilir, ancak çoğu arama ayrıntısı kaydı geçici olarak arama ayrıntı kaydı (CDR) sunucularında depolanır. İçerik kiracı başına bölümlenmez, ancak RBAC aracılığıyla çok kiracılılık uygulanır.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online'da veri yalıtımı sağlayan çeşitli bağımsız mekanizmalar vardır. Nesneleri uygulama veritabanlarında soyut kod olarak depolar. Örneğin, bir kullanıcı SharePoint Online'a dosya yüklediğinde dosya ayrıştırılır, uygulama koduna çevrilir ve birden çok veritabanında birden çok tabloda depolanır.

Bir kullanıcı verileri içeren depolama alanına doğrudan erişim elde edebilirse, içerik bir insan veya SharePoint Online dışında herhangi bir sistem tarafından yorumlanamaz. Bu mekanizmalar güvenlik erişim denetimi ve özellikleri içerir. Tüm SharePoint Online kaynaklarının güvenliği, kiracı içinde olmak üzere yetkilendirme kodu ve RBAC ilkesiyle sağlanır. Bir kaynağın güvenliğini sağlayan erişim denetimi listesi (ACL), kiracı düzeyinde kimliği doğrulanmış bir kimlik içerir. Bir kiracının SharePoint Online verileri, kiracı için kimlik doğrulama sağlayıcısı tarafından kimliği doğrulanan kimliklerle sınırlıdır.

ACL'lere ek olarak, kimlik doğrulama sağlayıcısını (kiracıya özgü Azure AD) belirten bir kiracı düzeyi özelliği bir kez yazılır ve ayarlandıktan sonra değiştirilemez. Bir kiracı için kimlik doğrulama sağlayıcısı kiracı özelliği ayarlandıktan sonra, kiracıya sunulan API'ler kullanılarak değiştirilemez.

Her kiracı için benzersiz *bir SubscriptionId* kullanılır. Tüm müşteri siteleri bir kiracıya aittir ve kiracıya benzersiz bir *SubscriptionId* atanır. Bir sitedeki *SubscriptionId* özelliği bir kez yazılır ve kalıcıdır. Bir kiracıya atandıktan sonra site farklı bir kiracıya taşınamaz. *SubscriptionId*, kimlik doğrulama sağlayıcısının güvenlik kapsamını oluşturmak için kullanılan anahtardır ve kiracıya bağlıdır.

SharePoint Online, içerik meta veri depolaması için SQL Server ve Azure Depolama kullanır. İçerik deposunun bölüm anahtarı, SQL'de *SiteId'dir* . Bir SQL sorgusu çalıştırırken, SharePoint Online kiracı düzeyinde *SubscriptionId* denetiminin bir parçası olarak doğrulanmış bir *SiteId* kullanır.

SharePoint Online şifrelenmiş dosya içeriğini Microsoft Azure bloblarında depolar. Her SharePoint Online grubu kendi Microsoft Azure hesabına sahiptir ve Azure'da kaydedilen tüm bloblar SQL içerik deposunda depolanan bir anahtarla ayrı ayrı şifrelenir. Kimlik doğrulama katmanı tarafından kodda korunan ve doğrudan son kullanıcıya sunulmayan şifreleme anahtarı. SharePoint Online, bir HTTP isteğinin birden çok kiracı için verileri ne zaman okuduğunu veya yazdığını algılamak için gerçek zamanlı izleme özelliğine sahiptir. *SubscriptionId* istek kimliği, erişilen kaynağın *SubscriptionId* değeriyle izlenir. Birden fazla kiracının kaynaklarına erişim istekleri hiçbir zaman son kullanıcılar tarafından gerçekleşmemelidir. Çok kiracılı bir ortamdaki hizmet istekleri tek istisnadır. Örneğin, arama gezgini tüm veritabanı için içerik değişikliklerini aynı anda çeker. Bu genellikle, verimlilik nedenleriyle yapılan tek bir hizmet isteğinde birden fazla kiracının sitelerini sorgulamayı içerir.

## <a name="teams"></a>Teams

Teams verileriniz içerik türüne bağlı olarak farklı şekilde depolanır. 

Ayrıntılı bir tartışma için [Microsoft Teams mimarisinde Ignite tartışma oturumuna](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) göz atın.

### <a name="core-teams-customer-data"></a>Çekirdek Teams müşteri verileri

Kiracınız Avustralya, Kanada, Avrupa Birliği, Fransa, Almanya, Hindistan, Japonya, Güney Afrika, Güney Kore, İsviçre (Liechtenstein dahil), Birleşik Arap Emirlikleri, Birleşik Krallık veya Birleşik Devletler sağlanırsa, Microsoft aşağıdaki müşteri verilerini yalnızca bu konumda bekleyen olarak depolar:

- Teams sohbetleri, ekip ve kanal konuşmaları, resimler, sesli mesaj iletileri ve kişiler.
- SharePoint Online site içeriği ve bu site içinde depolanan dosyalar.
- İş veya okul için OneDrive'a yüklenen dosyalar.

#### <a name="chat-channel-messages-team-structure"></a>Sohbet, kanal iletileri, ekip yapısı

Teams'deki her ekip, bir Microsoft 365 Grubu, sharepoint sitesi ve Exchange posta kutusu tarafından desteklenir. Özel sohbetler (grup sohbetleri dahil), kanaldaki konuşmanın parçası olarak gönderilen iletiler ve ekiplerin ve kanalların yapısı Azure'da çalışan bir sohbet hizmetinde depolanır. Veriler, Information Protection özellikleri etkinleştirmek için kullanıcı ve grup posta kutularında gizli bir klasörde de depolanır.

#### <a name="voicemail-and-contacts"></a>Sesli mesaj ve kişiler

Sesli mesajlar Exchange'de depolanır. Kişiler Exchange tabanlı bulut veri deposunda depolanır. Exchange ve Exchange tabanlı bulut deposu, dünya çapındaki veri merkezi coğrafi bölgelerinin her birinde zaten veri yerleşimi sağlar. Tüm ekipler için sesli mesaj ve kişiler Avustralya, Kanada, Fransa, Almanya, Hindistan, Japonya, Birleşik Arap Emirlikleri, Birleşik Krallık, Güney Afrika, Güney Kore, İsviçre (Liechtenstein dahil) ve Birleşik Devletler için ülke içinde depolanır. Diğer tüm ülkelerde dosyalar, kiracı benzeşimi temelinde ABD, Avrupa veya Asia-Pacific konumunda depolanır.

#### <a name="images-and-media"></a>Görüntüler ve medya

Sohbetlerde kullanılan medya (depolanmayan ancak özgün Giphy hizmeti URL'sine başvuru bağlantısı olan Giphy, Microsoft dışı bir hizmettir) sohbet hizmetiyle aynı konumlara dağıtılan Azure tabanlı bir medya hizmetinde depolanır.

#### <a name="files"></a>Dosyalar

Birinin kanalda paylaştığı dosyalar (OneNote ve Wiki dahil) ekibin SharePoint sitesinde depolanır. Toplantı veya arama sırasında özel sohbette veya sohbette paylaşılan dosyalar karşıya yüklenir ve dosyayı paylaşan kullanıcının OneDrive iş veya okul hesabında depolanır. Exchange, SharePoint ve OneDrive, dünya çapındaki veri merkezi coğrafi bölgelerinin her birinde zaten veri yerleşimi sağlar. Bu nedenle, mevcut müşteriler için teams deneyiminin bir parçası olan tüm dosyalar, OneNote not defterleri, Teams wiki içeriği ve posta kutuları kiracı benzitenize bağlı olarak konumda zaten depolanır. Dosyalar Avustralya, Kanada, Fransa, Almanya, Hindistan, Japonya, Birleşik Arap Emirlikleri, Birleşik Krallık, Güney Afrika, Güney Kore ve İsviçre (Liechtenstein dahil) için ülke içinde depolanır. Diğer tüm ülkelerde dosyalar, kiracı benzeşimi temelinde ABD, Avrupa veya Asya Pasifik konumunda depolanır.
