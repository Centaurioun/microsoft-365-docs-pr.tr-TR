---
title: Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme
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
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Tam veri eşleşmesi tabanlı hassas bilgi türleri hakkında bilgi edinin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eced8c769f7c1b8f35fd0eb4524d3518ea891881
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360073"
---
# <a name="learn-about-exact-data-match-based-sensitive-information-types"></a>Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme

[Hassas bilgi türleri](sensitive-information-type-learn-about.md) , hassas öğelerin yanlışlıkla veya uygunsuz bir şekilde paylaşılmasını önleyebilmeniz için tanımlanmasına yardımcı olmak için kullanılır. Ayrıca, eBulma'da ilgili verilerin bulunmasına yardımcı olmak ve belirli bilgi türlerine idare eylemleri uygulamak için de kullanılır. Aşağıdakilere göre özel bir hassas bilgi türü (SIT) tanımlarsınız:

- Desen
- *çalışan*, *sosyal güvenlik numarası* veya *kimlik* gibi anahtar sözcük kanıtı
- belirli bir desendeki kanıta karakter yakınlığı
- güvenilirlik düzeyleri

Peki ya genel desenleri temel alan eşleşmeler bulmak yerine tam veya neredeyse tam veri değerlerini kullanan özel bir hassas bilgi türü (SIT) istiyorsanız? Tam Veri Eşleşmesi (EDM) tabanlı sınıflandırma ile, aşağıdakileri yapmak için tasarlanmış özel bir hassas bilgi türü oluşturabilirsiniz:

- dinamik olmak ve kolayca yenilenmek
- daha az hatalı pozitif sonuç
- yapılandırılmış hassas verilerle çalışma
- Hassas bilgileri daha güvenli bir şekilde işleme, Microsoft dahil olmak üzere kimseyle paylaşmama
- çeşitli Microsoft bulut hizmetleriyle kullanılmak

![EDM tabanlı sınıflandırma.](../media/EDMClassification.png)

EDM tabanlı sınıflandırma, hassas bilgi veritabanındaki tam değerlere başvuran özel hassas bilgi türleri oluşturmanıza olanak tanır. Veritabanı günlük olarak yenilenebilir ve 100 milyon satıra kadar veri içerebilir. Çalışanlar, hastalar veya müşteriler gelip gittikçe ve kayıtlar değiştikçe, özel hassas bilgi türleriniz güncel ve geçerli kalır. Ayrıca, [Microsoft Purview veri kaybı önleme ilkeleri](dlp-learn-about-dlp.md) veya [Microsoft Cloud App Security dosya](/cloud-app-security/data-protection-policies) ilkeleri gibi ilkelerle EDM tabanlı sınıflandırmayı kullanabilirsiniz.

> [!NOTE]
> Microsoft Purview Bilgi Koruması için çift bayt karakter kümesi dillerini destekler:
>
> - Çince (basitleştirilmiş)
> - Çince (geleneksel)
> - Korean
> - Japanese
>
> Bu destek, hassas bilgi türleri için kullanılabilir. Daha fazla bilgi için bkz. [Çift bayt karakter kümeleri için bilgi koruma desteği sürüm notları (önizleme).](mip-dbcs-relnotes.md)

## <a name="whats-different-in-an-edm-sit"></a>EDM SIT'teki farklar

EDM SID'leri ile çalışırken, kendilerine özgü birkaç kavramı anlamanız yararlı olur.  

### <a name="schema"></a>Şema

Şema, aşağıdakileri tanımlayan bir xml dosyasıdır:

- Daha sonra *DataStore* olarak adlandırılan şemanın adı. 
- Hassas bilgi kaynağı tablonuzun içerdiği alan adları. Şema alanı adının hassas bilgi kaynağı tablo sütun adıyla 1:1 eşlemesi vardır.
- Hangi alanlar aranabilir.
- Sınırlayıcıları ve aranan değerlerdeki büyük/küçük harflerini yoksayma gibi *yapılandırılabilir eşleşme* olarak adlandırılan parametreleri değiştiren tüm aramalar.

