---
title: Microsoft 365 Defender'da Kimlik için Microsoft Defender algılama dışlamaları
description: Microsoft 365 Defender'da Kimlik için Microsoft Defender algılama dışlamalarını yapılandırmayı öğrenin.
ms.date: 11/02/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 66b9de2b9ab8d1a6026647f527495ed2f178fd58
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682657"
---
# <a name="configure-defender-for-identity-detection-exclusions-in-microsoft-365-defender"></a>Microsoft 365 Defender'de Kimlik algılama dışlamaları için Defender'ı yapılandırma

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede, [Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) algılama dışlamalarının nasıl yapılandırılır [açıklanmaktadır.](/microsoft-365/security/defender/overview-security-center)

> [!IMPORTANT]
> Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

[!INCLUDE [Product long](includes/product-long.md)] belirli IP adreslerinin, bilgisayarların, etki alanlarının veya kullanıcıların çeşitli algılamalardan dışlanmasını sağlar.

Örneğin, **DNS Keşif** uyarısı, DNS'yi tarama mekanizması olarak kullanan bir güvenlik tarayıcısı tarafından tetiklenebilir. Dışlama oluşturmak, Kimlik için Defender'ın bu tür tarayıcıları yoksaymalarına ve hatalı pozitif sonuçları azaltmalarına yardımcı olur.

