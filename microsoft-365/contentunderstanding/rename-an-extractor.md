---
title: Microsoft Syntex'te ayıklayıcıyı yeniden adlandırma
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
description: Microsoft Syntex'te ayıklayıcıyı nasıl ve neden yeniden adlandıracağınızı öğrenin.
ms.openlocfilehash: 8900eb68a5efab4d69911d193c35e82e6d58cbf6
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565652"
---
# <a name="rename-an-extractor-in-microsoft-syntex"></a>Microsoft Syntex'te ayıklayıcıyı yeniden adlandırma

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
