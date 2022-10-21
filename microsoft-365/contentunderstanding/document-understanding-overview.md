---
title: Microsoft Syntex'te yapılandırılmamış belge işlemeye genel bakış
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
description: Microsoft Syntex'te yapılandırılmamış belge işleme modeli hakkında bilgi edinin.
ms.openlocfilehash: 93ca7e2900098f9067f8c63ea9eae857f61bb7a0
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662368"
---
# <a name="overview-of-unstructured-document-processing-in-microsoft-syntex"></a>Microsoft Syntex'te yapılandırılmamış belge işlemeye genel bakış

> [!NOTE]
> *Yapılandırılmamış belge işleme* , önceki sürümlerde *belge anlama* olarak biliniyordu.

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7]

</br>
--->

Dosyaları otomatik olarak sınıflandırmak ve bilgileri ayıklamak için yapılandırılmamış belge işleme modelini ([eğitim yöntemi](create-syntex-model.md#train-a-custom-model)) kullanın. Mektuplar veya sözleşmeler gibi yapılandırılmamış belgeler için en uygun yöntemdir. 

Yapılandırılmamış belge işleme modeli (eski adıyla belge anlama modeli), belgeleri işlemek için yapay zeka (AI) kullanır. Bu belgelerde tümceciklere veya desenlere göre tanımlanabilen metinler olmalıdır. Tanımlanan metin hem dosyanın türünü (sınıflandırması) hem de ayıklamak istediklerinizi (ayıklayıcıları) tanımlar.

> [!NOTE]
> Syntex ve senaryo örneklerini kullanma hakkında daha fazla bilgi için bkz. [Microsoft Syntex'i benimsemeye başlama ve Microsoft Syntex](./adoption-getstarted.md) [senaryoları ve kullanım örnekleri](./adoption-scenarios.md).

Yapılandırılmamış belge işleme modelleri [, içerik merkezi](create-a-content-center.md) olarak adlandırılan bir Tür SharePoint sitesinde oluşturulur ve yönetilir. Bir SharePoint belge kitaplığına uygulandığında, model ayıklanan bilgileri depolamak için bir içerik türünün sütunlarıyla ilişkilendirilir. Oluşturduğunuz içerik türü SharePoint içerik türü galerisinde depolanır. Ayrıca, şemalarını kullanmak için mevcut içerik türlerini kullanmayı da seçebilirsiniz.

> [!NOTE]
> Salt okunur veya korumalı içerik türleri güncelleştirilemez, bu nedenle modelde kullanılamazlar.

Aşağıdaki eylemleri gerçekleştirmek için yapılandırılmamış belge işleme modellerinize [sınıflandırıcılar](create-a-classifier.md) ve [ayıklayıcılar](create-an-extractor.md) ekleyin:

- Sınıflandırıcılar, belge kitaplığına yüklenen belgeleri tanımlamak ve sınıflandırmak için kullanılır. Örneğin, sınıflandırıcı kitaplığa yüklenen tüm *sözleşme yenileme* belgelerini tanımlamak için "eğitilebilir". Sınıflandırıcınızı oluşturduğunuzda sözleşme yenileme içerik türü sizin tarafınızdan tanımlanır.

- Ayıklayıcılar bu belgelerden bilgi çeker. Örneğin, belge kitaplığınızda tanımlanan her sözleşme yenileme belgesi için, her belge için *Hizmet Başlangıç Tarihi* ve *İstemci'yi* gösteren sütunlar görüntülenir. 

Modelinizde sınıflandırıcılarınızı ve ayıklayıcılarınızı eğitmek ve test etmek için örnek dosyaları kullanabilirsiniz. Örnek dosyalar, dosyalardan verileri tanımlamaya ve ayıklamaya çalışırken neleri aramanız gerektiğinde model örnekleri sağlar. Örneğin, sözleşme yenileme sınıflandırıcılarınızı ve ayıklayıcılarınızı şirketinizin birlikte çalıştığı sözleşme yenileme belgelerinin örnekleriyle eğitebilirsiniz. Modelinizin verimliliğini test etmek için örnek dosyaları da kullanabilirsiniz.

Modelinizi yayımladıktan sonra, içerik merkezini kullanarak erişiminiz olan herhangi bir SharePoint belge kitaplığına uygulayın.  

## <a name="requirements"></a>Gereksinimler

Bu modeli seçerken dikkate alınması gereken gereksinimler hakkında bilgi için bkz [. Microsoft Syntex'te modeller için gereksinimler ve sınırlamalar](requirements-and-limitations.md#unstructured-document-processing).

## <a name="see-also"></a>Ayrıca bkz.

[Özel modelleri karşılaştırma](difference-between-document-understanding-and-form-processing-model.md)

