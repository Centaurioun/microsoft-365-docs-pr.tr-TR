---
title: PowerShell ile Microsoft 365 kullanıcı hesaplarını silme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Microsoft 365 kullanıcı hesaplarını silmek için PowerShell'de farklı modülleri kullanmayı öğrenin.
ms.openlocfilehash: 3ee58698400944b27f6e19d154d7a9d0c8bfccc1
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67560229"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>PowerShell ile Microsoft 365 kullanıcı hesaplarını silme

Kullanıcı hesaplarını silmek ve geri yüklemek için Microsoft 365 için PowerShell'i kullanabilirsiniz.

>[!Note]
>Microsoft 365 yönetim merkezi kullanarak [bir kullanıcı hesabını geri yüklemeyi](../admin/add-users/restore-user.md) öğrenin.
>
>Ek kaynakların listesi için bkz. [Kullanıcıları ve grupları yönetme](/admin).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph için Azure Active Directory PowerShell modülünü kullanma

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Bağlandıktan sonra, tek bir kullanıcı hesabını kaldırmak için aşağıdaki söz dizimini kullanın:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

Bu örnek, kullanıcı hesabı *doku litwareinc.com\@* kaldırır.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Remove-AzureADUser** cmdlet'indeki *-ObjectID* parametresi, hesabın oturum açma adını (Kullanıcı Asıl Adı olarak da bilinir) veya hesabın nesne kimliğini kabul eder.
  
Hesap adını kullanıcının adına göre görüntülemek için aşağıdaki komutları kullanın:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Bu örnekte *Caleb Sills* kullanıcısının hesap adı görüntülenir.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Kullanıcının görünen adına göre bir hesabı kaldırmak için aşağıdaki komutları kullanın:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell için Microsoft Azure Active Directory Modülünü kullanma

Windows PowerShell için Microsoft Azure Active Directory Modülü aracılığıyla bir kullanıcı hesabını sildiğinizde, hesap kalıcı olarak silinmez. Silinen kullanıcı hesabını 30 gün içinde geri yükleyebilirsiniz.

İlk olarak [Microsoft 365 kiracınıza bağlanın](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Kullanıcı hesabını silmek için aşağıdaki söz dizimini kullanın:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core, Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü ve adında *Msol* bulunan cmdlet'leri desteklemez. Bu cmdlet'leri Windows PowerShell çalıştırın.
>

Bu örnek *, BelindaN@litwareinc.com* kullanıcı hesabını siler.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Silinen bir kullanıcı hesabını 30 günlük yetkisiz kullanım süresi içinde geri yüklemek için aşağıdaki söz dizimini kullanın:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

Bu örnek, silinen *BelindaN\@hesabı litwareinc.com* geri yükler.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Geri yüklenebilen silinmiş kullanıcıların listesini görmek için aşağıdaki komutu çalıştırın:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Kullanıcı hesabının özgün kullanıcı asıl adı başka bir hesap tarafından kullanılıyorsa, kullanıcı hesabını geri yüklerken farklı bir kullanıcı asıl adı belirtmek için _UserPrincipalName yerine NewUserPrincipalName_ parametresini kullanın.


## <a name="see-also"></a>Ayrıca bkz.

[PowerShell ile Microsoft 365 kullanıcı hesaplarını, lisanslarını ve gruplarını yönetme](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell ile Microsoft 365’i yönetme](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 için PowerShell'i kullanmaya başlama](getting-started-with-microsoft-365-powershell.md)