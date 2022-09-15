---
title: Microsoft 365 için ağ planlama ve performans ayarlama
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 2/18/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: Bu makale, Microsoft 365 için ağ bant genişliği gereksinimlerinizi planlamanıza ve performansa ince ayar yapıp sorun gidermenize yardımcı olur.
ms.openlocfilehash: 090bfb41675089e5c9014e35ddf58e1e51bad311
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694491"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 için ağ planlama ve performans ayarlama
İlk kez dağıtmadan veya Microsoft 365'e geçirmeden önce, ihtiyacınız olan bant genişliğini tahmin etmek ve ardından Microsoft 365'i dağıtmak veya microsoft 365'e geçirmek için yeterli bant genişliğine sahip olduğunuzu test etmek ve doğrulamak için bu konulardaki bilgileri kullanabilirsiniz. Genel bakış için bkz. [Microsoft 365 için ağ ve geçiş planlaması](network-and-migration-planning.md).
  
|Kategori |Açıklama |Kategori |Açıklama |
|:-----|:-----|:-----|:-----|
|**Ağ planlaması** <br/> ![Ağ.](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |Hızlı bağlantılar ve hızla yüklenen sayfalar mı istiyorsunuz?  <br/> [Microsoft 365'te en iyi bağlantıyı ve performansı alma makalesini](https://aka.ms/o365perfprinciples) okuyun.<br/>Kavramları anlamak için [Microsoft 365 Ağ Bağlantısına Genel Bakış](microsoft-365-networking-overview.md) makalesini okuyun.<br/> |**Ağınızı ölçme** <br/> ![Hesap makinesi](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |[Temelleri ve performans geçmişini kullanarak Microsoft 365 performans ayarlamasını ve](performance-tuning-using-baselines-and-history.md) [Microsoft 365 için Performans sorun giderme planını](performance-troubleshooting-plan.md) okuyun.  <br/> [Mevcut ağınızı değerlendirmek](network-and-migration-planning.md#calculators) için bu araçları kullanın.  <br/> |
|**En iyi yöntemler** <br/> ![En iyi yöntemler.](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[Microsoft 365 için ağ planlaması ve geçiş performansını iyileştirmeye yönelik en iyi yöntemler](network-and-migration-planning.md#BestPractices). Kullanıcılarınıza hemen yardım etmeye başlamak mı istiyorsunuz? Bkz. [Yavaş bir ağda Office 365 kullanmak için en iyi yöntemler](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).  <br/> [Microsoft 365 Ağ Bağlantısı İlkeleri](./microsoft-365-network-connectivity-principles.md) , Microsoft 365 ağ bağlantısını güvenli bir şekilde iyileştirmeye yönelik en son yönergeleri anlamanıza yardımcı olur.  <br/> |**Başvuru** <br/> ![Kitap veya Günlük](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP adreslerinin ve bağlantı noktalarının listesi gibi ayrıntıları mı istiyorsunuz? Bkz. [Microsoft 365 için ağ planlama başvurusu](network-and-migration-planning.md#NetReference).  <br/> |
|![Kurumsal Mimarlar için Microsoft Bulut Ağı posteri'ne bakın.](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Ağınızı Microsoft 365 ve diğer Microsoft bulut platformları ve hizmetleri için iyileştirme adımları [için Kurumsal Mimarlar için Microsoft Bulut Ağı](../solutions/cloud-architecture-models.md) posterine bakın.  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Microsoft 365 için performans ayarlama ve sorun giderme kaynakları
<a name="apptuning"> </a>

Microsoft 365'i dağıttıktan sonra, bu bölümdeki konuları kullanarak performansınızı iyileştirebilirsiniz. Performans düşüşü yaşıyorsanız sorunları gidermek için bu konuları da kullanabilirsiniz.
  
 **[Office 365 performansını ayarlama](tune-microsoft-365-performance.md)**: Office 365 ile ağ adresi çevirisi kullanma hakkında bilgi için bkz. [Office 365 ile NAT desteği](nat-support-with-microsoft-365.md). Ayrıca, [Office 365 ağ bağlantınızı iyileştirmeye ve sorun gidermeye yönelik en iyi 10 ipucuna](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity) göz atın.
  
 **[Exchange Online performansını ayarlama](tune-exchange-online-performance.md)**: Exchange Online performansa ince ayar yapmak için bu makaleleri kullanın.

 **[Kuruluşunuzun ağını Microsoft Teams için hazırlama](/microsoftteams/prepare-network)**: Ağınızı Teams için iyileştirmek için bu makaleleri kullanın.
  
 **[çevrimiçi performans Skype Kurumsal ayarlama: Skype Kurumsal](tune-skype-for-business-online-performance.md)** Çevrimiçi performansa ince ayar yapmak için bu makaleleri kullanın.
  
 **[SharePoint Online performansını ayarlama: SharePoint Online performansına](tune-sharepoint-online-performance.md)** ince ayar yapmak için bu makaleleri kullanın.
  
 **[Project Online performansını ayarlama](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)**: Project Online performansa ince ayar yapmak için bu makaleyi kullanın
