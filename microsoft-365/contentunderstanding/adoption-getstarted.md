---
title: Microsoft Syntex'i benimsemeye başlama
ms.author: chucked
author: chuckedmonson
manager: pamgreen
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
description: İş süreçlerinizi kolaylaştırmaya yardımcı olmak için kuruluşunuzda Microsoft Syntex'i kullanmayı ve uygulamayı öğrenin.
ms.openlocfilehash: e824356fb5c729a6a508abebecffd4b6ea0c6e45
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660587"
---
# <a name="get-started-driving-adoption-of-microsoft-syntex"></a>Microsoft Syntex'i benimsemeye başlama

Microsoft Syntex'te bulunan akıllı içerik hizmetlerini üç bölüme sahip olarak düşünün:

- **İçerik anlama:** Bilgi bulma ve yeniden kullanma için meta verileri otomatik olarak uygulamak üzere içerikten bilgileri sınıflandırmak ve ayıklamak için kodsuz yapay zeka modelleri oluşturun. [İçerik anlama](document-understanding-overview.md) hakkında daha fazla bilgi edinin.
- **İçerik işleme:** Power Automate'i kullanarak içerik yakalama, alma ve kategorilere ayırma işlemlerini otomatikleştirin ve içerik odaklı işlemleri kolaylaştırın. [İçerik işleme](form-processing-overview.md) hakkında daha fazla bilgi edinin.
- **İçerik uyumluluğu:** Microsoft Purview Bilgi Koruması tümleştirmesi ile güvenliği ve idareyi geliştirmek için içeriği denetleme ve yönetme.

Yeni yapay zeka hizmetleri ve özellikleriyle Syntex kullanarak içerik anlama ve sınıflandırma uygulamalarını doğrudan içerik yönetimi akışına oluşturabilirsiniz. Özel model türleri için içeriğinizi anlamanın üç farklı yolu vardır. Kullandığınız özel model türü, dosya biçimine ve kullanım örneğine bağlıdır.

| Yapılandırılmamış belge işleme | Yapılandırılmış belge işleme | Serbest biçimli belge işleme |
| ------- | ------- | ------- |
| syntex'in bir parçası olan içerik merkezinde oluşturulur. | Belge kitaplığından oluşturulur. | Belge kitaplığından oluşturulur. |
| Yerel arabirimde oluşturulan model. | Yapay zeka oluşturucusunda oluşturulan model. | Yapay zeka oluşturucusunda oluşturulan model. |
| Yarı yapılandırılmış veya yapılandırılmamış dosya biçimleri için kullanılır. | Yapılandırılmış veya yarı yapılandırılmış dosya biçimleri için kullanılır. | Yapılandırılmamış veya serbest biçimli dosya biçimleri için kullanılır. |
| İsteğe bağlı ayıklayıcılarla eğitilebilir sınıflandırıcı. | Ayarlanabilir sınıflandırıcı. | Ayarlanabilir sınıflandırıcı. |
| Birden çok kitaplık için uygulanabilir. | Tek bir kitaplıkla sınırlıdır. | Tek bir kitaplıkla sınırlıdır. |
| Negatif örnekler de dahil olmak üzere 5-10 PDF, Office veya e-posta dosyaları üzerinde eğitin. | PDF, JPG, PNG biçiminde eğitin, toplam 50 MB/500 pp. | PDF, JPG, PNG biçiminde eğitin, toplam 50 MB/500 pp. |

