---
title: Otomasyon klasörü dışlamalarını yönetin
description: Otomatik araştırmanın dışında tutulan dosyaları denetlemek için otomasyon klasörü dışlamaları ekleyin.
keywords: yönetme, otomasyon, dışlama, engelleme, temiz, kötü amaçlı
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
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d7dd4fd8fe8961bc18dccc4720effc62de493768
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633713"
---
# <a name="manage-automation-folder-exclusions"></a>Otomasyon klasörü dışlamalarını yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Otomasyon klasörü dışlamaları, Otomatik araştırmanın atlanacağı klasörleri belirtmenize olanak tanır.

Atlanması istediğiniz klasörle ilgili aşağıdaki öznitelikleri denetleyebilirsiniz:

- **Klasörler**: Atlanacak klasörü ve alt klasörlerini belirtebilirsiniz.

  > [!NOTE]
  > Şu anda, bir dizin altındaki dosyaları dışlamanın bir yolu olarak joker karakterlerin kullanılması henüz desteklenmiyor.

- **Dosyaların uzantıları**: Belirli bir dizinde hariç tutulacak uzantıları belirtebilirsiniz. Uzantılar, saldırganın bir açıktan yararlanmayı gizlemek için dışlanan bir klasör kullanmasını önlemenin bir yoludur. Uzantılar hangi dosyaların yoksayılacağını açıkça tanımlar.

- **Dosya adları**: Belirli bir dizinde dışlanmasını istediğiniz dosya adlarını belirtebilirsiniz. Adlar, saldırganın bir açıktan yararlanmayı gizlemek için dışlanan bir klasör kullanmasını önlemenin bir yoludur. Adlar hangi dosyaların yoksayılacağını açıkça tanımlar.

## <a name="add-an-automation-folder-exclusion"></a>Otomasyon klasörü dışlama ekleme

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Kuralları** \> **Otomasyon klasörü dışlamaları'nı** seçin.

2. **Yeni klasör dışlama'ya** tıklayın.

3. Klasör ayrıntılarını girin:

    - Klasör
    - Uzantı -ları
    - Dosya adları
    - Açıklama

4. **Kaydet**'e tıklayın.

> [!NOTE]
> Dışlanan dosyaları toplamak veya incelemek için Canlı Yanıt komutları şu hatayla başarısız olur: "Dosya dışlandı". Ayrıca, otomatik araştırmalarda dışlanan öğeler yoksayılır.

## <a name="edit-an-automation-folder-exclusion"></a>Otomasyon klasörü dışlama düzenleme

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Kuralları** \> **Otomasyon klasörü dışlamaları'nı** seçin.
2. Klasör dışlamada **Düzenle'ye** tıklayın.
3. Kuralın ayrıntılarını güncelleştirin ve **Kaydet'e** tıklayın.

## <a name="remove-an-automation-folder-exclusion"></a>Otomasyon klasörü dışlamasını kaldırma

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Kuralları** \> **Otomasyon klasörü dışlamaları'nı** seçin.
2. **Dışlama kaldır'a** tıklayın.

## <a name="related-topics"></a>İlgili konular

- [Otomasyona izin verilen/engellenen listeleri yönetme](manage-indicators.md)
- [Otomasyon dosyası yüklemelerini yönetin](manage-automation-file-uploads.md)
