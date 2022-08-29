---
title: Kullanıcılar için güçlü parola gereksinimlerini kapatma
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: bir işletme, okul veya kar amacı gütmeyen kuruluş için parola ilkesini yöneten bir yöneticiyseniz, PowerShell'Azure AD kullanarak güçlü parola gereksinimleri ayarlayabilirsiniz.
ms.openlocfilehash: 72f7e5dd36cf011592daf4bac2e57c438106319a
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441690"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Kullanıcılar için güçlü parola gereksinimlerini kapatma

Bu makalede, kullanıcılarınız için güçlü parola gereksinimlerini nasıl kapattığınız açıklanmaktadır. İş için Microsoft 365 kuruluşunuzda güçlü parola gereksinimleri varsayılan olarak açıktır. Kuruluşunuzun güçlü parolaları devre dışı bırakma gereksinimleri olabilir. Güçlü parola gereksinimlerini kapatmak için aşağıdaki adımları izleyin. PowerShell kullanarak bu adımları tamamlamanız gerekir.

## <a name="before-you-begin"></a>Başlamadan önce

Bu makale, bir işletme, okul veya kar amacı gütmeyen kuruluş için parola ilkesini yöneten kişilere yöneliktir. Bu adımları tamamlamak için Microsoft 365 yönetici hesabınızla oturum açmanız gerekir. [Yönetici hesabı nedir?](../admin-overview/admin-center-overview.md#overview-of-the-microsoft-365-admin-center) Bu adımları gerçekleştirmek için [genel yönetici veya parola yöneticisi](about-admin-roles.md) olmanız gerekir.

PowerShell ile Microsoft 365'e de bağlanmanız gerekir.

## <a name="set-strong-passwords"></a>Güçlü parolalar ayarlama

1. [PowerShell ile Microsoft 365'e bağlanın](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. PowerShell'i kullanarak, aşağıdaki komutu kullanarak tüm kullanıcılar için güçlü parola gereksinimlerini kapatabilirsiniz:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> userPrincipalName, kullanıcı adının ardından at işareti (@) ve bir etki alanı adının geldiği İnternet stilinde oturum açma biçiminde olmalıdır. Örneğin: user@contoso.com.

## <a name="related-content"></a>İlgili içerik

[PowerShell ile Microsoft 365'e bağlanma](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[PowerShell MsolUser komutları hakkında daha fazla bilgi](/powershell/azure/active-directory/install-adv2)

[Parola ilkesi hakkında daha fazla bilgi](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
