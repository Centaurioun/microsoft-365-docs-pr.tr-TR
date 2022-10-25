---
title: Arama sorgunuzda hata olup olmadığını kontrol etme
description: Aramayı çalıştırmadan önce eBulma aramaları için anahtar sözcük sorgunuzdaki hataları ve yazım hatalarını algılamayı öğrenin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
ms.collection:
- tier1
- purview-compliance
- ediscovery
ms.openlocfilehash: 30aebce0734c7e9043516cb058fb1aceaa79c9ef
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688038"
---
# <a name="check-your-search-query-for-errors"></a>Arama sorgunuzda hata olup olmadığını kontrol etme
  
İçerik arama ve Microsoft Purview eKeşif (Standart) için arama sorgularında denetlediğimiz desteklenmeyen karakterlerin listesi aşağıdadır. Desteklenmeyen karakterler genellikle gizlenir ve genellikle bir arama hatasına neden olur veya istenmeyen sonuçlar döndürür.
  
- **Akıllı tırnak işaretleri** - Akıllı tek ve çift tırnak işaretleri (kıvrımlı tırnak olarak da adlandırılır) desteklenmez. Arama sorgusunda yalnızca düz tırnak işaretleri kullanılabilir.
- **Yazdırılamayan ve denetim karakterleri** - Yazdırılamayan ve denetim karakterleri, alfasayısal karakter gibi yazılı bir simgeyi temsil etmez. Yazdırılamayan karakterlere ve denetim karakterlerine örnek olarak, metni biçimlendiren karakterler veya ayrı metin satırları verilebilir.
- **Soldan sağa ve sağdan sola işaretler** - Bu işaretler, soldan sağa dillerin (İngilizce ve İspanyolca gibi) ve sağdan sola dillerin (Arapça ve İbranice gibi) metin yönünü belirtmek için kullanılan denetim karakterleridir.
- **Küçük HarfLi Boole işleçleri** - Bir arama sorgusunda **AND**, **OR** ve **NOT** gibi bir Boole işleci kullanıyorsanız, büyük harfle yazılmalıdır. Bir sorguda yazım hatası olup olmadığını denetlediğimizde, sorgu söz dizimi genellikle küçük harf işleçleri kullanılsa bile Boole işlecinin kullanıldığını gösterir; örneğin,  `(WordA or WordB) and (WordC or WordD)`.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>Sorgu desteklenmeyen bir karaktere sahipse ne olur?

Sorgunuzda desteklenmeyen karakterler bulunursa desteklenmeyen karakterlerin bulunduğunu belirten ve alternatif bir seçenek öneren bir uyarı iletisi görüntülenir. Ardından özgün sorguyu tutma veya önerilen düzeltilmiş sorguyla değiştirme seçeneğiniz vardır.

Önceki ekran görüntüsünde **Arama sorgusu için yazım hatalarını denetle'yi** seçtikten sonra görüntülenen uyarı iletisinin bir örneğini aşağıda bulabilirsiniz. Özgün sorgunun akıllı tırnak işaretleri ve küçük harf Boole işleçleri kullandığını unutmayın.
  
![Sorgunuz için önerilen düzeltmeyle birlikte bir uyarı iletisi görüntülenir.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Arama sorgularınızda desteklenmeyen karakterleri önleme

Desteklenmeyen karakterler genellikle sorguyu veya sorgunun bölümlerini diğer uygulamalardan (Microsoft Word veya Microsoft Excel gibi) kopyalayıp İçerik Arama'nın sorgu sayfasındaki anahtar sözcük kutusuna yapıştırdığınızda sorguya eklenir. Desteklenmeyen karakterleri önlemenin en iyi yolu, sorguyu anahtar sözcük kutusuna yazmaktır. Ya da Word veya Excel'den bir sorgu kopyalayıp Microsoft Not Defteri gibi düz bir metin düzenleyicisine yapıştırabilirsiniz. Metin dosyasını kaydedin ve **Kodlama** açılan listesinde **ANSI'yi** seçin. Bu, tüm biçimlendirmeleri ve desteklenmeyen karakterleri kaldırır. Ardından sorguyu kopyalayıp metin dosyasından anahtar sözcük sorgu kutusuna yapıştırabilirsiniz.
