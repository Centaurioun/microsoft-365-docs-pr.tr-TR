---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824648"
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

    En az sürüm 4.1.0 olduğunu ve Shifts bağlayıcısı cmdlet'lerini içerdiğini doğrulayın.

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