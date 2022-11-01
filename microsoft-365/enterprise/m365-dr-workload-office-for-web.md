---
title: Web için Office Data Residency
description: Web için Office Data Residency
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
ms.openlocfilehash: ed0c8f67eedf666c7a20d2169d64bc2fad41f576
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806116"
---
# <a name="data-residency-for-office-for-the-web"></a>Web için Office Data Residency

## <a name="overview"></a>Genel bakış

Hizmet belgeleri: [Web için Office hizmet açıklaması - Hizmet Açıklamaları](/office365/servicedescriptions/office-online-service-description/office-online-service-description)

Yetenek özeti: Web için Office (eski adıyla Office Web Apps), Web tarayıcınızda Word, Excel ve PowerPoint belgelerini açar. Web için Office, Office dosyalarının neredeyse tüm cihazlardan İnternet bağlantısıyla her yerden çalışmasını ve paylaşılması kolaylaşır. Word, Excel veya PowerPoint'e sahip Microsoft 365 müşterileri, dosyaları yolda görüntüleyebilir, oluşturabilir ve düzenleyebilir.

## <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının__, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir _Gelişmiş Data Residency_ _aboneliğine sahiptir_.
1. Web aboneliği için Office müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

Web için Office'e yönelik bekleyen taahhüt kapsamındaki belirli müşteri verileri için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#office-for-the-web) bakın.

### <a name="migration"></a>Geçiş

Belgeler için önbellek yeni _Coğrafya'ya_ geçirilmez ve kullanıcılar belgeler üzerinde çalışırken yeniden oluşturulur.

### <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

_Kiracı_ Yönetici Merkezi'nde gerçek veri konumunu güncelleştirme sürecindeyiz. Bu değişiklik tamamlandığında kiracı, kapsam verileri için gerçek veri konumunu Yönetici| Ayarlar| Kuruluş Ayarları| Kuruluş Profili| Veri Konumu. Bu değişiklik görünene kadar, kapsam verilerinin bu hizmet için nerede depolandığını anlamak için Exchange Online verilerini veya SharePoint Online konum bilgilerini görüntüleyebilirsiniz.
