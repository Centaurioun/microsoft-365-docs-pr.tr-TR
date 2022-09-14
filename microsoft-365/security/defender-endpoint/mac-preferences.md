---
title: Mac'te Uç Nokta için Microsoft Defender tercihlerini ayarlama
description: Kurumsal kuruluşlarda Mac'te Uç Nokta için Microsoft Defender yapılandırın.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, management, tercihler, enterprise, intune, jamf, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 64b6db32974a7755c46ff4cd87eea87512d8bfc5
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683307"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [macOS üzerinde Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> Bu makale, kurumsal kuruluşlarda macOS'ta Uç Nokta için Microsoft Defender için tercihleri ayarlama yönergelerini içerir. komut satırı arabirimini kullanarak macOS'ta Uç Nokta için Microsoft Defender yapılandırmak için bkz[. Kaynaklar](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Özet

Kurumsal kuruluşlarda, macOS üzerindeki Uç Nokta için Microsoft Defender çeşitli yönetim araçlarından biri kullanılarak dağıtılan bir yapılandırma profili aracılığıyla yönetilebilir. Güvenlik operasyonları ekibiniz tarafından yönetilen tercihler, cihazda yerel olarak ayarlanan tercihlerden önceliklidir. Yapılandırma profili aracılığıyla ayarlanan tercihlerin değiştirilmesi, yükseltilmiş ayrıcalıklar gerektirir ve yönetici izinleri olmayan kullanıcılar için kullanılamaz.

Bu makalede yapılandırma profilinin yapısı açıklanır, başlamak için kullanabileceğiniz önerilen bir profil bulunur ve profilin nasıl dağıtılacağına ilişkin yönergeler sağlanır.

## <a name="configuration-profile-structure"></a>Yapılandırma profili yapısı

Yapılandırma profili, bir anahtar tarafından tanımlanan girdilerden (tercihin adını belirtir) ve ardından tercihin yapısına bağlı olarak bir değerden oluşan bir *.plist* dosyasıdır. Değerler basit (sayısal değer gibi) veya iç içe yerleştirilmiş tercih listesi gibi karmaşık olabilir.

> [!CAUTION]
>Yapılandırma profilinin düzeni, kullandığınız yönetim konsoluna bağlıdır. Aşağıdaki bölümlerde JAMF ve Intune için yapılandırma profilleri örnekleri yer almaktadır.

Yapılandırma profilinin en üst düzeyi, ürün genelindeki tercihleri ve Uç Nokta için Microsoft Defender alt alanları için girişleri içerir ve bunlar sonraki bölümlerde daha ayrıntılı olarak açıklanmıştır.

### <a name="antivirus-engine-preferences"></a>Virüsten koruma altyapısı tercihleri

Yapılandırma profilinin *antivirusEngine* bölümü, Uç Nokta için Microsoft Defender virüsten koruma bileşeninin tercihlerini yönetmek için kullanılır.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|antivirusEngine|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

#### <a name="enforcement-level-for-antivirus-engine"></a>Virüsten koruma altyapısı için zorlama düzeyi

Virüsten koruma altyapısının zorlama tercihini belirtir. Zorlama düzeyini ayarlamak için üç değer vardır:

- Gerçek zamanlı (`real_time`): Gerçek zamanlı koruma (erişilen dosyaları tara) etkinleştirilir.
- İsteğe bağlı (`on_demand`): Dosyalar yalnızca isteğe bağlı olarak taranır. Burada:
  - Gerçek zamanlı koruma kapalıdır.
- Pasif (`passive`): Virüsten koruma altyapısını pasif modda çalıştırır. Burada:
  - Gerçek zamanlı koruma kapalıdır.
  - İsteğe bağlı tarama açıktır.
  - Otomatik tehdit düzeltme kapalı.
  - Güvenlik bilgileri güncelleştirmeleri açıktır.
  - Durum menüsü simgesi gizlenir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|enforcementLevel|
|**Veri türü**|Dize|
|**Olası değerler**|real_time (varsayılan) <p> on_demand <p> Pasif|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.10.72 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="configure-file-hash-computation-feature"></a>Dosya karması hesaplama özelliğini yapılandırma

