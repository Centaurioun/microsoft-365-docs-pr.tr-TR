---
title: OneDrive ve SharePoint Online'daki Multi-Geo Özellikleri
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: OneDrive Online'da çok coğrafi özelliklerle Microsoft 365 iletişim durumunuzu birden çok coğrafi bölgeye genişletin.
ms.openlocfilehash: b25d74c76673c8fcaf2de0e8bbbd1c73ba371856
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694369"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>OneDrive ve SharePoint Online’da Multi-Geo Özellikleri

OneDrive ve SharePoint Online'daki Multi-Geo özellikleri, SharePoint ekip siteleri ve Microsoft 365 Grubu posta kutuları gibi paylaşılan kaynakların belirli bir coğrafi konumda bekleyen posta kutularının denetimini sağlar.

Her kullanıcı, Grup posta kutusu ve SharePoint sitesi, ilgili verilerin depolandığı coğrafi konumu gösteren Tercih Edilen Veri Konumu'na (PDL) sahiptir. Kullanıcıların kişisel verileri (Exchange posta kutusu ve OneDrive) ve oluşturdukları tüm Microsoft 365 Grupları veya SharePoint siteleri, veri yerleşimi gereksinimlerini karşılamak için belirtilen coğrafi konumda depolanabilir. [Her coğrafi konum için farklı yöneticiler belirtebilirsiniz](add-a-sharepoint-geo-admin.md).

Kullanıcılar Office uygulamaları, OneDrive ve Arama gibi Microsoft 365 hizmetlerini kullanırken sorunsuz bir deneyim yaşar. Ayrıntılar için bkz. [Çok coğrafi ortamda kullanıcı deneyimi](multi-geo-user-experience.md) .

## <a name="onedrive"></a>OneDrive

Her kullanıcının OneDrive'ı [, yönetici tarafından](move-onedrive-between-geo-locations.md) kullanıcının PDL'sine uygun olarak bir uydu konumuna sağlanabilir veya taşınabilir. Kişisel dosyalar daha sonra bu coğrafi konumda tutulur ancak diğer coğrafi konumlardaki kullanıcılarla paylaşılabilir.

## <a name="sharepoint-sites-and-groups"></a>SharePoint Siteleri ve Grupları

Multi-Geo özelliğinin <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">yönetimine SharePoint yönetim merkezinden</a> ulaşabilirsiniz. Ayrıntılı bilgileri [ilgili blog gönderisinde](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302) bulabilirsiniz.

Bir kullanıcı çok coğrafi bir ortamda SharePoint grubuna bağlı bir site oluşturduğunda, sitenin ve ilişkili Grup posta kutusunun oluşturulduğu coğrafi konumu belirlemek için PDL'leri kullanılır. (Kullanıcının PDL değeri ayarlanmamışsa veya uydu konumu olarak yapılandırılmamış coğrafi konuma ayarlanmışsa, site ve posta kutusu merkezi konumda oluşturulur.)

Exchange, OneDrive, SharePoint ve Teams dışındaki Microsoft 365 hizmetleri Multi-Geo değildir. Ancak, bu hizmetler tarafından oluşturulan Microsoft 365 Grupları oluşturucunun PDL'siyle ve Exchange Grubu posta kutusuyla yapılandırılır, SharePoint sitesi ilgili coğrafi bölgede sağlanır. 

## <a name="managing-the-multi-geo-environment"></a>Çok coğrafi ortamı yönetme

Çok coğrafi ortamınızı ayarlama ve yönetme işlemi <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint yönetim merkezi</a> üzerinden yapılır. 

![SharePoint yönetim merkezindeki coğrafi konumlar sayfasının ekran görüntüsü.](../media/sharepoint-multi-geo-admin-center.png)

(SharePoint sitesini veya OneDrive sitesini taşıma gibi bazı eylemler Için Microsoft PowerShell gerekir.)

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint ve Microsoft 365 Grupları'da Multi-Geo](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Multi-Geo ortamı yönetme](administering-a-multi-geo-environment.md)

[Çok coğrafili ortamlarda SharePoint depolama kotaları](sharepoint-multi-geo-storage-quota.md)

[Çok coğrafi bir ortamda Exchange Online posta kutularını yönetme](administering-exchange-online-multi-geo.md)
