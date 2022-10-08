---
title: Microsoft 365 Defender'de avcılık için destekli modda desteklenen veri türleri ve filtreler
description: Microsoft 365 Defender'da gelişmiş avcılıkta farklı destekli mod özelliklerini kullanarak sorgunuzu geliştirin.
keywords: destekli mod, gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, Kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-m365-defender
- tier2
ms.topic: conceptual
ms.openlocfilehash: 5ad8b108ddd6de6734c9fdccfa79aeac0e7d13ef
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051882"
---
# <a name="refine-your-query-in-guided-mode"></a>Sorgunuzu kılavuzlu modda daraltma 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.
## <a name="use-different-data-types"></a>Farklı veri türleri kullanma

Kılavuzlu modda gelişmiş avcılık, sorgunuzda ince ayar yapmak için kullanabileceğiniz çeşitli veri türlerini destekler.

- Numara<br>
![Üçüncü koşul olarak sayıların ekran görüntüsü](../../media/guided-hunting/data-numbers.png)

- Dize<br>
![Üçüncü koşul olarak dizelerin ekran görüntüsü](../../media/guided-hunting/data-strings.png)

   Serbest metin kutusuna değeri yazın ve eklemek için **Enter tuşuna** basın. Değerler arasındaki sınırlayıcının **Enter** olduğunu unutmayın.<br>

   ![Kullanabileceğiniz farklı koşulları gösteren ekran görüntüsü](../../media/guided-hunting/data-strings-2.png)

- Boole<br>
![Üçüncü koşul olarak Boole değerlerinin ekran görüntüsü](../../media/guided-hunting/boolean.png)


- Datetime<br>
![Üçüncü koşul olarak tarih saat değerlerinin ekran görüntüsü](../../media/guided-hunting/data-datetime.png)


- Kapalı liste - Aradığınız değeri tam olarak hatırlamanız gerekmez. Çoklu seçimi destekleyen önerilen kapalı listeden kolayca seçim yapabilirsiniz.<br>
![Üçüncü koşul olarak kullanılan kapalı listenin ekran görüntüsü](../../media/guided-hunting/data-closed.png)


## <a name="use-subgroups"></a>Alt grupları kullanma
**Alt grup ekle'ye** tıklayarak koşul grupları oluşturabilirsiniz:

![Alt grup ekle düğmesini vurgulayan ekran görüntüsü](../../media/guided-hunting/subgroup-1.png)

![Alt grupların kullanımını gösteren ekran görüntüsü](../../media/guided-hunting/subgroup-2.png)

## <a name="use-smart-auto-complete-for-search"></a>Arama için akıllı otomatik tamamlama kullanma
Cihazlarda ve kullanıcı hesaplarında arama için akıllı otomatik tamamlama desteklenir. Cihaz kimliğini, tam cihaz adını veya kullanıcı hesabı adını hatırlamanız gerekmez. Aradığınız cihazın veya kullanıcının ilk birkaç karakterini yazmaya başlayabilirsiniz ve ihtiyacınız olanı seçebileceğiniz önerilen bir liste görüntülenir:

![Akıllı otomatik tamamlama desteğini gösteren ekran görüntüsü](../../media/guided-hunting/smart-auto.png)

## <a name="use-eventtype"></a>Kullanın `EventType`
Hatta tüm başarısız oturum açma işlemleri, dosya değişikliği olayları veya başarılı ağ bağlantıları gibi belirli olay türlerini, uygun olduğu herhangi bir bölümde **EventType** filtresini kullanarak da arayabilirsiniz.

Örneğin, kayıt defteri değeri silmelerini arayabilen bir koşul eklemek istiyorsanız **, Kayıt Defteri Olayları** bölümüne gidip **EventType'ı** seçebilirsiniz.

![Çeşitli EventType'ların ekran görüntüsü](../../media/guided-hunting/hunt-specific-events-1.png)

Kayıt Defteri Olayları'nın altında EventType'ı seçtiğinizde, avladığınız olay olan **RegistryValueDeleted** dahil olmak üzere farklı kayıt defteri olayları arasından seçim yapabilirsiniz.

![EventType RegistryValueDeleted ekran görüntüsü](../../media/guided-hunting/hunt-specific-events-2.png)

>[!NOTE] 
>`EventType` , gelişmiş mod kullanıcılarının `ActionType` daha aşina olabileceği veri şemasının eşdeğeridir.

## <a name="test-your-query-with-a-smaller-sample-size"></a>Sorgunuzu daha küçük bir örnek boyutuyla test edin
Sorgunuz üzerinde çalışmaya devam ediyorsanız ve performansını ve bazı örnek sonuçları hızla görmek istiyorsanız, **Örnek boyut** açılan menüsünden daha küçük bir küme seçerek kayıt sayısını döndürecek şekilde ayarlayın. 
 
![Örnek boyutu açılan menüsünün ekran görüntüsü](../../media/guided-hunting/smaller-sample.png)

Örnek boyutu varsayılan olarak 10.000 sonuç olarak ayarlanır. Bu, avlanmada döndürülebilecek maksimum kayıt sayısıdır. Bununla birlikte, sorgunuzu hızlı bir şekilde test etmek için örnek boyutunun 10 veya 100'e düşürülmesi önerilir. Bu işlem sorguyu geliştirmeye devam ederken daha az kaynak tüketir.

Ardından, sorgunuzu sonlandırdıktan ve tehdit avcılığı etkinliğiniz için tüm ilgili sonuçları almak için kullanmaya hazır olduğunuzda, örnek boyutunun en fazla 10 bin olarak ayarlandığından emin olun.

## <a name="switch-to-advanced-mode-after-building-a-query"></a>Sorguyu derledikten sonra gelişmiş moda geçme
Seçtiğiniz koşullar tarafından oluşturulan KQL sorgusunu görüntülemek için **KQL'de Düzenle'ye** tıklayabilirsiniz. KQL'de düzenleme, ilgili KQL sorgusuyla birlikte gelişmiş modda yeni bir sekme açar:

![KQL'de Düzenle düğmesini vurgulayan ekran görüntüsü](../../media/guided-hunting/switch-to-advanced.png)

![Kılavuzludan gelişmişe aynı sorguyu gösteren ekran görüntüsü](../../media/guided-hunting/switch-to-advanced-2.png)

Yukarıdaki örnekte, seçilen görünüm Tümü'dür, bu nedenle KQL sorgusunun ad ve SHA256 dosya özelliklerine sahip tüm tablolarda ve bu özellikleri kapsayan tüm ilgili sütunlarda arama gerçekleştirdiğini görebilirsiniz. 

Görünümü **e-postalar & işbirliği** olarak değiştirirseniz, sorgu şu şekilde daraltılır:

![Aynı sorguyu kılavuzludan gelişmişe ancak sınırlı etki alanıyla gösteren ekran görüntüsü](../../media/guided-hunting/switch-to-advanced-3.png)

## <a name="see-also"></a>Ayrıca bkz.
 - [Gelişmiş tehdit avcılığı kotaları ve kullanım parametreleri](advanced-hunting-limits.md)
 - [Doğru ayarlarla gelişmiş avcılık kapsamını genişletme](advanced-hunting-extend-data.md)