---
title: Cihaz Denetimi Yazıcı Korumasını Uç Nokta için Microsoft Defender
description: Uç Nokta için Microsoft Defender Cihaz Denetimi Yazıcı Koruması, kişilerin şirket dışı yazıcılar veya onaylanmamış USB yazıcılar aracılığıyla yazdırmasını engeller.
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: dansimp
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.subservice: mde
ms.topic: article
ms.collection:
- m365-security
- tier3
ms.custom: admindeeplinkDEFENDER
search.appverid: met150
ms.openlocfilehash: c93cb1d3280976337a6174f15c2a668b9d84091b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231758"
---
# <a name="device-control-printer-protection"></a>Cihaz Denetimi Yazıcı Koruması

**Uygulandığı öğe**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Uç Nokta için Microsoft Defender Cihaz Denetimi Yazıcı Koruması, kişilerin şirket dışı yazıcılar veya onaylanmamış USB yazıcılar aracılığıyla yazdırmasını engeller.

## <a name="licensing"></a>Lisanslama

Yazıcı Koruması'yla çalışmaya başlamadan önce [Microsoft 365 aboneliğinizi onaylamanız](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) gerekir. Yazıcı Koruması'na erişmek ve kullanmak için aşağıdakilere sahip olmanız gerekir:

- İşlevsellik/ilke dağıtımı için Microsoft 365 E3
- Raporlama için Microsoft 365 E5

## <a name="permission"></a>Izni

Intune'da İlke dağıtımı için, ilkeyi OMA-URI aracılığıyla dağıtmak için hesabın cihaz yapılandırma profillerini oluşturma, düzenleme, güncelleştirme veya silme izinlerine sahip olması gerekir. Özel roller oluşturabilir veya şu izinlere sahip yerleşik rollerden herhangi birini kullanabilirsiniz:

- İlke ve profil Yöneticisi rolü.
- Veya Cihaz Yapılandırması profilleri için Raporları Oluşturma/Düzenleme/Güncelleştirme/Okuma/Silme/Görüntüleme izinlerinin açık olduğu özel rol
- Veya Genel yönetici

Cihaz yapılandırma raporlarını görmek için hesabın rapor görüntüleme izinlerine sahip olması gerekir. Özel roller oluşturabilir veya yerleşik rolleri şu izinlerle kullanabilirsiniz:

- Genel güvenlik yöneticisi
- Güvenlik yöneticisi
- Güvenlik Okuyucusu

## <a name="prepare-your-endpoints"></a>Uç noktalarınızı hazırlama

Bu gereksinimleri karşılamak için Yazıcı Koruması'nı dağıtmayı planladığınız Windows 10 veya Windows 11 cihazlardan emin olun.

1. Aşağıdaki Windows Güncelleştirmeler yüklenir.
    - Windows 1809 için: [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) Windows Update yükleyin
    - Windows 1909 için: [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1) Windows Update yükleyin
    - Windows 2004 veya üzeri için

2. İlkeyi grup ilkesi aracılığıyla dağıtmayı planlıyorsanız, cihazın Uç Nokta için Microsoft Defender katılmış olması gerekir; ilkeyi Microsoft Endpoint Manager aracılığıyla dağıtmayı planlıyorsanız, cihazın Microsoft Intune kullanılarak birleştirilmiş olması gerekir.

## <a name="deploy-device-control-printer-protection-policy"></a>Cihaz Denetimi Yazıcı Koruması ilkesini dağıtma

İlkeyi grup ilkesi veya Intune aracılığıyla dağıtabilirsiniz.

<br>

****

|Başlık|Açıklama|CSP Desteği | GPO Desteği | Kullanıcı Tabanlı Destek | Makine Tabanlı Destek |
|---|---|:---:|:---:|:---:|:---:|
|**Cihaz denetimi Yazdırma Kısıtlamalarını Etkinleştirme**|Kişilerin şirket dışı yazıcı aracılığıyla yazdırmalarını engelleme|Evet|Evet|Evet|Evet|
|**Onaylı USB bağlantılı yazdırma cihazlarının listesi**\*|Belirli BIR USB yazıcısına izin ver|Evet|Evet|Evet|Evet|
|

\* Bu ilke **, Cihaz Denetimi Yazdırma Kısıtlamalarını Etkinleştir** ile birlikte kullanılmalıdır.

## <a name="deploy-policy-via-intune"></a>İlkeyi Intune aracılığıyla dağıtma

Intune için, şu anda Cihaz Denetimi Yazıcı Koruması yalnızca OMA-URI'yi destekler.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Senaryo 1: kişilerin Intune kullanarak şirket dışı yazıcılar aracılığıyla yazdırmalarını engelleme

