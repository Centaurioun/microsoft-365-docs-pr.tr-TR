---
title: Microsoft 365 Defender ile olay yanıtı
description: Microsoft 365 Defender portalında cihazlar, kullanıcılar ve posta kutuları arasında görülen olayları araştırın.
keywords: olaylar, uyarılar, saldırı hikayesi, araştırma, analiz etme, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: da8e2ea8c4f3c239324a2a15992a0bd831fca55d
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688216"
---
# <a name="incident-response-with-microsoft-365-defender"></a>Microsoft 365 Defender ile olay yanıtı

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender'deki bir olay, bir saldırının hikayesini oluşturan bağıntılı uyarıların ve ilişkili verilerin bir koleksiyonudur.

Microsoft 365 hizmetleri ve uygulamaları, şüpheli veya kötü amaçlı bir olay veya etkinlik algıladığında uyarılar oluşturur. Tek tek uyarılar, tamamlanmış veya devam eden bir saldırı hakkında değerli ipuçları sağlar. Ancak saldırılar genellikle cihazlar, kullanıcılar ve posta kutuları gibi farklı varlık türlerine karşı çeşitli teknikler uygular. Sonuç, kiracınızdaki birden çok varlık için birden çok uyarıdır.

Bir saldırı hakkında içgörü elde etmek için tek tek uyarıların birlikte pastalanması zor ve zaman alıcı olabileceğinden, Microsoft 365 Defender uyarıları ve ilişkili bilgilerini bir olayda otomatik olarak toplar.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender varlıkların olaylarını bir olayla ilişkilendirmesi." lightbox="../../media/incidents-overview/incidents.png":::

İlgili uyarıların bir olay halinde gruplanması, bir saldırının kapsamlı bir görünümünü sağlar. Örneğin, şunları görebilirsiniz:

- Saldırının başladığı yer.
- Hangi taktiklerin kullanıldığı.
- Saldırının kiracınıza ne kadar gittiğini.
- Kaç cihazın, kullanıcının ve posta kutusunun etkilendiği gibi saldırının kapsamı.
- Saldırıyla ilişkili tüm veriler.

[Etkinleştirilirse](m365d-enable.md) Microsoft 365 Defender otomatik olarak otomasyon ve yapay zeka aracılığıyla uyarıları [araştırabilir ve çözümleyebilir](m365d-autoir.md). Ayrıca, saldırıyı çözmek için ek düzeltme adımları da gerçekleştirebilirsiniz.

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında olaylar ve uyarılar

**Olayları olaylar & uyarıları > Microsoft 365 Defender** <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target=" blank">portalının</a> hızlı başlatılmasıyla olayları yönetirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender portalındaki Olaylar sayfası." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

Bir olay adı seçildiğinde olayın tüm saldırı hikayesi görüntülenir, örneğin:

- Olay içindeki uyarı sayfası: Olayla ilgili uyarıların kapsamı ve aynı sekmedeki bilgileri.
- Graf: Saldırının parçası olan farklı şüpheli varlıkları kullanıcılar, cihazlar ve posta kutuları gibi ilgili varlıklarına bağlayan saldırının görsel bir gösterimi. 

Varlık ayrıntılarını doğrudan grafikten görüntüleyebilir ve dosya silme veya cihaz yalıtımı gibi yanıt seçenekleriyle bunlar üzerinde işlem yapabilirsiniz.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 Defender portalındaki bir olayın saldırı hikayesi sayfasını gösteren ekran görüntüsü." lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

Bir olayın ek sekmeleri şunlardır:

- Uyarılar

  Olayla ilgili tüm uyarılar ve bilgileri.

- Aygıtları

  Olayın parçası olduğu veya olayla ilgili olduğu belirlenen tüm cihazlar.

- Kullanıcılar

  Olayın parçası olduğu veya olayla ilgili olduğu belirlenen tüm kullanıcılar.

- Posta kutu -ları

  Olayın parçası olduğu veya olayla ilgili olduğu belirlenen tüm posta kutuları.

- Sondajları

  Olaydaki uyarılar tarafından tetiklenen tüm [otomatik araştırma](m365d-autoir.md) .

- Kanıt ve Yanıt

  Olayın uyarılarında desteklenen tüm olaylar ve şüpheli varlıklar.

