---
title: eBulma arama sonuçlarını dışarı aktarırken PST dosyalarının boyutunu değiştirme
description: eBulma arama sonuçlarını dışarı aktarırken bilgisayarınıza indirilen PST dosyalarının varsayılan boyutunu değiştirebilirsiniz.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.collection:
- tier1
- purview-compliance
- ediscovery
ms.openlocfilehash: 7b8ed400283b303339e5cc3bbd7c31d41433f4b6
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687850"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>eBulma arama sonuçlarını dışarı aktarırken PST dosyalarının boyutunu değiştirme

Farklı Microsoft eBulma araçlarından eBulma aramasının e-posta sonuçlarını dışarı aktarmak için eBulma Dışarı Aktarma aracını kullandığınızda, dışarı aktarılabilir pst dosyasının varsayılan boyutu 10 GB'tır. Bu varsayılan boyutu değiştirmek istiyorsanız, arama sonuçlarını dışarı aktarmak için kullandığınız bilgisayarda Windows Kayıt Defteri'ni düzenleyebilirsiniz. Bunun bir nedeni PST dosyalarının DVD, cd veya USB sürücüsü gibi çıkarılabilir medyaya sığabilmesidir.
  
> [!NOTE]
> eBulma Dışarı Aktarma aracı, Microsoft Purview uyumluluk portalı İçerik arama aracı kullanılırken arama sonuçlarını dışarı aktarmak için kullanılır.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>eBulma arama sonuçlarını dışarı aktarırken PST dosyalarının boyutunu değiştirmek için bir kayıt defteri ayarı oluşturma

eBulma aramasının sonuçlarını dışarı aktarmak için kullanacağınız bilgisayarda aşağıdaki yordamı uygulayın.
  
1. Açıksa eBulma Dışarı Aktarma aracını kapatın.

2. .reg dosyasının dosya adı sonekini kullanarak aşağıdaki metni bir Window kayıt defteri dosyasına kaydedin; örneğin, PstExportSize.reg.

    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Yukarıdaki  `PstSizeLimitInBytes` örnekte değer 1.073.741.824 bayt veya yaklaşık 1 GB olarak ayarlanmıştır. Ayarın diğer bazı örnek değerleri aşağıda verilmiştir  `PstSizeLimitInBytes` . 

    |**GB cinsinden boyut (yaklaşık)**|**Bayt cinsinden boyut**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2GB  <br/> |2147483648  <br/> |
    |4GB  <br/> |4294967296  <br/> |
    |8GB  <br/> |8589934592  <br/> |

3. `PstSizeLimitInBytes` Arama sonuçlarını dışarı aktardığınızda, değeri BIR PST dosyasının istenen en büyük boyutuna değiştirin ve dosyayı kaydedin.

4. Windows Gezgini'nde, önceki adımlarda oluşturduğunuz .reg dosyasını seçin veya çift tıklayın.

5. Kullanıcı Access Control penceresinde, Kayıt Defteri Düzenleyicisi'nin değişikliği yapmasına izin vermek için **Evet'i** seçin.

6. Devam etmek isteyip istemediğiniz sorulduğunda **Evet'i** seçin.

    Kayıt Defteri Düzenleyicisi, ayarın kayıt defterine başarıyla eklendiğini belirten bir ileti görüntüler.

7. Kayıt defteri ayarının değerini değiştirmek için  `PstSizeLimitInBytes` 3 - 6 arası adımları yineleyebilirsiniz.
  
## <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Varsayılan boyut neden 10 GB?**
  
Varsayılan 10 GB boyutu müşteri geri bildirimlerine dayanıyordu; 10 GB, tek bir PST'deki en uygun içerik miktarı ile dosya bozulması olasılığı en düşük olan arasında iyi bir dengedir.
  
**PST dosyalarının varsayılan boyutunu artırmalı veya küçültmeli miyim?**
  
Müşteriler, arama sonuçlarının kuruluşlarındaki diğer konumlara fiziksel olarak gönderebilecekleri çıkarılabilir medyaya sığması için boyut sınırını azaltma eğilimindedir. 10 GB'tan büyük PST dosyalarında bozulma sorunları olabileceğinden varsayılan boyutu artırmanızı önermeyiz.
  
**Bunu hangi bilgisayarda yapmam gerekiyor?**
  
eKeşif Dışarı Aktarma aracını çalıştırdığınız herhangi bir yerel bilgisayarda kayıt defteri ayarını değiştirmeniz gerekir.
  
**Bu ayarı değiştirdikten sonra bilgisayarı yeniden başlatmam gerekiyor mu?**
  
Hayır, bilgisayarı yeniden başlatmanız gerekmez. Ancak, eBulma Dışarı Aktarma aracı çalışıyorsa, bu ayarı değiştirdikten sonra aracı kapatmanız ve yeniden başlatmanız gerekir.
  
**Var olan bir kayıt defteri anahtarı düzenlenip düzenlenmiyor mu yoksa yeni bir anahtar mı oluşturuluyor?**
  
Bu yordamda oluşturduğunuz .reg dosyasını ilk kez çalıştırdığınızda yeni bir kayıt defteri anahtarı oluşturulur. Ardından ,reg düzenleme dosyasını her değiştirdiğinizde ve yeniden çalıştırdığınızda ayar düzenlenir.