Özel özelliklerin daha eksiksiz bir karşılaştırması için bkz. [Syntex'te özel modelleri karşılaştırma](difference-between-document-understanding-and-form-processing-model.md).

Özel bir model oluşturmanız gerekmiyorsa, belirli yapılandırılmış belgeler için önceden eğitilmiş önceden oluşturulmuş bir [model](prebuilt-overview.md) kullanabilirsiniz.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>İyileştirme için pilot iş senaryolarını belirleme

Kuruluşunuzda Syntex'i kullanmaya hazırlanmak için öncelikle yararlı olacağı senaryoları anlamanız gerekir. "Neden", hangi modelin gerekli olacağını ve modelin uygulanacağı yere göre kuruluşunuzun nasıl yapılandırılacağını belirlemeye yardımcı olur. Özel modellerin kuruluşunuza yardımcı olabileceği birkaç senaryo aşağıdadır:

- **İçerik işleme**: sözleşmeleri, iş deyimlerini ve form benzeri diğer belgeleri işleme. Formları alın, alanları anlamak ve eşlemek için modeli eğitin ve ardından verileri otomatik olarak toplamak için formlarınızı çalıştırın.

- **Fatura analizi**: Faturalarınızdan ilgili ayrıntıları çekin ve ilkeye uygun olduklarından veya uygun şekilde işlendiklerinden emin olun.

Syntex'in kuruluşunuza nasıl yardımcı olabileceğini düşünün:

- İş süreçlerini otomatikleştirme
- Arama doğruluğunu geliştirme
- Uyumluluk riskini yönetme

Dikkate almanız gereken iş senaryolarını düşünürken kendinize aşağıdaki soruları sorun:

- Gerçek bir sorunu çözer mi?
- Yaygın olarak kullanılacak mı yoksa geniş bir etkisi olacak mı?
- Elde edilebilir mi?
- Başarıyı ölçebilir misiniz?

Etki ve uygulama kolaylığına göre senaryoların önceliklerini belirleyin. İlk odak alanınızı kolayca uygulanabilecek daha yüksek etki senaryoları haline getirin. Uygulanması zor olan düşük etki senaryolarının önceliklerini kaldırın.

Kuruluşunuzda Syntex'i nasıl kullanabileceğiniz hakkında fikir almak için [örnek senaryoları ve kullanım örneklerini](adoption-scenarios.md) kullanın.

## <a name="identify-roles-and-responsibilities"></a>Rolleri ve sorumlulukları belirleme

Kuruluşunuzda modelleri kimin oluşturacağını ve yöneteceğini belirleyin. Aşağıdaki roller söz konusu olabilir.

| SharePoint/Bilgi yöneticisi | Power Platform yöneticisi | Bilgi yöneticisi | Model sahibi |
|:-------|:-------|:-------|:-------|
| AAD rolü| AAD rolü | AAD rolü | Şampiyonlar |
| Yapılandırılmış belge işleme ve serbest biçimli belge işleme modellerini yapılandırma | Dataverse ortamını yapılandırma | Kullanım örneklerini toplama | İş kullanım örneklerini toplama |
| İçerik merkezlerini ve izinleri yönetme| AIB kredilerini satın alma ve ayırma | En iyi uygulamaları oluşturma ve model analizini gözden geçirme | Model oluşturma ve uygulama |

Bilgi yöneticisi, iş süreci sahibi ve içerik modeli sahibi, kuruluşta örnek modeller ve şampiyon benimsemesi oluşturur. Uyumluluk yöneticisi ve taksonomi yöneticileriyle ilgili olabilecek diğer kişiler.

Modelleri nerede oluşturup uygulayacak? İyileştirilebilen mevcut süreçler veya depolar var mı?

- Yapılandırılmamış belge işleme: Farklı iş alanları için birden çok içerik merkezi oluşturabilirsiniz.
- Yapılandırılmış belge işleme veya serbest biçimli belge işleme: Bu eylemi alacak sitelere karar verin.

## <a name="strategic-positioning"></a>Stratejik konumlandırma

Syntex kullanma stratejisine uygun olduklarından emin olmak için proje katılımcılarıyla birlikte çalışın. Bu konumlandırmaya yardımcı olmak için aşağıdaki kaynakları araştırın ve sağlayın:

- İş sonuçları:
  - Olası mali sonuçlar
  - Olası çeviklik sonuçları
  - İş sonucu şablonu
- Paydaşlar/Exec sponsoru satın alma/hizalama
  - İş olayı desteleri
  - Finansal modeller
  - Şirket hazırlığı - kültür

## <a name="identify-stakeholders"></a>Paydaşları belirleme

Projeniz için paydaşları belirleyin.

|Rol |Sorumluluk |Bölüm |
|:-------|:-------|:--------|
| Yönetici sponsoru   | Üst düzey vizyon ve değerleri şirkete iletme   |  Yönetici liderliği   |
| Proje müşteri adayı | Başlatma yürütme ve dağıtım işleminin tamamını denetleme | Proje yönetimi |
| Bilgi yöneticileri| İçerik merkezleri oluşturma ve yönetme | BT veya diğer departman|
| İçerik yöneticileri ve model sahipleri| Kullanım örneklerini toplama ve model oluşturma ve uygulama | Herhangi bir departman|
| Şampiyonlar | İtiraz işlemeyi yaygınlaştırmaya ve yönetmeye yardımcı olun | Herhangi bir departman (personel) |
| Kiracı yöneticisi | Kiracı düzeyi ayarlarını yapılandırma | BT departmanı|
| Power Platform yöneticisi| Dataverse ortamını yapılandırma | BT departmanı|

> [!NOTE]
> Dağıtımınız boyunca bu rollerin her birinin yerine getirilmesini önersek de, tanımlanan çözümünüzü kullanmaya başlamak için tümünün gerekli olmadığını fark edebilirsiniz.

## <a name="readiness-checklist"></a>Hazırlık denetim listesi

Syntex'i uygulamaya hazırlanmak için şunları yapmanız gerekir:

![İçerik anlama için hazır olma.](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Bitiş durumunu planlama
    - Modeller son değil, araçlardır.
    - Ayıklanan meta verilerin değerinden şu şekilde yararlanmayı planlayın:
      - Arama
      - Biçimlendirmeyi filtreleme ve görüntüleme
      - Uyumluluk
      - Otomasyon
2. Tanımlamak
    - Mevcut bilgi mimarisini ve içerik yönetimi özellik kullanımını anlama.
    - Mevcut içerik türleri modeller için iyi adaylar mıdır?
    - Meta verilerle hangi mevcut işlemler geliştirilebilir?
3. Design
    - Bilgi mimarisi, yönetilen meta veriler ve içerik türlerine yaklaşımınızı tasarlar.
    - Tanım, oluşturma ve yönetim sürecini tasarlar.

## <a name="engage-your-organization"></a>Kuruluşunuzla etkileşime geçme

1. Bahis sahiplerini belirleyin, senaryoları onaylayın ve bir proje planı geliştirin.
2. Ayarları yapılandırın ve lisansları uygulayın.
3. Farkındalık ve eğitime başlayın - şampiyonları işe alın.
4. Aşamalı olarak dağıt.  
5. Geri bildirim toplayın ve yineleme yapın.
6. Kullanım gerektiğinde AI Builder kredileri için plan arttıkça.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex benimseme merkezi](https://adoption.microsoft.com/sharepoint-syntex/adoption/)

[Microsoft Syntex için senaryolar ve kullanım örnekleri](adoption-scenarios.md)

[Microsoft Syntex'teki model türlerine genel bakış](syntex-overview.md)
