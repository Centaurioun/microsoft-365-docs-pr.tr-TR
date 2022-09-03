---
title: Office 365 için Defender için Güvenlik İşlemleri Kılavuzu
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: SecOps personelinin Office 365 için Microsoft Defender yönetmesi için açıklayıcı bir playbook.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 2c22dd6e0d6fef3607bc51325d66691e2b9fc979
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67595773"
---
# <a name="microsoft-defender-for-office-365-security-operations-guide"></a>Office 365 için Microsoft Defender Güvenlik İşlemleri Kılavuzu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bu makalede, kuruluşunuzda Office 365 için Microsoft Defender başarıyla çalıştırma gereksinimleri ve görevlerine genel bir bakış sunun. Bu görevler, güvenlik operasyonları merkezinizin (SOC) e-posta ve işbirliğiyle ilgili güvenlik tehditlerini korumak, algılamak ve yanıtlamak için yüksek kaliteli, güvenilir bir yaklaşım sağlamasına yardımcı olur.

Bu kılavuzun geri kalanında SecOps personeli için gerekli etkinlikler açıklanmaktadır. Etkinlikler günlük, haftalık, aylık ve geçici olarak açıklayıcı görevler halinde gruplandırılır.

Bu kılavuzun yardımcı makalesi, [Microsoft 365 Defender portalının Olaylar sayfasındaki Office 365 için Defender olayları ve uyarıları yönetmeye](mdo-sec-ops-manage-incidents-and-alerts.md) yönelik bir genel bakış sağlar.

[Microsoft 365 Defender Güvenlik İşlemleri Kılavuzu](/microsoft-365/security/defender/integrate-microsoft-365-defender-secops), planlama ve geliştirme için kullanabileceğiniz ek bilgiler içerir.

Bu bilgiler hakkında bir video için bkz <https://youtu.be/eQanpq9N1Ps>. .

## <a name="daily-activities"></a>Günlük etkinlikler

### <a name="monitor-the-microsoft-365-defender-incidents-queue"></a>Microsoft 365 Defender Olayları kuyruğunun izlenmesi

konumundaki Microsoft 365 Defender portalındaki <https://security.microsoft.com/incidents-queue> **Olaylar** sayfası (_Olaylar kuyruğu_ olarak da bilinir), Office 365 için Defender'da aşağıdaki kaynaklardan olayları yönetmenize ve izlemenize olanak tanır:

