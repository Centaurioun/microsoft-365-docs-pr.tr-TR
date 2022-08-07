---
title: Mac'te Uç Nokta için Microsoft Defender'deki yenilikler
description: Mac'te önceki Uç Nokta için Microsoft Defender sürümlerindeki önemli değişiklikler hakkında bilgi edinin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: f617129218d9ce7f75204c45fba39109bf214680
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67275850"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Mac'te Uç Nokta için Microsoft Defender'deki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Diğer işletim sistemleriyle ilgili Uç Nokta için Microsoft Defender hakkında daha fazla bilgi için: 
- [Linux'ta Uç Nokta için Microsoft Defender'deki yenilikler](linux-whatsnew.md) 
- [iOS'ta Uç Nokta için Microsoft Defender'deki yenilikler](ios-whatsnew.md)</br>

<details>
  <summary>Ağustos 2022 (Derleme: 101.75.90 | Sürüm: 20.122071.17590.0)</summary>

&ensp;Yayın tarihi: **3 Ağustos 2022**<br/>
&ensp;Yayımlanma Tarihi: **3 Ağustos 2022**<br/>
&ensp;Derleme: **101.75.90**<br/>
&ensp;Sürüm: **20.122071.17590.0**<br/>
&ensp;Altyapı sürümü: **1.1.19300.3**<br/>
&ensp;İmza sürümü: **1.369.395.0**<br/>

**Yenilikler**

- çıkışına `mdatp health` , ağ koruma özelliğinin zorlama düzeyini sorgulamak için kullanılabilecek yeni bir alan eklendi. Yeni alan çağrılır `network_protection_enforcement_level` ve şu değerlerden birini alabilir: `audit`, `block`veya `disabled`.
- Aynı içeriğin birden çok algılamasının tehdit geçmişinde yinelenen girişlere yol açabileceği bir ürün hatası giderildi.
- Diğer hata düzeltmeleri.

<br/>
</details>

<details>
  <summary>Temmuz 2022 (Derleme: 101.73.77 | Sürüm: 20.122062.17377.0)</summary>

&ensp;Yayın tarihi: **21 Temmuz 2022**<br/>
&ensp;Yayımlanma Tarihi: **21 Temmuz 2022**<br/>
&ensp;Derleme: **101.73.77**<br/>
&ensp;Sürüm: **20.122062.17377.0**<br/>
&ensp;Altyapı sürümü: **1.1.19200.3**<br/>
&ensp;İmza sürümü: **1.367.1011.0**<br/>

**Yenilikler**

