---
title: Microsoft Syntex'teki model türlerine genel bakış
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-overview
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te özel modeller ve önceden oluşturulmuş modeller hakkında bilgi edinin.
ms.openlocfilehash: 47eea92e8e9e4e5eb4588d04dd1422a43afd16ae
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664354"
---
# <a name="overview-of-model-types-in-microsoft-syntex"></a>Microsoft Syntex'teki model türlerine genel bakış

Microsoft Syntex'teki içerik anlama, yapay zeka modelleriyle başlar. Modeller, SharePoint belge kitaplıklarına yüklenen belgeleri tanımlamanıza ve sınıflandırmanıza ve ardından her dosyadan ihtiyacınız olan bilgileri ayıklamanıza olanak tanır.

SharePoint belge kitaplığına uygulandığında, model bir içerik türüyle ilişkilendirilir ve ayıklanan bilgilerin depolandığı sütunlara sahiptir. Oluşturduğunuz içerik türü SharePoint içerik türü galerisinde depolanır. Ayrıca, şemalarını kullanmak için mevcut içerik türlerini kullanmayı da seçebilirsiniz.

Syntex [, özel modeller](#custom-models) ve [önceden oluşturulmuş modeller](#prebuilt-models) kullanır. 

![Syntex özel ve önceden oluşturulmuş model türlerini gösteren diyagram.](../media/content-understanding/syntex-model-types-diagram.png)

Modeller, [bir içerik merkezinde](create-a-content-center.md) oluşturulan *kurumsal modeller* veya [yerel SharePoint sitenizde](create-local-model.md) oluşturulan *yerel modeller* olabilir.

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GJXS] 

</br>
--->

## <a name="custom-models"></a>Özel modeller

Seçtiğiniz özel modelin türü, kullandığınız dosya türlerine, dosyaların biçimine ve yapısına ve modeli uygulamak istediğiniz yere bağlıdır.

Özel modeller şunlardır:

