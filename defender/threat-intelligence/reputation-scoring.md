---
title: Microsoft Defender Tehdit Analizi (Defender TI) Saygınlık Puanlaması
description: Bu genel bakış makalesinde, Microsoft Defender Tehdit Analizi (Defender TI) saygınlık puanlama özelliği hakkında bilgi edinin.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: bdb1acd3ca60042978710b8e59f28865530213ae
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68339718"
---
# <a name="reputation-scoring"></a>İtibar puanlaması

Microsoft Defender Tehdit Analizi (Defender TI), herhangi bir Ana Bilgisayar, Etki Alanı veya IP Adresi için özel itibar puanları sağlar. Bu puan, bilinen veya bilinmeyen bir varlığın itibarını doğrulayarak kullanıcıların kötü amaçlı veya şüpheli altyapıyla ilgili algılanan tüm bağları hızla anlamasına yardımcı olur. Platform, bu varlıkların etkinliği hakkında hızlı bilgiler (örneğin, İlk ve Son Görülen zaman damgaları, ASN, ilişkili altyapı) ve uygun olduğunda saygınlık puanını etkileyen kuralların bir listesi sağlar.

Saygınlık verileri, kendi saldırı yüzeyinizin güvenilirliğini anlamak için önemlidir ve araştırmalarda görünen bilinmeyen konakları, etki alanlarını veya IP adreslerini değerlendirirken de yararlıdır. Bu puanlar, daha önce varlığı etkilemiş kötü amaçlı veya şüpheli etkinlikleri veya dikkate alınması gereken diğer bilinen güvenlik ihlali göstergelerini ortaya çıkarır.

![Saygınlık Kenarı Ekran Görüntüsü](media/reputationEdgeScreenshot.png)
## <a name="understanding-reputation-scores"></a>Saygınlık puanlarını anlama

Saygınlık Puanları, bir varlıkla ilişkili riski hızla ölçmek için tasarlanmış bir dizi algoritma tarafından belirlenir. Gezinme altyapımızdan ve dış kaynaklardan toplanan IP bilgilerinden yararlanarak mülkiyet verilerimizi temel alan İtibar Puanlarını geliştiririz.

![İtibar Özet Kartı](media/reputationSummaryCard.png)

## <a name="detection-methods"></a>Algılama yöntemleri
Saygınlık Puanları, engellenen varlıklarla bilinen ilişkilendirmeler ve riski değerlendirmek için kullanılan bir dizi makine öğrenmesi kuralı da dahil olmak üzere bir dizi faktör tarafından belirlenir.

## <a name="scoring-brackets"></a>Puanlama köşeli ayraçları
Saygınlık Puanları, 0 ile 100 arasında bir aralığa sahip sayısal puan olarak görüntülenir. Puanı "0" olan bir varlığın şüpheli etkinlikle veya bilinen risk göstergeleriyle bilinen bir ilişkisi yoktur; "100" puanı varlığın kötü amaçlı olduğunu gösterir. Konaklar, Etki Alanları ve IP Adresleri, sayısal puanlarına bağlı olarak aşağıdaki kategorilerde gruplandırılır:

|     Puan             |     Kategori              |     Açıklama                                                                                                                                                                          |
|-----------------------|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     75+               |     Kötü amaçlı             |     Varlık, engellenenler listemizde görünen ve şüpheli etkinliği algılayan makine öğrenmesi kurallarıyla eşleşen bilinen kötü amaçlı altyapıyla ilişkilendirmeleri onayladı.      |
|     50   – 74         |     Şüpheli            |     Varlık büyük olasılıkla üç veya daha fazla makine öğrenmesi kuralıyla eşleşmelere göre şüpheli altyapıyla ilişkilendirilir.                                                           |
|     25   – 49         |     Nötr               |     Varlık en az iki makine öğrenmesi kuralıyla eşleşir.                                                                                                                            |
|     0   – 24          |     Bilinmiyor (Yeşil)     |     Puan "Bilinmiyor" ve yeşil ise varlık en az bir eşleşen kural döndürmüştür.                                                                                          |
|     0   – 24          |     Bilinmiyor (Gri)      |     Puan "Bilinmiyor" ve gri ise varlık herhangi bir kural eşleşmesi döndürmemiştir.                                                                                                |  

## <a name="detection-rules"></a>Algılama kuralları