- Ağ uzantısı nedeniyle yazdırmanın başarıyla tamamlanamadığına ilişkin bir sorun giderildi
- [Dosya karması hesaplamasını yapılandırma](mac-preferences.md#configure-file-hash-computation-feature) seçeneği eklendi
- Bu derlemeden itibaren, ürün varsayılan olarak yeni kötü amaçlı yazılımdan koruma altyapısına sahip olacaktır
- Dosya kopyalama işlemleri için performans geliştirmeleri
- Hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Temmuz 2022 (Derleme: 101.71.18 | Sürüm: 20.122052.17118.0)</summary>

&ensp;Yayın tarihi: **7 Temmuz 2022**<br/>
&ensp;Yayımlanma Tarihi: **7 Temmuz 2022**<br/>
&ensp;Derleme: **101.71.18**<br/>
&ensp;Sürüm: **20.122052.17118.0**<br/>

**Yenilikler**

- `mdatp connectivity test` ürünün düzgün çalışması için gereken ek bir URL ile genişletilmiştir. Yeni URL şeklindedir [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- Şimdiye kadar ürün yeniden başlatma işlemleri arasında ürün günlüğü düzeyi kalıcı hale gelmedi. Bu sürümden başlayarak günlük düzeyini kalıcı hale getiren yeni bir komut satırı araç anahtarı vardır. Yeni komut şeklindedir `mdatp log level persist --level <level>`.
- Ürün yükleme paketinde nadir durumlarda güncelleştirmeler sırasında ürün durumu kaybına yol açabilen bir hata düzeltildi
- Dosya kopyalama işlemleri ve yerleşik macOS uygulamaları için performans iyileştirmeleri
- Hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Haziran 2022 (Derleme: 101.70.19 | Sürüm: 20.122051.17019.0)</summary>

&ensp;Yayın tarihi: **14 Haziran 2022**<br/>
&ensp;Yayımlanma Tarihi: **14 Haziran 2022**<br/>
&ensp;Derleme: **101.70.19**<br/>
&ensp;Sürüm: **20.122051.17019.0**<br/>

**Yenilikler**

- Tehditle ilgili bildirimlerin her zaman son kullanıcıya sunulmadığı bir hata düzeltildi.
- Performans iyileştirmeleri & diğer hata düzeltmeleri

<br/>
</details>


<details>
  <summary>Haziran 2022 (Derleme: 101.70.18 | Sürüm: 20.122042.17018.0)</summary>

&ensp;Yayın tarihi: **2 Haziran 2022**<br/>
&ensp;Yayımlanma Tarihi: **2 Haziran 2022**<br/>
&ensp;Derleme: **101.70.18**<br/>
&ensp;Sürüm: **20.122042.17018.0**<br/>

**Yenilikler**

- Yükleme paketinin bazen ürün güncelleştirmeleri sırasında süresiz olarak asılı kaldığı bir hata düzeltildi
- Ürünün bazen karantina klasörünün içindeki dosyaları yanlış algıladığı bir hata düzeltildi
- Performans iyileştirmeleri & diğer hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Mayıs 2022 (Derleme: 101.66.54 | Sürüm: 20.122041.16654.0) </summary>

&ensp;Yayın tarihi: **11 Mayıs 2022**<br/>
&ensp;Yayımlanma Tarihi: **11 Mayıs 2022**<br/>
&ensp;Derleme: **101.66.54**<br/>
&ensp;Sürüm: **20.122041.16654.0**<br/>


**Yenilikler**

- Bazı durumlarda doğru işlem yolunun yazdırılmaması sorunu `mdatp diagnostic real-time-protection-statistics` giderildi.
- Hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Nisan 2022 (Derleme: 101.64.15 | Sürüm: 20.122032.16415.0)</summary>

&ensp;Yayın tarihi: **26 Nisan 2022**<br/>
&ensp;Yayımlanma Tarihi: **26 Nisan 2022**<br/>
&ensp;Derleme: **101.64.15**<br/>
&ensp;Sürüm: **20.122032.16415.0**<br/>

**Yenilikler**

- Sürüm 101.61.69'da ortaya çıkan ve son kullanıcıdan hiçbir eylem gerekmese de durum menüsü simgesinin bazen hata simgesi gösterdiği bir regresyon düzeltildi
- `conflicting_applications` içindeki alanı `mdatp health` yalnızca en son 10 işlemi gösterecek şekilde ve işlem adlarını içerecek şekilde geliştirildi. Bu, Mac için Uç Nokta için Microsoft Defender hangi işlemlerin çakışıyor olduğunu belirlemeyi kolaylaştırır.
- Satıcı kimliği ve ürün kimliğinin onaltılık yerine ondalık olarak görüntülendiği bir hata `mdatp device-control removable-media policy list` düzeltildi
- Performans iyileştirmeleri & diğer hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Mart 2022 (Derleme: 101.61.69 | Sürüm: 20.122022.16169.0) </summary>

&ensp;Yayın tarihi: **25 Mart 2022**<br/>
&ensp;Yayımlanma Tarihi: **25 Mart 2022**<br/>
&ensp;Derleme: **101.61.69**<br/>
&ensp;Sürüm: **20.122022.16169.0**<br/>

**Yenilikler**

- Hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Mar-2022 (Derleme: 101.60.91 | Sürüm: 20.122021.16091.0)</summary>

&ensp;Yayın tarihi: **8 Mart 2022**<br/>
&ensp;Yayımlanma Tarihi: **8 Mart 2022**<br/>
&ensp;Derleme: **101.60.91**<br/>
&ensp;Sürüm: **20.122021.16091.0**<br/>

**Yenilikler**

- Bu sürüm [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) için bir güvenlik güncelleştirmesi içerir

<br/>
</details>

<details>
  <summary>Şubat 2022 (Derleme: 101.59.50 | Sürüm: 20.122021.15950.0) </summary>

&ensp;Yayın tarihi: **28 Şubat 2022**<br/>
&ensp;Yayımlanma Tarihi: **28 Şubat 2022**<br/>
&ensp;Derleme: **101.59.50**<br/>
&ensp;Sürüm: **20.122021.15950.0**<br/>

**Yenilikler**

- Bu sürüm macOS 12.3 için destek ekler. MacOS 12.3 sürümünden itibaren Apple, [Python 2.7'yi kaldırıyor](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes). MacOS'ta varsayılan olarak önceden yüklenmiş python sürümü yoktur. **EYLEM GEREKLI**: 
  - Kullanıcıların cihazlarını macOS Monterey 12.3(veya daha yeni) sürümüne güncelleştirmeden önce Mac için Uç Nokta için Microsoft Defender 101.59.50 (veya daha yeni) sürümüne güncelleştirmeleri gerekir. Bu en düşük sürüm 101.59.50, macOS Monterey'de Mac için Uç Nokta için Microsoft Defender ile ilgili Python ile ilgili sorunları ortadan kaldırmanın önkoşuludur.
  - Uzak dağıtımlar için, mevcut MDM kurulumları Mac için Uç Nokta için Microsoft Defender sürüm 101.59.50 (veya daha yeni) olarak güncelleştirilmelidir. MDM aracılığıyla macOS Monterey 12.3'e (veya daha yeni bir sürüme) Mac için eski bir Uç Nokta için Microsoft Defender göndererek yükleme hatasına neden olur.

<br/>
</details>

<details>
  <summary>Şubat 2022 (Derleme: 101.59.10 | Sürüm: 20.122012.15910.0)</summary>

&ensp;Yayın tarihi: **22 Şubat 2022**<br/>
&ensp;Yayımlanma Tarihi: **22 Şubat 2022**<br/>
&ensp;Derleme: **101.59.10**<br/>
&ensp;Sürüm: **20.122012.15910.0**<br/>

**Yenilikler**

- Komut satırı aracı artık karantinaya alınan dosyaların dosyanın ilk algılandığı konumdan farklı bir konuma geri yüklenmesini destekliyor. Bu işlem aracılığıyla `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`yapılabilir.
- Thunderbolt 3 üzerinden bağlanan cihazları işlemek için genişletilmiş cihaz denetimi
- Geçersiz satıcı kimlikleri ve ürün kimlikleri içeren cihaz denetimi ilkelerinin işlenmesi geliştirildi. Bu sürümden önce, ilke bir veya daha fazla geçersiz kimlik içeriyorsa ilkenin tamamı yoksayılırdı. Bu sürümden başlayarak, ilkenin yalnızca geçersiz bölümleri yoksayılır. İlkeyle ilgili sorunlar aracılığıyla `mdatp device-control removable-media policy list`ortaya konur.
- Hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Şubat 2022 (Derleme: 101.56.62 | Sürüm: 20.121122.15662.0)</summary>

&ensp;Yayın tarihi: **7 Şubat 2022**<br/>
&ensp;Yayımlanma Tarihi: **7 Şubat 2022**<br/>
&ensp;Derleme: **101.56.62**<br/>
&ensp;Sürüm: **20.121122.15662.0**<br/>

**Yenilikler**

- Hata düzeltmeleri 

<br/>
</details>

<details>
  <summary> Ocak 2022 (Derleme: 101.56.35 | Sürüm: 20.121121.15635.0)</summary>

&ensp;Yayın tarihi: **30 Ocak 2022**<br/>
&ensp;Yayımlanma Tarihi: **30 Ocak 2022**<br/>
&ensp;Derleme: **101.56.35**<br/>
&ensp;Sürüm: **20.121121.15635.0**<br/>

**Yenilikler**

- Uygulama "Microsoft Defender ATP" olarak "Microsoft Defender" olarak yeniden adlandırıldı. Son kullanıcılar aşağıdaki değişiklikleri gözlemler:
- Uygulama yükleme yolu olarak değiştirildi `/Application/Microsoft Defender ATP.app` `/Applications/Microsoft Defender.app`.
- Kullanıcı deneyiminde " Microsoft Defender ATP" oluşumları "Microsoft Defender" ile değiştirilmiştir
- Mac için Uç Nokta için Microsoft Defender ile dağıtılan ağ içerik filtresi nedeniyle bazı VPN uygulamalarının bağlanamadığı bir sorun çözüldü
- macOS 12.2 beta 2'de bulunan ve işletim sistemindeki (işletim sistemi) belirli özelliklere sahip paketlerin yüklenmesini engelleyen bir değişiklik nedeniyle yükleme paketinin açılamadığı bir sorun giderildi. Bu işletim sistemi değişikliği macOS 12.2'nin son sürümünde yer almamış gibi görünse de, gelecekteki bir macOS sürümünde yeniden kullanıma sunulacaktır. Bu nedenle, tüm kuruluş yöneticilerinin yönetim konsolundaki Uç Nokta için Microsoft Defender paketini bu ürün sürümüne (veya daha yeni bir sürüme) yenilemelerini öneririz.
- Bazı M1 cihazlarında görülen ve ürünün geçersiz kötü amaçlı yazılımdan koruma tanımlarıyla takıldığı ve çalışan bir tanım kümesine başarıyla güncelleştirilemediği bir sorun giderildi.
- `mdatp health`çıktısı, Mac için Uç Nokta için Microsoft Defender tüm bileşenlerine Tam Disk Erişimi verilip verilmediğini belirlemek için kullanılabilecek adlı `full_disk_access_enabled` ek bir öznitelikle genişletilmiştir.
- Performans iyileştirmeleri & hata düzeltmeleri

<br/>
</details>

<details>
  <summary>Ocak 2022 (Derleme: 101.54.16 | Sürüm: 20.121111.15416.0) </summary>

&ensp;Yayın tarihi: **12 Ocak 2022**<br/>
&ensp;Yayımlanma Tarihi: **12 Ocak 2022**<br/>
&ensp;Derleme: **101.54.16**<br/>
&ensp;Sürüm: **20.121111.15416.0**<br/>

**Yenilikler**

- macOS 10.14 (Mojave) artık desteklenmiyor
- Bir ürün ayarı MDM aracılığıyla yönetici tarafından yönetilmeyi durdurduktan sonra, yönetilmeden önce sahip olduğu değere geri döner (son kullanıcı tarafından yerel olarak yapılandırılan değer veya böyle bir yerel değer açıkça sağlanmazsa, ürün tarafından kullanılan varsayılan değer). Bu değişiklikten önce, bir ayar yönetilmeyi durdurduktan sonra yönetilen değeri kalıcı hale gelip ürün tarafından kullanılmaya devam etti.
- Performans iyileştirmeleri & hata düzeltmeleri
    
<br/>
</details>

<details><summary>2021 sürümleri </summary><blockquote>
    <details><summary>(Derleme: 101.49.25 | Sürüm: 20.121092.14925.0)</summary>

&ensp;Derleme: **101.49.25**<br/>
&ensp;Sürüm: **20.121092.14925.0** <br/>

**Yenilikler**

- İsteğe bağlı taramalar sırasında arşivlerin taranıp taranmayacağını denetlemek için komut satırı aracına yeni bir anahtar eklendi. Bu, aracılığıyla `mdatp config scan-archives --value [enabled/disabled]` yapılandırılabilir. Varsayılan olarak, bu etkin olarak ayarlanır. 
- Hata düzeltmeleri  

<br/>
</details>
 
<details><summary>(Derleme: 101.47.27 | Sürüm: 20.121082.14727.0)</summary>

&ensp;Derleme: **101.47.27**<br/>
&ensp;Sürüm: **20.121082.14727.0** <br/>

**Yenilikler**
- macOS Mojave ve macOS Catalina'da kapatma sırasında oluşan sistem donması için düzeltme. 

<br/>
</details>

<details><summary>(Derleme: 101.43.84 | Sürüm: 20.121082.14384.0)</summary>

&ensp;Derleme: **101.43.84**<br/>
&ensp;Sürüm: **20.121082.14384.0** <br/>

**Yenilikler**
- macOS 12 için aday derleme (Monterey) 
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.41.10 | Sürüm: 20.121072.14110.0)</summary>

&ensp;Derleme: **101.41.10**<br/>
&ensp;Sürüm: **20.121072.14110.0** <br/>

**Yenilikler**
- Komut satırı aracına yeni anahtarlar eklendi: 
    - İsteğe bağlı taramalar için paralellik derecesini denetleme. Bu, aracılığıyla `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]` yapılandırılabilir. Varsayılan olarak, 2'nin paralellik derecesi kullanılır. 
    - Güvenlik bilgileri güncelleştirmelerinin etkinleştirilip etkinleştirilmediğini veya devre dışı bırakılıp bırakılmayacağını denetleyin. Bu, aracılığıyla `mdatp config scan-after-definition-update --value [enabled/disabled]` yapılandırılabilir. Varsayılan olarak, bu etkin olarak ayarlanır. 
- Ürün günlüğü düzeyini değiştirmek için artık yükseltme gerekiyor. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.40.84 | Sürüm: 20.121071.14084.0)</summary>

&ensp;Derleme: **101.40.84**<br/>
&ensp;Sürüm: **20.121071.14084.0** <br/>

**Yenilikler**
- M1 yonga yerel desteği 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.37.97 | Sürüm: 20.121062.13797.0)</summary>

