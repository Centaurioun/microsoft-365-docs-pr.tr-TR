---
title: Contoso Corporation'a genel bakış
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation'ı bir işletme olarak ve dünya çapındaki ofislerinin katmanlı yapısını anlayın.
ms.openlocfilehash: dbaac2a60e47843d74ec13effe95a87049b8c9ea
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178899"
---
# <a name="overview-of-contoso-corporation"></a>Contoso Corporation'a genel bakış

Contoso Corporation, merkezi Paris'te olan çok uluslu bir işletmedir. Şirket, 100.000'den fazla ürünü olan bir üretim, satış ve destek kuruluşudur.

## <a name="contoso-around-the-world"></a>Dünyanın dört bir yanındaki Contoso

Şekil 1'de Paris'teki merkez ofisi ve çeşitli kıtalardaki bölgesel merkez ve uydu ofisleri gösterilmektedir.

![Dünyanın dört bir yanındaki Contoso ofisleri.](../media/contoso-overview/contoso-overview-fig1.png)

**Şekil 1: Dünyanın dört bir yanındaki Contoso ofisleri**
 
Contoso'nun üç ofis katmanı vardır:

- Genel Müdürlük

  Contoso genel merkezi, Paris'in eteklerinde, yönetim, mühendislik ve üretim tesisleri için onlarca bina içeren bir şirket kampüsüdür. Tüm Contoso veri merkezleri ve İnternet varlığı Paris'in merkezinde yer almaktadır.

  Merkezde 25.000 işçi var.

- Bölgesel merkezler

  Merkez ofisleri, yüzde 60 satış ve destek personeliyle dünyanın belirli bir bölgesine hizmet sağlar. Her bölgesel merkez, yüksek bant genişliğine sahip BIR WAN bağlantısı aracılığıyla Paris genel merkezine bağlanır.

  Bölgesel merkezlerde ortalama 2.000 çalışan vardır.

- Uydu ofisleri

  Uydu ofisleri yüzde 80 satış ve destek personeli içerir. Önemli şehirlerdeki veya alt bölgelerdeki Contoso müşterileri için yerinde iletişim durumu sağlar. Her uydu ofis, yüksek bant genişliğine sahip WAN bağlantısı aracılığıyla bölgesel bir hub'a bağlanır.

  Uydu ofislerinde ortalama 250 işçi var.

Contoso iş gücünün yaklaşık yüzde 25'i yalnızca mobildir. Bölgesel merkezlerde ve uydu ofislerde bu çalışanların yüzdesi daha yüksektir. Yalnızca mobil çalışanlara daha iyi destek sağlamak Contoso için önemli bir iş hedefidir.

## <a name="design-considerations-for-microsoft-365-for-enterprise"></a>Kuruluş için Microsoft 365'e yönelik tasarım konuları

Contoso BT mimarları, kuruluş için Microsoft 365'i dağıtmak için aşağıdaki tasarım gereksinimi faktörlerini tanımladı:

- Yerel düzenlemelere ve uyumluluk gereksinimlerine sahip birden çok coğrafi konum
- Şirket içi iş kolu uygulamalarını barındıran merkez ofis ve bölgesel uygulama sunucularında merkezi intranet veri merkezi
- Mevcut bir Microsoft Endpoint Configuration Manager altyapısı
- Windows, Mac ve Linux çalıştıran istemci bilgi işlem cihazlarının bir karışımı
- iOS (iPhone ve iPad) ve Android akıllı telefonlar ve tabletler dahil olmak üzere kişisel ve şirkete ait mobil cihazların bir karışımı
- Birçok uzak ve mobil çalışan
- Birçok iş ortağı
- Yönetmek ve güvenliğini sağlamak için büyük miktarda müşteri ve diğer gizli kişisel bilgiler
- Ürünler ve üretim ticari sırları için tasarım belirtimleri biçiminde büyük miktarda yüksek değerli fikri mülkiyet

## <a name="next-step"></a>Sonraki adım

Contoso Corporation [şirket içi BT altyapısı](contoso-infra-needs.md) ve şirket için Microsoft 365 kurumsal gereksinimlerinin nasıl karşılandığı hakkında bilgi edinin.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)
