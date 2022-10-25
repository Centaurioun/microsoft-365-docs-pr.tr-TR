---
title: Microsoft Edge'de eBulma Dışarı Aktarma Aracı'nı kullanma
description: Güvenlik ve uyumluluk portalında İçerik Arama ve eKeşif'ten arama sonuçlarını indirmek için Microsoft Edge'in en yeni sürümünü kullanmak için ClickOnce desteğini etkinleştirmeniz gerekir.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 31e8937ba83bc1612f2396040b16563fd3dbea9e
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688641"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Microsoft Edge'de eBulma Dışarı Aktarma Aracı'nı kullanma

Microsoft Edge'in en yeni sürümünde yapılan son değişikliklerin sonucunda ClickOnce desteği artık varsayılan olarak etkin değildir. İçerik Arama veya eBulma arama sonuçlarını indirmek için eBulma Dışarı Aktarma Aracı'nı kullanmaya devam etmek için [Microsoft Internet Explorer'ı](https://support.microsoft.com/help/17621/internet-explorer-downloads) kullanmanız veya Microsoft Edge'in en yeni sürümünde ClickOnce desteğini etkinleştirmeniz gerekir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Microsoft Edge'de ClickOnce desteğini etkinleştirme

1. Microsoft Edge'de **edge://flags/#edge-click-once** gidin.

2. Açılan listede mevcut değer **Varsayılan** veya **Devre Dışı** olarak ayarlandıysa, **etkin** olarak değiştirin.

   ![Açılan listeden Etkin'i seçin.](../media/ClickOnceimage1.png)

3. Tarayıcı penceresinin en altına kadar aşağı kaydırın ve Microsoft Edge'i yeniden başlatmak için **Yeniden Başlat'ı** seçin.

   ![Yeniden Başlat'a tıklayın.](../media/ClickOnceimage2.png)

**Not:** Kuruluşlar ClickOnce desteğini devre dışı bırakmak için grup ilkesi kullanabilir. ClickOnce desteği için bir kuruluş ilkesi olup olmadığını denetlemek için **edge://policy** gidin. Aşağıdaki ekran görüntüsünde ClickOnce'un tüm kuruluş genelinde etkinleştirildiği gösterilmektedir. Bu ilke değeri **false** olarak ayarlanırsa, kuruluşunuzdaki bir yöneticiye başvurmanız gerekir.

![Edge kuruluş ilkelerinin listesi.](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>eBulma Dışarı Aktarma Aracı'nı yükleme ve çalıştırma

1. İçerik Arama'da veya eBulma durumundaki dışarı aktarmanın açılır sayfasında **Sonuçları indir'i** seçin.

   ![Arama sonuçlarını indirmek için açılır sayfada Sonuçları indir'e tıklayın.](../media/ClickOnceExport1.png)

2. Aracı başlatmanız için bir onay istenir ve **Aç'ı** seçin.

   ![eBulma Dışarı Aktarma Aracı'nı başlatmak için Aç'a tıklayın.](../media/ClickOnceimage4.png)

   eBulma Dışarı Aktarma Aracı yüklü değilse bir Güvenlik Uyarısı girmeniz istenir. 

   ![eBulma Dışarı Aktarma Aracı'nı yüklemek için Yükle'ye tıklayın.](../media/ClickOnceimage5.png)

3. **Yükle**’yi seçin. Yüklendikten sonra dışarı aktarma aracı otomatik olarak başlatılır.

Daha fazla bilgi için aşağıdaki makalelere bakın:

- [İçerik Arama sonuçlarını dışarı aktarma](export-search-results.md)

- [Microsoft Edge'de deneme bayraklarını etkinleştirme](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
