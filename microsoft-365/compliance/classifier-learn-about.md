---
title: Eğitilebilir sınıflandırıcılar hakkında daha fazla bilgi edinme
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- highpri
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Eğitilebilir sınıflandırıcılar, etiketleme veya ilke uygulamasına bakılması için pozitif ve negatif örnekler vererek çeşitli içerik türlerini tanıyabilir.
ms.openlocfilehash: 37dc3e1f57d4572e95eb78c9794a120f9c99d19c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630260"
---
# <a name="learn-about-trainable-classifiers"></a>Eğitilebilir sınıflandırıcılar hakkında daha fazla bilgi edinme

İçeriğin korunabilmesi ve düzgün işlenebilmesi için kategorilere ayırmak ve etiketlemek, bilgi koruma uzmanlık alanı için başlangıç noktasıdır. Microsoft Purview' un içeriği sınıflandırmak için üç yolu vardır.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="manually"></a>Elle

El ile kategorilere ayırma, insan yargısı ve eylemi gerektirir. Kullanıcılar ve yöneticiler, içerikle karşılaştıklarında içeriği kategorilere ayırır. Önceden var olan etiketleri ve hassas bilgi türlerini veya özel oluşturulanları kullanabilirsiniz.  Daha sonra içeriği koruyabilir ve eğilimini yönetebilirsiniz.

## <a name="automated-pattern-matching"></a>Otomatik desen eşleştirme

Bu kategorilere ayırma mekanizmaları, içeriği şu şekilde bulmayı içerir:

- Anahtar sözcükler veya meta veri değerleri (anahtar sözcük sorgu dili).
- Sosyal güvenlik, kredi kartı veya banka hesabı numaraları ( [Hassas bilgi türü varlık tanımları)](sensitive-information-type-entity-definitions.md) gibi hassas bilgilerin önceden tanımlanmış desenlerini kullanma.
- Şablondaki bir çeşitleme olduğundan [öğeyi tanıma (belge parmağıyla yazdırma)](document-fingerprinting.md).
- Tam dizelerin varlığının [kullanılması tam veri eşleşmesi](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types).

Daha sonra duyarlılık ve bekletme etiketleri otomatik olarak uygulanarak içeriğin [Microsoft Purview Veri Kaybı Önleme hakkında bilgi edinin](dlp-learn-about-dlp.md) ve [bekletme etiketleri için ilkeleri otomatik olarak uygulama](apply-retention-labels-automatically.md) başlığı altında kullanılabilir hale getirilebilir.

## <a name="classifiers"></a>Sınıflandırıcı

Bu kategorilere ayırma yöntemi, el ile veya otomatik desen eşleştirme yöntemleriyle kolayca tanımlanmayan içeriğe çok uygundur. Bu kategorilere ayırma yöntemi, öğedeki öğeler (desen eşleştirme) tarafından değil, öğenin ne olduğuna bağlı olarak bir öğeyi tanımlamak için sınıflandırıcı kullanmakla daha fazla ilgili olur. Sınıflandırıcı, girintilendirmek istediğiniz içeriğin yüzlerce örneğine bakarak bir içerik türünü tanımlamayı öğrenir.

> [!NOTE]
> Önizlemede - Filtreler panelinde Eğitilebilir Sınıflandırıcılar'ı genişleterek içerik gezgininde **eğitilebilir sınıflandırıcıları** görüntüleyebilirsiniz. Eğitilebilir sınıflandırıcılar, hiçbir etiketleme gerektirmeden SharePoint, Teams ve OneDrive'da bulunan olay sayısını otomatik olarak görüntüler.
> Bu özelliği kullanmak istemiyorsanız, Microsoft Desteği ile bir istekte bulunmanız gerekir. Bu, İçerik Gezgini'ndeki hiçbir etiketleme ilkesinde kullanılmayan hassas verilerinizin görüntülenmesini devre dışı bırakır. Verilerinizi taramayı da devre dışı bırakabilirsiniz. Tarama kapalıysa, bu sınıflandırıcılarla duyarlılık etiketleme ve DLP ilkeleri çalışmaz

### <a name="where-you-can-use-classifiers"></a>Sınıflandırıcıları kullanabileceğiniz yerler

Sınıflandırıcılar şunlar için bir koşul olarak kullanılabilir:

- [Duyarlılık etiketleriyle Office otomatik etiketlemesi](apply-sensitivity-label-automatically.md)
- [Bir koşula göre bekletme etiketi ilkesini otomatik uygulama](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)
- [İletişim uyumluluğu](communication-compliance.md)
- Duyarlılık etiketleri sınıflandırıcıları koşul olarak kullanabilir. Bkz. [İçeriğe otomatik olarak duyarlılık etiketi uygulama](apply-sensitivity-label-automatically.md).
- [Veri kaybı önleme](dlp-learn-about-dlp.md)

> [!IMPORTANT]
> Sınıflandırıcılar yalnızca şifrelenmemiş öğelerle çalışır.

## <a name="types-of-classifiers"></a>Sınıflandırıcı türleri