&ensp;Derleme: **101.37.97**<br/>
&ensp;Sürüm: **20.121062.13797.0** <br/>

**Yenilikler**
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.34.28 | Sürüm: 20.121061.13428.0)</summary>

&ensp;Derleme: **101.34.28**<br/>
&ensp;Sürüm: **20.121061.13428.0** <br/>

**Yenilikler**
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.34.27 | Sürüm: 20.121052.13427.0)</summary>

&ensp;Derleme: **101.34.27**<br/>
&ensp;Sürüm: **20.121052.13427.0** <br/>

**Yenilikler**
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.34.20 | Sürüm: 20.121051.13420.0)</summary>

&ensp;Derleme: **101.34.20**<br/>
&ensp;Sürüm: **20.121051.13420.0** <br/>

**Yenilikler**
- [macOS](mac-device-control-overview.md)  için cihaz denetimi artık genel kullanılabilirlik aşamasındadır. 
- macOS 11'de (Big Sur) durum menüsünden hızlı taramanın başlatılamadığı bir sorun giderildi. 
- Diğer hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.32.69 | Sürüm: 20.121042.13269.0)</summary>

&ensp;Derleme: **101.32.69**<br/>
&ensp;Sürüm: **20.121042.13269.0** <br/>

**Yenilikler**
- Uç Nokta için Microsoft Defender ve diğer uygulamalardan anahtarlığa eşzamanlı erişimin anahtar zinciri bozulmasına yol açması sorunu giderildi.

