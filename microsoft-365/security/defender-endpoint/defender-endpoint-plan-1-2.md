---
title: Microsoft uç nokta güvenlik planlarını karşılaştırma
description: Uç Nokta Için Defender Plan 1 gibi Microsoft uç nokta güvenlik planlarını Uç Nokta Için Defender Plan 2 ile karşılaştırın. Planlar arasındaki farklar hakkında bilgi edinin ve kuruluşunuzun gereksinimlerine uygun planı seçin.
keywords: Uç Nokta için Defender, gelişmiş tehdit koruması, uç nokta koruması, uç nokta güvenliği, cihaz güvenliği, siber güvenlik
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 08/09/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: shlomi, efratka
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: f53f86e693a2acc7ac39ec1c7e0b3665df92cb79
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67301189"
---
# <a name="compare-microsoft-endpoint-security-plans"></a>Microsoft uç nokta güvenlik planlarını karşılaştırma

Uç Nokta için Microsoft Defender ve Microsoft 365 Defender gibi Microsoft uç nokta güvenlik planları, kurumsal kuruluşların gelişmiş tehditleri engellemesine, algılamasına, araştırmasına ve yanıtlamasına yardımcı olmak için tasarlanmıştır. İş için Microsoft Defender ve Microsoft 365 İş Ekstra, küçük ve orta ölçekli işletmeler için iyileştirilmiş benzer özellikler sağlar. Bu planlar, merkezi yönetim ve raporlama ile birlikte virüsten koruma ve kötü amaçlı yazılımdan koruma, fidye yazılımı azaltma ve daha fazlası ile gelişmiş tehdit koruması sağlar. 

Bu makale, aşağıdaki planlara nelerin dahil olduğunu netleştirmeye yardımcı olur: 

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [eklentiyi Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md) ve [Microsoft 365 İş Ekstra](../../business-premium/index.md)

