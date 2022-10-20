---
title: Uç Nokta için Microsoft Defender’da güvenlik duvarı raporlama oturumu düzenleyin
description: Microsoft 365 Defender portalında güvenlik duvarı raporlamayı barındırın ve görüntüleyin.
keywords: windows defender, güvenlik duvarı
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
search.appverid: met150
ms.openlocfilehash: 4ee445ba46eebf912251849b2f4f2aec0edb9282
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644603"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender’da güvenlik duvarı raporlama oturumu düzenleyin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Genel yönetici veya güvenlik yöneticisiyseniz artık güvenlik duvarı raporlamasını [Microsoft 365 Defender portalında](https://security.microsoft.com) barındırabilirsiniz. Bu özellik, Windows güvenlik duvarı raporlamasını merkezi bir konumdan görüntülemenizi sağlar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- R2 veya sonraki Windows Server 2012 Windows 10 veya üzerini çalıştırıyor olmanız gerekir.
     > [!NOTE]
     > Windows2012 R2 ve Windows Server 2016'nin Güvenlik Duvarı raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).
- Cihazları Uç Nokta için Microsoft Defender hizmetine eklemek için [buraya](onboard-configure.md) bakın.
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalın</a> verileri almaya başlaması için Gelişmiş Güvenlik özellikli Windows Defender Güvenlik Duvarı için **Denetim Olaylarını** etkinleştirmeniz gerekir:
  - [Denetim Filtreleme Platformu Paket Bırakma](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [Filtre Platformu Bağlantısını Denetle](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- grup ilkesi Nesne Düzenleyicisi, Yerel Güvenlik İlkesi veya auditpol.exe komutlarını kullanarak bu olayları etkinleştirin. Daha fazla bilgi için [buraya](/windows/win32/fwp/auditing-and-logging) bakın.
  - İki PowerShell komutu şunlardır:
    - `auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable`
    - `auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable`

```powershell
param (
    [switch]$remediate
)
try {

    $categories = "Filtering Platform Packet Drop,Filtering Platform Connection"
    $current = auditpol /get /subcategory:"$($categories)" /r | ConvertFrom-Csv    
    if ($current."Inclusion Setting" -ne "failure") {
        if ($remediate.IsPresent) {
            Write-Host "Remediating. No Auditing Enabled. $($current | ForEach-Object {$_.Subcategory + ":" + $_.'Inclusion Setting' + ";"})"
            $output = auditpol /set /subcategory:"$($categories)" /failure:enable
            if($output -eq "The command was successfully executed.") {
                Write-Host "$($output)"
                exit 0
            }
            else {
                Write-Host "$($output)"
                exit 1
            }
        }
        else {
            Write-Host "Remediation Needed. $($current | ForEach-Object {$_.Subcategory + ":" + $_.'Inclusion Setting' + ";"})."
            exit 1
        }
    }

}
catch {
    throw $_
} 
```

## <a name="the-process"></a>İşlem

> [!NOTE]
> Yukarıdaki bölümde yer alan yönergeleri izlediğinizden ve cihazlarınızı erken önizleme katılımı için düzgün yapılandırdığından emin olun.

- Olayları etkinleştirdikten sonra Microsoft 365 Defender verileri izlemeye başlar ve bunlar şunlardır: 
   - Uzak IP
   - Uzak Bağlantı Noktası
   - Yerel Bağlantı Noktası
   - Yerel IP
   - Bilgisayar Adı
   - Gelen ve giden bağlantılar arasında işlem gerçekleştirme
- Yöneticiler artık windows ana bilgisayar güvenlik duvarı etkinliğini [burada](https://security.microsoft.com/firewall) görebilir.
   - Power BI kullanarak Windows Defender Güvenlik Duvarı etkinliklerini izlemek için [Özel Raporlama betiğini](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) indirerek ek raporlama kolaylaştırılabilir.
   - Verilerin yansıtılabilmesi 12 saat kadar sürebilir.

## <a name="supported-scenarios"></a>Desteklenen senaryolar

- [Güvenlik duvarı raporlama](#firewall-reporting)
- ["Bağlantısı engellenen bilgisayarlar"dan cihaza](#from-computers-with-a-blocked-connection-to-device)
- [Gelişmiş avcılık (önizleme yenilemesi) detayına gitme](#drill-into-advanced-hunting-preview-refresh)

### <a name="firewall-reporting"></a>Güvenlik duvarı raporlama

Güvenlik duvarı rapor sayfalarına bazı örnekler aşağıda verilmiştir. Burada gelen, giden ve uygulama etkinliğinin özetini bulabilirsiniz. Bu sayfaya doğrudan adresine giderek <https://security.microsoft.com/firewall>erişebilirsiniz.

:::image type="content" source="images/host-firewall-reporting-page.png" alt-text="Konak güvenlik duvarı raporlama sayfası" lightbox="\images\host-firewall-reporting-page.png":::

Bu raporlara, **Güvenlik Duvarı Engellenen Gelen Bağlantılar** kartının en altında bulunan **Raporlar** > **Güvenlik Raporu** > **Cihazları** (bölüm) bölümüne giderek de erişilebilir.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>"Bağlantısı engellenen bilgisayarlar"dan cihaza

Kartlar etkileşimli nesneleri destekler. Yeni bir sekmede Microsoft 365 Defender portalını başlatacak ve sizi doğrudan **Cihaz Zaman Çizelgesi** sekmesine götürecek cihaz adına tıklayarak bir cihazın etkinliğinde detaya gidebilirsiniz.

:::image type="content" source="images/firewall-reporting-blocked-connection.png" alt-text="Bağlantısı engellenen bilgisayarlar sayfası" lightbox="\images\firewall-reporting-blocked-connection.png":::

Artık **Zaman Çizelgesi** sekmesini seçebilirsiniz. Bu sekme, size bu cihazla ilişkili olayların listesini verir.

Görüntüleme bölmesinin sağ üst köşesindeki **Filtreler** düğmesine tıkladıktan sonra istediğiniz olay türünü seçin. Bu durumda **Güvenlik duvarı olayları'nı** seçtiğinizde bölme Güvenlik duvarı olayları olarak filtrelenir.

:::image type="content" source="images/firewall-reporting-filters-button.png" alt-text="Filtreler düğmesi" lightbox="\images\firewall-reporting-filters-button.png":::

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Gelişmiş avcılık (önizleme yenilemesi) detayına gitme

Güvenlik duvarı raporları, Gelişmiş **Avcılığı Aç** düğmesine tıklayarak doğrudan karttan **Gelişmiş Avcılık'a** detaya gitme desteği verir. Sorgu önceden doldurulur.

:::image type="content" source="images/firewall-reporting-advanced-hunting.png" alt-text="Gelişmiş avcılığı aç düğmesi" lightbox="\images\firewall-reporting-advanced-hunting.png":::

Sorgu artık yürütülebilir ve son 30 güne ait tüm ilgili Güvenlik Duvarı olayları incelenebilir.

Daha fazla raporlama veya özel değişiklik için sorgu, daha fazla analiz için Power BI'a aktarılabilir. Power BI kullanarak Windows Defender Güvenlik Duvarı etkinliklerini izlemek için [Özel Raporlama betiği](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) indirilerek özel raporlama kolaylaştırılabilir.
