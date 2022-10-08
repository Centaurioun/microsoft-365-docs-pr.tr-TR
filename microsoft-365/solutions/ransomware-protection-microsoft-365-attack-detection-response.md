---
title: Adım 2. Saldırı algılama ve yanıt dağıtın
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, HumOR, gasp saldırısı, fidye yazılımı saldırısı, şifreleme, kriptoviroloji, sıfır güven
description: Microsoft 365 kaynaklarınızı fidye yazılımı saldırılarına karşı korumak için Microsoft 365 Defender ve güvenlik sinyali kaynaklarını kullanın.
ms.openlocfilehash: 882e138717e7bad8e71db3914d034edf5bc0b6c2
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986476"
---
# <a name="step-2-deploy-attack-detection-and-response"></a>Adım 2. Saldırı algılama ve yanıt dağıtın

Microsoft 365 kiracınızda fidye yazılımı saldırı algılaması ve yanıtı için kesinlikle önerilen bir başlangıç adımı olarak, Microsoft 365 Defender özelliklerini ve özelliklerini değerlendirmek için [bir deneme ortamı ayarlayın](/microsoft-365/security/defender/eval-overview).

Ek bilgi için bu kaynaklara bakın.

| Özellik | Açıklama | Nereden başlayacağız? | Algılama ve yanıt için kullanma |
|:-------|:-----|:-------|:-------|
| [Microsoft 365 Defender](/microsoft-365/security/defender) | Sinyalleri birleştirir ve özellikleri tek bir çözümde düzenler. <br><br> Güvenlik uzmanlarının tehdit sinyallerini birleştirmesini ve bir tehdidin tam kapsamını ve etkisini belirlemesini sağlar. <br><br> Saldırıyı önleme veya durdurma eylemlerini otomatikleştirir ve etkilenen posta kutularını, uç noktaları ve kullanıcı kimliklerini kendi kendine iyileştirir. | [Başlarken](/microsoft-365/security/defender/get-started) | [Olay yanıtı](/microsoft-365/security/defender/incidents-overview) |
| [Kimlik için Microsoft Defender](/defender-for-identity/what-is) |  Bulut tabanlı bir güvenlik arabirimi aracılığıyla kuruluşunuza yönlendirilen gelişmiş tehditleri, güvenliği aşılmış kimlikleri ve kötü amaçlı insider eylemlerini tanımlar, algılar ve araştırır şirket içi Active Directory Domain Services (AD DS) sinyallerinizi kullanır. | [Genel Bakış](/defender-for-identity/what-is) | [Kimlik için Microsoft Defender portalıyla çalışma](/defender-for-identity/workspace-portal) |
| [Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security) | Kuruluşunuzu e-posta iletileri, bağlantılar (URL'ler) ve işbirliği araçları tarafından ortaya konan kötü amaçlı tehditlere karşı korur. <br><br> Kötü amaçlı yazılımlara, kimlik avına, kimlik sahtekarlığına ve diğer saldırı türlerine karşı koruma sağlar. | [Genel Bakış](/microsoft-365/security/office-365-security/overview) | [Tehdit avcılığı](/microsoft-365/security/office-365-security/threat-hunting-in-threat-explorer) |
| [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint) | Uç noktalar (cihazlar) genelindeki gelişmiş tehditleri algılamayı ve yanıtlamayı etkinleştirir. | [Genel Bakış](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)  | [Uç nokta algılama ve yanıt](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) |
| [Azure Active Directory (Azure AD) Kimlik Koruması](/azure/active-directory/identity-protection/) | Kimlik tabanlı riskleri algılamayı ve düzeltmeyi ve bu risklerin araştırılması işlemini otomatikleştirir. | [Genel Bakış](/azure/active-directory/identity-protection/overview-identity-protection) | [Riski araştırma](/azure/active-directory/identity-protection/howto-identity-protection-investigate-risk) |
| [Bulut Uygulamaları için Microsoft Defender](/cloud-app-security) | Tüm Microsoft ve üçüncü taraf bulut hizmetlerinizde bulma, araştırma ve idare için bir bulut erişim güvenlik aracısı. | [Genel Bakış](/cloud-app-security/what-is-cloud-app-security) | [Araştır](/cloud-app-security/investigate) |

>[!Note]
>Bu hizmetlerin tümü için Microsoft 365 E5 Güvenlik eklentisiyle Microsoft 365 E5 veya Microsoft 365 E3 gerekir.
>

Fidye yazılımı saldırganlarının aşağıdaki yaygın tehditlerini algılamak ve yanıtlamak için bu hizmetleri kullanın:

- Kimlik bilgisi hırsızlığı

   - Azure AD Kimlik Koruması
   - Kimlik için Microsoft Defender
   - Office 365 için Defender

- Cihaz güvenliğinin aşılmasına neden olan

   - Uç Nokta için Defender
   - Office 365 için Defender

- Ayrıcalığı yükseltme

   - Azure AD Kimlik Koruması
   - Bulut Uygulamaları için Defender

- Kötü amaçlı uygulama davranışı

   - Bulut Uygulamaları için Defender

- Veri sızdırma, silme veya karşıya yükleme

   - Office 365 için Defender
   - [Anomali algılama ilkeleriyle](/cloud-app-security/anomaly-detection-policy#ransomware-activity) Cloud Apps için Defender

Aşağıdaki hizmetler Microsoft 365 Defender ve portalını (https://security.microsoft.com)yaygın bir tehdit toplama ve analiz noktası olarak) kullanır:

- Kimlik için Microsoft Defender
- Office 365 için Defender
- Uç Nokta için Defender
- Bulut Uygulamaları için Defender

Microsoft 365 Defender, güvenlik analistlerinizin fidye yazılımı saldırısı aşamalarını daha hızlı algılaması, araştırması ve düzeltmesi için tehdit sinyallerini uyarılara ve bağlı uyarıları bir olaya birleştirir.

## <a name="resulting-configuration"></a>Sonuçta elde edilen yapılandırma

1. ve 2. adımlarda kiracınız için fidye yazılımı koruması aşağıdadır.

![2. Adımdan sonra Microsoft 365 kiracınız için fidye yazılımı koruması](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step2.png)

## <a name="next-step"></a>Sonraki adım

[![Microsoft 365 ile fidye yazılımı koruması için 3. Adım](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step3.png)](ransomware-protection-microsoft-365-identities.md)

Microsoft 365 kiracınızdaki kimlikleri korumak için 3. [Adımla](ransomware-protection-microsoft-365-identities.md) devam edin.
