---
title: Uç Nokta için Microsoft Defender'de cihaz durumu raporlama
description: Cihaz durumunu, virüsten koruma durumunu ve sürümlerini, işletim sistemi platformlarını ve Windows 10 sürümlerini izlemek için cihaz durumu raporunu kullanın.
keywords: sistem durumu, virüsten koruma, işletim sistemi platformu, windows 10 sürümü, sürüm, sistem durumu, uyumluluk, durum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: d26415db3a43dc4628daad3ce8c795ab293a1570
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731706"
---
# <a name="device-health-reports-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'da cihaz durumu raporları

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cihaz Durumu raporu, kuruluşunuzdaki cihazlar hakkında bilgi sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını, Windows 10 sürümlerini ve Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini gösteren popüler bilgileri içerir.

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

Microsoft 365 Güvenlik panosu gezinti panelinde **Raporlar'ı** seçin ve ardından **Cihaz durumu ve uyumluluğu'nu** açın.
Cihaz durumu ve uyumluluk panosu iki sekmede yapılandırılmıştır:

- [**Algılayıcı sistem durumu & işletim** sistemi sekmesi](device-health-sensor-health-os.md#sensor-health--os-tab), aşağıdaki cihaz özniteliklerini görüntüleyen üç karta ayrılmış genel işletim sistemi bilgileri sağlar:
  - [Algılayıcı sistem durumu kartı](device-health-sensor-health-os.md#sensor-health-card)
  - [İşletim sistemleri ve platformlar kartı](device-health-sensor-health-os.md#operating-systems-and-platforms-card)
  - [Windows sürümleri kartı](device-health-sensor-health-os.md#windows-versions-card)

- [**Microsoft Defender Virüsten Koruma sistem durumu sekmesinde Microsoft**](device-health-microsoft-defender-antivirus-health.md#microsoft-defender-antivirus-health-tab) Defender Virüsten Koruma'nın özelliklerini bildiren sekiz kart vardır:
  - [Virüsten koruma modu kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-mode-card)
  - [Virüsten koruma altyapısı sürüm kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-engine-version-card)
  - [Virüsten koruma güvenlik bilgileri sürüm kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-security-intelligence-version-card)
  - [Virüsten koruma platformu sürüm kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-platform-version-card)
  - [En son virüsten koruma tarama sonuçları kartı](device-health-microsoft-defender-antivirus-health.md#recent-antivirus-scan-results-card)
  - [Virüsten koruma altyapısı güncelleştirme kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-engine-updates-card)
  - [Güvenlik bilgileri güncelleştirme kartı](device-health-microsoft-defender-antivirus-health.md#security-intelligence-updates-card)
  - [Virüsten koruma platformu güncelleştirme kartı](device-health-microsoft-defender-antivirus-health.md#antivirus-platform-updates-card)

## <a name="report-access-permissions"></a>Rapor erişim izinleri

Microsoft 365 Güvenlik panosunda Cihaz durumu ve virüsten koruma uyumluluk raporuna erişmek için aşağıdaki izinler gereklidir:

| İzin adı | İzin türü |
|:---|:---|
| Verileri Görüntüle | Tehdit ve güvenlik açığı yönetimi (TVM) |

Bu izinleri atamak için:

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.
1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).
1. Düzenlemek istediğiniz rolü seçin.
1. **Düzenle'yi** seçin.
1. **Rolü düzenle'nin** **Genel** sekmesindeki **Rol adı** alanına rol için bir ad yazın.
1. **Açıklama** alanına rolün kısa bir özetini yazın.
1. **İzinler'de** **Verileri Görüntüle'yi** seçin ve **Verileri Görüntüle'nin** altında **Tehdit ve güvenlik açığı yönetimi** (TVM) öğesini seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [Rol tabanlı erişim denetimi için roller oluşturun ve yönetin](user-roles.md).
- [Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)
