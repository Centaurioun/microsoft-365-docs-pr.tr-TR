---
title: Otomatik araştırma ve yanıt ile özel raporlama çözümleri
keywords: SIEM, API, AIR, autoIR, Uç Nokta için Microsoft Defender, otomatik araştırma, tümleştirme, özel rapor
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Otomatik araştırma ve yanıtı özel veya üçüncü taraf raporlama çözümüyle tümleştirmeyi öğrenin.
ms.date: 01/29/2021
ms.custom:
- air
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ff0326e755b6f2be96e99bc9e1894cf1c721ade8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480139"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender için özel veya üçüncü taraf raporlama çözümleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365 için Microsoft Defender](defender-for-office-365.md) ile [otomatik araştırmalarla ilgili ayrıntılı bilgiler](air-view-investigation-results.md) alırsınız. Ancak bazı kuruluşlar özel veya üçüncü taraf raporlama çözümü de kullanır. Kuruluşunuz [otomatik araştırmalarla](office-365-air.md) ilgili bilgileri böyle bir çözümle tümleştirmek istiyorsa Office 365 Yönetim Etkinliği API'sini kullanabilirsiniz.

[Office 365 için Microsoft Defender](defender-for-office-365.md) ile [otomatik araştırmalarla ilgili ayrıntılı bilgiler](air-view-investigation-results.md) alırsınız. Ancak bazı kuruluşlar özel veya üçüncü taraf raporlama çözümü de kullanır. Kuruluşunuz otomatik araştırmalarla ilgili bilgileri böyle bir çözümle tümleştirmek istiyorsa Office 365 Yönetim Etkinliği API'sini kullanabilirsiniz.

|Kaynak|Açıklama|
|:---|:---|
|[Office 365 Yönetimi API'lerine genel bakış](/office/office-365-management-api/office-365-management-apis-overview)|Office 365 Yönetim Etkinliği API'sinde Microsoft 365 ve Azure Active Directory etkinlik günlüklerindeki çeşitli kullanıcı, yönetici, sistem ve ilke eylemleri ve olayları hakkında bilgi sağlanır.|
|[Office 365 Yönetim API'lerini kullanmaya başlama](/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 Yönetim API'si, uygulamanızın Microsoft 365 verilerine erişmesi için kimlik doğrulama hizmetleri sağlamak üzere Azure AD kullanır. Bunu ayarlamak için bu makaledeki adımları izleyin.|
|[Office 365 Yönetim Etkinliği API’si referansı](/office/office-365-management-api/office-365-management-activity-api-reference)|Microsoft 365 ve Azure AD etkinlik günlüklerinden kullanıcı, yönetici, sistem ve ilke eylemleri ve olayları hakkında bilgi almak için Office 365 Yönetim Etkinliği API'sini kullanabilirsiniz. Bunun nasıl çalıştığı hakkında daha fazla bilgi edinmek için bu makaleyi okuyun.|
|[Office 365 Yönetim Etkinliği API’si şeması](/office/office-365-management-api/office-365-management-activity-api-schema)|Office 365 Yönetim Etkinliği API'sinde kullanılabilen belirli veri türleri hakkında bilgi edinmek için [Ortak şemaya](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) [ve Office 365 için Defender ve tehdit araştırması ile yanıt şemasına](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) genel bir bakış edinin.|

## <a name="see-also"></a>Ayrıca bkz.

- [Office 365 için Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender'de otomatik araştırma ve yanıt](/microsoft-365/security/defender/m365d-autoir)
