---
title: Office P1 için Microsoft Defender için Data Residency
description: Office P1 için Microsoft Defender Data Residency hakkında bilgi edinin
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
ms.openlocfilehash: 4e4c002ca4748b2d125c0b8043e6198ac962115f
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806205"
---
# <a name="data-residency-for-microsoft-defender-for-office-p1"></a>Office P1 için Microsoft Defender için Data Residency

## <a name="overview"></a>Genel bakış

Hizmet belgeleri: [Office 365 için Microsoft Defender ve Exchange Online Protection dahil Office 365 Güvenliği](/microsoft-365/security/office-365-security/defender-for-office-365)

Yetenek Özeti: E-postayı ve işbirliğini sıfır günlük kötü amaçlı yazılımlardan, kimlik avından ve iş e-posta güvenliğinin aşılmasına karşı korur.  MDO P1, Exchange Online Protection (EOP) üzerinde derler.  

## <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının__, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_
1. MDO P1 aboneliği müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

Office P1 için Microsoft Defender için bekleyen müşteri verileri için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#microsoft-defender-for-office-p1) bakın.

Diğer Bilgiler

Ayrıca, tehditleri analiz etmek ve şüpheli e-postaları, belgeleri, iletileri ve bağlantıları incelemek için gereken verilerin işlenmesi bir korumalı alan ortamında yapılır ve _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge_ içinde gerçekleştirilir.

## <a name="exchange-online-protection"></a>Exchange Online Protection

### <a name="overview"></a>Genel bakış

Hizmet belgeleri: [Exchange Online Protection (EOP) genel bakış](/microsoft-365/security/office-365-security/exchange-online-protection-overview)

Yetenek özeti: Exchange Online Protection (EOP), kuruluşunuzu istenmeyen postalara, kötü amaçlı yazılımlara ve diğer e-posta tehditlerine karşı koruyan bulut tabanlı filtreleme hizmetidir.

### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

#### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının_ _Yerel Bölge Coğrafyası veya Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi _vardır_.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_
1. EOP aboneliği müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır

**Taahhüt:**

Exchange Online Protection için bekleyen taahhüt kapsamındaki belirli müşteri verileri için [gelişmiş Data Residency Taahhüdü](m365-dr-commitments.md) sayfasına bakın.

## <a name="migration"></a>Geçiş

EOP müşteri verileri, Exchange Online geçişi sırasında geçirildi. MDO P1'de geçirilecek müşteri verileri yok.

## <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

_Kiracı_ Yönetici Merkezi'ndeki gerçek veri konumunu güncelleştirme sürecindeyiz. Bu değişiklik tamamlandığında, Yönetici| Ayarlar| Kuruluş Ayarları| Kuruluş Profili| Veri Konumu. Bu değişiklik görünene kadar, kapsam dahilindeki müşteri verilerinizin bu hizmet için nerede depolandığını anlamak için Exchange Online veri konumu bilgilerini görüntüleyebilirsiniz.
