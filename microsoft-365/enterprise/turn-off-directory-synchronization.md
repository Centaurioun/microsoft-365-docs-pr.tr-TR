---
title: Microsoft 365 için dizin eşitlemeyi kapatma
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: Bu makalede, Microsoft 365 için dizin eşitlemesini kapatmak için PowerShell kullanma hakkında bilgi bulabilirsiniz.
ms.openlocfilehash: 32609aafa42ece651064f4ea0b772b15409ea4ff
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191771"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Microsoft 365 için dizin eşitlemeyi kapatma
Dizin eşitlemesini kapatmak ve eşitlenen kullanıcılarınızı yalnızca buluta dönüştürmek için PowerShell'i kullanabilirsiniz. Ancak, sorun giderme adımı olarak dizin eşitlemesini kapatmanız önerilmez. Dizin eşitleme sorunlarını giderme konusunda yardıma ihtiyacınız varsa [Microsoft 365 için dizin eşitleme sorunlarını giderme](fix-problems-with-directory-synchronization.md) makalesine bakın. 
  
Gerekirse iş ürünleri için [desteğe başvurun](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="turn-off-directory-synchronization"></a>Dizin eşitlemeyi kapatma  
Dizin eşitlemesini kapatmak için:
  
1. İlk olarak gerekli yazılımı yükleyin ve Microsoft 365 aboneliğinize bağlanın. Yönergeler için bkz[. Windows PowerShell için Microsoft Azure Active Directory Modülü ile bağlanma](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Dizin eşitlemesini devre dışı bırakmak için [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) kullanın: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Bu komutu kullanırsanız, dizin eşitlemesini yeniden açabilmeniz için 72 saat beklemeniz gerekir.
>
