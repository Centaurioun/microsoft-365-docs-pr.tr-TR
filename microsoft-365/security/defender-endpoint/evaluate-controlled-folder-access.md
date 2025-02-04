---
title: Denetimli klasör erişimini değerlendirin
description: Denetimli klasör erişiminin dosyaların kötü amaçlı uygulamalar tarafından değiştirilmesini nasıl koruyabileceğini görün.
keywords: Yararlanma koruması, windows 10, windows 11, windows defender, fidye yazılımı, koruma, değerlendirme, test, tanıtım, deneme
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 4a6d0d1be1e26023b93164861a6d3533fda94220
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68173841"
---
# <a name="evaluate-controlled-folder-access"></a>Denetimli klasör erişimini değerlendirin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Denetimli klasör erişimi](controlled-folders.md) , belgelerinizi ve dosyalarınızın şüpheli veya kötü amaçlı uygulamalar tarafından değiştirilmesine karşı korunmasına yardımcı olan bir özelliktir. Denetimli klasör erişimi Windows Server 2019, Windows Server 2022, Windows 10 ve Windows 11 istemcilerinde desteklenir.

Dosyalarınızı şifrelemeye ve onları rehin tutmaya çalışan [fidye yazılımlarına](https://www.microsoft.com/wdsi/threats/ransomware) karşı korunmaya yardımcı olmak için özellikle yararlıdır.

Bu makale, denetimli klasör erişimini değerlendirmenize yardımcı olur. Özelliği doğrudan kuruluşunuzda test edebilmeniz için denetim modunun nasıl etkinleştirileceği açıklanır.

## <a name="use-audit-mode-to-measure-impact"></a>Etkiyi ölçmek için denetim modunu kullanma

Tam olarak etkinleştirildiğinde neler *olabileceğinin* kaydını görmek için denetim modunda denetimli klasör erişimini etkinleştirin. İş kolu uygulamalarınızı etkilemediğinden emin olmak için özelliğin kuruluşunuzda nasıl çalışacağını test edin. Ayrıca, belirli bir süre boyunca genellikle kaç şüpheli dosya değişikliği girişimi gerçekleştiği hakkında da bir fikir edinebilirsiniz.

Denetim modunu etkinleştirmek için aşağıdaki PowerShell cmdlet'ini kullanın:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Kuruluşunuzda denetimli klasör erişiminin nasıl çalışacağını tam olarak denetlemek istiyorsanız, bu ayarı ağınızdaki cihazlara dağıtmak için bir yönetim aracı kullanmanız gerekir.
Ayrıca, ana [denetimli klasör erişimi konusunda](controlled-folders.md) açıklandığı gibi ayarı yapılandırmak ve dağıtmak için grup ilkesi, Intune, mobil cihaz yönetimi (MDM) veya Microsoft Endpoint Manager kullanabilirsiniz.

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Windows Olay Görüntüleyicisi'da denetimli klasör erişimi olaylarını gözden geçirme

Aşağıdaki denetimli klasör erişimi olayları Windows Olay Görüntüleyicisi'da Microsoft/Windows/Windows Defender/Operasyonel klasörü altında görünür.

Olay Kimliği | Açıklama
-|-
 5007 | Ayarlar değiştirildiğinde gerçekleşen olay
 1124 | Denetlenen denetimli klasör erişimi olayı
 1123 | Engellenen denetimli klasör erişimi olayı

> [!TIP]
> Günlükleri merkezi olarak toplamak için [bir Windows Olay İletme aboneliği](/windows/win32/wec/setting-up-a-source-initiated-subscription) yapılandırabilirsiniz. 

## <a name="customize-protected-folders-and-apps"></a>Korumalı klasörleri ve uygulamaları özelleştirme

Değerlendirmeniz sırasında, korumalı klasörler listesine eklemek veya bazı uygulamaların dosyaları değiştirmesine izin vermek isteyebilirsiniz.

Grup ilkesi, PowerShell ve MDM yapılandırma hizmeti sağlayıcıları (CSP'ler) dahil olmak üzere yönetim araçlarıyla özelliği yapılandırmak için bkz. [Denetimli klasör erişimiyle önemli klasörleri koruma](controlled-folders.md).

## <a name="see-also"></a>Ayrıca bkz.

* [Denetimli klasör erişimiyle önemli klasörleri koruma](controlled-folders.md)
* [Uç Nokta için Microsoft Defender'ı Değerlendirme](evaluate-mde.md)
* [Denetim modunu kullanma](audit-windows-defender.md)