<br/>
</details>

<details><summary>(Derleme: 101.29.64 | Sürüm: 20.121042.12964.0)</summary>

&ensp;Derleme: **101.29.64**<br/>
&ensp;Sürüm: **20.121042.12964.0** <br/> 

**Yenilikler**
- Bu sürümden başlayarak, komut satırı istemcisi aracılığıyla tetiklenen isteğe bağlı virüsten koruma taramaları sırasında algılanan tehditler otomatik olarak düzeltilir. Kullanıcı arabirimi aracılığıyla tetiklenen taramalar sırasında algılanan tehditler yine de el ile eylem gerektirir. 
- `mdatp diagnostic real-time-protection-statistics` şimdi iki ek anahtarı destekler: 
    - `--sort`: Taranan toplam dosya sayısına göre azalan çıktıyı sıralar 
    - `--top N`: en iyi N sonuçlarını görüntüler (yalnızca belirtilirse `--sort` çalışır) 
- Performans iyileştirmeleri (özellikle `YARN` kullanıldığında) & hata düzeltmeleri

<br/>
</details>

<details><summary>(Derleme: 101.27.50 | Sürüm: 20.121022.12750.0)</summary>

&ensp;Derleme: **101.27.50**<br/>
&ensp;Sürüm: **20.121022.12750.0** <br/> 

