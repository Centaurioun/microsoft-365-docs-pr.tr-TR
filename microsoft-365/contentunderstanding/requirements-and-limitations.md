---
title: Microsoft Syntex'teki modeller için gereksinimler ve sınırlamalar
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
description: Microsoft Syntex'teki modeller için dosya sınırlamaları, dosya türleri, desteklenen diller ve diğer gereksinimler hakkında bilgi edinin.
ms.openlocfilehash: 967a47f96c2345772fb8a7eac12db6e95d5128c8
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664408"
---
# <a name="requirements-and-limitations-for-models-in-microsoft-syntex"></a>Microsoft Syntex'teki modeller için gereksinimler ve sınırlamalar

<sup>**Şunlar için geçerlidir:**  &ensp; &#10003; Tüm özel modeller &ensp; | &ensp; &#10003; Tüm önceden oluşturulmuş modeller</sup>

Microsoft Syntex [, özel modeller ve önceden oluşturulmuş modeller oluşturmanıza](model-types-overview.md) olanak tanır. Seçtiğiniz modelin türüne bağlı olarak, dosya türü ve boyutu, desteklenmesi gereken diller, coğrafi konular ve hangi model türünü kullanacağınıza karar vermenize yardımcı olacak diğer faktörler gibi farklı gereksinimler olabilir.

Özel modeller:

