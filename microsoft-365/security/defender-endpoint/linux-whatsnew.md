---
title: Linux'ta Uç Nokta için Microsoft Defender'deki yenilikler
description: Linux'ta Uç Nokta için Microsoft Defender için önemli değişikliklerin listesi.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, whatsnew, release
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 8cddb2ab6a1f56fddb9be30d33a0934e3189845b
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67661025"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender'deki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Bu makale, Linux'ta Uç Nokta için Microsoft Defender'nin en son sürümlerindeki yenilikler hakkında bilgi edinmek için sık sık güncelleştirilir. 

- [macOS'ta Uç Nokta için Defender'daki yenilikler](mac-whatsnew.md)
- [iOS'ta Uç Nokta için Defender'daki yenilikler](ios-whatsnew.md)

<details>
  <summary>Eylül 2022 (Derleme: 101.80.97 | Sürüm: 30.122072.18097.0)</summary>

&ensp;Yayın tarihi: **14 Eylül 2022**<br/>
&ensp;Yayımlanma Tarihi: **14 Eylül 2022**<br/>
&ensp;Derleme: **101.80.97**<br/>
&ensp;Sürüm: **30.122072.18097.0**<br/>
&ensp;Altyapı sürümü: **1.1.19300.3**<br/>
&ensp;İmza sürümü: **1.369.395.0**<br/>

**Yenilikler**

- mdatp sürüm 101.75.43 çalıştıran belirli müşteri iş yüklerinde gözlemlenen çekirdek kilitlenmesini düzeltir. RCA'nın ardından bu, bir algılayıcı dosya tanımlayıcısının sahipliğini serbest bırakırken bir yarış durumuna atfedildi. Kapatma yolundaki son ürün değişikliği nedeniyle yarış durumu ortaya çıktı. Daha yeni Çekirdek sürümleri (5.1+) üzerindeki müşteriler bu sorundan etkilenmez.
</br>

<br/><br/>
</details>

<details>
  <summary>Ağustos 2022 (Derleme: 101.75.43 | Sürüm: 30.122071.17543.0)</summary>

&ensp;Yayın tarihi: **2 Ağustos 2022**<br/>
&ensp;Yayımlanma Tarihi: **2 Ağustos 2022**<br/>
&ensp;Derleme: **101.75.43**<br/>
&ensp;Sürüm: **30.122071.17543.0**<br/>
&ensp;Altyapı sürümü: **1.1.19300.3**<br/>
&ensp;İmza sürümü: **1.369.395.0**<br/>

**Yenilikler**

- Red Hat Enterprise Linux sürüm 9.0 desteği eklendi
- çıkışına `mdatp health` , ağ koruma özelliğinin zorlama düzeyini sorgulamak için kullanılabilecek yeni bir alan eklendi. Yeni alan çağrılır `network_protection_enforcement_level` ve şu değerlerden birini alabilir: `audit`, `block`veya `disabled`.
- Aynı içeriğin birden çok algılamasının tehdit geçmişinde yinelenen girişlere yol açabileceği bir ürün hatası giderildi
- Hizmet durdurulduğunda ürün (`mdatp_audisp_plugin`) tarafından oluşturulan işlemlerden birinin bazen düzgün şekilde sonlandırılmaması sorunu giderildi
- Diğer hata düzeltmeleri
</br>

<br/><br/>
</details>

<details>
  <summary>Temmuz 2022 (Derleme: 101.73.77 | Sürüm: 30.122062.17377.0)</summary>

&ensp;Yayın tarihi: **21 Temmuz 2022**<br/>
&ensp;Yayımlanma Tarihi: **21 Temmuz 2022**<br/>
&ensp;Derleme: **101.73.77**<br/>
&ensp;Sürüm: **30.122062.17377.0**<br/>
&ensp;Altyapı sürümü: **1.1.19200.3**<br/>
&ensp;İmza sürümü: **1.367.1011.0**<br/>


**Yenilikler**

