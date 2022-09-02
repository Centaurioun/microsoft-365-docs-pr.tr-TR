---
title: Uç Nokta için Microsoft Defender etki alanlarını araştırma
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
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
ms.openlocfilehash: 9565d80da339722ba070cb4525f0f7339c1ff6ce
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520983"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Uç Nokta için Microsoft Defender uyarısıyla ilişkili bir etki alanını araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

Kurumsal ağınızdaki cihazların ve sunucuların bilinen bir kötü amaçlı etki alanıyla iletişim kurup kurmadığını görmek için bir etki alanını araştırın.

Arama özelliğini kullanarak veya **Cihaz zaman çizelgesinden** bir etki alanı bağlantısına tıklayarak bir etki alanını araştırabilirsiniz.

URL görünümünde aşağıdaki bölümlerde yer alan bilgileri görebilirsiniz:

- URL ayrıntıları, Kişiler, Ad Sunucuları
- Bu URL ile ilgili uyarılar 
- Kuruluş url'si
- URL ile en son gözlemlenen cihazlar

## <a name="url-worldwide"></a>Dünya çapında URL

**URL Worldwide bölümünde URL**, Whois'deki diğer ayrıntıların bağlantısı, ilgili açık olayların sayısı ve etkin uyarı sayısı listelenir.

## <a name="incident"></a>Olay

**Olay** kartı, son 180 gün içindeki olaylardaki tüm etkin uyarıların çubuk grafiğini görüntüler.

## <a name="prevalence"></a>Prevalans

**Yaygınlık** kartı, belirli bir süre boyunca URL'nin kuruluş içindeki yaygınlığı hakkında ayrıntılı bilgi sağlar.

Varsayılan süre son 30 gün olsa da, kartın köşesindeki aşağı dönük oku seçerek aralığı özelleştirebilirsiniz. Kullanılabilir en kısa aralık son gündeki yaygınlık için, en uzun aralık ise son 6 ay içindedir.

## <a name="alerts"></a>Uyarılar

**Uyarılar** sekmesi, URL ile ilişkili uyarıların listesini sağlar. Burada gösterilen tablo Uyarı kuyruğu ekranında görünen uyarıların filtrelenmiş bir sürümüdür ve yalnızca etki alanıyla ilişkili uyarıları, önem derecesini, durumunu, ilişkili olayı, sınıflandırmayı, araştırma durumunu ve daha fazlasını gösterir.

Uyarılar sekmesi, sütun üst bilgilerinin üstündeki eylem menüsünde **Sütunları özelleştir'i** seçerek daha fazla veya daha az bilgi gösterecek şekilde ayarlanabilir. Aynı menüde **sayfa başına öğe** seçilerek görüntülenen öğe sayısı da ayarlanabilir.

## <a name="observed-in-organization"></a>Kuruluşta gözlemlenen

**Kuruluşta gözlemlenen sekmesi, URL'de** gözlemlenen olaylar ve ilişkili uyarılar hakkında kronolojik bir görünüm sağlar. Bu sekmede zaman çizelgesi ve zaman, cihaz gibi olay ayrıntılarının listelendiği özelleştirilebilir bir tablo ve neler olduğuyla ilgili kısa bir açıklama yer alır. 

Tarihleri tablo üst bilgilerinin üstündeki metin alanlarına girerek farklı zaman aralıklarındaki olayları görüntüleyebilirsiniz. Zaman çizelgesinin farklı alanlarını seçerek zaman aralığını da özelleştirebilirsiniz.

**Etki alanını araştırma:**

1. **Arama çubuğu** açılan menüsünden **URL'yi** seçin.
2. **Arama** alanına URL'yi girin.
3. Arama simgesine tıklayın veya **Enter tuşuna** basın. URL ile ilgili ayrıntılar görüntülenir. Not: Arama sonuçları yalnızca kuruluştaki cihazlardan gelen iletişimlerde gözlemlenen URL'ler için döndürülür.
4. Arama ölçütlerini tanımlamak için arama filtrelerini kullanın. Zaman çizelgesi arama kutusunu kullanarak kuruluştaki url ile iletişim kurarak gözlemlenen tüm cihazların görüntülenen sonuçlarını, iletişimle ilişkili dosyayı ve gözlemlenen son tarihi de filtreleyebilirsiniz.
5. Cihaz adlarından herhangi birine tıkladığınızda bu cihazın görünümüne gidersiniz; burada bildirilen uyarıları, davranışları ve olayları araştırmaya devam edebilirsiniz.

## <a name="related-topics"></a>İlgili konular
- [Uç Nokta için Microsoft Defender Uyarıları kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
- [Uç Nokta için Microsoft Defender uyarılarını yönetme](manage-alerts.md)
- [Uç Nokta için Microsoft Defender uyarılarını araştırma](investigate-alerts.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili bir dosyayı araştırma](investigate-files.md)
- [Uç Nokta için Microsoft Defender Cihazlar listesindeki cihazları araştırma](investigate-machines.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili IP adresini araştırma](investigate-ip.md)
- [Uç Nokta için Microsoft Defender'de kullanıcı hesabını araştırma](investigate-user.md)
