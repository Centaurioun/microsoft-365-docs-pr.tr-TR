---
title: İşletmeler için Office istemci dağıtımına Microsoft 365 hazırlama
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Bilgisayarınıza 32 bit Office uygulamaları otomatik olarak Windows 10 ve güncel tutma hakkında bilgi edinin.
ms.openlocfilehash: 134d5f2918e3f28c2025b282b9ae0325b64fe0474ae8123d0637bb43c4730c55
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53803566"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>İşletmeler için Office istemci dağıtımına Microsoft 365 hazırlama

Bu makale diğer Microsoft 365 İş Ekstra.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>İstemci bilgisayarlara Office uygulamalarını otomatik olarak yükleme hazırlığı

Microsoft 365 İş Ekstra'i kullanarak bilgisayarınıza 32 bit Office uygulamalarını Windows 10 güncelleştirmelerle bunları güncel tutabilirsiniz.
  
Otomatik yükleme en iyi şekilde, son kullanıcının bilgisayarı bilgisayarda ise en Windows 10 Business ve:
  
- Mevcut Office masaüstü uygulamaları (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access ve OneDrive) bulunmamalıdır.
    
    veya
    
- Office'in Tıkla-Çalıştır sürümü yüklü olmalıdır.
    
Office'in Tıkla-Çalıştır sürümüne sahip olup olmadığınızı belirlemek için, herhangi bir Office uygulamasında **Dosya** \> **Hesap**'a (Outlook'ta **Office Hesabı**) gidin. Aşağıdaki şekilde **Office Güncelleştirmeler** görüyorsanız, yükleme Tıkla-Çalıştır kullanılarak yapılır. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Who özelliğin avantajlarından yararlanma**
  
Bilgisayarı aşağıdaki özelliklere sahip olan son kullanıcılar:
  
- **İş** Windows 10 Business lisansına sahip, Microsoft 365 lisansına sahip Windows 10 Creators Update lisansına sahip ve Azure Active Directory. 
    
- **64** bit uygulama veya Office (örneğin: Word, Excel, PowerPoint). 64 bit Office uygulamaları gerekirse, bu özellik uygun değildir çünkü kurumsal yönetici konsolundan Office'un 64 bit 2016 Tıkla-Çalıştır sürümünü tetikleme desteği Microsoft 365 değildir. 
    
- Herhangi bir 2016 Windows Installer (MSI) tek başına uygulaması (örneğin, Visio veya Project) **yoktur**. Microsoft 365 için Office yükseltmeleri Office 2016'nın Tıkla-Çalıştır sürümüne yükseltmedir ve bu da Office 2016 MSI tek başına uygulamalarıyla işe yaramadı. 
    
Aşağıdaki tablo, son kullanıcıların/yöneticilerin, başlangıç durumlarına bağlı olarak işletmeler için Microsoft 365 yönetim konsolundan Office dağıtımının başarılı bir 32 bit Tıkla-Çalıştır sürümüne sahip olmak için hangi eylemi uygulaması gerekten olduğunu gösterir.<br/>


|Başlangıçtaki Office yükleme durumu|İşletmeler için yüklemeden Microsoft 365 önce Office işlem|Son durum|
|:-----|:-----|:-----|
|Hiçbir Office paketi yüklü değil  <br/> |Yok  <br/> |Office-Çalıştır kullanılarak 2016 32 bit yüklenir  <br/> |
|Office'in Tıkla-Çalıştır 32 bit sürümü (2016 veya önceki) var ve tek başına uygulama yok  <br/> |Yok  <br/> |Gerektiği gibi Office 2016'nın en son 32 bit Tıkla-Çalıştır sürümüne yükseltilir **\*** <br/> |
|Office'un Tıkla-Çalıştır 32 bit sürümü ve Tıkla-Çalıştır 32 bit veya 64 bit tek başına Office uygulamaları (örneğin, Visio, Project)  <br/> |Yok  <br/> |Tek başına uygulamalar etkilenmez. Paket, Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilir  <br/> |
|Office'in Tıkla-Çalıştır 32 bit sürümü ve 32 bit veya 64 bit (2016 dışında) MSI tek başına Office uygulamaları var  <br/> |Yok  <br/> |Tek başına uygulamalar etkilenmez. Paket, Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilir  <br/> |
|Office'in Tıkla-Çalıştır 64 bit sürümü var  <br/> |64 bit veya Office 32 bit uygulamayla değiştirmek sorun yoksa bu Office kaldırın  <br/> |Office 64 bit uygulamaları kaldırılmışsa, Office 2016'nın Tıkla-Çalıştır 32 bit sürümü yüklenir  <br/> |
|Tek başına uygulamalarla veya bu uygulamalar olmadan Office 2016'nın MSI yüklemesi var  <br/> |MSI Office 2016'yı kaldırın.  <br/> |Office 2016'nın Tıkla-Çalıştır 32 bit sürümü yüklenir. Tek başına uygulamalarda hiçbir değişiklik olmaz  <br/> |
|Office 2013'ün (veya önceki sürümlerin) ve/veya tek başına Office uygulamalarının MSI yüklemesi var  <br/> |Yok  <br/> |Office 2016'nın Tıkla-Çalıştır 32 bit sürümü, önceden var olan MSI Office yüklemesiyle (ve tek başına uygulamalarla) birlikte kullanılır  <br/> |
||||
   
 **(\*) Not:** Bilinen bir hata nedeniyle Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilmez. Düzeltme için çalışma devam etmektedir. 
  
