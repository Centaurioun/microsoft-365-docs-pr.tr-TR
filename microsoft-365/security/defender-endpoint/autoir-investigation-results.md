---
title: Otomatik bir soruşturmanın ayrıntılarını ve sonuçlarını görüntüleyin
description: Otomatik araştırma sırasında ve sonrasında sonuçları ve önemli bulguları görüntüleyebilirsiniz
keywords: otomatik, araştırma, sonuçlar, analiz, ayrıntılar, düzeltme, otomatik hava aracı
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: cd405a02e2148c0a82921b45b66e20d238c12ec4
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387979"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Otomatik bir soruşturmanın ayrıntılarını ve sonuçlarını görüntüleyin

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Uç Nokta için Microsoft Defender ile otomatik araştırma çalıştırıldığında, bu [araştırmayla](automated-investigations.md) ilgili ayrıntılar hem otomatik araştırma işlemi sırasında hem de sonrasında kullanılabilir. Gerekli izinlere sahipseniz, bu ayrıntıları araştırma ayrıntıları görünümünde görüntüleyebilirsiniz. Araştırma ayrıntıları görünümü size güncel durum ve bekleyen eylemleri onaylama olanağı sağlar.

## <a name="new-unified-investigation-page"></a>(YENİ!) Birleşik araştırma sayfası

Araştırma sayfası yakın zamanda cihazlarınız, e-postanız ve işbirliği içeriğiniz arasında bilgi içerecek şekilde güncelleştirildi. Yeni, birleşik araştırma sayfası ortak bir dil tanımlar ve [Uç Nokta için Microsoft Defender](microsoft-defender-endpoint.md) ve [Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security/office-365-atp) genelinde otomatik araştırmalara yönelik birleşik bir deneyim sağlar.