> [!IMPORTANT]
> Bu makale, Microsoft uç nokta güvenlik planlarındaki tehdit koruma özelliklerinin özetini sağlar; ancak hizmet açıklaması veya lisans sözleşmesi belgesi olarak tasarlanmamıştır. Daha ayrıntılı bilgi için bkz. [Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="compare-microsoft-endpoint-security-plans"></a>Microsoft uç nokta güvenlik planlarını karşılaştırma

Aşağıdaki tabloda, Microsoft uç nokta güvenlik planlarına dahil edilenler özetlenmiştir.

| Plan | Dahil olanlar |
|:---|:---|
| [Uç Nokta Için Defender Plan 1](defender-endpoint-plan-1.md) <sup>[[1](#fn1)]</sup> | <ul><li>[Yeni nesil koruma](defender-endpoint-plan-1.md#next-generation-protection) (kötü amaçlı yazılımdan koruma ve virüsten koruma içerir)</li><li>[Saldırı yüzeyini azaltma](defender-endpoint-plan-1.md#attack-surface-reduction)</li><li> [El ile yanıt eylemleri](defender-endpoint-plan-1.md#manual-response-actions)</li><li>[Merkezi yönetim](defender-endpoint-plan-1.md#centralized-management)</li><li>[Güvenlik raporları](defender-endpoint-plan-1.md#reporting)</li><li>[Apı 'leri](defender-endpoint-plan-1.md#apis)</li><li>[Windows 10, iOS, Android işletim sistemi ve macOS cihazları için destek](defender-endpoint-plan-1.md#cross-platform-support)</li></ul>|
| [Uç Nokta Için Defender Plan 2](microsoft-defender-endpoint.md) <sup>[[2](#fn2)]</sup> | Uç Nokta için Defender Plan 1 özelliklerinin tümüne ek olarak:<ul><li>[cihaz keşfi](device-discovery.md)</li><li>[Cihaz envanteri](machines-view-overview.md)</li><li>[Core Defender Güvenlik Açığı Yönetimi özellikleri](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md)</li><li>[Tehdit Analizi](threat-analytics.md)</li><li>[Otomatik araştırma ve yanıt](automated-investigations.md)</li><li>[Gelişmiş avcılık örneği](advanced-hunting-overview.md)</li><li>[Uç nokta algılama ve yanıt](overview-endpoint-detection-response.md)</li><li>[Microsoft Tehdit Uzmanları](microsoft-threat-experts.md)</li><li>[Windows](configure-endpoints.md) (istemci ve sunucu) ve [Windows dışı platformlar](configure-endpoints-non-windows.md) (macOS, iOS, Android ve Linux) desteği</li></ul> |
| [Defender Güvenlik Açığı Yönetimi eklentisi](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md) | Uç Nokta Için Defender Plan 2 için diğer Defender Güvenlik Açığı Yönetimi özellikleri:<ul><li>[Güvenlik temelleri değerlendirmesi](../defender-vulnerability-management/tvm-security-baselines.md)</li><li>[Güvenlik açığı bulunan uygulamaları engelleyin](../defender-vulnerability-management/tvm-block-vuln-apps.md)</li><li>[Tarayıcı uzantıları](../defender-vulnerability-management/tvm-browser-extensions.md)</li><li>[Dijital sertifika değerlendirmesi](../defender-vulnerability-management/tvm-certificate-inventory.md)</li><li>[Ağ paylaşımı analizi](../defender-vulnerability-management/tvm-network-share-assessment.md)</li><li>[Windows](configure-endpoints.md) (istemci ve sunucu) ve [Windows dışı platformlar](configure-endpoints-non-windows.md) (macOS, iOS, Android ve Linux) desteği</li></ul> |
| [İş için Defender](../defender-business/mdb-overview.md) <sup>[[3](#fn3)]</sup>  | [Küçük ve orta ölçekli işletmeler için iyileştirilmiş hizmetler](../defender-business/compare-mdb-m365-plans.md) şunlardır: <ul><li>Yeni nesil koruma (kötü amaçlı yazılımdan koruma ve fidye yazılımı koruması dahil)</li><li>Saldırı yüzeyini azaltma</li><li>Uç nokta algılama ve yanıt</li><li>Otomatik araştırma ve yanıt </li><li>Tehdit ve güvenlik açığı yönetimi</li><li>Merkezi raporlama</li><li>API'ler (özel uygulamalar veya raporlama çözümleriyle tümleştirme için)</li><li>[Microsoft 365 Lighthouse ile tümleştirme](../defender-business/mdb-lighthouse-integration.md)</li></ul> |

(<a id="fn1">1</a>) Uç Nokta için Microsoft Defender Plan 1, ticari ve eğitim müşterileri için tek başına abonelik olarak kullanılabilir. Ayrıca Microsoft 365 E3/A3'ün bir parçası olarak da dahildir.

(<a id="fn2">2</a>) daha önce Uç Nokta için Microsoft Defender olarak adlandırılan Uç Nokta için Microsoft Defender Plan 2, tek başına abonelik olarak kullanılabilir. Ayrıca aşağıdaki planların bir parçası olarak da dahildir:

- Windows 11 Enterprise E5/A5
- E5/A5 Windows 10 Enterprise
- Microsoft 365 E5/A5/G5 (Windows 10 veya Windows 11 Enterprise E5 içerir)
- Microsoft 365 E5/A5/G5/F5 Güvenliği
- Microsoft 365 F5 Güvenlik & Uyumluluğu

(<a id="fn3">3</a>) İş için Microsoft Defender küçük ve orta ölçekli işletmeler için tek başına abonelik olarak kullanılabilir. Ayrıca [Microsoft 365 İş Ekstra](/microsoft-365/business-premium) bir parçası olarak da dahildir. Bu planlar, basitleştirilmiş kurulum ve yapılandırma deneyimiyle gelişmiş güvenlik özelliklerine sahiptir. Bkz[. İş için Microsoft Defender Microsoft 365 İş Ekstra ile karşılaştırma](/microsoft-365/security/defender-business/compare-mdb-m365-plans#compare-microsoft-defender-for-business-to-microsoft-365-business-premium).

## <a name="options-for-onboarding-servers"></a>Sunucuları ekleme seçenekleri

Uç Nokta Için Defender Plan 1 ve 2 (tek başına), İş için Defender (tek başına) ve Microsoft 365 İş Ekstra sunucu lisansları içermez. Sunucuları eklemek için aşağıdaki seçeneklerden birini belirleyin:

- [Bulut](/azure/defender-for-cloud/defender-for-cloud-introduction) için Defender teklifinin bir parçası olarak **Sunucular için Microsoft Defender Plan 1 veya Plan 2**. Daha fazla bilgi edinmek için. Bkz [. Sunucular için Microsoft Defender'a genel bakış](/azure/defender-for-cloud/defender-for-servers-introduction).
- Küçük ve orta ölçekli işletmeler için **İş için Microsoft Defender sunucuları (önizleme).** Bkz. [İş için Microsoft Defender sunucuları alma (önizleme)](../defender-business/get-defender-business-servers.md).

## <a name="mixed-licensing-scenarios"></a>Karma lisanslama senaryoları

Kuruluşunuzun Uç Nokta Için Defender Plan 1 ve Uç Nokta Için Defender Plan 2 gibi Microsoft uç nokta güvenlik aboneliklerinin bir karışımını kullandığını varsayalım. **Şu anda en yüksek işlevsel Microsoft uç nokta güvenlik aboneliği kiracınızın deneyimini ayarlar**. Bu örnekte kiracı deneyiminiz tüm kullanıcılar için Uç Nokta Planı 2 için Defender olacaktır.

Ancak, **destek birimine başvurabilir ve kiracı deneyiminiz için geçersiz kılma isteğinde bulunabilirsiniz**. Diğer bir ifadeyle, tüm kullanıcılar için Uç Nokta Planı 1 için Defender deneyimini korumak için bir geçersiz kılma isteyebilirsiniz. 

- Lisanslar ve ürün koşulları hakkında ayrıntılı bilgi için bkz. [Microsoft 365 abonelikleri için lisanslama ve ürün koşulları](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA).
- Desteğe başvurma hakkında bilgi için bkz. [Destek Uç Nokta için Microsoft Defender başvurun](contact-support.md).

> [!TIP]
> Kuruluşunuz küçük veya orta ölçekli bir işletmeyse aşağıdaki makalelere bakın:
> - [İş için Microsoft Defender nedir?](../defender-business/mdb-overview.md)
> - [Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırın](../defender-business/compare-mdb-m365-plans.md).

## <a name="start-a-trial"></a>Deneme sürümü başlatma

- Uç Nokta için Defender'ı denemek [için Uç Nokta için Defender deneme sürümüne kaydolma sayfasına](https://go.microsoft.com/fwlink/p/?LinkID=2168109) gidin.
- Uç Nokta Planı 2 için Defender Microsoft Defender Güvenlik Açığı Yönetimi eklentisini denemek için adresini ziyaret edin[https://aka.ms/AddonPreviewTrial](https://aka.ms/AddonPreviewTrial). 

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Security'yi kullanmaya başlama (deneme teklifleri)](https://www.microsoft.com/security/business/get-started/start-free-trial)
- [Uç Nokta için Microsoft Defender](microsoft-defender-endpoint.md)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md) (küçük ve orta ölçekli işletmeler için uç nokta koruması)