Saygınlık puanları, bir analistin etki alanının veya adresin göreli kalitesini belirlemek için başvurabileceği birçok faktöre dayanır. Bu faktörler, itibar puanlarını oluşturan makine öğrenmesi kurallarına yansıtılır. Örneğin, ".xyz" veya ".cc" üst düzey etki alanları (TLD) genellikle ".com" veya ".org" TD'lerinden daha şüphelidir. Düşük maliyetli veya ücretsiz bir barındırma sağlayıcısı tarafından barındırılan bir ASN (Otonom Sistem Numarası), otomatik olarak imzalanan ssl sertifikası gibi kötü amaçlı etkinliklerle ilişkilendirilebilir. Bu saygınlık modeli, bir varlığın genel itibarını puanlama amacıyla bu özelliklerin hem kötü amaçlı hem de zararsız göstergeler arasındaki göreli oluşumlarına bakılarak geliştirilmiştir.

Bir konağın, etki alanının veya IP adresinin şüpheliliğini belirlemek için kullanılan kural örnekleri için lütfen aşağıdaki listeye bakın. Bu listenin kapsamlı olmadığını ve sürekli değiştiğini lütfen unutmayın; algılama mantığımız ve sonuç özelliklerimiz, gelişen tehdit ortamını yansıttıkça dinamiktir. Bu nedenle, bir varlığın itibarını değerlendirmek için kullanılan makine öğrenmesi kurallarının kapsamlı bir listesini yayımlamayız.

Aşağıdaki örnek saygınlık puanlama kurallarına bakın:

|     Kural Adı                    |     Açıklama                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------|
|     SSL-Certificate Self-Signed    |     Otomatik olarak imzalanan sertifikalar kötü amaçlı davranışa işaret edebilir                                         |
|     Kötü Amaçlı Olarak Etiketlenmiş            |     Kuruluşunuzdaki bir üye tarafından kötü amaçlı olarak etiketlendi                                         |
|     Gözlemlenen web bileşenleri        |     Gözlemlenen web bileşeni sayısı kötü amaçlılığa işaret edebilir                                 |
|     Ad sunucusu                    |     Etki alanı, kötü amaçlı altyapı tarafından kullanılma olasılığı daha yüksek olan bir ad sunucusu kullanıyor         |
|     Kayıt                      |     Bu kayıt şirketine kayıtlı etki alanlarının kötü amaçlı olma olasılığı daha yüksektir                           |
|     Kayıt olan e-posta sağlayıcısı      |     Etki alanı, kötü amaçlı etki alanlarını kaydetme olasılığı daha yüksek olan bir e-posta sağlayıcısına kaydedilir    |

Bir varlığın itibarı hakkında doğru bir değerlendirme yapmak için bu faktörlerin bütünsel olarak değerlendirilmesi gerektiğini unutmayın. Herhangi bir gösterge yerine belirli gösterge birleşimi, bir varlığın kötü amaçlı mı yoksa şüpheli mi olacağını tahmin edebilir.

## <a name="severity"></a>Önem derecesi

Makine öğrenmesi algılama sistemi için kurallar oluşturulurken, buna bir önem derecesi uygulanır. Her kurala, kuralla ilişkili risk düzeyine bağlı olarak "Yüksek", "Orta" veya "Düşük" önem derecesi atanır.

## <a name="use-cases"></a>Kullanım örnekleri

### <a name="incident-triage-response-and-threat-hunting"></a>Olay önceliklendirme, yanıt ve tehdit avcılığı
Defender TI'nin saygınlık puanı, sınıflandırması, kuralları ve kuralların açıklaması, bir IP adresinin veya etki alanı göstergesinin iyi, şüpheli veya kötü amaçlı olup olmadığını hızla değerlendirmek için kullanılabilir. Diğer zamanlarda, göstergenin iyi veya kötü olup olmadığını çıkarsamak için bir IP adresi veya etki alanıyla ilişkili yeterli altyapıyı gözlemlememiş olabiliriz. Bir göstergenin bilinmeyen veya nötr sınıflandırması varsa, kullanıcıların göstergenin iyi veya kötü olup olmadığını belirlemek için veri kümelerimizi gözden geçirerek daha derin bir araştırma yapmaları teşvik edilir. Bir göstergenin itibarı bir makale ilişkilendirmesi içeriyorsa, kullanıcıların göstergenin olası bir tehdit aktörünün kampanyasına nasıl bağlı olduğu, hangi sektörleri veya ulusları hedefledikleri, ilişkili TTP'ler olduğu ve olayın yanıt ve tehdit avcılığı çalışmalarının kapsamını genişletmek için diğer ilgili güvenlik ihlal göstergelerini belirlemesi hakkında daha fazla bilgi edinmek için bu listelenen makaleyi gözden geçirmeleri teşvik edilir.

### <a name="intelligence-gathering"></a>Zeka toplama

İlişkili tüm makaleler analistin siber tehdit bilgileri ekibiyle paylaşılabilir, böylece kuruluşunu kimlerin hedeflediklerini daha net bir şekilde anlayabilirler.

## <a name="next-steps"></a>Sonraki adımlar
Daha fazla bilgi için bkz. [Çözümleyici içgörüleri](analyst-insights.md).
