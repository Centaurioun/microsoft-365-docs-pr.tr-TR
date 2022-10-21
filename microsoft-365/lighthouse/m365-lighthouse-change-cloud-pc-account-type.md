---
title: Microsoft 365 Lighthouse'da Windows 365 Business Cloud PC hesap türünü değiştirme
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: katmartin
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için Windows 365 Business Cloud PC hesap türünü ayarlamayı veya değiştirmeyi öğrenin.
ms.openlocfilehash: 75446c284a61672d08d96e866278c9abfc567e28
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68661078"
---
# <a name="change-a-windows-365-business-cloud-pc-account-type-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'da Windows 365 Business Cloud PC hesap türünü değiştirme

Yönetilen Hizmet Sağlayıcısı (MSP) teknisyenleri bir İş Bulutu bilgisayarı için hesap türünü ayarlayabilir veya mevcut bir hesap türünde değişiklik yapabilir. Aşağıdaki hesap türleri kullanılabilir:

- **Standart kullanıcı (Önerilen)** - Standart kullanıcı hesaplarının yalnızca Microsoft Store'dan yazılım yükleme izni vardır.

- **Yerel yönetici** - Yerel yönetici hesapları, herhangi bir yazılımı yükleme ve işletim sisteminin herhangi bir bölümünde değişiklik yapma iznine sahiptir. Kötü amaçlı yazılımlar dosyalara bulaşmak veya dosyalara zarar vermek için yönetici izinlerini kullanabileceğinden bu hesap türünü yalnızca gerektiğinde seçin.

> [!NOTE]
> Hesap türünü yalnızca İş lisansına sahip Bulut bilgisayarlar için ayarlayabilir veya değiştirebilirsiniz. Kurumsal lisansa sahip Bulut bilgisayarların hesap türünü değiştiremezsiniz.

## <a name="before-you-begin"></a>Başlamadan önce 

İş ortağı kiracısında Windows 365 Yöneticisi veya Genel Yönetici olmanız gerekir.

## <a name="set-or-change-a-windows-365-business-cloud-pc-account-type"></a>Windows 365 Business Cloud PC hesap türünü ayarlama veya değiştirme

1.  Lighthouse'un sol gezinti bölmesinde **Cihazlar** >  **Windows 365'ı** seçin.

2.  **Tüm Bulut Bilgisayarları** sekmesini seçin.

3.  **Sağlanan** durumu olan Bulut bilgisayarlarda detaya gitmek için renkli count-annotation çubuğunu kullanın.

4.  **Filtreler** açılan **menüsünden İş** lisans türünü seçerek müşteri kiracılarınızda İş lisansına sahip tüm Bulut bilgisayarların listesini görüntüleyin.

5.  Bulut bilgisayarlar listesinden, hesap türünü değiştirmek istediğiniz Bulut bilgisayarı seçin.

6.  Bulut bilgisayar ayrıntıları bölmesinde **Hesap türünü değiştir'i** seçin.

7.  **Bulut bilgisayarı hesap türünü değiştir** bölmesinde, Bulut bilgisayar için hesap türünü seçin ve ardından **Kaydet'i** seçin.

## <a name="next-steps"></a>Sonraki adımlar

Güncelleştirme uygulandıktan sonra, Bulut bilgisayarın atanan kullanıcısının Cloud PC'de yeniden oturum açması veya cihazını yeniden başlatması gerekir. Yeni değişikliklerin Microsoft 365 Lighthouse görünmesi birkaç dakika sürebilir. Cloud PC Yöneticisi ayrıca Cloud PC'yi uzaktan yeniden başlatabilir, ancak kullanıcı kaydedilmemiş verileri kaybedebilir.

## <a name="related-content"></a>İlgili içerik

[Bulut bilgisayar rol tabanlı erişim denetimi](/windows-365/enterprise/role-based-access) (makale)\
[Microsoft 365 Lighthouse Windows 365 (Bulut Bilgisayarları) sayfasına genel bakış](m365-lighthouse-win365-page-overview.md) (makale)\
[Microsoft 365 Lighthouse'de Windows 365 Bulut PC yeniden sağlama](m365-lighthouse-reprovision-cloudpc.md) (makale)
