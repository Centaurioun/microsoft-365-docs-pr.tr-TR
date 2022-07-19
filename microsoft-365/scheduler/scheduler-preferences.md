---
title: Microsoft 365 için Scheduler'a genel bakış için zamanlama tercihlerini ayarlama
ms.author: shivb
author: shivbijlani
manager: charlle
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: Microsoft 365 için Scheduler zamanlama tercihlerini ayarlamayı öğrenin.
ms.openlocfilehash: e6b6f4426b173bced90fcc8f2a705bc3e48cd09e
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2022
ms.locfileid: "66861826"
---
# <a name="scheduling-preferences-used-by-scheduler"></a>Scheduler tarafından kullanılan zamanlama tercihleri

Zamanlayıcı, bir düzenleyici için toplantı zamanlamak için birkaç Outlook tercihi kullanır. Outlook istemcilerindeki tercih ayarlarında yapılan tüm değişiklikler Zamanlayıcı'nın Cortana'ya gönderilen istekleri nasıl işlediğini etkiler. Örneğin, bir düzenleyici Outlook Web'deki ayarlar sayfasındaki saat dilimi tercihini değiştirirse, düzenleyici tarafından yapılan ve izleyen tüm istekler varsayılan olarak yeni saat dilimine ayarlanır.

## <a name="supported-settings"></a>Desteklenen ayarlar

- **Saat dilimi**. Zamanlayıcı, toplantılar için uygun bir saati belirlemek için kullanır. Bilgi için bkz. [Saat dilimlerini ekleme, kaldırma veya değiştirme](https://support.microsoft.com/en-us/office/add-remove-or-change-time-zones-5ab3e10e-5a6c-46af-ab48-156fedf70c04) .

- **Çalışma saatleri ve günler**. Çoğu toplantı türü için Zamanlayıcı, düzenleyicinin çalışma haftası ve toplantı saatleri tercihlerine göre bir saat seçer. Bilgi için bkz. [Outlook'ta çalışma saatlerinizi ve günlerinizi değiştirme](https://support.microsoft.com/en-us/office/change-your-work-hours-and-days-in-outlook-a27f261d-0681-415f-8ac1-388ab21e833f) .

- **Çevrimiçi toplantılar**. Outlook ve Scheduler'dan zamanladığınız tüm toplantıların konferans ayrıntılarıyla çevrimiçi olarak gerçekleştirilmesi için Bir Takvim seçeneğini açabilirsiniz. Scheduler şu anda toplantı sağlayıcıları olarak Teams ve Skype'ı desteklemektedir. Bilgi için bkz. [Tüm toplantıları teams toplantıları yapma](https://support.microsoft.com/en-us/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f#bkmk_makeallteamsmtngs) .

- **Varsayılan toplantı süresi**. Düzenleyici istekte istenen toplantı süresini belirtmezse, Zamanlayıcı istek için tercih edilen toplantı süresini kullanır. Bu ayar yalnızca Windows Outlook istemcisinde kullanılabilir.

   1. Outlook Seçenekleri iletişim kutusunu görmek için **Dosya** > **Seçenekleri'ni** seçin.

   2. İletişim kutusunun sol tarafındaki listeden **Takvim'i** seçin.

   3. İletişim kutusunun sağ tarafındaki Takvim seçenekleri ayarlarında **Yeni randevular ve toplantılar için varsayılan süre'yi** seçin.

      :::image type="content" source="../media/OutlookOptions.png" alt-text="Windows'da çalışma süresini, varsayılan toplantı süresini ayarlayabileceğiniz ve Zamanlayıcı'nın kullanacağı toplantıları kısalt seçeneğini belirleyebileceğiniz Outlook Takvim seçenekler iletişim kutusu.":::

- **Arka arkaya toplantılardan kaçının**. Outlook ayarı, arka arkaya toplantılardan kaçınmak için toplantıları geç başlatabilir veya toplantıları erken sonlandırabilir. Ayrıca Zamanlayıcı, toplantı süresini ayarladığınız tercihe göre kısaltabilir. Bilgi için bkz. [Varsayılan toplantı uzunluğunu değiştirme](https://techcommunity.microsoft.com/t5/hybrid-work/change-default-meeting-length-in-outlook-avoid-back-to-back/m-p/1247361) .

> [!NOTE]
> Windows istemcisini kullanıyorsanız tercihlerinizi Scheduler ve diğer Outlook istemcileriyle eşitlemek için **Outlook ayarlarımı bulutta depola'yı** seçmeniz gerekir.
> :::image type="content" source="../media/OutlookOptions2.png" alt-text="Windows'da Outlook Takvim seçenekleri iletişim kutusu. Zamanlama tercihlerini istemciler arasında eşitlemek için Outlook ayarlarımı bulutta depola'yı seçin.":::
