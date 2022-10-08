---
title: Yerleşik koruma fidye yazılımlarından korunmaya yardımcı olur
description: Yerleşik korumanın Uç Nokta için Microsoft Defender bir parçası olarak fidye yazılımlarına karşı nasıl koruma sağdiğini öğrenin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 09/21/2022
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.collection:
- m365-security
- tier2
ms.custom: ''
ms.reviewer: joshbregman
f1.keywords: NOCSH
ms.openlocfilehash: 3a69a91b647bc5b94e11dd086314c05c67e5fd7f
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68151661"
---
# <a name="built-in-protection-helps-guard-against-ransomware"></a>Yerleşik koruma fidye yazılımlarından korunmaya yardımcı olur

[Uç Nokta için Microsoft Defender](microsoft-defender-endpoint.md) fidye yazılımı saldırıları gibi gelişmiş tehditleri önlemeye, algılamaya, araştırmaya ve yanıtlamaya yardımcı olur. Uç Nokta için Defender'daki [yeni nesil koruma](next-generation-protection.md) ve [saldırı yüzeyi azaltma](overview-attack-surface-reduction.md) özellikleri, ortaya çıkan tehditleri yakalamak için tasarlanmıştır. Fidye yazılımlarından ve diğer siber tehditlerden en iyi korumanın uygulanabilmesi için belirli ayarların yapılandırılması gerekir. Yerleşik koruma, daha iyi koruma için varsayılan ayarları sağlayarak size yardımcı olabilir.

> [!TIP]
> **Yerleşik korumanın size gelmesini beklemek zorunda değilsiniz**! Şu özellikleri yapılandırarak kuruluşunuzun cihazlarını koruyabilirsiniz:
> - [Bulut korumasını etkinleştirme](why-cloud-protection-should-be-on-mdav.md)
> - [Kurcalama korumasını açma](prevent-changes-to-security-settings-with-tamper-protection.md)
> - [Temel saldırı yüzeyi azaltma kurallarını blok moduna ayarlama](attack-surface-reduction-rules-deployment.md)
> - [Blok modunda ağ korumasını etkinleştirme](enable-network-protection.md)

## <a name="what-is-built-in-protection-and-how-does-it-work"></a>Yerleşik koruma nedir ve nasıl çalışır?

Yerleşik koruma, cihazlarınızın korunduğundan emin olmak için kullanıma sunulan bir dizi varsayılan ayardır. Bu varsayılan ayarlar, cihazları fidye yazılımlarına ve diğer tehditlere karşı korumak için tasarlanmıştır. Başlangıçta, yerleşik koruma kiracınız için [kurcalama korumasını](prevent-changes-to-security-settings-with-tamper-protection.md) açmayı içerir ve diğer varsayılan ayarlar yakında kullanıma sunulacaktır. Daha fazla bilgi için Teknik Topluluk blog gönderisine bakın. [Tüm kurumsal müşteriler için kurcalama koruması açılacaktır](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-will-be-turned-on-for-all-enterprise-customers/ba-p/3616478).

