---
title: Microsoft 365 İş Ekstra koruma özellikleri Intune ayarlarıyla nasıl eşler?
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Microsoft 365 İş Ekstra'deki koruma özelliklerinin Intune ayarlarıyla nasıl eş olduğunu öğrenin. Abonelik, Intune ayarlarını değiştirmek için size bir lisans sağlar.
ms.openlocfilehash: 185eda9e5b5e214716608d4232a0ea81c00d6b4b
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096379"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Microsoft 365 İş Ekstra koruma özellikleri Intune ayarlarıyla nasıl eşler?

## <a name="android-and-ios-application-protection-settings"></a>Android ve iOS uygulama koruma ayarları

Aşağıdaki tabloda, Android ve iOS uygulama ilkesi ayarlarının Intune ayarlarıyla nasıl eşlendiği ayrıntılarıyla gösterilir.
  
Intune ayarını bulmak için Microsoft 365 İş Ekstra yönetici kimlik bilgilerinizle oturum açın, **Yönetici merkezlerine** gidin ve **Intune**.
  
 > [!IMPORTANT]
 > 
 > Microsoft 365 İş Ekstra aboneliği size tüm Intune ayarlarını değiştirme lisansı verir. [Başlamak için bkz. Intune giriş.](/intune/introduction-intune)
  
İstediğiniz &mdash; İlke adını seçin, örneğin Android &mdash; için uygulama ilkesi'ni ve ardından **İlke ayarları'nı** seçin.
  
**Cihaz kaybolursa veya çalınırsa iş dosyalarını koru** alanında
  
|**Android veya iOS uygulama ilkesi ayarı**|**Intune ayarları**|
|:-----|:-----|
|Şu süre sonunda iş dosyalarını etkin olmayan cihazdan sil  |Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden)  |
|Kullanıcıları, iş dosyalarını OneDrive İş'e kaydetmeye zorla  <br/> Yalnızca OneDrive İş'e izin verildiğini unutmayın  |Şirket verilerinin kaydedileceği depolama hizmetlerini seçin  |
   
**Kullanıcının mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet** alanında
  
|**Android veya iOS uygulama ilkesi ayarı**|**Intune ayarları**|
|:-----|:-----|
|Şu süre sonunda iş dosyalarını etkin olmayan cihazdan sil  |Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden)  |
|Kullanıcıları, iş dosyalarını OneDrive İş'e kaydetmeye zorla  <br/> Yalnızca OneDrive İş'e izin verildiğini unutmayın  |Şirket verilerinin kaydedileceği depolama hizmetlerini seçin  |
|İş dosyalarını şifrele  |Uygulama verilerini şifrele  |
|**Kullanıcının mobil cihazlarda Office dosyalarına nasıl erişeceğini yönet** alanında ||
|Office uygulamalarına erişirken PIN veya parmak izi iste  | Erişim için PIN iste  <br/>  Ayrıca şu ayarları da yapar:  <br/> **Basit PIN'e İzin Ver** için **Evet** <br/> **PIN Uzunluğu** için 4  <br/> **PIN yerine parmak izine izin ver** için **Evet** <br/> **Cihaz PIN'i yönetildiğinde uygulama PIN'ini devre dışı bırakma** için **Hayır** |
|Oturum açma işlemi bu kadar çok başarısız olduğunda PIN'i sıfırla (PIN gerekli değilse bu devre dışı bırakılır)  |PIN sıfırlamadan önceki deneme sayısı  |
|Office uygulamaları boşta kaldığında kullanıcıların yeniden oturum açmasını gerektir (PIN gerekli değilse bu devre dışı bırakılır)  | Şu sürenin ardından erişim gereksinimlerini yeniden denetle (dakika cinsinden)  <br/>  Ayrıca şu ayarları da yapar:  <br/> **Zaman aşımı** dakika sayısına ayarlanır  <br/>  Bu, Microsoft 365 İş içinde ayarladığınız dakika sayısıyla aynıdır.  <br/> **Çevrimdışı tanınan süre** değeri varsayılan olarak 720 dakikaya ayarlanır  |
|İşletim sistemi kısıtlamaları kaldırılmış veya kök erişim izni verilmiş cihazlardan iş dosyalarına erişilmesini engelle  |Yönetilen uygulamaların işletim sistemi kısıtlamaları kaldırılmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle  |
|Kullanıcıların Office uygulamalarından kişisel uygulamalara içerik kopyalamasına izin ver  | Kesme, kopyalama ve yapıştırma işlemlerini diğer uygulamalarla kısıtlama  <br/>  Microsoft 365 İş Ekstra seçeneği **Açık** olarak ayarlanırsa, bu üç seçenek de **Intune'deki Tüm Uygulamalar** olarak ayarlanır:  <br/> **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** <br/> **Uygulamanın diğer uygulamalardan veri almasına izin ver** <br/> **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla** <br/>  Microsoft 365 İş seçeneği **Açık** olarak ayarlandıysa, tüm Intune seçenekleri şöyle ayarlanır:  <br/> **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** seçeneği **İlke ile yönetilen uygulamalar** olarak ayarlanır <br/> **Uygulamanın diğer uygulamalardan veri almasına izin ver** seçeneği **Tüm Uygulamalar** olarak ayarlanır <br/> **Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla** seçeneği **İçine Yapıştırmayla İlke ile Yönetilen Uygulamalar** olarak ayarlanır |
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 uygulama koruma ayarları