- **önceden eğitilmiş sınıflandırıcılar** - Microsoft, eğitmeden kullanmaya başlayabileceğiniz birden çok sınıflandırıcı oluşturmuş ve önceden eğitmiştir. Bu sınıflandırıcılar, durumunda `Ready to use`görüntülenir.
- **özel eğitilebilir sınıflandırıcılar** - Önceden eğitilen sınıflandırıcıların kapsadığını aşan içerik tanımlama ve kategorilere ayırma gereksinimleriniz varsa, kendi sınıflandırıcılarınızı oluşturabilir ve eğitebilirsiniz.

Önceden [eğitilmiş tüm sınıflandırıcıların](classifier-tc-definitions.md#trainable-classifiers-definitions) tam listesi için eğitilebilir sınıflandırıcı tanımlarına bakın.

### <a name="custom-classifiers"></a>Özel sınıflandırıcılar

Önceden eğitilmiş sınıflandırıcılar gereksinimlerinizi karşılamadığında kendi sınıflandırıcılarınızı oluşturabilir ve eğitebilirsiniz. Kendi çalışmanızı oluşturma konusunda daha fazla iş vardır, ancak bunlar kuruluşunuzun ihtiyaçlarına göre çok daha iyi uyarlanır.

Özel eğitilebilir sınıflandırıcıyı, kesinlikle kategoride yer alan örnekleri besleyerek oluşturmaya başlarsınız. Bu örnekleri işledikten sonra, hem eşleşen hem de eşleşmeyen örneklerin bir karışımını vererek test edebilirsiniz. Ardından sınıflandırıcı, belirli bir öğenin oluşturduğunuz kategoriye girip girmediğine ilişkin tahminlerde bulunur. Ardından, tahminlerinin doğruluğunu artırmaya yardımcı olmak için gerçek pozitifleri, gerçek negatifleri, hatalı pozitifleri ve hatalı negatifleri sıralayarak sonuçlarını onaylarsınız.

Sınıflandırıcıyı yayımladığınızda, SharePoint Online, Exchange ve OneDrive gibi konumlardaki öğeleri sıralar ve içeriği sınıflandırır. Sınıflandırıcıyı yayımladıktan sonra, ilk eğitim sürecine benzer bir geri bildirim işlemi kullanarak eğitmeye devam edebilirsiniz.

Örneğin, aşağıdakiler için eğitilebilir sınıflandırıcılar oluşturabilirsiniz:

- Yasal belgeler - avukat müşteri ayrıcalığı, kapanış kümeleri, iş bildirimi gibi
- Basın bültenleri, birleşme ve satın alma, anlaşmalar, iş veya pazarlama planları, fikri mülkiyet, patentler, tasarım belgeleri gibi stratejik iş belgeleri
- Faturalar, fiyat teklifleri, iş siparişleri, teklif belgeleri gibi fiyatlandırma bilgileri
- Finansal bilgiler - kurumsal yatırımlar, üç aylık veya yıllık sonuçlar gibi

#### <a name="process-flow-for-creating-custom-classifiers"></a>Özel sınıflandırıcılar oluşturmak için işlem akışı

Bekletme ilkeleri ve iletişim denetimi gibi uyumluluk çözümlerinde kullanılmak üzere bir sınıflandırıcı oluşturma ve yayımlama bu akışı izler. Özel eğitilebilir sınıflandırıcı oluşturma hakkında daha fazla ayrıntı için bkz. [Özel sınıflandırıcı oluşturma](classifier-get-started-with.md).

![işlem akışı özel sınıflandırıcısı.](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Sınıflandırıcıları yeniden eğitme

Tüm özel eğitilebilir sınıflandırıcıların doğruluğunu artırmaya yardımcı olabilir ve gerçekleştirdikleri sınıflandırmanın doğruluğu hakkında geri bildirim sağlayabilirsiniz. Buna yeniden eğitme denir ve bu iş akışını izler.

> [!NOTE]
> Önceden eğitilmiş sınıflandırıcılar yeniden eğitilemez.

![sınıflandırıcı yeniden eğitme iş akışı.](../media/classifier-retraining-workflow.png)

## <a name="provide-matchnot-a-match-accuracy-feedback-in-trainable-classifiers"></a>Eğitilebilir sınıflandırıcılarda eşleşme/eşleşme doğruluğu geri bildirimi sağlama

Eğitilebilir bir sınıflandırıcının **İçerik gezgininde** ve **Eğitilebilir lassifier'larda sahip olduğu eşleşmelerin** sayısını görüntüleyebilirsiniz. Ayrıca bir öğenin gerçekten eşleşme olup olmadığıyla ilgili geri bildirim sağlayabilir veya **Eşleştir**, **Eşleştir değil** geri bildirim mekanizmasını kullanabilir ve sınıflandırıcılarınızı ayarlamak için bu geri bildirimi kullanabilirsiniz. Daha fazla bilgi için bkz. [Sınıflandırıcı doğruluğunu artırma (önizleme).](data-classification-increase-accuracy.md) 


## <a name="see-also"></a>Ayrıca bkz.

- [Bekletme etiketleri](retention.md)
- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md)
- [Duyarlılık etiketleri](sensitivity-labels.md)
- [Hassas bilgi türü varlık tanımları](sensitive-information-type-entity-definitions.md)
- [Belge parmakla yazdırma](document-fingerprinting.md)
- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
