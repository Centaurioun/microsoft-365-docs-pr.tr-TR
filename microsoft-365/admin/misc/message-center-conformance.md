---
title: İleti Merkezi gönderileri için uyumluluk meta verileri
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: İleti merkezi gönderileri için uyumluluk meta verilerine genel bakış alma
ms.openlocfilehash: 93259a813990bf106dc91729f042f5a10b727599
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68566456"
---
# <a name="conformance-metadata-for-message-center-posts"></a>İleti Merkezi gönderileri için uyumluluk meta verileri

Yeni özellikleri veya hizmet dağıtımlarını planlarken, sektörünüzün, bölgenizin ve ülkenizin uyumluluğu için değişiklikleri anlamanız ve değerlendirmeniz gerekir. Yeni veya değişen bir özellik hakkında yeterli uyumluluk bilgisi yoksa, özellik hakkında kendi araştırmanızı yürütmeniz veya sorularla Uyumluluk Programı'na ulaşmanız gerekmesi hakkında geri bildiriminizi aldık.  

Bu pilot programda, yeni ve güncelleştirilmiş Microsoft 365 özellikleri ve hizmetleri için proaktif olarak meta veriler sağlamak istiyoruz. Hedefimiz, uyumluluk gereksinimlerinizi verimli bir şekilde değerlendirmenize yardımcı olmak ve benimseme ve değişiklik yönetimi kararları konusunda size yardımcı olmaktır.  

Örneğin, bir özellik için meta veriler aşağıdaki değerlere sahipse, özellik benimseme kararı hızlı olmalıdır.  

- Müşteri verileri depolanıyor mu? **No**

- Müşteri veri depolama alanı değiştirlsin mi? **No**

- Mevcut veri akışında değişiklikler mi var? **No**

- Özellik üçüncü taraf hizmetlerle tümleştirilir mi? **No**

> [!NOTE]
> Yukarıdaki liste, pilot uyumluluk gönderilerinde daha önce gördüklerinizden biraz farklıdır. Listeyi pilot müşterilerden aldığımız geri bildirimlere göre güncelleştirdik.

Meta verilerin yukarıdaki listeden farklı olduğu özellikler için İleti merkezi gönderisi size belgeler sağlayabilir.

## <a name="understanding-conformance-metadata"></a>Uyumluluk meta verilerini anlama

|**Meta veri adı**|**Değerler**|**Tanım ve sorulan sorular**|**Örnek: Evet**|**Örnek: Hayır**|
|---|---|---|---|
|**Müşteri verileri depolanır**|Evet/Hayır|Bu değişiklik, daha önce bu özelliğin hizmet/önceki sürümü tarafından depolanmayan veya işlenmemiş net yeni verileri (müşteri veya kişisel veriler olarak sınıflandırılmış) depolar veya işler mi?|Teams Toplantıları, müşteri verilerini yakalayan ve toplayan kayıtların depolandığı yerdir.|İleti Merkezi Hizmeti aylık etkin kullanıcılar (MAU) özelliği, müşteri veya kişisel veri olarak sınıflandırılmamış bir kiracı kimliği için aylık toplu hizmet etkin kullanıcılarını gösterir.|
|**Müşteri veri depolama alanına geçiş**|Evet/Hayır|Bu değişiklik verileri depolamak için yeni veya farklı bir hizmet mi kullanıyor?|Teams Toplantıları Müşteri verilerini/içeriğini yakalayan/toplayan kayıtlar artık içinde depolanıyor.|Teams'de genişletilmiş tepkiler. Teams'deki ileti tepkilerini daha büyük bir kümeye genişletme. Depolanan yeni tepkiler müşteri verileridir ancak verilerin depolanması veya işlenmesinde bir değişiklik yoktur.|
|**Mevcut veri akışındaki değişiklikler**|Evet/Hayır|Bu özellik verileri yeni veya farklı bir işlem hattı üzerinden işliyor mu? <br> Veya <br> Bu özellik yalnızca mevcut işleme işlem hattını daha yeni verilere mi genişletiyor yoksa zaten bir yüzeyde kullanıma sunulan verileri başka bir yüzeye mi kullanıma siliyor? (**Yanıt = Hayır**).|İş için Bing, Bing'e göndermek için Word'den metin kullanmaya başladığında ve ardından verileri Word'e geri getirdiğinde, veri akışı değişti.|Yönetim merkezindeki Deneyim İçgörüleri sayfasında kullanılan üretkenlik puanı, veriler yeni bir yüzeyde gösterilir, ancak depolama ve işleme aynıdır. <br> Teams Masaüstünde Grup Sohbetlerinde Önerilen Yanıt (1:1 sohbet uzantısı) herhangi bir net yeni veriye sahip değildir. Bu, 1:1 sohbetlerinde Önerilen Yanıt için ayarlanmış olan işlem hattının bir uzantısıdır.|
|**Özellik, üçüncü taraf hizmetlerle tümleştirilir**|Evet/Hayır|Bu özellik, müşteri verilerinin Microsoft 365 dışında depolanabileceği veya işlenebileceği net yeni bir hizmet veya uygulama (birinci taraf veya üçüncü taraf) kullanıyor mu?|Bing İş, bir kullanıcıya ilgili olabilecek bilgileri/içeriği sunmak için "arama" verileri biçiminde müşteri içeriği alabilir.|İleti Merkezi Hizmeti aylık etkin kullanıcılar (MAU) özelliği, Microsoft 365 sınırındaki Kullanım Raporu Graph API kullanan hizmet aylık etkin kullanıcılarını gösterir.|
|

## <a name="join-the-pilot-program"></a>Pilot programa katılın

Bu [anketi](https://go.microsoft.com/fwlink/p/?linkid=2211581) tamamlayarak katılabilirsiniz.

İleti merkezi gönderisi teslim edildiğinde, şu ek bir İleti Merkezi gönderisi alırsınız: **MC### için Ek Uyumluluk Bilgileri**. Bu gönderi daha fazla uyumluluk meta verileri içerir. Doğrudan ek gönderiyle ilgili geri bildirim sağlayabilir veya e-posta gönderebilirsiniz: MCSHDPMS@Microsoft.com. [Teams kanalında](https://go.microsoft.com/fwlink/p/?linkid=2211676) da geri bildirim gönderebilirsiniz.

> [!NOTE]
> Microsoft Teams, OneDrive İş ve SharePoint Online özellikleriyle başlayacağız.
