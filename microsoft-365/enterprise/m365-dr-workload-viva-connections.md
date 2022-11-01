---
title: Viva Connections için Data Residency
description: Viva Connections için Data Residency
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: ce1bb0dc936c57493c5fd16e4301adda9e214c8d
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806149"
---
# <a name="data-residency-for-viva-connections"></a>Viva Connections için Data Residency

## <a name="overview"></a>Genel bakış

Hizmet belgeleri: [Genel Bakış: Viva Connections](/viva/connections/viva-connections-overview)

Yetenek Özeti: Microsoft Viva Connections, herkesin etkileşimde ve bilgi sahibi olmasını sağlamak için tasarlanmış modern bir çalışan deneyimine açılan ağ geçidinizdir. Viva Connections, Microsoft Teams'de herkese ilgili haberleri, konuşmaları ve başarılı olması için ihtiyaç duydukları araçları keşfetmek için kişiselleştirilmiş bir hedef sağlayan özelleştirilebilir bir uygulamadır.  Veri depolama aşağıdaki Viva Connections Bileşenleriyle ilgilidir: Pano ve akış.

## <a name="data-residency-commitments-available"></a>Data Residency Taahhütleri Kullanılabilir

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının__, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_.
1. Viva Connections abonelik müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

Viva Connections için bekleyen taahhüt kapsamındaki belirli müşteri verileri için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#viva-connections) bakın.

### <a name="migration"></a>Geçiş

Veriler Exchange Online, SharePoint Online ve Microsoft Teams'de depolanır.  Geçiş işlemleri ilgili/ilgili iş yükleri tarafından işlenir.

### <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

_Kiracı_ Yönetici Merkezi'nde gerçek veri konumunu güncelleştirme sürecindeyiz.  Bu değişiklik tamamlandığında, Yönetici->Settings->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek, işlenen veriler için gerçek veri konumunu görebilirsiniz.  Bu değişiklik görünene kadar, bu hizmet için taahhüt edilen verilerinizin nerede depolandığını anlamak için Exchange Online, SharePoint Online ve Microsoft Teams veri konumu bilgilerini görüntüleyebilirsiniz.
