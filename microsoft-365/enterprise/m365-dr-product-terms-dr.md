---
title: Ürün Koşullarına Genel Bakış Data Residency
description: Ürün Koşulları Data Residency hakkında bilgi edinin
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
ms.openlocfilehash: 0ea7e9b9915bb44655905f406c4acf117b27899a
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812921"
---
# <a name="overview-of-product-terms-data-residency"></a>Ürün Koşullarına Genel Bakış Data Residency

Microsoft'un Bulut ürün koşullarına dahil edilen Microsoft Gizlilik ve Güvenlik ürün koşulları, aşağıdaki kapsama sahip veri yerleşimi taahhüdü sağlar:

1. Çevrimiçi Hizmetler: Exchange Online, SharePoint Online ve Microsoft Teams [ihtiyaç tarihi] itibarıyla.
2. Taahhüt süresi: Müşterilerin Microsoft ile sözleşmelerinin uzunluğu. Genellikle bu 1-3 yıldır.
3. Ülke/bölgeler dahil: Yerel Coğrafyalar, Birleşik Devletler ve Avrupa Birliği.

Bu makaleyi yazarken dil şu şekildedir:

- **Office 365 Hizmetleri** Müşteri Avustralya, Brezilya, Kanada, Avrupa Birliği, Fransa, Almanya, Hindistan, Japonya, Norveç, Katar, Güney Afrika, Güney Kore, İsveç, İsviçre, Birleşik Krallık, Birleşik Arap Emirlikleri veya Birleşik Devletler kiracısını sağlarsa, Microsoft şu Müşteri Verilerini yalnızca bu Coğrafi Bölge içinde bekleyen olarak depolar: (1) Exchange Online posta kutusu içeriği (e-posta gövdesi, takvim girişleri ve e-posta eklerinin içeriği), (2) SharePoint Online site içeriği ve bu site içinde depolanan dosyalar, (3) OneDrive İş yüklenen dosyalar ve (4) Microsoft Teams sohbet iletileri (özel iletiler, kanal iletileri, toplantı iletileri ve sohbetlerde kullanılan görüntüler dahil) ve kullanan müşteriler için Microsoft Stream (SharePoint'te), toplantı kayıtları.
- Geçerli dil için Gizlilik ve Güvenlik Ürün Koşulları <a href="https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all" target="_blank">web sayfasına</a> bakın ve "Core Online Services için Bekleyen Müşteri Verilerinin Konumu" başlıklı bölümü görüntüleyin.

Ek veri yerleşimi özellikleri için [_Multi-Geo_ hizmetine](microsoft-365-multi-geo.md) ve/veya [_Gelişmiş Data Residency_ hizmetine](advanced-data-residency.md) bakın.

## <a name="product-terms-data-residency-migration"></a>Geçiş Data Residency Ürün Koşulları

Microsoft'un veri merkezleri _Yerel Bölge Coğrafyaları'nda_ başlatıldığında, uygun _Varsayılan Coğrafyaya_ sahip herhangi bir _Kiracının_ verilerini _Yerel Bölge Coğrafyalarına_ taşımayı kabul etmesi mümkündü. Bu kabul süresi, Veri Merkezi faaliyete geçtikten sonra altı ay boyunca açıktı.

Pratik olarak bu, _Makro Bölgesi Coğrafyası_ veri merkezlerinde taşınmayı ve burada kalmayı kabul etmeyen bir dizi kiracı olduğu anlamına gelir. 1 Kasım 2022 tarihinde veya 1 Kasım 2022'de Gelişmiş Data Residency eklentisinin kullanıma sunulmasıyla birlikte _, Makro Bölgesi Coğrafyası_ veri merkezlerinde kalan tüm kiracıların _Yerel Bölge Coğrafyasına_ veri geçişini kabul etmek için altı ay daha süresi olacaktır.  Diğer ayrıntılar için [Eski Taşıma Programı sayfasına](m365-dr-legacy-move-program.md#how-to-request-your-data-move---final-opportunity) bakın.
