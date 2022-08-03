---
title: GCC High ortamlarında Microsoft Whiteboard için paylaşımı yönetme
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: GCC High ortamlarında Microsoft Whiteboard için paylaşımı yönetmeyi öğrenin.
ms.openlocfilehash: b6efeac47cec8de02487bf4526891b52c9098079
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175344"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>GCC High ortamlarında Microsoft Whiteboard için paylaşımı yönetme

>[!NOTE]
> Bu kılavuz, ABD Kamu Topluluk Bulutu (GCC) Yüksek ortamları için geçerlidir.

Paylaşım deneyimi, kullanılan cihaz ve istemciye göre farklılık gösterir. 

## <a name="share-in-teams-meetings"></a>Teams toplantılarında paylaşma

Teams toplantısında beyaz tahta paylaştığınızda Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur ve beyaz tahtayı toplantıdaki kiracı içi kullanıcılarla otomatik olarak paylaşır. Beyaz tahtalar, varsayılan ayardan bağımsız olarak şirket tarafından paylaşılabilir bağlantılar kullanılarak paylaşılır. Varsayılan paylaşım bağlantı türü desteği planlandı.

Toplantı sırasında dış ve paylaşılan cihaz hesaplarının çoğu tarafından geçici işbirliği için ek özellik vardır. Bu, kullanıcıların teams toplantısında paylaşıldığında beyaz tahtaları PowerPoint Canlı paylaşımına benzer şekilde geçici olarak görüntülemesine ve üzerinde işbirliği yapmasına olanak tanır.

>[!NOTE]
> Teams toplantısı sırasında dış paylaşım henüz kullanılamamaktadır, ancak gelecek bir sürümde eklenecektir.

|Senaryo |Depolama ve sahiplik |Paylaşım ayarları |Paylaşım deneyimi |
|---------|---------|---------|---------|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı |Henüz kullanılamıyor |Kiracı içi kullanıcılar: Oluşturabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Henüz kullanılamıyor<br><br>Paylaşılan cihaz hesapları: Henüz kullanılamıyor |
|Beyaz tahtayı Surface Hub'dan veya Microsoft Teams Odaları başlatma |Henüz kullanılamıyor |         |         |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams kanallarında ve sohbetlerinde sekme olarak ekleme

Teams kanalına veya sohbete sekme olarak beyaz tahta eklediğinizde Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur.

|Senaryo  |Depolama ve sahiplik  |Paylaşım ayarları  |Paylaşım deneyimi  |
|---------|---------|---------|---------|
|Beyaz tahtayı bir kanala ekleme veya masaüstü veya mobil cihazdan sohbet etme  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Geçerli değil  |Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Desteklenmez  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard yerel istemcilerinde oluşturma ve paylaşma

Web, masaüstü veya mobil istemcilerden bir beyaz tahta paylaştığınızda, belirli kişileri seçebilirsiniz. Kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı da oluşturabilirsiniz. 

>[!NOTE]
> Teams toplantısı sırasında dış paylaşım henüz kullanılamamaktadır, ancak gelecek bir sürümde eklenecektir.

|Senaryo  |Depolama ve sahiplik  |Paylaşım ayarları  |Paylaşım deneyimi  |
|---------|---------|---------|---------|
|Masaüstü veya mobil cihazdan beyaz tahta oluşturma  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Geçerli değil  |Kiracı içi kullanıcılar: Kuruluşlarında paylaşabilir<br><br>Dış kullanıcılar: Dış kullanıcılarla paylaşım şu anda desteklenmiyor  |
|Surface Hub'dan beyaz tahta oluşturma  |Depolama: Yerel<br><br>Sahip: Yok  |Geçerli değil  |Kiracı içi kullanıcılar (yakında): Kullanıcı panoyu kaydetmek ve paylaşmak için oturum açabilecek<br><br>Dış kullanıcılar: Dış kullanıcılarla paylaşım şu anda desteklenmiyor |
|Microsoft Teams Odaları'dan beyaz tahta oluşturma  |Henüz kullanılamıyor         |         |         |

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme - GCC High](manage-whiteboard-access-gcc-high.md)

[Whiteboard için verileri yönetme - GCC High](manage-data-gcc-high.md)

[Whiteboard için istemcileri yönetme - GCC High](manage-clients-gcc-high.md)
