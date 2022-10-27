---
title: Temel Mobilite ve Güvenlik'te cihaz erişim ayarlarını yönetme
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basic Mobility ve Security ile yönetemezseniz, e-postaya Exchange ActiveSync uygulama erişimini engelleyin ve kuruluş cihazlarıyla ilgili ayrıntıları almak için PowerShell'i Azure AD kullanın.
ms.openlocfilehash: 833f155570e3234c5731ac23541ca8db7948c403
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720492"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>Temel Mobilite ve Güvenlik'te cihaz erişim ayarlarını yönetme

Temel Mobilite ve Güvenlik kullanıyorsanız, Basic Mobility ve Security ile yönetemediğiniz cihazlar olabilir. Bu durumda, Temel Hareket ve Güvenlik tarafından desteklenmeyen mobil cihazlar için Microsoft 365 e-postasına Exchange ActiveSync uygulama erişimini engellemeniz gerekir. Bu, daha fazla cihaz arasında kuruluş bilgilerinizin güvenliğini sağlar.

Şu adımları kullanın:

1. Genel yönetici hesabınızla Microsoft 365'te oturum açın.

2. Tarayıcınızda şunu yazın: <https://protection.office.com/>.

    > [!IMPORTANT]
    > Microsoft 365 İş Standart için Basic Mobility ve Security'yi ilk kez kullanıyorsanız buradan etkinleştirin: [Temel Güvenlik ve Hareketliliği Etkinleştirme](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Etkinleştirdikten sonra Office 365 [Güvenlik & Uyumluluğu](https://protection.office.com/) ile cihazlarınızı yönetin.

3. **Veri kaybı önleme** \> **Cihaz yönetimi** \> **Cihaz ilkeleri'ne** gidin ve **Kuruluş genelinde cihaz erişim ayarlarını yönet'i** seçin.

4. **Erişim'i** seçin.

    :::image type="content" source="../../media/basic-mobility-security/basic-mobility-access.png" alt-text="Temel Mobilite ve Güvenlik erişimi engelle onay kutusu.":::

5. **Kaydet**'i seçin.

Basic Mobility ve Security'nin hangi cihazları desteklediğini öğrenmek için bkz. [Temel Mobilite ve Güvenlik Özellikleri](capabilities.md).

## <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Temel Mobilite ve Güvenlik ile yönetilen cihazlar hakkında ayrıntılı bilgi edinin

Ayrıca, kuruluşunuzdaki Temel Mobilite ve Güvenlik için ayarladığınız cihazlar hakkında ayrıntılı bilgi almak için Azure AD PowerShell'i kullanabilirsiniz.

Aşağıda, kullanabileceğiniz cihaz ayrıntılarının dökümü yer alır.

|Ayrıntı|PowerShell'de aranacaklar|
|---|---|
|Cihaz Temel Mobilite ve Güvenlik'e kayıtlıdır. Daha fazla bilgi için bkz [. Basic Mobility ve Security kullanarak mobil cihazınızı kaydetme](enroll-your-mobile-device.md)|*isManaged* parametresinin değeri:<br/>**True**= cihaz kaydedildi.<br/>**False**= cihaz kayıtlı değil.|
|Cihaz, cihaz güvenlik ilkelerinizle uyumludur. Daha fazla bilgi için bkz [. Cihaz güvenlik ilkeleri oluşturma](create-device-security-policies.md)|*isCompliant* parametresinin değeri:<br/>**True** = cihaz ilkelerle uyumludur.<br/>**False** = cihaz ilkelerle uyumlu değil.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Temel Mobilite ve Güvenlik PowerShell parametreleri.":::

> [!NOTE]
> İzleyen komutlar ve betikler, [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) tarafından yönetilen tüm cihazlarla ilgili ayrıntıları da döndürür.

Aşağıdaki komutları ve betikleri çalıştırmak için ayarlamanız gereken birkaç şey şunlardır:

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>1. Adım: Windows PowerShell için Azure Active Directory Modülünü indirme ve yükleme