### <a name="sensitive-information-source-table"></a>Hassas bilgi kaynağı tablosu

Hassas bilgi kaynağı tablosu, EDM SIT'in arayacağı değerleri içerir. Sütunlardan ve satırlardan oluşur. Sütun üst bilgileri alan adlarıdır, satırlar öğenin bir örneğidir ve her hücre o alanın öğe örneğine ait değerleri içerir.

Hassas bilgi kaynağı tablosunun basit bir örneği aşağıda verilmiştır.

|Ad|Soyadı|Doğum tarihi|
|---|---|---|
|Yeşaya|Langer| 05-05-1960|
|Ana|Bowman|11-24-1971|
|Oscar|Ward|02-12-1998|

### <a name="rule-package"></a>Kural paketi

Her SIT'in bir kural paketi vardır. Kural paketini bir EDM SIT'te kullanarak aşağıdakileri tanımlarsınız:

- Eşleşmeler, tam aramada kullanılacak birincil öğe olacak alanı belirtir. Sağlama toplamı doğrulaması, anahtar sözcük listesi, anahtar sözcük sözlüğü veya işlev içeren veya olmayan normal bir ifade olabilir.
- EDM aramasını tetikleyen hassas bilgi türü eşleşmesini belirten sınıflandırma.
- Bulunduğunda eşleşmenin güvenilirliğini artırmaya yardımcı olan kanıt sağlayan öğeler olan destekleyici öğe. Örneğin, "SSN" anahtar sözcüğünü gerçek bir sosyal güvenlik numarasına yakın bir yerde ortaya çıkması. Destekleyici öğe sağlama toplamı doğrulaması, anahtar sözcük listesi veya anahtar sözcük sözlüğü içeren veya içermeyen normal bir ifade olabilir.
- Güvenilirlik düzeyleri (yüksek, orta, düşük), birincil öğeye ek olarak ne kadar destekleyici kanıt algılandığını yansıtır. Bir öğe ne kadar destekleyici kanıt içeriyorsa, eşleşen bir öğenin aradığınız hassas bilgileri içerdiğine o kadar fazla güvenir. Güvenilirlik düzeyleri hakkında daha fazla [bilgi için bkz. Hassas bilgi türünün temel bölümleri](sensitive-information-type-learn-about.md#fundamental-parts-of-a-sensitive-information-type) .
- Yakınlık - Birincil ve destekleyici öğe arasındaki karakter sayısı.

### <a name="you-supply-your-own-schema-and-data"></a>Kendi şemanızı ve verilerinizi sağlayın

[Microsoft Purview önceden tanımlanmış birçok SITS ile birlikte gelir](sensitive-information-type-entity-definitions.md). Bu SITS şemalar, regex desenleri, anahtar sözcükler ve güvenilirlik düzeyleriyle birlikte gelir. Ancak, EDM SID'leri ile şemanın yanı sıra hassas öğeleri tanımlayan birincil ve ikincil alanları tanımlamak sizin sorumluluğundadır. Şema ve birincil ve ikincil veri değerleri son derece hassas olduğundan, bunları rastgele oluşturulan veya kendi kendine sağlanan [bir tuz](https://en.wikipedia.org/wiki/Salt_(cryptography)#:~:text=The%20salt%20value%20is%20generated%20at%20random%20and,the%20salt%20value%20and%20hashed%20value%20are%20stored.) değeri içeren bir [karma](/dotnet/standard/security/ensuring-data-integrity-with-hash-codes) işlevi aracılığıyla şifrelersiniz. Hizmete yalnızca karma değerler yüklenir, bu nedenle hassas verileriniz hiçbir zaman açık olmaz.

### <a name="primary-and-secondary-support-elements"></a>Birincil ve ikincil destek öğeleri

EDM SIT oluşturduğunuzda, kural paketinde *bir birincil öğe* alanı tanımlarsınız. Tüm içerik birincil öğe için aranacak. EDM, birincil öğenin mevcut bir SIT aracılığıyla bulunabilir olmasını gerektirir. 

> [!NOTE]
> Kullanılabilir SID'lerin tam listesi için [bkz. Hassas bilgi türü varlık tanımları](sensitive-information-type-entity-definitions.md) .  

EDM SIT'inizin algılamasını istediğiniz hassas bilgileri algılayan önceden tanımlanmış bir SIT bulmanız gerekir. Örneğin, EDM SIT şemanızda birincil öğe olarak ABD sosyal güvenlik numarası varsa, EDM şemanızı oluşturduğunuzda, bunu [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md) SIT ile ilişkilendirmiş olursunuz. Birincil öğelerin algılanması için tanımlı bir deseni izlemesi gerekir.

Taranan bir öğede birincil öğe bulunduğunda, EDM *ikincil* veya destekleyici öğeleri arar. İkincil öğelerin bir deseni izlemesi gerekmez, ancak birincil öğeye belirli bir yakınlık içinde olması gerekir.

## <a name="how-matching-works"></a>Eşleştirme nasıl çalışır?

EDM, taranan içerikteki değerlerin tabloda mevcut olup olmadığını görmek için belgelerinizdeki dizeleri ve e-postaları hassas bilgi kaynağı tablosundaki değerlerle karşılaştırarak çalışır. Karşılaştırma, tek yönlü şifreleme karmaları karşılaştırılarak yapılır.


> [!TIP]
> Daha iyi algılama için DLP kurallarında hem EDM SID'lerini hem de temel aldıkları önceden tanımlanmış SID'leri birlikte kullanabilirsiniz. EDM SIT'i daha yüksek güvenilirlik düzeyleriyle ve önceden tanımlanmış SIT'i daha düşük güvenilirlik düzeyleriyle kullanın. Örneğin, yüksek güvenle katı gereksinimlere sahip sosyal güvenlik numarası ve diğer destekleyici verileri arayabilen bir EDM SIT kullanın. Yüksek güvenin kullanılması, az sayıda örnek algılandığında bir DLP eşleşmesi oluşturur. Ardından, daha fazla sayıda oluşum algılandığında DLP eşleşmesini tetikleyecek daha düşük güvenilirlik düzeyleriyle ABD Sosyal Güvenlik Numarası gibi önceden tanımlanmış bir SIT kullanın.  

## <a name="services-that-edm-supports"></a>EDM'nin desteklediği hizmetler


|Hizmet  |Konum  |
|---------|---------|
| Microsoft Purview Veri Kaybı Önleme    | - SharePoint online </br>- OneDrive İş </br>- Teams Sohbeti </br>- Exchange Online </br>- Cihazlar       |
|Bulut Uygulamaları için Microsoft Defender     | - SharePoint Online </br>- OneDrive İş        |
|Otomatik etiketleme (hizmet tarafı)     |- SharePoint online </br>- OneDrive İş </br>- Exchange Online         |
|Otomatik etiketleme (istemci tarafı)     |- Word </br>- Excel </br>- PowerPoint </br>- Exchange masaüstü istemcileri         |
|Müşteri Tarafından Yönetilen Anahtar     |- SharePoint online </br>- OneDrive İş </br>- Teams Sohbeti </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange masaüstü istemcileri </br>- Cihazlar         |
|Ediscovery     |- SharePoint online </br>- OneDrive İş </br>- Teams Sohbeti </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange masaüstü istemcileri  |
|Insider Risk Management     |- SharePoint online </br>- OneDrive İş </br>- Teams Sohbeti </br>- Exchange Online </br>- Word </br>- Excel </br>- PowerPoint </br>- Exchange masaüstü istemcileri      |

## <a name="see-also"></a>Ayrıca bkz.

- [Tam veri eşleşmesine dayalı hassas bilgi türlerini kullanmaya başlama](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
