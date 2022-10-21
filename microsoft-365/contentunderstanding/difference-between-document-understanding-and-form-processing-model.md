---
title: Microsoft Syntex'te özel modelleri karşılaştırma
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'teki özel modeller arasındaki temel farklar hakkında bilgi edinin.
ms.openlocfilehash: 63d6d444fad48da993413b15943bffda7b175ad1
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660103"
---
# <a name="compare-custom-models-in-microsoft-syntex"></a>Microsoft Syntex'te özel modelleri karşılaştırma 

Gereksinimlerinize en uygun modeli belirlemenize yardımcı olmak için özel modellerdeki farkları görmek için aşağıdaki tabloyu kullanın.

| Özellik | Yapılandırılmamış belge işleme | Serbest biçimli belge işleme | Yapılandırılmış belge işleme |
| ------- | ------- | ------- | ------- |
| Bu içerik türü için kullanın | Yapılandırılmamış veya yarı yapılandırılmış dosya biçimleri, örneğin, düzende farklılıklar bulunan ancak yine de ayıklanacak benzer bilgiler olan Office belgeleri. | Yapılandırılmamış ve serbest biçimli dosya biçimleri, örneğin harfler, sözleşmeler ve iş deyimleri gibi ayarlanmış yapısı olmayan belgeler. | Yapılandırılmış ve yarı yapılandırılmış dosya biçimleri, örneğin, düzen ve biçimlendirmenin benzer olduğu faturalar veya satın alma siparişleri gibi form içeriğine yönelik PDF'ler. |
| Model oluşturma | SharePoint'te içerik merkezi olan yeni bir sitede oluşturulan model.  | SharePoint belge kitaplığından sorunsuz erişimle [AI Builder'da](/ai-builder/overview) oluşturulan model.| SharePoint belge kitaplığından sorunsuz erişimle [AI Builder'da](/ai-builder/overview) oluşturulan model. |
| Sınıflandırma türü | Hangi verilerin ayıklanması için belge konumu atamak için makine öğretimi kullanan isteğe bağlı ayıklayıcılarla eğitilebilir sınıflandırıcı. | Geçerli değil | Geçerli değil |
| Konum | Birden çok kitaplık için uygulanabilir. | Tek bir belge kitaplığı için eğitildi. | Tek bir belge kitaplığı için eğitildi. |
| Desteklenen dosya türleri | Negatif örnekler de dahil olmak üzere 5-10 .pdf, Office veya e-posta dosyaları üzerinde eğitin.<br>Office dosyaları 64.000 karakterle kesilir. OCR ile taranan dosyalar 20 sayfayla sınırlıdır. 20'den fazla dosya türünü destekler. [Desteklenen dosya türlerine](requirements-and-limitations.md#unstructured-document-processing) bakın.  | Toplam 50 MB ve 500 sayfa .pdf, .jpg veya .png biçiminde eğitin. | Toplam 50 MB ve 500 sayfa .pdf, .jpg veya .png biçiminde eğitin. |
| Yönetilen meta verilerle tümleştirme | Evet, yapılandırılmış yönetilen meta veri alanına başvuran varlık ayıklayıcısı eğiterek. | Hayır | Hayır |
| Microsoft Purview Bilgi Koruması ile uyumluluk özelliği tümleştirmesi | Yayımlanan bekletme etiketlerini ayarlayın.<br>Yayımlanan duyarlılık etiketlerini ayarlayın. | Bekletme etiketlerini ayarlama geliyor. <br>Duyarlılık etiketlerini ayarlama geliyor. | Yayımlanan bekletme etiketlerini ayarlayın. <br>Duyarlılık etiketlerini ayarlama geliyor. |
| Desteklenen bölgeler| Tüm bölgelerde kullanılabilir. | Power Platform'a dayanır. Power Platform ve AI Builder için genel kullanılabilirlik hakkında bilgi için bkz. [Power Platform kullanılabilirliği](https://dynamics.microsoft.com/geographic-availability/). | Power Platform'a dayanır. Power Platform ve AI Builder için genel kullanılabilirlik hakkında bilgi için bkz. [Power Platform kullanılabilirliği](https://dynamics.microsoft.com/geographic-availability/). |
| İşlem maliyeti | Geçerli değil | AI Builder kredilerini kullanır.<br>Aylık her Syntex lisansı için 3.500 kredi dahildir.<br>1 milyon kredi, 2.000 dosya sayfası işlenmesine izin verecek. | AI Builder kredilerini kullanır.<br>Aylık her Syntex lisansı için 3.500 kredi dahildir.<br>1 milyon kredi, 2.000 dosya sayfası işlenmesine izin verecek. |
| Kapasite | Kapasite kısıtlaması yok. | Varsayılan Power Platform ortamını kullanır (Dataverse veritabanının desteklendiği özel ortamlar). | Varsayılan Power Platform ortamını kullanır (Dataverse veritabanının desteklendiği özel ortamlar). |
| Desteklenen diller| Modeller tüm Latin alfabesi dillerinde çalışır. İngilizceye ek olarak: Almanca, İsveççe, Fransızca, İspanyolca, İtalyanca ve Portekizce. | Geçerli dil desteği İngilizce içindir. | [73 dil için dil](/ai-builder/form-processing-model-requirements.md#languages-supported) desteği. |

## <a name="see-also"></a>Ayrıca bkz.

[Eğitim: AI Builder ile iş performansını geliştirme](/training/paths/improve-business-performance-ai-builder/?source=learn)


