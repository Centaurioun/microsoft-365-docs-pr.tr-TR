---
title: Microsoft SharePoint Syntex'de ayıklayıcıyı yeniden adlandırma
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
description: Microsoft SharePoint Syntex'da ayıklayıcıyı nasıl ve neden yeniden adlandıracağınızı öğrenin.
ms.openlocfilehash: 81c325e937378b5c00bac354f14e43d9ab676724
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67576835"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex'de ayıklayıcıyı yeniden adlandırma

Ayıklanan bir veri alanına farklı bir adla başvurmak istiyorsanız, bir noktada ayıklayıcıyı yeniden adlandırmanız gerekebilir. Örneğin, kuruluşunuz sözleşme belgelerinde değişiklik yapmaya karar verir ve belgelerinde "müşteriler"i "müşteriler" olarak ifade eder. Modelinizde bir "Müşteri" alanı ayıkladıysanız, alanı "İstemci" olarak yeniden adlandırmayı seçebilirsiniz.

Güncelleştirilmiş modelinizi SharePoint belge kitaplığınızla eşitlediğinizde, belge kitaplığı görünümünüzde yeni bir "İstemci" sütunu görürsünüz. Görünümünüz geçmiş etkinlikler için "Müşteri" sütununu korur, ancak modeliniz tarafından işlenen tüm yeni belgeler için yeni "İstemci" sütununu güncelleştirir. 

> [!IMPORTANT]
>  Güncelleştirilmiş modelinizi, yeni sütun adının görüntülenmesi için daha önce uyguladığınız belge kitaplıklarına eşitlediğinizden emin olun. 

## <a name="rename-an-extractor"></a>Ayıklayıcıyı yeniden adlandır

Varlık ayıklayıcısını yeniden adlandırmak için bu adımları izleyin.

1. model listenizi görmek için içerik merkezinde **Modeller'i** seçin.

2. **Modeller** sayfasındaki **Ad** sütununda, ayıklayıcıyı yeniden adlandırmak istediğiniz modeli seçin.

3. **Varlık ayıklayıcıları'nın** altında, yeniden adlandırmak istediğiniz ayıklayıcının adını seçin ve ardından **Yeniden Adlandır'ı** seçin.

    ![Yeniden Adlandır seçeneğinin vurgulandığı seçili ayıklayıcıyı gösteren Varlık ayıklayıcıları bölümünün ekran görüntüsü.](../media/content-understanding/entity-extractor-rename.png) 

4. **Varlık ayıklayıcısını yeniden adlandır** panelinde:

   a. **Yeni ad'ın** altında ayıklayıcının yeni adını girin.

    ![Varlık ayıklayıcı panelini gösteren ekran görüntüsü.](../media/content-understanding/rename-entity-extractor-panel.png) 

   b. (İsteğe bağlı) **Gelişmiş ayarlar'ın** altında, var olan bir site sütununu ilişkilendirmek isteyip istemediğinizi seçin.

5. **Yeniden Adlandır'ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.
[Ayıklayıcı oluştur](create-an-extractor.md)

[Sınıflandırıcı oluştur](create-a-classifier.md)

[Modeli yeniden adlandır](rename-a-model.md)

[Açıklama türleri](explanation-types-overview.md)

[Ayıklayıcı oluştururken terim deposu taksonomisini kullan](leverage-term-store-taxonomy.md)

[Document Understanding'e genel bakış](document-understanding-overview.md)

[Model uygulama](apply-a-model.md) 
