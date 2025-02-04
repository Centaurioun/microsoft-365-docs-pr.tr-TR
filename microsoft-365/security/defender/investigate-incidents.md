---
title: Microsoft 365 Defender'daki olayları araştırma
description: Cihazlar, kullanıcılar ve posta kutularıyla ilgili olayları araştırın.
keywords: olay, olaylar, saldırı hikayesi, analiz, yanıt, makineler, cihazlar, kullanıcılar, kimlikler, posta, e-posta, posta kutusu, araştırma, graf, kanıt
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 41006d8c68eef16d09bc872ca3d8fc471812cb1c
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687771"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender'daki olayları araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

Microsoft 365 Defender cihazlarınız, kullanıcılarınız ve posta kutularınızdaki tüm ilgili uyarıları, varlıkları, araştırmaları ve kanıtları bir olay halinde toplayarak bir saldırının tüm kapsamına kapsamlı bir bakış sağlar.

Bir olay içinde ağınızı etkileyen uyarıları analiz eder, ne anlama geldiğini anlar ve etkili bir düzeltme planı oluşturabilmeniz için kanıtları harmanlarsınız.

## <a name="initial-investigation"></a>İlk araştırma

Ayrıntılara girmeden önce, olayın özelliklerine ve saldırı hikayesinin tamamına göz atın.

Onay işareti sütunundan olayı seçerek başlayabilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Microsoft 365 Defender portalında bir olay seçme" lightbox="../../media/investigate-incidents/incidents-ss-incident-select.png":::

