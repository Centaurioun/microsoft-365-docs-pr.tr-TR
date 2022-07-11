---
title: Olay sırasını görüntüleyin ve düzenleyin
ms.reviewer: ''
description: Olay listesine bakın ve listeyi sınırlamak ve daha odaklanmış bir görünüm elde etmek için filtre uygulamayı öğrenin.
keywords: görüntüleme, düzenleme, olaylar, toplama, araştırma, kuyruk, ttp
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a2d75b935c19a20c37ecdbdb77feff73bbed4a79
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66714651"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Uç Nokta için Microsoft Defender Olayları sırasını görüntüleme ve düzenleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

**Olaylar kuyruğu**, ağınızdaki cihazlardan bayrak eklenmiş bir olay koleksiyonunu gösterir. Bilinçli bir siber güvenlik yanıtı kararını önceliklendirmek ve oluşturmak için olayları sıralamanıza yardımcı olur.

Kuyruk varsayılan olarak son 30 gün içinde görülen olayları görüntüler ve en son olay listenin en üstünde gösterilir ve en son olayları ilk olarak görmenize yardımcı olur.

Olaylar kuyruğu görünümünü özelleştirmek için aralarından seçim yapabileceğiniz çeşitli seçenekler vardır. 

Üst gezintide aşağıdakileri yapabilirsiniz:
- Sütunları eklemek veya kaldırmak için sütunları özelleştirme 
- Sayfa başına görüntüleyebileceğiniz öğe sayısını değiştirme
- Sayfa başına gösterilecek öğeleri seçin
- Batch-atanacak olayları seçin 
- Sayfalar arasında gezinme
- Filtre uygulama
- Tarih aralıklarını özelleştirme ve uygulama

:::image type="content" source="images/atp-incident-queue.png" alt-text="Olaylar kuyruğu" lightbox="images/atp-incident-queue.png":::

## <a name="sort-and-filter-the-incidents-queue"></a>Olaylar sırasını sıralama ve filtreleme
Olay listesini sınırlamak ve daha odaklanmış bir görünüm elde etmek için aşağıdaki filtreleri uygulayabilirsiniz.

### <a name="severity"></a>Önem derecesi

Olay önem derecesi | Açıklama
:---|:---
Yüksek </br>(Kırmızı) | Genellikle gelişmiş kalıcı tehditlerle (APT) ilişkili tehditler. Bu olaylar, cihazlara verebilecekleri hasarın önem derecesine bağlı olarak yüksek risk olduğunu gösterir.
Orta </br>(Turuncu) | Anormal kayıt defteri değişikliği, şüpheli dosyaların yürütülmesi ve saldırı aşamalarının tipik gözlemlenen davranışları gibi kuruluşta nadiren görülen tehditler.
Düşük </br>(Sarı) | Yaygın kötü amaçlı yazılımlarla ve hack araçlarıyla ilişkili tehditler, kuruluşu hedefleyen gelişmiş bir tehdidi belirtmez.
Bilgi </br>(Gri) | Bilgilendirici olaylar ağa zararlı olarak kabul edilmeyebilir, ancak takip etmek iyi olabilir.

## <a name="assigned-to"></a>Atanan
Size atanan herkese veya kişilere atanmış olanları seçerek listeyi filtrelemeyi seçebilirsiniz.

### <a name="category"></a>Kategori
Olaylar, siber güvenlik sonlandırma zincirinin bulunduğu aşamanın açıklamasına göre kategorilere ayrılmıştır. Bu görünüm, tehdit analistinin bağlama göre dağıtılacak öncelik, aciliyet ve karşılık gelen yanıt stratejisini belirlemesine yardımcı olur.

### <a name="status"></a>Durum
Hangilerinin etkin veya çözümlenmiş olduğunu görmek için durumlarına göre gösterilen olayların listesini sınırlamayı seçebilirsiniz.

### <a name="data-sensitivity"></a>Veri duyarlılığı
Duyarlılık etiketleri içeren olayları göstermek için bu filtreyi kullanın.

## <a name="incident-naming"></a>Olay adlandırma

Olayın kapsamını bir bakışta anlamak için, olay adları etkilenen uç nokta sayısı, etkilenen kullanıcılar, algılama kaynakları veya kategoriler gibi uyarı özniteliklerine göre otomatik olarak oluşturulur.

Örneğin: *Birden çok kaynak tarafından bildirilen birden çok uç noktada çok aşamalı olay.*

> [!NOTE]
> Otomatik olay adlandırmanın dağıtımından önce var olan olaylar adlarını korur.


## <a name="see-also"></a>Ayrıca bkz.
- [Olay sırası](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Olayları yönetin](manage-incidents.md)
- [Olayları araştırın](investigate-incidents.md)

