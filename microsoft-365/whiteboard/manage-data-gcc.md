---
title: GCC ortamlarında Microsoft Whiteboard için verileri yönetme
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Whiteboard erişimini etkinleştirmeyi, devre dışı bırakmayı ve yönetmeyi öğrenin.
ms.openlocfilehash: 681993a060c85dcd7b71753b00698d5a56636565
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67876511"
---
# <a name="manage-data-for-microsoft-whiteboard-in-gcc-environments"></a>GCC ortamlarında Microsoft Whiteboard için verileri yönetme

>[!NOTE]
> Bu kılavuz US Government Community Cloud (GCC) ortamları için geçerlidir.

Veriler OneDrive İş.whiteboard dosyaları olarak depolanır. Ortalama beyaz tahta boyutu 50 KB ile 1 MB arasında olabilir ve OneDrive İş içeriğinizin bulunduğu her yerde bulunabilir. Yeni verilerin nerede oluşturulduğunu denetlemek için bkz. [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations). OneDrive İş konumuna bakın. OneDrive İş'daki genel dosyalara uygulanan tüm özellikler, dış paylaşım dışında Whiteboard için de geçerlidir.

Mevcut OneDrive İş denetimlerini kullanarak Whiteboard verilerini yönetebilirsiniz. Daha fazla bilgi için bkz. [Kuruluşlar için OneDrive kılavuzu](/onedrive/plan-onedrive-enterprise).

Genel Veri Koruma Yönetmeliği (GDPR) için veri sahibi isteklerini (DSR) karşılamak için mevcut OneDrive İş araçlarını kullanabilirsiniz. Beyaz Tahta dosyaları, OneDrive İş'daki diğer içerikle aynı şekilde taşınabilir. Ancak, paylaşım bağlantıları ve izinleri taşınamayabilir.

Verileri yönetmek için önce Whiteboard'un kuruluşunuz için etkinleştirildiğinden emin olmanız gerekir. Daha fazla bilgi için bkz. [GCC ortamlarında Whiteboard erişimini yönetme](manage-whiteboard-access-gcc.md).

## <a name="data-controls-supported"></a>Desteklenen veri denetimleri

Şu anda Whiteboard'da aşağıdaki veri denetimleri desteklenmektedir:

- Bekletme ilkeleri
- Kota
- Yasal tutma
- Veri Kaybı Önleme (DLP)
- Temel eBulma: Beyaz Tahtalar, oluşturucunun OneDrive İş .whiteboard dosyaları olarak depolanır. Anahtar sözcük ve dosya türü araması için dizine eklenmiştir, ancak önizleme/gözden geçirme için kullanılamaz. Dışarı aktarma işleminin ardından, bir yöneticinin içeriği görüntülemek için dosyayı OneDrive İş'a geri yüklemesi gerekir. Gelecek için daha fazla destek planlanıyor.

## <a name="data-controls-planned"></a>Planlanan veri denetimleri

Whiteboard'un gelecek sürümleri için aşağıdaki veri denetimleri planlanıyor:

- Duyarlılık etiketleri
- Analytics
- Daha fazla eBulma desteği
- SharePoint sitelerinde beyaz tahtaları depolama

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard erişimini yönetme - GCC](manage-whiteboard-access-gcc.md)

[Whiteboard için paylaşımı yönetme - GCC](manage-sharing-gcc.md)

[Whiteboard için istemcileri yönetme - GCC](manage-clients-gcc.md)
