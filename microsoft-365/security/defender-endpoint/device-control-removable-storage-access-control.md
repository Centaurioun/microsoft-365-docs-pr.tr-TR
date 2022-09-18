---
title: Uç Nokta için Microsoft Defender Aygıt Denetimi Çıkarılabilir Depolama birimi Access Control, çıkarılabilir depolama medyası
description: Uç Nokta için Microsoft Defender hakkında kılavuz
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
ms.date: 09/15/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 9a5add52188afcecc4df6a369f65468e79452e95
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799406"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama birimi Access Control

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> Bu ürünün grup ilkesi yönetimi ve Intune OMA-URI/Özel İlke yönetimi genel kullanıma sunuldu (4.18.2106): [Teknik Topluluk blogu: Çıkarılabilir depolama alanınızı ve yazıcınızı Uç Nokta için Microsoft Defender ile koruma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

## <a name="overview"></a>Genel bakış

Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi Access Control özelliği, dışlamayla veya dışlamadan çıkarılabilir depolama birimine okuma, yazma veya yürütme erişimini denetlemenizi, izin vermenizi veya engellemenizi sağlar.

|Ayrıcalık|Izni|
|---|---|
|Access|Okuma, Yazma, Yürütme|
|Eylem Modu|Denetim, İzin Ver, Engelle|
|CSP Desteği|Evet|
|GPO Desteği|Evet|
|Kullanıcı Tabanlı Destek|Evet|
|Makine Tabanlı Destek|Evet|

Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi Access Control özelliği size aşağıdaki özellikleri sağlar:

### <a name="prepare-your-endpoints"></a>Uç noktalarınızı hazırlama

Kötü amaçlı yazılımdan koruma istemcisi sürümü **4.18.2103.3 veya** sonraki bir sürüme sahip Windows 10 ve Windows 11 cihazlarda Çıkarılabilir Depolama Birimi Access Control dağıtın.

- **4.18.2104 veya üzeri**: , , `VID_PID`dosya yolu tabanlı GPO desteği ve `SerialNumberId``ComputerSid`

- **4.18.2105 veya üzeri**: için `HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId`joker karakter desteği ekleyin, belirli makinedeki belirli kullanıcının birleşimi, kaldırılabilir SSD (SanDisk Extreme SSD)/USB Bağlı SCSI (UAS) desteği

- **4.18.2107 veya üzeri**: Windows Taşınabilir Cihaz (WPD) desteği ekleme (tabletler gibi mobil cihazlar için); [gelişmiş avlanmaya](device-control-removable-storage-access-control.md#view-data-in-microsoft-defender-for-endpoint) ekleme `AccountName`

- **4.18.2205 veya üzeri**: Varsayılan zorlamayı **Yazıcı** olarak genişletin. **Bunu Reddet** olarak ayarlarsanız, Yazıcı da engellenir, bu nedenle yalnızca depolama alanını yönetmek istiyorsanız Yazıcı'ya izin vermek için özel bir ilke oluşturduğunuzdan emin olun

:::image type="content" source="images/powershell.png" alt-text="PowerShell arabiriminin ekran görüntüsü" lightbox="images/powershell.png":::

> [!NOTE]
> Windows Güvenliği durumundan bağımsız olarak Çıkarılabilir Depolama Birimi Access Control çalıştırabildiğiniz için Windows Güvenliği bileşenlerin hiçbirinin etkin olmaması gerekir.

## <a name="device-control-removable-storage-access-control-properties"></a>Cihaz Denetimi Çıkarılabilir Depolama Birimi Access Control özellikleri

Çıkarılabilir Depolama Birimi Access Control Çıkarılabilir depolama grubu oluşturma ve erişim ilkesi kuralı oluşturma içerir:

- Çıkarılabilir depolama grubu, grup oluşturmanıza olanak tanır. Örneğin, yetkili USB grubu veya şifrelenmiş USB grubu.
- Erişim ilkesi kuralı, her çıkarılabilir depolama grubunu kısıtlamak için ilke oluşturmanıza olanak tanır. Örneğin, yalnızca yetkili kullanıcının Erişim yetkili USB grubu yazmasına izin verin.
- Belirli bir çıkarılabilir depolama sınıfını engellemek ancak belirli bir medyaya izin vermek için '`IncludedIdList` aracılığıyla bir grup `PrimaryId` ve `ExcludedIDList` /etc aracılığıyla`HardwareId``DeviceId`\/ bir grup kullanabilirsiniz.' Ek yönergeler için bkz. [Intune OMA-URI kullanarak Çıkarılabilir Depolama Access Control dağıtma](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri).

Grup ve ilke XML dosyalarını oluştururken kullanabileceğiniz özellikler şunlardır.

### <a name="removable-storage-group"></a>Çıkarılabilir depolama grubu

|Özellik Adı|Açıklama|Seçenekler|
|---|---|---|
|**Groupıd**|Benzersiz bir kimlik olan GUID, grubu temsil eder ve ilkede kullanılır.||
|**DescriptorIdList**|Grupta ele almak için kullanmak istediğiniz cihaz özelliklerini listeleyin. Tüm özellikler büyük/küçük harfe duyarlıdır. |**PrimaryId**: Birincil kimlik `RemovableMediaDevices`, , `CdRomDevices`, `WpdDevices``PrinterDevices`içerir. <p>**InstancePathId**: InstancePathId, sistemdeki cihazı benzersiz olarak tanımlayan bir dizedir; örneğin, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`. Aygıt Yöneticisi`Device instance path`. Sonundaki sayı (örneğin &0) kullanılabilir yuvayı temsil eder ve cihazdan cihaza değişebilir. En iyi sonuçları elde için sonunda joker karakter kullanın. Örneğin, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`. <p>**DeviceId**: Cihaz Kimliği biçimine dönüştürmek `Device instance path` için bkz. [Standart USB Tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers), örneğin, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07` <p>**HardwareId**: Sistemdeki cihazı tanımlayan bir dize, örneğin. `USBSTOR\DiskGeneric_Flash_Disk___8.07` Aygıt Yöneticisi`Hardware Ids`. <br>**Not**: Donanım Kimliği benzersiz değildir; farklı cihazlar aynı değeri paylaşabilir.<p>**FriendlyNameId**: Cihaza bağlı bir dizedir; örneğin, `Generic Flash Disk USB Device`. Aygıt Yöneticisi`Friendly name`. <p>**BusId**: Örneğin, USB, SCSI <p>**SerialNumberId**: SerialNumberId `Device instance path` değerini Aygıt Yöneticisi bulabilirsiniz; örneğin, `03003324080520232521` USBSTOR\DISK&VEN__USB&PROD__SANDISK_3.2GEN1&REV_1.00&0'da\\`03003324080520232521` SerialNumberId değeridir <p>**VID_PID**: Satıcı Kimliği, USB komitesinin satıcıya atadığını dört basamaklı satıcı kodudur. Ürün Kimliği, satıcının cihaza atadığını dört basamaklı ürün kodudur. Joker karakteri destekler. Satıcı Kimliği ve Ürün Kimliği biçimine dönüştürmek `Device instance path` için bkz. [Standart USB Tanımlayıcıları](/windows-hardware/drivers/install/standard-usb-identifiers). Örneğin: <br>`0751_55E0`: bu tam VID/PID çifti eşleştir<br>`_55E0`: HERHANGI bir medyayı PID=55E0 ile eşleştirme <br>`0751_`: VID=0751 ile herhangi bir medyayı eşleştirme <p> **Not**: [Aygıt Yöneticisi'da özelliğin nasıl bulunu](device-control-removable-storage-access-control-faq.md#how-do-i-find-the-media-property-in-the-device-manager) olduğunu anlamak için bkz. Aygıt Yöneticisi media özelliğini bulmak Nasıl yaparım??|
|**Matchtype**|içinde `DescriptorIDList`kullanılan birden çok cihaz özelliği olduğunda, MatchType ilişkiyi tanımlar.|**MatchAll**: altındaki `DescriptorIdList` tüm öznitelikler **And** ilişkisi olur; örneğin, yönetici bağlı her USB için ve `InstancePathID`eklerse `DeviceID` sistem USB'nin her iki değeri de karşılayıp karşılamadığını denetler. <p> **MatchAny**: DescriptorIdList altındaki öznitelikler **Or** ilişkisi olacaktır; örneğin, yönetici bağlı her USB için ve `InstancePathID`koyarsa`DeviceID`, USB'de aynı **DeviceID** veya **InstanceID** değeri olduğu sürece sistem uygulamayı yapar.|

### <a name="access-policy-rule"></a>Erişim ilkesi kuralı

Erişim denetimi ilkesini oluşturmak için aşağıdaki özellikleri kullanabilirsiniz:

| Özellik Adı | Açıklama | Seçenekler |
|---|---|---|
| **PolicyRule Kimliği** | Benzersiz bir kimlik olan GUID, ilkeyi temsil eder ve raporlama ve sorun giderme işlemlerinde kullanılır. | |
| **IncludedIdList** | İlkenin uygulanacağı gruplar. Birden çok grup eklenirse, ilke tüm bu gruplardaki herhangi bir medyaya uygulanır.|Bu örnekte Grup Kimliği/GUID kullanılmalıdır. <p> Aşağıdaki örnekte GroupID kullanımı gösterilmektedir: <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | İlkenin uygulanmayacağı gruplar. | Bu örnekte Grup Kimliği/GUID kullanılmalıdır. |
| **Giriş Kimliği** | Bir PolicyRule birden çok girdiye sahip olabilir; benzersiz GUID'ye sahip her giriş, Cihaz Denetimi'ne bir kısıtlama bildirir.| |
| **Tür** | IncludedIDList içindeki çıkarılabilir depolama grupları için eylemi tanımlar. <p>Zorlama: İzin Ver veya Reddet <p>Denetim: AuditAllowed veya AuditDenied<p> | İzin ver<p>Inkar <p>AuditAllowed: Erişime izin verildiğinde bildirim ve olayı tanımlar <p>AuditDenied: Erişim reddedildiğinde bildirimi ve olayı tanımlar; **Deny** girdisiyle birlikte çalışması gerekir.<p> Aynı medya için çakışma türleri olduğunda, sistem ilkedeki ilki uygular. Çakışma türüne örnek olarak **İzin Ver** ve **Reddet** yer alır. |
| **Sid** | Yerel kullanıcı SID'i veya kullanıcı SID grubu ya da AD nesnesinin SID'i, bu ilkenin belirli bir kullanıcı veya kullanıcı grubuna uygulanıp uygulanmayacağını tanımlar. Bir girdi en fazla bir SID'ye sahip olabilir ve sid içermeyen bir giriş ilkenin makineye uygulanması anlamına gelir. |  |
| **ComputerSID** | Yerel bilgisayar SID veya bilgisayar SID grubu veya AD nesnesinin SID'si, bu ilkenin belirli bir makine veya makine grubuna uygulanıp uygulanmayacağını tanımlar. Bir girdi en fazla bir ComputerSID'ye sahip olabilir ve herhangi bir ComputerSID içermeyen bir giriş, ilkenin makineye uygulanması anlamına gelir. Belirli bir kullanıcıya ve belirli bir makineye giriş uygulamak istiyorsanız, aynı Girdiye hem SID hem de ComputerSID ekleyin. |  |
| **Seçenekler** | Bildirimin görüntülenip görüntülenmeyeceğini tanımlar |**İzin Ver Türü seçildiğinde**: <p>0: hiçbir şey<p>4: Bu Giriş için **AuditAllowed** ve **AuditDenied'i** devre dışı bırakın. **allow** gerçekleşse ve AuditAllowed ayarı yapılandırılmış olsa bile sistem olay göndermez. <p>8: Dosya bilgilerini yakalayın ve Yazma erişimi için kanıt olarak dosyanın bir kopyasını alın. <p>16: Yazma erişimi için dosya bilgilerini yakalayın. <p>**Tür Reddetme seçildiğinde**: <p>0: hiçbir şey<p>4: Bu Giriş için **AuditDenied'i** devre dışı bırakın. **Block** gerçekleşse ve AuditDenied ayarı yapılandırılmış olsa bile sistem bildirim göstermez. <p>****AuditAllowed** Türü seçildiğinde**: <p>0: hiçbir şey <p>1: hiçbir şey <p>2: olay gönderme<p> ****AuditDenied** Türü seçildiğinde**: <p>0: hiçbir şey <p>1: bildirimi göster <p>2: olay gönderme<p>3: bildirim gösterme ve olay gönderme |
|Accessmask|Erişimi tanımlar. | **Disk düzeyinde erişim**: <p>1: Okuma <p>2: Yazma <p>4: Yürütme <p>**Dosya sistemi düzeyinde erişim**: <p>8: Dosya sistemi Okuma <p>16: Dosya sistemi Yazma <p>32: Dosya sistemi yürütme <p><p>İkili VEYA işlemi gerçekleştirerek birden çok erişiminiz olabilir; örneğin Okuma ve Yazma ve Yürütme için AccessMask değeri 7 olur; Okuma ve Yazma için AccessMask 3 olacaktır.|

Belirli yönergeler için bkz:

| Konu | Açıklama |
|---|---|
| [grup ilkesi kullanarak Çıkarılabilir Depolama Birimi Access Control dağıtma](deploy-manage-removable-storage-group-policy.md) | İlkeyi dağıtmak için grup ilkesi kullanın.|
| [Intune OMA-URI kullanarak Çıkarılabilir Depolama birimi Access Control dağıtma](deploy-manage-removable-storage-intune.md) | İlkeyi dağıtmak için Intune kullanın.|

## <a name="view-data-in-microsoft-defender-for-endpoint"></a>verileri Uç Nokta için Microsoft Defender'de görüntüleme

[Microsoft 365 Defender portalı](https://security.microsoft.com/advanced-hunting), Cihaz Denetimi Çıkarılabilir Depolama Birimi Access Control tarafından tetiklenen olayları gösterir. Microsoft 365 güvenliğine erişmek için aşağıdaki aboneliğe sahip olmanız gerekir:

- E5 için Microsoft 365 raporlama

İlkenizde veya `AuditDenied` yapılandırılmışsa ve **Seçenekler'de** **Olayı gönder** seçiliyse`AuditAllowed`, sistem veya oturum açan kullanıcı tarafından başlatılmış olmasına bakılmaksızın, her kapsanan erişim için (`AccessMask`girişte) Gelişmiş avcılık veya Cihaz denetimi raporuna bir olay gönderilir.

```kusto
//RemovableStoragePolicyTriggered: event triggered by Disk level enforcement
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
| extend parsed=parse_json(AdditionalFields)
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)
| extend MediaBusType = tostring(parsed.BusType)
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId)
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

```kusto
//information of file written to removable storage
DeviceEvents
| where ActionType contains "RemovableStorageFileEvent"
| extend parsed=parse_json(AdditionalFields)
| extend Policy = tostring(parsed.Policy)
| extend PolicyRuleId = tostring(parsed.PolicyRuleId)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaInstanceId = tostring(parsed.InstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
| extend FileInformationOperation = tostring(parsed.DuplicatedOperation)
| extend FileEvidenceLocation = tostring(parsed.TargetFileLocation)
| project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, Policy, PolicyRuleId, FileInformationOperation, MediaClassName, MediaInstanceId, MediaName, MediaProductId, MediaVendorId, MediaSerialNumber, FileName, FolderPath, FileSize, FileEvidenceLocation, AdditionalFields
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Çıkarılabilir depolama biriminin engelini gösteren ekran.":::
