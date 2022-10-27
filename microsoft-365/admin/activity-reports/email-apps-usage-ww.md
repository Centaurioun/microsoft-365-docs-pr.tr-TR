---
title: E-posta uygulamaları kullanım raporlarını Microsoft 365 yönetim merkezi
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Exchange Online bağlanan e-posta uygulamalarının sayısını ve Outlook kullanıcılarının hangi sürümünü kullandığını öğrenmek için e-posta uygulamaları kullanım raporunu nasıl alacağınızı öğrenin.
ms.openlocfilehash: a2bc937e0282c13f68f71b08cdd5d07850a649da
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68724869"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Yönetim merkezinde Microsoft 365 Raporları - Email uygulama kullanımı

Microsoft 365 Raporları panosu, kuruluşunuzdaki ürünler genelindeki etkinliğe genel bakışı gösterir. Bu pano sayesinde her bir üründeki etkinliklerle ilgili daha ayrıntılı bilgi edinmek için ürün düzeyinde raporları ayrıntılı olarak inceleyebilirsiniz. [Raporlara genel bakış konusuna](activity-reports.md) göz atın. E-posta uygulamaları kullanım raporunda, Exchange Online bağlanan e-posta uygulamalarının sayısını görebilirsiniz. Kullanıcıların kullandığı Outlook uygulamalarının sürüm bilgilerini de görebilirsiniz. Bu bilgiler, desteklenen Outlook sürümlerini yüklemek için desteklenmeyen sürümleri kullananlarla iletişim kurmanızı sağlar.
  
## <a name="how-to-get-to-the-email-apps-report"></a>E-posta uygulamaları raporuna erişme

1. Yönetim merkezinde, **Raporlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Kullanımı</a> sayfasına gidin.
2. **etkinlik Email** altında **Daha Fazla Görüntüle'yi** seçin. 
3. **Email etkinlik** açılan **listesinden Exchange** \> **Email uygulamaları kullanımını** seçin.
  
## <a name="interpret-the-email-apps-report"></a>E-posta uygulamaları raporunu yorumlama

**Kullanıcılar** ve **İstemciler** grafiklerine bakarak e-posta uygulamaları etkinliğine ilişkin bir görünüm elde edebilirsiniz. 
  
![kullanılan Email istemcileri.](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)

**Email uygulamaları kullanım** raporu son 7 gün, 30 gün, 90 gün veya 180 günlük eğilimler için görüntülenebilir. Ancak raporda belirli bir gün seçerseniz, tablo geçerli tarihten itibaren (raporun oluşturulduğu tarihten değil) 28 güne kadar olan verileri gösterir. Her rapordaki veriler genellikle son 24-48 saati kapsar.

**Kullanıcılar** görünümü, herhangi bir e-posta uygulamasını kullanarak Exchange Online'a bağlanan benzersiz kullanıcıların sayısını gösterir. 

**Uygulamalar** görünümü, seçilen süre içinde uygulamaya göre benzersiz kullanıcı sayısını gösterir. 

**Sürümler** görünümü, Windows'ta Outlook'un her sürümü için benzersiz kullanıcı sayısını gösterir. 

Kullanıcılar grafiğinde Y ekseni, rapor dönemindeki herhangi bir günde bir uygulamaya bağlanan benzersiz kullanıcıların toplam sayısını gösterir. X ekseni, bu raporlama dönemi için uygulamayı kullanan benzersiz kullanıcıların sayısıdır. 

Uygulamalar grafiğinde Y ekseni, rapor dönemi içerisinde belirli bir uygulamayı kullanan benzersiz kullanıcıların toplam sayısını gösterir. X ekseni, kuruluşunuzdaki uygulamaların listesidir. 

Sürümler grafiğinde Y ekseni, Outlook masaüstünün belirli bir sürümünü kullanan benzersiz kullanıcıların toplam sayısını gösterir. Rapor Outlook'un sürüm numarasını çözümleyemiyorsa miktar **Belirsiz** olarak gösterilir. X ekseni, kuruluşunuzdaki uygulamaların listesidir.

Göstergede bir öğe seçerek grafikte gördüğünüz seriyi filtreleyebilirsiniz. Tüm öğeleri ekleyene kadar aşağıdaki listenin sütunlarında bu öğeleri göremeyebilirsiniz.
 
|Öğe|Açıklama|
|:-----|:-----|
|Kullanıcı Adı | E-posta uygulamasının sahibinin adı. |
|Son etkinlik tarihi | Kullanıcının e-posta iletisini okuduğu veya gönderdiği en son tarih. |
|Mac posta, Mac Outlook, Outlook, Outlook mobile ve Web üzerinde Outlook | Kuruluşunuzda sahip olabileceğiniz e-posta uygulamaları örnekleri. |
   
Kuruluşunuzun ilkeleri nedeniyle kişisel kullanıcı bilgilerinin bulunduğu raporları görüntüleyemiyorsanız bu raporların gizlilik ayarını değiştirebilirsiniz. Microsoft 365 yönetim merkezi Etkinlik Raporları'nın **kullanıcı düzeyi ayrıntılarını Nasıl yaparım?** [gizlensin mi](activity-reports.md)? bölümüne göz atın. 

Rapora sütun eklemek veya rapordan sütun kaldırmak için Sütunları **seç'i** seçin.  

![Uygulama kullanım raporunu Email - sütunları seçin.](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)

Dışarı **Aktar bağlantısını** seçerek rapor verilerini bir Excel .csv dosyasına da aktarabilirsiniz. Bu işlem tüm kullanıcıların verilerini dışarı aktarır ve daha fazla çözümleme yapmak için basit sıralama ve filtreleme işlemlerini kullanmanıza olanak tanır. 