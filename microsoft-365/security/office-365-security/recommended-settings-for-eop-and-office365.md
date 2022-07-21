---
title: EOP ve Office 365 için Defender güvenlik ayarları için Microsoft önerileri
keywords: Office 365 güvenlik önerileri, Gönderen İlkesi Çerçevesi, Etki Alanı Tabanlı İleti Raporlama ve Uyumluluk, DomainKeys Tanımlı Posta, adımlar, nasıl çalıştığı, güvenlik temelleri, EOP temelleri, Office 365 için Defender için temeller, Office 365 için Defender ayarlama, EOP'yi ayarlama, yapılandırma Office 365 için Defender, EOP'yi yapılandırma, güvenlik yapılandırması
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Exchange Online Protection (EOP) ve Office 365 için Defender güvenlik ayarları için en iyi yöntemler nelerdir? Standart koruma için geçerli öneriler neleri içerir? Daha katı olmak istiyorsanız ne kullanılmalıdır? Ayrıca Office 365 için Defender kullanıyorsanız ne kadar ekstra alırsınız?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4653ac9212ef20d7baecdbfa11885e25b514a067
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943877"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP),** Microsoft 365 abonelikleri için güvenliğin temelidir ve kötü amaçlı e-postaların çalışanlarınızın gelen kutularına ulaşmasını engeller. Ancak her gün ortaya çıkan yeni ve daha gelişmiş saldırılarla, genellikle iyileştirilmiş korumalar gerekir. **Office 365 için Microsoft Defender** Plan 1 veya Plan 2, yöneticilere daha fazla güvenlik, denetim ve araştırma katmanı sağlayan ek özellikler içerir.

Güvenlik yöneticilerine güvenlik ayarlarını özelleştirme yetkisi verilmektedir ancak EOP ve Office 365 için Microsoft Defender iki güvenlik düzeyi vardır: **Standart** ve **Katı**. Müşteri ortamları ve ihtiyaçları farklı olsa da, bu filtreleme düzeyleri çoğu durumda istenmeyen postaların çalışanlarınızın Gelen Kutusuna ulaşmasını önlemeye yardımcı olur.

Standart veya Katı ayarları kullanıcılara otomatik olarak uygulamak için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).

Bu makalede varsayılan ayarlar ve kullanıcılarınızın korunmasına yardımcı olmak için önerilen Standart ve Katı ayarlar açıklanmaktadır. Tablolar, Microsoft 365 Defender portalındaki ve PowerShell'deki ayarları içerir (Exchange Online posta kutusu olmayan kuruluşlar için PowerShell veya tek başına Exchange Online Protection PowerShell Exchange Online).