- [Dosya karması hesaplamasını yapılandırma](linux-preferences.md#configure-file-hash-computation-feature) seçeneği eklendi
- Bu derlemeden itibaren, ürün varsayılan olarak yeni kötü amaçlı yazılımdan koruma altyapısına sahip olacaktır
- Dosya kopyalama işlemleri için performans geliştirmeleri
- Hata düzeltmeleri
</br>

<br/><br/>
</details>

<details>
  <summary>Haziran 2022 (Derleme: 101.71.18 | Sürüm: 30.122052.17118.0)</summary>

&ensp;Yayın tarihi: **24 Haziran 2022**<br/>
&ensp;Yayımlanma Tarihi: **24 Haziran 2022**<br/>
&ensp;Derleme: **101.71.18**<br/>
&ensp;Sürüm: **30.122052.17118.0**<br/>


**Yenilikler**

- v2 tanım güncelleştirmeleri için standart olmayan konumlarda (/var dışında) tanım depolamayı desteklemeye yönelik düzeltme
- RHEL 6'da kullanılan ürün sensöründe işletim sisteminin kilitlenmesine yol açabilecek bir sorun düzeltildi
- `mdatp connectivity test` ürünün düzgün çalışması için gereken ek bir URL ile genişletilmiştir. Yeni URL şeklindedir [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- Şimdiye kadar ürün yeniden başlatma işlemleri arasında ürün günlüğü düzeyi kalıcı hale gelmedi. Bu sürümden başlayarak günlük düzeyini kalıcı hale getiren yeni bir komut satırı araç anahtarı vardır. Yeni komut şeklindedir `mdatp log level persist --level <level>`.
- Ürün yükleme paketinden bağımlılığı `python` kaldırıldı
- Dosya kopyalama işlemleri ve kaynak ağ olaylarının işlenmesi için performans iyileştirmeleri `auditd`
- Hata düzeltmeleri
</br>

<br/><br/>
</details>


<details>
  <summary>Mayıs 2022 (Derleme: 101.68.80 | Sürüm: 30.122042.16880.0)</summary>

&ensp;Yayın tarihi: **23 Mayıs 2022**<br/>
&ensp;Yayımlanma Tarihi: **23 Mayıs 2022**<br/>
&ensp;Derleme: **101.68.80**<br/>
&ensp;Sürüm: **30.122042.16880.0**<br/>

**Yenilikler** 

- RHEL 6'da çalışırken çekirdek sürümü `2.6.32-754.47.1.el6.x86_64` desteği eklendi
- RHEL 6'da ürün artık Bölünemez Kurumsal Çekirdek (UEK) çalıştıran cihazlara yüklenebilir
- İşlem adının bazen çalışırken yanlış görüntülenmesine neden olan bir sorun düzeltildi `unknown``mdatp diagnostic real-time-protection-statistics`
- Ürünün bazen karantina klasörünün içindeki dosyaları yanlış algıladığı bir hata düzeltildi
- Komut satırı aracının `mdatp` geçici bağlantı olarak bağlandığında çalışmaması `/opt` sorunu düzeltildi
- Performans iyileştirmeleri & hata düzeltmeleri
</br>

<br/><br/>
</details>

<details>
<summary>Mayıs 2022 (Derleme: 101.65.77 | Sürüm: 30.122032.16577.0)</summary>

&ensp;Yayın tarihi: **2 Mayıs 2022**<br/>
&ensp;Yayımlanma Tarihi: **2 Mayıs 2022**<br/>
&ensp;Derleme: **101.65.77**<br/>
&ensp;Sürüm: **30.122032.16577.0**<br/>


**Yenilikler**

- `conflicting_applications` içindeki alanı `mdatp health` yalnızca en son 10 işlemi gösterecek şekilde ve işlem adlarını içerecek şekilde geliştirildi. Bu, Linux için Uç Nokta için Microsoft Defender hangi işlemlerin çakışıyor olduğunu belirlemeyi kolaylaştırır.
- Hata düzeltmeleri


<br/><br/>
</details><details>
<summary>Mart 2022 (Derleme: 101.62.74 | Sürüm: 30.122022.16274.0)</summary>

&ensp;Yayın tarihi: **24 Mart 2022**<br/>
&ensp;Yayımlanma Tarihi: **24 Mart 2022**<br/>
&ensp;Derleme: **101.62.74**<br/>
&ensp;Sürüm: **30.122022.16274.0**<br/>


**Yenilikler**

- Ürünün eski çekirdek sürümlerinde çalışırken boyutu 2 GB'tan büyük dosyalara erişimi yanlış engellemesi sorunu giderildi
- Hata düzeltmeleri


<br/><br/>
</details><details>
<summary>Mart 2022 (Derleme: 101.60.93 | Sürüm: 30.122012.16093.0)</summary>

&ensp;Yayın tarihi: **9 Mart 2022**<br/>
&ensp;Yayımlanma Tarihi: **9 Mart 2022**<br/>
&ensp;Derleme: **101.60.93**<br/>
&ensp;Sürüm: **30.122012.16093.0**<br/>

**Yenilikler**

- Bu sürüm [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) için bir güvenlik güncelleştirmesi içerir


<br/><br/>
</details><details>
<summary>Mart 2022 (Derleme: 101.60.05 | Sürüm: 30.122012.16005.0)</summary>

&ensp;Yayın tarihi: **3 Mart 2022**<br/>
&ensp;Yayımlanma Tarihi: **3 Mart 2022**<br/>
&ensp;Derleme: **101.60.05**<br/>
&ensp;Sürüm: **30.122012.16005.0**<br/>

**Yenilikler**

- RHEL 6.10 için çekirdek sürümü 2.6.32-754.43.1.el6.x86_64 desteği eklendi
- Hata düzeltmeleri


<br/><br/>
</details><details>
<summary>Şubat 2022 (Derleme: 101.58.80 | Sürüm: 30.122012.15880.0)</summary>

&ensp;Yayın tarihi: **20 Şubat 2022**<br/>
&ensp;Yayımlanma Tarihi: **20 Şubat 2022**<br/>
&ensp;Derleme: **101.58.80**<br/>
&ensp;Sürüm: **30.122012.15880.0**<br/>

**Yenilikler**

- Komut satırı aracı artık karantinaya alınan dosyaların dosyanın ilk algılandığı konumdan farklı bir konuma geri yüklenmesini destekliyor. Bu işlem aracılığıyla `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`yapılabilir.
- Bu sürümden başlayarak Linux için ağ koruması isteğe bağlı olarak değerlendirilebilir
- Hata düzeltmeleri



<br/><br/>
</details><details>
<summary>Ocak 2022 (Derleme: 101.56.62 | Sürüm: 30.121122.15662.0)</summary>

&ensp;Yayın tarihi: **26 Ocak 2022**<br/>
&ensp;Yayımlanma Tarihi: **26 Ocak 2022**<br/>
&ensp;Derleme: **101.56.62**<br/>
&ensp;Sürüm: **30.121122.15662.0**<br/>

**Yenilikler**

- 101.53.02'de ortaya çıkan ve birden çok müşteriyi etkileyen bir ürün kilitlenmesi düzeltildi


<br/><br/>
</details><details>
<summary>Ocak 2022 (Derleme: 101.53.02 | Sürüm: (30.121112.15302.0)</summary>

&ensp;Yayın tarihi: **8 Ocak 2022**<br/>
&ensp;Yayımlanma Tarihi: **8 Ocak 2022**<br/>
&ensp;Derleme: **101.53.02**<br/>
&ensp;Sürüm: **30.121112.15302.0**<br/>

**Yenilikler**

- Performans iyileştirmeleri & hata düzeltmeleri



</details>

<details><summary> 2021 sürümleri</summary><blockquote>
  <details><summary>(Derleme: 101.52.57 | Sürüm: 30.121092.15257.0)</summary>
   
  <p><b> Derleme: 101.52.57 <br>
Sürüm: 30.121092.15257.0</b></p>
   
  <p><b> Yenilikler </b></p>

   - Java uygulamaları tarafından kullanılan güvenlik açığı olan log4j jar'larını algılama özelliği eklendi. Makine, yüklenen log4j jar'ları ile Java işlemlerini çalıştırmak için düzenli aralıklarla incelenir. Bilgiler Uç Nokta için Microsoft Defender arka ucuna bildirilir ve portalın Güvenlik Açığı Yönetimi alanında kullanıma sunulur.
   
   </details>

  <details><summary>(Derleme: 101.47.76 | Sürüm: 30.121092.14776.0)</summary>
   
  <p><b> Derleme: 101.47.76 <br>
Sürüm: 30.121092.14776.0</b></p>
   
  <p><b>Yenilikler</b></p>

   - İsteğe bağlı taramalar sırasında arşivlerin taranıp taranmayacağını denetlemek için komut satırı aracına yeni bir anahtar eklendi. Bu, mdatp config scan-archives --value [enabled/disabled] aracılığıyla yapılandırılabilir. Varsayılan olarak, bu etkin olarak ayarlanır.

   - Hata düzeltmeleri

   </details>

   <details><summary>(Derleme: 101.45.13 | Sürüm: 30.121082.14513.0)</summary>
   
  <p> 
  Derleme: <b>101.45.13 </b>  <br>
Sürüm:<b> 30.121082.14513.0 </b></p>
   
  <p><b>Yenilikler</b></p>

  - Bu sürümden başlayarak, aşağıdaki dağıtımlara Uç Nokta için Microsoft Defender destek getiriyoruz:

    - RHEL6.7-6.10 ve CentOS6.7-6.10 sürümleri.
    - Amazon Linux 2
    - Fedora 33 veya üzeri

  - Hata düzeltmeleri

   </details>


   <details><summary>(Derleme: 101.45.00 | Sürüm: 30.121072.14500.0)</summary>
   
   <p> 
   Derleme:<b> 101.45.00</b> <br>
Sürüm: <b>30.121072.14500.0</b></p>
   
   <p><b>Yenilikler</b></p>
      

  - Komut satırı aracına yeni anahtarlar eklendi:
    - İsteğe bağlı taramalar için paralellik derecesini denetleme. Bu, aracılığıyla `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`yapılandırılabilir. Varsayılan olarak, bir paralellik `2` derecesi kullanılır.
    - Güvenlik bilgileri güncelleştirmelerinin etkinleştirilip etkinleştirilmediğini veya devre dışı bırakılıp bırakılmayacağını denetleyin. Bu, aracılığıyla `mdatp config scan-after-definition-update --value [enabled/disabled]`yapılandırılabilir. Bu, varsayılan olarak olarak `enabled`ayarlanır.
  - Ürün günlüğü düzeyini değiştirmek için artık yükseltme gerekiyor
  - Hata düzeltmeleri

   </details>

   <details><summary>(Derleme: 101.39.98 | Sürüm: 30.121062.13998.0)</summary>
   
   <p> 
   Derleme: <b>101.39.98 </b><br>
Sürüm: <b>30.121062.13998.0</b></p>
   
   <p><b>Yenilikler</b></p>

  - Performans iyileştirmeleri & hata düzeltmeleri
  
   </details>

   <details><summary>(Derleme: 101.34.27 | Sürüm: 30.121052.13427.0)</summary>
   
   <p> 
   Derleme:<b> 101.34.27</b> <br>
Sürüm: <b>30.121052.13427.0</b></p>
   
   <p><b>Yenilikler</b></p>

   - Performans iyileştirmeleri & hata düzeltmeleri
  
   </details>

   <details><summary>(Derleme: 101.29.64 | Sürüm: 30.121042.12964.0)</summary>
   
   <p> 
   Derleme:<b> 101.29.64 </b><br>
Sürüm:<b> 30.121042.12964.0</b></p>
   
   <p><b>Yenilikler</b></p>

   - Bu sürümden başlayarak, komut satırı istemcisi aracılığıyla tetiklenen isteğe bağlı virüsten koruma taramaları sırasında algılanan tehditler otomatik olarak düzeltilir. Kullanıcı arabirimi aracılığıyla tetiklenen taramalar sırasında algılanan tehditler yine de el ile eylem gerektirir.
   - `mdatp diagnostic real-time-protection-statistics` şimdi iki ek anahtarı destekler:
     - `--sort`: Taranan toplam dosya sayısına göre azalan çıktıyı sıralar
     - `--top N`: en iyi N sonuçlarını görüntüler (yalnızca belirtilirse `--sort` çalışır)
   - Performans iyileştirmeleri & hata düzeltmeleri
  
   </details>

   <details><summary>(Derleme: 101.25.72 | Sürüm: 30.121022.12563.0)</summary>
   
   <p> 
   Derleme:<b> 101.25.72</b> <br>
Sürüm: <b>30.121022.12563.0</b></p>
   
   <p><b>Yenilikler</b></p>

   - Linux'ta Uç Nokta için Microsoft Defender artık ABD Kamu müşterileri için önizleme aşamasında kullanıma sunulmuştur. Daha fazla bilgi için bkz. [US Government müşterileri için Uç Nokta için Microsoft Defender](gov.md).
   - FUSE dosya sistemlerine sahip sistemlerde Linux üzerinde Uç Nokta için Microsoft Defender kullanımının işletim sisteminin kilitlenmesine neden olduğu bir sorun düzeltildi
   - Performans iyileştirmeleri & diğer hata düzeltmeleri
  
   </details>

   
   <details><summary>(Derleme: 101.25.63 | Sürüm: 30.121022.12563.0)</summary>
   
   <p> 
   Derleme:<b> 101.25.63</b> <br>
Sürüm: <b>30.121022.12563.0</b></p>
   
   <p><b>Yenilikler</b></p>

   - Performans iyileştirmeleri & hata düzeltmeleri
  
   </details>

   <details><summary>(Derleme: 101.23.64 | Sürüm: 30.121021.12364.0)</summary>
   
   <p>
Derleme:<b> 101.23.64 </b><br>
Sürüm: 30.121021.12364.0</b></p>
   
   <p><b>Yenilikler</b></p>

   - Virüsten koruma dışlama listesine bağlama noktasının tamamının eklendiği durum için performans iyileştirmesi. Bu sürümden önce, bağlama noktasından kaynaklanan dosya etkinliği yine de ürün tarafından işlendi. Bu sürümden başlayarak, dışlanan bağlama noktaları için dosya etkinliği gizlenerek daha iyi ürün performansına yol açar
   - Son isteğe bağlı tarama hakkındaki bilgileri görüntülemek için komut satırı aracına yeni bir seçenek eklendi. Son isteğe bağlı tarama hakkındaki bilgileri görüntülemek için `mdatp health --details antivirus`
   - Hata düzeltmeleri & diğer performans iyileştirmeleri
  
   </details>

   <details><summary>(Derleme: 101.18.53)</summary>
   
    <p> 
    Derleme:<b> 101.18.53 </b><br>
        
    <p>Yenilikler</b></p>

   - Linux için EDR genel [kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
   - Özel taramalar sırasında AV dışlamalarını yoksaymak için yeni bir komut satırı anahtarı`--ignore-exclusions` () eklendi (`mdatp scan custom`)
   - Tanılama günlüklerinin farklı bir dizine kaydedilmesini sağlayan yeni bir parametre (`--path [directory]`) ile genişletilmiş `mdatp diagnostic create`
    - Performans iyileştirmeleri & hata düzeltmeleri
    
   </details>





</blockquote></details>

