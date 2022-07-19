---
title: Microsoft 365 İş Ekstra ile Office istemci dağıtımına hazırlanma
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
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
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows bilgisayarlara 32 bit Office uygulamalarını otomatik olarak yüklemeyi ve bunları Microsoft 365 İş Ekstra'de güncel tutmayı öğrenin.
ms.openlocfilehash: e65b6f0b0eb6c08d2d4cd612a61038ae75aa8030
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66862093"
---
# <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>İstemci bilgisayarlara Office uygulamalarını otomatik olarak yükleme hazırlığı

32 bit Office uygulamalarını Windows bilgisayarlara otomatik olarak yüklemek ve güncelleştirmelerle güncel tutmak için Microsoft 365 İş Ekstra kullanın.
  
Otomatik yükleme en iyi sonucu şu bilgisayar olduğunda sağlar: 

- , İş İçin Windows'tadır.
  
- mevcut Office masaüstü uygulamaları (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access ve OneDrive) veya Tıkla-Çalıştır Office'in mevcut bir sürümü yüklü değildir.

Office'in Tıkla-Çalıştır sürümüne sahip olup olmadığınızı belirlemek için, herhangi bir Office uygulamasında **Dosya** \> **Hesap**'a (Outlook'ta **Office Hesabı**) gidin. Aşağıdaki şekilde gösterildiği gibi **Office Güncelleştirmeler** görüyorsanız, yükleme Tıkla-Çalıştır kullanılarak yapılmıştır.
  
![Office uygulama hesabındaki Office güncelleştirmelerinin ekran görüntüsü.](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
## <a name="requirements-for-using-this-feature"></a>Bu özelliği kullanma gereksinimleri
  
Şu kişilerle çalışır:
  
- Windows business kullanıcı lisansına, etkin bir İş için Microsoft 365 lisansına sahip Windows 10 Creators Update ve Azure Active Directory'ye katılmış bir kullanıcı.

Şu işlemlerle çalışmaz: 

- 64 bit Office uygulamaları (örneğin: Word, Excel, PowerPoint). 64 bit Office uygulamaları gerekiyorsa, iş için Microsoft 365 yönetici konsolundan Office'in 64 bit 2016 Tıkla-Çalıştır sürümünü tetikleme desteği olmadığından bu özellik uygun değildir.

- Tüm 2016 Windows Installer (MSI) tek başına uygulamaları (örneğin, Visio veya Project). İş için Microsoft 365, Office'i Office 2016'nın Tıkla-Çalıştır sürümüne yükseltmektedir ve bu, Office 2016 MSI tek başına uygulamalarıyla çalışmaz.

Aşağıdaki tabloda, iş için Microsoft 365 yönetici konsolundan Office dağıtımının 32 bit Tıkla-Çalıştır sürümünün başarılı olması için, son kullanıcıların veya yöneticilerin başlangıç durumlarına bağlı olarak hangi eylemi gerçekleştirmesi gerekebileceği gösterilmektedir.<br/>


|Başlangıçtaki Office yükleme durumu|İş için Microsoft 365 Office yüklemeden önce gerçekleştirmesi gereken eylem|Son durum|
|:-----|:-----|:-----|
|Hiçbir Office paketi yüklü değil  |Yok  |Tıkla-Çalıştır kullanılarak Office 2016 32 bit yüklenir  |
|Office'in Tıkla-Çalıştır 32 bit sürümü (2016 veya önceki) var ve tek başına uygulama yok  |Yok  |Gerektiği gibi Office 2016'nın en son 32 bit Tıkla-Çalıştır sürümüne yükseltilir **\*** |
|Office'in Tıkla-Çalıştır 32 bit sürümü ve Tıkla-Çalıştır 32 bit veya 64 bit tek başına Office uygulamaları (örneğin, Visio, Project)  |Yok  |Tek başına uygulamalar etkilenmez. Paket, Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilir  |
|Office'in Tıkla-Çalıştır 32 bit sürümü ve 32 bit veya 64 bit (2016 dışında) MSI tek başına Office uygulamaları var  |Yok  |Tek başına uygulamalar etkilenmez. Paket, Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilir  |
|Office'in Tıkla-Çalıştır 64 bit sürümü var  |Bunları 32 bit Office uygulamalarıyla değiştirmek uygunsa 64 bit Office uygulamalarını kaldırın  |Office 64 bit uygulamaları kaldırılmışsa, Office 2016'nın Tıkla-Çalıştır 32 bit sürümü yüklenir  |
|Tek başına uygulamalarla veya bu uygulamalar olmadan Office 2016'nın MSI yüklemesi var  |MSI Office 2016'yı kaldırın.  |Office 2016'nın Tıkla-Çalıştır 32 bit sürümü yüklenir. Tek başına uygulamalarda hiçbir değişiklik olmaz  |
|Office 2013'ün (veya önceki sürümlerin) ve/veya tek başına Office uygulamalarının MSI yüklemesi var  |Yok  |Office 2016'nın Tıkla-Çalıştır 32 bit sürümü, önceden var olan MSI Office yüklemesiyle (ve tek başına uygulamalarla) birlikte kullanılır  |

 **(\*) Not:** Bilinen bir hata nedeniyle Office 2016'nın Tıkla-Çalıştır 32 bit sürümüne yükseltilmez. Bir düzeltme devam ediyor. 

## <a name="next-objective"></a>Sonraki hedef

[Uygulama koruma ayarları oluşturma](m365bp-protection-settings-for-windows-10-devices.md)
  