---
title: Microsoft Syntex'te önceden oluşturulmuş modellere genel bakış
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
description: Microsoft Syntex'te önceden oluşturulmuş modeller hakkında bilgi edinin.
ms.openlocfilehash: 0ec44b2f7b0b0360eedceadb71ddf9abdc6e2941
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659159"
---
# <a name="overview-of-prebuilt-models-in-microsoft-syntex"></a>Microsoft Syntex'te önceden oluşturulmuş modellere genel bakış

Microsoft Syntex, [özel modellere](model-types-overview.md#custom-models) ek olarak bilgilerin ayıklanmını otomatikleştirmek için *önceden oluşturulmuş modeller* de sağlar.

Önceden oluşturulmuş modeller, belgeleri ve belgelerdeki yapılandırılmış bilgileri tanımak için önceden yapılandırılmıştır. Sıfırdan yeni bir özel model oluşturmak yerine, kuruluşunuzun gereksinimlerine uygun belirli alanlar eklemek için önceden eğitilmiş mevcut bir modeli yineleyebilirsiniz. 

Önceden oluşturulmuş modeller, belirli belge türlerinde ortak olan önceden tanımlanmış metin ve veri alanlarını tanımlamak ve ayıklamak için derin öğrenme modelleriyle birlikte optik karakter tanıma (OCR) kullanır. Dosyalarınızdan birini önceden oluşturulmuş modele göre analiz ederek işe başlarsınız. Ardından, amacınız için anlamlı olan algılanan alanları seçersiniz. Model ihtiyacınız olan alanları algılamazsa farklı bir dosya kullanarak yeniden analiz edebilirsiniz.

Diğer modeller gibi önceden oluşturulmuş modeller de [içerik merkezinde](create-a-content-center.md) oluşturulur ve yönetilir. SharePoint belge kitaplığına uygulandığında, model bir içerik türüyle ilişkilendirilir ve ayıklanan bilgilerin depolandığı sütunlara sahiptir. 

Modelinizi yayımladıktan sonra, içerik merkezini kullanarak erişiminiz olan herhangi bir SharePoint belge kitaplığına uygulayın.  

## <a name="available-prebuilt-models"></a>Kullanılabilir önceden oluşturulmuş modeller

Şu anda önceden oluşturulmuş iki model vardır: [faturalar](prebuilt-model-invoice.md) ve [makbuzlar](prebuilt-model-receipt.md).

- *Fatura modeli, satış faturalarından* önemli bilgileri analiz eder ve ayıklar. API faturaları çeşitli biçimlerde analiz eder ve müşteri adı, faturalama adresi, son tarih ve son ödeme tutarı gibi [önemli fatura bilgilerini ayıklar](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction) .

- *Makbuz modeli, satış makbuzlarından* önemli bilgileri analiz eder ve ayıklar. API basılı ve el yazısı makbuzları analiz eder ve satıcı adı, satıcı telefon numarası, işlem tarihi, vergi ve işlem toplamı gibi [önemli makbuz bilgilerini ayıklar](/azure/applied-ai-services/form-recognizer/concept-receipt#field-extraction) .

Önceden oluşturulmuş ek modeller gelecek sürümlerde kullanıma sunulacaktır.

## <a name="requirements"></a>Gereksinimler

Bu modeli seçerken dikkate alınması gereken gereksinimler hakkında bilgi için bkz [. Microsoft Syntex'te modeller için gereksinimler ve sınırlamalar](requirements-and-limitations.md). 

## <a name="see-also"></a>Ayrıca bkz.

[Faturalardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma](prebuilt-model-invoice.md)

[Makbuzlardan bilgi ayıklamak için önceden oluşturulmuş bir model kullanma](prebuilt-model-receipt.md)

 

