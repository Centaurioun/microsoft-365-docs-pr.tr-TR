---
title: İş için Microsoft Defender'da tehditlere yanıt verme ve tehditleri azaltma
description: İş için Defender'da tehditler algılandığından, bu tehditlere yanıt vermek için eylemler gerçekleştirebilirsiniz. Cihaz envanteri görünümünü nasıl kullanacağınızı görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 09/14/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: f2a7f09807c4c17da30fab8fb3ca1eb2d6f4fa70
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67710619"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'da tehditlere yanıt verme ve tehditleri azaltma

Microsoft 365 Defender portalı, güvenlik ekibinizin algılanan tehditlere yanıt vermesini ve tehditleri azaltmasını sağlar. Bu makalede, İş için Defender'ı nasıl kullanabileceğinize ilişkin bir örnek açıklanabilir.


## <a name="view-detected-threats"></a>Algılanan tehditleri görüntüleme

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Giriş sayfasındaki kartlara dikkat edin. Kartlarda kaç tehdit algılandığı ve kaç kullanıcı hesabının, uç noktanın (cihazın) ve diğer varlıkların etkilendiği bir bakışta gösterilir. Aşağıdaki görüntüde görebileceğiniz bir kart örneği verilmiştir:

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="Microsoft 365 Defender portalındaki kartların ekran görüntüsü":::

3. Daha fazla bilgi görüntülemek ve işlem yapmak için kartta bir düğme veya bağlantı seçin. Örnek olarak, **Risk altındaki cihazlar** kartımızda **Ayrıntıları görüntüle** düğmesi bulunur. Bu düğmeyi seçmek, aşağıdaki görüntüde gösterildiği gibi bizi **Cihazlar** listesine götürür:

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Cihaz envanterinin ekran görüntüsü":::

   **Cihazlar** sayfası, şirket cihazlarının yanı sıra risk düzeylerini ve maruz kalma düzeylerini listeler.

4. Cihaz gibi bir öğe seçin. Bir açılır pencere bölmesi açılır ve aşağıdaki görüntüde gösterildiği gibi bu öğe için oluşturulan uyarılar ve olaylar hakkında daha fazla bilgi görüntüler:  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Seçili cihaz için açılır pencere bölmesinin ekran görüntüsü":::

5. Açılır öğede görüntülenen bilgileri görüntüleyin. Aşağıdaki görüntüde gösterildiği gibi kullanılabilir eylemlerin listelendiğini belirten bir menü açmak için üç noktayı (...) seçin: 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Seçili cihaz için kullanılabilir eylemlerin ekran görüntüsü":::

6. Kullanılabilir bir eylem seçin. Örneğin, Microsoft Defender Virüsten Koruma'nın cihazda hızlı bir tarama başlatmasına neden olacak **virüsten koruma taraması çalıştır'ı** seçebilirsiniz. Alternatif olarak, cihazda otomatik bir araştırma tetikleme için **Otomatik Araştırma Başlat'ı** da seçebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)
- [İş için Defender'da cihazları yönetme](mdb-manage-devices.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
