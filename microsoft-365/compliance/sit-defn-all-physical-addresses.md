---
title: Tüm Fiziksel Adresler varlık tanımı
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Tüm Fiziksel Adresler hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 3d8b40d6362c2a39525959467f524bc83c7cc3c8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948725"
---
# <a name="all-physical-addresses"></a>Tüm Fiziksel Adresler

Tüm fiziksel adresler, desteklenen tüm ülkelerden/bölgelerden fiziksel adreslerle ilgili desenleri algılayan paketlenmiş bir varlık SIT'tir.

## <a name="format"></a>Biçim

Çeşitli

## <a name="pattern"></a>Desen

Çeşitli

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="description"></a>Açıklama

Sokak adreslerinin eşleşmesi, bir insanın sokak adresi olarak tanımlayacağı dizelerle eşleşecek şekilde tasarlanmıştır. Bunu yapmak için birkaç birincil kaynak kullanır:

- Yerleşimler, ilçeler ve bölgelerin sözlüğü.
- Yol, Sokak veya Avenue gibi sokak sonekleri sözlüğü.
- Posta kodlarının desenleri.
- Adres biçimlerinin desenleri.

Kaynaklar her ülke için farklıdır. Birincil kaynaklar, belirli bir ülkede kullanılan adres biçimlerinin desenleridir. Mümkün olduğunca çok adresin eşleştiğinden emin olmak için farklı biçimler seçilir. Bu biçimler esneklik sağlar; örneğin, bir adres posta kodunu atlar veya bir şehir adını atlar veya sokak soneki olmayan bir caddeye sahip olabilir. Her durumda, bu tür eşleşmeler eşleşmenin güvenilirliğini artırmak için kullanılır.

Desenler, genel konumlarla değil tek tek adreslerle eşleşecek şekilde tasarlanmıştır. Bu nedenle *Redmond, WA 98052* veya *Main Street, Albuquerque* gibi dizeler eşleştirilmeyecek.

## <a name="contains"></a>Içerir

Bu paketlenmiş adlandırılmış varlık SIT şu ayrı SID'leri içerir:

- Avustralya fiziksel adresleri
- Avusturya fiziksel adresleri
- Belçika fiziksel adresleri
- Brezilya fiziksel adresleri
- Bulgaristan fiziksel adresleri
- Kanada fiziksel adresleri
- Hırvatistan fiziksel adresleri
- Kıbrıs fiziksel adresleri
- Çek Cumhuriyeti fiziksel adresleri
- Danimarka fiziksel adresleri
- Estonya fiziksel adresleri
- Finlandiya fiziksel adresleri
- Fransa fiziksel adresleri
- Almanya fiziksel adresleri
- Yunanistan fiziksel adresleri
- Macaristan fiziksel adresleri
- İzlanda fiziksel adresleri
- İrlanda fiziksel adresleri
- İtalya fiziksel adresleri
- Letonya fiziksel adresleri
- Liechtenstein fiziksel adresleri
- Litvanya fiziksel adresleri
- Lüksemburg fiziksel adresleri
- Malta fiziksel adresleri
- Hollanda fiziksel adresleri
- Yeni Zelanda fiziksel adresleri
- Norveç fiziksel adresleri
- Polonya fiziksel adresleri
- Portekiz fiziksel adresleri
- Romanya fiziksel adresleri
- Slovakya fiziksel adresleri
- Slovenya fiziksel adresleri
- İspanya fiziksel adresleri
- İsveç fiziksel adresleri
- İsviçre fiziksel adresleri
- Türkiye fiziksel adresleri
- Birleşik Krallık fiziksel adresleri
- Fiziksel adresleri Birleşik Devletler

## <a name="supported-languages"></a>Desteklenen diller

- English
- Bulgarian
- Çince
- Croatian
- Czech
- Danish
- Estonian
- Finnish
- French
- German
- Hungarian
- İzlanda dili
- İrlanda dili
- Italian
- Japanese
- Latvian
- Lithuanian
- Malta dili
- Dutch
- Norveç dili
- Polish
- Portekizce
- Romanian
- Slovak
- Slovenian
- Spanish
- Swedish
- Turkish