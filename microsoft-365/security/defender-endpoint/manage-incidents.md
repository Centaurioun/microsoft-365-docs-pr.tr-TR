---
title: Uç Nokta için Microsoft Defender olaylarını yönetme
description: Olayları, atayarak, durumunu güncelleştirerek veya sınıflandırmasını ayarlayarak yönetin.
keywords: olaylar, yönetme, atama, durum, sınıflandırma, doğru uyarı, yanlış uyarı
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 289f784bc36dcb1b17ec77fff39714ceceadd704
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521531"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Uç Nokta için Microsoft Defender olaylarını yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Olayları yönetmek her siber güvenlik operasyonunun önemli bir parçasıdır. **Olaylar kuyruğundan veya Olaylar** **yönetimi bölmesinden** bir olay seçerek olayları yönetebilirsiniz. 


**Olaylar kuyruğundan** bir olay seçildiğinde, ayrıntılar için olay sayfasını açabileceğiniz **Olay yönetimi bölmesi** açılır.

:::image type="content" source="images/atp-incidents-mgt-pane-updated.png" alt-text="Olay yönetimi bölmesi" lightbox="images/atp-incidents-mgt-pane-updated.png":::

İlerleme durumlarını izlemek için olayları kendinize atayabilir, durumu ve sınıflandırmayı değiştirebilir, yeniden adlandırabilir veya bunlara açıklama ekleyebilirsiniz.

> [!TIP]
> Bir bakışta ek görünürlük için, olay adları etkilenen uç nokta sayısı, etkilenen kullanıcılar, algılama kaynakları veya kategoriler gibi uyarı özniteliklerine göre otomatik olarak oluşturulur. Bu, olayın kapsamını hızlı bir şekilde anlamanıza olanak tanır.
>
> Örneğin: *Birden çok kaynak tarafından bildirilen birden çok uç noktada çok aşamalı olay.*
>
> Otomatik olay adlandırmanın dağıtımından önce var olan olaylar adlarını korur.
>

:::image type="content" source="images/atp-incident-details-updated.png" alt-text="Olay ayrıntı sayfası" lightbox="images/atp-incident-details-updated.png":::

## <a name="assign-incidents"></a>Olayları atama
Henüz bir olay atanmamışsa, olayı kendinize atamak **için Bana ata'yı** seçebilirsiniz. Bunu yaptığınızda yalnızca olayın değil, bununla ilişkili tüm uyarıların da sahipliği varsayılır.

## <a name="set-status-and-classification"></a>Durumu ve sınıflandırmayı ayarlama
### <a name="incident-status"></a>Olay durumu
Araştırmanız ilerledikçe durumlarını değiştirerek olayları kategorilere ayırabilirsiniz ( **Etkin** veya **Çözüldü**). Bu, ekibinizin olaylara nasıl yanıt verebileceğini düzenlemenize ve yönetmenize yardımcı olur.

Örneğin, SoC analistiniz günün acil **Etkin** olaylarını gözden geçirebilir ve bunları soruşturma için kendisine atamaya karar verebilir.

Alternatif olarak, olay düzeltildiyse SoC analistiniz olayı **Çözüldü** olarak ayarlayabilir. 

### <a name="classification"></a>Sınıflandırma
Sınıflandırma ayarlamamayı seçebilir veya bir olayın doğru mu yoksa yanlış mı olduğunu belirtmeye karar vekleyebilirsiniz. Bunu yapmak, ekibin desenleri görmesine ve onlardan öğrenmesine yardımcı olur.

### <a name="add-comments"></a>Açıklama ekleme
Bir olayda yapılan önceki değişiklikleri görmek için açıklama ekleyebilir ve olayla ilgili geçmiş olayları görüntüleyebilirsiniz.

Bir uyarıda her değişiklik veya açıklama yapıldığında, bu değişiklik Açıklamalar ve geçmiş bölümüne kaydedilir.

Eklenen açıklamalar bölmede anında görünür.



## <a name="related-topics"></a>İlgili konular
- [Olay sırası](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Olay sırasını görüntüleyin ve düzenleyin](view-incidents-queue.md)
- [Olayları araştırın](investigate-incidents.md)