**Yenilikler**
- macOS Catalina ve önceki sürümlerde Apple sertifikası süre sonu için uyum sağlama düzeltmesi. Bu düzeltme, Tehdit & Güvenlik Açığı Yönetimi (TVM) işlevselliğini geri yükler.  

<br/>
</details>

<details><summary>(Derleme: 101.25.69 | Sürüm: 20.121022.12569.0)</summary>

&ensp;Derleme: **101.25.69**<br/>
&ensp;Sürüm: **20.121022.12569.0** <br/> 

**Yenilikler**
- macOS'taki Uç Nokta için Microsoft Defender artık ABD Kamu müşterileri için önizleme sürümünde kullanıma sunulmuştur. Daha fazla bilgi için bkz [. US Government müşterileri için Uç Nokta için Microsoft Defender](gov.md). 
- Performans iyileştirmeleri (özellikle XCode Simülatörü uygulamasının kullanıldığı durum için) hata düzeltmeleri &. 

<br/>
</details>

<details><summary>(Derleme: 101.23.64 | Sürüm: 20.121021.12364.0)</summary>

&ensp;Derleme: **101.23.64**<br/>
&ensp;Sürüm: **20.121021.12364.0** <br/> 

**Yenilikler**
- Son isteğe bağlı tarama hakkındaki bilgileri görüntülemek için komut satırı aracına yeni bir seçenek eklendi. Son isteğe bağlı tarama hakkındaki bilgileri görüntülemek için komutunu çalıştırın `mdatp health --details antivirus`. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

</details>

<details><summary>Önceki sürümler </summary><blockquote>
<details><summary>(Derleme: 101.22.79 | Sürüm: 20.121012.12279.0)</summary>

&ensp;Derleme: **101.22.79** <br> &ensp;Sürüm: **20.121012.12279.0**<br>

**Yenilikler**
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.19.88 | Sürüm: 20.121011.11988.0)</summary>

&ensp;Derleme:**101.19.88**<br>
&ensp;Sürüm: **20.121011.11988.0**<br>

**Yenilikler**
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.19.48 | Sürüm: 20.120121.11948.0)</summary>

&ensp;Derleme: **101.19.48**<br>
&ensp;Sürüm: **20.120121.11948.0**<br>

