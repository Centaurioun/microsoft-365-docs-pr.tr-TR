---
title: Project Server 2013 destek sonu yol haritası
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: Project Server 2013 desteği 11 Nisan 2023'te sona erer. Şirket içi Project Server'ın Project Online veya daha yeni bir sürümüne yükseltmek için bu makaleyi kılavuz olarak kullanın.
ms.openlocfilehash: 5d7a31ebcb43cb157383ab0faf5ecfe5dd7c5940
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67736376"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>Project Server 2013 destek sonu yol haritası

Project Server 2013 **, 11 Nisan 2023'te** destek sonuna ulaşacaktır. Şu anda Project Server 2013 kullanıyorsanız, Project 2013 masaüstü uygulamasının da aynı destek sonu tarihlerine sahip olduğunu unutmayın.

## <a name="what-does-end-of-support-mean"></a>*Destek sonu* ne anlama gelir?

Neredeyse tüm Microsoft ürünlerinin yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri aldığı bir destek yaşam döngüsü vardır. Bu yaşam döngüsü genellikle ürünün ilk sürümünden itibaren 10 yıl sürer. Bu yaşam döngüsünün sonu, ürünün destek sonu olarak bilinir. Project Server 2013 11 Nisan 2023'te destek sonuna ulaştıktan sonra Microsoft artık şunları sağlamayacaktır:

- Oluşabilecek sorunlar için teknik destek.

- Bulunan ve sunucunun kararlılığını ve kullanılabilirliğini etkileyebilecek sorunlar için hata düzeltmeleri.

- Bulunan ve sunucuyu güvenlik ihlallerine karşı savunmasız hale getirebilecek güvenlik açıkları için güvenlik düzeltmeleri.

- Saat dilimi güncelleştirmeleri.

Project Server 2013 yüklemeniz bu tarihten sonra çalışmaya devam edecektir. Ancak, daha önce listelenen değişiklikler nedeniyle, Project Server 2013'ten en kısa sürede geçmenizi kesinlikle öneririz.

## <a name="what-are-my-options"></a>Seçeneklerim nelerdir?

Geçiş seçenekleriniz şunlardır:

- Project Online geçiş

- Project Server'ın daha yeni bir şirket içi sürümüne geçiş (tercihen Project Server Abonelik Sürümü)

|Neden Project Server 2019'a geçmeyi tercih ederim?|Neden Project Online geçişini tercih ederim?|
|---|---|
|İş kuralları, işletmemi bulutta çalıştırmamı kısıtlar.  <br/><br/>  Ortamımdaki güncelleştirmeleri denetlemem gerekiyor.|Mobil veya uzak kullanıcılarım var.<br/><br/>  Şirket içi sunucuları geçirme maliyetleri önemli bir sorundur (donanım, yazılım, uygulama zamanı ve çaba vb.). <br/><br/>  Geçiş sonrasında ortamımın bakımını yapmak için gereken maliyetler önemli bir konudur (örneğin, otomatik güncelleştirmeler, garantili çalışma süresi vb.).|

> [!NOTE]
> Project Server ve Project Online aynı kaynak havuzunu paylaşamadığından Project Server karma yapılandırmayı desteklemez.

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>Project Server 2013'ten geçiş için önemli noktalar

Project Server 2013'ten geçiş yapmayı planlarken aşağıdakileri göz önünde bulundurun:

