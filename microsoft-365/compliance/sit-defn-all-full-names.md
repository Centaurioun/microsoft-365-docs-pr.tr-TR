---
title: Tüm tam adlar varlık tanımı
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
description: Tüm tam adlara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 727448848dbc3a4ea46b83ec404b4c9151ea192e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948798"
---
# <a name="all-full-names"></a>Tüm tam adlar

Tüm tam adlar, paketlenmiş adlı bir varlıktır. Avustralya, Çin, Japonya, ABD ve AB'deki ülkeleri içeren tüm desteklenen ülkelerden/bölgelerden gelen kişilerin tam adlarını algılar. Tam adların tüm olası eşleşmelerini algılamak için bu SIT'i kullanın.

## <a name="format"></a>Biçim

Çeşitli.

## <a name="pattern"></a>Desen

Çeşitli.

## <a name="checksum"></a>Sağlama toplamı

Hayır.

## <a name="description"></a>Açıklama

Bu adlandırılmış varlık SIT, bir insanın yüksek güvene sahip bir ad olarak tanımlayacağı kişisel adlarla eşleşir. Örneğin, belirli bir addan oluşan bir dize bulunursa ve ardından bir aile adı gelirse, yüksek güvenle bir eşleşme yapılır. Üç birincil kaynak kullanır:

- Verilen adların sözlüğü.
- Aile adlarının sözlüğü.
- Adların nasıl oluşturulduğuna ait desenler.

Üç kaynak her ülke için farklıdır.  *Olivia Wilson'ın* dizeleri eşleşmeyi tetikler. Sık kullanılan verilen/aile adları nadir adlara göre daha yüksek bir güvene sahip olur. Ancak, desen kısmi eşleşmelere de izin verir. Sözlükten belirli bir ad bulunursa ve bunu sözlükte olmayan bir aile adı izlerse, kısmi bir eşleşme tetikler. Örneğin *, Tomas Richard* kısmi eşleşme tetikler. Kısmi eşleşmelere daha düşük güvenilirlik verilir.

Ayrıca, bir insanın adların göstergesi olarak göreceği desenler de uygun güvenle eşleştirilir. *O. Wilson*, *O.P. Wilson*, *Dr. O. P. Wilson**, Wilson, O.P. gibi.* ya da *T. Richard, Jr.* eşleşme olabilir.

## <a name="supported-languages"></a>Desteklenen diller

- English
- Bulgarian
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