- [Yapılandırılmamış belge işleme](#unstructured-document-processing)
- [Serbest biçimli belge işleme](#freeform-document-processing)
- [Yapılandırılmış belge işleme](#structured-document-processing)
 
Önceden oluşturulmuş modeller:

- [Fatura işleme](#invoice-processing)
- [Makbuz işleme](#receipt-processing)

## <a name="custom-models"></a>Özel modeller

### <a name="unstructured-document-processing"></a>Yapılandırılmamış belge işleme

| Simge          | Açıklama   |
| ------------- | ------------- |
| ![Dosyalar simgesi.](/office/media/icons/files-blue.png)  | **Desteklenen dosya türleri** <br>Bu model şu dosya türlerini destekler: .csv, .doc, .docx, .eml, .heic, .heif, .htm, .html, .jpeg, .jpg, .md, .msg, .pdf, .png, .ppt, .pptx, .rtf, .tif, .tiff, .txt, .xls ve .xlsx. |
| ![Konuşma simgesi.](/office/media/icons/chat-room-conversation-blue.png)  | **Desteklenen diller** <br>Bu model, İngilizce, Fransızca, Almanca, İtalyanca ve İspanyolca dahil olmak üzere tüm Latin tabanlı dilleri destekler. |
| ![Paragraf simgesi.](/office/media/icons/paragraph-writing-blue.png)  | **OCR ile ilgili dikkat edilmesi gerekenler** <br>Bu model, .pdf dosyalarını, görüntü dosyalarını ve .tiff dosyalarını taramak için optik karakter tanıma (OCR) teknolojisini kullanır. OCR işleme, aşağıdaki gereksinimleri karşılayan belgelerde en iyi sonucu sağlar: <br> - .jpg, .png veya .pdf dosya biçimi (metin veya taranmış). Karakter ayıklama ve konumda hata olmayacağından, metin eklenmiş .pdf dosyaları daha iyidir. <br> - .pdf dosyalarınız parola kilitliyse, göndermeden önce kilidi kaldırmanız gerekir. <br> - Koleksiyon başına eğitim için kullanılan belgelerin birleştirilmiş dosya boyutu 50 MB'ı aşmamalı ve PDF belgelerinde 500'den fazla sayfa olmamalıdır. <br> - Görüntüler için boyutlar 50 x 50 ile 10.000 x 10.000 piksel arasında olmalıdır. Çok geniş veya tek boyutlu görüntüler (örneğin, kat planları) OCR işleminde kesilebilir ve doğruluğu kaybolabilir. <br> - .pdf dosyalar için boyutlar Yasal veya A3 kağıt boyutlarına karşılık gelen en fazla 17 x 17 inç ve daha küçük olmalıdır. <br> - Kağıt belgelerden taranıyorsa taramalar yüksek kaliteli görüntüler olmalıdır. <br> - Latin alfabesini (İngilizce karakterler) kullanmalıdır. <br> Microsoft Office metin tabanlı dosyalar ve OCR ile taranan dosyalar (.pdf, görüntü veya .tiff) hakkında aşağıdaki farklara dikkat edin: <br> - Office dosyaları: 64.000 karakterde kesilir (eğitimde ve bir belge kitaplığındaki dosyalarda çalıştırıldığında). <br> - OCR ile taranan dosyalar: 500 sayfalık bir sınır vardır. Yalnızca PDF ve görüntü dosyası türleri OCR tarafından işlenir. |
| ![Dünya simgesi.](/office/media/icons/globe-internet.png)  | **Multi-Geo ortamları** <br>[Bir Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) ortamında Syntex'i ayarlarken, bunu yalnızca merkezi konumdaki model türünü kullanacak şekilde yapılandırabilirsiniz. Bu model türünü bir uydu konumunda kullanmak istiyorsanız Microsoft desteğine başvurun. |
| ![Nesneler simgesi.](/office/media/icons/objects-blue.png)  | **Çok modelli kitaplıklar** <br>Aynı kitaplığa iki veya daha fazla eğitilmiş model uygulanırsa, dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. |

### <a name="freeform-document-processing"></a>Serbest biçimli belge işleme

| Simge          | Açıklama   |
| ------------- | ------------- |
| ![Dosyalar simgesi.](/office/media/icons/files-blue.png)  | **Desteklenen dosya türleri** <br>Bu model aşağıdaki dosya türlerini destekler: bkz. [dosya türü gereksinimleri](/ai-builder/form-processing-model-requirements#requirements). |
| ![Konuşma simgesi.](/office/media/icons/chat-room-conversation-blue.png)  | **Desteklenen diller** <br>Bu model şu dili destekler: İngilizce. |
| ![Paragraf simgesi.](/office/media/icons/paragraph-writing-blue.png) | **OCR ile ilgili dikkat edilmesi gerekenler** <br>Bu model, .pdf dosyalarını, görüntü dosyalarını ve .tiff dosyalarını taramak için optik karakter tanıma (OCR) teknolojisini kullanır. OCR işleme [, bu gereksinimleri](/ai-builder/form-processing-model-requirements#requirements) karşılayan belgelerde en iyi şekilde çalışır. |
| ![Bant genişliği/verimlilik simgesi.](/office/media/icons/bandwidth-efficiency-blue.png)  | **İyileştirme ipuçları** <br>Modeliniz istediğiniz gibi çalışmıyorsa [, modelinizin performansını geliştirmek için bu adımları](/ai-builder/improve-form-processing-performance) deneyin. |
| ![Dünya simgesi.](/office/media/icons/globe-internet.png)  | **Multi-Geo ortamları** <br>[Bir Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) ortamında Syntex'i ayarlarken, bunu yalnızca merkezi konumdaki model türünü kullanacak şekilde yapılandırabilirsiniz. Bu model türünü bir uydu konumunda kullanmak istiyorsanız Microsoft desteğine başvurun. |
| ![Bloklar simgesi.](/office/media/icons/blocks-blue.png)  | **Özel Power Platform ortamları** <br>Power Platform işleme için özel bir ortam (varsayılan ortam yerine) kullanıyorsanız ek kurulum gereksinimleri vardır. Daha fazla bilgi için bkz [. Özel Power Platform ortamları](/microsoft-365/contentunderstanding/set-up-content-understanding#custom-power-platform-environments). |
| ![Nesneler simgesi.](/office/media/icons/objects-blue.png)  | **Çok modelli kitaplıklar** <br>Aynı kitaplığa iki veya daha fazla eğitilmiş model uygulanırsa, dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. Kitaplık başına yalnızca bir serbest biçimli veya yapılandırılmış modeliniz olabilir. |

### <a name="structured-document-processing"></a>Yapılandırılmış belge işleme

| Simge          | Açıklama   |
| ------------- | ------------- |
| ![Dosyalar simgesi.](/office/media/icons/files-blue.png)  | **Desteklenen dosya türleri** <br>Bu model aşağıdaki dosya türlerini destekler: bkz. [dosya türü gereksinimleri](/ai-builder/form-processing-model-requirements#requirements). |
| ![Konuşma simgesi.](/office/media/icons/chat-room-conversation-blue.png)  | **Desteklenen diller** <br>Bu model 73 dili destekler: [desteklenen dillere](/ai-builder/form-processing-model-requirements#languages-supported) bakın. |
| ![Paragraf simgesi.](/office/media/icons/paragraph-writing-blue.png) | **OCR ile ilgili dikkat edilmesi gerekenler** <br>Bu model, .pdf dosyalarını, görüntü dosyalarını ve .tiff dosyalarını taramak için optik karakter tanıma (OCR) teknolojisini kullanır. OCR işleme [, bu gereksinimleri](/ai-builder/form-processing-model-requirements#requirements) karşılayan belgelerde en iyi şekilde çalışır. |
| ![Bant genişliği/verimlilik simgesi.](/office/media/icons/bandwidth-efficiency-blue.png)  | **İyileştirme ipuçları** <br>Modeliniz istediğiniz gibi çalışmıyorsa [, modelinizin performansını geliştirmek için bu adımları](/ai-builder/improve-form-processing-performance) deneyin. |
| ![Dünya simgesi.](/office/media/icons/globe-internet.png)  | **Multi-Geo ortamları** <br>[Bir Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) ortamında Syntex'i ayarlarken, bunu yalnızca merkezi konumdaki model türünü kullanacak şekilde yapılandırabilirsiniz. Bu model türünü bir uydu konumunda kullanmak istiyorsanız Microsoft desteğine başvurun. |
| ![Bloklar simgesi.](/office/media/icons/blocks-blue.png)  | **Özel Power Platform ortamları** <br>Power Platform işleme için özel bir ortam (varsayılan ortam yerine) kullanıyorsanız ek kurulum gereksinimleri vardır. Daha fazla bilgi için bkz [. Özel Power Platform ortamları](/microsoft-365/contentunderstanding/set-up-content-understanding#custom-power-platform-environments). |
| ![Nesneler simgesi.](/office/media/icons/objects-blue.png)  | **Çok modelli kitaplıklar** <br>Aynı kitaplığa iki veya daha fazla eğitilmiş model uygulanırsa, dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. Kitaplık başına yalnızca bir serbest biçimli veya yapılandırılmış modeliniz olabilir. |

## <a name="prebuilt-models"></a>Önceden oluşturulmuş modeller

### <a name="invoice-processing"></a>Fatura işleme

| Simge          | Açıklama   |
| ------------- | ------------- |
| ![Dosyalar simgesi.](/office/media/icons/files-blue.png)  | **Desteklenen dosya türleri** <br>Bu model şu dosya türlerini destekler: .bmp, .jpeg, .pdf, .png ve .tiff. |
| ![Konuşma simgesi.](/office/media/icons/chat-room-conversation-blue.png)  | **Desteklenen diller** <br>Bu model yalnızca Birleşik Devletler İngilizce faturalarını destekler. |
| ![Paragraf simgesi.](/office/media/icons/paragraph-writing-blue.png)  | **OCR ile ilgili dikkat edilmesi gerekenler** <br>Bu model, .pdf dosyalarını, görüntü dosyalarını ve .tiff dosyalarını taramak için optik karakter tanıma (OCR) teknolojisini kullanır. OCR işleme, aşağıdaki gereksinimleri karşılayan belgelerde en iyi sonucu sağlar: <br> - .jpg, .png veya .pdf dosya biçimi (metin veya taranmış). Karakter ayıklama ve konumda hata olmayacağından, metin eklenmiş .pdf dosyaları daha iyidir. <br> - .pdf ve .tiff dosyaları için en fazla 2.000 sayfa işlenebilir. <br> - Dosya boyutu 50 MB'tan küçük olmalıdır. <br> - Görüntüler için boyutlar 50 x 50 ile 10.000 x 10.000 piksel arasında olmalıdır. <br> - .pdf dosyalar için boyutlar Yasal veya A3 kağıt boyutlarına karşılık gelen en fazla 17 x 17 inç ve daha küçük olmalıdır. <br> - Eğitim verilerinin toplam boyutu 500 sayfa veya daha azdır. <br> Microsoft Office metin tabanlı dosyalar ve OCR ile taranan dosyalar (.pdf, görüntü veya .tiff) hakkında aşağıdaki farklara dikkat edin: <br> - Office dosyaları: 64.000 karakterde kesilir (eğitimde ve bir belge kitaplığındaki dosyalarda çalıştırıldığında). <br> - OCR ile taranan dosyalar: 20 sayfalık bir sınır vardır.|
| ![Dünya simgesi.](/office/media/icons/globe-internet.png)  | **Multi-Geo ortamları** <br>[Bir Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) ortamında Syntex'i ayarlarken, bunu yalnızca merkezi konumdaki model türünü kullanacak şekilde yapılandırabilirsiniz. Bu model türünü bir uydu konumunda kullanmak istiyorsanız Microsoft desteğine başvurun. |
| ![Nesneler simgesi.](/office/media/icons/objects-blue.png)  | **Çok modelli kitaplıklar** <br>Aynı kitaplığa iki veya daha fazla eğitilmiş model uygulanırsa, dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. |

### <a name="receipt-processing"></a>Makbuz işleme

| Simge          | Açıklama   |
| ------------- | ------------- |
| ![Dosyalar simgesi.](/office/media/icons/files-blue.png)  | **Desteklenen dosya türleri** <br>Bu model şu dosya türlerini destekler: .bmp, .jpeg, .pdf, .png ve .tiff. |
| ![Konuşma simgesi.](/office/media/icons/chat-room-conversation-blue.png)  | **Desteklenen diller** <br>Bu model Avustralya, Kanada, Büyük Britanya, Hindistan ve Birleşik Devletler İngilizce satış makbuzlarını destekler. |
| ![Paragraf simgesi.](/office/media/icons/paragraph-writing-blue.png)  | **OCR ile ilgili dikkat edilmesi gerekenler** <br>Bu model, .pdf dosyalarını, görüntü dosyalarını ve .tiff dosyalarını taramak için optik karakter tanıma (OCR) teknolojisini kullanır. OCR işleme, aşağıdaki gereksinimleri karşılayan belgelerde en iyi sonucu sağlar: <br> - .jpg, .png veya .pdf dosya biçimi (metin veya taranmış). Karakter ayıklama ve konumda hata olmayacağından, metin eklenmiş .pdf dosyaları daha iyidir. <br> - .pdf ve .tiff dosyaları için en fazla 2.000 sayfa işlenebilir. <br> - Dosya boyutu 50 MB'tan küçük olmalıdır. <br> - Görüntüler için boyutlar 50 x 50 ile 10.000 x 10.000 piksel arasında olmalıdır. <br> - .pdf dosyalar için boyutlar Yasal veya A3 kağıt boyutlarına karşılık gelen en fazla 17 x 17 inç ve daha küçük olmalıdır. <br> - Eğitim verilerinin toplam boyutu 500 sayfa veya daha azdır. <br> Microsoft Office metin tabanlı dosyalar ve OCR ile taranan dosyalar (.pdf, görüntü veya .tiff) hakkında aşağıdaki farklara dikkat edin: <br> - Office dosyaları: 64.000 karakterde kesilir (eğitimde ve bir belge kitaplığındaki dosyalarda çalıştırıldığında). <br> - OCR ile taranan dosyalar: 20 sayfalık bir sınır vardır.|
| ![Dünya simgesi.](/office/media/icons/globe-internet.png)  | **Multi-Geo ortamları** <br>[Bir Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) ortamında Syntex'i ayarlarken, bunu yalnızca merkezi konumdaki model türünü kullanacak şekilde yapılandırabilirsiniz. Bu model türünü bir uydu konumunda kullanmak istiyorsanız Microsoft desteğine başvurun. |
| ![Nesneler simgesi.](/office/media/icons/objects-blue.png)  | **Çok modelli kitaplıklar** <br>Aynı kitaplığa iki veya daha fazla eğitilmiş model uygulanırsa, dosya en yüksek ortalama güvenilirlik puanına sahip model kullanılarak sınıflandırılır. Ayıklanan varlıklar yalnızca uygulanan modelden olacaktır. |
