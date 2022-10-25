---
title: İçerik konumu hatasını çözmek için İçerik Arama'yı yeniden deneyin
description: Araştırma sırasında, içerik konumu hataları olan İçerik Aramalarını çözmek için Yeniden Dene düğmesini kullanabilirsiniz.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- content-search
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 213340f424ef708de352b7b2d8c50648fefc6087
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688275"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>İçerik konumu hatasını çözmek için İçerik Arama'yı yeniden deneyin

Uyumluluk portalında çok sayıda posta kutusunda arama yapmak için İçerik Arama'yı kullandığınızda, hataya benzer arama hataları alabilirsiniz:

```text
Error

The search on the following locations failed:
User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)
User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

Bu hatalar (CS001-002, CS003-002, CS008-009, CS012-002 ve CS0XX-0XX biçimindeki diğer hatalarla) İçerik Arama'nın belirli içerik konumlarını aramada başarısız olduğunu gösterir. Bu örnekte iki posta kutusu aranmadı. Bu hatalar, İçerik Arama'nın durum ayrıntıları açılır sayfasında görüntülenir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="cause-of-content-location-errors"></a>İçerik konumu hatalarının nedeni

Çok sayıda posta kutusu aranırken, arama bir Microsoft veri merkezinde binlerce sunucuya dağıtılır. Belirli sunucular herhangi bir zamanda yeniden başlatma durumunda veya yedekli kopyalara yük devretme sürecinde olabilir. Bu iki durumda da İçerik Arama'nın veri alma isteği zaman aşımına uğradı. Önceki örnekte, başarısız olan posta kutularının hataları arama zaman aşımına uğradı.

## <a name="resolving-content-location-errors"></a>İçerik konumu hatalarını çözme

Aramanın yeniden başlatılması genellikle farklı sunucularda benzer hatalara neden olur. Aramayı yeniden başlatmak yerine, arama sonuçları sayfasının üst kısmında görüntülenen **Yeniden Dene** düğmesini seçin.

![İçerik konumu hatalarını çözmek için Yeniden Dene düğmesini seçin.](../media/retrycontentsearch3.png)

Bu, aramanın yalnızca başarısız olan posta kutuları için yeniden denenerek sonuçlanır. Aramayı yeniden denediğinizde, başarıyla döndürülen diğer sonuçlar korunur.

## <a name="tips-to-avoid-content-location-errors"></a>İçerik konumu hatalarını önleme ipuçları

burada, içerik konumu hatalarının bazı ek nedenleri ve çok sayıda posta kutusu ararken bunlardan kaçınmanıza yardımcı olacak bazı ipuçları yer alır.

- Aranan posta kutusu kullanıcı etkinliği nedeniyle meşgul olabilir. Bu durumda, arama hizmeti posta kutusunun kullanılamaz duruma gelmesini önlemek için kendini kısıtlayabilir. Bunu önlemek için, iş dışı saatlerde arama çalıştırmayı deneyin.
- Arama sorgusu posta kutusundan çok fazla içerik almakta olabilir. Mümkünse anahtar sözcükleri, tarih aralıklarını ve arama koşullarını kullanarak arama kapsamını daraltmayı deneyin.
- Anahtar sözcükler listesini kullanarak bir arama sorgusu oluşturduğunuzda çok fazla [anahtar sözcük veya anahtar sözcük](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches) tümceciği. Anahtar sözcükler listesini kullanan bir arama sorgusu çalıştırdığınızda, hizmet temelde anahtar sözcük listesindeki her satır için ayrı bir arama çalıştırarak istatistiklerin oluşturulabilmesini sağlar. Arama sorgularında anahtar sözcükler listesini kullanıyorsanız, anahtar sözcük listesindeki satır sayısını en aza indirin veya sayı anahtar sözcüklerini daha küçük listelere bölün ve her anahtar sözcük listesi için farklı bir arama oluşturun.

  > [!NOTE]
  > Büyük anahtar sözcük listelerinin neden olduğu sorunları azaltmaya yardımcı olmak için artık arama sorgusunun anahtar sözcük listesinde en fazla 20 satırla sınırlısınız.

- Aynı posta kutusunda aynı anda çok fazla arama yapılıyor. Mümkünse, herhangi bir posta kutusunda bir kerede bir arama çalıştırmayı deneyin.
- Tek bir aramada çok fazla posta kutusu aranıyor. Çok sayıda posta kutusu aranırken içerik konumu hatalarının olasılığı artar. Mümkünse, her aramanın kuruluşunuzdaki posta kutularının bir alt kümesini içermesi için birden çok arama çalıştırmayı deneyin.
- Posta kutusunda gerekli bakım gerçekleştiriliyor. Bu neden büyük olasılıkla seyrek gerçekleşse de, içerik konumu hatasını aldıktan sonra biraz bekleyin ve aramayı yeniden deneyin.
