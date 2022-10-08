---
title: Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi hakkında sık sorulan sorular
description: MDE cihaz denetimi çıkarılabilir depolama birimiyle ilgili sık sorulan soruların yanıtları.
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.date: 08/25/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 2b76369567e111e429c86a942bd11ab626606ca1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201561"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-frequently-asked-questions"></a>Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Birimi hakkında sık sorulan sorular

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="how-do-i-generate-guid-for-group-idpolicyrule-identry-id"></a>Grup Kimliği/PolicyRule Kimliği/Giriş Kimliği için GUID Nasıl yaparım? oluşturulsun?

GUID'yi çevrimiçi açık kaynak veya PowerShell aracılığıyla oluşturabilirsiniz. Daha fazla bilgi için bkz. [PowerShell aracılığıyla GUID oluşturma](/powershell/module/microsoft.powershell.utility/new-guid).

![PowerShell'de GUID'nin ekran görüntüsü.](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

## <a name="what-are-the-removable-storage-media-and-policy-limitations"></a>Çıkarılabilir depolama ortamı ve ilke sınırlamaları nelerdir?

Arka uç çağrısı, Microsoft Endpoint Manager yönetim merkezinden (Intune) veya Microsoft Graph API aracılığıyla OMA-URI (OKUNACAK GET veya UPDATE) aracılığıyla gerçekleştirilir. Sınırlama, Microsoft'taki xml dosyaları için resmi olarak 350.000 karakter olan herhangi bir OMA-URI özel yapılandırma profiliyle aynıdır.

Örneğin, belirli kullanıcılara "İzin Ver" / "Denetime izin verildi" için kullanıcı SID'i başına iki giriş bloğuna ve sonunda "Reddet" tümüne iki giriş bloğuna ihtiyacınız varsa, 2.276 kullanıcıyı yönetebilirsiniz.

## <a name="why-doesnt-the-policy-work"></a>İlke neden çalışmıyor?

1. En yaygın neden, gerekli [kötü amaçlı yazılımdan koruma istemcisi sürümü](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints) olmamasıdır.

2. Bir diğer neden de XML dosyasının doğru biçimlendirilmemiş olması olabilir. Örneğin, XML dosyasındaki "&" karakteri için doğru markdown biçimlendirmesini kullanmamak veya metin düzenleyicisi dosyaların başına xml ayrıştırma işleminin çalışmamasına neden olan bayt sırası işareti (BOM) 0xEF 0xBB 0xBF ekleyebilir. Basit bir çözüm [, örnek dosyayı](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) indirmek ( **Raw'ı** ve sonra **Farklı kaydet'i** seçin) ve ardından güncelleştirmektir.

3. İlkeyi grup ilkesi kullanarak dağıtıyor ve yönetiyorsanız, tüm PolicyRule'u PolicyRules adlı bir üst düğümde tek bir XML dosyasında birleştirdiğinizden emin olun. Ayrıca tüm Grupları Gruplar adlı bir üst düğümde tek bir XML dosyasında birleştirin. Intune aracılığıyla yönetiyorsanız, bir PolicyRule bir XML dosyası ve bir Grup bir XML dosyası tutun.

Hala çalışmıyorsa desteğe başvurun ve destek kabininizi paylaşın. Bu dosyayı almak için yönetici olarak Komut İstemi'ni kullanın: 

`"%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles`

## <a name="why-is-there-no-configuration-ux-for-some-policy-groups"></a>Bazı ilke grupları için neden yapılandırma UX'si yok? 

grup ilkesi **cihaz denetim ilkesi gruplarını tanımlama** ve **Cihaz denetimi ilkesi kurallarını tanımlama** için yapılandırma UX'si yoktur. Ancak, [WindowsDefender.adml ve WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) dosyalarında **Ham** ve **Farklı Kaydet'i** seçerek ilgili .adml ve [.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) dosyalarını almaya devam edebilirsiniz.

## <a name="how-do-i-confirm-that-the-latest-policy-has-been-deployed-to-the-target-machine"></a>Nasıl yaparım? en son ilkenin hedef makineye dağıtıldığını onaylıyor musunuz?

PowerShell cmdlet'ini `Get-MpComputerStatus` yönetici olarak çalıştırabilirsiniz. Aşağıdaki değer, en son ilkenin hedef makineye uygulanıp uygulanmadığını gösterir.

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

## <a name="how-can-i-know-which-machine-is-using-out-of-date-anti-malware-client-version-in-the-organization"></a>Kuruluşta hangi makinenin eski kötü amaçlı yazılımdan koruma istemcisi sürümünü kullandığını nasıl bilebilirim?

Microsoft 365 güvenlik portalında kötü amaçlı yazılımdan koruma istemcisi sürümünü almak için aşağıdaki sorguyu kullanabilirsiniz:

```kusto
//check the anti-malware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```

## <a name="how-do-i-find-the-media-property-in-the-device-manager"></a>Aygıt Yöneticisi media özelliğini Nasıl yaparım? buldunuz?

1. Medyayı takın.

2. Aygıt Yöneticisi açın. 

   ![Aygıt Yöneticisi ekran görüntüsü.](https://user-images.githubusercontent.com/81826151/181859412-affd6aa1-09ad-44bf-9541-330499cc2c87.png)

3. Aygıt Yöneticisi medyayı bulun, sağ tıklayın ve **özellikler'i** seçin.

   :::image type="content" alt-text="Aygıt Yöneticisi medyanın ekran görüntüsü." source="https://user-images.githubusercontent.com/81826151/181859700-62a6f704-b12e-41e3-a048-7d63432654a4.png":::

4. **Ayrıntılar'ı** açın ve **Özellikler'i** seçin.

   :::image type="content" alt-text="Aygıt Yöneticisi'deki cihaz özelliğinin ekran görüntüsü." source="https://user-images.githubusercontent.com/81826151/181859852-00bc8b11-8ee5-4d46-9770-fa29f894d13f.png":::
    