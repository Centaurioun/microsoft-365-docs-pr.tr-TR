---
title: Project Server 2010 destek sonu yol haritası
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Project Server 2010 desteği 13 Nisan 2021'de sona eriyor. Şirket içi Project Server'ın Project Online veya daha yeni bir sürümüne yükseltmek için bu makaleyi kılavuz olarak kullanın.
ms.openlocfilehash: ccf65987547304df5527cca862dbd0467d2f52a4
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670785"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 destek sonu yol haritası

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Project Server 2010 **, 13 Nisan 2021'de** destek sonuna ulaşacaktır. Bu tarih, 13 Ekim 2020'nin önceki destek sonu tarihinden itibaren uzatıldı. Şu anda Project Server 2010 kullanıyorsanız, bu ilgili ürünlerin aşağıdaki destek sonu tarihlerine sahip olduğunu unutmayın:

|Ürün |Destek sonu tarihi|
|---|---|
|Project 2010 Standard|13 Ekim 2020|
|Project 2010 Professional|13 Ekim 2020|

Destek sonuna ulaşma hakkında daha fazla bilgi için bkz. [Office 2010 sunucularından ve istemci ürünlerinden yükseltme](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>*Destek sonu* ne anlama gelir?

Neredeyse tüm Microsoft ürünlerinin yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri aldığı bir destek yaşam döngüsü vardır. Bu yaşam döngüsü genellikle ürünün ilk sürümünden itibaren 10 yıl sürer. Bu yaşam döngüsünün sonu, ürünün destek sonu olarak bilinir. Project Server 2010 13 Nisan 2021'de destek sonuna ulaştıktan sonra Microsoft artık şunları sağlamayacaktır:

- Oluşabilecek sorunlar için teknik destek.

- Bulunan ve sunucunun kararlılığını ve kullanılabilirliğini etkileyebilecek sorunlar için hata düzeltmeleri.

- Bulunan ve sunucuyu güvenlik ihlallerine karşı savunmasız hale getirebilecek güvenlik açıkları için güvenlik düzeltmeleri.

- Saat dilimi güncelleştirmeleri.

Project Server 2010 yüklemeniz bu tarihten sonra çalışmaya devam edecektir. Ancak, daha önce listelenen değişiklikler nedeniyle, project server 2010'dan mümkün olan en kısa sürede geçmenizi kesinlikle öneririz.

## <a name="what-are-my-options"></a>Seçeneklerim nelerdir?

Geçiş seçenekleriniz şunlardır:

- Project Online geçiş

- Project Server'ın daha yeni bir şirket içi sürümüne geçiş (tercihen Project Server 2019)

Project Server 2010 desteğinin sona ermesini önlemek için izleyebileceğiniz iki yol aşağıdadır.

![Project Server 2010 yükseltme yolları.](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Neden Project Server 2019'a geçmeyi tercih ederim?|Neden Project Online geçişini tercih ederim?|
|---|---|
|İş kuralları, işletmemi bulutta çalıştırmamı kısıtlar.  <br/><br/>  Ortamımdaki güncelleştirmeleri denetlemem gerekiyor.|Mobil veya uzak kullanıcılarım var.<br/><br/>  Şirket içi sunucuları geçirme maliyetleri önemli bir sorundur (donanım, yazılım, uygulama zamanı ve çaba vb.). <br/><br/>  Geçiş sonrasında ortamımın bakımını yapmak için gereken maliyetler önemli bir konudur (örneğin, otomatik güncelleştirmeler, garantili çalışma süresi vb.).|

> [!NOTE]
> Geçiş seçenekleriniz hakkında daha fazla bilgi için bkz. [Office 2010 sunucularından ve istemcilerinden yükseltmenize yardımcı olacak kaynaklar](upgrade-from-office-2010-servers-and-products.md). Project Server ve Project Online aynı kaynak havuzunu paylaşamadığından Project Server'ın karma yapılandırmayı desteklemediğini unutmayın.

### <a name="what-are-my-options-for-project-client"></a>Project istemcisi için seçeneklerim nelerdir?

Project Professional 2010 veya Project Standard 2010 kullanıyorsanız seçenekleriniz şunlardır:

- Project Professional veya Project Standard daha yeni bir sürümüne gitme
- Web için Project Online veya Project gibi çevrimiçi bir çözüme gitme

#### <a name="move-to-a-newer-version-of-project-client"></a>Project istemcisinin daha yeni bir sürümüne gitme

Project Standard 2010'dan geçiş gerçekleştiriyorsanız, Project Standard'ın daha yeni bir sürümüne geçebilirsiniz (Project Standard 2016 veya Project Standard 2019). En son özelliklerden yararlanmak için en yeni sürüme geçmenizi öneririz. Daha az güncel bir sürüme (Project Standard 2016) geçiş yapmak da daha erken geçiş yapmanız gerektiği anlamına gelir.

Benzer şekilde, Project Professional 2010'dan geçiş gerçekleştiriyorsanız daha yeni bir sürüme (Project Professional 2019 veya Project Professional 2016) geçebilirsiniz. Mümkünse en yeni sürüme geçin. Project Server'a bağlanmak için Project Professional kullanıyorsanız, kullandığınız Project Server sürümüne bağlanan bir Project Professional sürümüne geçiş yaptığınızdan emin olun.

Project Professional 2010 kullanıcıları, Project Professional 2019'un abonelik tabanlı bir sürümü olan Project Online Desktop istemcisine de geçiş yapabilir. Project Plan 3 ve Project Plan 5 aboneliklerine dahildir.

#### <a name="move-to-an-online-solution"></a>Çevrimiçi bir çözüme gitme

Ayrıca Project Professional 2010 veya Project Standard 2010'dan Project aboneliği tabanlı çevrimiçi çözüme de geçiş yapabilirsiniz. Hem Project Plan 3 hem de Plan 5, Project Online ve en son bulut teklifi [olan Web için Project'i](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) içerir. Her ikisi de keşfedilmesi gereken yeni özellikler ve avantajlar sunar.

Özellikler ve lisanslar hakkında daha fazla bilgi için bkz. [Microsoft Project hizmet açıklaması](/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010'dan geçiş için önemli noktalar

Project Server 2010'dan geçiş yapmayı planlarken aşağıdakileri göz önünde bulundurun:

- **Microsoft çözüm sağlayıcısından yardım alma** - Project Server 2010'dan yükseltme zor olabilir. Çok fazla hazırlık ve planlama gerektirir. Project Server 2010'un ilk kurulumunu yapan kişi siz değilseniz, bu özellikle zor olabilir. İster Project Server 2019'a ister Project Online geçirmeyi planlayın, Microsoft çözüm sağlayıcıları size yardımcı olabilir. Microsoft çözüm sağlayıcısı [merkezinde bir çözüm sağlayıcısı](https://go.microsoft.com/fwlink/p/?linkid=841249) arayın.

- **Özelleştirmelerinizi planlama** - Project Server 2010 ortamınızdaki özelleştirmeler, Project Server 2019'a veya Project Online geçiş yaptığınızda çalışmayabilir. Sürümler arasında Project Server mimarisinde önemli farklılıklar vardır. Ayrıca, sürümlerle çalışan gerekli işletim sistemleri, veritabanı sunucuları ve web tarayıcıları farklılık gösterir. Özelleştirmelerinizi yeni ortamda test etme veya yeniden derleme hakkında bir plan oluşturun. Belirli özelleştirmelerin hala gerekli olup olmadığını belirlemek için bu fırsatı değerlendirin. Daha fazla bilgi için bkz. [SharePoint 2013'e yükseltme sırasında geçerli özelleştirmeler için plan oluşturma](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Zaman ve sabır** - Yükseltme planlaması, yürütme ve test, özellikle Project Server 2019'a yükseltme için önemli ölçüde zaman ve çaba gerektirir. Project Server 2010'dan Project Server 2019'a geçiş gerçekleştiriyorsanız, önce Project Server 2013'e geçmeniz, verilerinizi denetlemeniz, sonra Project Server 2016 ve ardından Project Server 2019'a geçmeniz gerekir. Bir Microsoft çözüm sağlayıcısına yardımcı olması için bir zaman çerçevesi ve tahmini maliyet olup olmadığını kontrol etmek isteyebilirsiniz.

## <a name="migrate-to-project-online"></a>Project Online geçiş

Project Server 2010'dan Project Online geçiş yapmayı seçerseniz, proje planı verilerinizi el ile geçirmek için şu adımları izleyebilirsiniz:

1. Proje planlarınızı Project Server 2010'dan .mpp biçimine kaydedin.

2. Project Professional 2016, Project Professional 2019 veya Project Online Masaüstü İstemcisi'ni kullanarak her bir .mpp dosyasını açın ve kaydedin ve Project Online'de yayımlayın.

PWA yapılandırmanızı Project Online'da el ile oluşturabilirsiniz (örneğin, gerekli özel alanları veya kurumsal takvimleri yeniden oluşturun). Microsoft çözüm sağlayıcıları da bu işlemde yardımcı olabilir.

Önemli kaynaklar:

|Kaynak|Açıklama|
|---|---|
|[Project Online ile çalışmaya başlama](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online ayarlama ve kullanma|
|[Project Online Hizmet Açıklaması](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|Kullanılabilir farklı Project Online planları hakkında bilgi|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Project Server'ın daha yeni bir şirket içi sürümüne geçiş

Project Online geçiş yaparak en iyi değeri ve kullanıcı deneyimini elde ettiğinize kesinlikle inanıyoruz. Ancak bazı kuruluşların proje verilerini şirket içinde tutması gerektiğini de anlıyoruz. Proje verilerinizi şirket içinde tutmayı seçerseniz, Project Server 2010 ortamınızı Project Server 2013, Project Server 2016 veya Project Server 2019'a geçirebilirsiniz.

Project Online geçiremiyorsanız, Project Server 2019'a geçmenizi öneririz. Project Server 2019, Project Server'ın önceki sürümlerindeki temel özelliklerin çoğunu içerir. Bazı özellikler yalnızca Project Online'da kullanılabilse de, Project Online ile sunulan deneyimle en yakın şekilde eşleşir.

Her geçişi tamamladıktan sonra verilerinizin başarıyla geçirildiğini doğrulayın.

> [!NOTE]
> Şirket içi bir çözümle sınırlıysanız ve yalnızca Project Server 2013'e geçiş yapmayı düşünüyorsanız, bu sürümde yalnızca birkaç yıl daha destek kaldığına dikkat edin. Project Server 2013 Service Pack 2 13 Ekim 2023 için destek sonu tarihi. Destek sonu tarihleri hakkında daha fazla bilgi için bkz. [Microsoft Ürün Yaşam Döngüsü İlkesi](/lifecycle/).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Project Server 2019'a geçiş Nasıl yaparım??

Project Server 2010 ile Project Server 2019 arasındaki mimari farklılıklar doğrudan geçiş yolunu engeller. Bu nedenle, Project Server 2010 verilerinizi Project Server 2019'a ulaşana kadar Project Server'ın birbirini izleyen her sürümüne geçirmeniz gerekir. Project Server 2010'ı Project Server 2019'a yükseltme adımları:

1. Project Server 2013'e geçiş.

2. Project Serve 2013'ten Project Server 2016'a geçiş yapın.

3. Project Server 2016'den Project Server 2019'a geçiş.

Her geçişi tamamladıktan sonra verilerinizin başarıyla geçirildiğini doğrulayın.

### <a name="step-1-migrate-to-project-server-2013"></a>1. Adım: Project Server 2013'e geçiş

Project Server 2010'dan Project Server 2013'e yükseltme hakkında kapsamlı bilgi için bkz. [Project Server 2013'e yükseltme](/project/upgrade-to-project-server-2016).

Önemli kaynaklar:

- [Project Server 2013 yükseltme işlemine genel bakış](/project/upgrade-to-project-server-2016)

  Project Server 2010'dan Project Server 2013'e yükseltme hakkında üst düzey bir genel bakış edinin.
- [Project Server 2013'e yükseltmeyi planlama](/project/plan-for-upgrade-to-project-server-2016)

  Sistem gereksinimleri de dahil olmak üzere Project Server 2010'dan Project Server 2013'e yükseltme sırasında dikkat edilmesi gereken planlama noktalarına bakın.

- [Project Server 2013 yükseltmesindeki yenilikler](/project/what-s-new-in-project-server-2013-upgrade) , aşağıdakiler dahil olmak üzere bu sürüme yönelik önemli değişiklikleri kapsar:

  - Project Server 2013'e yerinde yükseltme yoktur. Veritabanı ekleme yöntemi, Project Server 2010'dan Project Server 2013'e yükseltmenin desteklenen tek yoludur.

  - Yükseltme işlemi Yalnızca Project Server 2010 verilerinizi Project Server 2013 biçimine dönüştürmekle kalmaz, aynı zamanda dört Project Server 2010 veritabanını tek bir Project Web App veritabanında birleştirir.

  - Hem SharePoint Server 2013 hem de Project Server 2013, önceki sürümden talep tabanlı kimlik doğrulaması olarak değiştirildi. Klasik kimlik doğrulaması kullanıyorsanız, yükseltme yaparken bunu göz önünde bulundurmanız gerekir. Daha fazla bilgi için bkz. [SharePoint 2013'te klasik moddan talep tabanlı kimlik doğrulamasına geçiş](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Önemli kaynaklar:

- [Project Server 2013'e yükseltme işlemine genel bakış](/project/overview-of-the-project-server-2016-upgrade-process)

- [Veritabanlarınızı ve Project Web App site koleksiyonlarınızı yükseltme (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Server yükseltme işlemi diyagramı](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [8 Kolay Adımda Harika Veritabanı Birleştirme, Project Server 2010-2013 Geçişi](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>2. Adım: Project Server 2016 geçiş

Project Server 2013'e geçtikten ve verilerinizin başarıyla geçirildiğini doğruladıktan sonra, sonraki adım Project Server 2016 geçirmektir.

Daha fazla bilgi için bkz[. Project Server 2016 yükseltme](/Project/upgrade-to-project-server-2016).

Önemli kaynaklar:

- [Project Server 2016 yükseltme işlemine genel bakış](/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2013'ten Project Server 2016'ye yükseltmek için yapmanız gerekenleri anlayın.

- [Project Server 2016 yükseltmeyi planlama](/Project/plan-for-upgrade-to-project-server-2016)

  Project Server 2013'ten Project Server 2016 yükseltirken dikkat edilmesi gereken planlama noktalarına bakın.

[Project Server 2016 yükseltmesi hakkında bilmeniz gerekenler](/project/plan-for-upgrade-to-project-server-2016#thingknow), bu sürüme yükseltme için aşağıdakiler gibi önemli değişiklikleri kapsar:

- Project Server 2016 ortamınızı oluştururken, Project Server 2016 yükleme dosyalarının SharePoint Server 2016'ya eklendiğini unutmayın. Daha fazla bilgi için bkz[. Project Server 2016 dağıtma](/project/deploy-project-server-2016).

- Kaynak planları Project Server 2016 kullanım dışıdır. Project Server 2013 kaynak planlarınız Project Server 2016 ve Project Online kaynak görevlendirmelerine geçirilecek. Daha fazla bilgi için bkz [. Genel Bakış: Kaynak görevlendirmeleri](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) .

### <a name="step-3-migrate-to-project-server-2019"></a>3. Adım: Project Server 2019'a geçiş

Project Server 2016 geçiş yaptıktan ve verilerinizin başarıyla geçirildiğini doğruladıktan sonra, sonraki adım verilerinizi Project Server 2019'a geçirmektir.

Project Server 2016'den Project Server 2019'a yükseltmek için yapmanız gerekenleri öğrenmek için bkz. [Project Server 2019'a yükseltme](/Project/upgrade-to-project-server-2016).

Önemli kaynaklar:

- [Project Server 2019 yükseltme işlemine genel bakış](/project/overview-of-the-project-server-2019-upgrade-process)

  Project Server 2013'ten Project Server 2016 yükseltmek için yapmanız gerekenler hakkında üst düzey bir anlayış elde edin.

- [Project Server 2019'a yükseltmeyi planlama](/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016'den Project Server 2019'a yükseltmeyle ilgili planlama konuları'na bakın.

- [Project Server 2019 yükseltmesi hakkında bilmeniz gerekenler](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>Bu sürüme yükseltmeye yönelik aşağıdaki önemli değişiklikler hakkında bilgi edinin:

  - Yükseltme işlemi verilerinizi Project Server 2016 veritabanınızdan SharePoint Server 2019 İçerik veritabanına geçirir.  Project Server 2019 artık SharePoint Server grubunda kendi Project Server veritabanını oluşturmayacaktır.

  - Yükseltmeden sonra Project Web App'teki çeşitli değişikliklere dikkat edin.  Ayrıntılar için bkz. [Project Server 2019'daki yenilikler](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Diğer kaynaklar**:

- [Project Online Hizmet Açıklamaları](/office365/servicedescriptions/project-online-service-description/project-online-service-description): Project Server 2016 ve Project Online Ekstra dahil edilen portföy yönetimi özelliklerine bakın.

- [Microsoft Office Project Portfolio Server 2010 geçiş kılavuzu](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 istemcisi ve sunucuları ile Windows 7 seçeneklerinin özeti

Office 2010 istemcileri ve sunucuları ile Windows 7 için yükseltme, geçiş ve buluta taşıma seçeneklerinin görsel bir özeti için [destek sonu posterine](../downloads/Office2010Windows7EndOfSupport.pdf) bakın.

[![Office 2010 istemcileri ve sunucuları ve Windows 7 posteri için destek sonu.](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Bu posterde, Office 2010 istemci ve sunucu ürünleri ile Windows 7 desteğinin sona ermesini önlemek için izleyebileceğiniz çeşitli yollar gösterilmektedir ve tercih edilen yollar ve Microsoft 365 Kurumsal seçeneği desteği vurgulanır.

Ayrıca bu posteri [indirebilir](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ve mektup, yasal veya tabloid (11 x 17) biçiminde yazdırabilirsiniz.

## <a name="related-topics"></a>İlgili konular

[SharePoint 2010'dan yükseltme](upgrade-from-sharepoint-2010.md)

[Office 2010 sunucuları ve istemcilerinden yükseltme](upgrade-from-office-2010-servers-and-products.md)
