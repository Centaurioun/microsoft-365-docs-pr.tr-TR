---
title: eBulma'da neredeyse yinelenen algılama
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: eBulma'da (Premium) büyük/küçük harf verilerini analiz ederken benzer belgeleri kısa metne göre gruplandırmak için neredeyse yinelenen algılamayı kullanın.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2860f4e516599966483df96b4fa276c334d3603b
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67817917"
---
# <a name="near-duplicate-detection-in-ediscovery-premium"></a>eBulma'da neredeyse yinelenen algılama (Premium)

Bir alt kümenin aynı şablonu temel aldığı ve çoğunlukla aynı ortak dile sahip olduğu, burada ve orada birkaç farkla gözden geçirilecek bir belge kümesini düşünün. Gözden geçiren kişi bu alt kümeyi tanımlayıp bunlardan birini ayrıntılı bir şekilde gözden geçirebilse ve geri kalanlar için farkları gözden geçirebilse, tüm belgelerin kapsanması için yalnızca birkaç zaman ayırarak benzersiz bilgileri kaçırmaz. Yakın yinelenen algılama, inceleme sürecinizi daha verimli hale getirmenize yardımcı olmak için metin olarak benzer belgeleri gruplandırıyor.

## <a name="how-does-it-work"></a>Nasıl çalışır?

Neredeyse yinelenen algılama çalıştırıldığında, sistem her belgeyi metinle ayrıştırıyor. Ardından, benzerliklerinin ayarlanan eşikten büyük olup olmadığını belirlemek için her belgeyi birbiriyle karşılaştırır. Bu durumda belgeler birlikte gruplandırılır. Tüm belgeler karşılaştırılıp gruplandırıldıktan sonra, her gruptan bir belge "özet" olarak işaretlenir; belgelerinizi gözden geçirirken, önce bir özeti gözden geçirebilir ve aynı yakın yinelenen kümedeki diğer belgeleri gözden geçirerek özet ile gözden geçirmedeki belge arasındaki farka odaklanabilirsiniz.
