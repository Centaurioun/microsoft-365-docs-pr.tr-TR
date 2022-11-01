---
title: Microsoft 365 Multi-Geo
ms.reviewer: anfra
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Bu makalede, Microsoft 365 Multi-Geo ile Microsoft 365 iletişim durumunuzu birden fazla coğrafi bölgeye genişletmeyi öğrenin.
ms.openlocfilehash: f663d95b6d1d714b0b144d32736013885a7aad87
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804958"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Microsoft 365 Multi-Geo Capabilities eklentisi, müşterilere Microsoft 365 iletişim durumlarını mevcut tek bir Microsoft 365 _Kiracısı_ içindeki birden çok coğrafi bölgeye veya ilçeye genişletme olanağı sağlar. Multi-Geo, müşterilerin bekleyen konumları kullanıcıları, SharePoint siteleri, Microsoft 365 Grupları ve Microsoft Teams ekipleri düzeyinde ayrıntılı bir düzeyde yönetmesini sağlar. Multi-Geo, veri yerleşimi gereksinimlerini karşılamak için müşteri verilerini aynı anda birden çok coğrafyada depolama ihtiyacı olan ve zaman içinde ihtiyaçları değişebilecek olan müşterileri hedefler.
  
Microsoft 365 Multi-Geo, müşterilerin veri yerleşimi gereksinimlerini karşılamak ve müşterilerin uydu konumu ve tercih edilen veri konumları arasında işbirliğine olanak sağlamak için tasarlanmıştır. Müşteri Microsoft 365 için performans iyileştirme işlevleri gerektiriyorsa bkz. <a href="https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848" target="_blank">Microsoft 365 için ağ planlama ve performans ayarlama</a> veya destek grubunuzla iletişime geçin.

