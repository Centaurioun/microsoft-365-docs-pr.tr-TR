---
title: Bilgi yönetimi ilkelerine giriş
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: İçeriğin ne kadar süreyle tutulduğunu veya kullanıcıların bu içerikle gerçekleştirebileceği eylemleri denetlemek ve izlemek için bilgi yönetimi ilkelerini kullanmayı öğrenin.
ms.openlocfilehash: 98eae2a08aa246a1f0ebe7d037103a82c132d060
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67680493"
---
# <a name="introduction-to-information-management-policies"></a>Bilgi yönetimi ilkelerine giriş

Bilgi yönetimi ilkesi, bir içerik türü için kurallar kümesidir. Bilgi yönetimi ilkeleri, kuruluşların içeriğin ne kadar süreyle tutulduğunu veya kullanıcıların bu içerikle gerçekleştirebileceği eylemleri denetlemesine ve izlemesine olanak tanır. Bilgi yönetimi ilkeleri kuruluşların yasal veya resmi düzenlemelere uymasına yardımcı olabilir veya yalnızca iç iş süreçlerini zorunlu kılabilir. 
  
Örneğin, mali tabloların "yeterli denetimlerini" göstermesini gerektiren kamu düzenlemelerine uyması gereken bir kuruluş, finansal dosyalamalarla ilgili tüm belgeler için yazma ve onay sürecindeki belirli eylemleri denetleyan bir veya daha fazla bilgi yönetimi ilkesi oluşturabilir.
  