| Aşama | Neler olur? |
|:---|:---|
| Yerleşik koruma [önizlemede](preview.md) kullanıma sunuldu | Önizleme özelliklerini almayı tercih eden müşteriler, yerleşik korumanın geldiğini [bildiren bir bildirim](#what-does-the-notification-look-like) alır. Henüz yapılandırılmamışsa, Uç Nokta için Defender Plan 2 veya Microsoft 365 E5 sahip müşteriler için kurcalama koruması açılır. |
| Yerleşik koruma kiracınız için kullanılabilir hale gelir | Kiracınızın yerleşik korumayı almak üzere olduğu ve kurcalama korumasının ne zaman açılacağı (henüz yapılandırılmamışsa) [size bildirilir](#what-does-the-notification-look-like) . |
| Yerleşik koruma geliyor | Kiracınız için kurcalama koruması açılır ve kuruluşunuzun Windows cihazlarına uygulanır. [Yerleşik koruma ayarlarınızı](#can-i-change-built-in-protection-settings) [geri çevirebilir](#can-i-opt-out) veya değiştirebilirsiniz. |
| Yerleşik koruma geldikten sonra | Uç Nokta için Defender'a yeni cihazlar ekli olduğunda, yerleşik koruma ayarları Windows çalıştıran tüm yeni cihazlara uygulanır. [Yerleşik koruma ayarlarınızı istediğiniz zaman değiştirebilirsiniz](#can-i-change-built-in-protection-settings). |

> [!NOTE]
> Yerleşik koruma, Windows cihazları için varsayılan değerleri ayarlar. [Microsoft Endpoint Manager'daki](/mem/endpoint-manager-overview) temeller veya ilkeler gibi uç nokta güvenlik ayarları değişirse, bu ayarlar yerleşik koruma ayarlarını geçersiz kılar.  

## <a name="what-does-the-notification-look-like"></a>Bildirim nasıl görünür?

İki tür bildirim almayı bekleyebilirsiniz:

- Yerleşik korumanın yakında geleceğini belirten bir ileti merkezi gönderisi; Ve 
- Microsoft 365 Defender portalında aşağıdaki resme benzeyen bir başlık:

   :::image type="content" source="media/bip-notification-m365defender.png" alt-text="Microsoft 365 Defender portalında yerleşik korumayı vurgulayan sarı başlık gösteren ekran görüntüsü.":::

Bildiriminiz, yerleşik korumanın ne zaman geldiğini ve kiracınız için kurcalama korumasının ne zaman açılacağını (henüz yapılandırılmamışsa) size bildirecektir.

## <a name="can-i-opt-out"></a>Geri çevirebilir miyim?

Kendi güvenlik ayarlarınızı belirterek yerleşik korumayı geri çevirebilirsiniz. Örneğin, kiracınız için kurcalama korumasının otomatik olarak açık olmamasını tercih ederseniz, açıkça devre dışı bırakabilirsiniz.

> [!NOTE]
> **Kurcalama korumasını kapatmanızı önermeyiz**. Kurcalama koruması size daha iyi fidye yazılımı koruması sağlar.
> Aşağıdaki yordamı gerçekleştirmek için genel yönetici veya güvenlik yöneticisi olmanız gerekir.

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Ayarlar** > **Uç Noktaları** > **Gelişmiş özellikler'e** gidin.

3. **Kurcalama korumasını** **Açık** olarak ayarlayın (henüz açık değilse) ve ardından **Tercihleri kaydet'i** seçin. *Bu sayfadan henüz ayrılmayın*.

4. **Kurcalama korumasını** **Kapalı** olarak ayarlayın ve ardından **Tercihleri kaydet'i** seçin.

## <a name="can-i-change-built-in-protection-settings"></a>Yerleşik koruma ayarlarını değiştirebilir miyim?

Yerleşik koruma, bir dizi varsayılan ayardır. Bu varsayılan ayarları yerinde tutmanız gerekmez. Ayarlarınızı istediğiniz zaman iş gereksinimlerinize uyacak şekilde değiştirebilirsiniz. Aşağıdaki tabloda güvenlik ekibinizin gerçekleştirebileceği görevlerin yanı sıra daha fazla bilgi edinmek için bağlantılar listelenir. 

| Görev | Açıklama |
|:---|:---|
| Kurcalama korumasının açık olup olmadığını belirleme | 1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.<br/>2. **Ayarlar** > **Uç Noktaları** > **Gelişmiş özellikler** > **Kurcalama koruması'na** gidin.  |
| Microsoft 365 Defender portalını ([https://security.microsoft.com](https://security.microsoft.com)) kullanarak kurcalama koruması kiracı genelinde yönetme | 1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.<br/>2. **Ayarlar** > **Uç Noktaları** > **Gelişmiş özellikler'e** gidin.<br/>3. **Kurcalama korumasını** **Açık** (*önerilen*) veya **Kapalı** olarak ayarlayın.<br/>4. **Tercihleri kaydet'i** seçin.<br/><br/>Bkz. [Microsoft 365 Defender portalını kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-microsoft-365-defender.md). |
| Tüm cihazlar için değil, bazıları için kurcalama koruması ayarlarını belirleme | Belirli cihazlara uygulanan uç nokta güvenlik ilkelerini ve profillerini kullanın. Aşağıdaki makalelere bakın:<br/>- [Microsoft Endpoint Manager kullanarak kurcalama korumasını yönetme](manage-tamper-protection-microsoft-endpoint-manager.md)<br/>- [Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kurcalama korumasını yönetme](manage-tamper-protection-configuration-manager.md)|
| Tek bir cihazda kurcalama korumasını açma veya kapatma | 1. Windows cihazınızda **Başlat'ı** seçin ve *Güvenlik* yazmaya başlayın.<br/>2. Arama sonuçlarında **Windows Güvenliği'ı** seçin.<br/>3. **Virüs & tehdit koruması** > **Virüs & tehdit koruması ayarlarını** seçin.<br/>4. **Kurcalama Koruması'yı** **Açık** (*önerilen*) veya **Kapalı** olarak ayarlayın. <br/><br/>Cihaz Uç Nokta için Defender'a eklendiyse veya cihaz Microsoft Endpoint Manager yönetim merkezinde yönetiliyorsa, bu ayarlar tek bir cihazdaki kullanıcı ayarlarını geçersiz kılar. <br/><br/>Bkz. [Tek bir cihazda kurcalama korumasını yönetme](manage-tamper-protection-individual-device.md). |
| Sorun giderme amacıyla cihazda kurcalama korumasını geçici olarak devre dışı bırakma | Aşağıdaki makalelere bakın:<br/>- [Uç Nokta için Microsoft Defender'de sorun giderme modunu kullanmaya başlama](enable-troubleshooting-mode.md)<br/>- [Uç Nokta için Microsoft Defender'de sorun giderme modu senaryoları](troubleshooting-mode-scenarios.md) |

## <a name="see-also"></a>Ayrıca bkz.

- [Teknoloji Topluluğu blogu: Tüm kurumsal müşteriler için kurcalama koruması açılacak](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-will-be-turned-on-for-all-enterprise-customers/ba-p/3616478)
- [Değişiklik korumasıyla güvenlik ayarlarını koruyun](prevent-changes-to-security-settings-with-tamper-protection.md)
- [Microsoft Intune'da uç nokta güvenliğini yönetme](/mem/intune/protect/endpoint-security)
- [Intune'da Uç Nokta için Microsoft Defender yapılandırma](/mem/intune/protect/advanced-threat-protection-configure)
- [Microsoft Endpoint Manager ile cihazlarda Uç Nokta için Microsoft Defender yönetme](/mem/intune/protect/mde-security-integration)
- [Fidye yazılımı saldırılarına yanıt verme](../defender/playbook-responding-ransomware-m365-defender.md)
