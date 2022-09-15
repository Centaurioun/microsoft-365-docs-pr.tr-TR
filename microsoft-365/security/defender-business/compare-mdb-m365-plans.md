---
title: Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırma
description: İş için Defender, Uç Nokta ve Microsoft 365 İş Ekstra için Defender ile karşılaştırıldığında nasıldır? Şirketiniz için daha bilinçli bir karar vermek için her plana nelerin dahil olduğunu görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/30/2022
ms.reviewer: shlomiakirav
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
f1.keywords: NOCSH
ms.openlocfilehash: fb43a239584ea2439b6f5c1042675cf81e4b8adc
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67710971"
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

| Plan | Açıklama |
|:---|:---|
| **[İş için Defender](mdb-overview.md)** (tek başına) | **Cihazlar için virüsten koruma, kötü amaçlı yazılımdan koruma ve fidye yazılımı koruması**<ul><li>[Yeni nesil koruma](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) (bulut koruması ile birlikte cihazlarda virüsten koruma/kötü amaçlı yazılımdan koruma)</li><li>[Saldırı yüzeyini azaltma](../defender-endpoint/overview-attack-surface-reduction.md) (ağ koruması, güvenlik duvarı ve saldırı yüzeyi azaltma kuralları) <sup>[[a](#fna)]</sup></li><li>[Uç nokta algılama ve yanıt](../defender-endpoint/overview-endpoint-detection-response.md) (davranış tabanlı algılama ve el ile yanıt eylemleri)</li><li>[Otomatik araştırma ve yanıt](../defender/m365d-autoir.md) (algılanan tehditler için kendi kendini düzeltme ile)</li><li>[Microsoft Defender Güvenlik Açığı Yönetimi](mdb-view-tvm-dashboard.md) (kullanıma sunulan cihazları ve önerileri görüntüleme)</li><li>Cihazlar (Windows, Mac, iOS ve Android) [için platformlar arası destek](mdb-onboard-devices.md) <sup>[[b](#fnb)]</sup></li><li>[Merkezi yönetim ve raporlama](mdb-get-started.md) (Microsoft 365 Defender portalı)</li><li>[Tümleştirme api'leri](../defender-endpoint/management-apis.md) (Microsoft iş ortakları veya özel araçlarınız ve uygulamalarınız için)</li></ul> |
| **[Microsoft 365 Business Premium](../../business-premium/index.md)** | **Üretkenlik ve ek güvenlik özellikleriyle birlikte İş için Defender özellikleri**<ul><li>[Microsoft 365 İş Standart](../../admin/admin-overview/what-is-microsoft-365-for-business.md) (Office uygulamaları ve hizmetleri ve Microsoft Teams)</li><li>[Paylaşılan bilgisayar etkinleştirmesi](/deployoffice/overview-shared-computer-activation) (Microsoft 365 Uygulamaları dağıtmak için)</li><li>[Windows 10/11 İş](../../business-premium/m365bp-upgrade-windows-10-pro.md) (Windows Pro'nun önceki sürümlerinden yükseltme)</li><li>[Windows Autopilot](/mem/autopilot/windows-autopilot) (Windows cihazlarını ayarlama ve yapılandırma için)</li><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) (e-posta için antiphishing, antispam, antimalware ve sahtekarlık zekası)</li><li>[Office 365 için Microsoft Defender Plan 1](../office-365-security/overview.md) (gelişmiş antiphishing, gerçek zamanlı algılamalar, Güvenli Ekler, Güvenli Bağlantılar)</li><li>[Arşivlemeyi otomatik genişletme](../../compliance/autoexpanding-archiving.md) (e-posta için)</li><li>[Azure Active Directory Premium Plan 1](/azure/active-directory/fundamentals/active-directory-whatis) (kimlik yönetimi)</li><li>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (cihaz ekleme ve yönetim)</li><li>[Azure Information Protection Premium Plan 1](/azure/information-protection/what-is-information-protection) (hassas bilgiler için koruma)</li><li>[Azure Sanal Masaüstü](/azure/virtual-desktop/overview) (bulutta merkezi olarak yönetilen, güvenli sanal makineler)</li></ul> |

  
(<a id="fna">a</a>) saldırı yüzeyi azaltma kurallarını değiştirmek veya özelleştirmek için Microsoft Intune gereklidir. Intune, İş için Defender'ın tek başına sürümüne eklenebilir. Intune Microsoft 365 İş Ekstra dahildir.

(<a id="fnb">b</a>) iOS ve Android cihazları eklemek için Microsoft Intune gereklidir. Bkz[. cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>İş için Microsoft Defender Uç Nokta için Microsoft Defender Plan 1 ve 2 ile karşılaştırma

İş için Defender, Uç Nokta için Defender'ın kurumsal sınıf özelliklerini küçük ve orta ölçekli işletmelere getirir. Aşağıdaki tabloda İş için Defender'daki güvenlik özellikleri ve özellikleri plan 1 ve 2 Uç Nokta için Microsoft Defender kurumsal tekliflerle karşılaştırmaktadır.

|Özellik/yetenek|[İş için Defender](mdb-overview.md)<br/>(tek başına)|[Uç Nokta için Defender Plan 1](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(kurumsal müşteriler için) |[Uç Nokta için Defender Plan 2](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(kurumsal müşteriler için) |
|---|---|---|---|
|[Merkezi yönetim](../defender-endpoint/manage-atp-post-migration.md) <sup>[[1](#fn1)]</sup> | :::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Basitleştirilmiş istemci yapılandırması](mdb-simplified-configuration.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::| | |
|[Microsoft Defender Güvenlik Açığı Yönetimi](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::| |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Saldırı yüzeyi azaltma özellikleri](../defender-endpoint/overview-attack-surface-reduction.md) <sup>[[2](#fn2)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Yeni nesil koruma](../defender-endpoint/next-generation-protection.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Uç nokta algılama ve yanıt](../defender-endpoint/overview-endpoint-detection-response.md) <sup>[[3](#fn3)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Otomatik araştırma ve yanıt](../defender-endpoint/automated-investigations.md) <sup>[[4](#fn4)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: ||:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Tehdit avcılığı](../defender-endpoint/advanced-hunting-overview.md) ve altı aylık veri saklama <sup>[[5](#fn5)]</sup> | | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Tehdit analizi](../defender-endpoint/threat-analytics.md) <sup>[[6](#fn6)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Platformlar arası destek](../defender-endpoint/minimum-requirements.md) <br/>(Windows, Mac, iOS ve Android işletim sistemi) <sup>[[7](#fn7)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Microsoft Tehdit Uzmanları](../defender-endpoint/microsoft-threat-experts.md)| | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|İş Ortağı API'leri|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil":::|
|[Microsoft 365 Lighthouse tümleştirmesi](../../lighthouse/m365-lighthouse-overview.md) <br/>(Müşteri kiracıları genelinde güvenlik olaylarını görüntülemek için) <sup>[[8](#fn8)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Dahil"::: |

(<a id="fn1">1</a>) Microsoft 365 Defender portalında () veya Microsoft Endpoint Manager yönetim merkezinde ([https://security.microsoft.com](https://security.microsoft.com)[https://endpoint.microsoft.com](https://endpoint.microsoft.com)) yönetilen Microsoft Intune kullanarak cihazları ekleyin ve yönetin.

(<a id="fn2">2</a>) [ASR kurallarını](../defender-endpoint/attack-surface-reduction.md) yapılandırmak ve yönetmek için Intune gereklidir.

(<a id="fn3">3</a>) İş için Defender'daki uç nokta algılama ve yanıt (EDR) özellikleri davranış tabanlı algılamayı ve aşağıdaki el ile yanıt eylemlerini içerir: 
- Antivirüs taraması başlat
- Cihazı yalıtma
- Dosyayı durdurma ve karantinaya al
- Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme

(<a id="fn4">4</a>) İş için Defender'da otomatik araştırma ve yanıt varsayılan olarak kiracı genelinde açılır. Otomatik araştırmanın ve yanıtın kapatılması gerçek zamanlı korumayı etkiler. Gelişmiş [özellikler için bkz. Ayarları gözden geçirme](mdb-configure-security-settings.md#review-settings-for-advanced-features).  

(<a id="fn5">5</a>) İş için Defender'da zaman çizelgesi görünümü yoktur.

(<a id="fn6">6</a>) İş için Defender'da tehdit analizi, küçük ve orta ölçekli işletmeler için iyileştirilmiştir.

(<a id="fn7">7</a>) Bkz. [cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

(<a id="fn8">8</a>) Uç Nokta için Defender'ı kullanarak kiracılar arasında olayları görüntüleme özelliği yeni!

> [!TIP]
> Ayrıca bkz. [Microsoft uç nokta güvenlik planlarını karşılaştırma](../defender-endpoint/defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Microsoft Defender gereksinimlerine bakın](mdb-requirements.md)
- [İş için Microsoft Defender alma](get-defender-business.md)
- [İş için Microsoft Defender ayarlamayı ve yapılandırmayı öğrenin](mdb-setup-configuration.md)
