---
title: Posta iletilerini okurken kullanılan belleği azaltmak için yalın açılır pencereleri kullanma
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Bu makale, Web üzerinde Outlook'da ileti indirme performansını geliştirmek için yalın açılır pencereleri kullanmaya yönelik bilgiler içerir.
ms.custom: seo-marvel-apr2020
ms.collection: scotvorg
ms.openlocfilehash: d266ba44930adbdc41f06c2e4b1658f9efa9bc35
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191727"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Posta iletilerini okurken kullanılan belleği azaltmak için yalın açılır pencereleri kullanma

Bu makale, Web üzerinde Outlook'da ileti indirme performansını geliştirmeye yönelik bilgiler içerir. Bu makale, [Office 365 projesi için ağ planlama ve performans ayarlamanın](./network-planning-and-performance.md) bir parçasıdır.
  
Office 365 **Uygulama Yönetici**, **Genel yönetici** veya **Kullanıcı Yönetici** olarak, microsoft Edge veya Internet Explorer'da belirli e-posta iletilerinin daha küçük, daha az bellek kullanan bir sürümü olan _yalın açılır_ pencereler sunmak için Web üzerinde Outlook yapılandırabilirsiniz. Yalın açılır pencereler Web üzerinde Outlook için yapılandırıldığında, performansı en iyi duruma getiren sunucu tarafı işlenmiş bileşenler yüklenir.
  
> [!NOTE]
> Mart 2018 itibarıyla bilgi hakları yönetimi (IRM) gibi kullanım hakları kısıtlamalarını belirten iletilerde yalın açılır pencereler kullanılamaz.
  
Bu özellikler ana pencerede çalışmaya devam eder ancak yalın açılır pencerelerde kullanılamaz:
  
- Outlook eklentileri
  
- Skype Kurumsal iletişim durumu
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Office 365 kuruluşunuzdaki tüm kullanıcılar için yalın açılır pencereleri yapılandırmak için
  
1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet'ini LeanPopoutEnabled parametresiyle aşağıdaki gibi çalıştırın:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Örneğin, kuruluşunuzdaki tüm kullanıcılar için yalın açılır pencereleri etkinleştirmek için:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Kuruluşunuzdaki tüm kullanıcılar için yalın açılır pencereleri devre dışı bırakmak için:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
