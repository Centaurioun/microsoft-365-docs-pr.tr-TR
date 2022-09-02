---
title: Uydu coğrafi konumunuzdaki SharePoint Multi-Geo'sunu etkinleştirme
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Bu makalede, küresel veya SharePoint yöneticilerine uydu coğrafi konumlarında SharePoint Multi-Geo etkinleştirme hakkında bilgi sağlanır.
ms.openlocfilehash: 41eb4573c9e07380b0df5df03848dadfb64c239d
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67556336"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Uydu coğrafi konumunuzdaki SharePoint Multi-Geo'sunu etkinleştirme

Bu makale, SharePoint Multi-Geo özellikleri 27 Mart 2019'da genel kullanıma **sunulmadan önce** Multi-Geo uydu konumu oluşturan ve uydu coğrafi konumlarında SharePoint Multi-Geo etkinleştirmeyen Genel veya SharePoint yöneticilerine yöneliktir. 

>[!Note]
>**27 Mart 2019'un ardından** yeni bir coğrafi konum eklediyseniz, yeni coğrafi konumunuz OneDrive ve SharePoint Multi-Geo için zaten etkinleştirileceği için bu yönergeleri gerçekleştirmeniz gerekmez.

Bu yönergeler, Multi-Geo uydu kullanıcılarınızın O365'teki hem OneDrive hem de SharePoint Multi-Geo özelliklerinden yararlanabilmesi için SharePoint'i uydu konumunuzda etkinleştirmenize olanak tanır. 

>[!IMPORTANT]
>Bunun tek bir etkinleştirme yöntemi olduğunu lütfen unutmayın. SPO modunu ayarladıktan sonra, destekle yükseltme olmadan kiracınızı yalnızca OneDrive Multi-Geo moduna geri döndüremezsiniz. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Coğrafi konumu SPO Moduna ayarlamak için

Bir coğrafi konumu SPO moduna ayarlamak için SPO Modunda ayarlamak istediğiniz coğrafi konuma bağlanın:

1.    SharePoint Online Yönetim Kabuğunuzu açma 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Kimlik bilgisi $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience.](../media/Set-SPO-MultiGeo.jpg)
4.    Bu işlem genellikle yaklaşık bir saat sürerken biz hizmette çeşitli geri yayımlama işlemleri gerçekleştirir ve kiracınızı yeniden damgalarız. En az 1 saat sonra lütfen Get-SPOMultiGeoExperience gerçekleştirin.  Bu, bu coğrafi konumun SPO modunda olup olmadığını gösterir.</br></br>
![Set-SPOMultiGeoExperience görüntüsü.](../media/Get-SPO-MultiGeo.jpg)

  
>[!Note]
>Hizmetteki belirli önbellekler 24 saatte bir güncelleştirilir, bu nedenle 24 saate kadar bir süre boyunca uydu coğrafi bölgeniz aralıklı olarak ODB modundaymış gibi davranabilir. Bu herhangi bir teknik soruna neden olmaz. 
 
SharePoint Multi-Geo hakkında daha fazla bilgi için lütfen [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


