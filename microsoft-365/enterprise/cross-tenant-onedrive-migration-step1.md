---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 1. Adım
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: OneDrive Kiracılar arası geçiş özelliğinin 1. adımı
ms.openlocfilehash: 59bb8047f1b85d1f8d9cc4843ecc3e0337cef5c2
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807552"
---
# <a name="step-1-connect-to-the-source-and-target-tenants"></a>1. Adım: Kaynak ve hedef kiracılara bağlanma

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 1. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- **1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)**
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

## <a name="before-you-begin"></a>Başlamadan önce

- **PowerShell'i Microsoft Office SharePoint Online**. En son sürümün yüklü olduğunu onaylayın. Aksi takdirde, [Resmi Microsoft İndirme Merkezi'nden SharePoint Online Yönetim Kabuğu'nu indirin](/download/details.aspx?id=35588).
- Hem kaynak hem de hedef kiracılarda SharePoint Online yöneticisi veya Microsoft 365 Genel yöneticisi olun


### <a name="connect-to-both-tenants"></a>Her iki kiracıya da bağlanma

1. SharePoint Yönetim Kabuğu'nda SharePoint Online yöneticisi veya Microsoft 365 Genel yöneticisi olarak oturum açın.
2. **Kaynak** kiracı URL'sini girerek aşağıdakileri çalıştırın: 

    ```powershell
    Connect-SPOService -url https://<TenantName>-admin.sharepoint.com
    ```

3. İstendiğinde, Yönetici kullanıcı adınızı ve parolanızı kullanarak **kaynak** kiracıda oturum açın.
 
4. **Hedef** kiracı URL'sini girerek aşağıdakileri çalıştırın: 

    ```powershell
    Connect-SPOService -url https://<TenantName>-admin.sharepoint.com
    ```

5. İstendiğinde, Yönetici kullanıcı adınızı ve parolanızı kullanarak **hedef** kiracıda oturum açın.

>[!Important]
>**Microsoft 365 Multi-Geo müşterileri:** Her coğrafyayı ayrı bir kiracı olarak değerlendirmelisiniz. Geçiş işlemi boyunca coğrafyaya özgü doğru URL'leri sağlayın.

## <a name="step-2-establish-trust-between-the-source-and-target-tenants"></a>2. Adım: [Kaynak ve hedef kiracılar arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md)