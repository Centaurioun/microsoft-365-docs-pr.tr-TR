---
title: Microsoft Syntex'te belge anlamaya genel bakış
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te belge anlama hakkında bilgi edinin.
ms.openlocfilehash: d6b374d55840a53f1d78c22f69deebdbb5d89958
ms.sourcegitcommit: ca082da1c51a3f643f152492579eef5679d52bd0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68547653"
---
# <a name="document-understanding-overview-in-microsoft-syntex"></a>Microsoft Syntex'te belge anlamaya genel bakış


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7]

</br>

Belge anlama, dosya sınıflandırmasını ve bilgilerin ayıklamasını otomatikleştirmek için yapay zeka (AI) modellerini kullanır. Mektuplar veya sözleşmeler gibi yapılandırılmamış belgelerle en iyi şekilde çalışır. Bu belgelerde tümceciklere veya desenlere göre tanımlanabilen metinler olmalıdır. Tanımlanan metin hem dosyanın türünü (sınıflandırması) hem de ayıklamak istediklerinizi (ayıklayıcıları) tanımlar.

> [!NOTE]
> Belge anlama senaryosu örnekleri hakkında daha fazla bilgi için [Syntex benimseme: Kullanmaya başlama kılavuzuna](./adoption-getstarted.md) bakın.

Belge anlama modelleri *, içerik merkezi* olarak adlandırılan bir SharePoint sitesi türünde oluşturulur ve yönetilir. Bir SharePoint belge kitaplığına uygulandığında, model ayıklanan bilgileri depolamak için bir içerik türünün sütunlarıyla ilişkilendirilir. Oluşturduğunuz içerik türü SharePoint içerik türü galerisinde depolanır. Ayrıca, şemalarını kullanmak için mevcut içerik türlerini kullanmayı da seçebilirsiniz.

> [!NOTE]
> Salt okunur veya korumalı içerik türleri güncelleştirilemediği için modelde kullanılamaz.

Aşağıdaki eylemleri gerçekleştirmek için belge anlama modellerinize *sınıflandırıcılar* ve *ayıklayıcılar* ekleyin:

- Sınıflandırıcılar, belge kitaplığına yüklenen belgeleri tanımlamak ve sınıflandırmak için kullanılır. Örneğin, sınıflandırıcı kitaplığa yüklenen tüm *sözleşme yenileme* belgelerini tanımlamak için "eğitilebilir". Sınıflandırıcınızı oluşturduğunuzda sözleşme yenileme içerik türü sizin tarafınızdan tanımlanır.

- Ayıklayıcılar bu belgelerden bilgi çeker. Örneğin, belge kitaplığınızda tanımlanan her sözleşme yenileme belgesi için, her belge için *Hizmet Başlangıç Tarihi* ve *İstemci'yi* gösteren sütunlar görüntülenir. 

Modelinizde sınıflandırıcılarınızı ve ayıklayıcılarınızı eğitmek ve test etmek için örnek dosyaları kullanabilirsiniz. Örnek dosyalar, dosyalardan verileri tanımlamaya ve ayıklamaya çalışırken neleri aramanız gerektiğinde model örnekleri sağlar. Örneğin, sözleşme yenileme sınıflandırıcılarınızı ve ayıklayıcılarınızı şirketinizin birlikte çalıştığı sözleşme yenileme belgelerinin örnekleriyle eğitebilirsiniz. Modelinizin verimliliğini test etmek için örnek dosyaları da kullanabilirsiniz.

Modelinizi yayımladıktan sonra, içerik merkezini kullanarak erişiminiz olan herhangi bir SharePoint belge kitaplığına uygulayın.  

## <a name="file-limitations"></a>Dosya sınırlamaları

Belge anlama modelleri PDF'leri, görüntüleri ve TIFF dosyalarını taramak için Optik Karakter Tanıma (OCR) teknolojisini kullanır. Bir modeli örnek dosyalarla eğittiğinizde ve modeli belge kitaplığındaki dosyalara karşı çalıştırdığınızda dosyalar taranır.

Microsoft Office metin tabanlı dosyalar ve OCR ile taranan dosyalar (PDF, resim veya TIFF) hakkında aşağıdaki farklara dikkat edin:

- Office dosyaları: 64.000 karakterde kesilir (eğitimde ve bir belge kitaplığındaki dosyalarda çalıştırıldığında).

- OCR ile taranan dosyalar: 20 sayfalık bir sınır vardır.  

### <a name="requirements"></a>Gereksinimler

OCR işleme, aşağıdaki gereksinimleri karşılayan belgelerde en iyi sonucu sağlar:

- JPG, PNG veya PDF biçimi (metin veya taranmış). Karakter ayıklama ve konumda hata olmayacağından, metin eklenmiş PDF'ler daha iyidir.

- PDF'leriniz parola kilitliyse, göndermeden önce kilidi kaldırmanız gerekir.

- Koleksiyon başına eğitim için kullanılan belgelerin birleştirilmiş dosya boyutu 50 MB'ı aşmamalı ve PDF belgelerinde 500'den fazla sayfa olmamalıdır.

- Görüntüler için boyutlar 50 x 50 ile 10.000 x 10.000 piksel arasında olmalıdır.
   > [!NOTE]
   > Çok geniş veya tek boyutlu görüntüler (örneğin, kat planları) OCR işleminde kesilebilir ve doğruluğu kaybolabilir.

- PDF dosyaları için boyutların Yasal veya A3 kağıt boyutlarına karşılık gelen en fazla 17 x 17 inç ve daha küçük olması gerekir.

- Kağıt belgelerden taranıyorsa taramalar yüksek kaliteli görüntüler olmalıdır.

- Latin alfabesini (İngilizce karakterler) kullanmalıdır.

### <a name="supported-file-types"></a>Desteklenen dosya türleri

Belge anlama modelleri aşağıdaki dosya türlerini destekler:

- Csv
- Doktor
- Docx
- Eml
- heik
- heif
- htm
- Html
- Jpeg
- Jpg
- markdown
- md
- Msg
- Pdf
- Png
- Ppt
- Pptx
- Rtf
- Tıf
- Tıff
- Txt
- Xls
- xlsx

### <a name="supported-languages"></a>Desteklenen diller

Belge anlama modelleri, aşağıdakiler de dahil olmak üzere *tüm* Latin tabanlı dilleri destekler:

- English
- French
- German
- Italian
- Spanish

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflandırıcı oluştur](create-a-classifier.md)

[Ayıklayıcı oluştur](create-an-extractor.md)

[İçerik merkezi oluştur](create-a-content-center.md)

[Form işleme modeli oluştur](create-a-form-processing-model.md)

[Model uygulama](apply-a-model.md)

[Belge anlama ile form işleme modeli arasındaki fark](difference-between-document-understanding-and-form-processing-model.md)
  
[Form işlemeye genel bakış](form-processing-overview.md)

[Syntex erişilebilirlik modu](accessibility-mode.md)
