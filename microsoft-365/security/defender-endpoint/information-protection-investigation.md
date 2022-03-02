---
title: Olay yanıtını önceliklendirmek için duyarlılık etiketlerini kullanma
description: Olayları önceliklendirmek ve araştırmak için duyarlılık etiketlerini kullanmayı öğrenin
keywords: bilgi, koruma, veri, kayıp, önleme,etiketler, dlp, olay, araştırma, araştırma
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a1cafe4cd54b7313e0555127221173e23a41bbf
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2021
ms.locfileid: "62997039"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Olay yanıtını önceliklendirmek için duyarlılık etiketlerini kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aşağıdakiler için geçerlidir:**
- [Uç Nokta Planı 1 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta Planı 2 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Defender'ı deneyimli yapmak mı istiyor musunuz? [Ücretsiz deneme için kaydol'](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Tipik bir kalıcı gelişmiş tehdit yaşam döngüsü, veri sızıntısını içerir. Bir güvenlik olayında, kurumsal verilerin ve bilgilerin korunması için hassas dosyaların tehlikeye atıldığı soruşturmalara öncelik sırasına sahip olmak önemlidir.

Uç Nokta için Defender, duyarlılık etiketlerinin kullanımıyla güvenlik olaylarının önceliklendirmesini çok daha basit hale getirmek için yardımcı olur. Duyarlılık etiketleri, gizli bilgiler gibi hassas bilgilerle ilgili cihazlarla ilgili olayları hızla tanır.

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Hassas veriler içeren olayları araştırma

Olay araştırmalarını önceliklendirmek için veri duyarlılığı etiketlerini kullanmayı öğrenin.

> [!NOTE]
> Etiketler Windows 10, sürüm 1809 sonraki Windows 10, sürüm 1809 için algılanır ve Windows 11.

1. Portalda Microsoft 365 Defender Olayları **ve Uyarıları &'ı** \> **seçin**.

2. Veri duyarlılığı sütununu görmek için **ekranı sağa kaydırın** . Bu sütun, olaylarla ilgili cihazlarda gözlemlenen duyarlılık etiketlerini yansıtmalı ve hassas dosyaların olaydan etkilenebilir olup olmadığının göstergesini sağlar.

    ![Veri duyarlılığı sütun resmi.](images/data-sensitivity-column.png)

    Ayrıca, Veri duyarlılığına dayalı **olarak filtre de ebilirsiniz**

    ![Veri duyarlılık filtresinin resmi.](images/data-sensitivity-filter.png)

3. Daha fazla araştırma yapmak için olay sayfasını açın.

    ![Olay sayfası ayrıntılarının görüntüsü.](images/incident-page.png)

4. Duyarlılık etiketleri **olan** dosyaların depolanması cihazlarını tanımlamak için Cihazlar sekmesini seçin.

    ![Cihaz sekmesinin resmi.](images/investigate-devices-tab.png)

5. Hassas verileri depoyan cihazları seçin ve hangi dosyaların etki olacağını belirlemek için zaman çizelgesinde arama ekleyin, sonra verilerin korunmasını sağlamak için uygun önlemleri alabilirsiniz.

   Veri duyarlılığı etiketlerini arayarak cihaz zaman çizelgesinde gösterilen etkinlikleri daraltabilirsiniz. Bunu yapmak yalnızca etiket adı adı olan dosyalarla ilişkilendirilmiş olayları gösterir.

    ![Etikete göre arama sonuçlarını daraltmış olarak cihaz zaman çizelgesinin resmi.](images/machine-timeline-labels.png)

> [!TIP]
> Bu veri noktaları ayrıca gelişmiş avlarda 'DeviceFileEvents' aracılığıyla da ortaya çıkar ve gelişmiş sorguların ve algılamanın hesap duyarlılığı etiketlerini ve dosya koruma durumunu dikkate almalarını sağlar.