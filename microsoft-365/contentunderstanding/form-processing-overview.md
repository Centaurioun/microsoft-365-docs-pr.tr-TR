---
title: Microsoft Syntex'te yapılandırılmış belge işlemeye genel bakış
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
description: Microsoft Syntex'te yapılandırılmış belge işleme modelleri oluşturmak için AI Builder'ı kullanmayı öğrenin.
ms.openlocfilehash: 9d006741cc236841f4438c5937666c1fc0f02e16
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662664"
---
# <a name="overview-of-structured-document-processing-in-microsoft-syntex"></a>Microsoft Syntex'te yapılandırılmış belge işlemeye genel bakış

> [!NOTE]
> *Yapılandırılmış belge işleme* , önceki sürümlerde *form işleme* olarak biliniyordu.

Alan ve tablo değerlerini otomatik olarak tanımlamak için yapılandırılmış belge işleme modelini ([düzen yöntemi](create-syntex-model.md#train-a-custom-model)) kullanın. Formlar ve faturalar gibi yapılandırılmış veya yarı yapılandırılmış belgeler için en iyi sonucu sağlar.

Microsoft Syntex, SharePoint belge kitaplıkları içinde yapılandırılmış belge işleme modelleri oluşturmak için Microsoft Power Apps [AI Builder](/ai-builder/form-processing-model-overview) belge işlemeyi (eski adıyla form işleme) kullanır.
<!---
 ![AI Builder.](../media/content-understanding/ai-builder.png)
--->
Formlar ve faturalar gibi yapılandırılmış veya yarı yapılandırılmış belgelerden anahtar-değer çiftlerini ve tablo verilerini tanımlamak ve ayıklamak için makine öğrenmesi teknolojisini kullanan yapılandırılmış belge işleme modelleri oluşturmak için AI Builder belge işlemeyi kullanabilirsiniz.

Kuruluşlar genellikle posta, faks ve e-posta gibi çeşitli kaynaklardan büyük miktarlarda fatura alır. Bu belgelerin işlenmesi ve veritabanına el ile girilmesi önemli ölçüde zaman alabilir. Belgelerinizdeki metinleri, anahtar-değer çiftlerini ve tabloları ayıklamak için yapay zeka kullanarak Syntex bu işlemi otomatikleştirir. 

> [!NOTE]
> Kuruluşunuzda bu modelleri kullanma hakkında daha fazla fikir için bkz. [Benimsemeyi ve](adoption-getstarted.md) [Senaryoları ve kullanım örneklerini](adoption-scenarios.md) kullanmaya başlama.

Örneğin, belge kitaplığına yüklenen tüm belgeleri tanımlayan yapılandırılmış bir belge işleme modeli oluşturabilirsiniz. Her belgeden, sizin için önemli olan belirli verileri ayıklayabilir ve görüntüleyebilirsiniz.

![Belge kitaplığı görünümünü gösteren ekran görüntüsü.](../media/content-understanding/doc-lib-done.png)  

Modelinizi eğitmek ve formunuzdan ayıklanacak bilgileri tanımlamak için örnek dosyaları kullanırsınız. Belgenizin düzeni, modeliniz eğitilerek öğrenilir. Başlamak için yalnızca beş form belgesine ihtiyacınız vardır. Syntex örnek dosyalarınızı anahtar-değer çiftleri için analiz eder ve algılanmamış olabilecek dosyaları el ile de tanımlayabilirsiniz.  AI builder, modelinizin doğruluğunu örnek dosyalarınızda test etmenizi sağlar.

Yalnızca etkin olduğu SharePoint belge kitaplıklarında yapılandırılmış bir belge işleme modeli oluşturabilirsiniz. Etkinleştirildiyse, belge kitaplığınızda **Sınıflandır ve ayıkla** seçeneğini görebilirsiniz. 

![AI Builder modelini gösteren ekran görüntüsü.](../media/content-understanding/create-ai-builder-model2.png)

Belge kitaplığınızda etkinleştirilmesi gerekiyorsa Microsoft 365 yöneticinize başvurun.

## <a name="requirements"></a>Gereksinimler

Bu modeli seçerken dikkate alınması gereken gereksinimler hakkında bilgi için bkz [. Microsoft Syntex'te modeller için gereksinimler ve sınırlamalar](requirements-and-limitations.md#structured-document-processing).

## <a name="see-also"></a>Ayrıca bkz.

[Özel modelleri karşılaştırma](difference-between-document-understanding-and-form-processing-model.md)

[Yapılandırılmış belge işleme modelini eğitin](create-a-form-processing-model.md)

[Power Automate belgeleri](/power-automate/)

[Eğitim: AI Builder ile iş performansını geliştirme](/training/paths/improve-business-performance-ai-builder/?source=learn)
