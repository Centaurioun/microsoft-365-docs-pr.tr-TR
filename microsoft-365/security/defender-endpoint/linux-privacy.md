---
title: Linux'ta Uç Nokta için Microsoft Defender için gizlilik
description: Gizlilik denetimleri, Linux'ta Uç Nokta için Microsoft Defender toplanan tanılama verileri hakkındaki bilgileri ve gizliliği etkileyen ilke ayarlarını yapılandırma.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, gizlilik, tanılama
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 810ad7177a46435554746eca1bded13c2c8549ed
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227294"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender için gizlilik

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft, Linux'ta Uç Nokta için Defender'ı kullanırken verilerinizin nasıl toplandığı ve kullanıldığı hakkında seçim yapmak için ihtiyacınız olan bilgileri ve denetimleri sağlamayı taahhüt eder.

Bu makalede ürün içinde kullanılabilen gizlilik denetimleri, ilke ayarlarıyla bu denetimlerin nasıl yönetileceğini ve toplanan veri olayları hakkında daha fazla ayrıntı açıklanmaktadır.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender gizlilik denetimlerine genel bakış

Bu bölümde, Linux üzerinde Uç Nokta için Defender tarafından toplanan farklı veri türleri için gizlilik denetimleri açıklanmaktadır.

### <a name="diagnostic-data"></a>Tanılama verileri

Tanılama verileri Uç Nokta için Defender'ı güvenli ve güncel tutmak, sorunları algılamak, tanılamak ve düzeltmek ve ürün geliştirmeleri yapmak için kullanılır.

Bazı tanılama verileri isteğe bağlıyken bazı tanılama verileri gereklidir. Kuruluşlar için ilke ayarları gibi gizlilik denetimlerini kullanarak gerekli veya isteğe bağlı tanılama verilerinin bize gönderilip gönderilmeyeceğini seçmenizi sağlarız.

Uç Nokta için Defender istemci yazılımı için aralarından seçim yapabileceğiniz iki tanılama verisi düzeyi vardır:

- **Gerekli**: Uç Nokta için Defender'ın güvenli, güncel ve yüklü olduğu cihazda beklendiği gibi performans göstermesini sağlamak için gereken minimum veriler.
- **İsteğe bağlı**: Microsoft'un ürün geliştirmeleri yapmasına yardımcı olan ve sorunları algılamaya, tanılamaya ve düzeltmeye yardımcı olacak gelişmiş bilgiler sağlayan diğer veriler.

Varsayılan olarak, Yalnızca gerekli tanılama verileri Microsoft'a gönderilir.

### <a name="cloud-delivered-protection-data"></a>Bulut tarafından sunulan koruma verileri

Bulut tarafından sunulan koruma, buluttaki en son koruma verilerine erişim ile daha yüksek ve daha hızlı koruma sağlamak için kullanılır.

Bulut tabanlı koruma hizmetinin etkinleştirilmesi isteğe bağlıdır, ancak uç noktalarınızda ve ağınızda kötü amaçlı yazılımlara karşı önemli koruma sağladığından kesinlikle önerilir.

### <a name="sample-data"></a>Örnek veriler

Örnek veriler, analiz edilebilmeleri için Microsoft şüpheli örnekleri göndererek ürünün koruma özelliklerini geliştirmek için kullanılır. Otomatik örnek gönderimini etkinleştirmek isteğe bağlıdır.

Örnek gönderimini denetlemek için üç düzey vardır:

- **Hiçbiri**: Microsoft'a şüpheli örnek gönderilmez.
- **Güvenli**: Yalnızca kişisel bilgiler (PII) içermeyen şüpheli örnekler otomatik olarak gönderilir. Bu, varsayılan değerdir.
- **Tümü**: Tüm şüpheli örnekler Microsoft'a gönderilir.

## <a name="manage-privacy-controls-with-policy-settings"></a>Gizlilik denetimlerini ilke ayarlarıyla yönetme

BT yöneticisiyseniz bu denetimleri kurumsal düzeyde yapılandırmak isteyebilirsiniz.

