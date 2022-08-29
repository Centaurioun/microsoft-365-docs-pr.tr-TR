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
ms.openlocfilehash: 4cb0ca9f318041bb209fedf567baa5987e39b61a
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67343078"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırma

Microsoft, küçük ve orta ölçekli işletmelere yönelik planlar da dahil olmak üzere çok çeşitli bulut çözümleri ve hizmetleri sunar. Örneğin[, Microsoft 365 İş Ekstra](../../business/microsoft-365-business-overview.md) güvenlik ve cihaz yönetimi özelliklerinin yanı sıra Office uygulamaları gibi üretkenlik özelliklerini içerir. Bu makalede Microsoft 365 İş Ekstra, İş için Microsoft Defender ve [Uç Nokta için Microsoft Defender](../defender-endpoint/microsoft-defender-endpoint.md) güvenlik özellikleri açıklanmaktadır.


**Aşağıdakiler için bu makaleyi kullanın**:

- [İş için Microsoft Defender ile Microsoft 365 İş Ekstra karşılaştırın](#compare-microsoft-defender-for-business-to-microsoft-365-business-premium).
- [İş için Defender'ı (tek başına) Uç Nokta için Defender kurumsal teklifleriyle karşılaştırın](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> [!TIP]
> İş için Defender, küçük ve orta ölçekli işletmeler için tek başına bir güvenlik çözümü olarak kullanılabilir. İş için Defender artık Microsoft 365 İş Ekstra'a dahil edilir. Zaten Microsoft 365 İş Temel veya Standard'ınız varsa, cihazlarınız için daha fazla tehdit koruması özelliği elde etmek için Microsoft 365 İş Ekstra yükseltmeyi veya geçerli aboneliğinize İş için Defender'ı eklemeyi göz önünde bulundurun.

## <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>İş için Microsoft Defender Microsoft 365 İş Ekstra ile karşılaştırma

> [!NOTE]
> Bu makalede, İş için Microsoft Defender (tek başına plan olarak) ve Microsoft 365 İş Ekstra (İş için Defender'ı içerir) dahil edilen özelliklere ve özelliklere üst düzey bir genel bakış sağlanır. Hizmet açıklaması veya lisans sözleşmesi belgesi olarak tasarlanmamıştır. Daha ayrıntılı bilgi için bkz. [Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

| İş için Microsoft Defender (tek başına) | Microsoft 365 Business Premium |
|:---|:---|
| Cihazlar için virüsten koruma, kötü amaçlı yazılımdan koruma ve fidye yazılımı koruma özellikleri şunlardır: <ul><li>[Yeni nesil koruma](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) (bulut koruması ile birlikte cihazlarda virüsten koruma/kötü amaçlı yazılımdan koruma)</li><li>[Saldırı yüzeyini azaltma](../defender-endpoint/overview-attack-surface-reduction.md) (ağ koruması, güvenlik duvarı ve saldırı yüzeyi azaltma kuralları) <sup>[[a](#fna)]</sup></li><li>[Uç nokta algılama ve yanıt](../defender-endpoint/overview-endpoint-detection-response.md) (davranış tabanlı algılama ve el ile yanıt eylemleri)</li><li>[Otomatik araştırma ve yanıt](../defender/m365d-autoir.md) (algılanan tehditler için kendi kendini düzeltme ile)</li><li>[Microsoft Defender Güvenlik Açığı Yönetimi](mdb-view-tvm-dashboard.md) (kullanıma sunulan cihazları ve önerileri görüntüleme)</li><li>Cihazlar (Windows, Mac, iOS ve Android) [için platformlar arası destek](mdb-onboard-devices.md) <sup>[[b](#fnb)]</sup></li><li>[Merkezi yönetim ve raporlama](mdb-get-started.md) (Microsoft 365 Defender portalı)</li><li>[Tümleştirme api'leri](../defender-endpoint/management-apis.md) (Microsoft iş ortakları veya özel araçlarınız ve uygulamalarınız için)</li></ul><br/><br/><br/><br/><br/><br/><br/> | Üretkenlik ve güvenlik özellikleri şunlardır:<ul><li>[Microsoft 365 İş Standart](../../admin/admin-overview/what-is-microsoft-365-for-business.md) (Office uygulamaları ve hizmetleri ve Microsoft Teams)</li><li>[Paylaşılan bilgisayar etkinleştirmesi](/deployoffice/overview-shared-computer-activation) (Microsoft 365 Uygulamaları dağıtmak için)</li><li>[Windows 10/11 İş](../../business-premium/m365bp-upgrade-windows-10-pro.md) (Windows Pro'nun önceki sürümlerinden yükseltme)</li><li>[Windows Autopilot](/mem/autopilot/windows-autopilot) (Windows cihazlarını ayarlama ve yapılandırma için)</li><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) (e-posta için antiphishing, antispam, antimalware ve sahtekarlık zekası)</li><li>[İş için Defender](mdb-overview.md) ("İş için Defender (tek başına)" sütununda listelenen her şey) </li><li>[Office 365 için Microsoft Defender Plan 1](../office-365-security/overview.md) (gelişmiş antiphishing, gerçek zamanlı algılamalar, Güvenli Ekler, Güvenli Bağlantılar)</li><li>[Arşivlemeyi otomatik genişletme](../../compliance/autoexpanding-archiving.md) (e-posta için)</li><li>[Azure Active Directory Premium Plan 1](/azure/active-directory/fundamentals/active-directory-whatis) (kimlik yönetimi)</li><li>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (cihaz ekleme ve yönetim)</li><li>[Azure Information Protection Premium Plan 1](/azure/information-protection/what-is-information-protection) (hassas bilgiler için koruma)</li><li>[Azure Sanal Masaüstü](/azure/virtual-desktop/overview) (bulutta merkezi olarak yönetilen, güvenli sanal makineler)</li></ul> |

(<a id="fna">a</a>) saldırı yüzeyi azaltma kurallarını değiştirmek veya özelleştirmek için Microsoft Intune gereklidir. Intune Microsoft 365 İş Ekstra dahildir.

(<a id="fnb">b</a>) iOS ve Android cihazları eklemek için Microsoft Intune gereklidir. Bkz[. cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>İş için Microsoft Defender Uç Nokta için Microsoft Defender Plan 1 ve 2 ile karşılaştırma

İş için Defender, Uç Nokta için Defender'ın kurumsal sınıf özelliklerini küçük ve orta ölçekli işletmelere getirir. Aşağıdaki tabloda İş için Defender'daki güvenlik özellikleri ve özellikleri plan 1 ve 2 Uç Nokta için Microsoft Defender kurumsal tekliflerle karşılaştırmaktadır.

|Özellik/yetenek|[İş için Defender](mdb-overview.md)<br/>(tek başına)|[Uç Nokta için Defender Plan 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(kurumsal müşteriler için) |[Uç Nokta için Defender Plan 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(kurumsal müşteriler için) |
|---|---|---|---|
|[Merkezi yönetim](../defender-endpoint/manage-atp-post-migration.md) |Evet <sup>[[1](#fn1)]</sup>|Evet|Evet|
|[Basitleştirilmiş istemci yapılandırması](mdb-simplified-configuration.md)|Evet|Hayır|Hayır|
|[Microsoft Defender Güvenlik Açığı Yönetimi](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|Evet|Hayır|Evet|
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

Ayrıca bkz. [Microsoft uç nokta güvenlik planlarını karşılaştırma](../defender-endpoint/defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender gereksinimlerine bakın](mdb-requirements.md)
- [İş için Microsoft Defender alma](get-defender-business.md)
- [İş için Microsoft Defender ayarlamayı ve yapılandırmayı öğrenin](mdb-setup-configuration.md)
