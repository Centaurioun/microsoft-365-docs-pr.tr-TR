---
title: Uç Nokta için Microsoft Defender Bulut tabanlı koruma tanıtımı
description: Bulut tabanlı korumanın kötü amaçlı dosyaları otomatik olarak nasıl algılayıp silebileceğini görün.
keywords: Uç Nokta için Microsoft Defender, Microsoft Defender ATP, virüs koruması, virüs algılama, virüs silme,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: 98aeeae72973f0a414b433f73a3ce66b15ef2798
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730259"
---
# <a name="cloud-delivered-protection-demonstration"></a>Bulut tabanlı koruma tanıtımı

Microsoft Gelişmiş Koruma Hizmeti (MAPS) olarak da adlandırılan Microsoft Defender Virüsten Koruma için bulut tabanlı koruma, standart gerçek zamanlı korumamıza ek olarak güçlü ve hızlı koruma sağlar.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 7, Windows 8.1, Windows 10 Windows 11
- Microsoft Defender Gerçek zamanlı koruma etkinleştirildi
- Bulut tabanlı koruma varsayılan olarak etkindir, ancak önceki kuruluş ilkelerinin bir parçası olarak devre dışı bırakıldıysa yeniden etkinleştirmeniz gerekebilir. Daha fazla bilgi için bkz[. Microsoft Defender Virüsten Koruma'da bulut tabanlı korumayı etkinleştirme](/windows/threat-protection/windows-defender-antivirus/enable-cloud-protection-windows-defender-antivirus?ocid=wd-av-demo-cloud-middle).
- Ayrıca bu ayarı ve diğer ayarları Windows 10 ve Windows 11 etkinleştirmek için [PowerShell betiğini](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings/) indirip kullanabilirsiniz.

### <a name="scenario"></a>Senaryo

1. [Test dosyasını](https://aka.ms/ioavtest) indirin. Önemli: Test dosyası kötü amaçlı değildir, yalnızca virüs simülasyonu yapılan zararsız bir dosyadır.

2. SmartScreen Microsoft Defender tarafından engellenen bir dosya görürseniz "İndirmeleri görüntüle" düğmesini seçin.

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-block.png" alt-text="SmartScreen güvenli olmayan bir indirmeyi engeller ve **İndirmeler** liste ayrıntılarını görüntülemek için seçebileceğiniz bir düğme sağlar.":::

3. İndirmeler menüsünde engellenen dosyayı sağ seçin ve **Güvenli olmayan dosyayı indir'i** seçin.

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-block-view-downloads.png" alt-text="İndirmeyi güvenli değil olarak listeler, ancak indirme işlemine devam etmek için bir seçenek sağlar":::

4. "Microsoft Defender Virüsten Koruma"nın bir virüs bulduğunu ve sildiğini görmeniz gerekir.

   > [!NOTE]
   >
   > Bazı durumlarda, Microsoft Defender Güvenlik Merkezi **Tehdit Bulundu** bildirimini de görebilirsiniz.

   :::image type="content" source="images/cloud-delivered-protection-smartscreen-threat-found-notification.png" alt-text="Microsoft Defender Virüsten Koruma Tehditleri bulundu bildirimi, ayrıntıları almak için seçenekler sağlar":::

5. Dosya yürütülürse veya Microsoft Defender SmartScreen tarafından engellendiğini görürseniz bulut tabanlı koruma çalışmaz. Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma için ağ bağlantılarını yapılandırma ve doğrulama](/windows/threat-protection/windows-defender-antivirus/configure-network-connections-windows-defender-antivirus?ocid=wd-av-demo-cloud-middle).

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Defender Virüsten Koruma'da Microsoft bulut tabanlı korumayı kullanma](/windows/threat-protection/windows-defender-antivirus/utilize-microsoft-cloud-protection-windows-defender-antivirus?ocid=wd-av-demo-cloud-bottom)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