Önceki bölümde açıklanan çeşitli veri türlerine yönelik gizlilik denetimleri [, Linux'ta Uç Nokta için Defender tercihlerini ayarlama](linux-preferences.md) bölümünde ayrıntılı olarak açıklanmıştır.

Tüm yeni ilke ayarlarında olduğu gibi, ilke ayarlarını kuruluşunuzda daha geniş bir şekilde uygulamadan önce yapılandırdığınız ayarların istenen etkiye sahip olduğundan emin olmak için bunları sınırlı, denetimli bir ortamda dikkatlice test etmelisiniz.

## <a name="diagnostic-data-events"></a>Tanılama veri olayları

Bu bölümde, gerekli tanılama verileri olarak kabul edilenler ve isteğe bağlı tanılama verileri olarak kabul edilenler ve toplanan olayların ve alanların açıklaması açıklanmaktadır.

### <a name="data-fields-that-are-common-for-all-events"></a>Tüm olaylar için ortak olan veri alanları

Kategorisi veya alt veri türü ne olursa olsun tüm olaylarda ortak olan olaylar hakkında bazı bilgiler bulunur.

Aşağıdaki alanlar tüm olaylar için ortak kabul edilir:

|Alan|Açıklama|
|---|---|
|Platform|Uygulamanın üzerinde çalıştığı platformun geniş sınıflandırması. Microsoft'un doğru önceliklendirilebilmesi için bir sorunun hangi platformlarda oluşabileceğini belirlemesine olanak tanır.|
|machine_guid|Cihazla ilişkili benzersiz tanımlayıcı. Microsoft'un sorunların belirli bir yükleme kümesini etkileyip etkilemediğini ve kaç kullanıcının etkilendiğini belirlemesine olanak tanır.|
|sense_guid|Cihazla ilişkili benzersiz tanımlayıcı. Microsoft'un sorunların belirli bir yükleme kümesini etkileyip etkilemediğini ve kaç kullanıcının etkilendiğini belirlemesine olanak tanır.|
|org_id|Cihazın ait olduğu kuruluşla ilişkilendirilmiş benzersiz tanımlayıcı. Microsoft'un sorunların belirli bir kuruluş kümesini etkileyip etkilemediğini ve kaç kuruluşun etkilendiğini belirlemesine olanak tanır.|
|Hostname|Yerel cihaz adı (DNS soneki olmadan). Microsoft'un sorunların belirli bir yükleme kümesini etkileyip etkilemediğini ve kaç kullanıcının etkilendiğini belirlemesine olanak tanır.|
|product_guid|Ürünün benzersiz tanımlayıcısı. Microsoft'un ürünün farklı çeşitlerini etkileyen sorunları ayırt etmesine olanak tanır.|
|app_version|Linux uygulamasında Uç Nokta için Defender sürümü. Microsoft'un doğru önceliklendirilebilmesi için ürünün hangi sürümlerinin sorun gösterdiğini belirlemesine olanak tanır.|
|sig_version|Güvenlik zekası veritabanının sürümü. Microsoft'un doğru önceliklendirilebilmesi için güvenlik zekasının hangi sürümlerinin sorun gösterdiğini belirlemesine olanak tanır.|
|supported_compressions|Uygulama tarafından desteklenen sıkıştırma algoritmalarının listesi, örneğin `['gzip']`. Microsoft'un uygulamayla iletişim kurarken hangi tür sıkıştırmaların kullanılabileceğini anlamasını sağlar.|
|release_ring|Cihazın ilişkili olduğu halka (örneğin Insider Hızlı, Insider Yavaş, Üretim). Microsoft'un doğru önceliklendirilebilmesi için bir sorunun hangi yayın kademesinde oluşabileceğini belirlemesine olanak tanır.|

### <a name="required-diagnostic-data"></a>Gerekli tanılama verileri

**Gerekli tanılama verileri** , Uç Nokta için Defender'ın güvenli, güncel ve yüklü olduğu cihazda beklendiği gibi performans göstermesini sağlamaya yardımcı olmak için gereken en düşük verilerdir.

Gerekli tanılama verileri, bir cihaz veya yazılım yapılandırmasıyla ilgili olabilecek Uç Nokta için Microsoft Defender sorunlarını belirlemeye yardımcı olur. Örneğin, bir Uç Nokta için Defender özelliğinin belirli bir işletim sistemi sürümünde, yeni eklenen özelliklerle veya belirli Uç Nokta için Defender özelliklerinin devre dışı bırakıldığında daha sık kilitlenip kilitlenmediğini belirlemeye yardımcı olabilir. Gerekli tanılama verileri, Microsoft'un bu sorunları daha hızlı algılamasına, tanılamasına ve düzeltmesine yardımcı olur, böylece kullanıcılar veya kuruluşlar üzerindeki etkisi azalır.

#### <a name="software-setup-and-inventory-data-events"></a>Yazılım kurulumu ve envanter veri olayları

**yükleme /kaldırma Uç Nokta için Microsoft Defender**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|correlation_id|Yüklemeyle ilişkili benzersiz tanımlayıcı.|
|Sürüm|Paketin sürümü.|
|Önem|İletinin önem derecesi (örneğin, Bilgilendirici).|
|Kod|İşlemi açıklayan kod.|
|Metin|Ürün yüklemesiyle ilişkili ek bilgiler.|

**Uç Nokta için Microsoft Defender yapılandırması**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|antivirus_engine.enable_real_time_protection|Cihazda gerçek zamanlı korumanın etkinleştirilip etkinleştirilmediği.|
|antivirus_engine.passive_mode|Cihazda pasif modun etkinleştirilip etkinleştirilmediği.|
|cloud_service.enabled|Bulutta sunulan korumanın cihazda etkinleştirilip etkinleştirilmediği.|
|cloud_service.timeout|Uygulama Uç Nokta için Defender bulutuyla iletişim kurarken zaman aşımına uğradı.|
|cloud_service.heartbeat_interval|Ürün tarafından buluta gönderilen ardışık sinyaller arasındaki aralık.|
|cloud_service.service_uri|Bulutla iletişim kurmak için kullanılan URI.|
|cloud_service.diagnostic_level|Cihazın tanılama düzeyi (gerekli, isteğe bağlı).|
|cloud_service.automatic_sample_submission|Cihazın otomatik örnek gönderim düzeyi (hiçbiri, güvenli, tümü).|
|cloud_service.automatic_definition_update_enabled|Otomatik tanım güncelleştirmesinin açık olup olmadığı.|
|edr.early_preview|Cihazın EDR erken önizleme özelliklerini çalıştırıp çalıştırmayacağı.|
|edr.group_id|Algılama ve yanıt bileşeni tarafından kullanılan grup tanımlayıcısı.|
|edr.tags|Kullanıcı tanımlı etiketler.|
|Özellik.\[ isteğe bağlı özellik adı\]|Önizleme özelliklerinin listesi ve bunların etkinleştirilip etkinleştirilmediği.|

#### <a name="product-and-service-usage-data-events"></a>Ürün ve hizmet kullanımı verisi olayları

**Güvenlik bilgileri güncelleştirme raporu**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|from_version|Özgün güvenlik bilgileri sürümü.|
|to_version|Yeni güvenlik bilgileri sürümü.|
|Durum|Başarılı veya başarısız olduğunu belirten güncelleştirmenin durumu.|
|using_proxy|Güncelleştirmenin bir ara sunucu üzerinden yapılıp yapılmadığı.|
|Hata|Güncelleştirme başarısız olursa hata kodu.|
|Neden|Güncelleştirme başarısız olursa hata iletisi.|

#### <a name="product-and-service-performance-data-events-for-required-diagnostic-data"></a>Gerekli tanılama verileri için ürün ve hizmet performansı veri olayları

**Çekirdek uzantısı istatistikleri**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|Sürüm|Linux'ta Uç Nokta için Defender sürümü.|
|instance_id|Çekirdek uzantısı başlangıcında oluşturulan benzersiz tanımlayıcı.|
|trace_level|Çekirdek uzantısının izleme düzeyi.|
|Alt|Gerçek zamanlı koruma için kullanılan temel alt sistem.|
|ipc.connects|Çekirdek uzantısı tarafından alınan bağlantı isteklerinin sayısı.|
|ipc.rejects|Çekirdek uzantısı tarafından reddedilen bağlantı isteklerinin sayısı.|
|ipc.connected|Çekirdek uzantısına etkin bir bağlantı olup olmadığı.|

#### <a name="support-data"></a>Destek verileri

**Tanılama günlükleri**:

Tanılama günlükleri yalnızca geri bildirim gönderme özelliğinin bir parçası olarak kullanıcının onayıyla toplanır. Aşağıdaki dosyalar destek günlüklerinin bir parçası olarak toplanır:

- */var/log/microsoft/mdatp* altındaki tüm dosyalar
- Linux üzerinde Uç Nokta için Defender tarafından oluşturulan ve kullanılan */etc/opt/microsoft/mdatp* altındaki dosyaların alt kümesi
- /var/log/microsoft/mdatp/*.log altında ürün yükleme ve kaldırma günlükleri

### <a name="optional-diagnostic-data"></a>İsteğe bağlı tanılama verileri

**İsteğe bağlı tanılama verileri** , Microsoft'un ürün geliştirmeleri yapmasına yardımcı olan ek verilerdir ve sorunları algılamaya, tanılamaya ve düzeltmeye yardımcı olmak için gelişmiş bilgiler sağlar.

Bize isteğe bağlı tanılama verilerini göndermeyi seçerseniz, bu durum gerekli tanılama verilerini de içerir.

İsteğe bağlı tanılama verilerine örnek olarak Microsoft'un ürün yapılandırması (örneğin cihazda ayarlanan dışlama sayısı) ve ürün performansı (ürünün bileşenlerinin performansı hakkında toplu ölçüler) hakkında topladığı veriler verilebilir.

#### <a name="software-setup-and-inventory-data-events-for-optional-diagnostic-data"></a>İsteğe bağlı tanılama verileri için yazılım kurulumu ve envanter verileri olayları

**Uç Nokta için Microsoft Defender yapılandırması**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|connection_retry_timeout|Bulutla iletişim kurarken bağlantı yeniden deneme zaman aşımına uğradı.|
|file_hash_cache_maximum|Ürün önbelleğinin boyutu.|
|crash_upload_daily_limit|Günlük olarak karşıya yüklenen kilitlenme günlüklerinin sınırı.|
|antivirus_engine.exclusions[].is_directory|Taramanın dışlanmasının bir dizin olup olmadığı.|
|antivirus_engine.exclusions[].path|Taramanın dışında bırakılan yol.|
|antivirus_engine.exclusions[].extension|Uzantı taramanın dışında bırakıldı.|
|antivirus_engine.exclusions[].name|Taramadan dışlanan dosyanın adı.|
|antivirus_engine.scan_cache_maximum|Ürün önbelleğinin boyutu.|
|antivirus_engine.maximum_scan_threads|Tarama için kullanılan iş parçacığı sayısı üst sınırı.|
|antivirus_engine.threat_restoration_exclusion_time|Karantinadan geri yüklenen bir dosyanın yeniden algılanması için önce zaman aşımı.|
|antivirus_engine.threat_type_settings|Farklı tehdit türlerinin ürün tarafından nasıl işlenme şekline yönelik yapılandırma.|
|filesystem_scanner.full_scan_directory|Tam tarama dizini.|
|filesystem_scanner.quick_scan_directories|Hızlı taramada kullanılan dizinlerin listesi.|
|edr.latency_mode|Algılama ve yanıt bileşeni tarafından kullanılan gecikme modu.|
|edr.proxy_address|Algılama ve yanıt bileşeni tarafından kullanılan proxy adresi.|

**Microsoft Otomatik Güncelleştirme yapılandırması**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|how_to_check|Ürün güncelleştirmelerinin nasıl denetleneceğini belirler (örneğin, otomatik veya el ile).|
|channel_name|Cihazla ilişkili kanalı güncelleştirin.|
|manifest_server|Güncelleştirmeleri indirmek için kullanılan sunucu.|
|update_cache|Güncelleştirmeleri depolamak için kullanılan önbelleğin konumu.|

### <a name="product-and-service-usage"></a>Ürün ve hizmet kullanımı

#### <a name="diagnostic-log-upload-started-report"></a>Tanılama günlüğü karşıya yükleme başlatıldı raporu

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|sha256|Destek günlüğünün SHA256 tanımlayıcısı.|
|Boyutu|Destek günlüğünün boyutu.|
|original_path|Destek günlüğünün yolu (her zaman */var/opt/microsoft/mdatp/wdavdiag/* altında).|
|Biçim|Destek günlüğünün biçimi.|

#### <a name="diagnostic-log-upload-completed-report"></a>Tanılama günlüğü karşıya yükleme tamamlandı raporu

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|request_id|Destek günlüğü karşıya yükleme isteği için bağıntı kimliği.|
|sha256|Destek günlüğünün SHA256 tanımlayıcısı.|
|blob_sas_uri|Uygulama tarafından destek günlüğünü karşıya yüklemek için kullanılan URI.|

#### <a name="product-and-service-performance-data-events-for-product-service-and-usage"></a>Ürün hizmeti ve kullanımı için ürün ve hizmet performansı veri olayları

**Beklenmeyen uygulama çıkışı (kilitlenme)**:

Uygulamadan beklenmeyen çıkışlar ve bu olduğunda uygulamanın durumu.

**Çekirdek uzantısı istatistikleri**:

Aşağıdaki alanlar toplanır:

|Alan|Açıklama|
|---|---|
|pkt_ack_timeout|Aşağıdaki özellikler, çekirdek uzantısının başlatılmasından bu yana gerçekleşen olayların sayısını temsil eden, toplanan sayısal değerlerdir.|
|pkt_ack_conn_timeout||
|ipc.ack_pkts||
|ipc.nack_pkts||
|ipc.send.ack_no_conn||
|ipc.send.nack_no_conn||
|ipc.send.ack_no_qsq||
|ipc.send.nack_no_qsq||
|ipc.ack.no_space||
|ipc.ack.timeout||
|ipc.ack.ackd_fast||
|ipc.ack.ackd||
|ipc.recv.bad_pkt_len||
|ipc.recv.bad_reply_len||
|ipc.recv.no_waiter||
|ipc.recv.copy_failed||
|ipc.kauth.vnode.mask||
|ipc.kauth.vnode.read||
|ipc.kauth.vnode.write||
|ipc.kauth.vnode.exec||
|ipc.kauth.vnode.del||
|ipc.kauth.vnode.read_attr||
|ipc.kauth.vnode.write_attr||
|ipc.kauth.vnode.read_ex_attr||
|ipc.kauth.vnode.write_ex_attr||
|ipc.kauth.vnode.read_sec||
|ipc.kauth.vnode.write_sec||
|ipc.kauth.vnode.take_own||
|ipc.kauth.vnode.link||
|ipc.kauth.vnode.create||
|ipc.kauth.vnode.move||
|ipc.kauth.vnode.mount||
|ipc.kauth.vnode.denied||
|ipc.kauth.vnode.ackd_before_deadline||
|ipc.kauth.vnode.missed_deadline||
|ipc.kauth.file_op.mask||
|ipc.kauth_file_op.open||
|ipc.kauth.file_op.close||
|ipc.kauth.file_op.close_modified||
|ipc.kauth.file_op.move||
|ipc.kauth.file_op.link||
|ipc.kauth.file_op.exec||
|ipc.kauth.file_op.remove||
|ipc.kauth.file_op.unmount||
|ipc.kauth.file_op.fork||
|ipc.kauth.file_op.create||

## <a name="resources"></a>Kaynaklar

- [Microsoft'ta Gizlilik](https://privacy.microsoft.com/)
