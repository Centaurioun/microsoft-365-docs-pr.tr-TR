---
title: Temsilci atamak için Teams durum iletisi kullanma
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
- highpri
- EngageScoreSep2022
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: acolonna
description: Dışarıda durumu veya Rahatsız Etmeyin durumu olan bir kullanıcının, durum iletisinde başka bir kullanıcıyı açıkça temsilci olarak nasıl ayarlayabileceğini öğrenin.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4837b6c2b8ac4a450705397819ccb93fdbbfa8f6
ms.sourcegitcommit: e326b492f6ff15b78d4b77b0a1da06dcdaad3f62
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2022
ms.locfileid: "68676047"
---
# <a name="use-a-teams-status-message-to-assign-a-delegate"></a>Temsilci atamak için Teams durum iletisi kullanma

Microsoft Teams'deki kullanıcılar durumlarını Dışarıda veya Rahatsız Etmeyin olarak ayarlayabilir ve özel bir metin durumu iletisi ekleyebilir. Uzakta olacak bir kullanıcı, kişilerin iletişim kurabileceği bir kişiyi temsilci olarak atayabilir. İleti temsilcisi özelliği aşağıdaki gibi çalışır:

1. Dışarıda olacak kullanıcı, durum iletisinde başka bir kullanıcı (temsilci) @mentions ve kullanıcılara, kullanıcı dışarıdayken bunun yerine temsilciyle iletişim kurmaları gerektiğini bildirir.

    ![Kullanıcı temsilci olarak ayarlanmış bir durum iletisinin ekran görüntüsü.](media/message-delegation.png)

1. @mentioned kullanıcıya temsilci olarak aday gösterildiği bildirilir.
1. Birisi dış kullanıcıyla bir sohbet açtığında ve durum iletisini gördüğünde, temsilcinin üzerine gelip kolayca ileti gönderebiliyor.

Kullanıcılar işlemi kendileri başlatabilir ve özelliği etkinleştirmek için yönetici katılımı gerekmez.

> [!NOTE]
> Durum notları ve temsilci bahsetme davranışları da Skype Kurumsal kullanılabilir, ancak bunların kullanılabilirliği kullanıcının birlikte kullanım moduna bağlıdır. Skype Kurumsal durum notlarında karakter sınırını zorlamaz. Ancak Microsoft Teams, Skype Kurumsal not kümesinin yalnızca ilk 280 karakterini görüntüler. Notun sonundaki üç nokta (...) kesildiğini gösterir. Skype Kurumsal notlar için süre sonu sürelerini desteklemez. <br>Skype Kurumsal Online, 31 Temmuz 2021'de kullanımdan kaldırıldı. [Microsoft Teams'e yükseltmeyi öğrenin](/microsoftteams/upgrade-start-here).

## <a name="delegation-use-scenario-in-healthcare"></a>Healthcare'de temsilci kullanımı senaryosu

**Temsilci ayarlamadan kullanım örneği**

Dr. Franco Piccio radyoloji bölümünden aradı. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri, Dr. Lena Ehrle, o yokken onu korumasını istiyor. Çağrıyı yapan dr. Ehrle'e, çağrıyı yapan acil mesajları ve pingleri dinleyen ve mevcut sorumluluklarına ek olarak Dr. Piccio adına onlara yanıt veren Dr. Ehrle'ye resmi olmayan bir şekilde teslim eder. Ekipte yer alan diğer kişiler, resmi olmayan temsilin gerçekleştiğini fark etmeyebilir. Karışıklık bir hastanın bakımıyla sonuçlanmış.

**Temsilci ayarlama ile kullanım örneği**

Dr. Franco Piccio radyoloji bölümünden aradı. Acil bir arama alır ve önümüzdeki birkaç saat için uzaklaşmak zorunda. Radyoloji departmanındaki akranlarından biri, Dr. Lena Ehrle'den, o yokken onun yerine onu korumasını istiyor. Özel durum iletisini "Önümüzdeki birkaç saat için kullanılamıyorum. Acil durumlar için lütfen @DrEhrle ile iletişime geçin."  Ekipteki diğer kişiler, Dr. Piccio'ya başvurmaya çalışırken temsilcinin gerçekleştiğini fark ettiler, bu arada Dr. Ehrle ile iletişime geçmeyi biliyorlar. Hastanın bakımıyla çok az karışıklığa yol açıyor.
