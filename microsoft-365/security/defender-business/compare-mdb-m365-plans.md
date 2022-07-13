---
title: Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırma
description: İş için Defender, Uç Nokta ve Microsoft 365 İş Ekstra için Defender ile karşılaştırıldığında nasıldır? Şirketiniz için daha bilinçli bir karar vermek için her plana nelerin dahil olduğunu görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: 9c3c4cf2914e268abeabc199e72ef28dac81a0f1
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772006"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırma

Microsoft, küçük ve orta ölçekli işletmelere yönelik planlar da dahil olmak üzere çok çeşitli bulut çözümleri ve hizmetleri sunar. Örneğin[, Microsoft 365 İş Ekstra](../../business/microsoft-365-business-overview.md) güvenlik ve cihaz yönetimi özelliklerinin yanı sıra Office uygulamaları gibi üretkenlik özelliklerini içerir. Bu makalede Microsoft 365 İş Ekstra, İş için Microsoft Defender ve [Uç Nokta için Microsoft Defender](../defender-endpoint/microsoft-defender-endpoint.md) güvenlik özellikleri açıklanmaktadır.


**Aşağıdakiler için bu makaleyi kullanın**:

- [İş için Defender'ı (tek başına) Microsoft 365 İş Ekstra ile karşılaştırın](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium).
- [İş için Defender'ı (tek başına) Uç Nokta için Defender kurumsal teklifleriyle karşılaştırın](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> [!TIP]
> İş için Defender, küçük ve orta ölçekli işletmeler için tek başına bir güvenlik çözümü olarak kullanılabilir. Ayrıca Microsoft 365 İş Ekstra de dahildir. Zaten Microsoft 365 İş Temel veya Standard'ınız varsa, cihazlarınız için daha fazla tehdit koruması özelliği elde etmek için Microsoft 365 İş Ekstra yükseltmeyi veya aboneliğinize İş için Defender'ı eklemeyi göz önünde bulundurun.

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>İş için Microsoft Defender'daki güvenlik özelliklerini Microsoft 365 İş Ekstra ile karşılaştırma

> [!NOTE]
> Bu makalede, İş için Microsoft Defender (tek başına plan olarak) ve Microsoft 365 İş Ekstra (İş için Defender'ı da içerir) dahil edilen tehdit koruma özelliklerine üst düzey bir genel bakış sağlanır. Hizmet açıklaması veya lisans sözleşmesi belgesi olarak tasarlanmamıştır. Daha ayrıntılı bilgi için bkz. [Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

İş için Defender, tek başına abonelik olarak da kullanılabilir ve Microsoft 365 İş Ekstra da dahil edilir. Aşağıdaki tabloda İş için Defender'daki (tek başına) güvenlik özellikleri ve özellikleri Microsoft 365 İş Ekstra ile karşılaştırılıyor.

|Özellik/yetenek|[İş için Microsoft Defender](mdb-overview.md)<br/>(tek başına)|[Microsoft 365 Business Premium](../../business/microsoft-365-business-overview.md)<br/>(İş için Defender'ı içerir)|
|---|---|---|
|Email koruması|Evet <br/>[Microsoft Defender Virüsten Koruma ile Email tarama](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)|Evet <ul><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)</li><li>[Microsoft Defender Virüsten Koruma ile Email tarama](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md)</li></ul>|
|Antispam koruması|Evet<br/>Cihazlar için|Evet <ul><li>Cihazlar için</li><li>İletiler ve ekler gibi Microsoft 365 e-posta içeriği için</li></ul>|
|Kötü amaçlı yazılımdan koruma|Evet<br/>Cihazlar için|Evet<ul><li>Cihazlar için</li><li>İletiler ve ekler gibi Microsoft 365 e-posta içeriği için</li></ul>|
|[Yeni nesil koruma](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/> (virüsten koruma ve kötü amaçlı yazılımdan koruma)|Evet<br/>Microsoft Defender Virüsten Koruma Windows 10 ve sonraki sürümlere dahildir|Evet <ul><li>Microsoft Defender Virüsten Koruma Windows 10 ve sonraki sürümlere dahildir</li><li>Eklenen cihazlar için yeni nesil koruma ilkeleri</li></ul>|
|[Saldırı yüzeyini azaltma](../defender-endpoint/overview-attack-surface-reduction.md) <br/>(Windows 10 veya sonraki sürümlerde ASR kuralları ve güvenlik duvarı koruması)|Evet|Evet|
|[Uç nokta algılama ve yanıt](../defender-endpoint/overview-endpoint-detection-response.md) <br/>(davranış tabanlı algılama ve el ile yanıt eylemleri)|Evet|Evet|
|[Otomatik araştırma ve yanıt](../defender-endpoint/automated-investigations.md)|Evet|Evet|
|[Tehdit ve Güvenlik Açığı Yönetimi](../defender-endpoint/tvm-dashboard-insights.md)|Evet|Evet|
|Merkezi yönetim ve raporlama|Evet|Evet|
|[Apı 'leri](../defender-endpoint/apis-intro.md) <br/>(özel uygulamalar veya raporlama çözümleriyle tümleştirme için)|Evet|Evet|

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>İş için Microsoft Defender Uç Nokta için Microsoft Defender Plan 1 ve 2 ile karşılaştırma

İş için Defender, Uç Nokta için Defender'ın kurumsal sınıf özelliklerini küçük ve orta ölçekli işletmelere getirir. Aşağıdaki tabloda İş için Defender'daki güvenlik özellikleri ve özellikleri plan 1 ve 2 Uç Nokta için Microsoft Defender kurumsal tekliflerle karşılaştırmaktadır.

|Özellik/yetenek|[İş için Defender](mdb-overview.md)<br/>(tek başına)|[Uç Nokta için Defender Plan 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(kurumsal müşteriler için) |[Uç Nokta için Defender Plan 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(kurumsal müşteriler için) |
|---|---|---|---|
|[Merkezi yönetim](../defender-endpoint/manage-atp-post-migration.md) |Evet <sup>[[1](#fn1)]</sup>|Evet|Evet|
|[Basitleştirilmiş istemci yapılandırması](mdb-simplified-configuration.md)|Evet|Hayır|Hayır|
|[Tehdit ve Güvenlik Açığı Yönetimi](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|Evet|Hayır|Evet|
|[Saldırı yüzeyi azaltma özellikleri](../defender-endpoint/overview-attack-surface-reduction.md)|Evet|Evet|Evet|
|[Yeni nesil koruma](../defender-endpoint/next-generation-protection.md)|Evet|Evet|Evet|
|[Uç nokta algılama ve yanıt](../defender-endpoint/overview-endpoint-detection-response.md)|Evet <sup>[[2](#fn2)]</sup>|Hayır|Evet|
|[Otomatik araştırma ve yanıt](../defender-endpoint/automated-investigations.md)|Evet <sup>[[3](#fn3)]</sup>|Hayır|Evet|
|[Tehdit avcılığı](../defender-endpoint/advanced-hunting-overview.md) ve altı aylık veri saklama |Hayır <sup>[[4](#fn4)]</sup>|Hayır|Evet|
|[Tehdit analizi](../defender-endpoint/threat-analytics.md)|Evet <sup>[[5](#fn5)]</sup>|Hayır|Evet|
|[Platformlar arası destek](../defender-endpoint/minimum-requirements.md) <br/>(Windows, Mac, iOS ve Android işletim sistemi)|Evet <sup>[[6](#fn6)]</sup>|Evet|Evet|
|[Microsoft Tehdit Uzmanları](../defender-endpoint/microsoft-threat-experts.md)|Hayır|Hayır|Evet|
|İş Ortağı API'leri|Evet|Evet|Evet|
|[Microsoft 365 Lighthouse tümleştirmesi](../../lighthouse/m365-lighthouse-overview.md) <br/>(Müşteri kiracıları genelinde güvenlik olaylarını görüntülemek için)|Evet |Evet <sup>[[7](#fn7)]</sup>|Evet <sup>[[7](#fn7)]</sup>|

(<a id="fn1">1</a>) Microsoft 365 Defender portalında () veya Microsoft Endpoint Manager yönetim merkezinde ([https://security.microsoft.com](https://security.microsoft.com)[https://endpoint.microsoft.com](https://endpoint.microsoft.com)) yönetilen Microsoft Intune kullanarak cihazları ekleyin ve yönetin.

(<a id="fn2">2</a>) İş için Defender'daki uç nokta algılama ve yanıt (EDR) özellikleri davranış tabanlı algılamayı ve aşağıdaki el ile yanıt eylemlerini içerir: 
- Antivirüs taraması başlat
- Cihazı yalıtma
- Dosyayı durdurma ve karantinaya al
- Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme

(<a id="fn3">3</a>) İş için Defender'da otomatik araştırma ve yanıt varsayılan olarak kiracı genelinde açılır. Otomatik araştırmayı ve yanıtı kapatırsanız, bu gerçek zamanlı korumayı etkiler. Gelişmiş [özellikler için bkz. Ayarları gözden geçirme](mdb-configure-security-settings.md#review-settings-for-advanced-features).  

(<a id="fn4">4</a>) İş için Defender'da zaman çizelgesi görünümü yoktur.

(<a id="fn5">5</a>) İş için Defender'da tehdit analizi, küçük ve orta ölçekli işletmeler için iyileştirilmiştir.

(<a id="fn6">6</a>) Bkz[. cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

(<a id="fn7">7</a>) Uç Nokta için Defender'ı kullanarak kiracılar arasında olayları görüntüleme özelliği yeni!

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender gereksinimlerine bakın](mdb-requirements.md)
- [İş için Microsoft Defender alma](get-defender-business.md)
- [İş için Microsoft Defender ayarlamayı ve yapılandırmayı öğrenin](mdb-setup-configuration.md)
