---
title: Microsoft Syntex için senaryolar ve kullanım örnekleri
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris
ms.date: ''
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
ms.localizationpriority: medium
description: Kuruluşunuzda Microsoft Syntex'i kullanma hakkında iş senaryoları bulun.
ms.openlocfilehash: a43231e268e69a74cdc0bbc35df2cdd24d9e0d37
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660917"
---
# <a name="scenarios-and-use-cases-for-microsoft-syntex"></a>Microsoft Syntex için senaryolar ve kullanım örnekleri

Kuruluşunuzda Microsoft Syntex'i nasıl kullanabileceğiniz hakkında fikir istemi göndermek için aşağıdaki örnek senaryoları kullanın.

- [Senaryo: Yapılandırılmış belge işleme modelini kullanarak faturalardan bilgileri izleme](adoption-scenarios.md#scenario-track-information-from-invoices-by-using-the-structured-document-processing-model)
- [Senaryo: Yapılandırılmamış belge işleme modelini kullanarak sözleşmelerden bilgileri izleme](adoption-scenarios.md#scenario-track-information-from-contracts-by-using-the-unstructured-document-processing-model)
- [Senaryo: Syntex tabanlı kayıt yönetimi, belge idaresi ve uyumluluk süreçlerinde riskten kaçının](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-syntex)
- [Senaryo: Daha önce erişilemeyen belgelerden bilgi yakalama](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Senaryo: İçgörüler ve analizler sağlamak için veri işlemeyi geliştirme](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Senaryo: Sipariş işlemeyi otomatikleştirme](adoption-scenarios.md#scenario-automate-order-processing)
- [Senaryo: Vize yenileme sürecini basitleştirme](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-information-from-invoices-by-using-the-structured-document-processing-model"></a>Senaryo: Yapılandırılmış belge işleme modelini kullanarak faturalardan bilgileri izleme

Örneğin, faturaları izlemek ve izlemek için Syntex ve Power Automate özelliklerini kullanarak bir işlem ayarlayabilirsiniz.

1. Fatura belgelerini depolamak için bir kitaplık ayarlayın.
2. Belgelerdeki alanları tanımak için modeli eğitin.
3. İzlemek istediğiniz alanları bir listeye ayıklayın.
4. Aşağıdakiler gibi belirli olaylar için size bildirimde bulunacak bir akış ayarlayın:
    - Yeni bir fatura eklenir.
    - Faturanın son tarihi geçmiştir.
    - Fatura, otomatik onay tutarınızdan daha büyük bir tutara yöneliktir.

![Syntex ve Power Automate ile faturaları izleyin ve izleyin.](../media/content-understanding/process-invoices-flow.png)

Bu senaryoyı otomatikleştirdiğinizde şunları yapabilirsiniz:

- Verileri el ile yapmak yerine otomatik olarak faturalardan ayıklayarak zamandan ve paradan tasarruf edin.
- Faturaları denetlemek ve sorunları size bildirmek için iş akışlarını kullanarak olası hataları azaltın ve daha iyi uyumluluk sağlayın.

## <a name="scenario-track-information-from-contracts-by-using-the-unstructured-document-processing-model"></a>Senaryo: Yapılandırılmamış belge işleme modelini kullanarak sözleşmelerden bilgileri izleme

Başka bir örnek olarak, şirketinizin diğer şirketler veya bireylerle olan sözleşmelerini belirlemek için bir süreç ayarlayabilirsiniz. Bu sözleşmelerden müşteri adı, ücretler, tarihler veya diğer önemli bilgiler gibi önemli bilgileri ayıklamak için bir model ayarlayın ve bilgileri hızla görüntüleyebileceğiniz alanlar olarak kitaplığa ekleyin. İş düzenlemelerinize uygun uyumluluk için sözleşmelerin belirli bir süreden önce silinemeden önce silinemeden emin olmak için belge kitaplığına bir bekletme etiketi uygulayın.

1. İçerik merkezinden başlayın ve sözleşmeler için yeni bir yapılandırılmamış belge işleme modeli oluşturun.
2. Pozitif ve negatif örnekler için örnek belgeleri karşıya yükleyin, ardından sözleşme belgelerini tanımlamak ve sonuçları gözden geçirmek için eğitimi çalıştırın.
3. Ayıklayıcıyı sözleşmelerdeki alanları (istemci adı, ücret ve tarih gibi) belirleyecek şekilde eğitin ve ayıklayıcıyı test edin.
4. Model tamamlandığında, modeli sözleşmeleri karşıya yükleyebileceğiniz bir kitaplığa uygulayın.
5. Sözleşmelerin gerekli süre boyunca kitaplıkta tutulması için tarih alanına bir bekletme etiketi uygulayın.

![Syntex ve bekletme etiketleriyle sözleşmeleri izleyin ve izleyin.](../media/content-understanding/process-contracts-flow.png)

Bu senaryoyı otomatikleştirdiğinizde şunları yapabilirsiniz:

- Sözleşmelerden verileri el ile yapmak yerine otomatik olarak ayıklayarak zamandan ve paradan tasarruf edin.
- Sözleşmelerin uygun şekilde korunmasını sağlamak için bekletme etiketlerini kullanarak daha iyi uyumluluk sağlayın.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-syntex"></a>Senaryo: Syntex tabanlı kayıt yönetimi, belge idaresi ve uyumluluk süreçlerinde riskten kaçının

Risklerin azaltılması çoğu şirket için ortak bir hedeftir. Aşağıdakilere ihtiyacınız olabilir:

- Kiracınız genelinde bilgi idaresi sağlamanın/zorlamanın daha iyi bir yolu.
- Belgeleri, e-postaları ve projeler için "kayıtlar" olarak kabul edilen diğer iletişim biçimlerini sınıflandırma sistemini geliştirmek.
- Makbuzları, sözleşmeleri vb. denetlemek, şirket ilkeleriyle uyumluluğu sağlamak.
- Projelerin uyumluluk için gereken tüm belgelere sahip olduğundan emin olmak için.

Daha iyi idare gerektiren belgeleri ve formları yakalamak ve uygun şekilde sınıflandırmak, denetlemek ve işaretlemek için Syntex ile uyumluluk için bazı süreçler ayarlayın. İçeriği el ile etiketlemek için son kullanıcılara güvenmek yerine içeriği otomatik olarak sınıflandırmak için Syntex'e veya idare kurallarını ve arşivlemeyi el ile uygulamak için uyumluluk ekibine güvenebilirsiniz. Ayrıca basitleştirilmiş bir arama deneyimini etkinleştirebilir, veri birimlerini yönetebilir, kayıt yönetimi ve bekletme ilkeleri uygulayabilir, uyumluluğu sağlayabilir ve arşivleme ve temizleme yöntemlerini en iyi şekilde uygulayabilirsiniz.

Bu senaryoyı otomatikleştirdiğinizde şunların güvenliğini sağlayabilirsiniz:

- Uyumluluk sağlanır ve risk azalır.
- Taksonomi ve kayıt yönetimi tutarlı ve doğru şekilde uygulanır.
- İçerik birimleri denetleniyor.
- Çalışanlar doğru bağlamda doğru bilgileri kolayca bulabilir.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Senaryo: Daha önce erişilemeyen belgelerden bilgi yakalama

Çoğu kuruluşta büyük yasal belgeler, ilkeler, sözleşmeler, İk belgeleri ve idare yönergeleri depoları vardır. Projeler, sektörler, temalar, insanlar, coğrafi alanlar vb. gibi değerli bilgileri ayıklamak için bu veri depolarını mayınlayın.

Örneğin, bir İk yöneticisinin özgeçmişler, İk ilkeleri ve diğer formlar da dahil olmak üzere tüm İk belgelerine hızla erişmesi gerekir. Ayrıca özgeçmişlerden ve İk ile ilgili diğer belgelerden gerekli bilgileri belgeler arasında el ile elemeden hızla tanımlamak istiyorlar. Binlerce özgeçmişe, İk ilkesine ve çeşitli sitelere yayılmış olabilecek diğer belgelere el ile bakmak zorunda kalmadan ihtiyaç duydukları bilgileri hızla bulmalarını sağlayan bir çözüm arıyor.

Bu senaryoyı otomatikleştirdiğinizde şunları yapabilirsiniz:

- Dijital içerikten bilgilerin kilidini açın.
- İk ilkelerini, özgeçmişleri, satış belgelerini, teknik şemaları ve hesap planlarını sınıflandırıp bilgileri ayıklayın.
- Aradığınız doğru bilgileri veya belgeyi hızla bulun.
- En son bilgilere anında erişim elde edin.
- Arama sürelerini azaltın.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Senaryo: İçgörüler ve analizler sağlamak için veri işlemeyi geliştirme

Örneğin, bir ilaç şirketi syntex kullanarak liderlerinin sorularını yanıtlamak için FDA belgelerinden bilgi ayıklayabilir. Yanıtların daha kolay erişilebilir olması, bu yanıtları üretmek için gereken süreyi kısaltabilir ve liderlik sorularına daha doğru yanıtlar üretmek için verilerin kullanılabilirliğini artırabilir.

Örneğin, bir proje yöneticisinin liderlik ekibimden ürünle ilgili sorulara hızlı bir şekilde yanıt sağlaması gerekiyor. Birleştirilmiş bir panoda sorgularla ilgili bilgileri ve ölçümleri bulmaları gerekir. Ürün etiketlerinden, ürün broşürlerinden ve diğer malzemelerden ihtiyaç duydukları bilgileri ayıklayan ve liderlik ekiplerine geri bildirimde bulunurken kullanabilecekleri birleştirilmiş bir rapor oluşturan bir çözüm arıyor.

Bu senaryoyı otomatikleştirdiğinizde şunları yapabilirsiniz:

- Yanıt üretme süresini azaltın.
- Verilerin kullanılabilirliğini artırın.
- Daha doğru yanıtlar sağlayın.

## <a name="scenario-automate-order-processing"></a>Senaryo: Sipariş işlemeyi otomatikleştirme

Syntex ile müşteri siparişlerinin el ile işlenmesi süresini kısaltabilirsiniz. Örneğin, OCR işlemeyi kullanarak faks, e-posta veya kağıttan SharePoint'e sipariş yükleyebilir ve ardından otomatik işlemleri kullanarak yerine getirebilmeniz için bu siparişlerden meta verileri ayıklayabilirsiniz.

Örneğin, tedarik zinciri yöneticisi el ile veri girişinin neden olduğu hataları azaltmak ister. İş sistemlerine giden hataları azaltmak için gelen müşteri siparişlerinin (kağıt, faks veya e-posta) el ile gözden geçirilmesini ve veri girişini önlemek istiyorlar. Sipariş karşılama ve mutabakat için gelen sipariş bilgilerini doğrulamak, çekirdek verileri ayıklamak ve otomatik olarak ERP sistemlerine göndermek için yapay zeka ve makine öğrenmesi tekniklerini uygulayan bir çözüm istiyor.

Bu senaryoyı otomatikleştirdiğinizde şunların yapıldığından emin olabilirsiniz:

- Sipariş ve sevkiyat doğruluğu artar.
- Sipariş veya sevkiyat hatalarıyla ilişkili ücretler veya cezalar azaltılır.
- Faturalamadaki gecikmeler veya ödemeler azalır.
- Personel maliyetleri azaltılır.

## <a name="scenario-simplify-visa-renewal-process"></a>Senaryo: Vize yenileme sürecini basitleştirme

Syntex, önemli sözleşme bilgileri için anımsatıcıları ve yenilemeleri otomatikleştirmenize yardımcı olabilir. Örneğin, bir İk direktörünün çalışanların vizelerinin güncel veya zamanında yenilenmesini sağlaması gerekir. İnsanlara vizelerini güncellemek için basit ve sezgisel bir süreç vermek istiyorlar. Sözleşmelerden yenileme tarihlerini ayıklayan ve yenileme tarihleri yaklaştığında çalışanlara otomatik olarak anımsatıcılar gönderen bir çözüme ihtiyaçları vardır.

Bu senaryoyı otomatikleştirdiğinizde şunların yapıldığından emin olabilirsiniz:

- Uyumsuzluk düzeyleri azaltılır.
- El ile anımsatıcı sayısı azaltılır.
- Uyumsuzluk için ceza sayısı azalır.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex'i benimsemeye başlama](adoption-getstarted.md)

[Microsoft 365 çözümü kullanarak sözleşmeleri yönetme](solution-manage-contracts-in-microsoft-365.md)
