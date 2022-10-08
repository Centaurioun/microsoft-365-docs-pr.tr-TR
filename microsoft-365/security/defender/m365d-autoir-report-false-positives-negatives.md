---
title: Microsoft 365 Defender hatalı pozitif sonuçları veya hatalı negatifleri ele alın
description: Microsoft 365 Defender'da AIR tarafından bir şey mi atlandı veya yanlış algılandı? Hatalı pozitif veya hatalı negatifleri analiz için Microsoft'a göndermeyi öğrenin.
keywords: otomatik, araştırma, uyarı, düzeltme, hatalı pozitif, yanlış negatif
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: a262927b45a1f24f0f3aa93de9521a1d9ed0d124
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069699"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Microsoft 365 Defender hatalı pozitif sonuçları veya hatalı negatifleri ele alın

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Herhangi bir tehdit koruması çözümünde bazen hatalı pozitifler veya negatifler oluşabilir. Microsoft 365 Defender'daki [otomatik araştırma ve yanıt özellikleri](m365d-autoir.md) bir şeyi kaçırdıysa veya yanlış algıladıysa, güvenlik operasyonları ekibinizin atabileceği adımlar vardır:

- [Hatalı pozitif/negatifi Microsoft'a bildirme](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Uyarılarınızı ayarlama](#adjust-an-alert-to-prevent-false-positives-from-recurring) (gerekirse)
- [Cihazlarda gerçekleştirilen düzeltme eylemlerini geri alma](#undo-a-remediation-action-that-was-taken-on-a-device)

Aşağıdaki bölümlerde bu görevlerin nasıl gerçekleştirildiği açıklanmaktadır.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Hatalı pozitif/negatifi analiz için Microsoft'a bildirme

|Öğe yanıtsız veya yanlış algılandı |Hizmet  |Yapılması gerekenler  |
|---------|---------|---------|
|- Email iletisi <br/>- ek Email <br/>- E-posta iletisindeki URL<br/>- Office dosyasındaki URL      |[Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Şüpheli istenmeyen posta, kimlik avı, URL'ler ve dosyaları tarama için Microsoft'a gönderin](../office-365-security/admin-submission.md)         |
|Bir cihazdaki dosya veya uygulama    |[Uç Nokta için Microsoft Defender](/windows/security/threat-protection)         |[Kötü amaçlı yazılım analizi için Microsoft'a dosya gönderme](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Hatalı pozitif sonuçların yinelenmesini önlemek için uyarıyı ayarlama

|Senaryo |Hizmet |Yapılması gerekenler |
|--------|--------|--------|
|- Bir uyarı geçerli kullanım tarafından tetikleniyor <br/>- Bir uyarı yanlış    |[Bulut Uygulamaları için Microsoft Defender](/cloud-app-security)<br/> veya <br/>[Azure tehdit koruması](/azure/security/fundamentals/threat-detection)         |[Cloud Apps için Defender portalında uyarıları yönetme](/cloud-app-security/managing-alerts)         |
|Dosya, IP adresi, URL veya etki alanı, güvenli olsa bile bir cihazda kötü amaçlı yazılım olarak değerlendirilir|[Uç Nokta için Microsoft Defender](/windows/security/threat-protection) |["İzin Ver" eylemiyle özel gösterge oluşturma](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Cihazda gerçekleştirilen düzeltme eylemini geri alma

Bir varlıkta (cihaz veya e-posta iletisi gibi) bir düzeltme eylemi yapıldıysa ve etkilenen varlık aslında bir tehdit değilse, güvenlik operasyonları ekibiniz [İşlem merkezindeki](m365d-action-center.md) düzeltme eylemini geri alabilir.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve oturum açın. 
2. Gezinti bölmesinde **İşlem merkezi'ni** seçin. 
3. **Geçmiş** sekmesinde, geri almak istediğiniz eylemi seçin. Açılır pencere bölmesi açılır.
4. Açılır bölmede **Geri Al'ı** seçin.

> [!TIP]
> Bkz. [Tamamlanan eylemleri geri alma](m365d-autoir-actions.md#undo-completed-actions).

## <a name="see-also"></a>Ayrıca bkz.

- [Otomatik bir soruşturmanın ayrıntılarını ve sonuçlarını görüntüleyin](m365d-autoir-results.md)
- [Microsoft 365 Defender'da gelişmiş arama ile tehditleri proaktif olarak avlama](advanced-hunting-overview.md)
