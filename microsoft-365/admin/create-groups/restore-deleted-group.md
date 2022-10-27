---
title: Silinen bir Microsoft 365 grubunu geri yükleme
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Silinen bir grup 30 gün boyunca saklanır ve yine de grubu geri yükleyebilirsiniz. 30 gün sonra grup ve içeriği kalıcı olarak silinir.
ms.openlocfilehash: ea154fa9a1533fdabf4cc9b1a8a6c50cd62cacff
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726738"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Silinen bir Microsoft 365 grubunu geri yükleme

Bir grubu sildiyseniz, grup varsayılan olarak 30 gün boyunca korunur. Grubu geri yükleyebildiğiniz için bu 30 günlük süre "geçici silme" olarak kabul edilir. 30 gün sonra grup ve ilişkili içeriği kalıcı olarak silinir ve geri yüklenemez.

Grup geri yüklendiğinde, aşağıdaki içerikler geri yüklenir:
  
- Azure Active Directory (AD) nesnesi, özellikleri ve üyeleri Microsoft 365 Grupları.
    
- Grubun e-posta adresleri.
    
- Paylaşılan Gelen Kutusu'nu ve takvimi Exchange Online.
    
- SharePoint Online ekip sitesi ve dosyaları.
    
- OneNote not defteri
    
- Planner
    
- Teams

- Yammer grubu ve grup içeriği (Microsoft 365 grubu Yammer'dan oluşturulduysa)

- Power BI [Klasik çalışma alanı](/power-bi/collaborate-share/service-create-workspaces)

> [!NOTE]
> Bu makalede yalnızca Microsoft 365 gruplarının geri yüklenmesi açıklanmaktadır. Diğer tüm gruplar silindikten sonra geri yüklenemez.

## <a name="restore-a-group"></a>Grubu geri yükleme

# <a name="outlook"></a>[Outlook](#tab/outlook)

Bir Microsoft 365 grubunun sahibiyseniz, aşağıdaki adımları izleyerek grubu Web üzerinde Outlook'da kendiniz geri yükleyebilirsiniz:

1. [Silinen gruplar sayfasında](https://outlook.office.com/people/group/deleted), **Gruplar** düğümü altındaki **Grupları yönet** seçeneğini ve ardından **Silinmiş'i** seçin.

2. Geri yüklemek istediğiniz grubun yanındaki **Geri Yükle** sekmesine tıklayın.

Silinen grup burada görünmüyorsa bir yöneticiye başvurun.

# <a name="admin-center"></a>[Yönetici merkezi](#tab/admin-center)

Genel yönetici veya grup yöneticisiyseniz, silinen bir grubu Microsoft 365 yönetim merkezi geri yükleyebilirsiniz:

1. [Yönetim merkezine](https://admin.microsoft.com) gidin.
2. **Gruplar'ı** genişletin ve **ardından Silinmiş gruplar'a** tıklayın.
3. Geri yüklemek istediğiniz grubu seçin ve ardından **Grubu geri yükle'ye** tıklayın.

> [!NOTE]
> Bazı durumlarda, grubun ve tüm verilerinin geri yüklenmesi 24 saat kadar sürebilir. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 Grupları hakkında sorularınız mı var?

Microsoft 365 gruplarıyla ilgili sorular göndermek ve konuşmalara katılmak için [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) ziyaret edin. 
  
## <a name="related-content"></a>İlgili içerik

[PowerShell ile Microsoft 365 Grupları yönetme](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (makale)\
[Remove-UnifiedGroup cmdlet'ini kullanarak grupları silme](/powershell/module/exchange/remove-unifiedgroup) (makale)\
[Gruba bağlı ekip sitesi ayarlarınızı yönetme](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (makale)\
[Outlook'ta grubu silme](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (makale)
