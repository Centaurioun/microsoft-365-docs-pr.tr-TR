---
title: Hassas bilgi türü sınırları
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MOE150
- MET150
description: Örnek sayısı ve diğer hassas bilgi türü sınırları hakkında bilgi edinin
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a09a2b81d04e706996cdee1fcd2a19a56f6aa990
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68117561"
---
# <a name="sensitive-information-type-limits"></a>Hassas bilgi türü sınırları

Bu sınırlar, 100'e kadar destekleyen hassas bilgi türleriyle tam olarak eşleşen veriler dışında tüm hassas bilgi türleri (SIT) için geçerlidir.

> [!NOTE]
> 100'e kadar tam veri eşleşmesi (EDM) değerlendirmesini destekliyoruz. EDM SID'lerini kullanan ilkeler **, en az** veya **en yüksek** örnek sayısı değeri 100'den büyük olacak şekilde yazılmamalıdır.

Bu sınırlar, SID kullanan tüm Microsoft Purview ilkeleri için geçerlidir.

Yüksek performans ve daha düşük gecikme süresi sağlamak için özel SID yapılandırmalarında sınırlamalar vardır.

|Sınırı|Değer|
|---|---|
|Uyumluluk merkezi aracılığıyla oluşturulan en fazla özel SID sayısı| 500 |
|normal ifadenin maksimum uzunluğu| 1024 karakter|
|anahtar sözcük listesindeki belirli bir terim için maksimum uzunluk| 50 karakter|
|anahtar sözcük listesindeki en fazla terim sayısı| 2048|
|hassas bilgi türü başına en fazla benzersiz kayıt defteri sayısı| 20|
|anahtar sözcük sözlüğünün en büyük boyutu (sıkıştırma sonrası)| 1 MB (~1.000.000 karakter)|
|kiracıdaki anahtar sözcük sözlüğü tabanlı SID sayısı üst sınırı|50 |

> [!NOTE]
> İşletmenin 500'den fazla özel SID oluşturması gerekiyorsa lütfen bir destek bileti oluşturun.

### <a name="instance-count-supported-values-for-sit"></a>SIT için örnek sayısı desteklenen değerler

SIT örneği sayısı sınırı, şu çözümlerde SID'ler kullanıldığında geçerlidir:

- Microsoft Purview Veri Kaybı Önleme ilkeleri
- Microsoft Purview Bilgi Koruması ilkeleri
- Microsoft Purview Veri Yaşam Döngüsü Yönetimi
- İletişim Uyumluluğu
- Microsoft Purview Kayıt Yönetimi
- Bulut Uygulamaları için Microsoft Defender
- Microsoft Priva

Taranan bir öğenin kural ölçütlerini karşılaması için, tek bir öğedeki bir SIT'in benzersiz örneklerinin sayısı min ve max değerleri arasında olmalıdır. Buna **Örnek sayısı** adı verilir.

- **En küçük** alan: Eşleşmeyi tetikleyebilmek için bir öğede bulunması gereken bir SIT'in benzersiz örneklerinin alt sınırı (minimum sayı). Min alanı şu değerleri destekler:
  - 1 - 500
- **Maksimum** alan: Bir öğede bulunabilen ve yine de eşleşme tetikleyen benzersiz sit örneği sayısı üst sınırı. Max alanı şu değerleri destekler:
  - 1 ile 500 arası - Bir öğedeki SIT örneğinin sayısı için 500 veya daha az olan belirli bir üst sınır ayarlamak istediğinizde bunu kullanın.
  - Herhangi Biri - Taranan bir öğede bir SIT'in tanımlanmamış sayıda benzersiz örneği bulunduğunda ve benzersiz örnek sayısı minimum benzersiz örnek değerini karşıladığında veya aştığında benzersiz örnek sayısı ölçütlerinin karşılanmasını istediğinizde kullanın `Any` . Başka bir deyişle, min değeri karşılandığı sürece benzersiz örnek sayısı ölçütleri karşılanır.

Örneğin, bir SIT'in en az 500 benzersiz örneği tek bir öğede bulunduğunda kuralın eşleşme tetiklemesini istiyorsanız **, en küçük** değeri olarak `500` , **maksimum** değeri `Any`olarak ayarlayın.



