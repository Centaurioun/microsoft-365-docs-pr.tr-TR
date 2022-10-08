---
title: Microsoft 365 Defender portalı
description: Microsoft 365 Defender portalı e-posta, işbirliği, kimlik, cihaz ve uygulama tehditlerine karşı koruma, algılama, araştırma ve yanıtı merkezi bir yerde birleştirir.
keywords: MMicrosoft 365 Defender'a giriş, siber güvenlik, gelişmiş kalıcı tehdit, kurumsal güvenlik, cihazlar, cihaz, kimlik, kullanıcılar, veriler, uygulamalar, olaylar, otomatik araştırma ve düzeltme, gelişmiş avcılık
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
adobe-target: true
ms.openlocfilehash: bc690e91ceb83d49814e869f40411da900faa719
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051266"
---
# <a name="microsoft-365-defender-portal"></a>Microsoft 365 Defender portalı

[Microsoft 365 Defender portalı](https://sip.security.microsoft.com/homepage), e-posta, işbirliği, kimlik, cihaz ve bulut uygulaması tehditlerine karşı koruma, algılama, araştırma ve yanıtı merkezi bir yerde birleştirir. Microsoft 365 Defender portalı bilgilere hızlı erişimi, daha basit düzenleri vurgular ve daha kolay kullanım için ilgili bilgileri bir araya getirir. İçindekiler:

- **[Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)** Office 365 için Microsoft Defender, kuruluşların e-postayı ve Office 365 kaynaklarını korumak için bir dizi önleme, algılama, araştırma ve avcılık özelliğiyle kuruluşlarının güvenliğini sağlamalarına yardımcı olur.
- **[Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** kuruluşunuzdaki cihazlar için önleyici koruma, ihlal sonrası algılama, otomatik araştırma ve yanıt sunar.
- **[Kimlik için Microsoft Defender](/defender-for-identity/what-is)** gelişmiş tehditleri, güvenliği aşılmış kimlikleri ve kuruluşunuza yönelik kötü amaçlı insider eylemlerini tanımlamak, algılamak ve araştırmak için şirket içi Active Directory sinyallerinizden yararlanan bulut tabanlı bir güvenlik çözümüdür.
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)**, bulut uygulamalarınıza derin görünürlük, güçlü veri denetimleri ve gelişmiş tehdit koruması getiren kapsamlı bir SaaS ve PaaS çözümüdür.

Microsoft 365 Defender portalı hakkında bilgi edinmek için bu kısa videoyu izleyin.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBKau]

## <a name="what-to-expect"></a>Bekleyebileceğiniz şeyler

Microsoft 365 Defender portalı, güvenlik ekiplerinin farklı iş yüklerinden gelen sinyalleri aşağıdakiler için birleştirilmiş deneyim kümesine getirerek saldırıları araştırmalarına ve yanıtlamalarına yardımcı olur:

- Olaylar & uyarıları
- Avcı -lık
- Gönderiler & eylemler
- Tehdit analizi
- Güvenlik puanı
- Öğrenme merkezi
- Deneme

Microsoft 365 Defender *birlik, netlik ve ortak hedefleri* vurgular. 

> [!NOTE]
> Microsoft 365 Defender portalına müşterilerin geçiş adımlarını gerçekleştirmesine veya yeni lisans satın almasına gerek kalmadan erişilebilir. Örneğin, bu yeni portalA3 aboneliğine sahip yöneticiler için de aynı Plan 1 ve Plan 2 Office 365 için Microsoft Defender olanlar için erişilebilir; ancak Exchange Online Protection veya Office 365 için Defender  Plan 1 müşterileri yalnızca abonelik lisanslarının desteklediği güvenlik özelliklerini görür. Portalın amacı güvenliği merkezileştirmektir.

## <a name="incident-and-alert-investigations"></a>Olay ve uyarı araştırmaları

Güvenlik bilgilerinin merkezileştirilmesi, Microsoft 365 genelindeki güvenlik olaylarını araştırmak için tek bir yer oluşturur. Birincil örnek, **Olaylar & uyarıları altındaki Olaylar'dır**.

:::image type="content" source="../../media/converged-incidents-2.png" alt-text="Microsoft 365 Defender portalındaki Olaylar sayfası" lightbox="../../media/converged-incidents-2.png":::

Bir olay adı seçildiğinde, e-postadan kimliğe ve uç noktalara kadar bir tehdidin tamamının genişletilmesiyle ilgili daha iyi içgörülere sahip olduğunuzdan güvenlik bilgilerini merkezileştirmenin değerini gösteren bir sayfa görüntülenir.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender portalındaki bir olayın Özet sayfası" lightbox="../../media/converged-incident-info-3.png":::

