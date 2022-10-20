---
title: Bulut için Microsoft Defender ile tümleştirme
description: Bulut için Microsoft Defender ile Uç Nokta için Microsoft Defender tümleştirmesi hakkında bilgi edinin
keywords: tümleştirme, sunucu, azure, 2012r2, 2016, 2019, sunucu ekleme, cihaz yönetimi, Uç Nokta için Microsoft Defender sunucuları yapılandırma, Uç Nokta için Microsoft Defender sunucuları ekleme, ekleme sunucuları Uç Nokta için Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 65a26cf05531ecea3c5c1f95e4013d283d677adf
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647309"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>Bulut için Microsoft Defender ile tümleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Bulut için Microsoft Defender

Uç Nokta için Microsoft Defender kapsamlı bir Windows sunucusu koruma çözümü sağlamak için Bulut için Microsoft Defender ile tümleştirebilir. Bu tümleştirme sayesinde Bulut için Microsoft Defender, Windows Server'lar için gelişmiş tehdit algılama sağlamak üzere Uç Nokta için Defender'ın gücünü kullanabilir.

Bu tümleştirmeye aşağıdaki özellikler dahildir:

- Otomatik ekleme - Uç Nokta için Defender algılayıcısı, Bulut için Microsoft Defender eklenen Windows Sunucularında otomatik olarak etkinleştirilir. Bulut ekleme Microsoft Defender hakkında daha fazla bilgi için bkz. [Tümleşik Uç Nokta için Microsoft Defender lisansını kullanma](/azure/security-center/security-center-wdatp).

    > [!NOTE]
    > Sunucular ve Uç Nokta için Microsoft Defender için Microsoft Defender arasındaki tümleştirme[, Windows Server 2019 ve Windows Sanal Masaüstü'nü (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview) destekleyecek şekilde genişletilmiştir.

- Bulut için Microsoft Defender tarafından izlenen Windows sunucuları Uç Nokta için Defender'da da kullanılabilir. Bulut için Microsoft Defender, istemciler ve sunucular arasında tek bir görünüm sağlayarak Uç Nokta için Defender kiracısına sorunsuz bir şekilde bağlanır.  Buna ek olarak, Uç Nokta için Defender uyarıları Bulut için Microsoft Defender konsolunda kullanılabilir.
- Sunucu araştırması - Bulut müşterileri için Microsoft Defender, olası bir ihlalin kapsamını ortaya çıkarmak üzere ayrıntılı araştırma yapmak üzere Microsoft 365 Defender portalına erişebilir.

> [!IMPORTANT]
> - Sunucuları izlemek için Bulut için Microsoft Defender kullandığınızda, otomatik olarak bir Uç Nokta için Defender kiracısı oluşturulur (ABD kullanıcıları için ABD'de, Avrupa ve Birleşik Krallık kullanıcıları için AB'de).<br>
Uç Nokta için Defender tarafından toplanan veriler, sağlama sırasında tanımlandığı gibi kiracının coğrafi konumunda depolanır.
> - Bulut için Microsoft Defender kullanmadan önce Uç Nokta için Defender kullanıyorsanız, daha sonra Bulut için Microsoft Defender ile tümleştirseniz bile verileriniz kiracınızı oluştururken belirttiğiniz konumda depolanır.
> - Yapılandırıldıktan sonra, verilerinizin depolandığı konumu değiştiremezsiniz. Verilerinizi başka bir konuma taşımanız gerekiyorsa, kiracıyı sıfırlamak için Microsoft Desteği'a başvurmanız gerekir. <br>
Bu tümleştirmeyi kullanan sunucu uç noktası izlemesi, Office 365 GCC müşterileri için devre dışı bırakıldı.



## <a name="related-topics"></a>İlgili konular
- [Windows'un önceki sürümlerini ekleyin](onboard-downlevel.md)
- [R2, 2016, SAC sürüm 1803 ve 2019 Windows Server 2012 ekleme](configure-server-endpoints.md)
