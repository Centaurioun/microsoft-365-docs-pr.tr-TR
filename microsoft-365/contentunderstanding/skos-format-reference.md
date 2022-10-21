---
title: SharePoint taksonomisi için SKOS biçim başvurusu
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: high
description: SharePoint taksonomisi için SKOS biçim başvurusu hakkında bilgi edinin.
ms.openlocfilehash: 305d3098a4481211623368e443294c387c879ef4
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660719"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SharePoint taksonomisi için SKOS biçim başvurusu

Bu makale [, SharePoint taksonomisini](/dotnet/api/microsoft.sharepoint.taxonomy) temsil etmek için kullanılan RDF sözcük dağarcığını içerir ve [SKOS'a](https://www.w3.org/TR/skos-primer/) dayanır. Bu RDF söz diziminin seri hale getirilmesi için RDF [TURTLE](https://www.w3.org/TR/turtle/) kullanın.

Aşağıdaki tabloda[, SharePoint taksonomi](/dotnet/api/microsoft.sharepoint.taxonomy) sözlüğü için [SKOS](https://www.w3.org/TR/skos-primer/) eşdeğerleri gösterilmektedir. SharePoint, SharePoint taksonomisi eşdeğeri olmayan [SKOS](https://www.w3.org/TR/skos-primer/) değerlerini desteklemez.

|SharePoint taksonomisi|SKOS eşdeğeri|
|:-----------------|:--------------|
|sharepoint-taksonomisi: Terim|skos: Kavram|
|sharepoint-taksonomisi: TermSet|skos: ConceptScheme|
|sharepoint-taksonomisi: inTermSet|skos: inScheme|
|sharepoint-taksonomisi: hasTopLevelTerm|skos: hasTopConcept|
|sharepoint-taksonomisi: topLevelTermOf|skos: topConceptOf|
|sharepoint-taksonomisi: defaultLabel|skos: prefLabel|
|sharepoint-taxonomy: termSetName|skos: prefLabel|
|sharepoint-taksonomisi: propertyName|skos: prefLabel|
|sharepoint-taksonomisi: otherLabel|skos: altLabel|
|sharepoint-taksonomisi: açıklama|skos: tanım|
|sharepoint-taksonomisi: üst|skos: daha geniş|
|sharepoint-taksonomisi: alt öğe|skos: daha dar|

Aşağıdaki tabloda, [OWL'den](https://www.w3.org/TR/owl2-primer/) türetilen SharePoint taksonomi sözlüğü varlıkları gösterilmektedir.

|SharePoint taksonomi sözlüğü|OWL'dan türetilmiş|
|:-----------------------------|:----------------------|
|sharepoint-taksonomisi: isAvailableForTagging|baykuş: datatypeproperty|
|sharepoint-taxonomy: SharedCustomPropertyForTerm|baykuş: ObjectProperty|
|sharepoint-taxonomy: LocalCustomPropertyForTerm|baykuş: ObjectProperty|
|sharepoint-taxonomy: CustomPropertyForTermSet|baykuş: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint taksonomi sözlüğü

Taksonomi resmi bir sınıflandırma sistemidir. Taksonomi, bir şeyi açıklayan sözcükleri, etiketleri ve terimleri gruplandırıp grupları bir hiyerarşide düzenler.

**sharepoint-taksonomisi:Terim**

Yönetilen meta veri hiyerarşisindeki bir Terimi veya Anahtar Sözcüğü temsil eder.

[Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term), SharePoint TermStore'nun atomik [birimidir](/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Her [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term), bir [TermGroup'a](/dotnet/api/microsoft.sharepoint.taxonomy.group) ait bir [TermSet'e](/dotnet/api/microsoft.sharepoint.taxonomy.termset) aittir.

[Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) tanımlama söz dizimi aşağıdaki gibidir:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.term) içinde zorunlu olarak bir [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.termset) var. DefaultLabel, görsel gösterimde göründüğü gibi [Terimin](/dotnet/api/microsoft.sharepoint.taxonomy.term) adıdır. [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) tanımlamak için gereken alanlar şunlardır:

- sharepoint-taksonomisi: defaultLabel
- sharepoint-taksonomisi: inTermSet

[Terim şu](/dotnet/api/microsoft.sharepoint.taxonomy.term) şekilde olabilir:

- Hem [Koşulların](/dotnet/api/microsoft.sharepoint.taxonomy.term) aynı [TermSet'e](/dotnet/api/microsoft.sharepoint.taxonomy.termset) ait olduğu sağlanan başka bir [Terimle](/dotnet/api/microsoft.sharepoint.taxonomy.term) hiyerarşik olarak ilgili olun.
- Birden çok alt [Terime](/dotnet/api/microsoft.sharepoint.taxonomy.term) sahip olur, ancak yalnızca tek bir üst [Terime sahip olur](/dotnet/api/microsoft.sharepoint.taxonomy.term).
- TopLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.term) ise, tanımlanmış bir üst [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.termset) yoktur.
- [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) çalışma dili başına bir varsayılanLabel kullanın.
- Üst [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) içermiyorsa veya topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) ise mevcut değildir.
- Aynı hiyerarşik düzeyde yalnızca benzersiz bir defaultLabel'e sahip olur.

**sharepoint-taksonomisi:TermSet**

"TermSet" olarak bilinen bir hiyerarşik veya düz Terim nesneleri kümesini temsil eder.

Adından da anlaşılacağı gibi, TermSet bir [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) kümesidir. [TermStore'daki](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) bir [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) bir [TermSet'e](/dotnet/api/microsoft.sharepoint.taxonomy.termset) ait olmalıdır. Hiçbir [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) bağımsız olarak mevcut olamaz.

[Terim Kümesi](/dotnet/api/microsoft.sharepoint.taxonomy.termset) tanımlamak için söz dizimi:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSet'ler](/dotnet/api/microsoft.sharepoint.taxonomy.termset)[, TermGroup'larda](/dotnet/api/microsoft.sharepoint.taxonomy.group) mantıksal olarak birlikte gruplandırılır. [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) tanımlamak için gereken alan:

