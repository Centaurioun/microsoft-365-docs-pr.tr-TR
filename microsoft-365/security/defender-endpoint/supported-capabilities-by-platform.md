---
title: Platforma göre desteklenen Uç Nokta için Microsoft Defender özellikleri
description: Windows 10 cihazlar, sunucular ve Windows olmayan cihazlar için desteklenen Uç Nokta için Microsoft Defender özelliklerini tanıyın.
keywords: ekleme, Uç Nokta için Microsoft Defender ekleme, sccm, grup ilkesi, mdm, yerel betik, algılama testi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: dcff54381dbdaf1362f9d4dd7cdc364e29c53426
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227756"
---
# <a name="supported-microsoft-defender-for-endpoint-capabilities-by-platform"></a>Platforma göre desteklenen Uç Nokta için Microsoft Defender özellikleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Cihazları eklemeyi ve Uç Nokta için Microsoft Defender özelliklerini yapılandırmayı](onboard-configure.md) öğrenin.

Aşağıdaki tabloda platforma göre desteklenen Uç Nokta için Microsoft Defender özellikleri hakkında bilgi velenmektedir.

|İşletim Sistemi  |Windows 10 & 11  |Windows Server 2012 R2 <sup>[[1](#fn1)]</sup>, <br> 2016 <sup>[[1](#fn1)]</sup>, <br> 2019 & 2022, <br> 1803+ |macOS |Linux| 
|---------|---------|---------|---------|---------|
|**Önleme**    |         |         |         |         | 
|Saldırı Yüzeyi Azaltma kuralları     | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)     |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Denetimli klasör erişimi     | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)    |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Cihaz Denetimi     | ![Evet.](images/svg/check-yes.svg)        | ![Hayır](images/svg/check-no.svg)   |  ![Evet.](images/svg/check-yes.svg)       |  ![Hayır](images/svg/check-no.svg)        |  
|Güvenlik duvarı      | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)    |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Ağ Koruması      | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)   |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|Yeni nesil koruma       | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
|Kurcalama Koruması        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Evet.](images/svg/check-yes.svg)       |  ![Hayır](images/svg/check-no.svg)         |
|Web Koruması       | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)     |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
||||||
|**Algılama**     |         |         |         |       |
|Gelişmiş Avcılık        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg) |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
|Özel dosya göstergeleri         | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
|Özel ağ göstergeleri        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|EDR Bloğu       | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Pasif Mod          | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
|Algılama algılayıcısı          | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)   |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
|Uç nokta & ağ cihazı bulma      | ![Evet.](images/svg/check-yes.svg)        | ![Hayır](images/svg/check-no.svg)  |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Güvenlik açığı yönetimi          | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg) |  ![Evet.](images/svg/check-yes.svg)       |  ![Evet.](images/svg/check-yes.svg)         |
||||||
|**Yanıt**     |         |         |         ||
|Otomatik Araştırma & Yanıtı (AIR)        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)  |  ![Hayır](images/svg/check-no.svg)       |  ![Hayır](images/svg/check-no.svg)        |
|Cihaz yanıtı özellikleri: araştırma paketi toplama, AV taraması çalıştırma        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)   |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>       |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>        |
|Cihaz yalıtımı        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)   |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>       |  ![Hayır](images/svg/check-no.svg)    |
|Dosya yanıtı özellikleri: dosya toplama, derin analiz, blok dosyası, durdurma ve karantina işlemleri        | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg)   |  ![Hayır](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>      |  ![Hayır](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>    |
|Canlı Yanıt       | ![Evet.](images/svg/check-yes.svg)        | ![Evet.](images/svg/check-yes.svg) |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Evet.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |


(<a id="fn1">1</a>) Windows Server 2012 R2 ve 2016 için modern, birleşik çözümü ifade eder. Daha fazla bilgi için bkz. [Uç Nokta için Defender hizmetine Windows Sunucuları ekleme](configure-server-endpoints.md).

(<a id="fn2">2</a>) Özellik şu anda önizleme aşamasındadır ([Uç Nokta için Microsoft Defender önizleme özellikleri](preview.md)) 

(<a id="fn3">3</a>) Canlı Yanıt kullanan yanıt özellikleri [2] 

(<a id="fn4">4</a>) Canlı Yanıt kullanarak yalnızca dosya toplama [2]  
>[!NOTE]
>Windows 7, 8.1, Windows Server 2008 R2, EDR algılayıcısı ve System Center Endpoint Protection (SCEP) kullanan AV için destek içerir.

