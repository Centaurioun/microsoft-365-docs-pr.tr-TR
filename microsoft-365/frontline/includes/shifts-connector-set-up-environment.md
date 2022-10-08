---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 7415d4dfd8d6a7a1935d9aca2e04726f7b929996
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222616"
---
1. PowerShell sürüm 7 veya üzerini yükleyin. Adım adım yönergeler için bkz [. PowerShell'i Windows'a yükleme](/powershell/scripting/install/installing-powershell-on-windows).

1. PowerShell'i yönetici modunda çalıştırın.
1. Microsoft Graph PowerShell modülünü yükleyin.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Sürüm 1.6.1 veya üzeri olduğunu doğrulayın.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Teams Preview PowerShell modülünü yükleyin.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    En az sürüm 4.7.0 olduğunu ve Shifts bağlayıcı cmdlet'lerini içerdiğini doğrulayın.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Betik çalıştırılırken bir hata oluşursa PowerShell'i çıkış olarak ayarlayın.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Betiklerin Windows'ta çalıştırılmasını etkinleştirin.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```