- Özet

  Uyarılarla ilişkili etkilenen varlıklara hızlı bir genel bakış.

> [!NOTE]
> *Desteklenmeyen uyarı türü* uyarı durumu görüyorsanız, bu otomatik araştırma özelliklerinin otomatik araştırma çalıştırmak için bu uyarıyı alamayacağı anlamına gelir. Ancak [, bu uyarıları el ile araştırabilirsiniz](investigate-incidents.md#alerts).

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Microsoft 365 Defender için örnek olay yanıtı iş akışı

Microsoft 365'teki olaylara Microsoft 365 Defender portalıyla yanıt vermek için örnek bir iş akışı aşağıda verilmiştir.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 Defender portalı için olay yanıtı iş akışı örneği." lightbox="../../media/incidents-overview/incidents-example-workflow.png":::

Sürekli olarak, olay kuyruğundaki analiz ve çözüm için en yüksek öncelikli olayları belirleyin ve yanıt için hazır olmalarını sağlayın. Bu, aşağıdakilerin bir bileşimidir:

- [Olay](incident-queue.md) kuyruğunun filtrelenmesi ve sıralanması yoluyla en yüksek öncelikli olayları belirlemeye öncelik verme.
- Başlıkları değiştirerek, bunları analiste atayarak ve etiketlerle açıklamalar ekleyerek olayları [yönetme](manage-incidents.md).

Kendi olay yanıtı iş akışınız için şu adımları göz önünde bulundurun:

1. Her olay için bir [saldırı ve uyarı araştırması ve analizi](investigate-incidents.md) başlatın:

   1. Kapsamını, önem derecesini, algılama kaynağını ve hangi varlıkların etkilendiğini anlamak için olayın saldırı hikayesini görüntüleyin.

   1. Olay içindeki uyarı hikayesiyle bunların kaynağını, kapsamını ve önem derecesini anlamak için uyarıları analiz etmeye başlayın.

   1. Gerektiğinde, etkilenen cihazlar, kullanıcılar ve posta kutuları hakkında grafla bilgi toplayın. Tüm ayrıntıları içeren bir açılır öğeyi açmak için herhangi bir varlığa sağ tıklayın.

   1. **araştırma** sekmesiyle Microsoft 365 Defender [bazı uyarıları otomatik olarak nasıl çözümlediğini](m365d-autoir.md) görün.

   1. Kanıt **ve Yanıt** sekmesiyle daha fazla bilgi için gerektiğinde olay için veri kümesindeki bilgileri kullanın.

2. Analizinizden sonra veya analiz sırasında, saldırının ek etkisini azaltmak ve güvenlik tehdidinin ortadan kaldırılmasını sağlamak için kapsama gerçekleştirin.

3. Mümkün olduğunca, kiracı kaynaklarınızı olay öncesinde bulundukları duruma geri yükleyerek saldırıdan kurtarın.

4. [Olayı çözün](manage-incidents.md#resolve-an-incident) ve olay sonrası öğrenme için zaman ayırarak aşağıdakileri yapın:

   - Saldırının türünü ve etkisini anlama.
   - Bir güvenlik saldırısı eğilimi için [Tehdit Analizi'nde](threat-analytics.md) ve güvenlik topluluğunda saldırıyı araştırın.
   - Olayı çözmek için kullandığınız iş akışını hatırlayın ve standart iş akışlarınızı, süreçlerinizi, ilkelerinizi ve playbook'larınızı gerektiği gibi güncelleştirin.
   - Güvenlik yapılandırmanızdaki değişikliklerin gerekli olup olmadığını belirleyin ve bunları uygulayın.

Güvenlik analizi konusunda yeniyseniz ek bilgi edinmek ve örnek [bir olayda adım adım ilerletmek için ilk olayınıza yanıt vermeye giriş](incidents-overview.md) bölümüne bakın.

Microsoft ürünleri genelinde olay yanıtı hakkında daha fazla bilgi için [bu makaleye](/security/compass/incident-response-overview) bakın.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Microsoft 365 Defender için örnek güvenlik işlemleri

aşağıda Microsoft 365 Defender için güvenlik işlemlerinin (SecOps) bir örneği verilmiştır.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Microsoft 365 Defender için güvenlik işlemleri örneği" lightbox="../../media/incidents-overview/incidents-example-operations.png":::

Günlük görevler şunları içerebilir:

- Olayları [yönetme](manage-incidents.md)
- İşlem merkezinde [otomatik araştırma ve yanıt (AIR)](m365d-action-center.md) eylemlerini gözden geçirme
- En son [Tehdit Analizini](threat-analytics.md) gözden geçirme
- [Olaylara yanıt verme](investigate-incidents.md)

Aylık görevler şunları içerebilir:

- [AIR ayarlarını](m365d-configure-auto-investigation-response.md) gözden geçirme
- [Güvenli Puan](microsoft-secure-score-improvement-actions.md) ve [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) gözden geçirme
- BT güvenlik yönetimi zincirinize raporlama

Üç aylık görevler arasında Bir rapor ve güvenlik sonuçlarının Bilgi Güvenliği Başkanı'na (CISO) bildirilmesi yer alabilir.

Yıllık görevler, personelinizi, sistemlerinizi ve süreçlerinizi test etmek için önemli bir olay veya ihlal alıştırması gerçekleştirmeyi içerebilir.

İşlemleri, ilkeleri ve güvenlik yapılandırmalarını güncelleştirmek veya iyileştirmek için günlük, aylık, üç aylık ve yıllık görevler kullanılabilir.

Daha fazla ayrıntı için bkz. [Microsoft 365 Defender güvenlik işlemlerinizle tümleştirme](integrate-microsoft-365-defender-secops.md).

### <a name="secops-resources-across-microsoft-products"></a>Microsoft ürünleri genelinde SecOps kaynakları

Microsoft'un ürünleri arasında SecOps hakkında daha fazla bilgi için şu kaynaklara bakın:

- [Yetenek -lerini](/security/compass/security-operations-capabilities)
- [En iyi yöntemler](/security/compass/security-operations)
- [Videolar ve slaytlar](/security/compass/security-operations-videos-and-decks)

## <a name="get-incident-notifications-by-email"></a>Olay bildirimlerini e-postayla alma

Personelinize yeni olaylar veya mevcut olaylarla ilgili güncelleştirmeler hakkında e-postayla bildirim göndermek için Microsoft 365 Defender ayarlayabilirsiniz. Bildirimleri şu temel alarak almayı seçebilirsiniz:

- Uyarı önem derecesi
- Uyarı kaynakları 
- Cihaz grubu

**Yalnızca belirli hizmet kaynağı için e-posta bildirimleri almayı seçin: E-posta** bildirimleri almak istediğiniz belirli hizmet kaynaklarını kolayca seçebilirsiniz.
 
**Belirli algılama kaynaklarıyla daha ayrıntılı bilgi edinin**: Yalnızca belirli bir algılama kaynağı için bildirim alabilirsiniz. 

**Algılama veya hizmet kaynağı başına önem derecesini ayarlayın**: E-posta bildirimlerini yalnızca kaynak başına belirli önem derecelerinde almayı seçebilirsiniz. Örneğin, EDR için Orta ve Yüksek uyarılar ve Microsoft Defender Uzmanları için tüm önem dereceleri için bildirim alabilirsiniz.  

E-posta bildirimi olayla ilgili olay adı, önem derecesi ve kategoriler gibi önemli ayrıntıları içerir. Ayrıca doğrudan olaya gidip analizinizi hemen başlatabilirsiniz. Daha fazla bilgi için bkz [. Olayları araştırma](investigate-incidents.md).

E-posta bildirimlerinde alıcı ekleyebilir veya kaldırabilirsiniz. Yeni alıcılar eklendikten sonra olaylar hakkında bildirim alır.

> [!NOTE]
> E-posta bildirim ayarlarını yapılandırmak için **Güvenlik ayarlarını yönet** iznine sahip olmanız gerekir. Temel izin yönetimini kullanmayı seçtiyseniz, Güvenlik Yöneticisi veya Genel Yönetici rollerine sahip kullanıcılar e-posta bildirimlerini yapılandırabilir. <br> <br>
Benzer şekilde, kuruluşunuz rol tabanlı erişim denetimi (RBAC) kullanıyorsa yalnızca yönetmenize izin verilen cihaz gruplarına göre bildirim oluşturabilir, düzenleyebilir, silebilir ve alabilirsiniz.

### <a name="create-a-rule-for-email-notifications"></a>E-posta bildirimleri için kural oluşturma

Yeni bir kural oluşturmak ve e-posta bildirim ayarlarını özelleştirmek için bu adımları izleyin.

1. Gezinti bölmesinde [Microsoft 365 Defender](https://security.microsoft.com) gidin, **Ayarlar > Microsoft 365 Defender > Olay e-posta bildirimleri'ni** seçin.
2. **Öğe ekle'yi** seçin.
3. **Temel Bilgiler** sayfasında kural adını ve açıklamayı yazın ve **İleri'yi** seçin.
4. **Bildirim ayarları** sayfasında şunları yapılandırın:
    - **Uyarı önem derecesi** - Olay bildirimini tetikleyecek uyarı önem derecelerini seçin. Örneğin, yalnızca yüksek önem dereceli olaylar hakkında bilgi almak istiyorsanız **Yüksek'i** seçin.
    - **Cihaz grubu kapsamı** - Tüm cihaz gruplarını belirtebilir veya kiracınızdaki cihaz grupları listesinden seçim yapabilirsiniz.
    - **Olay başına yalnızca bir bildirim gönder - Olay başına** bir bildirim isteyip istemediğinizi seçin.
    - **E-postaya kuruluş adını ekle - Kuruluşunuzun adının e-posta** bildiriminde görünmesini isteyip istemediğinizi seçin.
    - **Kiracıya özgü portal bağlantısını ekle** - Belirli bir Microsoft 365 kiracısına erişim için e-posta bildiriminde kiracı kimliğine sahip bir bağlantı eklemek isteyip istemediğinizi seçin.

    :::image type="content" source="../../media/get-incident-notifications/incidents-email-notification-settings.png" alt-text="Microsoft 365 Defender portalında olay e-posta bildirimleri için Bildirim ayarları sayfasının ekran görüntüsü." lightbox="../../media/get-incident-notifications/incidents-email-notification-settings.png":::

5. **İleri**'yi seçin. **Alıcılar** sayfasında, olay bildirimlerini alacak e-posta adreslerini ekleyin. Her yeni e-posta adresini yazdıktan sonra **Ekle'yi** seçin. Bildirimleri test etmek ve alıcıların gelen kutularına aldığından emin olmak için **Test e-postası gönder'i** seçin.
6. **İleri**'yi seçin. **Kuralı gözden geçir** sayfasında kuralın ayarlarını gözden geçirin ve kural **oluştur'u** seçin. Alıcılar, ayarlara göre e-posta aracılığıyla olay bildirimleri almaya başlar.

Mevcut bir kuralı düzenlemek için kural listesinden bu kuralı seçin. Kural adının yer aldığı bölmede **Kuralı düzenle'yi** seçin ve **Temel Bilgiler**, **Bildirim ayarları** ve **Alıcılar** sayfalarında değişikliklerinizi yapın.

Kuralı silmek için kural listesinden bu kuralı seçin. Kural adının olduğu bölmede **Sil'i** seçin.

Bildirimi aldıktan sonra doğrudan olaya gidebilir ve araştırmanıza hemen başlayabilirsiniz. Olayları araştırma hakkında daha fazla bilgi için bkz[. Microsoft 365 Defender'de olayları araştırma](investigate-incidents.md).

## <a name="training-for-security-analysts"></a>Güvenlik analistleri için eğitim

Olayları ve uyarıları yönetmek için Microsoft 365 Defender kullanmayı anlamak için Microsoft Learn'den bu öğrenme modülünü kullanın.

|Eğitim:|Microsoft 365 Defender ile olayları araştırma|
|---|---|
|![Microsoft 365 Defender eğitim simgesiyle olayları araştırın.](../../media/incidents-overview/m365-defender-address-security-investigation.svg)| Microsoft 365 Defender birden çok hizmetten gelen tehdit verilerini birleştirir ve bunları olaylar ve uyarılar halinde birleştirmek için yapay zekayı kullanır. Sonraki yanıt ve çözüm için bir olayla yönetimi arasındaki süreyi en aza indirmeyi öğrenin. <p> 27 dk - 6 Birim |

> [!div class="nextstepaction"]
> [Başlangıç >](/training/modules/defender-investigate-incidents/)

## <a name="next-steps"></a>Sonraki adımlar

Güvenlik ekibinizdeki deneyim düzeyinize veya rolünüz temelinde listelenen adımları kullanın.

### <a name="experience-level"></a>Deneyim düzeyi

Güvenlik analizi ve olay yanıtıyla ilgili deneyim düzeyiniz için bu tabloyu izleyin.

| Düzey | Adımlar |
|:-------|:-----|
| **Yeni** | <ol><li> Örnek bir saldırıyla Microsoft 365 Defender portalında tipik bir analiz, düzeltme ve olay sonrası gözden geçirme sürecinin kılavuzlu turuna ulaşmak için [İlk olay yönergelerinize yanıt verme kılavuzuna](first-incident-overview.md) bakın. </li><li> Önem derecesine ve diğer faktörlere göre [hangi olayların önceliklendirilmesi](incident-queue.md) gerektiğini görün. </li><li> [Olay](manage-incidents.md) yönetimi iş akışınıza göre etiketleri ve açıklamaları yeniden adlandırmayı, atamayı, sınıflandırmayı ve eklemeyi içeren olayları yönetin.</li></ol> |
| **Deneyimli** | <ol><li> Microsoft 365 Defender portalının **Olaylar** sayfasından olay kuyruğuyla çalışmaya başlayın. Buradan: </li> <ul><li> Önem derecesine ve diğer faktörlere göre [hangi olayların önceliklendirilmesi](incident-queue.md) gerektiğini görün. </li><li> [Olay](manage-incidents.md) yönetimi iş akışınıza göre etiketleri ve açıklamaları yeniden adlandırmayı, atamayı, sınıflandırmayı ve eklemeyi içeren olayları yönetin. </li><li> Olaylarla [ilgili incelemeler](investigate-incidents.md) yapın. </li></ul> </li><li> Tehdit analizi ile yeni ortaya çıkan tehditleri izleyin ve yanıt [verin](threat-analytics.md). </li><li>  [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) ile tehditleri proaktif olarak avlar. </li><li> Kimlik avı, parola spreyi ve uygulama onayı verme saldırıları hakkında ayrıntılı yönergeler için bu [olay yanıtı playbook'larına](/security/compass/incident-response-playbooks) bakın. </li></ol> |

### <a name="security-team-role"></a>Güvenlik ekibi rolü

Güvenlik ekibi rolünüz temelinde bu tabloyu izleyin.

| Rol | Adımlar |
|---|---|
| Olay yanıtlayıcısı (Katman 1) | Microsoft 365 Defender portalının **Olaylar** sayfasından olay kuyruğuyla çalışmaya başlayın. Buradan: <ul><li> Önem derecesine ve diğer faktörlere göre [hangi olayların önceliklendirilmesi](incident-queue.md) gerektiğini görün. </li><li> [Olay](manage-incidents.md) yönetimi iş akışınıza göre etiketleri ve açıklamaları yeniden adlandırmayı, atamayı, sınıflandırmayı ve eklemeyi içeren olayları yönetin. </li></ul> |
| Güvenlik araştırmacısı veya analisti (Katman 2) | <ol><li> Microsoft 365 Defender portalının Olaylar sayfasından **olaylarla** ilgili [araştırma](investigate-incidents.md) yapın. </li><li> Kimlik avı, parola spreyi ve uygulama onayı verme saldırıları hakkında ayrıntılı yönergeler için bu [olay yanıtı playbook'larına](/security/compass/incident-response-playbooks) bakın. </li></ol> |
| Gelişmiş güvenlik analisti veya tehdit avcısı (Katman 3) | <ol><li>Microsoft 365 Defender portalının Olaylar sayfasından **olaylarla** ilgili [araştırma](investigate-incidents.md) yapın. </li><li> Tehdit analizi ile yeni ortaya çıkan tehditleri izleyin ve yanıt [verin](threat-analytics.md). </li><li> [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) ile tehditleri proaktif olarak avlar. </li><li> Kimlik avı, parola spreyi ve uygulama onayı verme saldırıları hakkında ayrıntılı yönergeler için bu [olay yanıtı playbook'larına](/security/compass/incident-response-playbooks) bakın. |
| SOC yöneticisi | [Microsoft 365 Defender Güvenlik İşlemleri Merkezinizle (SOC) tümleştirmeyi](integrate-microsoft-365-defender-secops.md) öğrenin. |
