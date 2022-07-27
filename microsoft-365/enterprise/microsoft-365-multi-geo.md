---
title: Microsoft 365 Multi-Geo
ms.reviewer: anfra
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Bu makalede, Microsoft 365 Multi-Geo ile Microsoft 365 iletişim durumunuzu birden fazla coğrafi bölgeye genişletmeyi öğrenin.
ms.openlocfilehash: 154082785b71be8fbba55e00e2df8a1a3eacb500
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490220"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Microsoft 365 Multi-Geo ile kuruluşunuz, Microsoft 365 iletişim durumunuzu mevcut kiracınız dahilinde birden fazla coğrafi bölgeye ve/veya ülkeye genişletebilir. Çok Uluslu Şirketinizi Microsoft 365 Multi-Geo'ya kaydettirmek için Microsoft Hesabı Ekibinize ulaşın.
  
Microsoft 365 Multi-Geo ile veri yerleşimi gereksinimlerini karşılamak için seçtiğiniz coğrafi konumlarda bekleyen verileri sağlayabilir, depolayabilir ve aynı zamanda modern üretkenlik deneyimlerinin iş gücünüze küresel olarak sunulmasını sağlayabilirsiniz.

Microsoft 365 Multi-Geo'ya giriş videosu için bkz. [Verilerinizin nerede bulunduğunu denetlemek için SharePoint Online ve OneDrive Multi-Geo](https://www.youtube.com/watch?v=Do9U3JuROhk).

## <a name="multi-geo-architecture"></a>Multi-Geo mimarisi

Bir Multi-Geo ortamında, Microsoft 365 kiracınız bir merkezi konumdan (Microsoft 365 aboneliğinizin başlangıçta sağlandığı yer) ve bir veya daha fazla uydu konumundan oluşur. Birden fazla coğrafi konumlu kiracıda, coğrafi konumlar, gruplar ve kullanıcı bilgileri hakkındaki bilgiler Azure Active Directory'de (Azure AD) yönetilir. Kiracı bilgileriniz merkezi olarak yönetildiğinden ve her coğrafi konumla eşitlendiğinde, şirketinizden herhangi birinin dahil olduğu paylaşımlar ve deneyimler küresel farkındalık içerir.

![SharePoint yönetim merkezinden birden fazla coğrafi konumlu haritanın ekran görüntüsü.](../media/multi-geo-world-map.png)

Microsoft 365 Multi-Geo'nun performans iyileştirmesi için tasarlanmadığını, veri yerleşimi gereksinimlerini karşılamak için tasarlandığını unutmayın. Microsoft 365 için performans iyileştirmesi hakkında bilgi için bkz. [Microsoft 365 için ağ planlama ve performans ayarlama](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) veya destek grubunuza başvurun.

## <a name="terminology"></a>Terminoloji

Microsoft 365 Multi-Geo'yu tanımlarken kullanılan temel koşullar şunlardır:

- **Merkezi konum**: Kiracınıza başlangıçta sağlanan coğrafi konum.
- **Coğrafi yönetici**: Bir veya daha fazla belirli uydu konumunu yönetebilen bir yönetici.
- **Coğrafi kod**: Belirli bir coğrafi konum için üç harfli bir kod.
- **Coğrafi konum**: Exchange posta kutuları ve OneDrive ve SharePoint siteleri dahil olmak üzere verileri barındırmak için biden fazla coğrafi konumlu kiracıda kullanılabilecek bir coğrafi konum.
- **Tercih Edilen Veri Konumu (PDL)**: Yönetici tarafından ayarlanan ve kullanıcıların Exchange posta kutusu ve OneDrive'ın sağlanması gereken coğrafi konumu belirten bir kullanıcı özelliği. PDL, kullanıcı tarafından oluşturulan SharePoint sitelerinin nerede sağlandığını da belirler.
- **Uydu konumu**: Coğrafi olarak duyarlı Microsoft 365 iş yüklerinin (SharePoint, OneDrive ve Exchange) bir birden fazla coğrafi konumlu kiracıda etkinleştirildiği coğrafi konumlar.
- **Kiracı**: Genellikle kendisiyle ilişkilendirilmiş bir veya daha fazla etki alanına sahip Microsoft 365'teki bir kuruluşun temsili (örneğin, contoso.com)