>[!NOTE]
>Exchange Online, SharePoint Online, OneDrive İş ve Microsoft Teams, Multi-Geo yapılandırması için kullanılabilir. Daha fazla ayrıntı için [Exchange Online](m365-dr-workload-exo.md), [SharePoint Online ve OneDrive İş ve](m365-dr-workload-spo.md) [Microsoft Teams](m365-dr-workload-teams.md#data-residency-commitments-available) için veri yerleşimi taahhüdü bölümlerine bakın.

Microsoft 365 Multi-Geo'ya giriş videosu için bkz. [Verilerinizin nerede bulunduğunu denetlemek için SharePoint Online ve OneDrive Multi-Geo](https://www.youtube.com/watch?v=Do9U3JuROhk).

## <a name="multi-geo-architecture"></a>Multi-Geo mimarisi

Multi-Geo ortamında, Microsoft 365 _Kiracınız_ merkezi bir konumdan (Microsoft 365 aboneliğinizin ilk sağlandığı yerde) ve bir veya daha fazla uydu konumundan oluşur. Multi-Geo özellikli _bir Kiracıda_ coğrafi konumlar, gruplar ve kullanıcı bilgileriyle ilgili bilgiler Azure Active Directory'de (Azure AD) ana veridir. _Kiracı_ bilgileriniz merkezi olarak yönetildiğinden ve her coğrafi konuma eşitlendiğinden, şirketinizden herhangi bir kişiyi kapsayan paylaşım ve deneyimler küresel farkındalık içerir.

![SharePoint yönetim merkezinden birden fazla coğrafi konumlu haritanın ekran görüntüsü.](../media/multi-geo-world-map.png)

## <a name="licensing"></a>Lisanslama

Microsoft 365 Multi-Geo, Kurumsal Anlaşma müşterileri için aşağıdaki Microsoft 365 abonelik planlarına bir eklenti olarak sunulur. Müşterilerin, toplam uygun koltuklarının %5'ine eşit veya daha büyük sayıda Multi-Geo lisansı satın alması gerekir. Kullanıcı abonelik lisansları, Multi-Geo Hizmetler lisanslarıyla aynı Kurumsal Anlaşmada olmalıdır. Ayrıntılar için lütfen Microsoft hesabı ekibinize başvurun.

- Microsoft 365 F1, F3, E3 veya E5
- Office 365 F3, E1, E3 veya E5
- Exchange Online Plan 1 veya Plan 2
- OneDrive İş Plan 1 veya Plan 2
- SharePoint Online Plan 1 veya Plan 2

_Microsoft 365 planındaki Multi-Geo Özelliklerinin_ kullanıcı düzeyinde bir eklenti lisansı olduğunu unutmayın. _Uydu Coğrafya_ konumunda barındırmak istediğiniz her kullanıcı için bir lisansa ihtiyacınız vardır. _Uydu Coğrafya_ konumlarına kullanıcı eklerken zaman içinde ek lisanslar ekleyebilirsiniz.

SharePoint Siteleri, Microsoft 365 Grupları veya Microsoft Teams ekipleri gibi paylaşılan kaynaklara özgü Multi-Geo lisansı yoktur. Yeterli Multi-Geo kullanıcı lisansı edinildiyse müşteriler SharePoint Siteleri, Microsoft 365 Grupları ve Microsoft Teams ekipleriyle sınırlı olmaksızın Multi-Geo kullanmaya uygun olur.

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 Multi-Geo kullanılabilirliği

Microsoft 365 Multi-Geo şu anda şu bölgelerde ve ülkelerde sunulur:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Başlarken

Multi-Geo kullanmaya başlamak için şu adımları izleyin:

1. _Microsoft 365 hizmet planında Multi-Geo Capabilities eklemek_ için hesap ekibinizle birlikte çalışın. Gereken lisans sayısını eklemeniz için size yol gösterirler. Multi-Geo özelliği Kurumsal Anlaşma müşterileri tarafından kullanılabilir.

2. Microsoft 365 Multi-Geo kullanmaya başlamadan önce Microsoft'un Multi-Geo desteği için Exchange Online _Kiracınızı_ yapılandırması gerekir. Bu tek seferlik yapılandırma işlemi _, Microsoft 365 hizmet planında Multi-Geo Özelliklerini_ sipariş ettikten ve lisanslar _Kiracınızda_ gösterildikten sonra tetiklenir. _Kiracınız_ her iş yükü için yapılandırma işlemini tamamladıktan sonra [Microsoft 365 ileti merkezinde](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) iş yüküne özgü bildirimler alırsınız ve ardından Microsoft 365 Multi-Geo özelliklerinizi yapılandırmaya ve kullanmaya başlayabilirsiniz. Multi-Geo desteği için _kiracıyı_ yapılandırmak için gereken süre _Kiracıdan Kiracıya_ değişir, ancak çoğu Kiracı özellik _lisansları_ alındıktan sonraki bir ay içinde biter. Daha büyük veya daha karmaşık _Kiracılar_ yapılandırma işlemini tamamlamak için daha fazla zaman gerektirebilir. Gerekli olması halinde ilgili _Kiracınızla_ ilgili ayrıntılar için lütfen hesap ekibinize başvurun.

3. [Birden fazla coğrafi konumlu ortamınızı planlayın](plan-for-multi-geo.md)'ı okuyun.

4. [Birden fazla coğrafi konumlu ortamını yönetme](administering-a-multi-geo-environment.md) ve [kullanıcılarınızın ortamı deneyimlemesi](multi-geo-user-experience.md) hakkında bilgi edinin.

5. Microsoft 365 Multi-Geo'yu ayarlamaya hazır olduğunuzda, [kiracınızı birden fazla coğrafi konum için yapılandırın](multi-geo-tenant-configuration.md).

6. [Arama ayarlaması](configure-search-for-multi-geo.md).
  
> [!NOTE]
> Multi-Geo'yu destekleyen Microsoft 365 hizmetleri hakkında daha fazla bilgi için lütfen daha fazla ayrıntı için [EXO](m365-dr-workload-exo.md), [ODSP](m365-dr-workload-spo.md) ve [Teams](m365-dr-workload-teams.md) iş yükü veri yerleşimi sayfalarına bakın.


## <a name="see-also"></a>Ayrıca bkz.

[Exchange Online ve OneDrive'da Multi-Geo](https://Aka.ms/GoMultiGeo)

[OneDrive ve SharePoint Online’da Multi-Geo Özellikleri](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Exchange Online'da Multi-Geo Capabilities](multi-geo-capabilities-in-exchange-online.md)

[Birden fazla coğrafi konumlu ortamda Teams deneyimi](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
