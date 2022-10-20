---
title: Cihaz etiketlerini oluşturun ve yönetin
description: Bağlamı yakalamak ve bir olayın parçası olarak dinamik liste oluşturmayı etkinleştirmek için cihazları gruplandırmak için cihaz etiketlerini kullanma
keywords: etiketler, cihaz etiketleri, cihaz grupları, gruplar, düzeltme, düzey, kurallar, aad grubu, rol, atama, derecelendirme
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
ms.openlocfilehash: 21c86977c965c63e25822b9248a742ef48e1f647
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633757"
---
# <a name="create-and-manage-device-tags"></a>Cihaz etiketlerini oluşturun ve yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mantıksal bir grup ilişkisi oluşturmak için cihazlara etiketler ekleyin. Cihaz etiketleri, ağın uygun şekilde eşlenmesini destekleyerek bağlamı yakalamak için farklı etiketler eklemenize ve bir olayın parçası olarak dinamik liste oluşturmayı etkinleştirmenizi sağlar. Etiketler **, Cihaz envanteri** görünümünde filtre olarak veya cihazları gruplandırmak için kullanılabilir. Cihaz gruplandırma hakkında daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md).

> [!NOTE]
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

Cihazlara etiket eklemek için aşağıdaki yöntemleri kullanabilirsiniz:

- Portalı kullanma
- Kayıt defteri anahtarı değeri ayarlama

> [!NOTE]
> Bir etiketin cihaza eklenmesi ile cihaz listesinde ve cihaz sayfasında kullanılabilirliği arasında bir gecikme olabilir.

API kullanarak cihaz etiketleri eklemek için bkz. [Cihaz etiketleri API'si ekleme veya kaldırma](add-or-remove-machine-tags.md).

## <a name="add-and-manage-device-tags-using-the-portal"></a>Portalı kullanarak cihaz etiketleri ekleyin ve yönetin

1. Etiketleri yönetmek istediğiniz cihazı seçin. Aşağıdaki görünümlerden herhangi birinden bir cihaz seçebilir veya arayabilirsiniz:

   - **Uyarıları kuyruğu** - Uyarılar kuyruğundan cihaz simgesinin yanındaki cihaz adını seçin.
   - **Cihaz envanteri - Cihaz** listesinden cihaz adını seçin.
   - **Arama kutusu** - Açılan menüden Cihaz'ı seçin ve cihaz adını girin.

     Ayrıca, uyarı sayfasına dosya ve IP görünümleri aracılığıyla da ulaşabilirsiniz.

2. Yanıt eylemleri satırında **Etiketleri yönet'i** seçin.

    :::image type="content" source="images/manage-tags-option.png" alt-text="Etiketleri yönet düğmesinin resmi" lightbox="images/manage-tags-option.png":::
    

3. Etiketleri bulmak veya oluşturmak için yazın

    :::image type="content" source="images/create-new-tag.png" alt-text="Cihaza etiket ekleme1" lightbox="images/create-new-tag.png":::

Etiketler cihaz görünümüne eklenir ve **cihazlar envanter** görünümüne de yansıtılır. Ardından **, ilgili** cihaz listesini görmek için Etiketler filtresini kullanabilirsiniz.

> [!NOTE]
> Filtreleme parantez içeren etiket adlarında çalışmayabilir.
>
> Yeni bir etiket oluşturduğunuzda, mevcut etiketlerin listesi görüntülenir. Listede yalnızca portal aracılığıyla oluşturulan etiketler gösterilir. İstemci cihazlarından oluşturulan mevcut etiketler görüntülenmez.

Etiketleri bu görünümden de silebilirsiniz.

:::image type="content" source="images/new-tag-label-display.png" alt-text="Cihaza etiket ekleme2" lightbox="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Kayıt defteri anahtarı değeri ayarlayarak cihaz etiketleri ekleme

> [!NOTE]
> Yalnızca aşağıdaki cihazlarda geçerlidir:
>
> - Windows 11
> - Windows 10, sürüm 1709 veya üzeri
> - Windows Server, sürüm 1803 veya üzeri
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> Etikette ayarlanabilecek karakter sayısı üst sınırı 200'dür.

Benzer etiketlere sahip cihazlar, belirli bir cihaz listesine bağlamsal eylem uygulamanız gerektiğinde kullanışlı olabilir.

Cihaza etiket eklemek için aşağıdaki kayıt defteri anahtarı girişini kullanın:

- Kayıt defteri anahtarı: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Kayıt defteri anahtarı değeri (REG_SZ): `Group`
- Kayıt defteri anahtarı verileri: `Name of the tag you want to set`

> [!NOTE]
> Cihaz etiketi, günde bir kez oluşturulan cihaz bilgileri raporunun bir parçasıdır. Alternatif olarak, yeni bir cihaz bilgileri raporunu aktaracak uç noktayı yeniden başlatmayı seçebilirsiniz.
>
> Yukarıdaki Kayıt Defteri anahtarı kullanılarak eklenen bir etiketi kaldırmanız gerekiyorsa, 'Group' anahtarını kaldırmak yerine Kayıt defteri anahtarı verilerinin içeriğini temizleyin.