> [!TIP]
> Değişenler hakkında daha fazla bilgi edinmek için bkz. [(YENİ!) Birleşik araştırma sayfası](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Araştırma ayrıntıları görünümünü açma

Aşağıdaki yöntemlerden birini kullanarak araştırma ayrıntıları görünümünü açabilirsiniz:

- [İşlem merkezinde bir öğe seçme](#select-an-item-in-the-action-center)
- [Olay ayrıntıları sayfasından araştırma seçme](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>İşlem merkezinde bir öğe seçme

Geliştirilmiş [İşlem merkezi](auto-investigation-action-center.md) cihazlarınız, e-posta & işbirliği içeriği ve kimlikler genelinde [düzeltme eylemlerini](manage-auto-investigation.md#remediation-actions) bir araya getirir. Listelenen eylemler, otomatik olarak veya el ile gerçekleştirilen düzeltme eylemlerini içerir. İşlem merkezinde, onay bekleyen eylemleri ve zaten onaylanmış veya tamamlanmış eylemleri görüntüleyebilirsiniz. Araştırma sayfası gibi daha fazla ayrıntıya da gidebilirsiniz.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> gidin ve oturum açın.
2. Gezinti bölmesinde **İşlem merkezi'ni** seçin.
3. **Beklemede** veya **Geçmiş** sekmesinde bir öğe seçin. Açılır pencere bölmesi açılır.
4. Açılır pencere bölmesindeki bilgileri gözden geçirin ve aşağıdaki adımlardan birini uygulayın:
   - Araştırma hakkında daha fazla ayrıntı görüntülemek için **Araştırma sayfasını aç'ı** seçin.
   - Bekleyen bir eylem başlatmak için **Onayla'yı** seçin.
   - Bekleyen bir eylemin gerçekleştirilmesini önlemek için **Reddet'i** seçin.
   - [Gelişmiş avcılığa](advanced-hunting-overview.md) gitmek için **Avlanmaya git'i** seçin.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Olay ayrıntıları sayfasından araştırma açma

Etkilenen cihazlar, kullanıcı hesapları veya posta kutuları hakkında tetiklenen bilgiler de dahil olmak üzere bir olayla ilgili ayrıntılı bilgileri görüntülemek için olay ayrıntıları sayfasını kullanın.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> gidin ve oturum açın.
2. Gezinti bölmesinde **Olaylar & uyarılar** \> **Olaylar'ı** seçin.
3. Listeden bir öğe seçin ve ardından **Olay sayfasını aç'ı** seçin.
4. **Araştırma sekmesini** ve ardından listeden bir araştırma seçin. Açılır pencere bölmesi açılır.
5. **Araştırma sayfasını aç'ı** seçin.

## <a name="investigation-details"></a>Araştırma ayrıntıları

Araştırmayla ilgili geçmiş, geçerli ve bekleyen etkinlikleri görmek için araştırma ayrıntıları görünümünü kullanın. Araştırma ayrıntıları görünümü aşağıdaki görüntüye benzer:

Araştırma ayrıntıları görünümünde, aşağıdaki tabloda açıklanan **Araştırma grafı**, Uyarılar, **Cihazlar**, **Kimlikler**, **Anahtar bulguları**, **Varlıklar**, **Günlük** ve **Bekleyen eylemler** sekmeleriyle ilgili bilgileri görebilirsiniz. 

> [!NOTE]
> Araştırma ayrıntıları sayfasında gördüğünüz belirli sekmeler, aboneliğinizin içeriğine bağlıdır. Örneğin, aboneliğiniz Plan 2'Office 365 için Microsoft Defender içermiyorsa **Posta Kutuları** sekmesini görmezsiniz.

|Sekme|Açıklama|
|---|---|
|**Araştırma grafiği**|Araştırmanın görsel bir gösterimini sağlar. Bulunan tehditlerin yanı sıra uyarıları ve onay bekleyen eylemlerin olup olmadığını gösterir. <p> Daha fazla ayrıntı görüntülemek için grafikte bir öğe seçebilirsiniz. Örneğin, **Kanıt** simgesini seçtiğinizde, algılanan varlıkları ve bunların kararlarını görebileceğiniz **Kanıt** sekmesine gidebilirsiniz.|
|**Uyarılar**|Araştırmayla ilişkili uyarıları listeler. Uyarılar, kullanıcının cihazında, Office uygulamalarında, Bulut Uygulamaları için Defender'da ve diğer Microsoft 365 Defender özelliklerinde bulunan tehdit koruması özelliklerinden gelebilir.|
|**Aygıtları**|Araştırmada yer alan cihazları ve düzeltme düzeylerini listeler. (Düzeltme düzeyleri [, cihaz grupları için otomasyon düzeyine](automation-levels.md) karşılık gelir.)|
|**Posta kutu -ları**|Algılanan tehditlerden etkilenen posta kutularını listeler.|
|**Kullanıcılar**|Algılanan tehditlerden etkilenen kullanıcı hesaplarını listeler.|
|**Kanıt**|Uyarılar/araştırmalarla ortaya konan kanıt parçalarını listeler. Kararları (*Kötü Amaçlı*, *Şüpheli* veya *Tehdit bulunamadı*) ve düzeltme durumunu içerir.|
|**Varlık**|Her varlık türü (*Kötü Amaçlı*, *Şüpheli* veya *Tehdit bulunamadı*) için bir karar da dahil olmak üzere analiz edilen her varlıkla ilgili ayrıntıları sağlar.|
|**Günlük**|Uyarı tetiklendikten sonra gerçekleştirilen tüm araştırma eylemlerinin kronolojik, ayrıntılı bir görünümünü sağlar.|
|**Bekleyen eylemler**|Devam etmek için onay gerektiren öğeleri listeler. Bekleyen eylemleri onaylamak için İşlem merkezine (<https://security.microsoft.com/action-center>) gidin.|

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

## <a name="see-also"></a>Ayrıca bkz.

- [Otomatik bir araştırmanın ardından düzeltme eylemlerini gözden geçirin](manage-auto-investigation.md)
- [Uç Nokta için Microsoft Defender Olayları sırasını görüntüleme ve düzenleme](view-incidents-queue.md)
