---
title: Bulut koruması ve Microsoft Defender Virüsten Koruma
description: Bulut koruması ve Microsoft Defender Virüsten Koruma hakkında bilgi edinin
keywords: Microsoft Defender Virüsten Koruma, yeni nesil teknolojiler, yeni nesil av, makine öğrenmesi, kötü amaçlı yazılımdan koruma, güvenlik, defender, bulut, bulut koruması
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: conceptual
ms.date: 10/18/2021
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 3d9e9df1383a258f930741199659fc2c9728abb3
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632964"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>Bulut koruması ve Microsoft Defender Virüsten Koruma

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma'daki yeni nesil teknolojiler, yeni ve yeni ortaya çıkan tehditlere karşı neredeyse anında, otomatik koruma sağlar. Yeni tehditleri dinamik olarak tanımlamak için yeni nesil teknolojiler, Microsoft Akıllı Güvenlik Grafı'ndaki büyük bağlantılı veri kümeleriyle ve gelişmiş makine öğrenmesi modelleri tarafından yönetilen güçlü yapay zeka (AI) sistemleriyle çalışır. Bulut koruması doğru, gerçek zamanlı ve akıllı koruma sağlamak için Microsoft Defender Virüsten Koruma ile birlikte çalışır. 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="bulut korumasının Microsoft Defender Virüsten Koruma ile birlikte nasıl çalıştığını gösteren diyagram" lightbox="images/mde-cloud-protection.png":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> Bulut korumasını açık tutmanızı öneririz. Daha fazla bilgi edinmek için bkz. [Microsoft Defender Virüsten Koruma için neden bulut koruması etkinleştirilmelidir](why-cloud-protection-should-be-on-mdav.md). 

## <a name="how-cloud-protection-works"></a>Bulut koruması nasıl çalışır?

Microsoft Defender Virüsten Koruma, Microsoft bulut hizmetleriyle sorunsuz çalışır. Microsoft Gelişmiş Koruma Hizmeti (MAPS) olarak da adlandırılan bu bulut koruma hizmetleri, standart gerçek zamanlı korumayı geliştirir. Bulut koruması sayesinde yeni nesil teknolojiler, bazen tek bir uç noktaya virüs bulaşmadan önce bile yeni tehditlerin hızla tanımlanmasını sağlar. 

Aşağıdaki blog gönderileri, bulut korumasının nasıl çalıştığını göstermektedir:

- [Uç Nokta için Microsoft Defender yeni nesil korumanın temelindeki gelişmiş teknolojileri tanımaya başlayın](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [Microsoft Defender Virüsten Koruma neden kuruluşta en çok dağıtılandır?](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [Makine öğrenmesi ile birlikte davranış izleme, büyük bir madeni para madenciliği kampanyasını bozuyor](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [Yapay zeka bir "Emotet" salgınını nasıl durdurdu?](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [Kötü bir tavşanın patlatılıyor: virüsten koruma ve katmanlı makine öğrenmesi savunmaları Microsoft Defender](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Microsoft Defender Virüsten Koruma bulut koruma hizmeti: Daha önce görülmemiş kötü amaçlı yazılımlara karşı gelişmiş gerçek zamanlı savunma](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> Microsoft Defender Virüsten Koruma bulut hizmeti, ağınıza ve uç noktalarınıza güncelleştirilmiş koruma sunmaya yönelik bir mekanizmadır. Bir bulut hizmeti olarak, yalnızca bulutta depolanan dosyalar için koruma değildir; Bunun yerine bulut hizmeti, geleneksel güvenlik bilgileri güncelleştirmelerinden çok daha hızlı bir hızda uç noktalarınıza koruma sağlamak için dağıtılmış kaynakları ve makine öğrenmesini kullanır.

## <a name="how-to-get-cloud-protection"></a>Bulut korumasını alma 

Bulut koruması varsayılan olarak etkindir. Ancak, önceki kuruluş ilkelerinin bir parçası olarak devre dışı bırakılmışsa yeniden etkinleştirmeniz gerekebilir. Daha fazla bilgi için bkz. [Bulut korumasını açma](enable-cloud-protection-microsoft-defender-antivirus.md).

Aboneliğiniz Windows 10 E5 içeriyorsa, yeni ortaya çıkan tehditlere karşı neredeyse gerçek zamanlı koruma sağlayan acil durum dinamik zeka güncelleştirmelerinden yararlanabilirsiniz. Bulut korumasını açtığınızda, kötü amaçlı yazılım sorunlarının düzeltmeleri bir sonraki güncelleştirmeyi beklemek yerine birkaç dakika içinde bulut üzerinden teslim edilebilir. Bkz[. Bulut hizmetimizden gelen raporlara göre yeni koruma güncelleştirmelerini otomatik olarak almak için Microsoft Defender Virüsten Koruma'yi yapılandırma](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates).

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Defender Virüsten Koruma'da bulut korumasına genel bir bakış elde ettiğinize göre, sonraki adımlardan bazıları şunlardır:

1. Bkz. [Microsoft Defender Virüsten Koruma için bulut korumasının neden etkinleştirilmesi gerektiği](why-cloud-protection-should-be-on-mdav.md).

2. [Bulut korumasını etkinleştirme](enable-cloud-protection-microsoft-defender-antivirus.md) işlemine geçin

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)