- [Uyarılar'a bakın](../../compliance/alert-policies.md#default-alert-policies).
- [Otomatik araştırma ve yanıt (AIR)](automated-investigation-response-office.md).

Olaylar kuyruğu hakkında daha fazla bilgi için bkz. [Microsoft 365 Defender olayları önceliklendirme](../defender/incident-queue.md).

Olaylar kuyruğunun izlenmesine yönelik önceliklendirme planınız, olaylar için aşağıdaki öncelik sırasını kullanmalıdır:

1. **Kötü amaçlı olabilecek bir URL tıklaması algılandı**.
2. **Kullanıcının e-posta göndermesi kısıtlandı**.
3. **Şüpheli e-posta gönderme desenleri algılandı**.
4. **Email kullanıcı tarafından kötü amaçlı yazılım veya kimlik avı olarak rapor edildi** ve **Birden çok kullanıcı e-postayı kötü amaçlı yazılım veya kimlik avı olarak bildirdi**.
5. **teslimden sonra kaldırılan kötü amaçlı dosya içeren iletileri Email**, **teslim sonrasında kaldırılan kötü amaçlı URL içeren iletileri Email** ve **teslim sonrasında kaldırılan bir kampanyadan gelen iletileri Email**.
6. **ETR geçersiz kılma nedeniyle kimlik avı teslim edildi**, **Kullanıcının Gereksiz Posta klasörü devre dışı bırakıldığından kimlik avı teslim edildi** ve **Kimlik avı ip izin ilkesi nedeniyle teslim edildi**
7. **ZAP devre dışı bırakıldığından kötü amaçlı yazılım sınırlanamadı ve ZAP devre dışı** **olduğundan Kimlik avına izin verilmedi**.

Olay kuyruğu yönetimi ve sorumlu kişilikler aşağıdaki tabloda açıklanmıştır:

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|konumundaki Olaylar kuyruğundaki <https://security.microsoft.com/incidents-queue>olayları önceliklendirme.|Günlük|Office 365 için Defender tüm **Orta** ve **Yüksek** önem dereceli olayların önceliklendirildiğini doğrulayın.|Güvenlik operasyonları ekibi|
|Olaylar üzerinde Yanıt eylemlerini araştırın ve gerçekleştirin.|Günlük|Tüm olayları araştırın ve önerilen veya el ile yanıt eylemlerini etkin bir şekilde gerçekleştirin.|Güvenlik operasyonları ekibi|
|Olayları çözün.|Günlük|Olay düzeltildiyse, olayı çözün. Olayı çözümlemek, bağlantılı ve ilgili tüm etkin uyarıları çözer.|Güvenlik operasyonları ekibi|
|Olayları sınıflandırma.|Günlük|Olayları doğru veya yanlış olarak sınıflandırabilirsiniz. Gerçek uyarılar için tehdit türünü belirtin. Bu sınıflandırma, güvenlik ekibinizin tehdit desenlerini görmesine ve kuruluşunuzu onlardan korumasına yardımcı olur.|Güvenlik operasyonları ekibi|

### <a name="manage-false-positive-and-false-negative-detections"></a>Hatalı pozitif ve hatalı negatif algılamaları yönetme

Office 365 için Defender'da, aşağıdaki konumlarda hatalı pozitif sonuçları (kötü olarak işaretlenmiş iyi postalar) ve hatalı negatifleri (hatalı postaya izin verilir) yönetirsiniz:

- [Gönderimler portalı (yönetici gönderimleri)](admin-submission.md).
- [Kiracı İzin Ver/Engelle Listesi](manage-tenant-allow-block-list.md)
- [Tehdit Gezgini](threat-explorer.md)

Daha fazla bilgi için, bu makalenin devamında [yer alan Hatalı pozitif ve hatalı negatif algılamaları yönetme](#manage-false-positive-and-false-negative-detections) bölümüne bakın.

Hatalı pozitif ve hatalı negatif yönetim ve sorumlu kişilikler aşağıdaki tabloda açıklanmıştır:

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|Microsoft'a <https://security.microsoft.com/reportsubmission>adresinden hatalı pozitif ve hatalı negatifler gönderin.|Günlük|Yanlış e-posta, URL ve dosya algılamaları bildirerek Microsoft'a sinyaller sağlayın.|Güvenlik operasyonları ekibi|
|Yönetici gönderimi ayrıntılarını analiz edin.|Günlük|Microsoft'a yaptığınız gönderimler için aşağıdaki faktörleri anlayın: <ul><li>Hatalı pozitif veya yanlış negatife neden olan şey.</li><li>gönderim sırasındaki Office 365 için Defender yapılandırmanızın durumu.</li><li>Office 365 için Defender yapılandırmanızda değişiklik yapmanız gerekip gerekmediği.</li></ul>|Güvenlik operasyonları ekibi <br/><br/> Güvenlik Yönetimi|
|konumundaki Kiracı İzin Ver/Engelle Listesine <https://security.microsoft.com/tenantAllowBlockList>blok girdileri ekleyin.|Günlük|Gerektiğinde hatalı negatif URL, dosya veya gönderen algılamaları için blok girdileri eklemek için Kiracı İzin Ver/Engelle Listesi'ni kullanın.|Güvenlik operasyonları ekibi|
|Karantinadan hatalı negatifleri serbest bırakın.|Günlük|Alıcı iletinin yanlış karantinaya alındığını onayladıktan sonra, kullanıcılar için yayın isteklerini serbest bırakabilir veya onaylayabilirsiniz. <br/><br/> Kullanıcıların kendi karantinaya alınan iletilerine (yayın veya istek yayını dahil) neler yapabileceğini denetlemek için bkz. [Karantina ilkeleri](quarantine-policies.md).|Güvenlik operasyonları ekibi <br/><br/> Mesajlaşma Ekibi|

### <a name="review-phishing-and-malware-campaigns-that-resulted-in-delivered-mail"></a>Teslim edilen postayla sonuçlanan kimlik avı ve kötü amaçlı yazılım kampanyalarını gözden geçirin

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|E-posta kampanyalarını gözden geçirin.|Günlük|adresinde kuruluşunuzu <https://security.microsoft.com/campaigns>hedefleyen [e-posta kampanyalarını gözden geçirin](campaigns.md). İletilerin alıcılara teslimine neden olan kampanyalara odaklanın. <br/><br/> Kullanıcı posta kutularında bulunan kampanyalardan iletileri kaldırın. Bu eylem yalnızca bir kampanya olaylardan, [sıfır saatlik otomatik temizlemeden (ZAP)](zero-hour-auto-purge.md) veya el ile düzeltme eylemleriyle düzeltilmemiş e-posta içerdiğinde gereklidir.|Güvenlik operasyonları ekibi|

## <a name="weekly-activities"></a>Haftalık etkinlikler

### <a name="review-email-detection-trends-in-defender-for-office-365-reports"></a>Office 365 için Defender raporlarda e-posta algılama eğilimlerini gözden geçirme

Office 365 için Defender'da, kuruluşunuzdaki e-posta algılama eğilimlerini gözden geçirmek için aşağıdaki raporları kullanabilirsiniz:

- [Posta Akışı durum raporu](view-mail-flow-reports.md#mailflow-status-report)
- [Tehdit Koruması durum raporu](view-email-security-reports.md#threat-protection-status-report)

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|E-posta algılama raporlarını şu adreste gözden geçirin: <ul><li><https://security.microsoft.com/reports/TPSAggregateReportATP></li><li><https://security.microsoft.com/mailflowStatusReport?viewid=type></li></ul>|Hafta -lık|İyi e-postayla karşılaştırıldığında kötü amaçlı yazılım, kimlik avı ve istenmeyen posta için e-posta algılama eğilimlerini gözden geçirin. Zaman içindeki gözlem, tehdit desenlerini görmenizi ve Office 365 için Defender ilkelerinizi ayarlamanız gerekip gerekmediğini belirlemenizi sağlar.|Güvenlik Yönetimi <br/><br/> Güvenlik operasyonları ekibi|

### <a name="track-and-respond-to-emerging-threats-using-threat-analytics"></a>Tehdit analizini kullanarak yeni ortaya çıkan tehditleri izleme ve yanıtlama

Etkin ve popüler tehditleri gözden geçirmek için [Tehdit analizini](/microsoft-365/security/defender-endpoint/threat-analytics) kullanın.

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|Tehdit analizindeki tehditleri adresinden <https://security.microsoft.com/threatanalytics3>gözden geçirin.|Hafta -lık|Tehdit analizi, aşağıdaki öğeler de dahil olmak üzere ayrıntılı analiz sağlar: <ul><li>GÇ'ler.</li><li>Etkin tehdit aktörleri ve kampanyaları hakkında avcılık sorguları.</li><li>Popüler ve yeni saldırı teknikleri.</li><li>Kritik güvenlik açıkları.</li><li>Yaygın saldırı yüzeyleri.</li><li>Yaygın kötü amaçlı yazılım.</li></ul>|Güvenlik operasyonları ekibi <br/><br/> Tehdit avcılığı ekibi|

### <a name="review-top-targeted-users-for-malware-and-phishing"></a>Kötü amaçlı yazılım ve kimlik avı için en çok hedeflenen kullanıcıları gözden geçirin

Tehdit Gezgini'nde **[En çok hedeflenen kullanıcılar](threat-explorer.md#top-targeted-users)** sekmesini kullanarak kötü amaçlı yazılım ve kimlik avı e-postası için en çok hedef olan kullanıcıları bulun veya onaylayın.

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|konumundaki Tehdit Gezgini'nde <https://security.microsoft.com/threatexplorer>**En çok hedeflenen kullanıcılar** sekmesini gözden geçirin.|Hafta -lık|Bu kullanıcılar için ilkeleri veya korumaları ayarlamanız gerekip gerekmediğini belirlemek için bu bilgileri kullanın. Aşağıdaki avantajları elde etmek için etkilenen kullanıcıları [Öncelik hesaplarına](/microsoft-365/admin/setup/priority-accounts) ekleyin: <ul><li>Olaylar bunları etkilediğinde ek görünürlük.</li><li>Yönetici posta akışı desenleri (öncelik hesabı koruması) için uyarlanmış buluşsal yöntemler.</li><li>[Öncelik hesapları raporu için Email sorunları](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</li></ul>|Güvenlik Yönetimi <br/><br/> Güvenlik operasyonları ekibi|

### <a name="review-top-malware-and-phishing-campaigns-that-target-your-organization"></a>Kuruluşunuzu hedefleyen en önemli kötü amaçlı yazılım ve kimlik avı kampanyalarını gözden geçirin

Kampanya Görünümleri, kuruluşunuza yönelik kötü amaçlı yazılım ve kimlik avı saldırılarını gösterir. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de Kampanya Görünümleri](campaigns.md).

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|Sizi etkileyen kötü amaçlı yazılımları ve kimlik avı saldırılarını gözden geçirmek için **adresinden Kampanya Görünümleri'ni** <https://security.microsoft.com/campaigns> kullanın.|Hafta -lık|Saldırılar ve teknikler ve Office 365 için Defender neleri tanımlayıp engelleyebileceği hakkında bilgi edinin. <br/><br/> Kampanya hakkında ayrıntılı bilgi için Kampanya Görünümleri'nde **Tehdit raporunu indir'i** kullanın.|Güvenlik operasyonları ekibi|

## <a name="ad-hoc-activities"></a>Geçici etkinlikler

### <a name="manual-investigation-and-removal-of-email"></a>E-postayı el ile araştırma ve kaldırma

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|Tehdit Gezgini'nde <https://security.microsoft.com/threatexplorer> kullanıcı isteklerine göre hatalı e-postayı araştırın ve kaldırın.|Geçici|Son 30 günün herhangi bir e-postasında otomatik araştırma ve yanıt playbook'u başlatmak için Tehdit Gezgini'ndeki **Araştırmayı tetikle** eylemini kullanın. Araştırmayı el ile tetikleme, aşağıdakiler dahil olmak üzere zaman ve çabadan tasarruf etmenizi sağlar: <ul><li>Kök araştırma.</li><li>Tehditleri tanımlama ve ilişkilendirme adımları.</li><li>Bu tehditleri azaltmak için önerilen eylemler.</li></ul> <br/> Daha fazla bilgi için bkz [. Örnek: Kullanıcı tarafından bildirilen bir kimlik avı iletisi araştırma playbook'u başlatır](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) <br/><br/> İsterseniz Tehdit Gezgini'ni kullanarak güçlü arama ve filtreleme özelliklerine sahip [e-postaları el ile araştırabilir](investigate-malicious-email-that-was-delivered.md) ve doğrudan aynı yerden [el ile yanıt eylemi gerçekleştirebilirsiniz](remediate-malicious-email-delivered-office-365.md) . Kullanılabilir el ile gerçekleştirilen eylemler: <ul><li>Gelen Kutusuna Taşı</li><li>Gereksiz Öğeye Taşı</li><li>Silinmiş öğelere gitme</li><li>Geçici silme</li><li>Sabit silme.</li></ul>|Güvenlik operasyonları ekibi|

### <a name="proactively-hunt-for-threats"></a>Tehditleri proaktif olarak avlama

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|Tehditler için düzenli ve proaktif avcılık: <ul><li><https://security.microsoft.com/threatexplorer></li><li><https://security.microsoft.com/v2/advanced-hunting></li></ul>.|Geçici|[Tehdit Gezgini](threat-explorer.md) ve [Gelişmiş tehdit avcılığı](../defender-endpoint/advanced-hunting-overview.md) kullanarak tehditleri arayın.|Güvenlik operasyonları ekibi <br/><br/> Tehdit avcılığı ekibi|
|Avlanma sorgularını paylaşın.|Geçici|Daha hızlı el ile tehdit avcılığı ve düzeltme için güvenlik ekibi içinde sık kullanılan ve yararlı sorguları etkin bir şekilde paylaşın. <br/><br/> [Gelişmiş tehdit avcılığında](/microsoft-365/security/defender/advanced-hunting-shared-queries) [Tehdit izleyicilerini](threat-trackers.md) ve paylaşılan sorguları kullanın.|Güvenlik operasyonları ekibi <br/><br/> Tehdit avcılığı ekibi|
|konumunda <https://security.microsoft.com/custom_detection>özel algılama kuralları oluşturun.|Geçici|Gelişmiş Tehdit Avcılığı'nda Office 365 için Defender verilerine dayalı olayları, desenleri ve tehditleri proaktif olarak izlemek için [özel algılama kuralları oluşturun](../defender/custom-detections-overview.md). Algılama kuralları, eşleşen ölçütlere göre uyarılar oluşturan gelişmiş tehdit avcılığı sorguları içerir.|Güvenlik operasyonları ekibi <br/><br/> Tehdit avcılığı ekibi|

### <a name="review-defender-for-office-365-policy-configurations"></a>Office 365 için Defender ilkesi yapılandırmalarını gözden geçirin

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|konumundaki <https://security.microsoft.com/configurationAnalyzer>Office 365 için Defender ilkelerinin yapılandırmasını gözden geçirin.|Geçici <br/><br/> Aylık|Mevcut ilke ayarlarınızı [Office 365 için Defender için önerilen Standart veya Katı değerlerle](recommended-settings-for-eop-and-office365.md) karşılaştırmak için [Yapılandırma çözümleyicisini](configuration-analyzer-for-security-policies.md) kullanın. Yapılandırma çözümleyicisi, kuruluşunuzun güvenlik duruşunu düşürebilecek yanlışlıkla veya kötü amaçlı değişiklikleri tanımlar. <br/><br/> Ya da yu, PowerShell tabanlı [ORCA aracını](https://aka.ms/getorca) kullanabilir.|Güvenlik Yönetimi <br/><br/> Mesajlaşma Ekibi|
|Office 365 için Defender'de algılama geçersiz kılmalarını gözden geçirin:<https://security.microsoft.com/reports/TPSMessageOverrideReportATP>|Geçici <br/><br/> Aylık|**Tehdit Koruması durum raporunda**, kimlik avı olarak algılanan ancak ilke veya kullanıcı geçersiz kılma ayarları nedeniyle teslim edilen e-postayı gözden geçirmek için [Verileri Sisteme göre görüntüle geçersiz kılma \> Grafiği dökümünü](view-email-security-reports.md#view-data-by-system-override-and-chart-breakdown-by-reason) kullanın. <br/><br/> Kötü amaçlı olduğu belirlenen e-postaların teslimini önlemek için geçersiz kılmaları etkin bir şekilde araştırın, kaldırın veya hassas ayar yapın.|Güvenlik Yönetimi <br/><br/> Mesajlaşma Ekibi|

### <a name="review-spoof-and-impersonation-detections"></a>Kimlik sahtekarlığı ve kimliğe bürünme algılamalarını gözden geçirme

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|**Spoof intelligence içgörülerini** ve **Kimliğe Bürünme algılama içgörülerini** gözden geçirin: <ul><li><<https://security.microsoft.com/spoofintelligence>></li><li><https://security.microsoft.com/impersonationinsight></li></ul>.|Geçici <br/><br/> Aylık|Kimlik sahtekarlığı ve kimliğe bürünme algılamaları için filtrelemeyi ayarlamak için kimlik sahtekarlığı [zekası içgörülerini](learn-about-spoof-intelligence.md) ve kimliğe bürünme [içgörülerini](impersonation-insight.md) kullanın.|Güvenlik Yönetimi <br/><br/> Mesajlaşma Ekibi|

### <a name="review-priority-account-membership"></a>Öncelik hesabı üyeliğini gözden geçirme

|Etkinlik|Cadence|Açıklama|Persona|
|---|---|---|---|
|adresinde kimlerin öncelik hesabı <https://security.microsoft.com/securitysettings/userTags>olarak tanımlandığını gözden geçirin.|Geçici|Bu kullanıcılar için aşağıdaki avantajları elde etmek için, kurumsal değişikliklerle [öncelik hesaplarının](/microsoft-365/admin/setup/priority-accounts) üyeliğini güncel tutun: <ul><li>Raporlarda daha iyi görünürlük.</li><li>Olaylar ve uyarılarda filtreleme.</li><li>Yönetici posta akışı desenleri (öncelik hesabı koruması) için uyarlanmış buluşsal yöntemler.</li></ul> <br/> Aşağıdaki bilgileri almak için diğer kullanıcılar için özel [kullanıcı etiketlerini](user-tags.md) kullanın: <ul><li>Raporlarda daha iyi görünürlük.</li><li>Olaylar ve uyarılarda filtreleme.</li></ul>|Güvenlik operasyonları ekibi|

## <a name="appendix"></a>Ek

### <a name="learn-about-microsoft-defender-for-office-365-tools-and-processes"></a>Office 365 için Microsoft Defender araçları ve süreçleri hakkında bilgi edinin

Güvenlik operasyonları ve yanıt ekibi üyelerinin Office 365 için Defender araçları ve özellikleri mevcut araştırmalarla ve yanıt süreçleriyle tümleştirmesi gerekir. Yeni araçlar ve özellikler hakkında bilgi edinmek zaman alabilir ancak bu, ekleme işleminin kritik bir parçasıdır. SecOps ve e-posta güvenlik ekibi üyelerinin Office 365 için Defender hakkında bilgi edinmelerinin en basit yolu, konumundaki <https://aka.ms/mdoninja>Ninja eğitim içeriğinin bir parçası olarak sağlanan eğitim içeriğini kullanmaktır.

İçerik, düzey başına birden çok modül içeren farklı bilgi düzeyleri (Temel Bilgiler, Ara ve Gelişmiş) için yapılandırılmıştır.

Belirli görevlere yönelik kısa videolar [Office 365 için Microsoft Defender YouTube kanalında](https://www.youtube.com/playlist?list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf) da sağlanır.

### <a name="permissions-for-defender-for-office-365-activities-and-tasks"></a>Office 365 için Defender etkinlikleri ve görevleri için izinler

Microsoft 365 Defender portalında ve PowerShell'de Office 365 için Defender yönetme izinleri rol tabanlı erişim denetimi (RBAC) izin modelini temel alır. RBAC, microsoft 365 hizmetlerinin çoğu tarafından kullanılan izin modeliyle aynıdır. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md).

> [!NOTE]
> Azure AD'da Privileged Identity Management (PIM), SecOps personeline gerekli izinleri atamanın da bir yoludur. Daha fazla bilgi için bkz. [Privileged Identity Management (PIM) ve neden Office 365 için Microsoft Defender ile kullanılacağı](use-privileged-identity-management-in-defender-for-office-365.md).

Aşağıdaki izinler (roller ve rol grupları) Office 365 için Defender kullanılabilir ve güvenlik ekibi üyelerine erişim vermek için kullanılabilir:

- **Azure AD rolleri**: Office 365 için Defender dahil _olmak üzere tüm_ Microsoft 365 hizmetleri için izinler atayan merkezi roller. Microsoft 365 Defender portalında Azure AD rollerini ve atanmış kullanıcıları görüntüleyebilirsiniz, ancak bunları doğrudan orada yönetemezsiniz. Bunun yerine, Azure AD rollerini ve üyelerini adresinde <https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/RolesAndAdministrators>yönetirsiniz. Güvenlik ekipleri tarafından en sık kullanılan roller şunlardır:
  - **Güvenlik yöneticisi**
  - **Güvenlik operatörü**
  - **Güvenlik gözetmeni**

- **Email & işbirliği rolleri**: Office 365 için Microsoft Defender özgü izinler veren roller ve rol grupları. Aşağıdaki roller Azure AD'da kullanılamaz, ancak güvenlik ekipleri için önemli olabilir:

  - **Önizleme** rolü: Araştırma etkinliklerinin bir parçası olarak e-posta iletilerini önizlemesi veya indirmesi gereken ekip üyelerine bu rolü atayın. Kullanıcıların e-posta varlık sayfasını kullanarak bulut posta kutularındaki [e-posta](mdo-email-entity-page.md#email-preview-for-cloud-mailboxes) iletilerini [önizlemesine ve indirmesine](investigate-malicious-email-that-was-delivered.md#preview-role-permissions) olanak tanır.

    Varsayılan olarak, bu rol yalnızca aşağıdaki rol gruplarına atanır:

    - Veri Araştırmacısı
    - eBulma Yöneticisi

    Bu rolü yeni veya mevcut bir rol grubuna atamak için bkz. [Microsoft 365 Defender portalında Email & işbirliği rolü üyeliğini değiştirme](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal).

  - **Arama ve Temizleme** rolü: Kötü amaçlı iletilerin SILINMESIni AIR tarafından önerilen şekilde onaylayın veya Tehdit Gezgini gibi tehdit avcılığı deneyimlerindeki iletiler üzerinde el ile işlem yapın.

    Varsayılan olarak, bu rol yalnızca aşağıdaki rol gruplarına atanır:

    - Veri Araştırmacısı
    - Kuruluş Yönetimi

    Bu rolü yeni veya mevcut bir rol grubuna atamak için bkz. [Microsoft 365 Defender portalında Email & işbirliği rolü üyeliğini değiştirme](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal).

  - **Kiracı AllowBlockList Manager**: [Kiracı İzin Ver/Engelle Listesindeki izin ver ve engelle](manage-tenant-allow-block-list.md) girdilerini yönetin. URL'leri, dosyaları (dosya karması kullanarak) veya gönderenleri engellemek, teslim edilen kötü amaçlı e-postaları araştırırken yapmanız gereken yararlı bir yanıt eylemidir.

    Varsayılan olarak, bu rol yalnızca **Güvenlik İşleci** rol grubuna atanır. Ancak **, Güvenlik Yöneticileri** ve **Kuruluş yönetim** rol gruplarının üyeleri de Kiracı İzin Ver/Engelle Listesi'ndeki girdileri yönetebilir.

### <a name="siemsoar-integration"></a>SIEM/SOAR tümleştirmesi

Office 365 için Defender, verilerinin çoğunu bir dizi programlı API aracılığıyla kullanıma sunar. Bu API'ler iş akışlarını otomatikleştirmenize ve Office 365 için Defender özelliklerinden tam olarak yararlanmanıza yardımcı olur. Veriler [Microsoft 365 Defender API'leri](/microsoft-365/security/defender/api-overview) aracılığıyla sağlanır ve Office 365 için Defender mevcut SIEM/SOAR çözümleriyle tümleştirmek için kullanılabilir.

- [Olay API'si](/microsoft-365/security/defender/api-incident): Office 365 için Defender uyarıları ve otomatik araştırma, Microsoft 365 Defender'daki olayların etkin parçalarıdır. Güvenlik ekipleri, tam saldırı kapsamını ve etkilenen tüm varlıkları birlikte gruplandırarak kritik öneme odaklanabilir.

- [Olay akışı API'si](/microsoft-365/security/defender/streaming-api): Gerçek zamanlı olayların ve uyarıların gerçekleştiği anda tek bir veri akışına gönderilmesine izin verir. Desteklenen Office 365 için Defender olay türleri şunlardır:
  - [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table)
  - [EmailUrlInfo](/microsoft-365/security/defender/advanced-hunting-emailurlinfo-table)
  - [EmailAttachmentInfo](/microsoft-365/security/defender/advanced-hunting-emailattachmentinfo-table)
  - [EmailPostDeliveryEvents](/microsoft-365/security/defender/advanced-hunting-emailpostdeliveryevents-table)

  Olaylar, son 30 gün içindeki tüm e-postaların (kuruluş içi iletiler dahil) işlenmesinden alınan verileri içerir.

- [Gelişmiş Tehdit Avcılığı API'si](/microsoft-365/security/defender/api-advanced-hunting): Ürün arası tehdit avcılığı sağlar.

- [Tehdit Değerlendirmesi API'si](/graph/api/resources/threatassessment-api-overview): İstenmeyen posta, kimlik avı URL'leri veya kötü amaçlı yazılım eklerini doğrudan Microsoft'a bildirmek için kullanılabilir.

Office 365 için Defender olayları ve ham verileri Microsoft Sentinel ile bağlamak için [Microsoft 365 Defender (M365D) bağlayıcısını](/azure/sentinel/connect-microsoft-365-defender?tabs=MDO) kullanabilirsiniz

Microsoft Defender API'lerine API erişimini test etmek için bu basit "Merhaba Dünya" örneğini kullanabilirsiniz: [Microsoft 365 Defender REST API için Merhaba Dünya](/microsoft-365/security/defender/api-hello-world).

SIEM aracı tümleştirmesi hakkında daha fazla bilgi için bkz. [SIEM araçlarınızı Microsoft 365 Defender ile tümleştirme](/microsoft-365/security/defender/configure-siem-defender).

## <a name="address-false-positives-and-false-negatives-in-defender-for-office-365"></a>Office 365 için Defender hatalı pozitif sonuçları ve hatalı negatifleri ele alın

Kullanıcı gönderimi ve e-posta iletilerinin yönetici gönderimleri, makine öğrenmesi algılama sistemlerimiz için kritik pozitif pekiştirici sinyallerdir. Gönderiler saldırıları gözden geçirmemize, önceliklendirmemize, hızla öğrenmemize ve azaltmamıza yardımcı olur. Hatalı pozitif sonuçları ve hatalı negatifleri etkin bir şekilde raporlamak, algılama sırasında hatalar yapıldığında Office 365 için Defender geri bildirim sağlayan önemli bir etkinliktir.

Kuruluşların kullanıcı gönderimlerini yapılandırmak için birden çok seçeneği vardır. Yapılandırmaya bağlı olarak, kullanıcılar Microsoft'a hatalı pozitif veya hatalı negatifler gönderdiğinde güvenlik ekipleri daha etkin katılıma sahip olabilir:

- Kullanıcı [bildirilen ileti ayarları aşağıdaki ayarlardan](user-submission.md) biriyle yapılandırıldığında, kullanıcı gönderimleri analiz için Microsoft'a gönderilir:
  - Bildirilen iletileri Şu adresine gönderin: Microsoft.
  - Bildirilen iletileri şu adresine gönderin: Microsoft ve kuruluşumun posta kutusu.

  Kullanıcılar tarafından bildirilmeyen hatalı pozitifler veya hatalı negatifler operasyon ekipleri tarafından keşfedildiğinde güvenlik ekipleri üyeleri eklenti [yönetici gönderimleri](admin-submission.md) yapmalıdır.

- Kullanıcı tarafından bildirilen iletiler yalnızca kuruluşun posta kutusuna ileti gönderecek şekilde yapılandırıldığında, güvenlik ekipleri yönetici gönderimleri aracılığıyla kullanıcı tarafından bildirilen hatalı pozitif ve hatalı negatifleri etkin bir şekilde Microsoft'a göndermelidir.

Bir kullanıcı bir iletiyi kimlik avı olarak bildirdiği zaman, Office 365 için Defender bir uyarı oluşturur ve uyarı bir AIR playbook'unu tetikler. Olay mantığı, mümkün olduğunda bu bilgileri diğer uyarılarla ve olaylarla ilişkilendirecektir. Bilgilerin bu birleştirilmesi, güvenlik ekiplerinin kullanıcı tarafından bildirilen e-postayı önceliklendirmesine, araştırmasına ve yanıtlamasına yardımcı olur.

Kullanıcı gönderimleri ve yönetici gönderimleri, sıkı bir şekilde tümleşik bir süreci izleyen Microsoft tarafından gönderim işlem hattı tarafından işlenir. Bu işlem şunları içerir:

- Gürültü azaltma.
- Otomatik önceliklendirme.
- Güvenlik analistleri ve insan iş ortağı makine öğrenmesi tabanlı çözümler tarafından puanlama.

Daha fazla bilgi için bkz[. Office 365 için Defender - Microsoft Tech Community'de e-posta](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/reporting-an-email-in-microsoft-defender-for-office-365/ba-p/2870231) raporlama.

Güvenlik ekibi üyeleri, Microsoft 365 Defender portalında <https://security.microsoft.com>birden çok konumdan gönderim yapabilir:

- [Yönetici gönderimi](admin-submission.md): Şüpheli istenmeyen postaları, kimlik avı, URL'leri ve dosyaları Microsoft'a göndermek için Gönderimler portalını kullanın.
- Aşağıdaki ileti eylemlerinden birini kullanarak doğrudan Tehdit Gezgini'nden:
  - Rapor temizleme
  - Kimlik avı bildirme
  - Kötü amaçlı yazılımları bildirme
  - İstenmeyen posta bildirme

  Toplu gönderim gerçekleştirmek için en fazla 10 ileti seçebilirsiniz. Bu şekilde oluşturulan Yönetici gönderimler Gönderim portalında da görülebilir.

Hatalı negatiflerin kısa vadede azaltılması için, güvenlik ekipleri [Kiracı İzin Ver/Engelle Listesi'nde](manage-tenant-allow-block-list.md) dosyalar, URL'ler ve etki alanları veya e-posta adresleri için blok girişlerini doğrudan yönetebilir.

Hatalı pozitif sonuçların kısa vadeli risk azaltması için, güvenlik ekipleri Kiracı İzin Ver/Engelle Listesi'nde etki alanları ve e-posta adresleri için izin verme girdilerini doğrudan yönetemez. Bunun yerine, e-posta iletisini hatalı pozitif olarak raporlamak için [yönetici gönderimlerini kullanmaları](admin-submission.md) gerekir. Yönergeler için bkz. [Gönderimler portalında etki alanları ve e-posta adresleri için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanma](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal).

[Office 365 için Defender'de karantinaya almak](manage-quarantined-messages-and-files.md) tehlikeli veya istenmeyen iletileri ve dosyaları barındırıyor. Güvenlik ekipleri tüm kullanıcılar için tüm karantinaya alınmış iletileri görüntüleyebilir, yayımlayabilir ve silebilir. Bu özellik, hatalı pozitif bir ileti veya dosya karantinaya alındığında güvenlik ekiplerinin etkili bir şekilde yanıt vermesini sağlar.

## <a name="integrate-third-party-reporting-tools-with-defender-for-office-365-user-submission"></a>Üçüncü taraf raporlama araçlarını Office 365 için Defender kullanıcı gönderimiyle tümleştirme

Kuruluşunuzda kullanıcıların şüpheli e-postaları dahili olarak bildirmesine olanak tanıyan bir üçüncü taraf raporlama aracı kullanılıyorsa, aracı Office 365 için Defender kullanıcı gönderimi özellikleriyle tümleştirebilirsiniz. Bu tümleştirme, güvenlik ekiplerine aşağıdaki avantajları sağlar:

- Office 365 için Defender AIR özellikleriyle tümleştirme.
- Basitleştirilmiş önceliklendirme.
- Araştırma ve yanıt süresi azaltıldı.

Kullanıcı tarafından bildirilen iletilerin Microsoft 365 Defender portalındaki **Kullanıcı gönderimleri** sayfasında gönderildiği özel posta kutusunu belirleyin<https://security.microsoft.com/userSubmissionsReportMessage>. Daha fazla bilgi için bkz. [Kullanıcı tarafından bildirilen ileti ayarları](user-submission.md).

> [!NOTE]
>
> - Özel posta kutusu bir Exchange Online posta kutusudur.
> - Üçüncü taraf raporlama aracı, bildirilen özgün iletiyi sıkıştırılmamış olarak içermelidir. EML veya . Özel posta kutusuna gönderilen iletideki MSG eki (özgün iletiyi özel posta kutusuna iletmeyin).
> - Özel posta kutusu, olası hatalı iletilerin teslim edilmesine izin vermek için belirli önkoşullar gerektirir. Daha fazla bilgi için bkz [. Kullanıcı gönderimleri posta kutusu için yapılandırma gereksinimleri](user-submission.md#configuration-requirements-for-the-user-submissions-mailbox).

Kullanıcı tarafından bildirilen e-posta özel posta kutusuna ulaştığında, Office 365 için Defender kullanıcı **tarafından kötü amaçlı yazılım veya kimlik avı olarak bildirilen Email** adlı uyarıyı otomatik olarak oluşturur. Bu uyarı bir [AIR playbook'u](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook) başlatır. Playbook, bir dizi otomatik araştırma adımı gerçekleştirir:

- Belirtilen e-posta hakkında veri toplayın.
- Bu e-postayla ilgili tehditler ve varlıklar hakkında veri toplayın. Varlıklar dosyalar, URL'ler ve alıcılar içerebilir.
- Araştırma bulgularına göre SecOps ekibinin gerçekleştirmesi önerilen eylemleri sağlayın.

**Kullanıcı tarafından kötü amaçlı yazılım veya kimlik avı uyarıları olarak bildirilen Email**, otomatik araştırma ve önerilen eylemleri otomatik olarak Microsoft 365 Defender olaylarla ilişkilendirilir. Bu bağıntı, güvenlik ekipleri için önceliklendirme ve yanıt sürecini daha da basitleştirir. Birden çok kullanıcı aynı veya benzer iletileri bildirirse, tüm kullanıcılar ve iletiler aynı olayla ilişkilendirilir.

Office 365 için Defender'daki uyarılardan ve araştırmalardan alınan veriler, diğer Microsoft 365 Defender ürünlerindeki uyarı ve araştırmalarla otomatik olarak karşılaştırılır:

- Uç Nokta için Microsoft Defender
- Bulut Uygulamaları için Microsoft Defender
- Kimlik için Microsoft Defender

Bir ilişki bulunursa sistem, saldırının tamamı için görünürlük sağlayan bir olay oluşturur.
