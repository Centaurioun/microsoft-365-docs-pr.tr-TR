---
title: Microsoft 365 Multi-Geo kiracı yapılandırması
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: Bu makalede, microsoft 365 Multi-Geo için uydu konumları eklemeyi ve kiracınızı yapılandırmayı öğrenin.
ms.openlocfilehash: a656dc718dfaac14d87ea0ae5e1fa792d41a0648
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804696"
---
# <a name="microsoft-365-multi-geo-_tenant_-configuration"></a>Microsoft 365 Multi-Geo _Kiracı_ yapılandırması

_Kiracınızı_ Microsoft 365 Multi-Geo için yapılandırmadan önce [Microsoft 365 Multi-Geo planı](plan-for-multi-geo.md) makalesini okuduğunuzdan emin olun.

Bu makaledeki adımları izlemek için _, Uydu Coğrafya_ konumları olarak etkinleştirmek istediğiniz _Coğrafya_ konumlarının ve bu konumlar için sağlamak istediğiniz test kullanıcılarının listesi gerekir.

Tüm Multi-Geo iş yükleri müşteri odaklı yapılandırma gerektirmez.

## <a name="configuring-exchange-online-for-multi-geo"></a>Multi-Geo için Exchange Online yapılandırma

Multi-Geo özellikli _bir Kiracıda_ Exchange Online hazırlamak için müşteri odaklı yapılandırma gerekmez. Müşteri _, Kiracısı_ için Exchange Online içinde Multi-Geo etkinleştirildiğinde Exchange Online tüm Coğrafyaları kullanabilir.

## <a name="configuring-microsoft-teams-for-multi-geo"></a>Multi-Geo için Microsoft Teams'i yapılandırma

Multi-Geo özellikli bir kiracıda Microsoft Teams'i hazırlamak için müşteri odaklı yapılandırma gerekmez. Müşteri, _Kiracısı_ için Microsoft Teams'de Multi-Geo etkinleştirildikten hemen sonra Microsoft Teams ile tüm Coğrafyaları kullanabilir.

## <a name="configuring-sharepoint-online-and-onedrive-for-business-for-multi-geo"></a>Multi-Geo için SharePoint Online ve OneDrive İş yapılandırma

Verileri belirli bir Coğrafyada depolamak istiyorsanız, bu Coğrafyanın önceden SharePoint Online ve OneDrive için yapılandırılması gerekir.

SharePoint Online'da ve OneDrive İş _Kiracınız_ için Multi-Geo etkinleştirildikten sonra **, Coğrafi Konumlar** sekmesi OneDrive İş ve SharePoint Online yönetim merkezlerinde kullanılabilir duruma gelir. **Coğrafi Konumlar** sekmesini görmüyorsanız _, Kiracınızın_ Multi-Geo için etkinleştirilmesi henüz tamamlanmamıştır.

SharePoint ve OneDrive için verileri depolamak istediğiniz her Uydu Coğrafya konumunu eklemek için:

1. SharePoint yönetim merkezini açın. ve **Coğrafi konumlara** gidin.
1. **Konum ekle'yi** seçin.
1. Eklemek istediğiniz konumu seçin ve ardından **İleri'yi** seçin.
1. Coğrafi konumla kullanmak istediğiniz etki alanını yazın ve **Ekle'yi** seçin.
1. **Kapat**'ı seçin.

_Sağlama, Kiracınızın_ boyutuna bağlı olarak birkaç saatten 72 saate kadar sürebilir. _Uydu Coğrafya_ konumunun sağlanması tamamlandıktan sonra bir e-posta onayı alırsınız. Yeni _Coğrafya_ konumu, OneDrive ve SharePoint yönetim merkezindeki Coğrafi konumlar sekmesindeki haritada mavi renkte göründüğünde, kullanıcıların tercih ettiği veri konumunu bu _Coğrafya_ konumuna ayarlamaya devam edebilirsiniz.

> [!IMPORTANT]
> Yeni _Uydu Coğrafya_ konumunuz varsayılan ayarlarla ayarlanır. Bu, _uydu coğrafya_ konumunu yerel uyumluluk gereksinimlerinize uygun şekilde yapılandırmanıza olanak sağlar.
