---
title: Insider risk yönetimi adli kanıtlarını kullanmaya başlama (önizleme)
description: Microsoft Purview'da insider risk yönetimi adli kanıtlarını kullanmaya başlayın. Adli kanıt, kullanıcının eylemlerinin risk oluşturup oluşturmadığını ve bir güvenlik olayına yol açıp açmadığını saptamaya yardımcı olmak için yakalanan güvenlikle ilgili kullanıcı etkinliğini görüntülemeye yönelik bir araştırma aracıdır.
keywords: Microsoft 365, Microsoft Purview, insider riski, risk yönetimi, uyumluluk
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 1d4406ea6372786fda542d2a9b4e83f2ede9abac
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623945"
---
# <a name="get-started-with-insider-risk-management-forensic-evidence-preview"></a>Insider risk yönetimi adli kanıtlarını kullanmaya başlama (önizleme)

>[!IMPORTANT]
>Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

## <a name="configure-forensic-evidence"></a>Adli kanıtı yapılandırma

Kuruluşunuzda adli kanıt yapılandırmak, insider risk yönetimi ilke şablonlarından diğer ilkeleri yapılandırmaya benzer. Genel olarak, adli kanıt ayarlamak için aynı temel yapılandırma adımlarını izleyeceksiniz, ancak temel yapılandırma adımlarını kullanmaya başlamadan önce özelliğe özgü yapılandırma eylemleri gerektiren birkaç alan vardır.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

### <a name="step-1-confirm-your-subscription-and-configure-data-storage-access"></a>1. Adım: Aboneliğinizi onaylayın ve veri depolama erişimini yapılandırın

Adli kanıtlarla çalışmaya başlamadan önce [insider risk yönetimi aboneliğinizi](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-insider-risk-management) ve tüm eklentileri onaylamanız gerekir.

Ayrıca, kuruluşunuz için adli kanıt yakalama depolamasını desteklemek için güvenlik duvarı izin verilenler listenize aşağıdaki etki alanını eklemeniz gerekir:

- *compliancedrive.microsoft.com*

Yakalamalar ve yakalama verileri bu etki alanında depolanır ve yalnızca kuruluşunuza atanır. Başka hiçbir Microsoft 365 kuruluşu, kuruluşunuz için adli kanıt yakalamalarına erişir.

### <a name="step-2-configure-supported-devices"></a>2. Adım: Desteklenen cihazları yapılandırma

Adli kanıt yakalamaya uygun kullanıcı cihazları [Microsoft Purview uyumluluk portalı](/microsoft-365/compliance/microsoft-365-compliance-center) eklenmelidir ve Microsoft Purview İstemcisi yüklü olmalıdır. 

