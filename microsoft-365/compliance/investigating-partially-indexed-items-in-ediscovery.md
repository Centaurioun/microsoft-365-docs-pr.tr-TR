---
title: eBulma'da kısmen dizine alınan öğeleri araştırma
description: Kuruluşunuzdaki Exchange, SharePoint ve OneDrive İş kısmen dizine alınmış öğeleri (dizine alınmamış öğeler olarak da adlandırılır) yönetmeyi öğrenin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 06/14/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 813841c6c0196b51ad4a64eeb5ae0e4ab4f8a38b
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687662"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>eBulma'da kısmen dizine alınan öğeleri araştırma

Microsoft Purview uyumluluk portalı çalıştırdığınız bir eBulma araması, bir arama çalıştırdığınızda tahmini arama sonuçlarında otomatik olarak kısmen dizine alınan öğeler içerir. Kısmen dizine alınan öğeler, SharePoint ve OneDrive İş sitelerindeki Exchange posta kutusu öğeleri ve belgeleridir ve herhangi bir nedenle arama için tamamen dizine eklenmemiştir. Çoğu e-posta iletisi ve site belgesi, [e-posta iletileri için Dizin oluşturma sınırları](limits-for-content-search.md#indexing-limits-for-email-messages) içinde olduğundan başarıyla dizinlenir. Ancak, bazı öğeler bu dizin oluşturma sınırlarını aşabilir ve kısmen dizine alınabilir. eBulma araması çalıştırdığınızda öğelerin arama için dizine alınamamalarının ve kısmen dizine alınan öğeler olarak döndürüllerinin diğer nedenleri şunlardır:
  
- Email iletilerde açılabilen ekli bir dosya vardır; kısmen dizine alınan e-posta öğelerinin en yaygın nedeni budur.
- E-posta iletisine çok fazla dosya iliştirildi.
- E-posta iletisine eklenmiş bir dosya çok büyük.
- Dosya türü dizin oluşturma için desteklenir, ancak belirli bir dosya için dizin oluşturma hatası oluştu.

Değişiklik gösterse de çoğu kuruluş müşterisi, topluca göre içeriğin %1'inden az, kısmen dizine alınan boyuta göre içeriğin %12'sinden daha az içeriğe sahiptir. Birim ile boyut arasındaki farkın nedeni, büyük dosyaların tamamen dizine alınamaz içerik içerme olasılığının daha yüksek olmasıdır.

İçerik aramasında öğeleri kısmen dizinleme hakkında daha fazla bilgi için bkz. [İçerik aramasında kısmen dizine alınan öğeleri araştırma](partially-indexed-items-in-content-search.md).
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Kısmen dizine alınan öğe sayısı bir arama için neden değişiyor?

Bir eBulma araması çalıştırdıktan sonra, arama yapılan konumlardaki kısmen dizine alınan öğelerin toplam sayısı ve boyutu, aramanın ayrıntılı istatistiklerinde görüntülenen arama sonucu istatistiklerinde listelenir. Bunların arama istatistiklerinde  *dizinlenmemiş öğeler olarak adlandırıldıklarına*  dikkat edin. Aşağıda, arama sonuçlarında döndürülen kısmen dizine alınan öğelerin sayısını etkileyecek birkaç şey vardır:
  
- Bir öğe kısmen dizine eklenmişse ve arama sorgusuyla eşleşiyorsa, hem arama sonucu öğelerinin sayısına (hem de boyutuna) ve kısmen dizine alınan öğelere dahil edilir. Ancak, aynı aramanın sonuçları dışarı aktarıldığında, öğe yalnızca arama sonuçları kümesine eklenir; kısmen dizinlenmiş bir öğe olarak dahil değildir.
- SharePoint ve OneDrive sitelerinde bulunan kısmen dizinlenmiş öğeler, aramanın ayrıntılı istatistiklerinde görüntülenen kısmen dizine eklenmiş öğelerin tahmininde yer *almaz* . Ancak, eBulma aramasının sonuçlarını dışarı aktardığınızda kısmen dizine alınan öğeler dışarı aktarılabilir. Örneğin, yalnızca sitelerde arama yaparsanız, kısmen dizine alınan tahmini öğe sayısı sıfır olur.
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Kuruluşunuzda kısmen dizine alınan öğelerin oranını hesaplama

Kuruluşunuzun kısmen dizinlenmiş öğelere maruz kalmasını anlamak için, tüm posta kutularındaki tüm içerik için arama çalıştırabilirsiniz (boş bir anahtar sözcük sorgusu kullanarak). Aşağıdaki örnekte, 1.629.904 (146,46 GB) tam dizine alınan öğe ve kısmen dizinlenmiş 10.025 (10,27 GB) öğe vardır.
  
![Kısmen dizine alınan öğeleri gösteren arama istatistikleri örneği.](../media/PartiallyIndexedItemsTest.png)
  
Aşağıdaki hesaplamaları kullanarak kısmen dizine alınan öğelerin yüzdesini belirleyebilirsiniz.
  
 **Kuruluşunuzda kısmen dizine alınan öğelerin oranını hesaplamak için:**

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

Önceki örnekteki arama sonuçları kullanıldığında, tüm posta kutuları öğelerinin %0,62'sinde kısmen dizin oluşturulur.
  
 **Kuruluşunuzda kısmen dizine alınan öğelerin boyutunun yüzdesini hesaplamak için:**

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 GB) x 100 = 7.0%`

Bu nedenle, önceki örnekte posta kutusu öğelerinin toplam boyutunun %7'sini kısmen dizine alınan öğeler oluşturur. Daha önce belirtildiği gibi çoğu kuruluş müşterisi, topluca göre içeriğin %1'inden az ve kısmen dizinlenmiş boyuta göre içeriğin %12'sinden daha az içeriğe sahiptir.

## <a name="working-with-partially-indexed-items"></a>Kısmen dizinlenmiş öğelerle çalışma

İlgili bilgileri içermediklerini doğrulamak için kısmen dizine alınan öğeleri incelemeniz gerektiğinde, kısmen dizine alınan öğeler hakkında bilgi içeren [bir içerik arama raporunu dışarı aktarabilirsiniz](export-a-content-search-report.md) . İçerik arama raporunu dışarı aktarırken, kısmen dizine alınan öğeler içeren dışarı aktarma seçeneklerinden birini seçtiğinizden emin olun.
  
![Kısmen dizine alınan öğeleri dışarı aktarmak için ikinci veya üçüncü seçeneği belirtin.](../media/PartiallyIndexedItemsExportOptions.png)
  
Bu seçeneklerden birini kullanarak eBulma arama sonuçlarını veya arama raporunu dışarı aktardığınızda, dışarı aktarma işlemi Unindexed Items.csv adlı bir rapor içerir. Bu rapor, ResultsLog.csv dosyasıyla aynı bilgilerin çoğunu içerir; Ancak, Unindexed Items.csv dosyası kısmen dizine alınmış öğelerle ilgili iki alan da içerir: **Hata Etiketleri** ve **Hata Özellikleri**. Bu alanlar, kısmen dizine alınan her öğe için dizin oluşturma hatası hakkında bilgi içerir. Bu iki alandaki bilgileri kullanmak, belirli bir dizin oluşturma hatasının araştırmanızı etkileyip etkilemediğini belirlemenize yardımcı olabilir. 

> [!NOTE]
> Unindexed Items.csv dosyası, **Hata Türü** ve **Hata İletisi** adlı alanları da içerir. Bunlar, **Hata Etiketleri** ve **Hata Özellikleri** alanlarındaki bilgilere benzer ancak daha az ayrıntılı bilgi içeren bilgiler içeren eski alanlardır. Bu eski alanları güvenle yoksayabilirsiniz.
  
## <a name="errors-related-to-partially-indexed-items"></a>Kısmen dizine alınan öğelerle ilgili hatalar

Hata etiketleri, hata ve dosya türü olan iki bilgi parçasından oluşur. Örneğin, bu hata/dosya türü çiftinde:

```text
 parseroutputsize_xls