Bunu yaptığınızda, olayla ilgili önem derecesi, atandığı kişi gibi önemli bilgilerin ve olayın [MITRE ATT&CK&trade;](https://attack.mitre.org/) kategorilerinin yer aldığı bir özet bölmesi açılır. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Microsoft 365 Defender portalında bir olayın özet ayrıntılarını görüntüleyen bölme." lightbox="../../media/investigate-incidents/incidents-ss-incident-side-panel.png":::

Buradan **Olay sayfasını aç'ı** seçebilirsiniz. Bu, tam saldırı hikayesi bilgilerini ve uyarılar, cihazlar, kullanıcılar, araştırmalar ve kanıt sekmelerini bulabileceğiniz olayın ana sayfasını açar.

Olay kuyruğundan olay adını seçerek bir olayın ana sayfasını da açabilirsiniz.

## <a name="attack-story"></a>Saldırı hikayesi

Saldırı hikayeleri, saldırının tüm hikayesini aynı sekmede görüntülerken saldırıları hızla gözden geçirmenize, araştırmanıza ve düzeltmenize yardımcı olur. Ayrıca varlık ayrıntılarını gözden geçirmenize ve bir dosyayı silme veya bağlamı kaybetmeden bir cihazı yalıtma gibi düzeltme eylemleri gerçekleştirmenize olanak tanır.

:::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Bir olayın saldırı hikayesi" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

Saldırı hikayesinin içinde uyarı sayfasını ve olay grafiğini bulabilirsiniz.

Olay uyarısı sayfasında şu bölümler vardır:

- Uyarı hikayesi:

   - Ne oldu

   - Gerçekleştirilen eylemler

   - İlgili olaylar

- Sağ bölmedeki uyarı özellikleri (durum, ayrıntılar, açıklama ve diğerleri)

Her uyarının **Uyarı hikayesi** bölümünde listelenen tüm alt bölümlere sahip olmadığını unutmayın.

Grafikte saldırının tam kapsamı, saldırının zaman içinde ağınız üzerinden nasıl yayıldığı, nereden başladığı ve saldırganın ne kadar ileri gittiği gösterilir. Saldırının parçası olan farklı şüpheli varlıkları kullanıcılar, cihazlar ve posta kutuları gibi ilgili varlıklarına bağlar.

Grafikten şunları yapabilirsiniz:

- Saldırının kronolojisini anlamak için zaman içinde gerçekleşen uyarıları ve düğümleri grafikte oynatın.
  
  :::image type="content" source="../../media/investigate-incidents/play-alert-attack-story.gif" alt-text="Saldırı hikayesi grafı sayfasında uyarıların ve düğümlerin oynatıldığını gösteren ekran görüntüsü.":::

- Varlık bölmesini açarak varlık ayrıntılarını gözden geçirmenizi ve dosyayı silme veya cihazı yalıtma gibi düzeltme eylemleri üzerinde işlem yapmanızı sağlar.

  :::image type="content" source="../../media/investigate-incidents/review-entity-details-attack-story.gif" alt-text="Saldırı hikayesi graf sayfasındaki varlık ayrıntılarının gözden geçirilmesini gösteren ekran görüntüsü.":::

- İlgili oldukları varlığa göre uyarıları vurgulayın.

Olayın göreli önemini değerlendirmek ve ilişkili uyarılara ve etkilenen varlıklara hızla erişmek için **Özet** sayfasını kullanın.

## <a name="summary"></a>Özet

**Özet** sayfası, olayla ilgili dikkat çekmeniz gereken en önemli şeylere bir anlık görüntü bakışı sağlar.

:::image type="content" source="../../media/incidents-overview/incidents-investigate-summary.png" alt-text="Microsoft 365 Defender portalında bir olayın özet bilgilerini gösteren ekran görüntüsü." lightbox="../../media/incidents-overview/incidents-investigate-summary.png":::

Bilgiler bu bölümlerde düzenlenmiştir.

| Bölüm | Açıklama |
|:-------|:-----|
| Uyarılar ve kategoriler | Saldırının sonlandırma zincirine karşı ne kadar gelişmiş olduğunu gösteren görsel ve sayısal bir görünüm. Diğer Microsoft güvenlik ürünlerinde olduğu gibi Microsoft 365 Defender de [MITRE ATT&CK&trade;](https://attack.mitre.org/) çerçevesine hizalanır. Uyarılar zaman çizelgesi, uyarıların oluştuğu kronolojik sırayı ve her uyarı için durumlarını ve adlarını gösterir. |
| Kapsam |  Etkilenen cihazların, kullanıcıların ve posta kutularının sayısını görüntüler ve varlıkları risk düzeyi ve araştırma önceliği sırasına göre listeler. |
| Kanıt | Olaydan etkilenen varlık sayısını görüntüler. |
| Olay bilgileri | Olayın etiketler, durum ve önem derecesi gibi özelliklerini görüntüler. |
|||

## <a name="alerts"></a>Uyarılar

**Uyarılar** sekmesinde, olayla ilgili uyarılar ve bunlar hakkında aşağıdakiler gibi diğer bilgiler için uyarı sırasını görüntüleyebilirsiniz:

- Önem.
- Uyarıya katılan varlıklar.
- Uyarıların kaynağı (Kimlik için Microsoft Defender, Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender, Bulut Uygulamaları için Defender ve uygulama idare eklentisi).
- Bu yüzden birbirlerine bağlandılar.

İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Uyarılar bölmesi" lightbox="../../media/investigate-incidents/incident-alerts.png":::

Varsayılan olarak, uyarılar kronolojik olarak sıralanır ve bu sayede saldırının zaman içinde nasıl ilerlediğini görebilirsiniz. Bir olay içinde bir uyarı seçtiğinizde, Microsoft 365 Defender genel olayın bağlamı için uyarı bilgilerini görüntüler. 

Uyarının olaylarını, diğer tetiklenen uyarıların geçerli uyarıya neden olduğunu ve cihazlar, dosyalar, kullanıcılar ve posta kutuları dahil olmak üzere saldırıyla ilgili tüm etkilenen varlıkları ve etkinlikleri görebilirsiniz.

İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Microsoft 365 Defender portalındaki bir olay içindeki uyarının ayrıntıları." lightbox="../../media/investigate-incidents/incident-alert-example.png":::

Uyarıları [araştırmak](investigate-alerts.md) için uyarı kuyruğu ve uyarı sayfalarını kullanmayı öğrenin.

## <a name="devices"></a>Aygıtları

**Cihazlar** sekmesi olayla ilgili tüm cihazları listeler. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Cihazlar sayfası" lightbox="../../media/investigate-incidents/incident-devices.png":::

Cihazın ayrıntılarını, dizin verilerini, etkin uyarıları ve oturum açmış kullanıcıları görmek için cihazın onay işaretini seçebilirsiniz. Uç Nokta için Defender cihaz envanterinde cihaz ayrıntılarını görmek için cihazın adını seçin. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Uç Nokta için Microsoft Defender Cihaz envanteri seçeneğiyle ilgili sayfa." lightbox="../../media/investigate-incidents/incident-devices-details.png":::

Cihaz sayfasından cihaz hakkında tüm uyarıları, zaman çizelgesi ve güvenlik önerileri gibi ek bilgiler toplayabilirsiniz. Örneğin, **Zaman Çizelgesi** sekmesinde makine zaman çizelgesinde gezinebilir ve makinede gözlemlenen tüm olayları ve davranışları, tetiklenen uyarılarla birlikte kronolojik sırayla görüntüleyebilirsiniz.

> [!TIP]
> Bir cihaz sayfasında isteğe bağlı taramalar yapabilirsiniz. Microsoft 365 Defender portalında **Uç Noktalar > Cihaz envanteri'ni** seçin. Uyarıları olan bir cihaz seçin ve ardından virüsten koruma taraması çalıştırın. Virüsten koruma taramaları gibi eylemler izlenir ve **Cihaz envanteri** sayfasında görünür. Daha fazla bilgi için bkz. [Cihazlarda virüsten koruma taraması Microsoft Defender çalıştırma](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Kullanıcılar

**Kullanıcılar** sekmesi, olayın parçası olduğu veya olayla ilgili olduğu belirlenen tüm kullanıcıları listeler. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Microsoft 365 Defender portalındaki Kullanıcılar sayfası." lightbox="../../media/investigate-incidents/incident-users.png":::

Kullanıcı hesabı tehdidinin, açığa çıkarmanın ve iletişim bilgilerinin ayrıntılarını görmek için kullanıcının onay işaretini seçebilirsiniz. Ek kullanıcı hesabı ayrıntılarını görmek için kullanıcı adını seçin.

Kullanıcıları araştırmak için ek kullanıcı bilgilerini görüntülemeyi ve bir olayın [kullanıcılarını](investigate-users.md) yönetmeyi öğrenin.

## <a name="mailboxes"></a>Posta kutu -ları

**Posta Kutuları** sekmesi, olayın parçası olduğu veya olayla ilgili olduğu belirlenen tüm posta kutularını listeler. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Posta Kutuları sayfası." lightbox="../../media/investigate-incidents/incident-mailboxes.png":::

Etkin uyarıların listesini görmek için posta kutusunun onay işaretini seçebilirsiniz. Office 365 için Defender için Gezgin sayfasında ek posta kutusu ayrıntılarını görmek için posta kutusu adını seçin.

## <a name="investigations"></a>Sondajları

**Araştırma sekmesi**, bu olaydaki uyarılar tarafından tetiklenen tüm [otomatik araştırmaları](m365d-autoir.md) listeler. Otomatik araştırmalar, otomatik araştırmalarınızı Uç Nokta ve Office 365 için Defender için Defender'da çalışacak şekilde nasıl yapılandırdığınıza bağlı olarak düzeltme eylemleri gerçekleştirir veya analistin eylemleri onaylamasını bekler.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Araştırma sayfası" lightbox="../../media/investigate-incidents/incident-investigations.png":::

Araştırma ve düzeltme durumu hakkında tam bilgi için ayrıntılar sayfasına gitmek için bir araştırma seçin. Araştırmanın bir parçası olarak onay bekleyen eylemler varsa, **Bunlar Bekleyen eylemler geçmişi** sekmesinde görünür. Olay düzeltme işleminin bir parçası olarak işlem yapın.

Ayrıca şunları gösteren bir **Araştırma grafı** sekmesi de vardır:

- Uyarıların kuruluşunuzdaki etkilenen varlıklarla bağlantısı.
- Hangi varlıkların hangi uyarılarla ilgili olduğu ve bunların saldırı hikayesinin bir parçası olması.
- Olayın uyarıları.

Araştırma grafiği, saldırının parçası olan farklı şüpheli varlıkları kullanıcılar, cihazlar ve posta kutuları gibi ilgili varlıklarına bağlayarak saldırının tam kapsamını hızla anlamanıza yardımcı olur. 

Daha fazla bilgi için bkz. [Microsoft 365 Defender'de otomatik araştırma ve yanıt](m365d-autoir.md).

## <a name="evidence-and-response"></a>Kanıt ve Yanıt

**Kanıt ve Yanıt** sekmesi, olaydaki uyarılarda desteklenen tüm olayları ve şüpheli varlıkları gösterir. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Kanıt ve Yanıt sayfası" lightbox="../../media/investigate-incidents/incident-evidence.png":::

Microsoft 365 Defender, uyarılardaki tüm olayların desteklenen olaylarını ve şüpheli varlıkları otomatik olarak araştırır ve size önemli e-postalar, dosyalar, işlemler, hizmetler, IP Adresleri ve daha fazlası hakkında bilgi sağlar. Bu, olaydaki olası tehditleri hızla algılamanıza ve engellemenize yardımcı olur.

Analiz edilen varlıkların her biri bir karar (Kötü Amaçlı, Şüpheli, Temiz) ve bir düzeltme durumuyla işaretlenir. Bu, tüm olayın düzeltme durumunu ve sonraki adımları anlamanıza yardımcı olur.

## <a name="next-steps"></a>Sonraki adımlar

Gerektiğinde:

- [Bir olayın uyarılarını araştırma](investigate-alerts.md)
- [Bir olayın kullanıcılarını araştırma](investigate-users.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olaylara öncelik belirleyin](incident-queue.md)
- [Olayları yönetin](manage-incidents.md)