Ortamınızdaki olayları gözden geçirmek, her uyarıda detaya gitmek ve bilgilere nasıl erişileceğini anlamak ve analizinizdeki sonraki adımları belirlemek için zaman ayırın.

Daha fazla bilgi için bkz. [Microsoft 365 Defender'deki olaylar](incidents-overview.md).

## <a name="hunting"></a>Avcı -lık
Özel algılama kuralları oluşturabilir ve ortamınızdaki belirli tehditleri avlayabilirsiniz. **Tehdit avcılığı** , tehdit göstergelerini ve varlıkları bulmak için kuruluşunuzdaki olayları proaktif olarak incelemenize olanak tanıyan sorgu tabanlı bir tehdit avcılığı aracı kullanır. Bu kurallar, ihlal olduğundan şüphelenilen etkinliği, yanlış yapılandırılmış makineleri ve diğer bulguları denetlemek ve yanıtlamak için otomatik olarak çalıştırılır.

Daha fazla bilgi için bkz. [Microsoft 365 Defender'da gelişmiş avcılık ile tehditleri proaktif olarak avlama](advanced-hunting-overview.md).

## <a name="improved-processes"></a>Geliştirilmiş işlemler

Ortak denetimler ve içerik aynı yerde görünür veya tek bir veri akışında yoğunlaşarak bulmayı kolaylaştırır. Örneğin, birleşik ayarlar.

### <a name="unified-settings"></a>Birleşik ayarlar

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="Microsoft 365 Defender portalındaki Ayarlar sayfası" lightbox="../../media/converged-add-role-9.png":::

### <a name="permissions--roles"></a>İzinler & rolleri

:::image type="content" source="../../media/converged-roles-5.png" alt-text="İzinler & rolleri sayfasında görüntülenen Uç noktalar rolleri & grupları" lightbox="../../media/converged-roles-5.png":::

Microsoft 365 Defender erişimi, Azure AD genel rollerle veya özel roller kullanılarak yapılandırılır.

- [Microsoft 365 Defender erişimi yönetme](m365d-permissions.md) hakkında daha fazla bilgi edinin
- [Microsoft 365 Defender'de özel roller oluşturma](custom-roles.md) hakkında daha fazla bilgi edinin


### <a name="integrated-reports"></a>Tümleşik raporlar

Raporlar da Microsoft 365 Defender birleştirilir. Yöneticiler genel bir güvenlik raporuyla başlayabilir ve uç noktalar, e-posta & işbirliği hakkında belirli raporlara dallanabilir. Buradaki bağlantılar, iş yükü yapılandırmasına göre dinamik olarak oluşturulur.

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 ortamınızı hızlı bir şekilde görüntüleme

**Giriş** sayfasında güvenlik ekiplerinin ihtiyaç duyduğu birçok ortak kart gösterilir. Kartların ve verilerin bileşimi kullanıcı rolüne bağlıdır. Microsoft 365 Defender portalı rol tabanlı erişim denetimi kullandığından, farklı roller günlük işleri için daha anlamlı olan kartları görür.

Bu bir bakışta bilgiler, kuruluşunuzdaki en son etkinliklere ayak uydurmanıza yardımcı olur. Microsoft 365 Defender, Microsoft 365 ortamınızın bütünsel bir görünümünü sunmak için farklı kaynaklardan gelen sinyalleri bir araya getirir.

İhtiyaçlarınıza bağlı olarak farklı kartlar ekleyebilir ve kaldırabilirsiniz.

### <a name="search-across-entities-preview"></a>Varlıklar arasında arama (Önizleme)

>[!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.
Arama çubuğu sayfanın en üstünde yer alır. Siz yazarken, varlıkları bulmanın daha kolay olması için öneriler sağlanır. Gelişmiş arama sonuçları sayfası, tüm varlıklardaki sonuçları merkezileştirir.

Uç Nokta için Defender ve Kimlik için Defender'da aşağıdaki varlıklar arasında arama yapabilirsiniz: 

- **Cihazlar** - Hem Uç Nokta için Defender hem de Kimlik için Defender için desteklenir. Arama işleçlerinin kullanımını destekler. 
- **Kullanıcılar** - Uç Nokta için Defender, Kimlik için Defender ve Bulut Uygulamaları için Defender için desteklenir. 
- **Dosyalar, IP'ler ve URL'ler** - Uç Nokta için Defender'daki özelliklerle aynıdır.

    >[!NOTE]
    >IP ve URL aramaları tam olarak eşleşir ve arama sonuçları sayfasında görünmez; doğrudan varlık sayfasına yönlendirir. 

- **MDVM** - Uç Nokta için Defender'dakiyle aynı özellikler (güvenlik açıkları, yazılımlar ve öneriler). 

## <a name="threat-analytics"></a>Tehdit analizi

Ortaya çıkan tehditleri aşağıdaki Microsoft 365 Defender tehdit analiziyle izleyin ve yanıt verin: Tehdit analizi, uzman Microsoft güvenlik araştırmacılarının Microsoft 365 Defender tehdit bilgileri çözümüdür. Aşağıdakiler gibi yeni tehditlerle karşı karşıyayken güvenlik ekiplerinin mümkün olduğunca verimli olması için tasarlanmıştır:

- Etkin tehdit aktörleri ve kampanyaları
- Popüler ve yeni saldırı teknikleri
- Kritik güvenlik açıkları
- Yaygın saldırı yüzeyleri
- Yaygın kötü amaçlı yazılım

## <a name="learning-hub"></a>Öğrenme Merkezi

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalı</a>, Microsoft güvenlik blogu, YouTube'da Microsoft güvenlik topluluğu ve resmi belgeler gibi kaynaklardan rehberlik sağlayan bir öğrenme merkezi içerir.

> [!NOTE]
> Microsoft 365 Defender öğrenme hub'ının üst kısmında ürünler (şu anda Microsoft 365 Defender, Uç Nokta için Microsoft Defender ve  Office 365 için Microsoft Defender). Her bölüm için öğrenme kaynaklarının sayısının listelendiğine dikkat edin. Bu, öğrencilerin eğitim ve öğrenme için ellerindeki kaynakların sayısını takip etmelerine yardımcı olabilir.
>
> Ürün filtresiyle birlikte geçerli konular, kaynak türleri (videolardan web seminerlerine), güvenlik alanları, güvenlik rolleri ve ürün özellikleriyle ilgili bilgi ve deneyim düzeyleri listelenir.

> [!TIP]
> [Microsoft Learn'de](/training/) birçok başka öğrenme fırsatı vardır. [Kurs MS-500T02-A: Microsoft 365 Tehdit Koruması Uygulama gibi sertifika eğitimleri](/training/certifications/courses/ms-500t02) bulacaksınız.

## <a name="send-us-your-feedback"></a>Bize geri bildiriminizi gönderin

Geri bildiriminize ihtiyacımız var. Her zaman iyileştirmeye çalışıyoruz. Bu nedenle, görmek istediğiniz bir şey varsa [geri bildirimlerinizi okumamız için bize nasıl güvenebileceğinizi öğrenmek için bu videoyu izleyin](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

## <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>Microsoft 365 Defender portalının neler sundığını keşfedin

Microsoft 365 Defender'daki özellikleri ve özellikleri keşfetmeye devam edin:

- [Olayları ve uyarıları yönetin](manage-incidents.md)
- [Tehdit analizi ile yeni ortaya çıkan tehditleri izleme ve yanıtlama](threat-analytics.md)
- [İşlem merkezi](m365d-action-center.md)
- [Cihazlar, e-postalar, uygulamalar ve kimlikler arasında tehditleri avlama](./advanced-hunting-query-emails-devices.md)
- [Özel algılama kuralları](./custom-detection-rules.md)
- [İşbirliği uyarılarını Email &](../../compliance/alert-policies.md#default-alert-policies)
- [Kimlik avı saldırısı simülasyonu oluşturma](../office-365-security/attack-simulation-training.md) ve [ekiplerinizi eğitme yükü oluşturma](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>Güvenlik analistleri için eğitim

Microsoft Learn'den gelen bu öğrenme yolu ile Microsoft 365 Defender ve güvenlik tehditlerini tanımlamaya, denetlemeye ve düzeltmeye nasıl yardımcı olabileceğini anlayabilirsiniz.

|Eğitim:|Microsoft 365 Defender ile siber saldırıları algılama ve yanıtlama|
|---|---|
|![Microsoft 365 Defender eğitim simgesi.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender gelişmiş siber saldırılara karşı tümleşik koruma sağlamak için uç noktalar, kimlikler, e-postalar ve uygulamalar arasında tehdit sinyallerini birleştirilir. Microsoft 365 Defender, olayları araştırmak ve yanıtlamak ve devam eden kötü amaçlı siber güvenlik etkinliklerini proaktif olarak aramak için merkezi bir deneyimdir.<p> 1 sa 38 dk - Öğrenme Yolu - 5 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/paths/defender-detect-respond/)


## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 Defender'daki yenilikler](whats-new.md)
- [Microsoft 365 Defender'da Office 365 için Microsoft Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender'da Uç Nokta için Microsoft Defender](microsoft-365-security-center-mde.md)