Aşağıdaki tabloda, Windows 10 uygulama ilkesi ayarlarının Intune ayarlarıyla nasıl eşlendiği ayrıntılarıyla gösterilir.
  
Intune ayarını bulmak için Microsoft 365 İş Ekstra yönetici kimlik bilgilerinizle oturum açın ve [Azure portal](https://portal.azure.com) gidin. **Diğer hizmetler'i** seçin ve **Filtre'ye** Intune yazın. Uygulama Koruma \> **Uygulama İlkesi'ni Intune** seçin.
  
 > [!IMPORTANT]
 > Microsoft 365 İş Ekstra aboneliği, yalnızca Microsoft 365 İş Ekstra'da bulunan ayarlarla eşleşen Intune ayarlarını değiştirme lisansı verir. 
  
Kullanılabilir ayarları keşfetmek için, istediğiniz ilke adını seçin ve ardından sol gezinti **bölmesinden Genel, Atamalar,** **İzin verilen uygulamalar**, **Muaf uygulamalar**, **Gerekli ayarlar** veya **Gelişmiş ayarlar'ı** seçin. 
  
|**Windows 10 uygulama ilkesi ayarı**|**Intune ayarları**|
|:-----|:-----|
|İş dosyalarını şifrele  |**Gelişmiş ayarlar** \> **Veri koruma**: **Kayıt kaldırılırken şifreleme anahtarlarını iptal et** ve **Cihaz MDM'ye kaydedildiğinde korumalı verilere erişimi iptal et** seçeneklerinin ikisi de **Açık** olarak ayarlanır.  |
|Kullanıcıların şirket verilerini kişisel dosyalara kopyalamasını engeller.  |**Gerekli ayarlar** \> **Windows Bilgi Koruması modu**. Microsoft 365 İş Ekstra **içinde** şunun için açık: **Geçersiz Kılmaları Gizle**, **Kapalı**, Microsoft 365 İş Ekstra eşler: **Kapalı**.  |
|Office belgeleri erişimi denetimi  | Bu, Microsoft 365 İş Ekstra'da **Açık** olarak ayarlanırsa  <br/> **Gelişmiş ayarlar** \> **Erişim**, **Windows'ta oturum açma yöntemi olarak İş İçin Windows Hello kullan** seçeneği **Açık** olarak ayarlanır ve aşağıdaki ek ayarlar da yapılır:  <br/> **PIN için gerekli en az karakter sayısını ayarla** seçeneği **4** olarak ayarlanır.  <br/> **İş İçin Windows Hello PIN'inde büyük harf kullanımını yapılandır** seçeneği **PIN için büyük harf kullanımına izin verme** olarak ayarlanır.  <br/> **İş İçin Windows Hello PIN'inde küçük harf kullanımını yapılandır** seçeneği **PIN için küçük harf kullanımına izin verme** olarak ayarlanır.  <br/> **İş İçin Windows Hello PIN'inde özel karakter kullanımını yapılandır** seçeneği **PIN'de özel karakter kullanımına izin verme** olarak ayarlanır.  <br/> **Sistemin kullanıcının değiştirmesini gerektirmeden önce PIN'in 0 olarak ayarlanacağı süreyi (gün cinsinden) belirtin**.  <br/> **Tekrar kullanılamayan bir kullanıcı hesabı ile ilişkili eski PIN'lerin sayısını belirtin** seçeneği **0** olarak ayarlanır.  <br/> **Cihaz silinmeden önce izin verilen kimlik doğrulama hatası sayısı** seçeneği Microsoft 365 İş'tekiyle aynı değere ayarlanır (varsayılan olarak 5).  <br/> **Cihazın PIN'inin veya parolasının kilitlenmesine neden olan izin verilen en uzun boşta kalma süresi (dakika cinsinden)** seçeneği Microsoft 365 İş'tekiyle aynı değere ayarlanır.  |
|Korumalı verilerde kurtarmayı etkinleştir  |**Gelişmiş ayarlar** \> **Veri koruma**: **Kurumsal verileri koruma simgesini göster** ve **WIP için Azure RMS kullan** seçenekleri **Açık** olarak ayarlanır.  |
|Ek şirket bulut konumlarını koru  |**Gelişmiş ayarlar** \> **Korunan etki alanları** ve **Bulut kaynakları**, etki alanlarını ve SharePoint sitelerini gösterir.  |
|Bu uygulamaların kullandığı dosyalar korunur  |Korunan uygulamalar, **İzin verilen uygulamalar**'da listelenir.  |
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 cihaz koruma ayarları

Aşağıdaki tabloda, Windows 10 cihaz yapılandırma ayarlarının Intune ayarlarıyla nasıl eşlendiği ayrıntılarıyla gösterilir.
  
Intune ayarını bulmak için, Microsoft 365 İş Ekstra yönetici kimlik bilgilerinizle oturum açın ve [Azure portal](https://portal.azure.com) gidin, **ardından Diğer hizmetler'i** seçin ve **Filtre'ye** Intune yazın, **Cihaz yapılandırma** \> **Profillerini** **Intune** \> seçin . Ardından Windows 10 \> Özellikleri **Ayarları** **için Cihaz ilkesi'ni**  \> seçin.
  
|**Windows 10 cihazı ilkesi ayarı**|**Intune ayarları**|
|:-----|:-----|
|Microsoft Defender Virüsten Koruma kullanarak bilgisayarları virüslerden ve diğer tehditlerden korumaya yardımcı olun  |Gerçek Zamanlı İzlemeye İzin Ver = Açık  <br/> Bulut Korumasına İzin Ver = Açık  <br/> Kullanıcılardan Örnek Göndermelerini İste = Güvenli örnekleri otomatik olarak gönder (Varsayılan PII dışını otomatik gönder)  |
|Bilgisayarları Microsoft Edge'de web tabanlı tehditlere karşı korumaya yardımcı ol  |**Edge Tarayıcı Ayarları**'nda **SmartScreen** seçeneği **Gerekli** olarak ayarlanır.  |
|Cihaz şu kadar süreyle boşta kaldığında ekranı kapat (dakika)  |Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı  |
|Kullanıcıların Microsoft Store'ndan uygulama indirmesine izin ver  |Özel URI ilkesi  |
|Kullanıcıların Cortana'ya erişmesine izin ver  |**Genel** \> **Cortana**, Microsoft 365 İş Ekstra'da **kapalı** olarak ayarlandığında Intune'da **engelleyecek** şekilde ayarlanır.  |
|Kullanıcıların Microsoft'tan Windows ipucu ve reklam almasına izin ver  |**Windows spotlight**, bu ayar Microsoft 365 İş Ekstra kapalıysa tümü engellenir.  |
|Windows 10 cihazları otomatik olarak güncelleştir  | Bu ayar **Microsoft Intune** \> **Hizmet güncelleştirmelerindedir- Güncelleştirme Halkaları Windows 10****, Windows 10 cihazlar için ilkeyi güncelleştir'i** ve ardından **Özellikler Ayarları'nı** \> seçin.  <br/>  Microsoft 365 İş Ekstra ayarı **Açık** olarak ayarlandığında, aşağıdaki tüm ayarlar ayarlanır:  <br/> **Hizmet dalı** **CB** (Microsoft 365 İş Ekstra'de kapatıldığında CBB) olarak ayarlanır.  <br/> **Microsoft ürün güncelleştirmeleri** seçeneği **İzin ver** olarak ayarlanır.  <br/> **Windows sürücüleri** seçeneği **İzin ver** olarak ayarlanır.  <br/> **Otomatik güncelleştirme davranışı** seçeneği **Bakım zamanında otomatik yükle** olarak ayarlanır ve:  <br/> **Etkin saatlerin başlangıcı** için **06:00** ayarlanır.  <br/> **Etkin saatlerin sonu** için **22:00** ayarlanır.  <br/> **Kalite güncelleştirmesi erteleme süresi (gün)** için **0** ayarlanır.  <br/> **Özellik güncelleştirmesi erteleme süresi (gün)** için **0** ayarlanır.  <br/> **Teslimi iyileştirme indirme modu** için **Aynı NAT arkasında eşleme ile karışık HTTP** ayarlanır.  |

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)
