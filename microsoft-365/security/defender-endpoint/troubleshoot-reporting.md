---
title: Microsoft Defender Virüsten Koruma için raporlama araçlarıyla ilgili sorunları giderme
description: Güncelleştirme Uyumluluğu'nda virüsten koruma durumunu Microsoft Defender bildirmeye çalışırken sık karşılaşılan sorunları belirleme ve çözme
keywords: sorun giderme, hata, düzeltme, güncelleştirme uyumluluğu, oms, izleme, rapor Microsoft Defender Virüsten Koruma
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: ec4d628d3eee6cb8331560241f008ef92168961b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226020"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Güncelleştirme Uyumluluğunda Microsoft Defender Virüsten Koruma raporlama sorunlarını giderin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

> [!IMPORTANT]
> 31 Mart 2020'de Güncelleştirme Uyumluluğu'nun Microsoft Defender Virüsten Koruma raporlama özelliği kaldırılacaktır. Güvenlik özellikleri ve güncelleştirmeleri üzerinde daha ayrıntılı denetime olanak tanıyan [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) kullanarak güvenlik uyumluluk ilkelerini tanımlamaya ve gözden geçirmeye devam edebilirsiniz.

Güncelleştirme Uyumluluğu ile Microsoft Defender Virüsten Koruma kullanabilirsiniz. E3, B, F1, VL ve Pro lisanslarının durumunu görürsünüz. Ancak E5 lisansları için [Uç Nokta için Microsoft Defender portalını](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) kullanmanız gerekir. Lisanslama seçenekleri hakkında daha fazla bilgi edinmek için bkz. [Windows 10 ürün lisanslama seçenekleri](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).

Microsoft Defender Virüsten Koruma kullanan ağınızdaki [cihazların veya uç noktaların koruma durumunu raporlamak için Windows Analytics Güncelleştirme Uyumluluğu'nu](/windows/deployment/update/update-compliance-using#wdav-assessment) kullandığınızda, sorunlarla veya sorunlarla karşılaşabilirsiniz.

Genellikle, bir sorunun en yaygın göstergeleri şunlardır:

- Görmeyi beklediğiniz tüm cihazların yalnızca küçük bir sayısını veya alt kümesini görürsünüz
- Hiç cihaz görmüyorsunuz
- Gördüğünüz raporlar ve bilgiler güncel değil (birkaç günden eski)

Güncelleştirme Uyumluluğu ile ilgili olmayan Microsoft Defender Virüsten Koruma hizmetiyle ilgili yaygın hata kodları ve olay kimlikleri için bkz[. virüsten koruma olayları Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md).

Bu sorunları gidermenin üç adımı vardır:

1. Tüm önkoşulları karşıladığınızdan emin olun
2. Windows Defender bulut tabanlı hizmete bağlantınızı denetleyin
3. Destek günlüklerini gönderme

> [!IMPORTANT]
> Cihazların Güncelleştirme Uyumluluğu'nda görünmeye başlaması genellikle 3 gün sürer.

## <a name="confirm-prerequisites"></a>Önkoşulları onaylama

Cihazların Güncelleştirme Uyumluluğu'nda düzgün bir şekilde görünmesi için hem Güncelleştirme Uyumluluğu hizmeti hem de Microsoft Defender Virüsten Koruma için belirli önkoşulları karşılamanız gerekir:

>[!div class="checklist"]
>
> - Uç noktalar tek virüsten koruma uygulaması olarak Microsoft Defender Virüsten Koruma kullanıyor. [Başka bir virüsten koruma uygulaması kullanmak Microsoft Defender Virüsten Koruma'nın kendisini devre dışı bırakmasına neden](microsoft-defender-antivirus-compatibility.md) olur ve uç nokta Güncelleştirme Uyumluluğu'nda raporlanmaz.
> - [Bulut tabanlı koruma etkindir](enable-cloud-protection-microsoft-defender-antivirus.md).
> - Uç noktalar [Microsoft Defender Virüsten Koruma buluta bağlanabilir](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Uç nokta 1607 veya önceki bir Windows 10 çalıştırıyorsa, [Windows 10 tanılama verileri Gelişmiş düzeyine ayarlanmalıdır](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).
> - Tüm gereksinimlerin karşılanmasından bu yana 3 gün geçti

"Güncelleştirme Uyumluluğu ile Microsoft Defender Virüsten Koruma kullanabilirsiniz. E3, B, F1, VL ve Pro lisanslarının durumunu görürsünüz. Ancak E5 lisansları için Uç Nokta için Microsoft Defender portalını (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) kullanmanız gerekir. Lisanslama seçenekleri hakkında daha fazla bilgi edinmek için bkz. Windows 10 ürün lisanslama seçenekleri"

Yukarıdaki önkoşulların tümü karşılandıysa, tanılama bilgilerini toplamak ve bize göndermek için sonraki adıma geçmeniz gerekebilir.

> [!div class="nextstepaction"]
> [Güncelleştirme Uyumluluğu sorunlarını gidermek için tanılama verilerini toplama](collect-diagnostic-data.md)

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="related-topics"></a>İlgili konular

- [Windows 10'de virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Virüsten Koruma Dağıtma](deploy-manage-report-microsoft-defender-antivirus.md)
