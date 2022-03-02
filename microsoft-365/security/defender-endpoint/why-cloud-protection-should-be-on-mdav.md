---
title: Bulut korumasının etkin olması için neden Microsoft Defender Virüsten Koruma
description: Daha fazla bilgi için bulut korumasının neden açık Microsoft Defender Virüsten Koruma. Uç nokta çalışması için Microsoft Defender'da birçok güvenlik özelliğine yardımcı olur
keywords: Microsoft Defender Virüsten Koruma, bulut koruması, güvenlik özellikleri, örnek gönderim
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/22/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 0dc1279f59ac272031067c415354f1f615ead205
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/27/2022
ms.locfileid: "63010006"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>Bulut korumasının etkin olması için neden Microsoft Defender Virüsten Koruma

**Aşağıdakiler için geçerlidir:**

- [Uç Nokta Planı 1 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta Planı 2 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

Microsoft Defender Virüsten Koruma koruma, uç noktalarınız ve ağ genelinde kötü amaçlı yazılımlara karşı korunmanıza yardımcı olur. Bulut korumasını açık tutmayı öneririz, çünkü Uç Nokta için Microsoft Defender'daki bazı güvenlik özellikleri ve özellikleri yalnızca bulut koruması etkinleştirildiğinde çalışır. 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="Bulut korumasına bağlı şeyleri gösteren diyagram":::](enable-cloud-protection-microsoft-defender-antivirus.md)

Aşağıdaki tabloda, bulut korumasına bağlı özellik ve özellikler özetlenmiştir: <br/><br/>

| Özellik/Özellik  | Abonelik gereksinimi |  Açıklama  |
|---------|---------|--------|
| Buluttaki meta verileri denetleme  | Uç Nokta Plan 1 veya Plan 2 için Microsoft Defender (Tek başına veya Microsoft 365 E3 E5 gibi bir plana dahil) | Bulut Microsoft Defender Virüsten Koruma, makine öğrenme modellerini fazladan bir savunma katmanı olarak kullanır. Bu makine öğrenme modelleri meta verileri içerir, dolayısıyla şüpheli veya kötü amaçlı bir dosya algılandığında meta verileri denetlenir. <br/><br/>Daha fazla bilgi edinmek [için bkz. Blog:](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/) Yeni nesil koruma uç nokta için Microsoft Defender'ın temel noktasını kullanarak gelişmiş teknolojileri öğrenin  |
| Bulut koruması ve örnek gönderim | Uç Nokta Plan 1 veya Plan 2 için Microsoft Defender (Tek başına veya Microsoft 365 E3 E5 gibi bir plana dahil) | Dosyalar ve yürütülebilir dosyalar, Microsoft Defender Virüsten Koruma ve analiz için dosya bulut hizmetine gönderebilirsiniz. <br/><br/>Daha fazla bilgi edinmek için bkz[. Buluttan koruma ve örnek gönderim Microsoft Defender Virüsten Koruma](cloud-protection-microsoft-antivirus-sample-submission.md).<br/><br/>**NOT**: Otomatik örnek gönderim bulut korumasına dayandır, ancak tek başına bir ayar olarak da yalıtabilirsiniz.         |
| Tamper protection | Uç Nokta Plan 2 için Microsoft Defender (Tek başına veya uygulama gibi bir plana Microsoft 365 E5) | Tamper protection, ayarlarınızın istenmeyen değişikliklere karşı korunmasına yardımcı olur. Portalda değişiklik korumasının zorunlu Microsoft 365 Defender için bulut korumasının etkinleştirilmiş olması gerekir. <br/><br/>Daha fazla bilgi edinmek için bkz [. Koruma koruma ile güvenlik ayarlarını koruma](prevent-changes-to-security-settings-with-tamper-protection.md).        |
| İlk görüşte engelle | Uç Nokta Plan 1 veya Plan 2 için Microsoft Defender (Tek başına veya Microsoft 365 E3 E5 gibi bir plana dahil) | İlk görüşte engelle yeni kötü amaçlı yazılımı saniyeler içinde algılar ve engeller. Şüpheli veya kötü amaçlı bir dosya algılandığında, ilk görüşte engellenmiş özellik, bulut koruma arka uçlarını sorgular ve bunun bir tehdit olup olmadığını belirlemek için dosyanın heuristics, makine öğrenimi ve otomatik çözümlemelerini uygular.<br/><br/>Daha fazla bilgi edinmek için bkz [. "İlk görüşte blok" nedir?](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| Acil durum imza güncelleştirmeleri | Uç Nokta Plan 2 için Microsoft Defender (Tek başına veya uygulama gibi bir plana Microsoft 365 E5) | Kötü amaçlı içerik algılandığında, acil durum imza güncelleştirmeleri ve düzeltmeleri dağıtılır. Gelecek normal güncelleştirmeyi beklemek yerine, bu düzeltmeleri ve güncelleştirmeleri dakikalar içinde alırsınız.   |
| Engelleme modunda uç nokta algılama EDR yanıt (EDR) | Uç Nokta Plan 2 için Microsoft Defender (Tek başına veya uygulama gibi bir plana Microsoft 365 E5) | EDR modundayken e-Microsoft Defender Virüsten Koruma, cihazda birincil virüsten koruma ürünü değilken fazladan koruma sağlar. EDR modundaki düzeltmeler, Microsoft olmayan birincil virüsten koruma çözümünün atlemiş EDR taramaları sırasında bulunan yapıları düzelter. Birincil virüsten koruma çözümü Microsoft Defender Virüsten Koruma olan cihazlar için etkinleştirildiğinde, engelleme modundaki EDR, önceden oluşturulan taramalar sırasında tanımlanan yapıları otomatik olarak düzeltmenin EDR avantajını sağlar. <br/><br/>Daha fazla bilgi için bkz[. EDR modunda çalışma](edr-in-block-mode.md).|
| Saldırı yüzeyini azaltma kuralları | Uç Nokta Plan 1 veya Plan 2 için Microsoft Defender (Tek başına veya Microsoft 365 E3 E5 gibi bir plana dahil) | Saldırı yüzeyini azaltma, kuruluş uç noktalarının siber saldırılara karşı açık olduğu yerleri ve yöntemleri azaltmayı içerir. Saldırı yüzeyini azaltma kuralları, kötü amaçlı yazılımı durdurmanıza yardımcı olmak için yapılandırılan akıllı kurallardır. Bazı kuralların tam çalışması için bulut korumasının açık olması gerekir. Bu kurallar şunlardır: <br/>- Yürütülebilir dosyaların bir yaygınlık, yaş veya güvenilir liste ölçütlerine uygun olmadığı sürece çalıştırılabilir <br/>- Fidye yazılımlarına karşı gelişmiş koruma kullanın <br/>- Güvenilmeyen programların çıkarılabilir sürücülerden çalıştırmalarını engelleme <br/><br/>Daha fazla bilgi edinmek için bkz [. Kötü amaçlı yazılım bulaşmasını önlemek için saldırı yüzeyi azaltma kurallarını kullanma](attack-surface-reduction.md).  |
| Güvenlik göstergeleri (IOC) | Uç Nokta Plan 2 için Microsoft Defender (Tek başına veya uygulama gibi bir plana Microsoft 365 E5) | Uç Nokta için Defender'daki IoC'ler varlıkları algılama, önleme ve dışlama olarak tanımlamak üzere yalıtıldı. Örneğin, Uç Nokta için Defender'da tarama ve düzeltme eylemlerini Microsoft Defender Virüsten Koruma özel durumları tanımlamak için "izin ver" göstergeleri kullanılabilir. Başka bir örnek olarak, dosya veya işlemlerin yürütülmesini önlemek ve bu etkinlikleri portalda değiştirilebilir uyarılarla izlemek için "uyarı ve engelleme" Microsoft 365 Defender kullanılabilir. <br/><br/>Daha fazla bilgi edinmek için bkz [. Gösterge oluşturma](manage-indicators.md).    |

> [!TIP]
> Uç nokta planları için Defender hakkında daha fazla bilgi edinmek için bkz. Uç Nokta [Planı 1 için Microsoft Defender ve Plan 2](defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Sonraki adımlar

Artık bulut korumasına ve bu korumanın Buluttaki rolüne genel bir bakış Microsoft Defender Virüsten Koruma, aşağıdaki adımları izleyin:

1. **[Bulut korumasını etkinleştirin](enable-cloud-protection-microsoft-defender-antivirus.md)**. Microsoft Endpoint Manager (şu anda Microsoft Endpoint Configuration Manager ve Microsoft Intune içerir), Grup İlkesi veya PowerShell cmdlet'leriyle bulut korumasını etkinleştirabilirsiniz.

2. **[Bulut koruma düzeyini belirtin](specify-cloud-protection-level-microsoft-defender-antivirus.md)**. Bulut tarafından sunulan koruma düzeyini, Grup İlkesi'ne veya Microsoft Endpoint Manager belirtabilirsiniz. Koruma düzeyi, bulutla paylaşılan bilgi miktarını ve yeni dosyaların ne kadar saldırgan bir şekilde engellenmiş olduğunu etkiler.

3. **[İş için ağ bağlantılarını yapılandırma ve Microsoft Defender Virüsten Koruma](configure-network-connections-microsoft-defender-antivirus.md)**. Bulut korumasının etkili bir şekilde çalışması için ağ ve uç noktalarınıza bağlanabilecek bazı Microsoft URL'leri vardır. Bu makalede güvenlik duvarı veya ağ filtreleme kuralları aracılığıyla izin verilen URL'lerin ve ağ korumasını doğrulama yönergelerinin bulut korumasına düzgün bir şekilde kaydedilir.

4. **["birinci görüşte blok" özelliğini yapılandırabilirsiniz](configure-block-at-first-sight-microsoft-defender-antivirus.md)**. "İlk görüşte engelle" özelliği, geleneksel Güvenlik zekası için saatler beklemek zorunda kalmadan yeni kötü amaçlı yazılımları saniyeler içinde engelleyebilir. Grup İlkesi veya Grup İlkesi'Microsoft Endpoint Manager etkinleştirerek ve yapılandırarak.

5. **[Bulut engelleme zaman aşımı dönemini yapılandırabilirsiniz](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)**. Microsoft Defender Virüsten Koruma koruma hizmetimizi sorgularken şüpheli dosyaların çalışanlarını engelleyebilir. Grup İlkesi veya Grup İlkesi kullanarak dosyanın çalıştırılamayacak Microsoft Endpoint Manager yapılandırabilirsiniz.