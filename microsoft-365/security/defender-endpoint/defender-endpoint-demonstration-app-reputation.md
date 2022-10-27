---
title: Uç Nokta için Microsoft Defender SmartScreen uygulaması saygınlığı tanıtımı
description: Uç Nokta için Microsoft Defender SmartScreen'in kimlik avı ve kötü amaçlı yazılım web sitelerini tanımlamanıza nasıl yardımcı olduğunu test edin
keywords: Uç Nokta için Microsoft Defender, kimlik avı web sitesi, kötü amaçlı yazılım web sitesi, uygulama itibarı,
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
ms.openlocfilehash: cc7081f8c6e71e321e68016f45c5d400e3a1c3cd
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730281"
---
# <a name="smartscreen-app-reputation-demonstration"></a>SmartScreen uygulaması saygınlığı tanıtımı

Uç Nokta için Microsoft Defender SmartScreen'in Uygulama itibarına göre kimlik avı ve kötü amaçlı yazılım web sitelerini tanımlamanıza nasıl yardımcı olduğunu test edin.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10
- Internet Explorer veya Microsoft Edge tarayıcısı gerekiyor
- AÇI/KAPALI özelliğini açmak için **Ayarlar** > **Güncelleştirme & Güvenlik'e** >  gidin **Windows Güvenliği** >  **Uygulama Windows Güvenliği** >  **Uygulama & tarayıcı denetimini açma** > **Uygulamaları ve dosyaları denetleme**

## <a name="scenario-demos"></a>Senaryo Tanıtımları

### <a name="known-good-program"></a>Bilinen iyi program

Bu program iyi bir üne sahiptir; İndirme işlemi kesintisiz olarak çalıştırılmalıdır:

- [Bilinen iyi program indirme](https://demo.smartscreen.msft.net/download/known/freevideo.exe)

  Bu bağlantının başlatılması aşağıdakine benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-app-reputation-known-good.png" alt-text="Hedef dosyanın itibarına bağlı olarak, SmartScreen engelleme olmadan indirmeye izin verir.":::

### <a name="unknown-program"></a>Bilinmeyen program

Program indirmesinin güvenilir olduğundan emin olmak için yeterli saygınlığı olmadığından, SmartScreen program indirmesini çalıştırmadan önce bir uyarı gösterir.

- [Bilinmeyen program](https://demo.smartscreen.msft.net/download/unknown/freevideo.exe)
  
  Bu bağlantının başlatılması aşağıdakine benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-app-reputation-unknown.png" alt-text="SmartScreen indirme dosyası hakkında yeterli saygınlık bilgilerine sahip değildir ve kullanıcıyı durması veya dikkatli olması konusunda uyarır.":::

### <a name="known-malware"></a>Bilinen kötü amaçlı yazılım

Bu indirme bilinen kötü amaçlı yazılımdır; SmartScreen bu programın çalışmasını engellemelidir.

- [Bilinen kötü amaçlı yazılım](https://demo.smartscreen.msft.net/download/known/knownmalicious.exe)

  Bu bağlantının başlatılması aşağıdakine benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-app-reputation-known-malware.png" alt-text="SmartScreen'in güvenli olmayan bir üne sahip bir dosya indirmesini nasıl algılayanı gösteren ekran görüntüsü.; indirme engellendi.":::

## <a name="learn-more"></a>Daha fazla bilgi

[Microsoft Defender SmartScreen Belgeleri](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
