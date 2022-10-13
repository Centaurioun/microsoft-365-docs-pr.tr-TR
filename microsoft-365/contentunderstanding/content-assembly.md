---
title: Microsoft Syntex'te içerik derlemesine genel bakış
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te modern bir şablon kullanarak belge ve diğer içerik oluşturma hakkında bilgi edinin.
ms.openlocfilehash: 62016db6ee47a94c0b7c22ac8173b89c8150cc5f
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564125"
---
# <a name="overview-of-content-assembly-in-microsoft-syntex"></a>Microsoft Syntex'te içerik derlemesine genel bakış

Sözleşmeler, iş bildirimleri, hizmet sözleşmeleri, onay mektupları, satış sunumları ve yazışmalar gibi standart yinelenen iş belgelerini otomatik olarak oluşturmanıza yardımcı olması için Microsoft Syntex'teki içerik derleme özelliklerini kullanabilirsiniz. Tüm bu eylemleri daha hızlı, daha tutarlı ve daha az hatayla yapmak için modern şablonlar oluşturabilir ve bu şablonları kullanarak belge oluşturabilirsiniz.

![Modern bir şablondan belge oluşturma akışının diyagramı.](../media/content-understanding/content-assembly-diagram.png)

Modern bir şablon oluşturmak için var olan bir belgeyi karşıya yükler ve ardından sharepoint listelerini veya el ile girdileri veri kaynağı olarak kullanarak otomatik olarak yeni içerik oluşturmak için bu şablonu kullanırsınız.

> [!NOTE]
> İçerik derleme özelliklerine erişmek ve bunları kullanmak için lisanslı bir Syntex kullanıcısı olmanız gerekir. SharePoint listelerini yönetmek için de izinleriniz olmalıdır.


## <a name="requirements-and-limitations"></a>Gereksinimler ve sınırlamalar

### <a name="supported-file-types"></a>Desteklenen dosya türleri

Şablon oluşturmak için şu anda yalnızca Microsoft Word belgeleri (.docx/.doc uzantısı) desteklenmektedir.

### <a name="file-limitations"></a>Dosya sınırlamaları

- Modern şablon olarak kullanmak istediğiniz Word belgesinde açıklamalar olmamalıdır veya Değişiklikleri İzle etkin olmamalıdır.

- Word'de içerik denetimleri modern şablon için alanlar oluşturmak için kullanıldığından, resimlere yönelik metin yer tutucularının metin sarmalı olmadığından emin olun. Belge zaten içerik denetimleri içeriyorsa, modern bir şablon oluşturmak için kullanmadan önce bunları kaldırın.

### <a name="current-release-limitations"></a>Geçerli sürüm sınırlamaları

- Şablon ve belge bir belge kitaplığıyla ilişkilendirilir. Şablonu başka bir belge kitaplığında kullanmak için, şablonu bu belge kitaplığında yeniden oluşturmanız gerekir.

- Modern şablonu oluşturmak için kullanılan karşıya yüklenen belge ayrı bir kopya olarak kaydedilir ve belge kitaplığının /forms dizinine yerleştirilir. Disk üzerindeki özgün dosya etkilenmez.

- Metin için alanlar ve ayrıca tablodaki hücrelerdeki metinler için alanlar oluşturabilirsiniz. Ancak görüntüler, akıllı resim, tam tablolar ve madde işaretli listeler şu anda desteklenmiyor.

- Şablondan bir belge oluşturulduktan sonra, şablonla ilişkilendirilmemiş olur.

## <a name="differences-between-modern-templates-and-other-document-templates"></a>Modern şablonlarla diğer belge şablonları arasındaki farklar

|Özellik  |Modern şablonlar  |Diğer şablonlar  |
|---------|---------|---------|
|Lisanslama      |Bu teklife erişmek için Syntex lisansı gerekir.  |Microsoft E3 veya E5 lisansının bir parçası olarak sunulur.  |
|Bunların ne zaman kullanılacağı            | Belgenin yalnızca belirli bölümleri değiştiğinde, hizmet sözleşmeleri ve iş deyimleri gibi standart işlem belgeleri oluşturmak için kullanmanız gerekir. Modern şablonlardan oluşturulan belgeler tutarlılık ve kullanıcılar serbest akışta belgenin bölümlerini değiştirdiğinde el ile hata ve yazım hatası oluşma olasılığının daha az olmasını sağlar.  |Belgeyi diğer kullanıcıların başvurması için örnek olarak ayarlamak istediğinizde bu yöntemi kullanmalısınız. Satış sunumları veya yönetici özetleri gibi işlem dışı belgeler için normal şablonları kullanmayı düşünebilirsiniz.  |
|İçerik oluşturmayı standartlaştırma |Şablon yayımlandıktan sonra kullanıcıların belge oluşturmasını kolaylaştırmak için alanlar ekleyebilir ve ardından içeriğin yalnızca belirli bölümleri için çeşitli veri kaynaklarıyla ilişkilendirebilirsiniz.  |Karşıya yüklendikten sonra dosya şablonda olduğu gibi tutulur. Şablonu kullanan tüm kullanıcıların içeriği buna göre değiştirmesi gerekir.   |
|Desteklenen veri kaynakları     |Şablonları oluştururken alanları SharePoint listeleri ve terim deposuyla ilişkilendirebilirsiniz.   |Geçerli değil   |
|Desteklenen belge türleri    |Şablon oluşturmak için şu anda yalnızca Microsoft Word belgeleri (.docx/.doc uzantısı) desteklenmektedir.  |Şablon olarak karşıya yüklemek için herhangi bir dosyayı kullanabilirsiniz.   |
|Şablonların yönetimi    |Şablon oluşturulduktan sonra şablon alanlarını düzenleyebilir veya yönetebilir, şablonu yeniden adlandırabilir ve kullanım için yeniden yayımlayabilirsiniz.  |Geçerli değil   |
|Şablonların taslak sürümü |Son olarak diğer kullanıcılar tarafından kullanılmak üzere yayımlamadan önce şablonların taslak sürümlerini oluşturabilirsiniz.   |Normal şablonların taslaklarını oluşturma özelliği yoktur.  |
|Iş akışı   |[Power Automate iş akışlarını ayarlayarak](automate-document-generation.md) şablonlardan belge oluşturmayı otomatikleştirebilirsiniz.  |İş akışları normal şablonlarla yapılandırılamaz.  |

> [!div class="nextstepaction"]
> [Modern şablon oluşturma > kullanmaya başlama](content-assembly-modern-template.md)



 