Dosya karması hesaplama özelliğini etkinleştirir veya devre dışı bırakır. Bu özellik etkinleştirildiğinde, Uç Nokta için Defender taramış olduğu dosyalar için karmaları hesaplar. Bu özelliğin etkinleştirilmesi cihaz performansını etkileyebilir. Daha fazla ayrıntı için bkz. [Dosyalar için gösterge oluşturma](indicator-file.md).

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|enableFileHashComputation|
|**Veri türü**|Dize|
|**Olası değerler**|devre dışı (varsayılan) <p> Etkin|
|**Açıklamalar**|Uç Nokta için Defender sürüm 101.73.77 veya sonraki sürümlerde kullanılabilir.|

#### <a name="run-a-scan-after-definitions-are-updated"></a>Tanımlar güncelleştirildikten sonra tarama çalıştırma

Cihaza yeni güvenlik bilgileri güncelleştirmeleri indirildikten sonra işlem taraması başlatılıp başlatılmayacağını belirtir. Bu ayarın etkinleştirilmesi, cihazın çalışan işlemlerinde virüsten koruma taraması tetikler.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|scanAfterDefinitionUpdate|
|**Veri türü**|Boole|
|**Olası değerler**|true (varsayılan) <p> False|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.41.10 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>Arşivleri tara (yalnızca isteğe bağlı virüsten koruma taramaları)

İsteğe bağlı virüsten koruma taramaları sırasında arşivlerin taranıp taranmayacağını belirtir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|scanArchives|
|**Veri türü**|Boole|
|**Olası değerler**|true (varsayılan) <p> False|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.41.10 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>İsteğe bağlı taramalar için paralellik derecesi

İsteğe bağlı taramalar için paralellik derecesini belirtir. Bu, taramayı gerçekleştirmek için kullanılan iş parçacığı sayısına karşılık gelir ve CPU kullanımını ve isteğe bağlı tarama süresini etkiler.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|maximumOnDemandScanThreads|
|**Veri türü**|Tamsayı|
|**Olası değerler**|2 (varsayılan). İzin verilen değerler 1 ile 64 arasındaki tamsayılardır.|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.41.10 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="exclusion-merge-policy"></a>Dışlama birleştirme ilkesi

Dışlamalar için birleştirme ilkesini belirtin. Bu, yönetici tanımlı ve kullanıcı tanımlı dışlamaların (`merge`) veya yalnızca yönetici tanımlı dışlamaların (`admin_only`) birleşimi olabilir. Bu ayar, yerel kullanıcıların kendi dışlamalarını tanımlamasını kısıtlamak için kullanılabilir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|exclusionsMergePolicy|
|**Veri türü**|Dize|
|**Olası değerler**|merge (varsayılan) <p> admin_only|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 100.83.73 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="scan-exclusions"></a>Tarama dışlamaları

Taranmayan varlıkları belirtin. Dışlamalar tam yollar, uzantılar veya dosya adlarıyla belirtilebilir.
(Dışlamalar bir öğe dizisi olarak belirtilir, yönetici gerektiği kadar öğeyi herhangi bir sırada belirtebilir.)

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Dışlamalar|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

##### <a name="type-of-exclusion"></a>Dışlama türü

Türe göre taranmayan içeriği belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|$type|
|**Veri türü**|Dize|
|**Olası değerler**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|||

##### <a name="path-to-excluded-content"></a>Dışlanan içeriğin yolu

Tam dosya yolu tarafından taranmayan içeriği belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Yolu|
|**Veri türü**|Dize|
|**Olası değerler**|geçerli yollar|
|**Açıklamalar**|Yalnızca *$type* *excludedPath* olduğunda uygulanabilir|
|||

## <a name="supported-exclusion-types"></a>Desteklenen dışlama türleri

Aşağıdaki tabloda, Mac'te Uç Nokta için Defender tarafından desteklenen dışlama türleri gösterilmektedir.

<br>

****