- [Yapılandırılmamış belge işleme](#unstructured-document-processing)
- [Serbest biçimli belge işleme](#freeform-document-processing)
- [Yapılandırılmış belge işleme](#structured-document-processing)

Özel modellerdeki yan yana farkları görüntülemek için bkz. [Özel modelleri karşılaştırma](./difference-between-document-understanding-and-form-processing-model.md).

### <a name="unstructured-document-processing"></a>Yapılandırılmamış belge işleme

Belgeleri otomatik olarak sınıflandırmak ve onlardan bilgi ayıklamak için yapılandırılmamış belge işleme modelini kullanın. Mektuplar veya sözleşmeler gibi yapılandırılmamış belgelerle en iyi şekilde çalışır. Bu belgelerde tümceciklere veya desenlere göre tanımlanabilen metinler olmalıdır. Tanımlanan metin hem dosyanın türünü (sınıflandırması) hem de ayıklamak istediklerinizi (ayıklayıcıları) tanımlar.

Örneğin, yapılandırılmamış bir belge, farklı şekillerde yazılabilen bir sözleşme yenileme mektubu olabilir. Ancak, bilgiler her sözleşme yenileme belgesinin gövdesinde tutarlı bir şekilde bulunur. Örneğin, "Hizmet başlangıç tarihi" metin dizesi ve ardından gerçek bir tarih.

Bu model türü en geniş dosya türlerini destekler ve yalnızca Latin alfabesini (İngilizce karakterler) kullanan dosyalarda çalışır.

Daha fazla bilgi için bkz. [Yapılandırılmamış belge işlemeye genel bakış](document-understanding-overview.md).

### <a name="freeform-document-processing"></a>Serbest biçimli belge işleme

Bilgilerin belgenin herhangi bir yerinde görünebileceği mektuplar ve sözleşmeler gibi yapılandırılmamış ve serbest biçimli belgelerden otomatik olarak bilgi ayıklamak için serbest biçimli belge işleme modelini kullanın.

Serbest biçimli belge işleme modelleri, Syntex içinde model oluşturmak ve eğitmek için Microsoft Power Apps [AI Builder'ı](/ai-builder/form-processing-model-overview) kullanır. 

> [!NOTE]
> Serbest biçimli belge işleme modeli henüz bazı bölgelerde kullanılamamaktadır. Daha fazla bilgi için bkz. [Bölgeye göre özellik kullanılabilirliği](/ai-builder/availability-region).

Kuruluşunuz posta, faks ve e-posta gibi çeşitli kaynaklardan büyük miktarlarda mektup ve belge aldığından. Bu belgelerin işlenmesi ve veritabanına el ile girilmesi önemli ölçüde zaman alabilir. Bu model, bu belgelerden metin ve diğer bilgileri ayıklamak için yapay zeka kullanarak bu işlemi otomatikleştirir.

Bu model türü, belge türünün otomatik olarak sınıflandırılması gerekmiyorsa PDF veya görüntü dosyalarındaki İngilizce belgeler için en iyi seçenektir.

Daha fazla bilgi için bkz. [Serbest biçimli belge işlemeye genel bakış](freeform-document-processing-overview.md).

### <a name="structured-document-processing"></a>Yapılandırılmış belge işleme

Alan ve tablo değerlerini otomatik olarak tanımlamak için yapılandırılmış belge işleme modelini kullanın. Formlar ve faturalar gibi yapılandırılmış veya yarı yapılandırılmış belgeler için en iyi sonucu sağlar.

Yapılandırılmış belge işleme modelleri, Syntex içinde model oluşturmak ve eğitmek için Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) belge işlemeyi (eski adıyla form işleme) kullanır. 

Bu model türü en geniş dil aralığını destekler ve örnek belgelerden formunuzun düzenini anlamak için eğitilir ve ardından benzer konumlardan ayıklamak için ihtiyacınız olan verileri aramayı öğrenir. Formlar genellikle varlıkların aynı konumda olduğu daha yapılandırılmış bir düzene sahiptir (örneğin, vergi formundaki bir sosyal güvenlik numarası).

Daha fazla bilgi için bkz. [Yapılandırılmış belge işlemeye genel bakış](form-processing-overview.md).

## <a name="prebuilt-models"></a>Önceden oluşturulmuş modeller

Özel bir model oluşturmanız gerekmiyorsa, belirli yapılandırılmış belgeler için önceden eğitilmiş önceden oluşturulmuş bir [model](prebuilt-overview.md) kullanabilirsiniz.

Önceden oluşturulmuş modeller şunlardır:

- [Fatura işleme](#invoice-processing)
- [Makbuz işleme](#receipt-processing)

Önceden oluşturulmuş modeller, belgeleri ve belgelerdeki yapılandırılmış bilgileri tanımak için önceden eğitilir. Sıfırdan yeni bir özel model oluşturmak yerine, kuruluşunuzun gereksinimlerine uygun belirli alanlar eklemek için önceden eğitilmiş mevcut bir modeli yineleyebilirsiniz.

### <a name="invoice-processing"></a>Fatura işleme

Fatura işleme modeli, satış faturalarından önemli bilgileri analiz eder ve ayıklar. API faturaları çeşitli biçimlerde analiz eder ve müşteri adı, faturalama adresi, son tarih ve son ödeme tutarı gibi önemli fatura bilgilerini ayıklar.

Önceden oluşturulmuş fatura işleme modelleri hakkında daha fazla bilgi için bkz. [Faturalardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma](prebuilt-model-invoice.md).

### <a name="receipt-processing"></a>Makbuz işleme

Önceden oluşturulmuş makbuz işleme modeli, satış makbuzlarından önemli bilgileri analiz eder ve ayıklar. API basılı ve el yazısı makbuzları analiz eder ve satıcı adı, satıcı telefon numarası, işlem tarihi, vergi ve işlem toplamı gibi önemli makbuz bilgilerini ayıklar.

Önceden oluşturulmuş makbuz işleme modelleri hakkında daha fazla bilgi için bkz. [Makbuzlardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma](prebuilt-model-receipt.md).

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex'te özel modelleri karşılaştırma](./difference-between-document-understanding-and-form-processing-model.md)

[Eğitim: AI Builder ile iş performansını geliştirme](/learn/paths/improve-business-performance-ai-builder/?source=learn)