**Yenilikler**
> [!NOTE]
> Eski komut satırı aracının söz dizimi bu sürümle kullanım dışı bırakıldı. Yeni söz dizimi hakkında bilgi için bkz [. Kaynaklar](mac-resources.md#configuring-from-the-command-line). 
- Ağ uzantısını devre dışı bırakmak için yeni bir komut satırı anahtarı eklendi: `mdatp system-extension network-filter disable` Bu komut, Mac'te Uç Nokta için Microsoft Defender ile ilgili olabilecek ağ sorunlarını gidermek için yararlı olabilir. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.19.21 | Sürüm: 20.120101.11921.0)</summary>

&ensp;Derleme: **101.19.21**<br>
&ensp;Sürüm: **20.120101.11921.0** <br>

**Yenilikler**
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.15.26 | Sürüm: 20.120102.11526.0)</summary>

&ensp;Derleme: **101.15.26**<br>
&ensp;Sürüm: **20.120102.11526.0**<br>

**Yenilikler**
- macOS 11 Big Sur'da çalışırken aracının güvenilirliği geliştirildi. 
- Özel taramalar () sırasında AV dışlamalarını yoksaymak için yeni bir komut satırı anahtarı`--ignore-exclusions` (`mdatp scan custom`) eklendi. 
- Performans iyileştirmeleri & hata düzeltmeleri

<br/> 
</details>

<details><summary>(Derleme: 101.13.75 | Sürüm: 20.120101.11375.0)</summary>

&ensp;Derleme: **101.13.75**<br>
&ensp;Sürüm: **20.120101.11375.0**<br>

**Yenilikler** 
- Uç Nokta için Microsoft Defender çekirdek paniğine dönüşen bir macOS 11 (Big Sur) hatasını tetiklediğinde koşullar kaldırıldı. 
- mac 11 (Big Sur) üzerinde çalışırken Endpoint Security sistem uzantısındaki bellek sızıntısı düzeltildi. 
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.10.72)</summary>

&ensp;Derleme: **101.10.72** <br>

**Yenilikler** 
- Hata düzeltmeleri  

<br/>
</details>

<details><summary>(Derleme: 101.09.61)</summary>

&ensp;Derleme: **101.09.61**<br>

**Yenilikler** 
-  [Geri bildirim gönderme seçeneğini devre dışı bırakmak](mac-preferences.md#show--hide-option-to-send-feedback) için yeni bir yönetilen tercih eklendi. 
- Durum menüsü simgesi artık ürün ayarları yönetildiğinde iyi durumda bir durum gösteriyor. Daha önce, ürün ayarları yönetici tarafından yönetilse bile durum menüsü simgesi bir uyarı veya hata durumu görüntülüyordu. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.09.50)</summary>

&ensp;Derleme: **101.09.50**<br>

**Yenilikler** 
- Bu ürün sürümü macOS Big Sur 11 beta 9 üzerinde doğrulanmıştır. 
- mdatp komut satırı aracının yeni söz dizimi artık varsayılan söz dizimidir. Yeni söz dizimi hakkında daha fazla bilgi için bkz [. macOS'ta Uç Nokta için Microsoft Defender için kaynaklar](mac-resources.md#configuring-from-the-command-line). 
> [!NOTE]
> Eski komut satırı aracının söz dizimi **1 Ocak 2021'de** üründen kaldırılacaktır.
- Tanılama günlüklerinin farklı bir dizine kaydedilmesini sağlayan yeni bir parametre (`--path [directory]`) ile genişletilmiş. `mdatp diagnostic create`  
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.09.49)</summary>

&ensp;Derleme: **101.09.49**<br>

**Yenilikler** 
- BT yöneticisi tarafından yönetilen dışlamaları yerel kullanıcı tarafından tanımlanan dışlamalarla ayırt etmeye yönelik kullanıcı arabirimi geliştirmeleri. 
- İsteğe bağlı taramalar sırasında geliştirilmiş CPU kullanımı. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.07.23)</summary>

&ensp;Derleme: **101.07.23**<br>

**Yenilikler** 
- Pasif modun durumunu ve EDR grup kimliğini denetlemek için çıkışına `mdatp --health` yeni alanlar eklendi. 
> [!NOTE]
> `mdatp --health` , gelecekteki bir ürün güncelleştirmesinde ile `mdatp health` değiştirilecektir. 
- Otomatik örnek gönderiminin kullanıcı arabiriminde yönetilen olarak işaretlenmediği bir hata düzeltildi. 
- Virüsten koruma tarama geçmişindeki öğelerin saklamasını denetlemek için yeni ayarlar eklendi. Artık [tarama geçmişindeki öğelerin tutulacak gün sayısını belirtebilir ve tarama geçmişindeki](mac-preferences.md#antivirus-scan-history-retention-in-days)  [en fazla öğe sayısını belirtebilirsiniz](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history). 
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.06.63)</summary>

