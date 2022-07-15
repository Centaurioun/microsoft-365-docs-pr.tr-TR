---
title: İleti temsilcisi
author: samanro
ms.author: samanro
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: acolonna
description: Dışarıda durumu veya Rahatsız Etmeyin durumu olan bir kullanıcının, durum iletisinde başka bir kullanıcıyı açıkça temsilci olarak nasıl ayarlayabileceğini öğrenin.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 190b1f8bfdcf06c124163d97ecf77465f66ad67c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824743"
---
# <a name="message-delegation"></a>İleti temsilcisi

Kullanıcı zaten durumunu açıkça Dışarıda veya Rahatsız Etmeyin olarak ayarlayabilir ve özel metin sağlayabilir. İleti temsilcisi özelliği aşağıdaki gibi çalışır:

1. Bir kullanıcı @username metin durumu iletisinin bir bölümünde başka bir kullanıcıdan bahseder ve bu kullanıcı uygun olmasa da, bu kullanıcıyla iletişim kurmak isteyen kişilerin söz @username kullanıcıyla iletişim kurmasını önerir.
2. Temsilci olarak atanan kişiye temsilci olarak aday gösterildiği bildirilir.
3. İlk kullanıcıyla iletişim kurmaya çalışan biri, daha sonra aday gösterilen temsilcinin üzerine gelebilir ve bunun yerine temsilciye kolayca ileti iletebilir.  

Bu, istemcide kullanıcı tarafından başlatılan bir işlemdir ve özelliği etkinleştirmek için Yönetici katılımı gerekmez. 

## <a name="delegation-use-scenario-in-healthcare"></a>Healthcare'de temsilci kullanımı senaryosu

*Temsilci ayarlamadan kullanım örneği:*  Dr. Franco Piccio radyoloji departmanında aramada. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri, Dr. Lena Ehrle, o yokken onu korumasını istiyor. Çağrıyı yapan dr. Ehrle'e, çağrıyı yapan acil mesajları ve ping'leri dinleyen ve mevcut sorumluluklarına ek olarak Dr. Piccio adına onlara yanıt veren Dr. Ehrle'ye resmi olmayan bir şekilde teslim eder. Ekipte yer alan diğer kişiler, resmi olmayan temsilin gerçekleştiğini fark etmeyebilir ve bir hastanın bakımıyla ilgili karışıklıklar meydana gelebilir.

*Temsilci ayarlamayla ilgili kullanım örneği:* Dr. Franco Piccio radyoloji departmanında çağrıda. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri olan Dr. Lena Ehrle'den, kendisi yokken onu korumasını istiyor. Özel durum iletisini şu şekilde değiştirir: "Önümüzdeki birkaç saat için kullanılamıyorum. Acil durumlar için lütfen @DrEhrle ile iletişime geçin."  Ekipteki diğer kişiler, Dr. Piccio'ya başvurmaya çalışırken temsilcinin gerçekleştiğini fark ettiler, bu arada Dr. Ehrle ile iletişime geçmeyi biliyorlar. Hastanın bakımıyla çok az karışıklığa yol açıyor.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Birlikte kullanım modlarının Teams istemcisindeki kullanıcı durumu üzerindeki etkisi

Yöneticiler, durum notlarının ve temsilci bahsetme davranışlarının kısmen kullanıcının birlikte kullanım moduna bağlı olduğunu bilmeli. Bu matris olasılıkları gösterir:

|Co-Existence Modu | Beklenen Davranış|
|---|---|
|TeamsOnly |Kullanıcılar yalnızca Teams'den not ayarlayabilir. <br> Kullanıcının Teams notu Teams & SfB'de görünür. |
|Adaları | Kullanıcının Teams'de ayarlanan notları yalnızca Teams'de görünür. <br> SfB'de kullanıcının not kümesi yalnızca SfB'de görünür |
|SfB* modları | Kullanıcılar yalnızca SfB'den bir not ayarlayabilir. <br> Kullanıcının SfB notu SfB & Teams'de görünür.  |
|||

Bir kullanıcı Teams'de yalnızca modu TeamsOnly veya Islands ise bir not ayarlayabilir.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Skype Kurumsal'de ayarlanan notları görüntüleme
  
Skype Kurumsal'dan bir not ayarlandığını gösteren görsel bir gösterge yoktur.

Skype Kurumsal durum notlarında karakter sınırını zorlamaz. Microsoft Teams, Skype Kurumsal not kümesinin yalnızca ilk 280 karakterini görüntüler. Notun sonundaki üç nokta (...) noktalama işlemini gösterir.
  
Skype Kurumsal notlar için süre sonu sürelerini desteklemez.

Bir kullanıcı TeamsOnly moduna yükseltildiğinde notların Skype Kurumsal Teams'e geçirilmesi desteklenmez.

## <a name="related-topics"></a>İlgili konular

[Skype Kurumsal ile birlikte bulunma](/microsoftteams/coexistence-chat-calls-presence)
