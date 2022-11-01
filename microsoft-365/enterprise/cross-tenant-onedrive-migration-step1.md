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
ms.openlocfilehash: b9bb72707e11e3257eabac093e4a76daa903bf40
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806292"
---
# <a name="step-1-cross-tenant-onedrive-migration---connect-to-the-source-and-target-tenants"></a>1. Adım: Kiracılar arası OneDrive geçişi - Kaynak ve hedef kiracılara bağlanma

Kiracılar arası OneDrive geçişinizin ilk adımı hem SharePoint kaynağınıza hem de hedef kiracınıza bağlanmaktır.

## <a name="before-you-begin"></a>Başlamadan önce

- **PowerShell'i Microsoft Office SharePoint Online**. En son sürümün yüklü olduğunu onaylayın. Aksi takdirde, [Resmi Microsoft İndirme Merkezi'nden SharePoint Online Yönetim Kabuğu'nu indirin](/download/details.aspx?id=35588).
- Hem kaynak hem de hedef kiracılarda SharePoint Online yöneticisi veya Microsoft 365 Genel yöneticisi olun.


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