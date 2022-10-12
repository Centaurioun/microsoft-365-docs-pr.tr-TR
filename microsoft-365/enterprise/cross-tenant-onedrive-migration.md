---
title: Kiracılar arası OneDrive geçişi
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Kiracılar arası OneDrive geçişi
ms.openlocfilehash: 0d2076ed4b74cd8bbe21e5d7e7b6e1d0189f822d
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537427"
---
# <a name="cross-tenant-onedrive-migration"></a>Kiracılar arası OneDrive geçişi

>[!Note]
> Bu makaledeki bilgiler **, Kiracılar arası OneDrive geçişi** anlamına gelir. [Kiracılar arası Posta Kutusu geçişi hakkında buradan bilgi edinin](/microsoft-365/enterprise/cross-tenant-mailbox-migration)

Birleştirmeler veya dalışlar sırasında genellikle kullanıcı OneDrive hesaplarınızı yeni bir Microsoft 365 kiracısına taşımanız gerekir. Kiracılar arası OneDrive geçişiyle, kiracı yöneticileri kullanıcıları yeni kuruluşlarına aktarmak için *SharePoint Online PowerShell* gibi tanıdık araçları kullanabilir.

İki ayrı kiracının SharePoint yöneticileri, bir kuruluş ilişkisi oluşturmak *için Set-SPOCrossTenantRelationship* cmdlet'ini ve Kiracılar Arası OneDrive taşımalarını başlatmak için *Start-SPOCrossTenantUserContentMove* komutunu kullanabilir.

Belirli bir zamanda geçiş için en fazla 4.000 OneDrive hesabı zamanlanabilir. Zamanlandıktan sonra, geçişler kullanıcının verileri Microsoft 365 bulutunu terk etmeden ve minimum kesintiyle gerçekleşir ve kullanıcının OneDrive'ını salt okunur hale gelmesi için yalnızca birkaç dakika gerekir. Geçişler tamamlandığında, kullanıcının özgün OneDrive konumuna bir yeniden yönlendirme yerleştirilir, böylece dosya ve klasörlere yönelik tüm bağlantılar yeni konumda çalışmaya devam edebilir. 

>[!Important]
>- OneDrive'ları kiracılar arası geçirilen her kullanıcının Kiracılar Arası Kullanıcı Verileri Geçişi lisansına sahip olması gerekir.
>- Microsoft Purview Müşteri Anahtarı ile Hizmet Şifrelemesi kullanan müşteriler için kiracılar arası OneDrive geçişi kullanılamaz. [Microsoft Purview Müşteri Anahtarı ile Hizmet şifrelemesi hakkında bilgi edinin - Microsoft Purview](/microsoft-365/compliance/customer-key-overview?view=o365-worldwide)