---
title: Microsoft Syntex'te modeli yineleme
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te belge anlama modelini nasıl ve neden çoğaltacağınızı öğrenin.
ms.openlocfilehash: 4cacd968082bb875e9b9bfdfd1df13d87dba3cb6
ms.sourcegitcommit: ca082da1c51a3f643f152492579eef5679d52bd0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68547872"
---
# <a name="duplicate-a-model-in-microsoft-syntex"></a>Microsoft Syntex'te modeli yineleme

Yeni bir model oluşturmanız gerekiyorsa ve mevcut bir modelin ihtiyacınız olan modele çok benzer olduğunu biliyorsanız, belge anlama modelinin çoğaltılarak zaman ve çabadan tasarruf etmenize neden olabilir.

Örneğin, "Sözleşmeler" adlı mevcut bir model, çalışmanız gereken dosyaları sınıflandırır. Yeni modeliniz mevcut verilerin bir kısmını ayıklar, ancak bazı ek verileri ayıklamak için güncelleştirilmiş olması gerekir. Sıfırdan yeni bir model oluşturup eğitmek yerine, yinelenen model özelliğini kullanarak Sözleşmeler modelinin bir kopyasını oluşturabilirsiniz. Bu kopya, örnek dosyalar ve varlık ayıklayıcıları gibi tüm ilişkili eğitim öğelerini de kopyalar.

Modeli çoğalttığınızda, modeli yeniden adlandırdıktan sonra (örneğin, "Sözleşme Yenilemeleri" olarak), bu modelde güncelleştirmeler yapabilirsiniz. Örneğin, ihtiyacınız olmayan mevcut ayıklanan alanlardan bazılarını kaldırmayı seçebilir ve ardından modeli yenisini ayıklamak için eğitebilirsiniz (örneğin, "Yenileme tarihi").

## <a name="duplicate-a-model"></a>Modeli çoğalt

Belge anlama modelini yinelemek için bu adımları izleyin.

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

[Sınıflandırıcı oluştur](create-a-classifier.md)

[Modeli yeniden adlandır](rename-a-model.md)

[Ayıklayıcı oluştur](create-an-extractor.md)

[Document Understanding'e genel bakış](document-understanding-overview.md)

[Açıklama türleri](explanation-types-overview.md)

[Model uygulama](apply-a-model.md) 

[Syntex erişilebilirlik modu](accessibility-mode.md)