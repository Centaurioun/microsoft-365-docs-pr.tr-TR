---
title: Office 365 için Microsoft Defender'de düzeltme eylemleri
keywords: AIR, autoIR, Uç Nokta için Microsoft Defender, otomatik, araştırma, yanıt, düzeltme, tehditler, gelişmiş, tehdit, koruma
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Office 365 için Microsoft Defender'da otomatik araştırmanın ardından düzeltme eylemleri hakkında bilgi edinin.
ms.date: 04/30/2021
ms.custom:
- air
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e3a50a2f194c6a82a28082acd8b86fe4b4466301
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630940"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'de düzeltme eylemleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Düzeltme eylemleri

[Office 365 için Microsoft Defender'deki](defender-for-office-365.md) tehdit koruma özellikleri belirli düzeltme eylemlerini içerir. Bu tür düzeltme eylemleri şunları içerebilir:

- E-posta iletilerini veya kümelerini geçici silme
- URL'yi engelle (tıklama zamanı)
- Dış posta iletmeyi kapatma
- Temsilci seçmeyi kapatma

Office 365 için Microsoft Defender düzeltme eylemleri otomatik olarak yapılmaz. Bunun yerine, düzeltme eylemleri yalnızca kuruluşunuzun güvenlik operasyonları ekibi tarafından onaylandığında gerçekleştirilen işlemlerdir.

## <a name="threats-and-remediation-actions"></a>Tehditler ve düzeltme eylemleri

Office 365 için Microsoft Defender çeşitli tehditleri ele almak için düzeltme eylemleri içerir. Otomatik araştırmalarda genellikle gözden geçirilip onaylanması için bir veya daha fazla düzeltme eylemi elde edilir. Bazı durumlarda, otomatik bir araştırma belirli bir düzeltme eylemiyle sonuçlanmaz. Daha fazla araştırma yapmak ve uygun eylemleri yapmak için aşağıdaki tabloda yer alan yönergeleri kullanın.

|Kategori|Tehdit/risk|Düzeltme eylemleri|
|:---|:---|:---|
|E-posta|Malware|E-postayı/kümeyi geçici silme <p> Bir kümedeki birden fazla e-posta iletisi kötü amaçlı yazılım içeriyorsa, küme kötü amaçlı olarak kabul edilir.|
|E-posta|Kötü Amaçlı URL <br> ( [Güvenli Bağlantılar](safe-links.md) tarafından kötü amaçlı bir URL algılandı.)|E-postayı/kümeyi geçici silme <br> URL'yi engelle (tıklama zamanı doğrulaması) <p> Kötü amaçlı URL içeren Email kötü amaçlı olarak kabul edilir.|
|E-posta|Phish|E-postayı/kümeyi geçici silme <p> Bir kümedeki birden fazla e-posta iletisi kimlik avı denemeleri içeriyorsa, tüm küme bir kimlik avı girişimi olarak kabul edilir.|
|E-posta|Zapped kimlik avı <br> (Email iletiler teslim edildi ve ardından [zapped](zero-hour-auto-purge.md) edildi.)|E-postayı/kümeyi geçici silme <p> Raporlarda, zapped iletileri görüntülenebilir. [ZAP'ın bir iletiyi ve SSS'leri taşıyıp taşımadığını görün](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|E-posta|Kullanıcı tarafından [bildirilen](enable-the-report-message-add-in.md) yanıtsız kimlik avı e-postası|[Kullanıcının raporu tarafından tetiklenen otomatik araştırma](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-posta|Birim anomalisi <br> (Son e-posta miktarları eşleşen ölçütler için önceki 7-10 günü aşıyor.)|Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p>Birim anomalisi net bir tehdit değildir, yalnızca son günlerde son 7-10 güne kıyasla daha büyük e-posta hacimlerinin göstergesidir. <p>Yüksek miktarda e-posta olası sorunları gösterebilse de, kötü amaçlı hükümler veya e-posta iletilerinin/kümelerinin el ile gözden geçirilmesi açısından onay gerekir. Bkz [. Teslim edilen şüpheli e-postayı bulma](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|E-posta|Tehdit bulunamadı <br> (Sistem dosyalara, URL'lere veya e-posta kümesi kararlarının analizine dayalı herhangi bir tehdit bulamadı.)|Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p>Araştırma tamamlandıktan sonra bulunan ve [hedeflenen](zero-hour-auto-purge.md) tehditler, araştırmanın sayısal bulgularına yansıtılmaz, ancak bu tür tehditler [Tehdit Gezgini'nde](threat-explorer.md) görüntülenebilir.|
|Kullanıcı|Kullanıcı kötü amaçlı bir URL'ye tıkladı <br> (Bir kullanıcı daha sonra kötü amaçlı olduğu belirlenen bir sayfaya gider veya bir kullanıcı kötü amaçlı bir [sayfaya ulaşmak için Güvenli Bağlantılar uyarı sayfasını](safe-links.md#warning-pages-from-safe-links) atlar.)|Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p> URL'yi engelle (tıklama zamanı) <p> [URL'ler hakkındaki verileri görüntülemek ve kararlara tıklamak](threat-explorer.md#view-phishing-url-and-click-verdict-data) için Tehdit Gezgini'ni kullanın. <p> Kuruluşunuz [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/) kullanıyorsa, hesabının gizliliğinin ihlal edilmiş olup olmadığını belirlemek için [kullanıcıyı araştırmayı](/microsoft-365/security/defender-endpoint/investigate-user) göz önünde bulundurun.|
|Kullanıcı|Kullanıcı kötü amaçlı yazılım/kimlik avı gönderiyor|Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p> Kullanıcı kötü amaçlı yazılım/kimlik avı bildiriyor veya birisi bir saldırının parçası olarak [kullanıcıyı aldatıyor](anti-spoofing-protection.md) olabilir. [Kötü amaçlı yazılım](threat-explorer-views.md#email--malware) veya [kimlik avı](threat-explorer-views.md#email--phish) içeren e-postaları görüntülemek ve işlemek için [Tehdit Gezgini'ni](threat-explorer.md) kullanın.|
|Kullanıcı|Email iletme <br> (Posta kutusu iletme kuralları yapılandırıldı, chch veri sızdırma için kullanılabilir.)|İletme kuralını kaldırma <p> İletilen e-posta hakkında daha ayrıntılı bilgi görüntülemek için [Otomatik olarak yönlendirilen iletiler raporu](mfi-auto-forwarded-messages-report.md) da dahil olmak üzere posta [akışı içgörülerini](mail-flow-insights-v2.md) kullanın.|
|Kullanıcı|temsilci seçme kurallarını Email <br> (Kullanıcının hesabında temsilciler ayarlanmıştır.)|Temsilci seçme kuralını kaldırma <p> Kuruluşunuz [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/) kullanıyorsa temsilci iznini alan [kullanıcıyı araştırmayı](/microsoft-365/security/defender-endpoint/investigate-user) göz önünde bulundurun.|
|Kullanıcı|Veri sızdırma <br> (Kullanıcı e-posta veya dosya paylaşımı [DLP ilkelerini](../../compliance/dlp-learn-about-dlp.md) ihlal etti |Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p> [DLP raporlarını görüntüleyin ve işlem yapın](../../compliance/view-the-dlp-reports.md).|
|Kullanıcı|Anormal e-posta gönderme <br> (Bir kullanıcı yakın zamanda önceki 7-10 güne göre daha fazla e-posta gönderdi.)|Otomatik araştırma belirli bir bekleyen eylemle sonuçlanmaz. <p> Büyük miktarda e-posta göndermek tek başına kötü amaçlı değildir; kullanıcı yalnızca bir olay için büyük bir alıcı grubuna e-posta göndermiş olabilir. Araştırmak için, posta akışı [harita raporu](mfi-mail-flow-map-report.md) da dahil olmak üzere posta akışı [içgörülerini](mail-flow-insights-v2.md) kullanarak neler olduğunu belirleyin ve işlem yapın.|

## <a name="next-steps"></a>Sonraki adımlar

- [otomatik araştırmanın ayrıntılarını ve sonuçlarını Office 365 için Microsoft Defender](air-view-investigation-results.md)
- [Office 365 için Microsoft Defender'da otomatik bir araştırmanın ardından bekleyen veya tamamlanmış düzeltme eylemlerini görüntüleme](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>İlgili makaleler

- [Uç Nokta için Microsoft Defender'de otomatik araştırma hakkında bilgi edinin](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft 365 Defender'deki özellikler hakkında bilgi edinin](/microsoft-365/security/defender/microsoft-365-defender)