- **Microsoft çözüm sağlayıcısından yardım alma** - Project Server 2013'ten yükseltme zor olabilir. Çok fazla hazırlık ve planlama gerektirir. Project Server 2013'i ilk olarak ayarlayan kişi siz değilseniz, bu özellikle zor olabilir. microsoft çözüm sağlayıcıları, ister Project Server Abonelik Sürümü ister Project Online geçirmeyi planlayın, size yardımcı olabilir. Microsoft çözüm sağlayıcısı [merkezinde bir çözüm sağlayıcısı](https://go.microsoft.com/fwlink/p/?linkid=841249) arayın.

- **Zaman ve sabır** - Yükseltme planlaması, yürütmesi ve testi, özellikle de Project Server Abonelik Sürümü yükseltmesi için önemli ölçüde zaman ve çaba gerektirir. Project Server 2013'ten Project Server Abonelik Sürümü geçiriyorsanız, önce Project Server 2016'a geçmeniz, verilerinizi denetlemeniz ve ardından Project Server Abonelik Sürümü. Bir Microsoft çözüm sağlayıcısına yardımcı olması için bir zaman çerçevesi ve tahmini maliyet olup olmadığını kontrol etmek isteyebilirsiniz.

## <a name="migrate-to-project-online"></a>Project Online geçiş

Project Server 2013'ten Project Online'a geçiş yapmayı seçerseniz, proje planı verilerinizi el ile geçirmek için şu adımları izleyebilirsiniz:

1. Project Server 2013'ten .mpp biçimine proje planlarınızı kaydedin.

2. Project Professional 2016, Project Professional 2019 veya Project Online Masaüstü İstemcisi'ni kullanarak her bir .mpp dosyasını açın ve kaydedin ve Project Online'de yayımlayın.

PWA yapılandırmanızı Project Online'da el ile oluşturabilirsiniz (örneğin, gerekli özel alanları veya kurumsal takvimleri yeniden oluşturun). Microsoft çözüm sağlayıcıları da bu işlemde yardımcı olabilir.

Önemli kaynaklar:

|Kaynak|Açıklama|
|---|---|
|[Project Online ile çalışmaya başlama](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online ayarlama ve kullanma|
|[Project Online Hizmet Açıklaması](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Kullanılabilir farklı Project Online planları hakkında bilgi|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Project Server'ın daha yeni bir şirket içi sürümüne geçiş

Project Online geçiş yaparak en iyi değeri ve kullanıcı deneyimini elde ettiğinize kesinlikle inanıyoruz. Ancak bazı kuruluşların proje verilerini şirket içinde tutması gerektiğini de anlıyoruz. Proje verilerinizi şirket içinde tutmayı seçerseniz, Project Server 2013 ortamınızı Project Server 2016, Project Server 2019 veya Project Server Abonelik Sürümü geçirebilirsiniz.

Project Online geçiremiyorsanız, Project Server'ın önceki sürümlerindeki önemli özelliklerin çoğunu içeren Project Server Abonelik Sürümü geçişini öneririz. Bazı özellikler yalnızca Project Online'da kullanılabilse de, Project Online ile sunulan deneyimle en yakın şekilde eşleşir. Dikkate alınması gereken ek faktörler şunlardır:

- Project Server Abonelik Sürümü, ileride Project Server'ın yeni ana sürümlerini yayınlama gereksinimini ortadan kaldıran sürekli bir güncelleştirme modeli getirir.
- Hem Project Server 2016 hem de 2019, 14 Temmuz 2026'da destek sonuna ulaşacaktır. Her iki sürüme de geçiş yaparsanız, üç yıl içinde başka bir yükseltme planlamanız gerekir. Daha fazla bilgi için hem [2016 hem de 2019](/lifecycle/products/project-server-2016) için destek [](/lifecycle/products/project-server-2019)yaşam döngüsü sayfalarına bakın.

Her geçişi tamamladıktan sonra verilerinizin başarıyla geçirildiğini doğrulayın.

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>Project Server Abonelik Sürümü geçiş Nasıl yaparım??

Project Server 2013 ile Project Server Abonelik Sürümü arasındaki mimari farklar doğrudan geçiş yolunu engeller. Bu nedenle önce Project Server 2013 verilerinizi Project Server 2016 ve ardından Project Server Abonelik Sürümü geçirmeniz gerekir. 

1. Project Server 2016'a geçiş.

2. Project Server 2016'den Project Server Abonelik Sürümü geçiş.

Her geçişi tamamladıktan sonra verilerinizin başarıyla geçirildiğini doğrulayın.

### <a name="step-1-migrate-to-project-server-2016"></a>1. Adım: Project Server 2016 geçiş

Project Server 2013'ten Project Server 2016 yükseltme hakkında kapsamlı bilgi için bkz. [Project Server 2016 yükseltme](/project/upgrade-to-project-server-2016).

Önemli kaynaklar:

- [Project Server 2016 yükseltme işlemine genel bakış](/project/upgrade-to-project-server-2016): Project Server 2013'ten Project Server 2016 yükseltmeye ilişkin üst düzey bir genel bakış edinin.
- [Project Server 2016 yükseltmeyi planlama](/project/plan-for-upgrade-to-project-server-2016): Sistem gereksinimleri de dahil olmak üzere Project Server 2013'ten Project Server 2016 yükseltme sırasında dikkat edilmesi gereken planlama konularına bakın.
- [Project Server 2016 yükseltme](/project/upgrading-to-project-server-2016): Yükseltme işlemiyle ilgili ayrıntılı yönergelere bakın.

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>2. Adım: Project Server Abonelik Sürümü geçiş

Project Server 2016'a geçtikten ve verilerinizin başarıyla geçirildiğini doğruladıktan sonra, sonraki adım Project Server Abonelik Sürümü geçirmektir.

Daha fazla bilgi için bkz[. Project Server Abonelik Sürümü yükseltme](/project/upgrade-project-server-subscription-edition).

Önemli kaynaklar:

- [Project Server Abonelik Sürümü yükseltme işlemine genel bakış](/project/overview-project-server-subscription-edition-upgrade-process): Project Server 2013'ten Project Server 2016 yükseltmek için yapmanız gerekenleri anlayın.
- [Project Server Abonelik Sürümü yükseltmeyi planlama](/Project/plan-upgrade-project-server-subscription-edition): Project Server 2013'ten Project Server 2016'a yükseltme yaparken dikkat edilmesi gereken planlama noktalarına bakın.
- [Project Server Abonelik Sürümü yükseltme](/project/how-to-upgrade-project-server-subscription-edition): Yükseltme işlemiyle ilgili ayrıntılı yönergelere bakın.


