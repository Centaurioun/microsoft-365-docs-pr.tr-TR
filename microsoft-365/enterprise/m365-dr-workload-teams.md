---
title: Microsoft Teams için Data Residency
description: Microsoft Teams için veri yerleşimi hakkında bilgi edinin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 6f7853537a4a263e888fc27b496cd61f83f13024
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806181"
---
# <a name="data-residency-for-microsoft-teams"></a>Microsoft Teams için Data Residency

## <a name="data-residency-commitments-available"></a>Data Residency Taahhütleri Kullanılabilir

### <a name="product-terms"></a>Ürün Koşulları

Gerekli Koşullar:

1. _Kiracının_ _Yerel Bölge Coğrafyası_, Avrupa Birliği veya Birleşik Devletler dahil bir kaydolma ülkesi vardır.

**Taahhüt:**

_Geçerli dil için lütfen [Gizlilik ve Güvenlik Ürün Koşulları'na](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) bakın ve "Core Online Services için Bekleyen Müşteri Verilerinin Konumu" başlıklı bölümü görüntüleyin._

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının__, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_
1. Microsoft Teams aboneliği müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

Ürün Koşulları aracılığıyla sağlanan belirli taahhütleri anlamak için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#microsoft-teams) bakın.  Taahhüt edilen verilere örnek olarak şunlar verilebilir:

- Sohbet/kanal iletileri ve ekip yapısı: Microsoft Teams'deki her ekip, bir Microsoft 365 Modern Grubu ve SharePoint sitesi ve Exchange posta kutusu tarafından desteklenir. Özel sohbetler (grup sohbetleri dahil), bir kanaldaki konuşmanın parçası olarak gönderilen iletiler ve ekiplerin ve kanalların yapısı Azure destekli bir sohbet hizmetinde depolanır. Veriler, bilgi koruma özelliklerini etkinleştirmek için kullanıcı ve grup posta kutularında gizli bir klasörde de depolanır.  
- Görüntüler ve Medya: Sohbetlerde kullanılan medya (depolanmayan ancak özgün Giphy URL'sine başvuru bağlantısı olan Giphy GIF'leri hariç) sohbet hizmetiyle aynı konumlara dağıtılan Azure tabanlı bir Media Service'te depolanır.
- Toplantı Kayıtları: Microsoft Stream (SharePoint'te) kullanıcıları için Toplantı Kayıtları, kaydı başlatan kullanıcının OneDrive İş depolama alanında depolanır.

### <a name="multi-geo-add-on"></a>Multi-Geo eklentisi

Gerekli Koşullar:

1. _Kiracılar__, Uydu Coğrafya'ya_ atanan tüm kullanıcıları kapsayan geçerli bir Multi-Geo aboneliğine sahiptir
1. Müşterinin etkin bir Kurumsal Anlaşma olması gerekir.
1. Satın alınan toplam Multi-Geo birimi _, Kiracıdaki_ toplam uygun koltukların %5'inden büyük olmalıdır.

**Taahhüt:** Müşteriler, Microsoft Teams kullanıcılarını Multi-Geo tarafından desteklenen herhangi bir _Uydu Coğrafyasına_ atayabilir. Aşağıdaki müşteri verileri ilgili _Uydu Coğrafya'da_ depolanır: Özel iletiler, kanal iletileri ve sohbetlerde kullanılan görüntüler dahil olmak üzere sohbet iletilerinden oluşan Teams sohbet verileri.

## <a name="multi-geo-capabilities-in-microsoft-teams"></a>Microsoft Teams'de Multi-Geo Özellikleri

Teams'deki Multi-Geo özellikleri, Teams sohbet verilerinin belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumunda bekleyen konumda depolanmasını sağlar. Sohbet verileri özel iletiler, kanal iletileri ve sohbetlerde kullanılan görüntüler de dahil olmak üzere sohbet iletilerinden oluşur.

Teams, verilerin nerede depoleneceğini belirlemek için kullanıcılar ve gruplar için Tercih Edilen Veri Konumu'nı (PDL) kullanır. PDL ayarlanmamışsa veya geçersizse, veriler kiracının _Birincil Sağlanan Coğrafya_ konumunda depolanır.

>[!NOTE]
>Teams'deki Multi-Geo özellikleri Temmuz 2021'de kullanıma sunulmaya devam etti. Sohbetiniz ve kanal iletileriniz, önümüzdeki birkaç çeyrekte otomatik olarak doğru _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumuna geçirilecektir. Tüm yeni PDL değişiklikleri _Kiracı_ ilk eşitlemeyi tamamladıktan sonra işlenir ve bunun ötesindeki yeni PDL değişiklikleri alındıkları sırayla kuyruğa alınır ve işlenir.

### <a name="user-chat"></a>Kullanıcı sohbeti

Kullanıcı sohbeti bire bir, bire çok ve özel toplantı iletileri içerir.

Yeni bir kullanıcı oluşturulduğunda, Teams kullanıcının PDL'sini okur ve tüm sohbet verilerini _bu Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumunda depolar.
Mevcut kullanıcılar için, bir yönetici bir kullanıcının PDL'sini ekler veya değiştirirse, o kullanıcının sohbet verileri belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumuna taşınacak bir geçiş kuyruğuna eklenir.

Bire bir veya bire çok sohbetin depolama konumu, sohbeti oluşturan kişinin PDL'sini temel alır. Kullanıcının PDL'sini değiştirirseniz, sohbet yeni _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafya_ konumuna geçirilir. Toplantı sohbetinin depolama konumu, toplantı düzenleyicisinin PDL'sini temel alır.

Kullanıcının Teams verilerinin geçerli konumunu bulmak için Teams PowerShell'e bağlanın ve aşağıdaki komutu çalıştırın:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

### <a name="channel-messages"></a>Kanal iletileri

Her Microsoft 365 grubunun, ilgili verilerin depolandığı _Coğrafya_ konumunu gösteren Tercih Edilen Veri Konumu (PDL) vardır. Ekipler, ekip için kanal mesajlaşma verilerinin depolandığı yeri belirlemek için her ekiple ilişkili grup için PDL'yi kullanır. Bu, bir kanal toplantısında gerçekleşen özel kanalları ve sohbeti içerir.

Kullanıcı yeni bir ekip oluşturduğunda, bu kullanıcının PDL'i Microsoft 365 grubuna hangi PDL'nin atandığını belirler. Grup PDL' i, ekibin verilerinin nerede depolandığını belirler. Bu kullanıcının PDL'i daha sonra değişirse, grubun PDL'i değiştirilmez.

Mevcut ekipler için, bir yönetici bir ekibi destekleyen Microsoft 365 grubunun PDL'sini ekler veya değiştirirse, bu ekibin kanal mesajlaşma verileri belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumuna taşınacak bir geçiş kuyruğuna eklenir.

Microsoft 365 grubunun PDL'sini değiştirmek, Teams verilerini seçilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumuna geçirmek için kuyruğa alır. Ancak bu, SharePoint sitesini veya Grupla ilişkili dosyaları otomatik olarak geçirmez. SharePoint sitesini farklı bir _Coğrafya_ konumuna taşıma'daki yordamları izleyerek siteyi ayrı olarak taşımanız gerekir. Farklı konumlardaki bir grup için Teams verilerini ve SharePoint verilerini önlemek için her iki adımı da uyguladığından emin olun.

Ekip verilerinin geçerli konumunu bulmak için Teams PowerShell'e bağlanın ve aşağıdaki komutu çalıştırın:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

### <a name="user-experience"></a>Kullanıcı Deneyimi

Teams Multi-Geo, son kullanıcıya sorunsuz bir şekilde sağlanır. Bir kullanıcının veya grubun PDL'sini değiştirdiğinizde, ilgili veriler geçiş için kuyruğa alır ve geçiş gerçekleşirken etkin olsalar bile kullanıcı veya Teams istemcisini etkilemeden geçiş otomatik olarak gerçekleşir.

### <a name="migration"></a>Geçiş

**Dosyalar Sekmesi** Geçiş tamamlandıktan sonra, kullanıcı ilk kez kullanmayı denediğinde Dosyalar sekmesinin tamamen yüklenmesi ek zaman alabilir (7 saniyeye kadar).

**Salt okunur dönem** Teams sohbet hizmetleri her yazışmayı ayrı ayrı taşır. taşıma sırasında iş parçacığı salt okunur durumda kilitlenir ve bu durum iş parçacığı başına birkaç saniye sürer. Geçiş sırasında iş parçacıklarına erişilebilir durumda kalır.

**Geçiş için kapsam içi** Exchange Online, SharePoint Online ve OneDrive İş ek olarak; Microsoft, Teams verilerini yerel veri merkezine geçirir.

- Özel iletiler ve kanal iletileri de dahil olmak üzere Teams sohbet iletileri.
- Sohbetlerde kullanılan Teams görüntüleri.

Teams dosyaları SharePoint Online'da, Teams sohbet dosyaları ise OneDrive İş'de depolanır. Sesli mesaj, takvim ve kişiler Exchange Online depolanır. Çoğu durumda, Exchange Online, SharePoint Online ve OneDrive İş yerel _veri merkezinde müşteri_ tarafından zaten kullanılır ve ayrıca uygun müşteri ülkeleri için Microsoft 365 geçiş programının bir parçasıdır.

### <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?
Gerçek veri konumunu _Kiracı_ Yönetici Merkezi'nde bulabilirsiniz. _Kiracı_ yöneticisi olarak, kaydedilmiş veriler için gerçek veri konumunu bulmak için Yönetici| Ayarlar| Kuruluş Ayarları| Kuruluş Profili| Veri Konumu.