```

 `parseroutputsize` hatadır ve `xls` hatanın oluştuğu dosyanın dosya türüdür. Dosya türünün tanınmadığı veya dosya türünün hataya uygulanmadığı durumlarda, dosya türünün yerine değeri `noformat` görürsünüz.
  
Aşağıda dizin oluşturma hatalarının listesi ve hatanın olası nedeninin açıklaması yer alır.
  
| Hata etiketi | Açıklama |
|:-----|:-----|
| `attachmentcount` <br/> |Bir e-posta iletisinde çok fazla ek vardı ve bu eklerden bazıları işlenmedi.  <br/> |
| `attachmentdepth` <br/> |İçerik seçici ve belge ayrıştırıcısı, diğer eklerin içine yerleştirilmiş çok fazla sayıda ek düzeyi buldu. Bu eklerden bazıları işlenmedi.  <br/> |
| `attachmentrms` <br/> |RMS korumalı olduğundan bir ekin kodu çözülemedi.  <br/> |
| `attachmentsize` <br/> |E-posta iletisine eklenmiş bir dosya çok büyük ve işlenemedi.  <br/> |
| `indexingtruncated` <br/> |İşlenen e-posta iletisi dizine yazılırken, dizine alınabilir özelliklerden biri çok büyük ve kesildi. Kesilen özellikler Hata Özellikleri alanında listelenir.  <br/> |
| `invalidunicode` <br/> |Geçerli Unicode olarak işlenemeyen bir e-posta iletisi metni içeriyordu. Bu öğe için dizin oluşturma tamamlanmamış olabilir.  <br/> |
| `parserencrypted` <br/> |Ek veya e-posta iletisinin içeriği şifrelenir ve Microsoft 365 içeriğin kodunu çözemedi.  <br/> |
| `parsererror` <br/> |Ayrıştırma sırasında bilinmeyen bir hata oluştu. Bu durum genellikle bir yazılım hatasından veya hizmet kilitlenmesinden kaynaklar.  <br/> |
| `parserinputsize` <br/> |Ek ayrıştırıcının işleyemeyecek kadar büyük olduğunu ve bu ekin ayrıştırılması gerçekleşmedi veya tamamlanmadı.  <br/> |
| `parsermalformed` <br/> |Ek yanlış biçimlendirilmiş ve ayrıştırıcı tarafından işlenemedi. Bu sonuç eski dosya biçimlerinden, uyumsuz yazılımlar tarafından oluşturulan dosyalardan veya iddia edilenden başka bir şeymiş gibi davranan virüslerden kaynaklanabilir.  <br/> |
| `parseroutputsize` <br/> |Ek ayrıştırma çıktısı çok büyük ve kesilmesi gerekiyordu.  <br/> |
| `parserunknowntype` <br/> |Ekte Microsoft 365'in algılayamadıdığı bir dosya türü vardı.  <br/> |
| `parserunsupportedtype` <br/> |Ekin Office 365 algılayabildiği bir dosya türü vardı, ancak bu dosya türünün ayrıştırılması desteklenmiyor.  <br/> |
| `propertytoobig` <br/> |Exchange Store'daki bir e-posta özelliğinin değeri alınamayacak kadar büyük ve ileti işlenemedi. Bu genellikle yalnızca bir e-posta iletisinin gövde özelliğine olur.  <br/> |
| `retrieverrms` <br/> |İçerik alıcı, RMS korumalı bir iletinin kodunu çözemedi.  <br/> |
| `wordbreakertruncated` <br/> |Dizin oluşturma sırasında belgede çok fazla sözcük tanımlandı. Sınıra ulaşıldığında özelliğin işlenmesi durduruldu ve özellik kesildi.  <br/> |

Hata alanları, Hata Etiketleri alanında listelenen işleme hatasından hangi alanların etkilendiğini açıklar. veya `participants`gibi `subject` bir özelliği arıyorsanız, iletinin gövdesindeki hatalar aramanızın sonuçlarını etkilemez. Bu, tam olarak hangi kısmen dizine alınan öğeleri daha fazla araştırmanız gerekebileceğini belirlerken yararlı olabilir.