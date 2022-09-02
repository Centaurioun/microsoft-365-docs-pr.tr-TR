---
title: Microsoft 365'te dizin eşitleme hatalarını görüntüleme
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
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: dizin eşitleme hatalarını ve olası düzeltmeleri Microsoft 365 yönetim merkezi görüntülemeyi öğrenin.
ms.openlocfilehash: bbbff97b424c65b92affca67cae338efb0220b87
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67560339"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Microsoft 365'te dizin eşitleme hatalarını görüntüleme

dizin eşitleme hatalarını <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> görüntüleyebilirsiniz. Yalnızca Kullanıcı nesnesi hataları görüntülenir. PowerShell hatalarını görüntülemek için bkz. [DirSyncProvisioningErrors ile nesneleri tanımlama](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi dizin eşitleme hatalarını görüntüleme

Microsoft 365 yönetim merkezi hataları görüntülemek için:
  
1. genel yönetici hesabıyla [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın. 
    
2. **Giriş** sayfasında **Kullanıcı yönetimi** kartını görürsünüz. 
    
    ![Microsoft 365 yönetim merkezi Kullanıcı yönetim kartı.](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. **Dizin eşitleme** hataları sayfasındaki hataları görmek için kartta **, Bağlan Azure AD'ın altında** Hataları **eşitle'yi** seçin.   
    
    ![Dizin eşitleme hataları sayfasına bir örnek.](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Hata hakkında bilgi ve düzeltme ipuçları içeren ayrıntılar bölmesini görüntülemek için hatalardan herhangi birini seçin.

   ![Dizin eşitleme hatasının ayrıntıları örneği.](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Görüntüledikten sonra, tanımlanan [sorunları düzeltmek için bkz. Microsoft 365 için dizin eşitleme sorunlarını](fix-problems-with-directory-synchronization.md) düzeltme.