Nasıl yapılır bilgileri için bkz. [Bilgi yönetimi ilkeleri oluşturma ve uygulama](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Bilgi yönetimi ilkelerinin özellikleri
<a name="__top"> </a>

Kuruluşların içeriği ve işlemleri yönetmek için ayrı ayrı veya birlikte kullanabileceği önceden tanımlanmış ilke özelliklerinin dört temel kategorisi vardır. 
  
![İçerik ilkesi türleri.](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
Denetim ilkesi özelliği, kuruluşların belgelerde ve liste öğelerinde gerçekleştirilen olayları ve işlemleri günlüğe kaydederek içerik yönetim sistemlerinin nasıl kullanıldığını analiz etmelerine yardımcı olur. Bir belge veya öğenin düzenlenmesi, görüntülenmesi, iade edilmesi, kullanıma alınmış olması, silinmesi veya izinlerinin değiştirilmesi gibi olayları günlüğe kaydetmek için Denetim ilkesi özelliğini yapılandırabilirsiniz. Tüm denetim bilgileri sunucudaki tek bir denetim günlüğünde depolanır ve site yöneticileri bunun üzerinde raporlar çalıştırabilir. 
  
Süre sonu ilkesi özelliği, kuruluşların sitelerindeki güncel olmayan içeriği tutarlı ve izlenebilir bir şekilde silmelerine veya kaldırmalarına yardımcı olur. Bu, güncel olmayan içeriği saklamayla ilişkili hem maliyeti hem de riski yönetmenize yardımcı olur. Belirli içerik türlerinin belirli bir tarihte veya belge oluşturulduktan veya son değiştirildikten sonraki bir süre içinde sona ereceğini belirtmek için Bir Süre Sonu ilkesi yapılandırabilirsiniz.
  
Kuruluşlar ayrıca belirli gereksinimleri karşılamak için özel ilke özellikleri oluşturabilir ve dağıtabilir. Örneğin, üretim kuruluşu kullanıcıların bu belgelerin kopyalarını güvenli olmayan yazıcılarda yazdırmasını engelleyen tüm taslak ürün tasarımı belirtimi belgeleri için bir bilgi yönetimi ilkesi tanımlamak isteyebilir. Bu tür bir bilgi yönetimi ilkesi tanımlamak için, ürün tasarımı belirtimi içerik türü için ilgili bilgi yönetimi ilkesine eklenebilecek bir Yazdırma Kısıtlama ilkesi özelliği oluşturabilir ve dağıtabilirsiniz.
  
## <a name="locations-to-use-an-information-management-policy"></a>Bilgi yönetimi ilkesinin kullanılacağı konumlar
<a name="__toc340213528"> </a>

Bilgi yönetimi ilkesi uygulamak için, bunu sitedeki bir listeye, kitaplığa veya içerik türüne eklemeniz gerekir. Bilgi yönetimi ilkesi oluşturduğunuz veya eklediğiniz konum, ilkenin ne kadar geniş kapsamlı uygulanacağını veya ne kadar geniş bir şekilde kullanılabileceğini etkiler. Şunları yapabilirsiniz:
  
 **Site koleksiyonu ilkesi oluşturun ve ardından bu ilkeyi bir içerik türüne, listeye veya kitaplığa ekleyin** Site koleksiyonunun en üst düzey sitesindeki İlkeler listesinde bir site koleksiyonu ilkesi oluşturabilirsiniz. Bir site koleksiyonu ilkesi oluşturduktan sonra, diğer site koleksiyonlarının yöneticilerinin bunu İlkeler listesine içeri aktarabilmesi için dışarı aktarabilirsiniz. Dışarı aktarılabilir bir site koleksiyonu ilkesi oluşturmak, kuruluşunuzdaki siteler arasında bilgi yönetimi ilkelerini standartlaştırmanıza olanak tanır. 
  
Site içerik türüne site koleksiyonu ilkesi eklediğinizde ve bu site içerik türünün bir örneği bir liste veya kitaplığa eklendiğinde, söz konusu liste veya kitaplığın sahibi liste veya kitaplık için site koleksiyonu ilkesini değiştiremez. Site içerik türüne site koleksiyonu ilkesi eklemek, site koleksiyonu ilkelerinin site hiyerarşinizin her düzeyinde uygulanmasını sağlamanın iyi bir yoludur.
  
![Site Ayarları sayfasında İçerik Türü İlkesi Şablonu bağlantısı.](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Üst düzey sitenin Site İçerik Türü Galerisi'nde bir site içerik türü için bilgi yönetimi ilkesi oluşturun ve ardından bu içerik türünü bir veya daha fazla liste veya kitaplıka ekleyin** Ayrıca, doğrudan bir site içerik türü için bilgi yönetimi ilkesi oluşturabilir ve ardından bu site içerik türünün bir örneğini birden çok liste veya kitaplıkla ilişkilendirebilirsiniz. Bu şekilde bir bilgi yönetimi ilkesi oluşturursanız, site koleksiyonunda söz konusu içerik türündeki veya bu içerik türünden devralan içerik türündeki her öğe ilkeye sahiptir. Ancak, bir site içerik türü için doğrudan bir bilgi yönetimi ilkesi oluşturursanız, bu şekilde oluşturulan ilkeler dışarı aktarılamadığından, bu bilgi yönetimi ilkesini diğer site koleksiyonlarında yeniden kullanmak daha zordur. 
  
![Site Ayarları sayfasında site içerik türleri bağlantısı.](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Site içerik türünün ayarlar sayfasındaki bilgi yönetimi ilkesi bağlantısı.](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Not Site koleksiyonunda hangi ilkelerin kullanıldığını denetlemek için, site koleksiyonu yöneticileri ilke özelliklerini doğrudan bir içerik türünde ayarlama özelliğini devre dışı bırakabilir. Bu kısıtlama geçerli olduğunda, içerik türleri oluşturan kullanıcılar site koleksiyonu İlkeler listesinden ilke seçmeyle sınırlıdır.
  
 **Liste veya kitaplık için bilgi yönetimi ilkesi oluşturma** Kuruluşunuzun çok sınırlı bir içerik kümesine belirli bir bilgi yönetimi ilkesi uygulaması gerekiyorsa, yalnızca tek bir liste veya kitaplık için geçerli olan bir bilgi yönetimi ilkesi oluşturabilirsiniz. Bu bilgi yönetimi ilkesi oluşturma yöntemi en az esnektir çünkü ilke yalnızca bir konuma uygulanır ve diğer konumlar için dışarı aktarılamaz veya yeniden kullanılamaz. Ancak, bazen belirli durumları ele almak için sınırlı uygulanabilirliğe sahip benzersiz bilgi yönetimi ilkeleri oluşturmanız gerekebilir. 
  
![Belge kitaplığının ayarlar sayfasında bilgi yönetimi ilkeleri bağlantısı.](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Notlar 
  
Yalnızca liste veya kitaplık birden çok içerik türünü desteklemiyorsa, liste veya kitaplık için bilgi yönetimi ilkesi oluşturabilirsiniz. Bir liste veya kitaplık birden çok içerik türünü destekliyorsa, bu liste veya kitaplıkla ilişkilendirilmiş her bir liste içerik türü için bir bilgi yönetimi ilkesi tanımlamanız gerekir. (Belirli bir liste veya kitaplıkla ilişkilendirilmiş site içerik türünün örnekleri liste içerik türleri olarak bilinir.)
  
Site koleksiyonunda hangi ilkelerin kullanıldığını denetlemek için, site koleksiyonu yöneticileri ilke özelliklerini doğrudan liste veya kitaplıkta ayarlama özelliğini devre dışı bırakabilir. Bu kısıtlama geçerli olduğunda, listeleri veya kitaplıkları yöneten kullanıcılar site koleksiyonu İlkeler listesinden ilke seçmeyle sınırlıdır.
  
[Bilgi yönetimi ilkesi, bir içerik türü için kurallar kümesidir. Bilgi yönetimi ilkeleri, kuruluşların içeriğin ne kadar süreyle tutulduğunu veya kullanıcıların bu içerikle gerçekleştirebileceği eylemleri denetlemesine ve izlemesine olanak tanır. Bilgi yönetimi ilkeleri kuruluşların yasal veya resmi düzenlemelere uymasına yardımcı olabilir veya yalnızca iç iş süreçlerini zorunlu kılabilir. Örneğin, mali tabloların "yeterli denetimlerini" göstermesini gerektiren kamu düzenlemelerine uyması gereken bir kuruluş, finansal dosyalamalarla ilgili tüm belgeler için yazma ve onay sürecindeki belirli eylemleri denetleyan bir veya daha fazla bilgi yönetimi ilkesi oluşturabilir. Nasıl yapılır bilgileri için bkz. Bilgi yönetimi ilkeleri oluşturma ve uygulama.](intro-to-info-mgmt-policies.md#__top)
  