Bu adımlar hakkında daha fazla bilgi için bkz. [PowerShell ile Microsoft 365'e bağlanma](/office365/enterprise/powershell/connect-to-office-365-powershell).

1. [BT Uzmanları için Microsoft Online Services Sign-In Yardımcısı RTWl'a](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) gidin ve **Microsoft Online Services Oturum Açma Yardımcısı için İndir'i** seçin.

2. Windows PowerShell için Microsoft Azure Active Directory Modülünü şu adımlarla yükleyin:

    1. Yönetici düzeyinde bir PowerShell komut istemi açın.

    2. `Install-Module MSOnline` komutunu çalıştırın.

    3. NuGet sağlayıcısını yüklemeniz istenirse Y yazın ve ENTER tuşuna basın.

    4. Modülü PSGallery'den yüklemeniz istenirse Y yazın ve ENTER tuşuna basın.

    5. Yüklemeden sonra PowerShell komut penceresini kapatın.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>2. Adım: Microsoft 365 aboneliğinize bağlanma

1. Windows PowerShell için Windows Azure Active Directory Modülü'nde aşağıdaki komutu çalıştırın.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Windows PowerShell Kimlik Bilgisi İsteği iletişim kutusunda, Microsoft 365 genel yönetici hesabınızın kullanıcı adını ve parolasını yazın ve **tamam'ı** seçin.

3. Aşağıdaki komutu çalıştırın.

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>3. Adım: PowerShell betiklerini çalıştırabildiğinize emin olun

> [!NOTE]
> PowerShell betiklerini çalıştırmak için zaten ayarladıysanız bu adımı atlayabilirsiniz.

Get-MsolUserDeviceComplianceStatus.ps1 betiğini çalıştırmak için PowerShell betiklerinin çalıştırılmasını etkinleştirmeniz gerekir.

1. Windows Masaüstü'nüzden **Başlat'ı** seçin ve Windows PowerShell yazın. Windows PowerShell sağ tıklayın ve yönetici **olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu çalıştırın.

   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

3. İstendiğinde Y yazıp Enter tuşuna basın.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Kuruluşunuzdaki tüm cihazların ayrıntılarını görüntülemek için Get-MsolDevice cmdlet'ini çalıştırın

1. Windows PowerShell için Microsoft Azure Active Directory Modülünü açın.

2. Aşağıdaki komutu çalıştırın.

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Daha fazla örnek için bkz. [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

### <a name="run-a-script-to-get-device-details"></a>Cihaz ayrıntılarını almak için betik çalıştırma

İlk olarak, betiği bilgisayarınıza kaydedin.

1. Aşağıdaki metni kopyalayıp Not Defteri'ne yapıştırın.

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. .ps1 dosya uzantısını kullanarak Windows PowerShell betik dosyası olarak kaydedin; örneğin, Get-MsolUserDeviceComplianceStatus.ps1.

### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Tek bir kullanıcı hesabı için cihaz bilgilerini almak için betiği çalıştırın

1. Windows PowerShell için Microsoft Azure Active Directory Modülünü açın.

2. Betiği kaydettiğiniz klasöre gidin. Örneğin, C:\PS-Scripts'a kaydettiyseniz aşağıdaki komutu çalıştırın.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Cihaz ayrıntılarını almak istediğiniz kullanıcıyı tanımlamak için aşağıdaki komutu çalıştırın. Bu örnek, bar@example.com ayrıntılarını alır.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Betiği başlatmak için aşağıdaki komutu çalıştırın.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Bilgiler Windows Masaüstü'nüze CSV dosyası olarak aktarılır. CSV'nin dosya adını ve yolunu belirtmek için ek parametreler kullanabilirsiniz.

### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Bir kullanıcı grubu için cihaz bilgilerini almak için betiği çalıştırın

1. Windows PowerShell için Microsoft Azure Active Directory Modülünü açın.

2. Betiği kaydettiğiniz klasöre gidin. Örneğin, C:\PS-Scripts'a kaydettiyseniz aşağıdaki komutu çalıştırın.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Cihaz ayrıntılarını almak istediğiniz grubu tanımlamak için aşağıdaki komutu çalıştırın. Bu örnek, FinanceStaff grubundaki kullanıcıların ayrıntılarını alır.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Betiği başlatmak için aşağıdaki komutu çalıştırın.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Bilgiler Windows Masaüstü'nüze CSV dosyası olarak aktarılır. CSV'nin dosya adını ve yolunu belirtmek için ek parametreler kullanabilirsiniz.

## <a name="related-content"></a>İlgili içerik

[Microsoft Connect Kullanımdan Kaldırıldı](/collaborate/connect-redirect)

[Temel Hareketlilik ve Güvenlik'e Genel Bakış](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)