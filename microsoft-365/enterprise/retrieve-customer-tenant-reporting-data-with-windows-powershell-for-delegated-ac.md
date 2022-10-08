---
title: DAP iş ortakları için Windows PowerShell ile müşteri kiracı raporlama verilerini alma
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
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Özet: Tek tek müşteri kiracılarından rapor almak için Microsoft Exchange Online için uzak Windows PowerShell kullanın.'
ms.openlocfilehash: 88d23874b3dbf3d392937c11365870acc85ea9f7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195533"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Temsilci Erişim İzinleri (DAP) iş ortakları için Windows PowerShell ile müşteri kiracı raporlama verilerini alma

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Tek tek müşteri kiracılarından rapor almak için Microsoft Exchange Online için uzak Windows PowerShell kullanın.

Dağıtım ve Bulut Çözümü Sağlayıcısı (CSP) iş ortakları, müşteri kiracı raporlarını oluşturan verilere doğrudan Exchange Online PowerShell için uzak Windows PowerShell üzerinden erişebilir. Bu yöntem, iş ortaklarının raporlama verilerini toplayıp kaydetmesine ve ardından üzerinde başka işlemler gerçekleştirmesine olanak tanır. Uzak bağlantıyı açtıktan sonra, müşteri kiracısı hakkındaki raporlama verilerini almak, herhangi bir cmdlet'i müşteri kiracısına göre çalıştırmakla aynıdır.

Bu makalede, tek bir müşteri kiracısına bağlanmak ve rapor almak için Exchange Online için uzak Windows PowerShell nasıl kullanabileceğiniz açıklanmaktadır. Varsayılan olarak, Windows PowerShell birden çok müşteri kiracısından raporlama verilerini toplamayı desteklemez. Bu yordamla aldığınız raporlar yalnızca bağlandığınız  _DelegatedOrg_ için geçerlidir.

## <a name="before-you-begin"></a>Başlamadan önce

- Uzak Windows PowerShell kullanarak Exchange Online kiracınıza bağlanın. Yönergeler için bkz. [Temsilci Erişim İzinleri (DAP) iş ortakları için uzak Windows PowerShell ile Exchange Online kiracılara bağlanma](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Get-StaleMailboxReport örneğini çalıştırma

Exchange Online uzak oturumu açtıktan sonra, 25.03.2015 ile 31.03.2015 tarihleri arasında **Get-StaleMailboxReport** değerini almak için aşağıdaki komutu çalıştırın.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Exchange Online, Lync Online, SharePoint Online ve kullanabileceğiniz ileti izleme için diğer hizmetler için başka birçok raporlama cmdlet'i vardır. Kullanılabilir raporlama cmdlet'leri hakkında daha fazla bilgi edinmek için aşağıdaki bölümde listelenen makalelere bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Office 365 Raporlama web hizmeti](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Exchange Online'de raporlama cmdlet'leri](/powershell/module/exchange/get-csclientdevicedetailreport)

[İş ortakları için yardım](https://go.microsoft.com/fwlink/p/?LinkID=533477)