|Dışlama|Tanım|Örnekler|
|---|---|---|
|Dosya uzantısı|Uzantılı tüm dosyalar, cihazın herhangi bir yerinde|`.test`|
|Dosya|Tam yol tarafından tanımlanan belirli bir dosya|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`|
|Klasör|Belirtilen klasör altındaki tüm dosyalar (özyinelemeli olarak)|`/var/log/` <p> `/var/*/`|
|Işlem|Belirli bir işlem (tam yol veya dosya adıyla belirtilir) ve tarafından açılan tüm dosyalar|`/bin/cat` <p> `cat` <p> `c?t`|
||||

> [!IMPORTANT]
> Yukarıdaki yolların başarıyla dışlanması için sembolik bağlantılar değil sabit bağlantılar olması gerekir. komutunu çalıştırarak `file <path-name>`yolun sembolik bir bağlantı olup olmadığını de kontrol edebilirsiniz.

Dosya, klasör ve işlem dışlamaları aşağıdaki joker karakterleri destekler:

<br>

****

|Joker|Açıklama|Örnek|Eşleşen|Eşleşmiyor|
|---|---|---|---|---|
|\*|Hiçbiri dahil olmak üzere herhangi bir sayıda karakterle eşleşir (bu joker karakter bir yolun içinde kullanıldığında yalnızca bir klasörü değiştireceğini unutmayın)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`|
|?|Herhangi bir tek karakterle eşleşir|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`|
||||||

### <a name="path-type-file--directory"></a>Yol türü (dosya / dizin)

*path* özelliğinin bir dosyaya veya dizine başvurup başvurmadığını belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|isDirectory|
|**Veri türü**|Boole|
|**Olası değerler**|false (varsayılan) <p> True|
|**Açıklamalar**|Yalnızca *$type* *excludedPath* olduğunda uygulanabilir|
|||

### <a name="file-extension-excluded-from-the-scan"></a>Dosya uzantısı taramanın dışında bırakıldı

Dosya uzantısı tarafından taranmayan içeriği belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Uzantısı|
|**Veri türü**|Dize|
|**Olası değerler**|geçerli dosya uzantıları|
|**Açıklamalar**|Yalnızca *$type* *excludedFileExtension* olduğunda geçerlidir|
|||

### <a name="process-excluded-from-the-scan"></a>Taramanın dışında tutulan işlem

Tüm dosya etkinliğinin taramanın dışında tutulacağını bir işlem belirtin. İşlem adıyla (örneğin, `cat`) veya tam yoluyla (örneğin, `/bin/cat`) belirtilebilir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Adı|
|**Veri türü**|Dize|
|**Olası değerler**|herhangi bir dize|
|**Açıklamalar**|Yalnızca *$type* *excludedFileName* olduğunda geçerlidir|
|||

#### <a name="allowed-threats"></a>İzin verilen tehditler

Tehditleri Mac'te Uç Nokta için Defender tarafından engellenmeyen ada göre belirtin. Bu tehditlerin çalışmasına izin verilir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|allowedThreats|
|**Veri türü**|Dize dizisi|
|||

#### <a name="disallowed-threat-actions"></a>İzin verilmeyen tehdit eylemleri

Bir cihazın yerel kullanıcısının tehdit algılandığında gerçekleştirebileceği eylemleri kısıtlar. Bu listede yer alan eylemler kullanıcı arabiriminde görüntülenmez.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|disallowedThreatActions|
|**Veri türü**|Dize dizisi|
|**Olası değerler**|allow (kullanıcıların tehditlere izin vermelerini kısıtlar) <p> geri yükleme (kullanıcıların karantinadan tehditleri geri yüklemesini kısıtlar)|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 100.83.73 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="threat-type-settings"></a>Tehdit türü ayarları

MacOS'ta belirli tehdit türlerinin Uç Nokta için Microsoft Defender tarafından nasıl işleneceğini belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|threatTypeSettings|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

##### <a name="threat-type"></a>Tehdit türü

Tehdit türlerini belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Anahtar|
|**Veri türü**|Dize|
|**Olası değerler**|potentially_unwanted_application <p> archive_bomb|
|||

##### <a name="action-to-take"></a>Gerçekleştirecek eylem

Önceki bölümde belirtilen türde bir tehdit algılandığında hangi eylemin gerçekleştirileceğini belirtin. Aşağıdaki seçeneklerden birini belirleyin:

- **Denetim**: Cihazınız bu tür tehditlere karşı korunmaz, ancak tehditle ilgili bir giriş günlüğe kaydedilir.
- **Engelle**: Cihazınız bu tür tehditlere karşı korunur ve kullanıcı arabiriminde ve güvenlik konsolunda size bildirilir.
- **Kapalı**: Cihazınız bu tür tehditlere karşı korunmaz ve hiçbir şey günlüğe kaydedilmez.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Değer|
|**Veri türü**|Dize|
|**Olası değerler**|denetim (varsayılan) <p> Blok <p> kapalı|
|||

#### <a name="threat-type-settings-merge-policy"></a>Tehdit türü ayarları birleştirme ilkesi

Tehdit türü ayarları için birleştirme ilkesini belirtin. Bu, yönetici tanımlı ve kullanıcı tanımlı ayarların () veya yalnızca yönetici tanımlı ayarların (`merge``admin_only`) birleşimi olabilir. Bu ayar, yerel kullanıcıların farklı tehdit türleri için kendi ayarlarını tanımlamasını kısıtlamak için kullanılabilir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|threatTypeSettingsMergePolicy|
|**Veri türü**|Dize|
|**Olası değerler**|merge (varsayılan) <p> admin_only|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 100.83.73 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Virüsten koruma tarama geçmişi saklama (gün olarak)

Sonuçların cihazdaki tarama geçmişinde tutulacağını gün sayısını belirtin. Eski tarama sonuçları geçmişten kaldırılır. Diskten de kaldırılan eski karantinaya alınan dosyalar.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|scanResultsRetentionDays|
|**Veri türü**|Dize|
|**Olası değerler**|90 (varsayılan). İzin verilen değerler 1 günden 180 güne kadardır.|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.07.23 veya üzeri sürümlerde kullanılabilir.|
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Virüsten koruma tarama geçmişindeki en fazla öğe sayısı

Tarama geçmişinde tutulacak en fazla girdi sayısını belirtin. Girişler, geçmişte gerçekleştirilen tüm isteğe bağlı taramaları ve tüm virüsten koruma algılamalarını içerir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|scanHistoryMaximumItems|
|**Veri türü**|Dize|
|**Olası değerler**|10000 (varsayılan). İzin verilen değerler 5000 öğeden 15000 öğeye kadardır.|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.07.23 veya üzeri sürümlerde kullanılabilir.|
|||

### <a name="cloud-delivered-protection-preferences"></a>Bulut tabanlı koruma tercihleri

macOS üzerinde Uç Nokta için Microsoft Defender bulut tabanlı koruma özelliklerini yapılandırın.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|cloudService|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Bulut tabanlı korumayı etkinleştirme/devre dışı bırakma

Cihazda bulut tabanlı korumanın etkinleştirilip etkinleştirilmeyeceğini belirtin. Hizmetlerinizin güvenliğini artırmak için bu özelliği açık tutmanızı öneririz.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Etkin|
|**Veri türü**|Boole|
|**Olası değerler**|true (varsayılan) <p> False|
|||

#### <a name="diagnostic-collection-level"></a>Tanılama toplama düzeyi

Tanılama verileri, Uç Nokta için Microsoft Defender güvenli ve güncel tutmak, sorunları algılamak, tanılamak ve düzeltmek ve ürün geliştirmeleri yapmak için kullanılır. Bu ayar, Uç Nokta için Microsoft Defender tarafından Microsoft'a gönderilen tanılama düzeyini belirler.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|diagnosticLevel|
|**Veri türü**|Dize|
|**Olası değerler**|isteğe bağlı (varsayılan) <p> Gerekli|
|||

#### <a name="configure-cloud-block-level"></a>Bulut bloğu düzeyini yapılandırma

Bu ayar, Uç Nokta için Defender'ın şüpheli dosyaları engelleme ve tarama konusunda ne kadar agresif olacağını belirler. Bu ayar açıksa, engellenecek ve taranacak şüpheli dosyaları tanımlarken Uç Nokta için Defender daha agresif olacaktır; aksi takdirde, daha az agresif olur ve bu nedenle daha az sıklıkta blok ve tarama olur. Bulut bloğu düzeyini ayarlamak için beş değer vardır:

- Normal (`normal`): Varsayılan engelleme düzeyi.
- Orta (`moderate`): Yalnızca yüksek güvenilirlik algılamaları için karar verir.
- Yüksek (`high`): Performansı iyileştirirken bilinmeyen dosyaları agresif bir şekilde engeller (zararlı olmayan dosyaları engelleme olasılığı daha yüksektir).
- High Plus (`high_plus`): Bilinmeyen dosyaları agresif bir şekilde engeller ve ek koruma önlemleri uygular (istemci cihaz performansını etkileyebilir).
- Sıfır Tolerans (`zero_tolerance`): Tüm bilinmeyen programları engeller.

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|cloudBlockLevel|
|**Veri türü**|Dize|
|**Olası değerler**|normal (varsayılan) <p> Orta <p> Yüksek <p> high_plus <p> zero_tolerance|
|**Açıklamalar**|Uç Nokta için Defender sürüm 101.56.62 veya sonraki sürümlerde kullanılabilir.|

#### <a name="enable--disable-automatic-sample-submissions"></a>Otomatik örnek gönderimlerini etkinleştirme/devre dışı bırakma

Şüpheli örneklerin (tehdit içerme olasılığı yüksek) Microsoft'a gönderilip gönderilmeyeceğini belirler. Gönderilen dosyanın kişisel bilgiler içerme olasılığı olup olmadığını sorarsınız.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|automaticSampleSubmission|
|**Veri türü**|Boole|
|**Olası değerler**|true (varsayılan) <p> False|
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Otomatik güvenlik bilgileri güncelleştirmelerini etkinleştirme/devre dışı bırakma

Güvenlik zekası güncelleştirmelerinin otomatik olarak yüklenip yüklenmediğini belirler:

<br>

****

|Bölüm|Değer|
|---|---|
|**Anahtar**|automaticDefinitionUpdateEnabled|
|**Veri türü**|Boole|
|**Olası değerler**|true (varsayılan) <p> False|
|||

### <a name="user-interface-preferences"></a>Kullanıcı arabirimi tercihleri

macOS'ta Uç Nokta için Microsoft Defender kullanıcı arabiriminin tercihlerini yönetin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|userInterface|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

#### <a name="show--hide-status-menu-icon"></a>Durum menüsü simgesini göster / gizle

Ekranın sağ üst köşesindeki durum menüsü simgesinin gösterilip gösterilmeyeceğini veya gizleneceğini belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|hideStatusMenuIcon|
|**Veri türü**|Boole|
|**Olası değerler**|false (varsayılan) <p> True|
|||

#### <a name="show--hide-option-to-send-feedback"></a>Geri bildirim göndermek için göster /gizle seçeneği

Kullanıcıların adresine giderek `Help` > `Send Feedback`Microsoft'a geri bildirim gönderip gönderemeyeceğini belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|userInitiatedFeedback|
|**Veri türü**|Dize|
|**Olası değerler**|etkin (varsayılan) <p> Devre dışı|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.19.61 veya üzeri sürümlerde kullanılabilir.|
|||



#### <a name="control-sign-in-to-consumer-version-of-microsoft-defender"></a>Microsoft Defender'ın tüketici sürümünde oturum açmayı denetleme

Kullanıcıların Microsoft Defender'ın tüketici sürümünde oturum açıp açamayacağını belirtin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|consumerExperience|
|**Veri türü**|Dize|
|**Olası değerler**|etkin (varsayılan) <p> Devre dışı|
|**Açıklamalar**|Uç Nokta için Microsoft Defender sürüm 101.60.18 veya üzeri sürümlerde kullanılabilir.|
|||


### <a name="endpoint-detection-and-response-preferences"></a>Uç nokta algılama ve yanıt tercihleri

macOS üzerinde Uç Nokta için Microsoft Defender uç nokta algılama ve yanıt (EDR) bileşeninin tercihlerini yönetin.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Edr|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

#### <a name="device-tags"></a>Cihaz etiketleri

Bir etiket adı ve değerini belirtin.

- GROUP etiketi, cihazı belirtilen değerle etiketler. Etiket portalda cihaz sayfasının altında yansıtılır ve cihazları filtrelemek ve gruplandırma için kullanılabilir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Etiketler|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|||

##### <a name="type-of-tag"></a>Etiket türü

Etiket türünü belirtir

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Anahtar|
|**Veri türü**|Dize|
|**Olası değerler**|`GROUP`|
|||

##### <a name="value-of-tag"></a>Etiketin değeri

Etiketin değerini belirtir

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Değer|
|**Veri türü**|Dize|
|**Olası değerler**|herhangi bir dize|
|||

> [!IMPORTANT]
>
> - Etiket türü başına yalnızca bir değer ayarlanabilir.
> - Etiketlerin türü benzersizdir ve aynı yapılandırma profilinde tekrarlanmamalıdır.

## <a name="recommended-configuration-profile"></a>Önerilen yapılandırma profili

Başlamak için, kuruluşunuzun Uç Nokta için Microsoft Defender sağladığı tüm koruma özelliklerinden yararlanması için aşağıdaki yapılandırmayı öneririz.

Aşağıdaki yapılandırma profili (veya JAMF durumunda, özel ayarlar yapılandırma profiline yüklenebilecek bir özellik listesi) şunları yapar:

- Gerçek zamanlı korumayı etkinleştirme (RTP)
- Aşağıdaki tehdit türlerinin nasıl işleneceğini belirtin:
  - **İstenmeyebilecek uygulamalar (PUA)** engellendi
  - **Arşiv bombaları** (yüksek sıkıştırma oranına sahip dosya) Uç Nokta için Microsoft Defender günlüklerde denetleniyor
- Otomatik güvenlik bilgileri güncelleştirmelerini etkinleştirme
- Bulut tabanlı korumayı etkinleştirme
- Otomatik örnek göndermeyi etkinleştirme

### <a name="property-list-for-jamf-recommended-configuration-profile"></a>JAMF önerilen yapılandırma profili için özellik listesi

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-recommended-profile"></a>Önerilen profili Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enforcementLevel</key>
                    <string>real_time</string>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Tam yapılandırma profili örneği

Aşağıdaki şablonlar, bu belgede açıklanan tüm ayarların girdilerini içerir ve macOS'ta Uç Nokta için Microsoft Defender üzerinde daha fazla denetime ihtiyacınız olan daha gelişmiş senaryolar için kullanılabilir.

### <a name="property-list-for-jamf-full-configuration-profile"></a>JAMF tam yapılandırma profili için özellik listesi

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
        <key>scanAfterDefinitionUpdate</key>
        <true/>
        <key>scanArchives</key>
        <true/>
        <key>maximumOnDemandScanThreads</key>
        <integer>2</integer>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-full-profile"></a>Tam profil Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enforcementLevel</key>
                    <string>real_time</string>
                    <key>scanAfterDefinitionUpdate</key>
                    <true/>
                    <key>scanArchives</key>
                    <true/>
                    <key>maximumOnDemandScanThreads</key>
                    <integer>1</integer>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="property-list-validation"></a>Özellik listesi doğrulama

Özellik listesi geçerli bir *.plist* dosyası olmalıdır. Bu, yürütülerek denetlenebilir:

```bash
plutil -lint com.microsoft.wdav.plist
```

```Output
com.microsoft.wdav.plist: OK
```

Dosya iyi biçimlendirilmişse, yukarıdaki komut çıkışını alır `OK` ve çıkış kodunu `0`döndürür. Aksi takdirde, sorunu açıklayan bir hata görüntülenir ve komutu çıkış `1`kodunu döndürür.

## <a name="configuration-profile-deployment"></a>Yapılandırma profili dağıtımı

Kuruluşunuz için yapılandırma profilini derledikten sonra, kuruluşunuzun kullandığı yönetim konsolu aracılığıyla dağıtabilirsiniz. Aşağıdaki bölümlerde JAMF ve Intune kullanarak bu profilin nasıl dağıtılacağına ilişkin yönergeler sağlanmaktadır.

### <a name="jamf-deployment"></a>JAMF dağıtımı

JAMF konsolundan **Bilgisayar** \> **Yapılandırma Profilleri'ni** açın, kullanmak istediğiniz yapılandırma profiline gidin ve **Özel Ayarlar'ı** seçin. tercih etki alanı olarak ile `com.microsoft.wdav` bir giriş oluşturun ve daha önce üretilen *.plist* dosyasını karşıya yükleyin.

> [!CAUTION]
> Doğru tercih etki alanını (`com.microsoft.wdav`) girmeniz gerekir; aksi takdirde, tercihler Uç Nokta için Microsoft Defender tarafından tanınmaz.

### <a name="intune-deployment"></a>Intune dağıtımı

1. **Cihaz yapılandırmasını yönet'i** \> açın. Profilleri **Yönet** \> **Profil Oluştur'u** \> seçin.

2. Profil için bir ad seçin. **Platform=macOS** **değerini Profil türü=Özel** olarak değiştirin. Yapılandır'ı seçin.

3. Daha önce üretilen .plist dosyasını olarak `com.microsoft.wdav.xml`kaydedin.

4. **Özel yapılandırma profili adı** olarak girin`com.microsoft.wdav`.

5. Yapılandırma profilini açın ve dosyayı karşıya yükleyin `com.microsoft.wdav.xml` . (Bu dosya 3. adımda oluşturulmuştur.)

6. **Tamam**'ı seçin.

7. **Atamaları** **Yönet'i** \> seçin. **Ekle** sekmesinde **Tüm Kullanıcılara Ata & Tüm cihazlar'ı** seçin.

> [!CAUTION]
> Doğru özel yapılandırma profili adını girmeniz gerekir; aksi takdirde, bu tercihler Uç Nokta için Microsoft Defender tarafından tanınmaz.

## <a name="resources"></a>Kaynaklar

- [Yapılandırma Profili Başvurusu (Apple geliştirici belgeleri)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
