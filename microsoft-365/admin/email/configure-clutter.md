---
title: Kuruluşunuz için İkincil'i yapılandırma
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Exchange PowerShell kullanarak kuruluşunuzdaki tüm veya belirli kullanıcılar için İkincil özelliğini etkinleştirmeyi veya devre dışı bırakmayı öğrenin. '
ms.openlocfilehash: 6858f96c20f7d3028891aae421199379521b5798
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718204"
---
# <a name="configure-microsoft-365-clutter-for-your-organization"></a>Kuruluşunuz için Microsoft 365 İkincil'i yapılandırma

> [!TIP]
> [Odaklanmış Gelen Kutusu](../setup/configure-focused-inbox.md) İkincil'in yerini alacak. Daha fazla bilgi edinin: [Odaklanmış Gelen Kutusu'nu ve İkincil planlarımızı güncelleştirme](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Yönetici olarak, Microsoft 365'teki İkincil özelliğini yönetmeniz gerekebilir. Kuruluşunuzdaki kullanıcılar için İkincil özelliğini açmak/kapatmak için Exchange PowerShell'i kullanmanız gerekir. (Kişiler şu yönergeleri kullanarak bu özelliği açabilir/kapatabilir: [Outlook'ta İkincil özelliğini kapatma/açma](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Exchange [PowerShell'i kullanmayla ilgili ayrıntılar için PowerShell'i Exchange Online ile kullanma](/powershell/exchange/exchange-online-powershell) ve [Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell) makalesine göz atın. En azından Exchange Hizmeti yönetici rolüne ve PowerShell ile Exchange Online bağlanabilen bir hesabınız olması gerekir. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Exchange PowerShell kullanarak İkincil özelliğini açma

[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet'ini çalıştırarak bir posta kutusu için İkincil'i el ile etkinleştirebilirsiniz. Get-Clutter cmdlet'ini çalıştırarak kuruluşunuzdaki posta kutuları için [İkincil](/powershell/module/exchange/get-clutter) ayarlarını da görüntüleyebilirsiniz. 
  
Allie Bellew adlı tek bir kullanıcı için İkincil özelliğini açma
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Exchange PowerShell kullanarak İkincil özelliğini kapatma

[Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet'ini çalıştırarak bir posta kutusu için İkincil özelliğini el ile devre dışı bırakabilirsiniz. **Get-Clutter** cmdlet'ini çalıştırarak kuruluşunuzdaki posta kutuları için [İkincil](/powershell/module/exchange/get-clutter) ayarlarını da görüntüleyebilirsiniz. 
  
Allie Bellew adlı tek bir kullanıcı için İkincil özelliğini kapatın:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Kullanıcılarınızı toplu olarak oluşturmak için PowerShell kullanıyorsanız, İkincil'i yönetmek için her kullanıcının posta kutusunda [Set-Clutter](/powershell/module/exchange/set-clutter) çalıştırmanız gerekir. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>İkincil açma/kapatma düğmesi Web üzerinde Outlook kullanıcılara ne zaman görünür?
<a name="bkmk_onoff"> </a>

Yönetici olarak, Exchange PowerShell kullanarak İkincil özelliğini yeniden etkinleştirebilirsiniz. Bu işlem tamamlandıktan sonra Odaklanmış Gelen Kutusu kapatılır ve İkincil özelliği yeniden etkin olur. 
  
 **Microsoft 365 İş Ekstra aboneliğiyle Web üzerinde Outlook kullanıyorsanız:**
  
- Kullanıcı şu anda İkincil özelliğini etkinleştirmişse: 
    
  - İkincil ayarları görünür
    
- Kullanıcının şu anda Odaklanmış Gelen Kutusu etkinse: 
    
  - İkincil ayarları görünmez
    
- İkincil veya Odaklanmış Gelen Kutusu etkin değilse: 
    
  - Hem İkincil hem de Odaklanmış Gelen Kutusu kullanıcının Posta Ayarları'nda seçenekler olarak görünür
    
 **Outlook.com kullanıyorsanız:**
  
- Kullanıcı şu anda İkincil özelliğini etkinleştirmişse: 
    
  - İkincil ayarları görünür
    
- Kullanıcının şu anda Odaklanmış Gelen Kutusu etkinse: 
    
  - İkincil ayarları görünmez
    
- İkincil veya Odaklanmış Gelen Kutusu etkin değilse: 
    
  - Hem İkincil hem de Odaklanmış Gelen Kutusu kullanıcının Posta Ayarları'nda seçenekler olarak görünür
    
- Kullanıcı geçmişte bir noktada Odaklanmış Gelen Kutusu'nu etkinleştirdiyse:
    
  - İkincil ayarları hiçbir zaman görünmez
    
    Aksi takdir -de 
    
  - İkincil ayarları görüntülenir
    
## <a name="related-content"></a>İlgili içerik

[Outlook'ta düşük öncelikli iletileri sıralamak için İkincil özelliğini kullanma](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (makale)\
[OWA'da düşük öncelikli iletileri sıralamak için İkincil özelliğini kullanma](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (makale)\
[Outlook'ta İkincil özelliğini kapatma](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (makale)
