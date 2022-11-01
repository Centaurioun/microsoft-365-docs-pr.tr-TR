---
title: Viva Topics için Data Residency
description: Viva Topics için Data Residency
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
ms.openlocfilehash: 416e6dccca24e4c79c0853cbed886b2d4e977c31
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806148"
---
# <a name="data-residency-for-viva-topics"></a>Viva Topics için Data Residency

## <a name="summary"></a>Özet

Hizmet belgeleri: [Microsoft Viva Topics genel bakış](/viva/topics/topic-experiences-overview)

Yetenek özeti: Viva Topics, SharePoint modern sayfaları, Outlook, Microsoft Search ve Word, PowerPoint ve Excel'de Arama'dan başlayarak, her gün kullandıkları Microsoft 365 uygulamalarında kullanıcılarınıza bilgi sunmak için Microsoft Yapay Zeka teknolojisi, Microsoft 365, Microsoft Graph, Arama ve diğer bileşen ve hizmetleri kullanır.

## <a name="data-residency-commitments-available"></a>Data Residency Taahhütleri Kullanılabilir

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının__, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_.
1. Viva Topics aboneliği müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

Viva Topics için bekleyen taahhüt kapsamındaki belirli müşteri verileri için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#viva-topics) bakın.

## <a name="migration"></a>Geçiş

Depolanan veriler Exchange Online, SharePoint Online ve Microsoft Teams'de tutulur.  Geçiş işlemleri ilgili/ilgili iş yükleri tarafından işlenir.

## <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

_Kiracı_ Yönetici Merkezi'nde gerçek veri konumunu güncelleştirme sürecindeyiz.  Bu değişiklik tamamlandığında, Yönetici->Settings->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek, işlenen veriler için gerçek veri konumunu görebilirsiniz.  Bu değişiklik görünene kadar, bu hizmet için kaydedilmiş verilerinizin nerede depolandığını anlamak için Exchange Online veri konumu bilgilerini görüntüleyebilirsiniz.
