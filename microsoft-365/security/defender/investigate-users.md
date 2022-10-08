---
title: Microsoft 365 Defender'de kullanıcıları araştırma
description: Microsoft 365 Defender portalında bir olay için kullanıcıları araştırın.
keywords: güvenlik, kötü amaçlı yazılım, Microsoft 365, M365, güvenlik merkezi, izleme, rapor, kimlikler, veriler, cihazlar, uygulamalar, olay, analiz, yanıt
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 865ff4645c8adce9f1a25d00dbe17b86cf524f1c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68064376"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Microsoft 365 Defender'de kullanıcıları araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

Olay araştırmanızın bir bölümü kullanıcı hesaplarını içerebilir. Microsoft 365 Defender portalındaki bir olayın uyarılarında tanımlanan kullanıcı hesaplarının ayrıntılarını **Olaylar & uyarılar** \> **_olayı_*_ \> _* Kullanıcılar'dan** görebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Kullanıcılar sayfası." lightbox="../../media/investigate-incidents/incident-users.png":::

Olayın kullanıcı hesabının hızlı bir özetini almak için kullanıcı hesabı adının yanındaki onay işaretini seçin. İşte bir örnek.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Kullanıcılar sekmesi" lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> Kullanıcı sayfasında Azure Active Directory (Azure AD) kuruluşunun yanı sıra gruplar gösterilir ve bir kullanıcıyla ilişkili grupları ve izinleri anlamanıza yardımcı olur.

Bu bölmede, mevcut olaylar, etkin uyarılar ve risk düzeyi dahil olmak üzere kullanıcı tehdit bilgilerini gözden geçirebileceğiniz gibi, kullanıcı maruziyeti, hesaplar, cihazlar ve daha fazlasını da inceleyebilirsiniz.

Buna ek olarak, güvenliği aşılmış bir kullanıcıyı ele almak için doğrudan Microsoft 365 Defender portalında kullanıcı hesabının gizliliğinin ihlal edildiğini onaylama veya yeni bir oturum açma gerektirme gibi işlemler yapabilirsiniz.

Burada, kullanıcı hesabının ayrıntılarını görmek **için Kullanıcı sayfasına git'i** seçebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 Defender portalında kullanıcı hesabının ayrıntıları" lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

Bu sayfayı **, Kullanıcılar** sayfasındaki listeden kullanıcı hesabının adını seçerek de görebilirsiniz.

**Gruplar'ın** altındaki numarayı seçerek kullanıcının grup üyeliğini görebilirsiniz. Grup seçildiğinde, oluşturma tarihi ve grup üyeliği gibi ek bilgileri içeren **Gruplar** bölmesi açılır.

> [!NOTE]
> Grup üyeliği yalnızca ilk 1000 grup üyesini görüntüler.

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="Microsoft 365 Defender portalında bir kullanıcının grup üyeliği hakkındaki bilgiler" lightbox="../../media/investigate-users/user-group-membership.png":::

**Yönetici'nin** altındaki simgeyi seçerek kullanıcının kuruluş ağacında nerede olduğunu görebilirsiniz.

Microsoft 365 Defender portalı kullanıcı sayfası, Uç Nokta için Microsoft Defender, Kimlik için Microsoft Defender ve Microsoft Defender for Cloud Apps (sahip olduğunuz lisanslara bağlı olarak).

Bu sayfada, bir kullanıcı hesabının güvenlik riskine özgü bilgiler gösterilir. Bu bilgiler, riskin değerlendirilmesine yardımcı olan bir puan ve genel riske katkıda bulunan son olayları ve uyarıları gösterir.

Bu sayfadan şu ek eylemleri gerçekleştirebilirsiniz:

- Kullanıcı hesabını güvenliği aşılmış olarak işaretleme
- Kullanıcının yeniden oturum açmasını gerektir
- Kullanıcı hesabını askıya alma
- Azure AD kullanıcı hesabı ayarlarına bakın
- Kullanıcı hesabına ait dosyaları görüntüleme
- Bu kullanıcıyla paylaşılan dosyaları görüntüleyin.

İşte bir örnek.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 Defender portalındaki bir olay için kullanıcı hesabındaki eylemleri açıklayan bölüm" lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

## <a name="view-lateral-movement-paths"></a>Yanal hareket yollarını görüntüleme

**Yanal hareket yolları** sekmesini seçerek, ağınıza sızmak için kullanılabilecek bu kullanıcıya giden ve bu kullanıcıdan gelen yanal hareket yollarının görsel bir gösterimini sağlayan tam dinamik ve tıklanabilir bir harita görüntüleyebilirsiniz.

Harita, bir saldırganın hassas bir hesabın güvenliğini aşmak için bilgisayarlar veya kullanıcılar arasında kaç atlama yapmak zorunda olacağının bir listesini sağlar ve kullanıcının hassas bir hesabı varsa, kaç kaynağın ve hesabın doğrudan bağlandığını görebilirsiniz.

Son iki gün içinde varlık için olası bir yanal hareket yolu algılanamadıysa grafik görüntülenmez. Bu varlık için bulunan önceki yanal hareket yolları grafiklerini görüntülemek için Farklı bir tarihi görüntüle'yi kullanarak farklı bir tarih seçin. Yanal hareket yolu raporu, bulunan olası yanal hareket yolları hakkında bilgi sağlamak için her zaman kullanılabilir ve zamana göre özelleştirilebilir.

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="Microsoft 365 Defender portalında bir kullanıcının yanal hareket yolu" lightbox="../../media/investigate-users/lateral-movement-path.png":::

Daha fazla bilgi için bkz [. Yanal hareket yolları](/defender-for-identity/use-case-lateral-movement-path).

## <a name="next-steps"></a>Sonraki adımlar

İşlem içi olaylar için gerektiğinde [araştırmanıza](investigate-incidents.md) devam edin.

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olaylara öncelik belirleyin](incident-queue.md)
- [Olayları yönetin](manage-incidents.md)
