---
title: Olaylar için Akış ayarlamak için Power Automate Bağlayıcısı'nı kullanma
ms.reviewer: ''
description: Kiracınızda yeni bir olay oluştuğunda tetiklenecek bir akış oluşturmak için Uç Nokta için Microsoft Defender Flow bağlayıcısını kullanın.
keywords: akış, desteklenen api'ler, api, Microsoft flow, sorgu, otomasyon, power automate
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 0b90fd4ecade2f79cac895c61a4a7327de8aaf66
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701972"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>Olaylar için Akış ayarlamak için Power Automate Bağlayıcısı'nı kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Güvenlik yordamlarının otomatikleştirilmesi, her modern Güvenlik İşlem Merkezi (SOC) için standart bir gereksinimdir. SOC ekiplerinin en verimli şekilde çalışması için otomasyon şarttır. Otomatik iş akışları oluşturmanıza ve birkaç dakika içinde uçtan uca yordam otomasyonu oluşturmanıza yardımcı olması için Microsoft Power Automate'i kullanın. Microsoft Power Automate tam olarak bunun için oluşturulmuş farklı bağlayıcıları destekler.  

Kiracınızda yeni bir uyarı oluşturulduğunda olduğu gibi bir olay tarafından tetiklenen otomasyonlar oluşturma konusunda size yol göstermek için bu makaleyi kullanın. Microsoft Defender API'sinde birçok özelliğe sahip resmi bir Power Automate Bağlayıcısı vardır. 

:::image type="content" source="images/api-flow-0.png" alt-text="Microsoft Defender 365 portalındaki Eylemler sayfası" lightbox="images/api-flow-0.png" :::

> [!NOTE]
> Premium bağlayıcı lisanslama önkoşulları hakkında daha fazla ayrıntı için bkz. [Premium bağlayıcılar için lisanslama](/power-automate/triggers-introduction#licensing-for-premium-connectors).

## <a name="usage-example"></a>Kullanım örneği

Aşağıdaki örnekte, kiracınızda yeni bir Uyarı oluştuğunda tetiklenen bir Flow'un nasıl oluşturulacağı gösterilmektedir. Akışı başlatan olayı ve bu tetikleyici gerçekleştiğinde gerçekleştirilecek sonraki eylemi tanımlama konusunda size yol gösterilir.  

1. [Microsoft Power Automate'te](https://flow.microsoft.com) oturum açın.

2. **Akışlarım** \> **Yeni** \> **Otomatikleştirilmiş- boş bölümüne** gidin.

    :::image type="content" source="images/api-flow-1.png" alt-text="Microsoft Defender 365 portalında Akışlarım menü öğesinin altındaki Yeni akış bölmesi" lightbox="images/api-flow-1.png":::

3. Akışınız için bir ad seçin, tetikleyici olarak "Microsoft Defender ATP Tetikleyicileri" ifadesini arayın ve ardından yeni Uyarılar tetikleyicisini seçin.

    :::image type="content" source="images/api-flow-2.png" alt-text=" Microsoft Defender 365 portalında Akışınızın tetikleyicisini seçin bölümü" lightbox="images/api-flow-2.png" :::

Artık her yeni Uyarı gerçekleştiğinde tetiklenen bir Akışa sahipsiniz.

:::image type="content" source="images/api-flow-3.png" alt-text="Tetikleyici açıklaması" lightbox="images/api-flow-3.png":::

Şimdi yapmanız gereken tek şey sonraki adımlarınızı seçmektir.
Örneğin, Uyarının Önem Derecesi Yüksekse cihazı yalıtabilir ve bu konuda bir e-posta gönderebilirsiniz.
Uyarı tetikleyicisi yalnızca Uyarı Kimliği ve Makine Kimliği sağlar. Bu varlıkları genişletmek için bağlayıcıyı kullanabilirsiniz.

### <a name="get-the-alert-entity-using-the-connector"></a>Bağlayıcıyı kullanarak Uyarı varlığını alma

1. Yeni adım için **Microsoft Defender ATP'yi** seçin.

2. **Uyarılar - Tek uyarı API'si alma'yı** seçin.

3. Son adımdaki **Uyarı Kimliğini** **Giriş** olarak ayarlayın.

    :::image type="content" source="images/api-flow-4.png" alt-text="Uyarılar bölmesi"  lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Uyarının önem derecesi Yüksekse cihazı yalıtma

1. **Koşul'u** yeni bir adım olarak ekleyin.

2. Uyarı önem derecesinin **Yüksek'e eşit** olup olmadığını denetleyin.

   Evet ise, Makine Kimliği ve açıklama ile **Microsoft Defender ATP - Makineyi yalıt** eylemini ekleyin.

    :::image type="content" source="images/api-flow-5.png" alt-text="Eylemler bölmesi"  lightbox="images/api-flow-5.png":::

3. Uyarı ve Yalıtım hakkında e-posta göndermeye yönelik yeni bir adım ekleyin. Outlook veya Gmail gibi kullanımı çok kolay birden çok e-posta bağlayıcısı vardır.

4. Akışınızı kaydedin.

Gelişmiş Tehdit Avcılığı sorguları ve çok daha fazlasını çalıştıran **zamanlanmış** bir akış da oluşturabilirsiniz!

## <a name="related-topic"></a>İlgili konu
- [api'leri Uç Nokta için Microsoft Defender](apis-intro.md)