- sharepoint-taxonomy: termSetName

Sağlanan TermSetName terimi [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) içinde benzersiz değilse, SharePoint termSetName'lerin benzersizliğini korumak için adın sonuna bir sayı ekler.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint bu özelliği kullanarak [TermSet'teki](/dotnet/api/microsoft.sharepoint.taxonomy.termset) en üstteki [Terim'i](/dotnet/api/microsoft.sharepoint.taxonomy.term) eşler ve bu da giriş noktası olarak Terim [Kümesindeki](/dotnet/api/microsoft.sharepoint.taxonomy.termset) [Terimler](/dotnet/api/microsoft.sharepoint.taxonomy.term) hiyerarşisini kullanır. Bu, sharepoint-taksonomisi ile ters bir ilişkidir: topLevelTermOf.

Bunu tanımlamak için söz dizimi şöyledir:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> Üst [Terimin](/dotnet/api/microsoft.sharepoint.taxonomy.term) en üst düzey [Terimini](/dotnet/api/microsoft.sharepoint.taxonomy.term) tanımlayamazsınız.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taksonomisi: topLevelTermOf, sharepoint-taksonomisinin tersidir: hasTopLevelTerm

Bunu tanımlamak için söz dizimi şöyledir:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Bir [Terimi](/dotnet/api/microsoft.sharepoint.taxonomy.term) [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) ile eşlemek için bunu kullanın. [Terim yalnızca](/dotnet/api/microsoft.sharepoint.taxonomy.term) tek bir [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) içinde bulunabilir. SharePoint [bir terim tanımlarken](#sharepoint-taxonomy-vocabulary) bu özelliği gerektirir.

## <a name="required-labels"></a>Gerekli etiketler

Kuruluşunuz, yönetilen meta verileri kullanmaya başlamadan önce dikkatli bir planlama yapmak isteyebilir. Yapmanız gereken planlama miktarı, taksonominizin ne kadar resmi olduğuna bağlıdır. Ayrıca meta verilere ne kadar denetim uygulamak istediğinize de bağlıdır. Hiyerarşinin her düzeyinde, Terim veya Terim Kümesi için gerekli etiketleri yapılandırmanız gerekir.

Bir Terim varsayılan dilde bir veya daha fazla etikete ve varsayılan olmayan dilde sıfır veya daha fazla etikete sahip olabilir. Terimin bir dilde etiketleri varsa, etiketlerden biri varsayılan etiket olmalıdır.

**sharepoint-taxonomy:defaultLabel**

Terim için [gerekli bir parametre](/dotnet/api/microsoft.sharepoint.taxonomy.term) olan Terim için bu varsayılan sözcük etiketini [kullanın.](/dotnet/api/microsoft.sharepoint.taxonomy.term) [Terimi](/dotnet/api/microsoft.sharepoint.taxonomy.term) görsel olarak temsil etmek için kullanın.

defaultLabel tanımlamak için söz dizimi:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

defaultLabel, dize ve dil etiketi olmak üzere iki bölümden oluşur. Dil [, TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) çalışma dillerinden biri olmalıdır. defaultLabel aynı [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) içindeki tüm [Koşullar](/dotnet/api/microsoft.sharepoint.taxonomy.term) için aynı hiyerarşik düzeyde benzersiz olmalıdır.

**sharepoint-taxonomy:termSetName**

Geçerli TermSet nesnesinin adını alır ve ayarlar.

Bu, [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) çalışma dilindeki bir [TermSet'in](/dotnet/api/microsoft.sharepoint.taxonomy.termset) sözcük temelli etiketidir. Bu, bir [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) için gerekli bir parametredir. [TermSet'i](/dotnet/api/microsoft.sharepoint.taxonomy.termset) görsel olarak temsil etmek için kullanın.

TerimSetName tanımlamak için söz dizimi:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Geçerli TermSet nesnesinin özellik adını alır ve ayarlar.

Bu, Bir [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) çalışma dilinde sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm ve sharepoint-taxonomy:CustomPropertyForTermSet sözcük temelli etiketidir.

sharepoint-taxonomy: propertyName, CustomProperty anahtarının anahtarı olarak değerlendirilir.

bir propetyName tanımlamak için söz dizimi:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>İsteğe bağlı etiketler

Taksonominize isteğe bağlı etiketler de ekleyebilirsiniz.

**sharepoint-taksonomisi:otherLabel**

Bu terim için alternatif sözcük [etiketidir](/dotnet/api/microsoft.sharepoint.taxonomy.term).

otherLabel tanımlamak için söz dizimi:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Anlamsal ilişkiler

Taksonomilerin hiyerarşik ve bazen basit bir "ilişkili terim" ilişkilendirici ilişkisi vardır, ancak bazılarının "semantik ilişkileri" veya özel olarak oluşturulmuş ilişkileri vardır.

**sharepoint-taxonomy:parent**

Bu hiyerarşik olarak bir Terimi başka bir [Terimle](/dotnet/api/microsoft.sharepoint.taxonomy.term) ilişkilendirmektedir.[](/dotnet/api/microsoft.sharepoint.taxonomy.term) [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term), bir [TermSet'in](/dotnet/api/microsoft.sharepoint.taxonomy.termset) en üst düzey [Terimi](/dotnet/api/microsoft.sharepoint.taxonomy.term) olabilir, ancak değilse üst [Terime](/dotnet/api/microsoft.sharepoint.taxonomy.term) sahip olması gerekir.

Üst öğe tanımlamak için söz dizimi:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Bu, TermA'nın üst öğe, TermA'nın ise alt öğe olduğu anlamına gelir.

**sharepoint-taxonomy:child**

nesnesi bir veya daha fazla alt TermSet örneği içerir ve bunlara TermSets özelliği aracılığıyla erişilebilir. Bu sınıf ayrıca yeni alt TermSet nesneleri oluşturmak için yöntemler sağlar. Alt Terim ve TermSet örneklerini düzenleme izinleri grupta belirtilir.

Bu hiyerarşik olarak bir Terimi başka bir [Terimle](/dotnet/api/microsoft.sharepoint.taxonomy.term) ilişkilendirmektedir.[](/dotnet/api/microsoft.sharepoint.taxonomy.term)

Alt öğe tanımlamak için söz dizimi:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Bu, TermA'nın üst öğe, TermA'nın ise alt öğe olduğu anlamına gelir.

## <a name="documentation-notes"></a>Belge notları

Bu bölümde, Microsoft.SharePoint.Taxonomy Ad Alanında ayrıntılı olarak açıklanan taksonomi ele alınmaktadır.

**sharepoint-taxonomy:description**

Bu, herhangi bir [SharePoint taksonomi sözlüğü varlığının](/dotnet/api/microsoft.sharepoint.taxonomy) ayrıntılı bir açıklamasıdır.

Açıklama eklemek için söz dizimi şu şekildedir:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Özel özellikler

Geçerli Terim nesnesi için özel özellik nesnelerinin koleksiyonunu salt okunur sözlükten alır.

Özel Özellikler, [Terim veya TermSet'in](/dotnet/api/microsoft.sharepoint.taxonomy.term) açıklamasını ilerletmek için Terim veya [Terim Kümesi](/dotnet/api/microsoft.sharepoint.taxonomy.termset) için [tanımlanabilen](/dotnet/api/microsoft.sharepoint.taxonomy.term) anahtar-değer çiftleridir[.](/dotnet/api/microsoft.sharepoint.taxonomy.termset) SharePoint, propertyName yardımıyla özel özelliğin anahtarını belirtir.

**sharepoint-taxonomy:CustomPropertyForTermSet**

Bunu tanımlamak için söz dizimi şöyledir:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

[Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) için özel özelliğin [Terimle](/dotnet/api/microsoft.sharepoint.taxonomy.term) birlikte taşınması gerekiyorsa, [Terimi](/dotnet/api/microsoft.sharepoint.taxonomy.term) başka bir yerde yeniden kullandığınızda, bunu SharedCustomPropertyForTerm altında tanımlamanız gerekir.

Bunu tanımlamak için söz dizimi şöyledir:

```SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

[Terimin](/dotnet/api/microsoft.sharepoint.taxonomy.term) özel özelliğinin [Terimle](/dotnet/api/microsoft.sharepoint.taxonomy.term) birlikte taşınması gerekmiyorsa, [Terimi](/dotnet/api/microsoft.sharepoint.taxonomy.term) başka bir yerde yeniden kullandığınızda, bunu LocalCustomPropertyForTerm altında tanımlamanız gerekir.

Bunu tanımlamak için söz dizimi şöyledir:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Veri özellikleri

Hiyerarşinin her düzeyinde, Bir Terim veya Terim Kümesi için belirli veri özelliklerini yapılandırabilirsiniz.

**sharepoint-taxonomy:isAvailableForTagging**

SharePoint Listelerinde ve Kitaplıklarında bir [Terim](/dotnet/api/microsoft.sharepoint.taxonomy.term) veya [Terim Kümesi](/dotnet/api/microsoft.sharepoint.taxonomy.termset) olup olmadığını belirtmek için bunu kullanın.

Bunun söz dizimi şöyledir:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Etki alanı ve aralık

Aşağıdaki tabloda SharePoint taksonomi sözlüğü etki alanı ve aralığı açıklanmaktadır.

|Koşul/fiil|Anlamı|Etki alanı|Aralığı|
|:--------------|:------|:-----|:----|
inTermSet|Terim kümesinde|Terim|Terim Kümesi|
inTermGroup|Terim grubunda|TermSet|TermGroup|
topLevelTermOf|En Üst Düzey Terimi|Terim|TermSet|
hasTopLevelTerm|En üst düzey terime sahiptir|Terim Kümesi|Terim|
termSetName|Terim kümesinin Adı var|Terim|Düz değişmez değer|
defaultLabel|Terim varsayılan etikete sahiptir|Terim|Düz değişmez değer|
otherLabel|Terim başka bir etikete sahip|Terim|Düz değişmez değer|
Propertyname|Özellik Etiketi Var|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boole, Dize, Tamsayı, Ondalık, Çift|
|Açıklama|Açıklaması Var|Tümü|Düz değişmez değer|
|Üst|Üst öğeye sahip|Terim|Terim|
|Çocuk|Alt Öğesi Var|Terim|Terim|
|isAvailableForTagging|Etiketleme için kullanılabilir|Terim, Terim Kümesi|Boole|
|SharedCustomPropertyForTerm|Paylaşılan özel özelliği var|Terim|Boole, dize, Tamsayı, Ondalık, Çift|
|LocalCustomPropertyForTerm|Yerel özel özelliğe sahiptir|Terim|Boole, Dize, Tamsayı, Ondalık, Çift|
|CustomPropertyForTermSet|Özel Özelliği Var|TermSet|Boole, Dize, Tamsayı, Ondalık, Çift|

[SharePoint taksonominin](/dotnet/api/microsoft.sharepoint.taxonomy) izin vermediği [geçerli SKOS](https://www.w3.org/TR/skos-primer/) senaryoları:

- Hiyerarşik yedeklilik - [Bir SKOS](https://www.w3.org/TR/skos-primer/) kavramı aynı anda birkaç daha geniş kavramlara eklenebilir, ancak bir sharepoint-taksonomisi:Terimin yalnızca bir sharepoint-taksonomisi:üst öğesi olabilir, bu nedenle Terimlerin döngüsel bağımlılığına da izin verilmez.
- SharePoint taksonomisinde yalnız bırakılmış terimlere izin verilmez. Her sharepoint-taksonomisi: Terimin bir sharepoint-taksonomisi olmalıdır: üst veya sharepoint-taksonomisi olmalıdır: topLevelTermOf a TermSet.
- SharePoint taksonomisi ilişkilendirici ilişkileri desteklemez.
- SharePoint taksonomisi yalnızca iki tür Hiyerarşik ilişkiye izin verir: sharepoint-taksonomisi: üst ve sharepoint-Taksonomi: alt.
- [SKOS'un](https://www.w3.org/TR/skos-primer/) aksine, SharePoint taksonomi sözlüğündeki hiyerarşik ilişki yalnızca aynı Terim Kümesi içindeki Terimler ile oluşturulabilir.

## <a name="see-also"></a>Ayrıca bkz.

[SKOS tabanlı biçim kullanarak terim kümesini içeri aktarma](import-term-set-skos.md)
