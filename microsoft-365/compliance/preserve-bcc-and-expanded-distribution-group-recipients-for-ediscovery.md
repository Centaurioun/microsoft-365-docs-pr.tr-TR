---
title: eBulma için Gizli ve genişletilmiş dağıtım grubu alıcılarını koruma
description: In-Place Tutma, Dava Tutma ve Microsoft 365 saklama ilkeleri, mevzuat uyumluluğu ve eBulma gereksinimlerini karşılamak için posta kutusu içeriğini korumanıza olanak tanır.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- ediscovery
ms.openlocfilehash: c68058974afb19778aa5674ae1217b6163ea0504
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687978"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>eBulma için Gizli ve genişletilmiş dağıtım grubu alıcılarını koruma
  
Microsoft Purview uyumluluk portalı oluşturulan dava tutmaları, eBulma [tutmaları ve Microsoft 365 bekletme ilkeleri](./retention.md), mevzuat uyumluluğu ve eBulma gereksinimlerini karşılamak için posta kutusu içeriğini korumanıza olanak tanır. Bir iletinin Kime ve Bilgi alanlarında doğrudan ele alınan alıcılar hakkındaki bilgiler varsayılan olarak tüm iletilere eklenir. Ancak kuruluşunuz, iletinin tüm alıcıları hakkındaki ayrıntıları arama ve yeniden oluşturma olanağı gerektirebilir. Bu, şunları kapsar:
  
- **İletinin Gizli alanı kullanılarak adreslenen alıcılar:** Gizli alıcılar, iletide gönderenin posta kutusunda depolanır, ancak alıcılara teslim edilen iletinin üst bilgilerine eklenmez.
- **Genişletilmiş dağıtım grubu alıcıları:** Kime, Bilgi veya Gizli alanlarında, iletinin ele alındığı bir dağıtım grubunun üyesi oldukları için iletiyi alan alıcılar.

Exchange Online ve Exchange Server 2013 (Toplu Güncelleştirme 7 ve sonraki sürümleri) Gizli ve genişletilmiş dağıtım grubu alıcıları hakkındaki bilgileri korur. Uyumluluk portalında bir eBulma aracı kullanarak bu bilgileri arayabilirsiniz.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Gizli alıcılar ve genişletilmiş dağıtım grubu alıcıları nasıl korunur?

Gizli alıcılarla ilgili bilgiler, gönderenin posta kutusunda iletiyle birlikte depolanır. Bu bilgiler dizine eklenir ve eBulma aramaları ve tutmaları için kullanılabilir.

Genişletilmiş dağıtım grubu alıcılarıyla ilgili bilgiler, In-Place Ayrı Tutma veya Dava Tutma'ya bir posta kutusu yerleştirildikten sonra iletiyle birlikte depolanır. Microsoft 365'te bu bilgiler, posta kutusuna bir Microsoft Purview bekletme ilkesi uygulandığında da depolanır. Dağıtım grubu üyeliği, ileti gönderildiğinde belirlenir. İletiyle birlikte depolanan genişletilmiş alıcılar listesi, ileti gönderildikten sonra grup üyeliğindeki değişikliklerden etkilenmez.

|Hakkında bilgi...|Depolandığı yer...|Varsayılan olarak depolanıyor mu?|Erişim...|
|:-------------------|:--------------|:--------------------|:------------------|
|Kime: ve Bilgi: alıcılar|Gönderen ve alıcıların posta kutularındaki ileti özellikleri.|Evet|Gönderen, alıcılar ve uyumluluk görevlileri|
|Gizli: alıcılar|Gönderenin posta kutusunda ileti özelliği.|Evet|Gönderen ve uyumluluk görevlileri|
|Genişletilmiş dağıtım grubu alıcıları|Gönderenin posta kutusunda ileti özellikleri.|Hayır. Genişletilmiş dağıtım grubu alıcı bilgileri, posta kutusu In-Place Ayrı Tutma veya Dava Tutma'ya yerleştirildikten veya microsoft Purview saklama ilkesine atandıktan sonra depolanır.|Uyumluluk görevlileri|

## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Gizli ve genişletilmiş dağıtım grubu alıcılarına gönderilen iletileri arama

Alıcıya gönderilen iletileri ararken, eBulma arama sonuçları artık alıcının üyesi olduğu bir dağıtım grubuna gönderilen iletileri içerir. Aşağıdaki tabloda, Gizli ve genişletilmiş dağıtım grubu alıcılarına gönderilen iletilerin eBulma aramalarında döndürüldüğü senaryolar gösterilmektedir.

**Senaryo 1**: John, US-Sales dağıtım grubunun bir üyesidir. Bu tabloda, Bob doğrudan veya dolaylı olarak bir dağıtım grubu aracılığıyla John'a ileti gönderdiğinde eBulma arama sonuçları gösterilir.

|Gönderilen iletiler için Bob'un posta kutusunda arama yaptığınızda...|Ve ileti ile gönderilir...|Sonuçlar ileti içeriyor mu?|
|---|---|---|
|Son: John|John on To:|Evet|
|Son: John|US-Sales:|Evet|
|Son: US-Sales|US-Sales:|Evet|
|Bilgi: John|Bilgi üzerinde John:|Evet|
|Bilgi: John|Bilgi US-Sales:|Evet|
|Bilgi: US-Sales|Bilgi US-Sales:|Evet|