&ensp;Derleme: **101.06.63**<br>

**Yenilikler** 
- Sürümde ortaya çıkan performans regresyonu giderildi `101.05.17`. Regresyon, bazı müşterilerin SMB paylaşımlarına erişirken gözlemlediği çekirdek paniğinin ortadan kaldırılmasına yönelik düzeltme ile sunulmuştur. Bu kod değişikliğini geri aldık ve çekirdek paniğini ortadan kaldırmak için alternatif yollar araştırıyoruz. 

<br/>
</details>

<details><summary>(Derleme: 101.05.17)</summary>

&ensp;Derleme: **101.05.17**<br> 

**Yenilikler** 
> [!IMPORTANT]
> Komut satırı aracı için `mdatp` yeni ve gelişmiş bir söz dizimi üzerinde çalışıyoruz. Yeni söz dizimi şu anda Insider Hızlı ve Insider Yavaş güncelleştirme kanallarında varsayılandır. Bu yeni söz dizimi ile kendinizi özetlemenizi öneririz. Eski söz dizimini yeni söz dizimiyle paralel olarak desteklemeye devam edeceğiz ve önümüzdeki aylarda eski söz dizimi için kullanımdan kaldırma planıyla ilgili daha fazla iletişim sağlayacağız. 
- Bazen SMB dosya paylaşımlarına erişilirken oluşan çekirdek paniği giderildi. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.05.16)</summary>

&ensp;Derleme: **101.05.16**<br>

**Yenilikler** 
- Taranan dosyaların sayısını önemli ölçüde azaltmak için hızlı tarama mantığını geliştirme. 
- Komut satırı aracı için [otomatik tamamlama desteği](mac-resources.md#how-to-enable-autocompletion) eklendi. 
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.03.12)</summary>

&ensp;Derleme: **101.03.12**<br>

**Yenilikler** 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.01.54)</summary>

&ensp;Derleme: **101.01.54**<br>

**Yenilikler** 
- Time Machine ile uyumlulukla ilgili iyileştirmeler 
- Erişilebilirlik geliştirmeleri 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 101.00.31)</summary>

&ensp;Derleme: **101.00.31** <br>

**Yenilikler** 
-  [Intune kullanıcıları için geliştirilmiş ürün ekleme deneyimi](/mem/intune/apps/apps-advanced-threat-protection-macos) 
- Virüsten [koruma dışlamaları artık joker karakterleri destekliyor](mac-exclusions.md#supported-exclusion-types)
- macOS bağlam menüsünden virüsten koruma taramalarını tetikleme özelliği eklendi. Artık Bulucu'da bir dosyaya veya klasöre sağ tıklayıp **Uç Nokta için Microsoft Defender ile tara'yı** seçebilirsiniz. 
- Yerinde ürün düşürme işlemlerine artık yükleyici tarafından açıkça izin verilmiyor. Eski sürüme düşürmeniz gerekiyorsa, önce mevcut sürümü kaldırın ve cihazınızı yeniden yapılandırın. 
- Hata düzeltmeleri & diğer performans iyileştirmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.90.27)</summary>

&ensp;Derleme: **100.90.27** <br>   

**Yenilikler** 
- Artık macOS'ta Uç Nokta için Microsoft Defender için sistem genelindeki [güncelleştirme kanalından](mac-updates.md#set-the-channel-name) farklı bir güncelleştirme kanalı ayarlayabilirsiniz. 
- Yeni ürün simgesi 
- Diğer kullanıcı deneyimi geliştirmeleri 
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.86.92)</summary>

&ensp;Derleme: **100.86.92**<br>

**Yenilikler** 
- Time Machine ile uyumlulukla ilgili iyileştirmeler 
- Ürünün bazen kaldırma sırasında altındaki tüm dosyaları `/Library/Application Support/Microsoft/Defender` temizlememesi sorunu giderildi. 
- Microsoft ürünleri Microsoft AutoUpdate aracılığıyla güncelleştirildiğinde ürünün CPU kullanımı azaltıldı. 
- Hata düzeltmeleri & diğer performans iyileştirmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.86.91)</summary>

&ensp;Derleme: **100.86.91**<br>

**Yenilikler**
> [!CAUTION]
> macOS cihazlarınız için en eksiksiz korumayı sağlamak ve Apple'ın macOS yerel güvenlik güncelleştirmelerinin [current - 2] sürümünden eski işletim sistemi sürümlerine teslimini durdurmasıyla uyumlu olması için Mac için MDATP dağıtımı ve güncelleştirmeleri artık macOS Sierra'da desteklenmeyecektir [10.12]. Mac için MDATP güncelleştirmeleri ve geliştirmeleri Catalina [10.15], Mojave [10.14] ve High Sierra [10.13] sürümlerini çalıştıran cihazlara sunulacaktır.
>
> Sierra [10.12] cihazlarınıza zaten Mac için MDATP dağıttıysanız koruma kaybı riskini ortadan kaldırmak için lütfen en son macOS sürümüne yükseltin.

