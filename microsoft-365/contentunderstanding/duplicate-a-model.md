---
title: Microsoft Syntex'te modeli yineleme
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te modeli nasıl ve neden çoğaltacağınızı öğrenin.
ms.openlocfilehash: 88860487d14a7a4bab3742f610854623cc8f681d
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660785"
---
# <a name="duplicate-a-model-in-microsoft-syntex"></a>Microsoft Syntex'te modeli yineleme

<sup>**Şunlar için geçerlidir:**  &ensp; Yapılandırılmamış belge işlemeyi &#10003;</sup>

Yapılandırılmamış bir belge işleme modelini çoğaltmak, yeni bir model oluşturmanız ve mevcut bir modelin ihtiyacınız olan modele çok benzer olduğunu bilmeniz gerektiğinde zaman ve çabadan tasarruf etmenizi sağlayabilir.

Örneğin, "Sözleşmeler" adlı mevcut bir model, çalışmanız gereken dosyaları sınıflandırır. Yeni modeliniz mevcut verilerin bir kısmını ayıklar, ancak bazı ek verileri ayıklamak için güncelleştirilmiş olması gerekir. Sıfırdan yeni bir model oluşturup eğitmek yerine, yinelenen model özelliğini kullanarak Sözleşmeler modelinin bir kopyasını oluşturabilirsiniz. Bu kopya, örnek dosyalar ve varlık ayıklayıcıları gibi tüm ilişkili eğitim öğelerini de kopyalar.

Modeli çoğalttığınızda, modeli yeniden adlandırdıktan sonra (örneğin, "Sözleşme Yenilemeleri" olarak), bu modelde güncelleştirmeler yapabilirsiniz. Örneğin, ihtiyacınız olmayan mevcut ayıklanan alanlardan bazılarını kaldırmayı seçebilir ve ardından modeli yenisini ayıklamak için eğitebilirsiniz (örneğin, "Yenileme tarihi").

## <a name="duplicate-a-model"></a>Modeli çoğalt

Yapılandırılmamış belge işleme modellerini yinelemek için bu adımları izleyin.

1. model listenizi görmek için içerik merkezinde **Modeller'i** seçin.

2. **Modeller** sayfasında, çoğaltmak istediğiniz modeli seçin.

3. Şeridi veya **Eylemleri göster** düğmesini (model adının yanında) kullanarak **Çoğalt'ı** seçin.</br>

    ![Yinelenen seçenekler vurgulanmış olarak seçili modeli gösteren Modeller sayfasının ekran görüntüsü.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. **Yinelenen model** panelinde:

   a. **Ad'ın** altında, çoğaltmak istediğiniz modelin yeni adını girin.</br>

    ![Yinelenen model panelini gösteren ekran görüntüsü.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. **Açıklama'nın** altında yeni modelinizin açıklamasını ekleyin.

   c. (İsteğe bağlı) **Gelişmiş ayarlar'ın** altında mevcut [bir içerik türünü](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) ilişkilendirmek isteyip istemediğinizi seçin.

5. **Çoğalt'ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Modeli yeniden adlandır](rename-a-model.md)

[Syntex erişilebilirlik modu](accessibility-mode.md)