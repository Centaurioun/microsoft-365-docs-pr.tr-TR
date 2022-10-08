---
title: PowerShell ile parolaları yönetme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Parolaları yönetmek için PowerShell kullanmayı öğrenin.
ms.openlocfilehash: ce8a8520d43f4ea3254fb5fb2d0c5128fced54d0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185391"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell ile parolaları yönetme

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft 365'te parolaları yönetmek için Microsoft 365 yönetim merkezi alternatif olarak Microsoft 365 için PowerShell'i kullanabilirsiniz. 

Bu makaledeki bir komut bloğu değişken değerleri belirtmenizi gerektirdiğinde bu adımları kullanın.

1. Komut bloğunu panoya kopyalayın ve Not Defteri'ne veya PowerShell Tümleşik Betik Ortamı'na (ISE) yapıştırın.
2. Değişken değerlerini doldurun ve "<" ve ">" karakterlerini kaldırın.
3. Komutları PowerShell penceresinde veya PowerShell ISE'de çalıştırın.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph için Azure Active Directory PowerShell modülünü kullanma

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="set-a-password"></a>Parola ayarlama

Kullanıcı hesabı için parola belirtmek için bu komutları kullanın.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>Kullanıcıyı parolasını değiştirmeye zorlama

Parola ayarlamak ve kullanıcıyı yeni parolasını değiştirmeye zorlamak için bu komutları kullanın.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

Parola ayarlamak ve bir sonraki oturum açışında kullanıcıyı yeni parolasını değiştirmeye zorlamak için bu komutları kullanın.

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell için Microsoft Azure Active Directory Modülünü kullanma

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="set-a-password"></a>Parola ayarlama

Kullanıcı hesabı için parola belirtmek için bu komutları kullanın.

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>Kullanıcıyı parolasını değiştirmeye zorlama

Bir kullanıcıyı parolasını değiştirmeye zorlamak için bu komutları kullanın.

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>Ayrıca bkz.

[PowerShell ile Microsoft 365 kullanıcı hesaplarını, lisanslarını ve gruplarını yönetme](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell ile Microsoft 365’i yönetme](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 için PowerShell'i kullanmaya başlama](getting-started-with-microsoft-365-powershell.md)

