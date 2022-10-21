---
title: Microsoft Syntex'te serbest biçimli belge işlemeye genel bakış
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te serbest biçimli belge işleme modelleri oluşturmak için AI Builder'ı kullanmayı öğrenin.
ms.openlocfilehash: 7937fd738cfa011eada44f1f57b46f6e2af2e267
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664372"
---
# <a name="overview-of-freeform-document-processing-in-microsoft-syntex"></a>Microsoft Syntex'te serbest biçimli belge işlemeye genel bakış

Harfler ve sözleşmeler gibi yapılandırılmamış ve serbest biçimli belgelerden otomatik olarak bilgi ayıklamak için serbest biçimli belge işleme modelini ([serbest biçimli seçim yöntemi](create-syntex-model.md#train-a-custom-model)) kullanın.

Microsoft Syntex, SharePoint belge kitaplıkları içinde serbest biçimli belge işleme modelleri oluşturmak için Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) belge işlemeyi (eski adıyla form işleme) kullanır.
<!---
 ![AI Builder.](../media/content-understanding/ai-builder.png)
--->
Anlaşmalar ve yazışmalar gibi yapılandırılmamış veya serbest biçimli belgelerden anahtar-değer çiftlerini ve tablo verilerini tanımlamak ve ayıklamak için makine öğrenmesi teknolojisini kullanan serbest biçimli belge işleme modelleri oluşturmak için AI Builder belge işlemeyi kullanabilirsiniz.

Kuruluşlar genellikle posta, faks ve e-posta gibi çeşitli kaynaklardan büyük miktarlarda yapısı olmayan belgeler alır. Bu belgelerin işlenmesi ve veritabanına el ile girilmesi önemli ölçüde zaman alabilir. Belgelerinizdeki metinleri, anahtar-değer çiftlerini ve tabloları ayıklamak için yapay zeka kullanarak Syntex bu işlemi otomatikleştirir. 

> [!NOTE]
> Kuruluşunuzda bu modelleri kullanma hakkında daha fazla fikir için bkz. [Benimsemeyi ve](adoption-getstarted.md) [Senaryoları ve kullanım örneklerini](adoption-scenarios.md) kullanmaya başlama.

Örneğin, belge kitaplığına yüklenen tüm belgeleri tanımlayan yapılandırılmış bir belge işleme modeli oluşturabilirsiniz. Her belgeden, sizin için önemli olan belirli verileri ayıklayabilir ve görüntüleyebilirsiniz.

![Belge kitaplığı görünümünü gösteren ekran görüntüsü.](../media/content-understanding/doc-lib-done.png) 

Modelinizi eğitmek ve formunuzdan ayıklanacak bilgileri tanımlamak için örnek dosyaları kullanırsınız. Belgenizin düzeni, modeliniz eğitilerek öğrenilir. Başlamak için yalnızca beş form belgesine ihtiyacınız vardır. Syntex örnek dosyalarınızı anahtar-değer çiftleri için analiz eder ve algılanmamış olabilecek dosyaları el ile de tanımlayabilirsiniz.  AI builder, modelinizin doğruluğunu örnek dosyalarınızda test etmenizi sağlar.

Yalnızca etkin olduğu SharePoint belge kitaplıklarında yapılandırılmış bir belge işleme modeli oluşturabilirsiniz. Etkinleştirildiyse, belge kitaplığınızda **Sınıflandır ve ayıkla** seçeneğini görebilirsiniz.

![AI Builder modelini gösteren ekran görüntüsü.](../media/content-understanding/create-ai-builder-model2.png)

Belge kitaplığınızda etkinleştirilmesi gerekiyorsa Microsoft 365 yöneticinize başvurun.

## <a name="requirements"></a>Gereksinimler

Bu modeli seçerken dikkate alınması gereken gereksinimler hakkında bilgi için bkz [. Microsoft Syntex'te modeller için gereksinimler ve sınırlamalar](requirements-and-limitations.md#freeform-document-processing). 

## <a name="see-also"></a>Ayrıca bkz.

[Özel modelleri karşılaştırma](difference-between-document-understanding-and-form-processing-model.md)

[Serbest biçimli belge işleme modelini eğitin](train-freeform-document-processing-model.md)