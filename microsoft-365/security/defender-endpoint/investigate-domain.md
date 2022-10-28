---
title: Uç Nokta için Microsoft Defender uyarısıyla ilişkili etki alanlarını ve URL'leri araştırma
description: Cihazların ve sunucuların kötü amaçlı etki alanlarıyla iletişim kurup kurmadığını görmek için araştırma seçeneklerini kullanın.
keywords: etki alanını, etki alanını, kötü amaçlı etki alanını, Uç Nokta için Microsoft Defender, uyarıyı, URL'yi araştırma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.date: 04/24/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7f218836b3b4fe54533fae623217a7781852e2bf
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769501"
---
# <a name="investigate-domains-and-urls-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Uç Nokta için Microsoft Defender uyarısıyla ilişkili etki alanlarını ve URL'leri araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

Kurumsal ağınızdaki cihazların ve sunucuların bilinen bir kötü amaçlı etki alanıyla iletişim kurup kurmadığını görmek için bir etki alanını araştırın.

Arama özelliğini kullanarak, olay deneyiminden (kanıt sekmesinde veya uyarı hikayesinden) veya **Cihaz zaman çizelgesindeki** URL veya etki alanı bağlantısına tıklayarak bir URL'yi veya etki alanını araştırabilirsiniz.

URL ve etki alanı görünümünde aşağıdaki bölümlerde yer alan bilgileri görebilirsiniz:

- Etki alanı ayrıntıları, kayıt şirketi iletişim bilgileri

- Microsoft kararı

- Bu URL veya etki alanıyla ilgili olaylar

- Kuruluştaki URL veya etki alanının yaygınlığı

- URL veya etki alanı ile en son gözlemlenen cihazlar

 ![Yeni URL & etki alanı sayfasının genel bakış bölümü bir bakışta.](media/domain-url-overview.png)

## <a name="domain-entity"></a>Etki alanı varlığı

URL sayfasındaki veya yan paneldeki etki alanı ayrıntılarından etki alanı sayfasına dönebilirsiniz, yalnızca **Etki alanı sayfasını görüntüle** bağlantısına tıklayın. Etki alanı varlığı, URL'lerden gelen tüm verilerin FQDN (Tam etki alanı adı) ile bir toplamasını gösterir. Örneğin, ile iletişim halinde `sub.domain.tld/path1`bir cihaz gözlemlenirse ve ile `sub.domain.tld/path2`iletişim halinde başka bir cihaz gözlemlenirse, yukarıdakilerin her URL'si bir cihaz gözlemi gösterir ve etki alanı iki cihaz gözlemini gösterir. Bu durumda, ile iletişim kuran bir cihaz bu etki alanı sayfasıyla değil, ile `othersub.domain.tld/path` bağıntı kurmaz `othersub.domain.tld`.

## <a name="url-and-domain-overview"></a>URL ve Etki Alanına genel bakış

URL dünya çapında bölümünde URL, Whois'teki diğer ayrıntıların bağlantısı, ilgili açık olayların sayısı ve etkin uyarı sayısı listelenir.

### <a name="url-summary-details"></a>URL özeti ayrıntıları

Sorgu parametreleri ve uygulama düzeyi protokolüyle özgün URL'yi (mevcut URL bilgileri) görüntüler. Bunun altında kayıt tarihi, değiştirme tarihi ve kayıt şirketi iletişim bilgileri gibi tüm etki alanı ayrıntılarını bulabilirsiniz.

URL veya etki alanı ve cihaz yaygınlığı bölümü için Microsoft kararı. Bu alanda, son 30 gün içinde URL veya etki alanıyla iletişim kuran cihaz sayısını görebilir ve cihaz zaman çizelgesindeki ilk veya son olaya hemen özetleyebilirsiniz. İlk erişimi araştırmak veya ortamınızda hala kötü amaçlı bir etkinlik olup olmadığını araştırmak için.

### <a name="incidents-and-alerts"></a>Olaylar ve uyarılar

Olay ve uyarılar bölümünde, son 180 gün içindeki olaylardaki tüm etkin uyarıların çubuk grafiği görüntülenir.

### <a name="microsoft-verdict"></a>Microsoft Kararı

Microsoft karar bölümünde, Microsoft TI kitaplığındaki URL veya etki alanının kararı görüntülenir. URL'nin veya etki alanının zaten kimlik avı veya kötü amaçlı varlık olarak bilinip bilinmediğini gösterir.

### <a name="prevalence"></a>Prevalans