## <a name="licensing"></a>Lisanslama

Microsoft 365 Multi-Geo, kiracılarında en az 250 Microsoft 365 lisansı ve bu lisansların en az %5'i birden fazla coğrafi konumu kullanan Kurumsal Anlaşma müşterileri için aşağıdaki Microsoft 365 abonelik planlarına bir ek olarak kullanılabilir. Kullanıcı abonelik lisansları, Multi-Geo Hizmetler lisanslarıyla aynı Kurumsal Anlaşmada olmalıdır. Ayrıntılar için lütfen Microsoft hesabı ekibinize başvurun.

- Microsoft 365 F1, F3, E3 veya E5
- Office 365 F3, E1, E3 veya E5
- Exchange Online Plan 1 veya Plan 2
- OneDrive İş Plan 1 veya Plan 2
- SharePoint Online Plan 1 veya Plan 2

Bir kullanıcıya lisans atanır ve daha sonra kaldırılırsa, Teams kullanıcı sohbet verileri, merkezi konuma geri taşınmak üzere kuyruğa alınır. SharePoint ve Exchange verileri taşınmaz.

## <a name="microsoft-365-multi-geo-availability"></a>Microsoft 365 Multi-Geo kullanılabilirliği

Microsoft 365 Multi-Geo şu anda şu bölgelerde ve ülkelerde sunulur:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Başlarken

Multi-geo kullanmaya başlamak için şu adımları izleyin:

1. _Microsoft 365 hizmet planında Multi-Geo Capabilities eklemek_ için hesap ekibinizle birlikte çalışın. Gereken lisans sayısını eklemeniz için size yol gösterirler. Multi-Geo özelliği, en az 250 Microsoft 365 aboneliği olan EA müşterileri tarafından kullanılabilir.

   Microsoft 365 Multi-Geo'yu kullanmaya başlamadan önce, Microsoft'un birden fazla coğrafi konumlu destek için Exchange Online kiracınızı yapılandırması gerekir. Bu tek seferlik yapılandırma işlemi, *Microsoft 365 hizmet planında Multi-Geo Capabilities* sipariş ettikten ve lisanslar kiracınızda göründükten sonra tetiklenir. Kiracınız her iş yükü için yapılandırma işlemini tamamladıktan sonra [Microsoft 365 ileti merkezinde](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) iş yüküne özel bildirimler alırsınız ve ardından Microsoft 365 Multi-Geo Capabilities’i yapılandırmaya ve kullanmaya başlayabilirsiniz. Bir kiracıyı Multi-Geo desteği için yapılandırmak için gereken süre kiracıdan kiracıya değişir ancak çoğu kiracı özellik lisansları aldıktan sonra bir ay içinde tamamlanır. Daha büyük veya daha karmaşık kiracılar, yapılandırma sürecini tamamlamak için daha fazla zaman gerektirebilir. Gerekli olması halinde kiracınız hakkındaki ayrıntılar için lütfen hesap ekibinize başvurun.

2. [Birden fazla coğrafi konumlu ortamınızı planlayın](plan-for-multi-geo.md)'ı okuyun.

3. [Birden fazla coğrafi konumlu ortamını yönetme](administering-a-multi-geo-environment.md) ve [kullanıcılarınızın ortamı deneyimlemesi](multi-geo-user-experience.md) hakkında bilgi edinin.

4. Microsoft 365 Multi-Geo'yu ayarlamaya hazır olduğunuzda, [kiracınızı birden fazla coğrafi konum için yapılandırın](multi-geo-tenant-configuration.md).

5. [Arama ayarlaması](configure-search-for-multi-geo.md).

## <a name="see-also"></a>Ayrıca bkz.

[Exchange Online ve OneDrive'da Multi-Geo](https://Aka.ms/GoMultiGeo)

[OneDrive ve SharePoint Online’da Multi-Geo Özellikleri](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Exchange Online'da Multi-Geo Capabilities](multi-geo-capabilities-in-exchange-online.md)

[Birden fazla coğrafi konumlu ortamda Teams deneyimi](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
