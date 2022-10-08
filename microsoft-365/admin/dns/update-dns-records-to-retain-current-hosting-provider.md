---
title: DNS kayıtlarını güncelleştirerek web sitenizi geçerli barındırma sağlayıcınızla koruma
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Microsoft'u özel etki alanınız için DNS kayıtlarını yönetecek şekilde ayarladıysanız trafiği Microsoft dışında barındırılan mevcut bir genel web sitesine yönlendirmeyi öğrenin.
ms.openlocfilehash: ad7a2c61c8eb7223b9f6c0dfabbe896ab651b275
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188625"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS kayıtlarını güncelleştirerek web sitenizi geçerli barındırma sağlayıcınızla koruma

 **Etki alanınızın Microsoft kayıtlarını DNS barındırma sağlayıcınızda yönetiyorsanız**, bu konudaki adımlarla ilgilenmeniz gerekmez. Web siteniz olduğu yerde kalır ve herkes sitenize erişmeye devam edebilir. 
  
 **DNS kayıtlarınızı Microsoft yönetiyorsa, etki alanınızı** Microsoft'a ekledikten sonra trafiği Microsoft dışında barındırılan mevcut bir genel web sitesine yönlendirmek için aşağıdakileri yapın: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi DNS kayıtlarını güncelleştirme
1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

1. **Etki Alanları** sayfasında etki alanını ve ardından **DNS Kayıtları'nı** seçin.

1. **+ Kayıt ekle'yi** seçin ve aşağıdakileri girin: 
    
   - **Tür için** şunu girin: **A (Adres)**
    
   - **Ana bilgisayar adı veya Diğer ad** olarak şunu yazın: **@**
    
   - **IP Adresi** olarak web sitenizin şu anda barındırıldığı statik IP adresini yazın (örneğin, 172.16.140.1). 
    
   This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website. 
    
1. **Kaydet**'i seçin. 
    
Buna ek olarak, müşterilerin web sitenizi bulmalarına yardım etmek için bir CNAME kaydı da oluşturabilirsiniz.
  
1. **+ Kayıt ekle'yi** seçin ve aşağıdakileri girin: 
    
   - **Tür için** şunu girin: **CNAME (Diğer ad)**
    
   - **Ana bilgisayar adı veya Diğer ad** olarak şunu yazın: **www**
    
   - **İşaret edilen adres** olarak, web sitenizin tam etki alanı adını (FQDN) yazın (örneğin, contoso.com). 
    
2. **Kaydet** 'i seçin. 
    
Son olarak da aşağıdakileri yapın:
  
[Etki alanınızın NS kayıtlarını Microsoft'a](../setup/add-domain.md) işaret etmek için güncelleştirin. 
  
NS kayıtları Microsoft'a işaret etmek üzere güncelleştirildiğinde, etki alanınızın tümü ayarlanır. Email Microsoft'a yönlendirilir ve web sitesi adresinize giden trafik geçerli web sitesi barındırma sağlayıcınıza gitmeye devam eder.