>[!NOTE]
>DNS uyarıları [üzerinden şüpheli iletişim](/defender-for-identity/exfiltration-alerts#suspicious-communication-over-dns-external-id-2031) açılan en yaygın etki alanlarından, müşterilerin uyarının dışında en çok dışlandığı etki alanlarını gözlemledik. Bu etki alanları varsayılan olarak dışlamalar listesine eklenir, ancak bunları kolayca kaldırma seçeneğiniz vardır.

## <a name="how-to-add-detection-exclusions"></a>Algılama dışlamaları ekleme

1. [Microsoft 365 Defender'da](https://security.microsoft.com/) **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ad sütunundaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

1. Ardından sol taraftaki menüde **Dışlanan varlıklar'ı** görürsünüz.

   :::image type="content" source="../../media/defender-identity/excluded-entities.png" alt-text="Dışlanan varlıklar bölmesi" lightbox="../../media/defender-identity/excluded-entities.png":::

Ardından dışlamaları iki yöntemle ayarlayabilirsiniz: **Algılama kuralına göre dışlamalar** ve **Genel dışlanan varlıklar**.

## <a name="exclusions-by-detection-rule"></a>Algılama kuralına göre dışlamalar

1. Sol taraftaki menüde **Algılama kuralına göre dışlamalar'ı** seçin. Algılama kurallarının listesini görürsünüz.

   :::image type="content" source="../../media/defender-identity/exclusions-by-detection-rule.png" alt-text="Sol bölmedeki Dışlanan varlıklar öğesindeki Algılama kuralına göre dışlamalar seçeneği" lightbox="../../media/defender-identity/exclusions-by-detection-rule.png":::

1. Yapılandırmak istediğiniz her algılama için aşağıdaki adımları uygulayın:

    1. Kuralı seçin. Arama çubuğunu kullanarak algılamaları arayabilirsiniz. Seçildikten sonra algılama kuralı ayrıntılarını içeren bir bölme açılır.

       :::image type="content" source="../../media/defender-identity/detection-rule-details.png" alt-text="Algılama kuralının ayrıntıları" lightbox="../../media/defender-identity/detection-rule-details.png":::

    1. Dışlama eklemek için **Dışlanan varlıklar** düğmesini ve ardından dışlama türünü seçin. Her kural için farklı dışlanmış varlıklar kullanılabilir. Kullanıcılar, cihazlar, etki alanları ve IP adreslerini içerir. Bu örnekte, seçenekler **Cihazları dışla** ve **IP adreslerini hariç tut seçenekleridir**.

       :::image type="content" source="../../media/defender-identity/exclude-devices-or-ip-addresses.png" alt-text="Cihazları veya IP adreslerini dışlama seçeneği" lightbox="../../media/defender-identity/exclude-devices-or-ip-addresses.png":::

    1. Dışlama türünü seçtikten sonra dışlamayı ekleyebilirsiniz. Açılan bölmede dışlama eklemek için düğmeyi seçin **+** .

       :::image type="content" source="../../media/defender-identity/add-exclusion.png" alt-text="Dışlama ekleme seçeneği" lightbox="../../media/defender-identity/add-exclusion.png":::

    1. Ardından dışlanacak varlığı ekleyin. Varlığı listeye eklemek için **+ Ekle'yi** seçin.

       :::image type="content" source="../../media/defender-identity/add-excluded-entity.png" alt-text="Dışlanacak varlığı ekleme seçeneği" lightbox="../../media/defender-identity/add-excluded-entity.png":::

    1. Ardından dışlamayı tamamlamak için **IP adreslerini dışla** 'yı (bu örnekte) seçin.

       :::image type="content" source="../../media/defender-identity/exclude-ip-addresses.png" alt-text="IP adreslerini dışlama seçeneği" lightbox="../../media/defender-identity/exclude-ip-addresses.png":::

    1. Dışlamalar ekledikten sonra **Dışlanan varlıklar** düğmesine dönerek listeyi dışarı aktarabilir veya dışlamaları kaldırabilirsiniz. Bu örnekte Cihazları **dışla'ya** geri döndük. Listeyi dışarı aktarmak için aşağı ok düğmesini seçin.

       :::image type="content" source="../../media/defender-identity/return-to-exclude-devices.png" alt-text="Cihazları Dışlamaya Dön seçeneği" lightbox="../../media/defender-identity/return-to-exclude-devices.png":::

    1. Bir dışlama silmek için dışlama'yı seçin ve çöp kutusu simgesini seçin.

       :::image type="content" source="../../media/defender-identity/delete-exclusion.png" alt-text="Dışlama sil seçeneği" lightbox="../../media/defender-identity/delete-exclusion.png":::

## <a name="global-excluded-entities"></a>Genel dışlanan varlıklar

Artık Dışlamaları **Genel dışlanan varlıklara** göre de yapılandırabilirsiniz. Genel dışlamalar, Kimlik için Defender'ın tüm algılamalarında dışlanacak belirli varlıkları (IP adresleri, alt ağlar, cihazlar veya etki alanları) tanımlamanızı sağlar. Bu nedenle, örneğin, bir cihazı dışlarsanız, yalnızca algılamanın bir parçası olarak cihaz tanımlamasına sahip olan algılamalar için geçerli olur.

1. Sol taraftaki menüde Genel **dışlanan varlıklar'ı** seçin. Dışlayabileceğiniz varlık kategorilerini görürsünüz.

   :::image type="content" source="../../media/defender-identity/global-excluded-entities.png" alt-text="Genel dışlanan varlıklar alt menüsü öğesi" lightbox="../../media/defender-identity/global-excluded-entities.png":::

1. Bir dışlama türü seçin. Bu örnekte **Etki alanlarını dışla'yı** seçtik.

   :::image type="content" source="../../media/defender-identity/exclude-domains.png" alt-text="Etki Alanları sekmesi" lightbox="../../media/defender-identity/exclude-domains.png":::

1. Dışlanacak bir etki alanı ekleyebileceğiniz bir bölme açılır. Dışlamak istediğiniz etki alanını ekleyin.

   :::image type="content" source="../../media/defender-identity/add-excluded-domain.png" alt-text="Dışlanacak bir etki alanı ekleme seçeneği" lightbox="../../media/defender-identity/add-excluded-domain.png":::

1. Etki alanı listeye eklenir. **Dışlamayı tamamlamak için Etki alanlarını dışla'yı** seçin.

   :::image type="content" source="../../media/defender-identity/select-exclude-domains.png" alt-text="Dışlanacak etki alanlarını seçme seçeneği" lightbox="../../media/defender-identity/select-exclude-domains.png":::

1. Ardından tüm algılama kurallarının dışında tutulacak varlık listesinde etki alanını görürsünüz. Listeyi dışarı aktarabilir veya varlıkları seçip **Kaldır** düğmesine tıklayarak kaldırabilirsiniz.

   :::image type="content" source="../../media/defender-identity/global-excluded-entries-list.png" alt-text="Genel dışlanan girdilerin listesi" lightbox="../../media/defender-identity/global-excluded-entries-list.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Kimlik için Defender güvenlik uyarılarını yönetme](manage-security-alerts.md)
