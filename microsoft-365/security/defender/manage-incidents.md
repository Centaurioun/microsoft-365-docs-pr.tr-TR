---
title: Microsoft 365 Defender'de olayları yönetme
description: Atamayı, durumu güncelleştirmeyi öğrenin,
keywords: olay, olaylar, saldırı hikayesi, analiz etme, yanıt, uyarılar, bağıntılı uyarılar, atama, güncelleştirme, durum, yönetme, sınıflandırma, Microsoft, 365, m365
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dc5e017732c9d00f3b9ab05310a6fff8a0777b86
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68686605"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender'de olayları yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Olay yönetimi, olay iş akışınızda zamanı iyileştirmek ve tehditleri daha hızlı bir şekilde içerip ele almak için olayların adlandırıldığından, atandığından ve etiketlendiğinden emin olmak için kritik öneme sahiptir.

**Olaylar & uyarıları > Olayları** Microsoft 365 Defender portalın ([security.microsoft.com](https://security.microsoft.com)) hızlı lansmanından yönetebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender portalındaki Olaylar sayfası" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Olaylarınızı yönetmek için kullanabileceğiniz yöntemler şunlardır:

- [Olay adını düzenleme](#edit-the-incident-name)
- [Olay etiketleri ekleme](#add-incident-tags)
- [Olayı bir kullanıcı hesabına atama](#assign-an-incident)
- [Bunları çözme](#resolve-an-incident)
- [Sınıflandırmasını belirtin](#specify-the-classification)
- [Açıklama ekleme](#add-comments)

Olayları bir olayın **Olay yönetme** bölmesinden yönetebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Microsoft 365 Defender portalındaki Olayı yönet bölmesi" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Bu bölmeyi aşağıdaki olay **yönet** bağlantısından görüntüleyebilirsiniz:

- **Uyarı hikayesi** sayfası.
- Olay kuyruğundaki bir olayın Özellikler bölmesi.
- Bir olayın **özet** sayfası.

Uyarıları bir olaydan diğerine taşımak istediğiniz durumlarda, **uyarılar sekmesinden** de bunu yapabilirsiniz, böylece tüm ilgili uyarıları içeren daha büyük veya daha küçük bir olay oluşturabilirsiniz.

## <a name="edit-the-incident-name"></a>Olay adını düzenleme

Microsoft 365 Defender, etkilenen uç nokta sayısı, etkilenen kullanıcılar, algılama kaynakları veya kategoriler gibi uyarı özniteliklerine göre otomatik olarak bir ad atar. Bu, olayın kapsamını hızlı bir şekilde anlamanıza olanak tanır. Örneğin: *Birden çok kaynak tarafından bildirilen birden çok uç noktada çok aşamalı olay.*

Olay adını, Olayı **yönet** bölmesindeki **Olay adı** alanından düzenleyebilirsiniz.

> [!NOTE]
> Otomatik olay adlandırma özelliği piyasaya sürülmeden önce var olan olaylar adlarını korur.

## <a name="add-incident-tags"></a>Olay etiketleri ekleme

Bir olaya, örneğin ortak bir özelliğe sahip bir olay grubuna bayrak eklemek için özel etiketler ekleyebilirsiniz. Daha sonra belirli bir etiket içeren tüm olaylar için olay kuyruğuna filtreleyebilirsiniz.

Yazmaya başladığınızda, önceden kullanılan ve seçilen etiketler listesinden seçim yapmak için seçeneğiniz vardır.

## <a name="assign-an-incident"></a>Olay atama

Henüz bir olay atanmamışsa, **Ata** kutusunu seçip kullanıcı hesabını belirtebilirsiniz. Bir olayı yeniden atamak için hesap adının yanındaki "x" işaretini seçip **Atanan** kutusunu seçerek geçerli atama hesabını kaldırın. Bir olayın sahipliğini atamak, kendisiyle ilişkilendirilmiş tüm uyarılara aynı sahipliği atar.

Olay kuyruğuna filtre uygulama yoluyla size atanan olayların listesini alabilirsiniz. 

1. Olay kuyruğundan **Filtreler'i** seçin.
2. **Olay ataması** bölümünde **Tümünü seç'i** temizleyin ve **Bana atanan'ı** seçin.
3. **Uygula'yı** seçin ve **filtreler bölmesini kapatın**.

Ardından, size atanan olayların listesini hızla görmek için elde edilen URL'yi tarayıcınıza yer işareti olarak kaydedebilirsiniz.

## <a name="resolve-an-incident"></a>Bir olayı çözme

Olay düzeltildiyse olayı **çözümle'yi** seçerek iki durumlu düğmeyi sağa taşıyın. Bir olayı çözümlemenin, olayla ilgili tüm bağlantılı ve etkin uyarıları da çözümlediğini unutmayın.

Çözümlenmeyen bir olay **Etkin** olarak görüntülenir.

## <a name="specify-the-classification"></a>Sınıflandırmayı belirtme

**Sınıflandırma** alanında, olayın aşağıdakilerden biri olup olmadığını belirtirsiniz:

- **Ayarlanmadı** (varsayılan).
- Bir tehdit türüyle **gerçek pozitif**. Gerçek bir tehdidi doğru şekilde gösteren olaylar için bu sınıflandırmayı kullanın. Tehdit türünü belirtmek, güvenlik ekibinizin tehdit desenlerini görmesine ve kuruluşunuzu onlardan korumak için harekete geçilmesine yardımcı olur.
- Bir etkinlik türüyle **bilgilendirici, beklenen** etkinlik. Güvenlik testlerine, kırmızı ekip etkinliğine ve güvenilen uygulamalardan ve kullanıcılardan beklenen olağan dışı davranışlara yönelik olayları sınıflandırmak için bu kategorideki seçenekleri kullanın.
- Teknik olarak yanlış veya yanıltıcı olduğundan, tespit ettiğiniz olay türleri için **hatalı pozitif** değeri yoksayılabilir.

Olayları sınıflandırmak, durumlarını ve türlerini belirtmek, zaman içinde daha iyi algılama belirlemesi sağlamak için Microsoft 365 Defender ayarlanmasına yardımcı olur.

## <a name="add-comments"></a>Açıklama ekleme

**Açıklama** alanıyla bir olaya birden çok açıklama ekleyebilirsiniz. Her açıklama, olayın geçmiş olaylarına eklenir. **Özet** sayfasındaki Açıklamalar ve geçmiş bağlantısından bir olayın açıklamalarını **ve geçmişini** görebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Yeni olaylar için [araştırmanıza](investigate-incidents.md) başlayın.

Devam eden olaylar için [araştırmanıza](investigate-incidents.md) devam edin.

Çözülen olaylar için [olay sonrası gözden geçirme gerçekleştirin](first-incident-post.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olaylara öncelik belirleyin](incident-queue.md)
- [Olayları araştırın](investigate-incidents.md)
