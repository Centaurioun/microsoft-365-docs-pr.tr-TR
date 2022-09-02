---
title: Uç Nokta için Microsoft Defender'de sorun giderme modunu kullanmaya başlama
description: Çeşitli virüsten koruma sorunlarını gidermek için Uç Nokta için Microsoft Defender sorun giderme modunu açın.
keywords: virüsten koruma, sorun giderme, sorun giderme modu, kurcalama koruması, uyumluluk
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: efe3ea8feb30e1177ff2c156fd6ccb284708a5b4
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523324"
---
# <a name="get-started-with-troubleshooting-mode-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de sorun giderme modunu kullanmaya başlama 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Uç Nokta için Microsoft Defender sorun giderme modu, çeşitli Microsoft Defender virüsten koruma özelliklerini cihazdan etkinleştirerek ve kuruluş ilkesi tarafından denetlense bile farklı senaryoları test ederek sorun gidermenize olanak tanır. Sorun giderme modu varsayılan olarak devre dışıdır ve bir cihaz (ve/veya cihaz grubu) için sınırlı bir süre için açmanızı gerektirir. Bunun yalnızca Kurumsal bir özellik olduğunu ve Microsoft 365 Defender erişim gerektirdiğini unutmayın.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Kurcalama koruma ayarını devre dışı bırakmak/değiştirmek için sorun giderme modunu kullanın:

  - Microsoft Defender Virüsten Koruma işlevsel sorun giderme /uygulama uyumluluğu (hatalı pozitif uygulama blokları).
  - Microsoft Defender Virüsten Koruma performans sorunlarını giderme, sorun giderme modunu kullanarak ve kurcalama korumasını ve diğer virüsten koruma ayarlarını değiştirerek.

- Bir kurcalama olayı oluşursa (örneğin, `MpPreference` anlık görüntü değiştirilir veya silinir), sorun giderme modu sona erer ve cihazda kurcalama koruması etkinleştirilir.

- Uygun izinlere sahip yerel yöneticiler, genellikle ilke tarafından kilitlenen tek tek uç noktalarda yapılandırmaları değiştirebilir. Bir cihazın sorun giderme modunda olması, Microsoft Defender Virüsten Koruma performans ve uyumluluk senaryolarını tanılarken yararlı olabilir.

  - Yerel yöneticiler Microsoft Defender Virüsten Koruma'yı kapatamaz veya kaldıramaz.
  - Yerel yöneticiler Microsoft Defender Virüsten Koruma paketindeki diğer tüm güvenlik ayarlarını yapılandırabilecektir (örneğin, bulut koruması, kurcalama koruması).

- "Güvenlik ayarlarını yönetme" izinlerine sahip yöneticilerin sorun giderme modunu açma erişimi olacaktır.

