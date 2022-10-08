---
title: PowerShell ile Microsoft 365 kullanıcı hesaplarını engelleme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Microsoft 365 hesaplarına erişimi engellemek ve engellemesini kaldırmak için PowerShell'i kullanma.
ms.openlocfilehash: ab212909aa0fa664bee42ac7d5ca74b4b29f7994
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68163458"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>PowerShell ile Microsoft 365 kullanıcı hesaplarını engelleme

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Bir Microsoft 365 hesabına erişimi engellediğinizde, microsoft 365 kuruluşunuzdaki hizmet ve verilere erişmek için herkesin hesabı kullanmasını engellersiniz. Tek veya birden çok kullanıcı hesabına erişimi engellemek için PowerShell'i kullanabilirsiniz.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph için Azure Active Directory PowerShell modülünü kullanma

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="block-access-to-individual-user-accounts"></a>Tek tek kullanıcı hesaplarına erişimi engelleme

Tek bir kullanıcı hesabını engellemek için aşağıdaki söz dizimini kullanın:

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> **Set-AzureAD** cmdlet'indeki *-ObjectID* parametresi, Kullanıcı Asıl Adı olarak da bilinen hesap oturum açma adını veya hesabın nesne kimliğini kabul eder.

Bu örnek *, fabricec@litwareinc.com* kullanıcı hesabına erişimi engeller.

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Bu kullanıcı hesabının engelini kaldırmak için aşağıdaki komutu çalıştırın:

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Kullanıcının görünen adına göre kullanıcı hesabı UPN'sini görüntülemek için aşağıdaki komutları kullanın:

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

Bu örnekte  *, Caleb Sills* kullanıcısı için kullanıcı hesabı UPN'sini görüntüler.

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Kullanıcının görünen adına göre bir hesabı engellemek için aşağıdaki komutları kullanın:

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Kullanıcı hesabının engellenen durumunu denetlemek için aşağıdaki komutu kullanın:

```powershell
Get-AzureADUser  -ObjectID <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Birden çok kullanıcı hesabını engelleme

Birden çok kullanıcı hesabına erişimi engellemek için, her satırda aşağıdaki gibi bir hesap oturum açma adı içeren bir metin dosyası oluşturun:

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

Aşağıdaki komutlarda örnek metin dosyası *C:\My Documents\Accounts.txt* şeklindedir. Bu dosya adını, metin dosyanızın yolu ve dosya adıyla değiştirin.

Metin dosyasında listelenen hesaplara erişimi engellemek için aşağıdaki komutu çalıştırın:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

Metin dosyasında listelenen hesapların engelini kaldırmak için aşağıdaki komutu çalıştırın:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell için Microsoft Azure Active Directory Modülünü kullanma

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="block-individual-user-accounts"></a>Tek tek kullanıcı hesaplarını engelleme

Tek bir kullanıcı hesabına erişimi engellemek için aşağıdaki söz dizimini kullanın:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core, Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü ve adında *Msol* bulunan cmdlet'leri desteklemez. Bu cmdlet'leri Windows PowerShell çalıştırmanız gerekir.

Bu örnek, kullanıcı hesabı *doku litwareinc.com\@* erişimini engeller.

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Kullanıcı hesabının engelini kaldırmak için aşağıdaki komutu çalıştırın:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Kullanıcı hesabının engellenen durumunu denetlemek için aşağıdaki komutu çalıştırın:

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Birden çok kullanıcı hesabı için erişimi engelleme

İlk olarak, her satırda aşağıdaki gibi bir hesap içeren bir metin dosyası oluşturun:

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

Aşağıdaki komutlarda örnek metin dosyası *C:\My Documents\Accounts.txt* şeklindedir. Bu dosya adını, metin dosyanızın yolu ve dosya adıyla değiştirin.

Metin dosyasında listelenen hesapların erişimini engellemek için aşağıdaki komutu çalıştırın:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Metin dosyasında listelenen hesapların engelini kaldırmak için aşağıdaki komutu çalıştırın:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Ayrıca bkz.

[PowerShell ile Microsoft 365 kullanıcı hesaplarını, lisanslarını ve gruplarını yönetme](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[PowerShell ile Microsoft 365’i yönetme](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 için PowerShell'i kullanmaya başlama](getting-started-with-microsoft-365-powershell.md)