> [!NOTE]
> PowerShell için Office 365 Gelişmiş Tehdit Koruması Önerilen Yapılandırma Çözümleyicisi (ORCA) modülü, (yöneticiler) bu ayarların geçerli değerlerini bulmanıza yardımcı olabilir. Özellikle **, Get-ORCAReport** cmdlet'i istenmeyen posta önleme, kimlik avı önleme ve diğer ileti hijyen ayarlarının bir değerlendirmesini oluşturur. ORCA modülünü adresinden <https://www.powershellgallery.com/packages/ORCA/>indirebilirsiniz.
>
> Microsoft 365 kuruluşlarında Gereksiz Email Filtresi'ni EOP'den gelen istenmeyen posta filtreleme kararlarıyla gereksiz çakışmaları (hem pozitif hem de negatif) önlemek için Outlook'ta **Otomatik filtreleme yok** olarak bırakmanızı öneririz. Daha fazla bilgi için aşağıdaki makalelere bakın:
>
> - [Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma](configure-junk-email-settings-on-exo-mailboxes.md)
> - [Outlook'ta gereksiz e-posta ayarları hakkında](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook)
> - [Gereksiz Email Filtresi'nde koruma düzeyini değiştirme](https://support.microsoft.com/en-us/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)
> - [EOP'de güvenilir gönderen listeleri oluşturma](create-safe-sender-lists-in-office-365.md)
> - [EOP'de engellenen gönderen listeleri oluşturma](create-block-sender-lists-in-office-365.md)

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP'de istenmeyen posta önleme, kötü amaçlı yazılımdan koruma ve kimlik avı koruması

İstenmeyen posta, kötü amaçlı yazılımdan koruma ve kimlik avı önleme, yöneticiler tarafından yapılandırılabilir EOP özellikleridir. Aşağıdaki Standart veya Katı yapılandırmaları öneririz.

### <a name="eop-anti-spam-policy-settings"></a>EOP istenmeyen posta önleme ilkesi ayarları

İstenmeyen posta önleme ilkeleri oluşturmak ve yapılandırmak için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

|Güvenlik özelliği adı|Varsayılan|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**İstenmeyen posta özellikleri & toplu e-posta eşiği**|||||
|**Toplu e-posta eşiği** <br><br> _BulkThreshold_|7|6|4|Ayrıntılar için bkz. [EOP'de toplu şikayet düzeyi (BCL).](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Bu ayar yalnızca PowerShell'de kullanılabilir.|
|**İstenmeyen posta puanı ayarlarını artırma**|Devre Dışı|Devre Dışı|Devre Dışı|Bu ayarların tümü Gelişmiş İstenmeyen Posta Filtresi'nin (ASF) bir parçasıdır. Daha fazla bilgi için bu makalenin [istenmeyen posta önleme ilkelerindeki ASF ayarları](#asf-settings-in-anti-spam-policies) bölümüne bakın.|
|**İstenmeyen posta ayarları olarak işaretle**|Devre Dışı|Devre Dışı|Devre Dışı|Bu ayarların çoğu ASF'nin bir parçasıdır. Daha fazla bilgi için bu makalenin [istenmeyen posta önleme ilkelerindeki ASF ayarları](#asf-settings-in-anti-spam-policies) bölümüne bakın.|
|**Belirli dilleri içerir** <br><br> _EnableLanguageBlockList_ <br><br> _LanguageBlockList_|**Devre Dışı** <br><br> `$false` <br><br> Boş|**Devre Dışı** <br><br> `$false` <br><br> Boş|**Devre Dışı** <br><br> `$false` <br><br> Boş|Bu ayar için belirli bir önerimiz yok. İş gereksinimlerinize göre belirli dillerde iletileri engelleyebilirsiniz.|
|**Bu ülkelerden** <br><br> _EnableRegionBlockList_ <br><br> _RegionBlockList_|**Devre Dışı** <br><br> `$false` <br><br> Boş|**Devre Dışı** <br><br> `$false` <br><br> Boş|**Devre Dışı** <br><br> `$false` <br><br> Boş|Bu ayar için belirli bir önerimiz yok. İş gereksinimlerinize göre belirli ülkelerden gelen iletileri engelleyebilirsiniz.|
|**Test modu** (_TestModeAction_)|**Yok**|**Yok**|**Yok**|Bu ayar ASF'nin bir parçasıdır. Daha fazla bilgi için bu makalenin [istenmeyen posta önleme ilkelerindeki ASF ayarları](#asf-settings-in-anti-spam-policies) bölümüne bakın.|
|**Eylem**||||**Karantina iletisini** seçtiğiniz her yerde **Karantina ilkesi** seçin kutusu kullanılabilir. Karantina ilkeleri, kullanıcıların karantinaya alınan iletilere ne yapmalarına izin verılacağını tanımlar. <br><br> Standart ve Katı önceden ayarlanmış güvenlik ilkeleri [, buradaki](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) tabloda açıklandığı gibi varsayılan karantina ilkelerini (AdminOnlyAccessPolicy veya DefaultFullAccessPolicy karantina bildirimleri olmadan) kullanır. <br><br> Yeni bir istenmeyen posta önleme ilkesi oluşturduğunuzda, boş bir değer varsayılan karantina ilkesinin söz konusu karar tarafından karantinaya alınan iletilerin geçmiş özelliklerini tanımlamak için kullanıldığı anlamına gelir ( **Yüksek güvenilirlikli kimlik avı** için karantina bildirimleri olmadan AdminOnlyAccessPolicy; Diğer her şey için karantina bildirimi olmayan DefaultFullAccessPolicy). <br><br> Yöneticiler, varsayılan veya özel istenmeyen posta önleme ilkelerinde kullanıcılar için daha kısıtlayıcı veya daha az kısıtlayıcı özellikler tanımlayan özel karantina ilkeleri oluşturabilir ve seçebilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).|
|**İstenmeyen posta** algılama eylemi <br><br> _İstenmeyen Posta_|**İletiyi Gereksiz Email klasörüne taşıma** <br><br> `MoveToJmf`|**İletiyi Gereksiz Email klasörüne taşıma** <br><br> `MoveToJmf`|**Karantina iletisi** <br><br> `Quarantine`||
|**Yüksek güvenilirlikli istenmeyen posta** algılama eylemi <br><br> _HighConfidenceSpamAction_|**İletiyi Gereksiz Email klasörüne taşıma** <br><br> `MoveToJmf`|**Karantina iletisi** <br><br> `Quarantine`|**Karantina iletisi** <br><br> `Quarantine`||
|**Kimlik avı** algılama eylemi <br><br> _PhishSpamAction_|**İletiyi Gereksiz Email klasörüne taşıma**<sup>\*</sup> <br><br> `MoveToJmf`|**Karantina iletisi** <br><br> `Quarantine`|**Karantina iletisi** <br><br> `Quarantine`|<sup>\*</sup>Varsayılan değer, varsayılan istenmeyen posta önleme ilkesinde ve PowerShell'de oluşturduğunuz yeni istenmeyen posta önleme ilkelerinde **iletiyi Gereksiz Email klasörüne taşı'dır**. Varsayılan değer, Microsoft 365 Defender portalında oluşturduğunuz yeni istenmeyen posta önleme ilkelerinde **karantina iletisidir**.|
|**Yüksek güvenilirlikli kimlik avı** algılama eylemi <br><br> _HighConfidencePhishAction_|**Karantina iletisi** <br><br> `Quarantine`|**Karantina iletisi** <br><br> `Quarantine`|**Karantina iletisi** <br><br> `Quarantine`||
|**Toplu** algılama eylemi <br><br> _BulkSpamAction_|**İletiyi Gereksiz Email klasörüne taşıma** <br><br> `MoveToJmf`|**İletiyi Gereksiz Email klasörüne taşıma** <br><br> `MoveToJmf`|**Karantina iletisi** <br><br> `Quarantine`||
|**İstenmeyen postaları bu kadar gün boyunca karantinada tutma** <br><br> _QuarantineRetentionPeriod_|15 gün<sup>\*</sup>|30 gün|30 gün|<sup>\*</sup> Varsayılan değer, varsayılan istenmeyen posta önleme ilkesinde ve PowerShell'de oluşturduğunuz yeni istenmeyen posta önleme ilkelerinde 15 gündür. varsayılan değer, Microsoft 365 Defender portalında oluşturduğunuz yeni istenmeyen posta önleme ilkelerinde 30 gündür. <br><br> Bu değer, kimlik avı önleme ilkeleri tarafından karantinaya alınan iletileri de etkiler. Daha fazla bilgi için bkz. [EOP'de karantinaya alınan e-posta iletileri](quarantine-email-messages.md).|
|**İstenmeyen posta güvenliği ipuçlarını etkinleştirme** <br><br> _InlineSafetyTipsEnabled_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|Kimlik avı iletileri için sıfır saatlik otomatik temizlemeyi (ZAP) etkinleştirme <br><br> _PhishZapEnabled_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|İstenmeyen posta iletileri için ZAP'i etkinleştirme <br><br> _SpamZapEnabled_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**& engelleme listesine izin ver**|||||
|İzin verilen gönderenler <br><br> _AllowedSenders_|Yok|Yok|Yok||
|İzin verilen gönderen etki alanları <br><br> _AllowedSenderDomains_|Yok|Yok|Yok|İzin verilen gönderenler listesine etki alanları eklemek çok kötü bir fikirdir. Saldırganlar, aksi takdirde filtrelenecek e-postaları size gönderebilir. <br><br> Kuruluşunuzun e-posta etki alanlarında gönderen e-posta adreslerini sahtekarlık yapan veya dış etki alanlarında gönderen e-posta adreslerini sahtekarlık yapan tüm gönderenleri gözden geçirmek için kimlik sahtekarlığına ilişkin bilgi sahtekarlık [içgörülerini](learn-about-spoof-intelligence.md) ve [Kiracı İzin Ver/Engelle Listesi'ni](tenant-allow-block-list.md) kullanın.|
|Engellenen gönderenler <br><br> _BlockedSenders_|Yok|Yok|Yok||
|Engellenen gönderen etki alanları <br><br> _BlockedSenderDomains_|Yok|Yok|Yok||

#### <a name="asf-settings-in-anti-spam-policies"></a>İstenmeyen posta önleme ilkelerinde ASF ayarları

İstenmeyen posta önleme ilkelerindeki Gelişmiş İstenmeyen Posta Filtresi (ASF) ayarları hakkında daha fazla bilgi için bkz. [EOP'de Gelişmiş İstenmeyen Posta Filtresi (ASF) ayarları](advanced-spam-filtering-asf-options.md).

|Güvenlik özelliği adı|Varsayılan|Önerilen<br/>Standart|Önerilen<br/>Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Uzak sitelere resim bağlantıları** <br><br> _IncreaseScoreWithImageLinks_|Devre Dışı|Devre Dışı|Devre Dışı||
|**URL'deki sayısal IP adresi** <br><br> _IncreaseScoreWithNumericIps_|Devre Dışı|Devre Dışı|Devre Dışı||
|**URL'yi başka bir bağlantı noktasına yönlendirme** <br><br> _IncreaseScoreWithRedirectToOtherPort_|Devre Dışı|Devre Dışı|Devre Dışı||
|**.biz veya .info web sitelerine bağlantılar** <br><br> _IncreaseScoreWithBizOrInfoUrls_|Devre Dışı|Devre Dışı|Devre Dışı||
|**Boş iletiler** <br><br> _MarkAsSpamEmptyMessages_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de etiketleri ekleme** <br><br> _MarkAsSpamEmbedTagsInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de JavaScript veya VBScript** <br><br> _MarkAsSpamJavaScriptInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de form etiketleri** <br><br> _MarkAsSpamFormTagsInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de çerçeve veya iframe etiketleri** <br><br> _MarkAsSpamFramesInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de web hataları** <br><br> _MarkAsSpamWebBugsInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**HTML'de nesne etiketleri** <br><br> _MarkAsSpamObjectTagsInHtml_|Devre Dışı|Devre Dışı|Devre Dışı||
|**Hassas sözcükler** <br><br> _MarkAsSpamSensitiveWordList_|Devre Dışı|Devre Dışı|Devre Dışı||
|**SPF kaydı: sabit hata** <br><br> _MarkAsSpamSpfRecordHardFail_|Devre Dışı|Devre Dışı|Devre Dışı||
|**Gönderen Kimliği filtrelemesi sabit başarısız oldu** <br><br> _MarkAsSpamFromAddressAuthFail_|Devre Dışı|Devre Dışı|Devre Dışı||
|**Backscatter** <br><br> _MarkAsSpamNdrBackscatter_|Devre Dışı|Devre Dışı|Devre Dışı||
|**Test modu** <br><br> _TestModeAction_)|Yok|Yok|Yok|Eylem olarak **Test'i** destekleyen ASF ayarları için, test modu eylemini **Yok**, **Varsayılan X Üst Bilgisi metni ekle** veya **Gizli İleti Gönder** (`None`, `AddXHeader`veya `BccMessage`) olarak yapılandırabilirsiniz. Daha fazla bilgi için bkz [. ASF ayarlarını etkinleştirme, devre dışı bırakma veya test edin](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings).|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP giden istenmeyen posta ilkesi ayarları

Giden istenmeyen posta ilkeleri oluşturmak ve yapılandırmak için bkz. [EOP'de giden istenmeyen posta filtrelemesini yapılandırma](configure-the-outbound-spam-policy.md).

Hizmetteki varsayılan gönderme sınırları hakkında daha fazla bilgi için bkz [. Gönderme sınırları](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

> [!NOTE]
> Giden istenmeyen posta ilkeleri Standart veya Katı önceden ayarlanmış güvenlik ilkelerinin bir parçası değildir. **Standart** ve **Katı** değerleri, oluşturduğunuz varsayılan giden istenmeyen posta ilkesinde veya özel giden istenmeyen posta ilkelerinde **önerilen** değerlerimizi gösterir.

|Güvenlik özelliği adı|Varsayılan|Önerilen<br/>Standart|Önerilen<br/>Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Dış ileti sınırı ayarlama** <br><br> _RecipientLimitExternalPerHour_|0|500|400|Varsayılan değer 0, hizmet varsayılanlarını kullanma anlamına gelir.|
|**İç ileti sınırı ayarlama** <br><br> _RecipientLimitInternalPerHour_|0|1000|800|Varsayılan değer 0, hizmet varsayılanlarını kullanma anlamına gelir.|
|**Günlük ileti sınırı ayarlama** <br><br> _RecipientLimitPerDay_|0|1000|800|Varsayılan değer 0, hizmet varsayılanlarını kullanma anlamına gelir.|
|**İleti sınırına ulaşan kullanıcılara getirilen kısıtlama** <br><br> _ActionWhenThresholdReached_|**Kullanıcının posta göndermesini bir sonraki güne kadar kısıtlayın** <br><br> `BlockUserForToday`|**Kullanıcının posta göndermesini kısıtlama** <br><br> `BlockUser`|**Kullanıcının posta göndermesini kısıtlama** <br><br> `BlockUser`||
|**Otomatik iletme kuralları** <br><br> _AutoForwardingMode_|**Otomatik - Sistem kontrollü** <br><br> `Automatic`|**Otomatik - Sistem kontrollü** <br><br> `Automatic`|**Otomatik - Sistem kontrollü** <br><br> `Automatic`|
|**Bu sınırları aşan giden iletilerin bir kopyasını bu kullanıcılara ve gruplara gönder** <br><br> _BccSuspiciousOutboundMail_ <br><br> _BccSuspiciousOutboundAdditionalRecipients_|Seçili değil <br><br> `$false` <br><br> Boş|Seçili değil <br><br> `$false` <br><br> Boş|Seçili değil <br><br> `$false` <br><br> Boş|Bu ayar için belirli bir önerimiz yok. <br><br> Bu ayar yalnızca varsayılan giden istenmeyen posta ilkesinde çalışır. Oluşturduğunuz özel giden istenmeyen posta ilkelerinde çalışmaz.|
|**Bir gönderen giden istenmeyen posta gönderdiği için engellendiyse bu kullanıcıları ve grupları bilgilendirin** <br><br> _NotifyOutboundSpam_ <br><br> _NotifyOutboundSpamRecipients_|Seçili değil <br><br> `$false` <br><br> Boş|Seçili değil <br><br> `$false` <br><br> Boş|Seçili değil <br><br> `$false` <br><br> Boş|**Kullanıcı'nın e-posta göndermesi kısıtlandı** adlı varsayılan [uyarı ilkesi](../../compliance/alert-policies.md), ilkedeki sınırları aştığı için kullanıcılar engellendiğinde **TenantAdmins** (**Genel yöneticiler**) grubunun üyelerine zaten e-posta bildirimleri gönderir. **Yöneticileri ve diğer kullanıcıları bilgilendirmek için giden istenmeyen posta ilkesinde bu ayar yerine uyarı ilkesini kullanmanızı kesinlikle öneririz**. Yönergeler için bkz [. Kısıtlı kullanıcılar için uyarı ayarlarını doğrulama](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).|

### <a name="eop-anti-malware-policy-settings"></a>EOP kötü amaçlı yazılımdan koruma ilkesi ayarları

Kötü amaçlı yazılımdan koruma ilkeleri oluşturmak ve yapılandırmak için bkz. [EOP'de kötü amaçlı yazılımdan koruma ilkelerini yapılandırma](configure-anti-malware-policies.md).

|Güvenlik özelliği adı|Varsayılan|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Koruma ayarları**|||||
|**Ortak ekler filtresini etkinleştirme** <br><br> _EnableFileFilter_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Bu ayar, ek içeriğine bakılmaksızın dosya türüne göre ek içeren iletileri karantinaya alır. Dosya türlerinin listesi için bkz [. Kötü amaçlı yazılımdan koruma ilkeleri](anti-malware-protection.md#anti-malware-policies).|
|**Kötü amaçlı yazılım için sıfır saatlik otomatik temizlemeyi etkinleştirme** <br><br> _ZapEnabled_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Karantina ilkesi**|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|Yeni bir kötü amaçlı yazılımdan koruma ilkesi oluşturduğunuzda boş bir değer, kötü amaçlı yazılım olarak karantinaya alınan iletilerin geçmiş özelliklerini tanımlamak için varsayılan karantina ilkesinin kullanıldığı anlamına gelir (Karantina bildirimleri olmadan AdminOnlyAccessPolicy). <br><br> Standart ve Katı önceden ayarlanmış güvenlik ilkeleri [, buradaki](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) tabloda açıklandığı gibi varsayılan karantina ilkesini (Karantina bildirimleri olmadan AdminOnlyAccessPolicy) kullanır. <br><br> Yöneticiler, varsayılan veya özel kötü amaçlı yazılımdan koruma ilkelerinde kullanıcılar için daha fazla özellik tanımlayan özel karantina ilkeleri oluşturabilir ve seçebilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).|
|**Yönetici bildirimleri**|||||
|**İç gönderenlerden gelen teslim edilmemiş iletiler hakkında yöneticiyi bilgilendirme** <br><br> _EnableInternalSenderAdminNotifications_ <br><br> _InternalSenderAdminAddress_|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Bu ayar için belirli bir önerimiz yok.|
|**Dış gönderenlerden gelen teslim edilmemiş iletiler hakkında yöneticiye bildirme** <br><br> _EnableExternalSenderAdminNotifications_ <br><br> _ExternalSenderAdminAddress_|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Bu ayar için belirli bir önerimiz yok.|
|**Bildirimleri özelleştirme**||||Bu ayarlar için belirli bir önerimiz yok.|
|**Özelleştirilmiş bildirim metnini kullanma** <br><br> _CustomNotifications_|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`||
|**Kimden adı** <br><br> _CustomFromName_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||
|**Kimden adresi** <br><br> _CustomFromAddress_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||
|**İç gönderenlerden gelen iletiler için bildirimleri özelleştirme**||||Bu ayarlar yalnızca **dahili gönderenlerden gelen teslim edilmemiş iletiler hakkında yöneticiye bildir** seçiliyse kullanılır.|
|**Konu** <br><br> _CustomInternalSubject_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||
|**İleti** <br><br> _CustomInternalBody_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||
|**Dış gönderenlerden gelen iletiler için bildirimleri özelleştirme**||||Bu ayarlar yalnızca **Dış gönderenlerden gelen teslim edilmemiş iletiler hakkında yöneticiye bildir** seçiliyse kullanılır.|
|**Konu** <br><br> _CustomExternalSubject_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||
|**İleti** <br><br> _CustomExternalBody_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`||

### <a name="eop-anti-phishing-policy-settings"></a>EOP kimlik avı önleme ilkesi ayarları

Bu ayarlar hakkında daha fazla bilgi için bkz. [Kimlik sahtekarlık ayarları](set-up-anti-phishing-policies.md#spoof-settings). Bu ayarları yapılandırmak için bkz. [EOP'de kimlik avı önleme ilkelerini yapılandırma](configure-anti-phishing-policies-eop.md).

Kimlik sahtekarlığı ayarları birbiriyle ilişkilidir, ancak **İlk kişi güvenlik ipucunu göster** ayarının kimlik sahtekarlığı ayarlarına bağımlılığı yoktur.

|Güvenlik özelliği adı|Varsayılan|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Kimlik avı eşiği & koruma**|||||
|**Kimlik sahtekarı zekasını etkinleştirme** <br><br> _EnableSpoofIntelligence_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Eylem**|||||
|**İletinin yanıltma olarak algılanırsa** <br><br> _AuthenticationFailAction_|**İletiyi alıcıların Gereksiz Email klasörlerine taşıma** <br><br> `MoveToJmf`|**İletiyi alıcıların Gereksiz Email klasörlerine taşıma** <br><br> `MoveToJmf`|**İletiyi karantinaya al** <br><br> `Quarantine`|Bu ayar, kimlik sahtekarlığı [bilgileri içgörülerinde](learn-about-spoof-intelligence.md) gösterildiği gibi otomatik olarak engellenen veya [Kiracı İzin Ver/Engelle Listesi'nde](tenant-allow-block-list.md) el ile engellenen sahte gönderenler için geçerlidir. <br><br> **İletiyi karantinaya al'ı** seçerseniz, kullanıcıların kimlik sahtekarlığına karşı **karantinaya** alınan iletilere ne yapmalarına izin verildiğini tanımlayan karantina ilkesini seçmek için bir Karantina ilkesi uygula kutusu kullanılabilir. Yeni bir kimlik avı önleme ilkesi oluşturduğunuzda boş bir değer, kimlik sahtekarlığı olarak karantinaya alınan iletilerin geçmiş özelliklerini tanımlamak için varsayılan karantina ilkesinin kullanıldığı anlamına gelir (Karantina bildirimleri olmadan DefaultFullAccessPolicy). <br><br> Standart ve Katı önceden ayarlanmış güvenlik ilkeleri [, buradaki](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) tabloda açıklandığı gibi varsayılan karantina ilkesini (Karantina bildirimleri olmadan DefaultFullAccessPolicy) kullanır. <br><br> Yöneticiler, varsayılan veya özel kimlik avı önleme ilkelerinde kullanıcılar için daha kısıtlayıcı veya daha az kısıtlayıcı özellikler tanımlayan özel karantina ilkeleri oluşturabilir ve seçebilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).|
|**İlk temas emniyet ipucunu göster** <br><br> _EnableFirstContactSafetyTips_|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Daha fazla bilgi için bkz. [İlk iletişim güvenliği ipucu](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Kimlik sahtekarlığına yönelik kimliği doğrulanmamış gönderenler için göster (?)** <br><br> _EnableUnauthenticatedSender_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Kimliği belirsiz gönderenler için Outlook'ta gönderenin fotoğrafına soru işareti (?) ekler. Daha fazla bilgi için bkz. [Kimliği doğrulanmamış gönderen göstergeleri](set-up-anti-phishing-policies.md#unauthenticated-sender-indicators).|
|**"via" etiketini göster** <br><br> _EnableViaTag_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|DKIM imzasında etki alanından veya **MAIL FROM** adresinden farklıysa Kimden adresine bir via etiketi (fabrikam.com aracılığıyla chris@contoso.com) ekler. <br><br> Daha fazla bilgi için bkz. [Kimliği doğrulanmamış gönderen göstergeleri](set-up-anti-phishing-policies.md#unauthenticated-sender-indicators).|

## <a name="microsoft-defender-for-office-365-security"></a>güvenlik Office 365 için Microsoft Defender

Ek güvenlik avantajları, Office 365 için Microsoft Defender bir abonelikle birlikte gelir. En son haberler ve bilgiler için [Office 365 için Defender'deki yenilikler'i](whats-new-in-defender-for-office-365.md) görebilirsiniz.

> [!IMPORTANT]
>
> - Office 365 için Microsoft Defender'daki varsayılan kimlik avı önleme ilkesi, tüm alıcılar için [kimlik sahtekarlığı koruması](set-up-anti-phishing-policies.md#spoof-settings) ve posta kutusu zekası sağlar. Ancak, diğer kullanılabilir [kimliğe bürünme koruması](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) özellikleri ve [gelişmiş ayarlar](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) varsayılan ilkede yapılandırılmaz veya etkinleştirilmez. Tüm koruma özelliklerini etkinleştirmek için varsayılan kimlik avı önleme ilkesini değiştirin veya ek kimlik avı önleme ilkeleri oluşturun.
>
> - Varsayılan Güvenli Ekler ilkesi veya Güvenli Bağlantılar ilkesi olmasa **da, yerleşik koruma** önceden ayarlanmış güvenlik ilkesi, özel Güvenli Ekler ilkelerine veya Güvenli Bağlantılar ilkelerine henüz dahil olmayan alıcılara Güvenli Ekler koruması ve Güvenli Bağlantılar koruması sağlar. Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).
>
> - [SharePoint, OneDrive ve Microsoft Teams koruması ve](mdo-for-spo-odb-and-teams.md) [Güvenli Belgeler](safe-docs.md) koruması için Güvenli Ekler'in Güvenli Bağlantılar ilkelerine bağımlılığı yoktur.

Aboneliğinizde Office 365 için Microsoft Defender varsa veya Office 365 için Defender eklenti olarak satın aldıysanız aşağıdaki Standart veya Katı yapılandırmaları ayarlayın.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender kimlik avı önleme ilkesi ayarları

EOP müşterileri daha önce açıklandığı gibi temel kimlik avı önleme özelliğine sahiptir, ancak Office 365 için Defender saldırıları önlemeye, algılamaya ve bunlara karşı düzeltmeye yardımcı olmak için daha fazla özellik ve denetim içerir. Bu ilkeleri oluşturmak ve yapılandırmak için bkz. [Office 365 için Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md).

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerindeki gelişmiş ayarlar

Bu ayar hakkında daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerinde gelişmiş kimlik avı eşikleri](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Bu ayarı yapılandırmak için bkz. [Office 365 için Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md).

|Güvenlik özelliği adı|Varsayılan|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Kimlik avı e-posta eşiği** <br><br> _PhishThresholdLevel_|**1 - Standart** <br><br> `1`|**2 - Agresif** <br><br> `2`|**3 - Daha agresif** <br><br> `3`||

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender kimlik avı önleme ilkelerindeki kimliğe bürünme ayarları

Bu ayarlar hakkında daha fazla bilgi için bkz[. Office 365 için Microsoft Defender kimlik avı önleme ilkelerindeki kimliğe bürünme ayarları](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Bu ayarları yapılandırmak için bkz. [Office 365 için Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md).

|Güvenlik özelliği adı|Varsayılan|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|---|
|**Kimlik avı eşiği & koruma**|||||
|**Kullanıcıların korumasını sağlama** (kimliğine bürünülen kullanıcı koruması) <br><br> _EnableTargetedUserProtection_ <br><br> _TargetedUsersToProtect_|Seçili değil <br><br> `$false` <br><br> yok|Seçili <br><br> `$true` <br><br> \<list of users\>|Seçili <br><br> `$true` <br><br> \<list of users\>|Önemli rollere kullanıcı (ileti gönderenler) eklemenizi öneririz. Dahili olarak, korunan gönderenler CEO'nuz, CFO'nuz ve diğer üst düzey liderler olabilir. Dışarıdan, korunan gönderenler konsey üyelerini veya yönetim kurulunuzu içerebilir.|
|**Etki alanlarının korunmasını etkinleştirme** (kimliğine bürünülen etki alanı koruması)|Seçili değil|Seçili|Seçili||
|**Sahip olduğum etki alanlarını dahil et** <br><br> _EnableOrganizationDomainsProtection_|Devre Dışı <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Özel etki alanları ekleme** <br><br> _EnableTargetedDomainsProtection_ <br><br> _TargetedDomainsToProtect_|Devre Dışı <br><br> `$false` <br><br> yok|Seçili <br><br> `$true` <br><br> \<list of domains\>|Seçili <br><br> `$true` <br><br> \<list of domains\>|Sahip olmadığınız ancak sık sık etkileşimde olduğunuz etki alanlarını (gönderen etki alanları) eklemenizi öneririz.|
|**Güvenilir gönderenler ve etki alanları ekleme** <br><br> _ExcludedSenders_ <br><br> _ExcludedDomains_|Yok|Yok|Yok|Kuruluşunuza bağlı olarak, kimliğine bürünme girişimleri olarak yanlış tanımlanan gönderenler veya etki alanları eklemenizi öneririz.|
|**Posta kutusu zekasını etkinleştirme** <br><br> _EnableMailboxIntelligence_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Kimliğe bürünme koruması için zekayı etkinleştirme** <br><br> _EnableMailboxIntelligenceProtection_|Devre Dışı <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Bu ayar, posta kutusu zekası tarafından kimliğe bürünme algılamaları için belirtilen eyleme izin verir.|
|**Eylem**||||**İletiyi karantinaya al'ı** seçtiğinizde **, Karantina ilkesi** seçin kutusu kullanılabilir. Karantina ilkeleri, kullanıcıların karantinaya alınan iletilere ne yapmalarına izin verılacağını tanımlar. <br><br> Standart ve Katı önceden ayarlanmış güvenlik ilkeleri [, buradaki](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) tabloda açıklandığı gibi varsayılan karantina ilkesini (Karantina bildirimleri olmadan DefaultFullAccessPolicy) kullanır. <br><br> Yeni bir kimlik avı önleme ilkesi oluşturduğunuzda, boş bir değer varsayılan karantina ilkesinin bu karar tarafından karantinaya alınan iletilerin geçmiş özelliklerini tanımlamak için kullanıldığı anlamına gelir (tüm kimliğe bürünme algılama türleri için DefaultFullAccessPolicy). <br><br> Yöneticiler, varsayılan veya özel kimlik avı önleme ilkelerindeki kullanıcılar için daha az kısıtlayıcı veya daha kısıtlayıcı özellikler tanımlayan özel karantina ilkeleri oluşturabilir ve seçebilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).|
|**İleti kimliğine bürünülen bir kullanıcı olarak algılanırsa** <br><br> _TargetedUserProtectionAction_|**Hiçbir eylem uygulama** <br><br> `NoAction`|**İletiyi karantinaya al** <br><br> `Quarantine`|**İletiyi karantinaya al** <br><br> `Quarantine`||
|**İleti kimliğine bürünülen bir etki alanı olarak algılanırsa** <br><br> _TargetedDomainProtectionAction_|**Hiçbir eylem uygulama** <br><br> `NoAction`|**İletiyi karantinaya al** <br><br> `Quarantine`|**İletiyi karantinaya al** <br><br> `Quarantine`||
|**Posta kutusu zekası algılarsa ve kimliğine bürünülen kullanıcı** <br><br> _MailboxIntelligenceProtectionAction_|**Hiçbir eylem uygulama** <br><br> `NoAction`|**İletiyi alıcıların Gereksiz Email klasörlerine taşıma** <br><br> `MoveToJmf`|**İletiyi karantinaya al** <br><br> `Quarantine`||
|**Kullanıcı kimliğe bürünme güvenlik ipucunu göster** <br><br> _EnableSimilarUsersSafetyTips_|Devre Dışı <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Etki alanı kimliğe bürünme güvenlik ipucunu göster** <br><br> _EnableSimilarDomainsSafetyTips_|Devre Dışı <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Kullanıcı kimliğe bürünme olağan dışı karakterler güvenlik ipucunu göster** <br><br> _EnableUnusualCharactersSafetyTips_|Devre Dışı <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'da EOP kimlik avı önleme ilkesi ayarları

Bunlar [, EOP'deki istenmeyen posta önleme ilkesi ayarlarında kullanılabilen ayarlarla](#eop-anti-spam-policy-settings) aynıdır.

### <a name="safe-attachments-settings"></a>Güvenli Ekler ayarları

Office 365 için Microsoft Defender'daki Güvenli Ekler, Güvenli Ekler ilkeleriyle ilişkisi olmayan genel ayarları ve her Güvenli Bağlantı ilkesine özgü ayarları içerir. Daha fazla bilgi için bkz. [Office 365 için Defender'da Güvenli Ekler](safe-attachments.md).

Varsayılan Güvenli Ekler ilkesi olmasa **da yerleşik koruma** ön ayarı güvenlik ilkesi, özel Güvenli Ekler ilkelerine henüz dahil olmayan tüm alıcılara Güvenli Ekler koruması sağlar. Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).

#### <a name="global-settings-for-safe-attachments"></a>Güvenli Ekler için genel ayarlar

> [!NOTE]
> Güvenli Ekler için genel ayarlar **Yerleşik koruma** önayarlı güvenlik ilkesi tarafından ayarlanır, ancak **Standart** veya **Katı** önceden belirlenmiş güvenlik ilkeleri tarafından ayarlanmaz. Her iki durumda da yöneticiler bu genel Güvenli Ekler ayarlarını istedikleri zaman değiştirebilir.
>
> **Varsayılan** sütun **, Yerleşik koruma** önceden ayarlanmış güvenlik ilkesinin varlığından önceki değerleri gösterir. **Yerleşik koruma** sütunu, yerleşik **koruma** önceden ayarlanmış güvenlik ilkesi tarafından ayarlanan değerleri gösterir ve bunlar da önerilen değerlerimizdir.

Bu ayarları yapılandırmak için bkz. [Microsoft 365 E5'da SharePoint, OneDrive ve Microsoft Teams ve](turn-on-mdo-for-spo-odb-and-teams.md) [Güvenli Belgeler için Güvenli Ekler'i](safe-docs.md) açma.

PowerShell'de, bu ayarlar için [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet'ini kullanırsınız.

|Güvenlik özelliği adı|Varsayılan|Yerleşik koruma|Açıklama ekleme|
|---|:---:|:---:|---|
|**SharePoint, OneDrive ve Microsoft Teams için Office 365 için Defender açma** <br><br> _EnableATPForSPOTeamsODB_|Devre Dışı <br><br> `$false`|-Inı <br><br> `$true`|Kullanıcıların kötü amaçlı dosyaları indirmesini önlemek için bkz. [Kullanıcıların kötü amaçlı dosyaları indirmesini önlemek için SharePoint Online PowerShell'i kullanma](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).|
|**Office istemcileri için Güvenli Belgeler'i açma** <br><br> _EnableSafeDocs_|Devre Dışı <br><br> `$false`|-Inı <br><br> `$true`|Bu özellik yalnızca Office 365 için Defender (örneğin, Microsoft 365 E5 veya Microsoft 365 E5 Güvenlik) dahil olmayan lisanslarla kullanılabilir ve anlamlıdır. Daha fazla bilgi için bkz. [Microsoft 365 E5'de Güvenli Belgeler](safe-docs.md).|
|**Güvenli Belgeler dosyayı kötü amaçlı olarak tanımlasa bile kişilerin Korumalı Görünüm'e tıklamasına izin ver** <br><br> _AllowSafeDocsOpen_|Devre Dışı <br><br> `$false`|Devre Dışı <br><br> `$false`|Bu ayar Güvenli Belgeler ile ilgilidir.|

#### <a name="safe-attachments-policy-settings"></a>Güvenli Ekler ilke ayarları

Bu ayarları yapılandırmak için bkz. [Office 365 için Defender'da Güvenli Ekler ilkelerini ayarlama](set-up-safe-attachments-policies.md).

PowerShell'de, bu ayarlar için [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) ve [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet'lerini kullanırsınız.

> [!NOTE]
> Daha önce açıklandığı gibi, varsayılan Güvenli Ekler ilkesi yoktur, ancak [**Yerleşik koruma** önceden ayarlanmış güvenlik ilkesi](preset-security-policies.md) tarafından tüm alıcılara Güvenli Ekler koruması atanır.
>
> **Özel sütunda Varsayılan**, oluşturduğunuz yeni Güvenli Ekler ilkelerindeki varsayılan değerleri ifade eder. Kalan sütunlar, karşılık gelen önceden belirlenmiş güvenlik ilkelerinde yapılandırılan değerleri belirtir (aksi belirtilmedikçe).

|Güvenlik özelliği adı|Özelde varsayılan|Yerleşik koruma|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|:---:|---|
|**Güvenli Ekler bilinmeyen kötü amaçlı yazılım yanıtı** <br><br> _Etkinleştir_ ve _Eylem_|**Devre Dışı** <br><br> `-Enable $false` Ve `-Action Block`|**Engelle** <br><br> `-Enable $true` Ve `-Action Block`|**Engelle** <br><br> `-Enable $true` Ve `-Action Block`|**Engelle** <br><br> `-Enable $true` Ve `-Action Block`|_Enable_ parametresi $false olduğunda _, Action_ parametresinin değeri önemli değildir.|
|**Karantina ilkesi** (_QuarantineTag_)|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy|AdminOnlyAccessPolicy| <br><br> Standart ve Katı önceden ayarlanmış güvenlik ilkeleri [, buradaki](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) tabloda açıklandığı gibi varsayılan karantina ilkesini (Karantina bildirimleri olmadan AdminOnlyAccessPolicy) kullanır. <br><br> Yeni bir Güvenli Ekler ilkesi oluşturduğunuzda, boş bir değer, Güvenli Ekler tarafından karantinaya alınan iletilerin geçmiş özelliklerini tanımlamak için varsayılan karantina ilkesinin kullanıldığı anlamına gelir (Karantina bildirimleri olmadan AdminOnlyAccessPolicy). <br><br> Yöneticiler, kullanıcılar için daha fazla özellik tanımlayan özel karantina ilkeleri oluşturabilir ve seçebilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).|
|**Algılanan eklerle eki yeniden yönlendirme** : **Yeniden yönlendirmeyi etkinleştirme** <br><br> _Yönlendirme_ <br><br> _RedirectAddress_|Seçili değil ve e-posta adresi belirtilmedi. <br><br> `-Redirect $false` <br><br> _RedirectAddress_ boş (`$null`)|Seçili değil ve e-posta adresi belirtilmedi. <br><br> `-Redirect $false` <br><br> _RedirectAddress_ boş (`$null`)|Seçili ve bir e-posta adresi belirtin. <br><br> `$true` <br><br> e-posta adresi|Seçili ve bir e-posta adresi belirtin. <br><br> `$true` <br><br> e-posta adresi|İletileri gözden geçirilmek üzere bir güvenlik yöneticisine yeniden yönlendirin. <br><br> **Not**: Bu ayar **Standart**, **Katı** veya Yerleşik koruma önceden ayarlanmış güvenlik **ilkelerinde** yapılandırılmaz. **Standart** ve **Katı** değerler, oluşturduğunuz yeni Güvenli Ekler ilkelerinde **önerilen** değerlerimizi gösterir.|
|**Tarama tamamlanamadıysa Güvenli Ekler algılama yanıtını uygulama (zaman aşımı veya hatalar)** <br><br> _ActionOnError_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||

### <a name="safe-links-settings"></a>Güvenli Bağlantılar ayarları

Office 365 için Defender'deki Güvenli Bağlantılar, etkin Güvenli Bağlantılar ilkelerine dahil edilen tüm kullanıcılar için geçerli olan genel ayarları ve her Güvenli Bağlantı ilkesine özgü ayarları içerir. Daha fazla bilgi için bkz. [Office 365 için Defender'de Güvenli Bağlantılar](safe-links.md).

Varsayılan Güvenli Bağlantılar ilkesi olmasa **da, yerleşik koruma** ön ayarı güvenlik ilkesi tüm alıcılara Güvenli Bağlantılar koruması sağlar (özel Güvenli Bağlantılar ilkelerinde veya Standart veya Katı ön ayarlı güvenlik ilkelerinde tanımlanmayan kullanıcılar). Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).

#### <a name="global-settings-for-safe-links"></a>Güvenli Bağlantılar için genel ayarlar

> [!NOTE]
> Güvenli Bağlantılar için genel ayarlar **Yerleşik koruma** önayarlı güvenlik ilkesi tarafından ayarlanır, ancak **Standart** veya **Katı** önceden belirlenmiş güvenlik ilkeleri tarafından ayarlanmaz. Her iki durumda da yöneticiler bu genel Güvenli Bağlantılar ayarlarını istedikleri zaman değiştirebilir.
>
> **Varsayılan** sütun **, Yerleşik koruma** önceden ayarlanmış güvenlik ilkesinin varlığından önceki değerleri gösterir. **Yerleşik koruma** sütunu, yerleşik **koruma** önceden ayarlanmış güvenlik ilkesi tarafından ayarlanan değerleri gösterir ve bunlar da önerilen değerlerimizdir.

Bu ayarları yapılandırmak için bkz[. Office 365 için Defender'de Güvenli Bağlantılar için genel ayarları yapılandırma](configure-global-settings-for-safe-links.md).

PowerShell'de, bu ayarlar için [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) cmdlet'ini kullanırsınız.

|Güvenlik özelliği adı|Varsayılan|Yerleşik koruma|Açıklama ekleme|
|---|:---:|:---:|---|
|**Aşağıdaki URL'leri engelleyin** <br><br> _ExcludedUrls_|Boş <br><br> `$null`|Boş <br><br> `$null`|Bu ayar için belirli bir önerimiz yok. <br><br> Daha fazla bilgi [için Güvenli Bağlantılar için "Aşağıdaki URL'leri engelle" listesine](safe-links.md#block-the-following-urls-list-for-safe-links) bakın. <br><br> **Not**: Artık [Kiracı İzin Ver/Engelle Listesi'nde](allow-block-urls.md#create-block-url-entries-in-the-tenant-allowblock-list) blok URL'si girdilerini yönetebilirsiniz. "Aşağıdaki URL'leri engelle" listesi kullanım dışı bırakılıyor. Kiracı İzin Ver/Engelle Listesindeki URL girdilerini engellemek için "Aşağıdaki URL'leri engelle" listesinden mevcut girdileri geçirmeyi deneyeceğiz. Engellenen URL'yi içeren iletiler karantinaya alınır.|

#### <a name="safe-links-policy-settings"></a>Güvenli Bağlantılar ilke ayarları

Bu ayarları yapılandırmak için bkz. [Office 365 için Microsoft Defender'de Güvenli Bağlantılar ilkelerini ayarlama](set-up-safe-links-policies.md).

PowerShell'de, bu ayarlar için [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) ve [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) cmdlet'lerini kullanırsınız.

> [!NOTE]
> Daha önce açıklandığı gibi, varsayılan Güvenli Bağlantılar ilkesi yoktur, ancak [**Yerleşik koruma** önceden ayarlanmış güvenlik ilkesi](preset-security-policies.md) tarafından tüm alıcılara Güvenli Bağlantılar koruması atanır.
>
> **Özel sütunda Varsayılan**, oluşturduğunuz yeni Güvenli Bağlantılar ilkelerindeki varsayılan değerleri ifade eder. Kalan sütunlar, karşılık gelen önceden belirlenmiş güvenlik ilkelerinde yapılandırılan değerleri belirtir (aksi belirtilmedikçe).

|Güvenlik özelliği adı|Özelde varsayılan|Yerleşik koruma|Standart|Sıkı|Açıklama ekleme|
|---|:---:|:---:|:---:|:---:|---|
|**URL & koruma ayarlarına tıklayın**||||||
|**E-postalar içindeki kötü amaçlı olabilecek URL'ler üzerinde eylem**||||||
|**Açık: Güvenli Bağlantılar, kullanıcılar e-postadaki bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler** <br><br> _EnableSafeLinksForEmail_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Kuruluş içinde gönderilen e-posta iletilerine Güvenli Bağlantılar uygulama** <br><br> _EnableForInternalSenders_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Şüpheli bağlantılar ve dosyalara işaret eden bağlantılar için gerçek zamanlı URL taraması uygulama** <br><br> _ScanUrls_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**İletiyi teslim etmeden önce URL taramasının tamamlanmasını bekleyin** <br><br> _DeliverMessageAfterScan_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**URL'leri yeniden yazmayın, denetimleri yalnızca Güvenli Bağlantılar API'si aracılığıyla yapın** <br><br> _DisableURLRewrite_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`||
|**E-postada aşağıdaki URL'leri yeniden yazmayın** <br><br> _DoNotRewriteUrls_|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`|Boş <br><br> `$null`|Bu ayar için belirli bir önerimiz yok. <br><br> **Not**: "Aşağıdaki URL'leri yeniden yazmayın" listesindeki girişler, posta akışı sırasında Güvenli Bağlantılar tarafından taranmıyor veya sarmalanmıyor. Posta akışı sırasında _ve_ tıklandığında URL'lerin Güvenli Bağlantılar tarafından taranmaması veya sarmalanmaması için [Kiracı İzin Ver/Engelle Listesi'ndeki İzin Ver URL girişlerini](allow-block-urls.md#create-allow-url-entries) kullanın.|
|**Microsoft Teams'de kötü amaçlı olabilecek URL'ler için eylem**||||||
|**Açık: Güvenli Bağlantılar, kullanıcılar Microsoft Teams'de bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler** <br><br> _EnableSafeLinksForTeams_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Microsoft Office uygulamalarında kötü amaçlı olabilecek URL'ler için eylem**||||||
|**Açık: Güvenli Bağlantılar, kullanıcılar Microsoft Office uygulamalarında bağlantılara tıkladığında bilinen, kötü amaçlı bağlantıların listesini denetler** <br><br> _EnableSafeLinksForO365Clients_|Seçili değil <br><br> `$false`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Desteklenen Office 365 masaüstü ve mobil (iOS ve Android) uygulamalarında Güvenli Bağlantılar'ı kullanın. Daha fazla bilgi için bkz. [Office uygulamaları için Güvenli Bağlantılar ayarları](safe-links.md#safe-links-settings-for-office-apps).|
|**Koruma ayarları'nı tıklatın**||||||
|**Kullanıcı tıklamalarını izleme** <br><br> _TrackUserClicks_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili <br><br> `$true`||
|**Kullanıcıların özgün URL'ye tıklamasına izin ver** <br><br> _AllowClickThrough_|Seçili <br><br> `$true`|Seçili <br><br> `$true`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Bu ayarı kapatmak ( _AllowClickThrough_ `$false`ayarı) özgün URL'ye tıklamayı engeller.|
|**Bildirim ve uyarı sayfalarında kuruluş markasını görüntüleme** <br><br> _EnableOrganizationBranding_|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Seçili değil <br><br> `$false`|Bu ayar için belirli bir önerimiz yok. <br><br> Bu ayarı açmadan önce, Şirketinizin logosunu karşıya yüklemek [için Microsoft 365 temasını özelleştirme](../../admin/setup/customize-your-organization-theme.md) başlığı altında yer alan yönergeleri izlemeniz gerekir.|
|**Bildirim**||||||
|**Kullanıcılarınıza nasıl bildirimde bulunacaksınız?** <br><br> _CustomNotificationText_ <br><br> _UseTranslatedNotificationText_|**Varsayılan bildirim metnini kullanma** <br><br> Boş (`$null`) <br><br> `$false`|**Varsayılan bildirim metnini kullanma** <br><br> Boş (`$null`) <br><br> `$false`|**Varsayılan bildirim metnini kullanma** <br><br> Boş (`$null`) <br><br> `$false`|**Varsayılan bildirim metnini kullanma** <br><br> Boş (`$null`) <br><br> `$false`|Bu ayar için belirli bir önerimiz yok. <br><br> Özelleştirilmiş bildirim metnini girmek ve kullanmak için **Özel bildirim metnini kullan** (`-CustomNotificationText "<Custom text>"`) seçeneğini belirleyebilirsiniz. Özel metin belirtirseniz, metni otomatik olarak kullanıcının diline çevirmek **için Microsoft Translator'ı otomatik yerelleştirme**`-UseTranslatedNotificationText $true` () için kullan'ı da seçebilirsiniz.|

## <a name="related-articles"></a>İlgili makaleler

- **Exchange posta akışı kuralları (taşıma kuralları olarak da bilinir**) için en iyi yöntemleri mi arıyorsunuz? Bkz. [Exchange Online'da posta akışı kurallarını yapılandırmak için en iyi yöntemler](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Yöneticiler ve kullanıcılar yanlış pozitifler (kötü olarak işaretlenmiş iyi e-postalar) ve hatalı negatifler (hatalı e-postaya izin verilir) analiz için Microsoft'a gönderebilir. Daha fazla bilgi için bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md).

- [EOP hizmetinizi](/exchange/standalone-eop/set-up-your-eop-service) **ayarlama** ve [Office 365 için Microsoft Defender](defender-for-office-365.md) **yapılandırma** hakkında bilgi için bu bağlantıları kullanın. 'Office 365 [Tehditlere Karşı Koruma](protect-against-threats.md)' bölümünde yer alan yararlı yönergeleri unutmayın.

- **Windows için güvenlik temelleri** burada bulunabilir: GPO/şirket içi seçenekler için [güvenlik temellerini nereden alabilirim?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) ve [windows cihazlarını Intune tabanlı güvenlik için Intune yapılandırmak için güvenlik temellerini kullanma](/intune/protect/security-baselines). Son olarak, Uç Nokta için Microsoft Defender ile Microsoft Intune güvenlik temelleri arasındaki karşılaştırma[, Uç Nokta için Microsoft Defender ve Windows Intune güvenlik temellerini karşılaştırma](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines) bölümünde sağlanır.