- Uç Nokta için Microsoft Defender, sorun giderme işlemi boyunca günlükleri ve araştırma verilerini toplar.

  - `MpPreference` Sorun giderme modu başlamadan önce anlık görüntüsü alınır.
  - sorun giderme modunun süresi dolmadan hemen önce ikinci anlık görüntü alınır.
  - Sorun giderme modundan işletimsel günlükler de toplanır.

  - Yukarıdaki tüm günlükler ve anlık görüntüler toplanır ve yöneticinin cihaz sayfasındaki [Araştırma paketi toplama](respond-machine-alerts.md#collect-investigation-package-from-devices) özelliğini kullanarak toplaması için kullanılabilir. Yönetici tarafından toplanana kadar Microsoft'un bu verileri cihazdan kaldırmayacağını unutmayın.

- Yöneticiler, cihaz sayfasındaki **Olay Görüntüleyicisi** sorun giderme modu sırasında gerçekleşen ayarlardaki değişiklikleri de gözden geçirebilir.

- Sorun giderme modu son kullanma süresine ulaştıktan sonra otomatik olarak kapanır (3 saat sürer). Süre dolduktan sonra, ilkeyle yönetilen tüm yapılandırmalar yeniden salt okunur hale gelir ve sorun giderme modunu açmadan önceki haline döner.

- Komutun Microsoft 365 Defender cihazda etkin hale gelmesi 15 dakika kadar sürebilir.

- Sorun giderme modu başladığında ve sorun giderme modu sona erdiğinde son kullanıcıya bildirim gönderilir. Yakında sona ereceğini bildiren bir uyarı da gönderilir.

- Sorun giderme modunun başlangıcı ve sonu, cihaz sayfasındaki **Cihaz Zaman Çizelgesi'nde** tanımlanır.

- Gelişmiş tehdit avcılığında tüm sorun giderme modu olaylarını sorgulayabilirsiniz.

> [!NOTE]
> sorun giderme modunda etkin olduğunda makineye ilke yönetimi değişiklikleri uygulanır. Ancak, sorun giderme modunun süresi dolana kadar değişiklikler geçerli olmaz. Ayrıca, Microsoft Defender Virüsten Koruma Platformu güncelleştirmeleri Sorun Giderme modu sırasında uygulanmaz. Sorun giderme modu bir Windows güncelleştirmesi ile sona erdiğinde platform güncelleştirmeleri uygulanır.

## <a name="prerequisites"></a>Önkoşullar

- Windows 10 (sürüm 19044.1618 veya üzeri), Windows 11, Windows Server 2019 veya Windows Server 2022 çalıştıran bir cihaz.

  Sömestr/Redstone|İşletim sistemi sürümü|Sürüm
  :---|:---|:---
  21H2/SV1|>=22000,593|[KB5011563: Microsoft Update Kataloğu](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011563)
  20H1/20H2/21H1|>=19042.1620<br/> >=19041.1620<br/> >=19043.1620|[KB5011543: Microsoft Update Kataloğu](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011543)
  Windows Server 2022|>=20348.617|[KB5011558: Microsoft Update Kataloğu](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011558)
  Windows Server 2019 (RS5)|>=17763.2746|[KB5011551: Microsoft Update Kataloğu](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011551)

- Sorun giderme modunun uygulanabilmesi için Uç Nokta için Microsoft Defender cihazda kiracıya kaydedilmiş ve etkin olmalıdır.

- Cihazın etkin olarak Microsoft Defender Virüsten Koruma, sürüm 4.18.2203 veya üzerini çalıştırıyor olması gerekir.

## <a name="enable-the-troubleshooting-mode"></a>Sorun giderme modunu etkinleştirme

1. Microsoft 365 Defender portalına ()<https://security.microsoft.com> gidin ve oturum açın.

2. Sorun giderme modunu açmak istediğiniz cihazın cihaz sayfasına/makine sayfasına gidin. **Sorun giderme modunu aç'ı** seçin. Bunun Uç Nokta için Microsoft Defender için "Güvenlik Merkezi'nde güvenlik ayarlarını yönetme" izinleri gerektirdiğini unutmayın.

   :::image type="content" source="../../media/ts-mode-menu.png" alt-text="Sorun giderme modunu açma" lightbox="../../media/ts-mode-menu.png":::

3. Cihaz için sorun giderme modunu açmak istediğinizi onaylayın.

   :::image type="content" source="../../media/ts-mode-conf-flyout.png" alt-text="Yapılandırma açılır öğesi" lightbox="../../media/ts-mode-conf-flyout.png":::

4. Cihaz sayfasında cihazın artık sorun giderme modunda olduğu gösterilir.

   :::image type="content" source="../../media/ts-mode-option-greyed-out.png" alt-text="Cihaz artık sorun giderme modunda" lightbox="../../media/ts-mode-option-greyed-out.png":::

## <a name="advanced-hunting-queries"></a>Gelişmiş tehdit avcılığı sorguları

Ortamınızda gerçekleşen sorun giderme olaylarına görünürlük sağlamak için önceden oluşturulmuş bazı gelişmiş avcılık sorgularını aşağıda bulabilirsiniz. Bu sorguları, cihazlar sorun giderme modundayken sizi uyaracak [algılama kuralları oluşturmak](/defender/custom-detection-rules.md#create-a-custom-detection-rule) için de kullanabilirsiniz.

### <a name="get-troubleshooting-events-for-a-particular-device"></a>Belirli bir cihaz için sorun giderme olaylarını alma
İlgili satırları açıklama satırı yaparak deviceId veya deviceName ölçütüne göre arama gerçekleştirin.  
```kusto
//let deviceName = "<deviceName>";   // update with device name
let deviceId = "<deviceID>";   // update with device id
DeviceEvents
| where DeviceId == deviceId
//| where DeviceName  == deviceName
| where ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| project Timestamp,DeviceId, DeviceName, _tsmodeproperties,
 _tsmodeproperties.TroubleshootingState, _tsmodeproperties.TroubleshootingPreviousState, _tsmodeproperties.TroubleshootingStartTime,
 _tsmodeproperties.TroubleshootingStateExpiry, _tsmodeproperties.TroubleshootingStateRemainingMinutes,
 _tsmodeproperties.TroubleshootingStateChangeReason, _tsmodeproperties.TroubleshootingStateChangeSource
```

### <a name="devices-currently-in-troubleshooting-mode"></a>Şu anda sorun giderme modunda olan cihazlar  

```kusto
DeviceEvents
| where ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
|summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| order by Timestamp desc
```

### <a name="count-of-troubleshooting-mode-instances-by-device"></a>Cihaza göre sorun giderme modu örneklerinin sayısı

```kusto
DeviceEvents
| where ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(30d)  // choose the date range you want
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| sort by count_
```

### <a name="total-count"></a>Toplam sayı

```kusto
DeviceEvents
| where ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(2d) //beginning of time range
| where Timestamp < ago(1d) //end of time range
| where _tsmodeproperties.TroubleshootingStateChangeReason contains "started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count()
| where count_ > 5          // choose your max # of TS mode instances for your time range
```

## <a name="related-topic"></a>İlgili konu

- [Sorun giderme modu senaryoları](troubleshooting-mode-scenarios.md)
- [Değişiklik korumasıyla güvenlik ayarlarını koruyun](prevent-changes-to-security-settings-with-tamper-protection.md)