Yaygınlık bölümü, url veya etki alanıyla belirli bir süre içinde iletişim kuran farklı cihazların sayısını gösteren ve eğilim grafiği gibi son 30 gün içinde kuruluş içindeki URL'nin yaygınlığıyla ilgili ayrıntıları sağlar. Son 30 gün içinde URL ile iletişim kuran ilk ve son cihaz gözlemlerinin ayrıntılarını bulabilirseniz, burada kimlik avı bağlantısından ilk erişimi araştırmak için hemen cihaz zaman çizelgesine dönebilirsiniz veya ortamınızda hala kötü amaçlı bir iletişim varsa.

## <a name="incident-and-alerts"></a>Olay ve uyarılar

![Olay ve uyarılar sekmesi, URL veya etki alanıyla ilişkili olayların listesini sağlar.](media/domain-incidents.png)

Olay ve uyarılar sekmesi, URL veya etki alanıyla ilişkili olayların listesini sağlar. Burada gösterilen tablo Olay kuyruğu ekranında görünen olayların filtrelenmiş bir sürümüdür ve yalnızca URL veya etki alanıyla ilişkili olayları, önem derecelerini, etkilenen varlıkları ve daha fazlasını gösterir.

Olaylar ve uyarılar sekmesi, sütun üst bilgilerinin üstündeki eylem menüsünde **Sütunları özelleştir'i** seçerek daha fazla veya daha az bilgi gösterecek şekilde ayarlanabilir. Aynı menüde sayfa başına öğe seçilerek görüntülenen öğe sayısı da ayarlanabilir.

## <a name="devices"></a>Aygıtları

![Cihaz sekmesi, belirli bir süre boyunca URL veya etki alanıyla iletişim kuran farklı cihazların sayısını görüntüler.](media/domain-device-overview.png)

Cihazlar sekmesi, belirli bir URL veya etki alanı için gözlemlenen tüm cihazların kronolojik görünümünü sağlar. Bu sekme bir eğilim grafiği ve risk düzeyi, etki alanı ve daha fazlası gibi cihaz ayrıntılarını listeleyen özelleştirilebilir bir tablo içerir. Bunun ötesinde, cihazın URL veya etki alanıyla etkileşime geçtiği ilk ve son olay zamanlarını ve bu olayın eylem türünü görebilirsiniz. Cihaz adının yanındaki menüyü kullanarak, bu URL'yi veya etki alanını içeren olaydan önce veya sonra ne olduğunu daha fazla araştırmak için cihaz zaman çizelgesine hızla dönebilirsiniz.

Varsayılan süre son 30 gün olsa da, kartın köşesindeki açılan menüden bunu özelleştirebilirsiniz. Kullanılabilir en kısa aralık, son gündeki yaygınlık için, en uzun aralık ise son altı ayın üzerindedir.

Tablonun üstündeki dışarı aktar düğmesini kullanarak, daha fazla araştırma ve raporlama için tüm verileri bir .csv dosyasına (ilk ve son olay zamanı ve eylem türü dahil) dışarı aktarabilirsiniz.

### <a name="investigate-a-url-or-domain"></a>URL'yi veya etki alanını araştırma

1. **Arama çubuğu** açılan menüsünden **URL'yi** seçin.

2. **Arama** alanına URL'yi girin.

3. Arama simgesine tıklayın veya **Enter tuşuna** basın. URL ile ilgili ayrıntılar görüntülenir.

   > [!NOTE]
   > Arama sonuçları yalnızca kuruluştaki cihazlardan gelen iletişimlerde gözlemlenen URL'ler için döndürülür.

4. Arama ölçütlerini tanımlamak için arama filtrelerini kullanın. Zaman çizelgesi arama kutusunu kullanarak kuruluştaki url ile iletişim kurarak gözlemlenen tüm cihazların görüntülenen sonuçlarını, iletişimle ilişkili dosyayı ve gözlemlenen son tarihi de filtreleyebilirsiniz.

5. Cihaz adlarından herhangi birine tıkladığınızda bu cihazın görünümüne gidebilirsiniz; burada bildirilen uyarıları, davranışları ve olayları araştırmaya devam edebilirsiniz.

## <a name="related-articles"></a>İlgili makaleler

- [Uç Nokta için Microsoft Defender Uyarıları kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
- [Uç Nokta için Microsoft Defender uyarılarını yönetme](manage-alerts.md)
- [Uç Nokta için Microsoft Defender uyarılarını araştırma](investigate-alerts.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili bir dosyayı araştırma](investigate-files.md)
- [Uç Nokta için Microsoft Defender Cihazlar listesindeki cihazları araştırma](investigate-machines.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili IP adresini araştırma](investigate-ip.md)
- [Uç Nokta için Microsoft Defender'de kullanıcı hesabını araştırma](investigate-user.md)
