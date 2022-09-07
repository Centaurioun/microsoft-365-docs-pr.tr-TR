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
ms.openlocfilehash: e09883e65cf8d4036aff8933d8cc5d25b9d319df
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2022
ms.locfileid: "67614137"
---
# <a name="message-delegation"></a>İleti temsilcisi

Microsoft Teams'deki kullanıcılar durumlarını Dışarıda veya Rahatsız Etmeyin olarak ayarlayabilir ve özel bir metin durumu iletisi ekleyebilir. Uzakta olacak bir kullanıcı, kişilerin iletişim kurabileceği bir kişiyi temsilci olarak atayabilir. İleti temsilcisi özelliği aşağıdaki gibi çalışır:

1. Dışarıda olacak kullanıcı, durum iletisinde başka bir kullanıcı (temsilci) @mentions ve kullanıcılara, kullanıcı dışarıdayken bunun yerine temsilciyle iletişim kurmaları gerektiğini bildirir. 

    ![Kullanıcı temsilci olarak ayarlanmış bir durum iletisinin ekran görüntüsü.](media/message-delegation.png)
    
1. @mentioned kullanıcıya temsilci olarak aday gösterildiği bildirilir.
1. Birisi dış kullanıcıyla bir sohbet açtığında ve durum iletisini gördüğünde, temsilcinin üzerine gelip kolayca ileti gönderebiliyor.

Kullanıcılar işlemi kendileri başlatabilir ve özelliği etkinleştirmek için yönetici katılımı gerekmez.

## <a name="delegation-use-scenario-in-healthcare"></a>Healthcare'de temsilci kullanımı senaryosu

**Temsilci ayarlamadan kullanım örneği** 

Dr. Franco Piccio radyoloji bölümünden aradı. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri, Dr. Lena Ehrle, o yokken onu korumasını istiyor. Çağrıyı yapan dr. Ehrle'e, çağrıyı yapan acil mesajları ve pingleri dinleyen ve mevcut sorumluluklarına ek olarak Dr. Piccio adına onlara yanıt veren Dr. Ehrle'ye resmi olmayan bir şekilde teslim eder. Ekipte yer alan diğer kişiler, resmi olmayan temsilin gerçekleştiğini fark etmeyebilir. Karışıklık bir hastanın bakımıyla sonuçlanmış.

**Temsilci ayarlama ile kullanım örneği** 

Dr. Franco Piccio radyoloji bölümünden aradı. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri, Dr. Lena Ehrle'den, o yokken onun yerine onu korumasını istiyor. Özel durum iletisini "Önümüzdeki birkaç saat için kullanılamıyorum. Acil durumlar için lütfen @DrEhrle ile iletişime geçin."  Ekipteki diğer kişiler, Dr. Piccio'ya başvurmaya çalışırken temsilcinin gerçekleştiğini fark ettiler, bu arada Dr. Ehrle ile iletişime geçmeyi biliyorlar. Hastanın bakımıyla çok az karışıklığa yol açıyor.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Birlikte kullanım modlarının Teams istemcisindeki kullanıcı durumu üzerindeki etkisi

Durum notları ve temsilci bahsetme davranışları kısmen kullanıcının birlikte kullanım moduna bağlıdır. Bu matris olasılıkları gösterir:

|Co-Existence Modu | Beklenen Davranış|
|---|---|
|TeamsOnly |Kullanıcılar yalnızca Teams'den not ayarlayabilir. <br> Kullanıcının Teams notu Teams & SfB'de görünür. |
|Adaları | Kullanıcının Teams'de ayarlanan notları yalnızca Teams'de görünür. <br> SfB'de kullanıcının not kümesi yalnızca SfB'de görünür |
|SfB* modları | Kullanıcılar yalnızca SfB'den bir not ayarlayabilir. <br> Kullanıcının SfB notu SfB & Teams'de görünür.  |

Bir kullanıcı Teams'de yalnızca modu TeamsOnly veya Islands ise bir not ayarlayabilir.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Skype Kurumsal'de ayarlanan notları görüntüleme
  
Skype Kurumsal'dan bir not ayarlandığını gösteren görsel bir gösterge yoktur.

Skype Kurumsal durum notlarında karakter sınırını zorlamaz. Ancak Microsoft Teams, Skype Kurumsal not kümesinin yalnızca ilk 280 karakterini görüntüler. Notun sonundaki üç nokta (...) kesildiğini gösterir.
  
Skype Kurumsal notlar için süre sonu sürelerini desteklemez.

Kullanıcı TeamsOnly moduna yükseltildiğinde notların Skype Kurumsal Teams'e geçirilmesi desteklenmez.

## <a name="related-topics"></a>İlgili konular

[Skype Kurumsal ile birlikte bulunma hakkında daha fazla bilgi edinin](/microsoftteams/coexistence-chat-calls-presence).