- makine üzerinden ilke uygulama:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- kullanıcı üzerinden ilke uygulama:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

ILE CSP destek dizesi `<enabled/>`:

:::image type="content" source="../../media/customeditrow.png" alt-text="Özel sayfası" lightbox="../../media/customeditrow.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Senaryo 2: Intune kullanarak onaylanan belirli USB yazıcılara izin ver

- makine üzerinden ilke uygulama:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- kullanıcı üzerinden ilke uygulama:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

'ApprovedUsbPrintDevices' özelliği aracılığıyla onaylı USB yazıcıları olan CSP destek dizesi, örneğin `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`:

:::image type="content" source="../../media/editrow.png" alt-text="Satırı Düzenle bölmesi" lightbox="../../media/editrow.png":::

## <a name="deploy-policy-via-group-policy"></a>İlkeyi grup ilkesi aracılığıyla dağıtma

Cihaz Intune katılmadıysa, ilkeyi grup ilkesi aracılığıyla da dağıtabilirsiniz.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Senaryo 1: grup ilkesi kullanarak kişilerin şirket dışı yazıcılar aracılığıyla yazdırmalarını engelleme

- makine üzerinden ilke uygulama:

  Bilgisayar Yapılandırması \> Yönetim Şablonları \> Yazıcısı: Cihaz denetimi Yazdırma Kısıtlamalarını Etkinleştirme

- kullanıcı üzerinden ilke uygulama:

  Yazıcılar Denetim Masası \> Kullanıcı Yapılandırması \> Yönetim Şablonları \> : Cihaz denetimi yazdırma kısıtlamalarını etkinleştirme

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="Cihaz Denetimi Yazdırma Kısıtlamalarını Etkinleştir bölmesi" lightbox="../../media/enable-device-ctrl-printing-restrictions.png":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Senaryo 2: grup ilkesi kullanarak onaylanan belirli USB yazıcılara izin ver

- makine üzerinden ilke uygulama:

  Bilgisayar Yapılandırması \> Yönetim Şablonları \> Yazıcısı: Onaylı USB bağlantılı yazdırma cihazlarının listesi

- kullanıcı üzerinden ilke uygulama:

  Yazıcılar Denetim Masası \> Kullanıcı Yapılandırması \> Yönetim Şablonları \> : Onaylı USB bağlantılı yazdırma cihazlarının listesi

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="Onaylı USB bağlantılı yazdırma cihazlarının listesi" lightbox="../../media/list-of-approved-connected-print-devices.png":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Uç Nokta için Microsoft Defender portalında Cihaz Denetimi Yazıcı Koruması verilerini görüntüleme

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalı</a>, yukarıdaki Cihaz Denetimi Yazıcı Koruması ilkesi tarafından engellenen yazdırmayı gösterir.

```kusto
DeviceEvents
| where ActionType == 'PrintJobBlocked'
| extend parsed=parse_json(AdditionalFields)
| extend PrintedFile=tostring(parsed.JobOrDocumentName)
| extend PrintPortName=tostring(parsed.PortName)
| extend PrinterName=tostring(parsed.PrinterName)
| extend Policy=tostring(parsed.RestrictionReason) 
| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName, Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields
| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="gelişmiş avcılık" lightbox="../../media/device-control-advanced-hunting.png":::

 PnP olayını kullanarak kuruluşta kullanılan USB yazıcıyı bulabilirsiniz:

```kusto
//find the USB Printer VID/PID
DeviceEvents
| where ActionType == "PnpDeviceConnected"
| extend parsed=parse_json(AdditionalFields)
| extend DeviceDescription = tostring(parsed.DeviceDescription) 
| extend PrinterDeviceId = tostring(parsed.DeviceId) 
| extend VID_PID_Array = split(split(PrinterDeviceId, "\\")[1], "&")
| extend VID_PID = replace_string(strcat(VID_PID_Array[0], '/', VID_PID_Array[1]), 'VID_', '')
| extend VID_PID = replace_string(VID_PID, 'PID_', '')
| extend ClassId = tostring(parsed.ClassId) 
| extend VendorIds = tostring(parsed.VendorIds) 
| where DeviceDescription == 'USB Printing Support'
| project Timestamp , DeviceId, DeviceName, ActionType, DeviceDescription, VID_PID, ClassId, PrinterDeviceId, VendorIds, parsed
| order by Timestamp desc
```

 :::image type="content" source="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png" alt-text="Gelişmiş Avcılık sayfası" lightbox="https://user-images.githubusercontent.com/81826151/128954383-71df3009-77ef-40db-b575-79c73fda332b.png":::