>[!IMPORTANT]
>Microsoft Purview İstemcisi, cihaz yapılandırması ve performans ölçümleriyle ilgili genel tanılama verilerini otomatik olarak toplar. Bu, kritik hatalara, RAM tüketimine, işlem hatalarına ve diğer verilere ilişkin verileri içerir. Bu veriler, istemcinin durumunu değerlendirmemize ve sorunları tanımlamamıza yardımcı olur. Tanılama verilerinin nasıl kullanılabileceğini öğrenmek için [Microsoft Ürün Koşulları'nda](https://www.microsoft.com/licensing/product-licensing/products) Online Services ile Yazılım Kullanımı bölümüne bakın.

Adli kanıttaki görsel yakalamalar aşağıdaki cihazlar/yapılandırmalar için desteklenir:

- En son Windows 10 veya Windows 11 x64 derlemesi
- Cihaz başına en fazla 4 monitör

Cihazları eklemek için, Microsoft [365'e cihaz ekleme ve Windows 11 Windows 10 genel bakış](/microsoft-365/compliance/device-onboarding-overview) makalesinde açıklanan adımları tamamlayın.

Microsoft Purview İstemcisi'ni yüklemek için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)İstemci yüklemesi'ne** >  gidin.
2. Windows **yükleme paketini indirmek için Yükleyici paketini indir (x64 sürümü)** seçeneğini belirleyin.
3. Yükleme paketini indirdikten sonra istemciyi kullanıcıların cihazlarına yüklemek için tercih ettiğiniz yöntemi kullanın. Bu seçenekler, istemci yüklemesini otomatikleştirmeye yardımcı olmak için istemciyi cihazlara veya araçlara el ile yüklemeyi içerebilir:

    - **Microsoft Endpoint Manager**: [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), tüm cihazlarınızı yönetmek için tümleşik bir çözümdür. Microsoft, [karmaşık](/mem/configmgr/core/understand/introduction) bir geçiş olmadan ve basitleştirilmiş lisanslama ile [Configuration Manager ve Intune](/mem/intune/fundamentals/what-is-intune) bir araya getirir.
    - **Üçüncü taraf cihaz yönetimi çözümleri**: Kuruluşunuz üçüncü taraf cihaz yönetimi çözümleri kullanıyorsa, istemciyi yüklemek için bu araçların belgelerine bakın.


### <a name="step-3-configure-settings"></a>3. Adım: Ayarları yapılandırma

Adli kanıt, yakalanan güvenlikle ilgili kullanıcı etkinliği türleri, parametreleri yakalama, bant genişliği sınırları ve çevrimdışı yakalama seçenekleri için esneklik sağlayan çeşitli yapılandırma ayarlarına sahiptir. Adli kanıt yakalama, yalnızca birkaç adımda gereksinimlerinize göre ilkeler oluşturmanıza olanak tanır ve bir ilkeye kullanıcı eklemek için çift yetkilendirme gerekir.

Adli kanıt ayarlarını yapılandırmak için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Adli kanıt ayarları'na** gidin.
2. **Adli kanıt ilkelerinizde destek yakalamayı** etkinleştirmek için Adli kanıt yakalama'yı seçin. Bu daha sonra kapatılırsa, adli kanıt ilkeleri için daha önce eklenen tüm kullanıcılar kaldırılır.

    >[!IMPORTANT]
    >Kullanıcıların cihazlarında etkinlik yakalamak için kullanılan Microsoft Purview İstemcisi, [Microsoft Ürün Koşulları'nda](https://www.microsoft.com/licensing/product-licensing/products) Çevrimiçi Hizmetler ile Yazılım Kullanımı kapsamında lisanslanmıştır. Müşterilerin, microsoft Purview İstemcisi de dahil olmak üzere tüm geçerli yasalara uygun olarak insider risk yönetimi çözümünü kullanmakla tek sorumlu olduğunu unutmayın.
 
1. **Yakalama penceresi** bölümünde etkinlik yakalamanın ne zaman başlatılacağını ve durdurulacağını tanımlayın. Kullanılabilir değerler *10 saniye*, *30 saniye*, *1 dakika*, *3 dakika* veya *5 dakikadır*.
1. **Bant genişliği sınırını karşıya yükle** bölümünde, kullanıcı başına günlük veri depolama hesabınıza yüklenecek yakalama verilerinin miktarını tanımlayın. Kullanılabilir değerler *100 MB*, *250 MB*, *500 MB*, *1 GB* veya *2 GB'tır*.
1. **Çevrimdışı yakalama** bölümünde, gerekirse çevrimdışı yakalamayı etkinleştirin. Etkinleştirildiğinde, kullanıcıların çevrimdışı etkinliği yakalanır ve bir sonraki çevrimiçi olduklarında veri depolama hesabınıza yüklenir.
1. **Çevrimdışı yakalama önbellek sınırı** bölümünde, çevrimdışı yakalama etkinleştirildiğinde kullanıcıların cihazlarında depolanacağı en büyük önbellek boyutunu tanımlayın. Kullanılabilir değerler *100 MB*, *250 MB*, *500 MB*, *1 GB* veya *2 GB'tır*.
1. **Kaydet**'i seçin.

### <a name="step-4-create-a-policy"></a>4. Adım: İlke oluşturma

Adli kanıt ilkeleri, yapılandırılmış cihazlarda yakalanacak güvenlikle ilgili kullanıcı etkinliğinin kapsamını tanımlar. Onaylanan kullanıcıların cihazlarında gerçekleştirdiği tüm etkinlikleri (tüm tuş vuruşları, fare hareketleri vb.) ve yalnızca belirli etkinlikleri (dosyaları yazdırma veya çıkarma gibi) yakalayan ek ilkeleri yakalayan bir ilkeniz olabilir. Oluşturulduktan sonra, istekleri onaylanan kullanıcılar için hangi etkinliğin yakalanacaklarını denetlemek için bu ilkeleri adli kanıt isteklerine ekleyeceksiniz.

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Adli kanıt ilkeleri'ne** gidin.
2. **Adli kanıt ilkesi oluştur'u** seçin.
3. **Kapsam** sayfasında, yakalanacak güvenlikle ilgili kullanıcı etkinliğinin kapsamını seçersiniz. Aşağıdaki seçeneklerden birini seçin:

    - **Belirli etkinlikler**: Bu seçenek yalnızca kullanıcıların dahil olduğu ilkeler tarafından algılanan etkinlikleri yakalar. Bu etkinlikler, adli kanıt ilkelerinde seçilen göstergeler tarafından tanımlanır. Bu seçenek için yakalamalar **, Uyarılar** veya **Vakalar** panosundaki **Adli kanıt (önizleme)** sekmesinde gözden geçirilebilir.
    - **Tüm etkinlikler**: Bu seçenek, kullanıcılar tarafından gerçekleştirilen tüm etkinlikleri yakalar. Buna fare hareketi, tuş vuruşları ve insider risk göstergeleri tarafından tanımlanan tüm etkinlikler dahildir. Bu seçenek için yakalamalar **, Kullanıcı etkinlik raporları** **(önizleme) panosundaki Adli kanıt (önizleme)** sekmesinde gözden geçirilebilir.
4. **İleri**'yi seçin.
5. **Ad ve açıklama** sayfasında aşağıdaki alanları doldurun:
    - **Ad (gerekli):** Adli kanıt ilkesi için kolay bir ad girin. İlke oluşturulduktan sonra bu ad değiştirilemez.
    - **Açıklama (isteğe bağlı)**: Adli kanıt ilkesi için bir açıklama girin.
6. **İleri**'yi seçin.
7. 3. Adım'da **Tüm Etkinlikler** seçeneğini belirlediyseniz **, Cihaz etkinlikleri** sayfası ilke sihirbazındaki son adımı size yönlendirir. **Tüm etkinlikler** seçeneği belirlendiğinde yapılandırılan hiçbir cihaz etkinliği yoktur.

    3. Adımda **Belirli etkinlikler** seçeneğini belirlediyseniz, **Cihaz** etkinlikleri sayfasında yakalanacak cihaz etkinliklerini seçersiniz. İlke tarafından yalnızca seçilen etkinlikler yakalanır. Göstergeler seçilemiyorsa, adli kanıt ilkesinde bu göstergeleri seçebilmeniz için önce kuruluşunuz için bu göstergeleri açmanız gerekir. 

    Göstergeleri seçtikten sonra **İleri'yi** seçin.
8. **Son** sayfasında, ilke için seçtiğiniz ayarları ve seçimleriniz için önerileri veya uyarıları gözden geçirin. İlke değerlerinden herhangi birini değiştirmek için **Düzenle'yi** veya ilkeyi oluşturup etkinleştirmek için **Gönder'i** seçin.

İlke yapılandırma adımlarını tamamladıktan sonra 5. Adıma geçin.

### <a name="step-5-define-and-approve-users-for-capturing"></a>5. Adım: Kullanıcıları yakalama için tanımlama ve onaylama

Güvenlikle ilgili kullanıcı etkinliklerinin yakalanabilmesi için önce yöneticilerin adli kanıtta çift yetkilendirme işlemini izlemesi gerekir. Bu işlem, belirli kullanıcılar için görsel yakalamayı etkinleştirmenin kuruluşunuzdaki ilgili kişiler tarafından tanımlanmasını ve onaylanmasını zorunlu kılmaktadır.

>[!IMPORTANT]
>Önizleme sürümü için en fazla 5 eşzamanlı kullanıcı adli kanıt yakalamaya uygundur. Gruplar için yakalama, önizleme sürümünde desteklenmez.

Belirli kullanıcılar için adli kanıt yakalamanın etkinleştirilmesini istemeniz gerekir. İstek gönderildiğinde, kuruluşunuzdaki onaylayanlara e-postayla bildirim gönderilir ve isteği onaylayabilir veya reddedebilir. Onaylanırsa, kullanıcı **Onaylı kullanıcılar** sekmesinde görünür ve yakalama için uygun olur.

- Kullanıcılar için adli kanıt yakalama onayı istemek için [bu yapılandırma adımlarını](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage#request-capturing-approvals) tamamlayın.
- Kullanıcılar için adli kanıt yakalama isteklerini onaylamak (veya reddetmek) için [bu yapılandırma adımlarını](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage#approve-capturing-requests) tamamlayın.

## <a name="next-steps"></a>Sonraki adımlar

Adli kanıt ilkenizi yapılandırdıktan sonra, ilk uygun klip yakalamalarının diğer ilkelere yönelik uyarılarda veya **Kullanıcı Etkinlik Raporları'ndaki** etkinlik olarak gözden geçirilebileceği 48 saat kadar sürebilir. Adli kanıtları yönetme ve klip yakalamalarını gözden geçirme hakkında daha fazla bilgi için [Bilgi risk yönetimi adli kanıtını yönetme](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage) makalesine bakın.