**Senaryo 2**: Bob, John (To/Cc) ve Jack'e (Gizli doğrudan veya dolaylı olarak bir dağıtım grubu aracılığıyla) bir e-posta gönderir. Aşağıdaki tabloda eBulma arama sonuçları gösterilmektedir.

|Aradığınızda...|Gönderilen iletiler için...|Sonuçlar ileti içeriyor mu?|Notlar|
|---|---|---|---|
|Bob'ın posta kutusu|Kime:/Bilgi: John|Evet|Jack'in gizli olduğunu gösterir.|
|Bob'ın posta kutusu|Gizli: Jack|Evet|Jack'in gizli olduğunu gösterir.|
|Bob'ın posta kutusu|Gizli: Jack (dağıtım grubu aracılığıyla)|Evet|İleti gönderildiğinde genişletilmiş Gizli dağıtım grubunun üyelerinin listesi eBulma arama önizlemesi, dışarı aktarma ve günlüklerde görünür.|
|John'un posta kutusu|Kime:/Bilgi: John|Evet|Gizli alıcıları yok.|
|John'un posta kutusu|Gizli: Jack (doğrudan veya dağıtım grubu aracılığıyla)|Hayır|Gizli: Bilgiler alıcılara teslim edilen iletide depolanmaz. Gönderenin posta kutusunda aramanız gerekir.|
|Jack'in posta kutusu|To:/Cc: John (doğrudan veya dağıtım grubu aracılığıyla)|Evet|Kime:/Bilgi: Bilgiler tüm alıcılara teslim edilen iletiye eklenir.|
|Jack'in posta kutusu|Gizli: Jack (doğrudan veya dağıtım grubu aracılığıyla)|Hayır|Gizli: Bilgiler alıcılara teslim edilen iletide depolanmaz. Gönderenin posta kutusunda aramanız gerekir.|

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Gizli alıcı bilgileri ne zaman ve nerede depolanır?**

Gizli alıcı bilgileri, gönderenin posta kutusunda özgün iletide varsayılan olarak korunur. Gizli alıcı bir dağıtım grubuysa, dağıtım grubu üyeliği yalnızca gönderenin posta kutusu beklemedeyse veya bir Microsoft 365 bekletme ilkesine atanmışsa genişletilir.

**Genişletilmiş dağıtım grubu alıcılarının listesi ne zaman ve nerede depolanır?**

Grup üyeliği, ileti gönderildiğinde genişletilir. Genişletilmiş dağıtım grubu üyelerinin listesi, gönderenin posta kutusunda özgün iletide depolanır. Gönderenin posta kutusu In-Place Ayrı Tutma, Dava Tutma veya microsoft 365 saklama ilkesine atanmış olmalıdır.

**Kime/Bilgi alıcıları hangi alıcıların Gizli olduğunu görebilir mi?**

Hayır. Bu bilgiler ileti üst bilgilerine dahil değildir ve Kime/Bilgi alıcıları tarafından görülemez. Gönderen, posta kutusunda depolanan özgün iletide depolanan Gizli alanını görebilir. Uyumluluk görevlileri, gönderenin posta kutusunda arama yaparken bu bilgileri görebilir.

**Genişletilmiş dağıtım grubu alıcılarının her zaman korunmasını nasıl sağlayabilirim?**

Genişletilmiş dağıtım grubu üyelerinin her zaman bir iletiyle korunmasını sağlamak için [tüm posta kutularını beklemeye alın](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) veya kuruluş genelinde bir Microsoft 365 bekletme ilkesi oluşturun.

**Hangi grup türleri desteklenir?**

Dağıtım grupları, posta etkin güvenlik grupları ve dinamik dağıtım grupları desteklenir.

**İletide genişletilip depolanan dağıtım grubu alıcılarının sayısında bir sınır var mı?**

Bir dağıtım grubunun en çok 10.000 üyesi korunur.

**İç içe dağıtım grupları destekleniyor mu?**

Evet, 25 iç içe dağıtım grubu düzeyi genişletilir.

**Gizli ve genişletilmiş dağıtım grubu alıcı bilgileri nerede görünür?**

Gizli ve genişletilmiş dağıtım grubu alıcıları bilgileri, eBulma araması yapılırken Uyumluluk görevlileri tarafından görülebilir. Gizli ve genişletilmiş dağıtım grubu alıcıları, Bulma posta kutusuna kopyalanan veya pst dosyasına aktarılan arama sonuçlarına ve arama sonuçlarına dahil edilen eBulma günlüğüne eklenir. Gizli alıcı bilgileri arama önizlemesinde de kullanılabilir.

**Dağıtım grubunun bir üyesi kuruluşun genel adres listesinden (GAL) gizlenirse ne olur?**

Hiçbir etkisi yok. Alıcılar GAL'den gizlenirse, genişletilmiş dağıtım grubu için alıcılar listesinde yer almaya devam eder.