-  Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.83.73)</summary>

&ensp;Derleme: **100.83.73**<br>

**Yenilikler**
- BT yöneticileri için [dışlamaların yönetimi](mac-preferences.md#exclusion-merge-policy),  [tehdit türü ayarlarının yönetimi](mac-preferences.md#threat-type-settings-merge-policy) ve [izin verilmeyen tehdit eylemleri](mac-preferences.md#disallowed-threat-actions) hakkında daha fazla denetim eklendi. 
- Cihazda Tam Disk Erişimi etkinleştirilmediğinde, artık durum menüsünde bir uyarı görüntülenir. 
- Performans iyileştirmeleri & hata düzeltmeleri
 
<br/>
</details>

<details><summary>(Derleme: 100.82.60)</summary>

&ensp;Derleme: **100.82.60** <br>

**Yenilikler**
- Ürünün bir tanım güncelleştirmesini takip etmeye başlayamaması sorunu giderildi.

<br/> 
</details>

<details><summary>(Derleme: 100.80.42)</summary>

&ensp;Derleme: **100.80.42**<br>

**Yenilikler**
- Hata düzeltmeleri

<br/> 
</details>

<details><summary>(Derleme: 100.79.42)</summary>

&ensp;Derleme: **100.79.42**<br>

**Yenilikler**
- Mac'te Uç Nokta için Microsoft Defender zaman zaman Time Machine'i engellemesi sorunu düzeltildi. 
- Arka uç hizmetiyle bağlantıyı test etmek için komut satırı yardımcı programı için yeni bir anahtar eklendi
 
  ```bash
  mdatp connectivity test
  ```
- Kullanıcı arabiriminde tehdit geçmişinin tamamını görüntüleme özelliği eklendi ( **Koruma geçmişi** görünümünden erişilebilir). 
- Performans iyileştirmeleri & hata düzeltmeleri

<br/>
</details>

<details><summary>(Derleme: 100.72.15)</summary> 

&ensp;Derleme: **100.72.15**<br>

**Yenilikler**
- Hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.70.99)</summary> 

&ensp;Derleme: **100.70.99**<br>

**Yenilikler**
- Gerçek zamanlı koruma etkinleştirildiğinde bazı kullanıcıların macOS Catalina'ya yükseltme yeteneğini etkileyen bir sorun giderildi. Bu düzensiz sorun, catalina yükseltme paketindeki dosyaları tehditlere karşı tararken Uç Nokta için Microsoft Defender kilitlemeden kaynaklandı ve bu da yükseltme sırasında hatalara yol açtı.

<br/>
</details> 

<details><summary>(Derleme: 100.68.99)</summary> 

&ensp;Derleme: **100.68.99**<br>

**Yenilikler**
- Virüsten koruma işlevini [pasif modda](mac-preferences.md#enforcement-level-for-antivirus-engine) çalışacak şekilde yapılandırma özelliği eklendi. 
- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<details><summary>(Derleme: 100.65.28)</summary> 

&ensp;Derleme: **100.65.28**<br>

**Yenilikler**
- macOS Catalina desteği eklendi. 
> [!CAUTION]
> macOS 10.15 (Catalina), yeni güvenlik ve gizlilik geliştirmeleri içerir. Bu sürümden başlayarak, uygulamalar varsayılan olarak açık onay olmadan disk üzerindeki belirli konumlara (Belgeler, İndirmeler, Masaüstü vb.) erişemez. Bu onay olmadığında, Uç Nokta için Microsoft Defender cihazınızı tam olarak koruyamaz.
> 
> Bu onayı verme mekanizması, Uç Nokta için Microsoft Defender nasıl dağıtdığınıza bağlıdır:
> 
> - El ile dağıtımlar için [El ile dağıtım konusunda](mac-install-manually.md#how-to-allow-full-disk-access) güncelleştirilmiş yönergelere bakın.
> - Yönetilen dağıtımlar için [JAMF tabanlı dağıtım ve Microsoft Intune tabanlı dağıtım](mac-install-with-jamf.md) konularındaki güncelleştirilmiş yönergelere bakın. [](mac-install-with-intune.md#create-system-configuration-profiles) 

- Performans iyileştirmeleri & hata düzeltmeleri 

<br/>
</details>

<br/><br/>
</details>