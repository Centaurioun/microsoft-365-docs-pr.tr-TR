---
title: Otomatik araştırmanın ayrıntıları ve sonuçları
description: otomatik araştırmanın sonuçlarını ve önemli bulgularını Microsoft 365 Defender
keywords: otomatik, araştırma, sonuçlar, analiz, ayrıntılar, düzeltme, otomatik hava aracı
search.appverid: met150
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
ms.date: 08/11/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: 238c2f90c47338e9ece876bf0a9146bdfaa9427c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069677"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Otomatik araştırmanın ayrıntıları ve sonuçları

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender ile [otomatik araştırma](m365d-autoir.md) çalıştırıldığında, bu araştırmayla ilgili ayrıntılar hem otomatik araştırma işlemi sırasında hem de sonrasında kullanılabilir. [Gerekli izinlere](m365d-action-center.md#required-permissions-for-action-center-tasks) sahipseniz, bu ayrıntıları size güncel durumu ve bekleyen eylemleri onaylama olanağı sağlayan bir araştırma ayrıntıları görünümünde görüntüleyebilirsiniz. 

## <a name="new-unified-investigation-page"></a>(YENİ) Birleşik araştırma sayfası

Araştırma sayfası yakın zamanda cihazlarınız, e-postanız ve işbirliği içeriğiniz arasında bilgi içerecek şekilde güncelleştirildi. Yeni, birleşik araştırma sayfası ortak bir dil tanımlar ve [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ve [Office 365 için Microsoft Defender](../office-365-security/defender-for-office-365.md) genelinde otomatik araştırmalara yönelik birleşik bir deneyim sağlar. Birleşik araştırma sayfasına erişmek için, göreceğiniz sarı başlıktaki bağlantıyı seçin:

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Microsoft Purview uyumluluk portalı</a> herhangi bir araştırma sayfası
- Microsoft 365 Defender portalındaki herhangi bir araştırma sayfası ([https://security.microsoft.com](https://security.microsoft.com))
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> herhangi bir olay veya İşlem merkezi deneyimi

## <a name="open-the-investigation-details-view"></a>Araştırma ayrıntıları görünümünü açma

Aşağıdaki yöntemlerden birini kullanarak araştırma ayrıntıları görünümünü açabilirsiniz:

- [İşlem merkezinde bir öğe seçme](#select-an-item-in-the-action-center)
- [Olay ayrıntıları sayfasından araştırma seçme](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>İşlem merkezinde bir öğe seçme

Geliştirilmiş [İşlem merkezi](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)), cihazlarınız, e-posta & işbirliği içeriği ve kimlikler genelinde [düzeltme eylemlerini](m365d-remediation-actions.md) bir araya getirir. Listelenen eylemler, otomatik olarak veya el ile gerçekleştirilen düzeltme eylemlerini içerir. İşlem merkezinde, onay bekleyen eylemleri ve zaten onaylanmış veya tamamlanmış eylemleri görüntüleyebilirsiniz. Araştırma sayfası gibi daha fazla ayrıntıya da gidebilirsiniz.

> [!TIP]
> Eylemleri onaylamak, reddetmek veya geri almak için [belirli izinlere](m365d-action-center.md#required-permissions-for-action-center-tasks) sahip olmanız gerekir.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve oturum açın. 

2. Gezinti bölmesinde **İşlem merkezi'ni** seçin. 

3. **Beklemede** veya **Geçmiş** sekmesinde bir öğe seçin. Açılır pencere bölmesi açılır.

4. Açılır pencere bölmesindeki bilgileri gözden geçirin ve aşağıdaki adımlardan birini uygulayın:
   - Araştırma hakkında daha fazla ayrıntı görüntülemek için **Araştırma sayfasını aç'ı** seçin.
   - Bekleyen bir eylem başlatmak için **Onayla'yı** seçin.
   - Bekleyen bir eylemin gerçekleştirilmesini önlemek için **Reddet'i** seçin.
   - [Gelişmiş avcılığa](advanced-hunting-overview.md) gitmek için **Avlanmaya git'i** seçin.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Olay ayrıntıları sayfasından araştırma açma

Etkilenen cihazlar, kullanıcı hesapları veya posta kutuları hakkında tetiklenen bilgiler de dahil olmak üzere bir olayla ilgili ayrıntılı bilgileri görüntülemek için olay ayrıntıları sayfasını kullanın.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve oturum açın. 

2. Gezinti bölmesinde **Olaylar & uyarılar** > **Olaylar'ı** seçin. 

3. Listeden bir öğe seçin ve ardından **Olay sayfasını aç'ı** seçin.

4. **Araştırma sekmesini** ve ardından listeden bir araştırma seçin. Açılır pencere bölmesi açılır.

5. **Araştırma sayfasını aç'ı** seçin. 

İşte bir örnek.

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Microsoft 365 Defender portalındaki araştırma sayfası" lightbox="../../media/mtp-incidentdetails-tabs.png":::

## <a name="investigation-details"></a>Araştırma ayrıntıları

Araştırmayla ilgili geçmiş, geçerli ve bekleyen etkinlikleri görmek için araştırma ayrıntıları görünümünü kullanın. İşte bir örnek.

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Microsoft 365 Defender portalındaki araştırma ayrıntıları sayfası" lightbox="../../media/mtp-air-investdetails.png":::

Araştırma ayrıntıları görünümünde, aşağıdaki tabloda açıklanan **Araştırma grafı**, Uyarılar, **Cihazlar**, **Kimlikler**, **Anahtar bulguları**, **Varlıklar**, **Günlük** ve **Bekleyen eylemler** sekmeleriyle ilgili bilgileri görebilirsiniz. 

> [!NOTE]
> Araştırma ayrıntıları sayfasında gördüğünüz belirli sekmeler, aboneliğinizin içeriğine bağlıdır. Örneğin, aboneliğiniz Plan 2'Office 365 için Microsoft Defender içermiyorsa **Posta Kutuları** sekmesini görmezsiniz.

| Sekme | Açıklama |
|:--------|:--------|
| **Araştırma grafiği** | Araştırmanın görsel bir gösterimini sağlar. Bulunan tehditlerin yanı sıra uyarıları ve onay bekleyen eylemlerin olup olmadığını gösterir.<br/>Daha fazla ayrıntı görüntülemek için grafikte bir öğe seçebilirsiniz. Örneğin, **Kanıt** simgesini seçtiğinizde, algılanan varlıkları ve bunların kararlarını görebileceğiniz **Kanıt** sekmesine gidebilirsiniz. |
| **Uyarılar** | Araştırmayla ilişkili uyarıları listeler. Uyarılar, kullanıcının cihazında, Office uygulamalarında, Microsoft Defender for Cloud Apps ve diğer Microsoft 365 Defender özelliklerindeki tehdit koruması özelliklerinden gelebilir. <br> <br> *Desteklenmeyen uyarı türü* görüyorsanız bu, otomatik araştırma özelliklerinin otomatik araştırma çalıştırmak için bu uyarıyı alamayacağı anlamına gelir. Ancak [, bu uyarıları el ile araştırabilirsiniz](investigate-incidents.md#alerts).
| **Aygıtları** | Araştırmada yer alan cihazları ve düzeltme düzeylerini listeler. (Düzeltme düzeyleri [, cihaz grupları için otomasyon düzeyine](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) karşılık gelir.) |
| **Posta kutu -ları** |Algılanan tehditlerden etkilenen posta kutularını listeler.  |
| **Kullanıcılar**  | Algılanan tehditlerden etkilenen kullanıcı hesaplarını listeler. |
| **Kanıt** | Uyarılar veya araştırmalarla ortaya konan kanıt parçalarını listeler. Kararları (*Kötü Amaçlı*, *Şüpheli*, *Bilinmeyen* veya *Tehdit bulunamadı*) ve düzeltme durumunu içerir. |
| **Varlık** | Her varlık türü (*Kötü Amaçlı*, *Şüpheli* veya *Tehdit bulunamadı*) için bir karar da dahil olmak üzere analiz edilen her varlıkla ilgili ayrıntıları sağlar.|
|**Günlük** | Uyarı tetiklendikten sonra gerçekleştirilen tüm araştırma eylemlerinin kronolojik, ayrıntılı bir görünümünü sağlar.|
| **Bekleyen eylemler geçmişi** | Devam etmek için onay gerektiren öğeleri listeler. Bekleyen eylemleri onaylamak için İşlem merkezine ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) gidin. |


## <a name="investigation-states"></a>Araştırma durumları

Aşağıdaki tabloda araştırma durumları ve bunların neyi gösterdiği listelenmiştir.


|Araştırma durumu  |Tanım  |
|---------|---------|
|Benign   | Yapıtlar araştırıldı ve herhangi bir tehdit bulunmadığını tespit edildi.|
|PendingResource     | Bir düzeltme eylemi onay beklemede olduğundan veya bir yapıtın bulunduğu cihaz geçici olarak kullanılamadığından otomatik araştırma duraklatıldı.|
|DesteklenmeyenAlertType     | Bu tür bir uyarı için otomatik araştırma kullanılamaz. Gelişmiş avcılık kullanılarak el ile daha fazla araştırma yapılabilir. |
|Başarısız     | En az bir araştırma çözümleyicisi, araştırmayı tamamlayamadığı bir sorunla karşılaştı. Düzeltme eylemleri onaylandıktan sonra bir araştırma başarısız olursa, düzeltme eylemleri yine de başarılı olmuş olabilir.|
|Başarıyla düzeltilmiş| Otomatik bir araştırma tamamlandı ve tüm düzeltme eylemleri tamamlandı veya onaylandı.|

Araştırma durumlarının nasıl gösteriliyor olduğu hakkında daha fazla bağlam sağlamak için aşağıdaki tabloda uyarılar ve buna karşılık gelen otomatik araştırma durumları listelenmektedir. Bu tablo, bir güvenlik operasyonları ekibinin Microsoft 365 Defender portalında neler görebileceğine ilişkin bir örnek olarak eklenmiştir.

|Uyarı adı | Önem derecesi | Araştırma durumu | Durum | Kategori |
|-----------|----------|---------------------|--------|----------|
|Wim disk görüntü dosyasında kötü amaçlı yazılım algılandı|Bilgi|Benign|Çözülmüş|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Wpakill hacktool engellendi|Düşük|Başarısız|Yeni|Malware|
|GendowsBatch hacktool engellendi|Düşük|Başarısız|Yeni|Malware|
|Keygen hacktool engellendi|Düşük|Başarısız|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Zip arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Bir rar arşiv dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Iso disk görüntü dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Iso disk görüntü dosyasında kötü amaçlı yazılım algılandı|Bilgi|PendingResource|Yeni|Malware|
|Pst Outlook veri dosyasında kötü amaçlı yazılım algılandı|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|Pst Outlook veri dosyasında kötü amaçlı yazılım algılandı|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|MediaGet algılandı|Orta|KısmenInvestigated|Yeni|Malware|
|TrojanEmailFile|Orta|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Bilgi|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|Etkin bir CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Düşük|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|Etkin bir CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Düşük|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|Etkin bir CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Düşük|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|TrojanEmailFile|Orta|Benign|Çözülmüş|Malware|
|CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Bilgi|DesteklenmeyenAlertType|Yeni|Malware|
|CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Bilgi|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|TrojanEmailFile|Orta|Başarıyla Kaldırıldı|Çözülmüş|Malware|
|TrojanEmailFile|Orta|Benign|Çözülmüş|Malware|
|Etkin bir CustomEnterpriseBlock kötü amaçlı yazılımı engellendi|Düşük|PendingResource|Yeni|Malware|

## <a name="next-steps"></a>Sonraki adımlar

- [Düzeltme eylemlerini görüntüleyin ve yönetin](m365d-autoir-actions.md)
- [Düzeltme eylemleri hakkında daha fazla bilgi edinin](m365d-remediation-actions.md)
