---
title: Microsoft 365 için Exchange Online izleme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
f1.keywords:
- NOCSH
description: Microsoft 365'te e-posta olayları veya önerileri hakkında bilgi için Exchange Online izlemeyi kullanın.
ms.openlocfilehash: 97500a7ad2eb801d4bbcad622cce8ca222ae363e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180571"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Microsoft 365 için Exchange Online izleme

Exchange Online izleme, aşağıdaki kuruluş düzeyinde senaryoları destekler:

- **Email istemcileri**: E-posta okuma etkinliğine göre aşağıdaki e-posta istemcilerinin durumunu görüntüleyebilirsiniz:

  - Outlook masaüstü
  - Web üzerinde Outlook
  - iOS ve Android'in yerel posta istemcileri
  - iOS ve Android'de Outlook Mobile uygulaması
  - Outlook Mac istemcisi

   Bu istemciler için, son 30 dakikada e-postayı okuyan kullanıcılara bağlı olarak etkin kullanıcıların sayısını ve panodaki olay ve öneri sayısını görebilirsiniz. Bu veriler, bir sorun olup olmadığını görmek için önceki haftanın aralığıyla karşılaştırılır.

   >[!Note]
   > Etkin kullanıcı sayısı, örneğin bir kullanıcı bir e-postayı okuduğunda tek bir etkinlikle ölçülür. Yalnızca son 30 dakikalık etkinliği hesaplar.

- **Uygulama bağlantısı**: Tahmini bağlantı, kuruluşunuzun cihazlarıyla Exchange Online arasındaki başarılı ve yapay bağlantı yüzdesini temel alır ve Microsoft'un denetimi dışındaki sorunları içerebilir. Daha fazla bilgi için bkz. [Microsoft 365 Bağlantı Optikleri](microsoft-365-connectivity-optics.md).

- **Temel Kimlik Doğrulaması ve Modern Kimlik Doğrulaması**: Exchange Online hizmetinde başarıyla doğrulanan kullanıcı sayısı.

- **Posta akışı**: İleti Microsoft 365 ağına ulaştıktan sonra herhangi bir gecikme olmadan posta kutusuna başarıyla teslim edilen ileti sayısı.

- **Web için Outlook'u açın**: Başarıyla oturum açan ve Web üzerinde Outlook başlatılan kullanıcıların sayısı.
  
Aşağıda, ana panodaki Exchange Online için kuruluş düzeyinde senaryolara bir örnek verilmiştir.

![Exchange Online İzleme için kuruluş düzeyinde senaryolar.](../media/microsoft-365-exchange-monitoring/exchange-monitoring-org-scenarios.png)

Bu senaryolar için ana panodaki son 30 dakika için önemli numaralar bulunur. Bu senaryoların her biri için ayrıntılı görünümler, önceki haftaya kıyasla 30 dakikalık toplamayla yedi güne yakın gerçek zamanlı eğilimi gösterir.

![Posta teslimi için Exchange sistem durumunu izleme örneği.](../media/microsoft-365-exchange-monitoring/exchange-monitoring-scenario-example.png)

Kuruluşunuz için oluşturulan ve "Kuruluşunuz" olarak etiketlenen iletişimde "Sorun kaynağı" olan olayları veya danışmanlıkları fark edeceksiniz. Bunlar, azaltma ve çözüm için dikkatinizi gerektiren sorunlarla birlikte kuruluşunuza yönelik tek tek bildirimlerdir. Kuruluşunuzu olası etki hakkında bilgilendirmek üzere hizmet durumu içinde oluşturulan ve iletilebilen çeşitli sorun türleri hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Posta kutusu kullanımı için hizmet uyarıları](microsoft-365-mailbox-utilization-service-alerts.md)

- [MRS kaynak gecikmeleri için hizmet uyarıları](microsoft-365-mrs-source-delays-service-alerts.md)

- [Dış alıcılara teslimi bekleyen iletiler için hizmet uyarıları](microsoft-365-external-recipient-service-alerts.md)

## <a name="priority-accounts-monitoring-scenarios"></a>Öncelik hesapları izleme senaryoları

Exchange Online öncelik hesabı izlemesiyle, [öncelik hesaplarını](/microsoft-365/admin/setup/priority-accounts) yapılandırdıktan sonra aşağıdaki senaryoların durumunu görüntüleyebilirsiniz:

- Exchange lisanslama

- Posta Kutusu depolama alanı

- İleti sınırı

- Klasör başına alt klasörler

- Klasör hiyerarşisi

- Kurtarılabilir öğeler

Exchange lisans senaryosu, kiracı yöneticisi tarafından giderilebilen geçersiz lisans sorunları nedeniyle öncelik hesabının oturum açıp açamayacağını denetler.

Yukarıdaki kalan beş senaryo, öncelik hesabınızın posta kutusunun ulaşılmaya yakın olup olmadığını veya [Exchange Online sınırları](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-storage-limits) içinde açıklanan sınırlara ulaşıp ulaşmadığını denetler.

Bu senaryolar için, etkin ve çözümlenmiş önerileri ve öncelik hesaplarınızı etkileyen olayları görebilirsiniz. Öncelik hesapları için tanımlanabilir bilgiler önerilerle birlikte danışmanlık veya olay ayrıntılarında görüntülenir. Sistem Durumu > Hizmet durumu > Exchange Online sayfasından bir örnek aşağıda **verilmiştır**.

:::image type="content" source="../media/microsoft-365-exchange-monitoring/exchange-priority-accounts-example.png" alt-text="Öncelikli hesaplarınızı etkileyen etkin ve çözümlenmiş öneriler ve olaylar örneği":::

Etkilenen hesap bölmesinde **Durum** sütununda şu değerler vardır:

- Düzeltildi: Öncelik hesabı için öneriye veya olaya neden olan sorun giderildi. Artık bir sorun yok. 

- Etkin: Öncelik hesabı için danışmanlık veya olaya neden olan sorun devam ediyor. Sorun devam ediyor. 

- Gecikmeli: Danışmanlık veya olaya neden olan sorun 96 saat içinde öncelik hesabı için giderilmediğinden askıya alındı. Sorun devam ediyor. 

İşte bir örnek.

:::image type="content" source="../media/microsoft-365-exchange-monitoring/exchange-status-column-example.png" alt-text="Etkilenen hesap bölmesindeki durum sütunu örneği":::

**Etkin** durumda hiçbir hesap kalmadıktan sonra bir danışmanlık veya olay çözülür.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="1-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>1. Her istemci için panodaki etkin kullanıcı sayısı düşük görünüyor. Kullanıcılara atanmış çok sayıda etkin lisansımız var. Bu ne anlama geliyor?

İzlemede gösterilen etkin kullanıcı sayısı, kullanıcıların özellikte belirtilen etkinliği gerçekleştirdiği 30 dakikalık bir pencereyi temel alır. Bu durum kullanım numaralarıyla karıştırılmamalıdır. Kullanım numaralarını görüntülemek için Microsoft 365 yönetim merkezi (**Rapor** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">**Kullanımı**</a>) içindeki etkinlik raporlarını kullanın.

### <a name="2-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>2. Etkinlik eğilimlerini gösteren senaryolar için veriler nerede izlenmektedir?

Veriler Exchange Online hizmetinde izlenmiştir. İstek Exchange Online ulaşmadan önce gerçekleşen bir hata varsa veya Exchange Online'de bir hata varsa etkinlik sinyalinde bir düşüş görürsünüz.
