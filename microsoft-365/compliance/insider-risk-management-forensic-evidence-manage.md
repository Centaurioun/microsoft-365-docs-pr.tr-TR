---
title: Insider risk yönetimi adli kanıtlarını yönetme (önizleme)
description: Microsoft Purview'da insider risk yönetimi adli kanıtlarını yönetin. Adli kanıt, kullanıcının eylemlerinin risk oluşturup oluşturmadığını ve bir güvenlik olayına yol açıp açmadığını saptamaya yardımcı olmak için yakalanan güvenlikle ilgili kullanıcı etkinliğini görüntülemeye yönelik bir araştırma aracıdır.
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
ms.openlocfilehash: a0cbe8409517d5b27e6f7eb1b9dca54cd3b238ae
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631418"
---
# <a name="manage-insider-risk-management-forensic-evidence-preview"></a>Insider risk yönetimi adli kanıtlarını yönetme (önizleme)

>[!IMPORTANT]
>Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Yapılandırma adımlarını tamamladıktan ve adli kanıt ilkenizi oluşturduktan sonra, ilkede tanımlanan göstergelerin koşullarını karşılayan riskli güvenlikle ilgili olabilecek kullanıcı etkinliklerine yönelik uyarılar görmeye başlarsınız.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="dashboard"></a>Pano

Adli kanıt panosu, kuruluşunuzdaki adli kanıt yapılandırmasının önemli alanlarının özet görünümüdür. Önizleme için pano yalnızca **Adli kanıt cihazı sistem durumu** bölümünü içerir. Cihaz durumu sekmesini ve raporunu açmak için **Cihaz sistem durumu** **raporunu görüntüle'yi** seçin. Diğer bölümler gelecek sürümlerde yer alacaktır.

## <a name="managing-users"></a>Kullanıcıları yönetme

Belirli kullanıcıları adli kanıt yakalamaya uygun hale gelmeden önce istemeniz ve onaylamanız gerekir. Yalnızca bir adli kanıt ilkesine kullanıcı eklemek, bu kullanıcıları yakalamaya otomatik olarak uygun hale getirmez. Adli kanıt ilkeleri oluşturulmadan önce veya sonra kullanıcıları isteyebilir ve onaylayabilirsiniz, ancak ilke göstergeleriyle ilişkili küçük resim yakalamaları yalnızca kullanıcılar onaylandıktan sonra oluşturulur ve gözden geçirilebilir.

*Insider Risk Yönetimi* veya *Insider Risk Yönetimi Yöneticileri* rol gruplarına atanan kullanıcılar *, Insider Risk Yönetimi Onaylayanları* rol grubuna atanan kullanıcılara onay istekleri gönderebilir.

### <a name="request-capturing-approvals"></a>Onayları yakalama isteği

Belirli kullanıcılar için adli kanıt yakalama özelliğinin açılmasını istemeniz gerekir. İstek gönderildiğinde, kuruluşunuzdaki onaylayanlara e-postayla bildirim gönderilir ve isteği onaylayabilir veya reddedebilir. Onaylanırsa, kullanıcı veya **Onaylanan kullanıcılar** sekmesinde görünür ve yakalama için uygun olur. Ele alınmazsa, isteğin süresi gönderildiği günden itibaren 6 ay sonra dolar.

Onaylanan kullanıcıları adli kanıt yakalama için yapılandırmak için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Kullanıcı yönetimi'ne** gidin.
2. **Adli kanıt isteklerini yönet** sekmesini seçin.
3. **İstek oluştur'u** seçin.
4. **Kullanıcılar** sayfasında **Kullanıcı ekle'yi** seçin.
5. Belirli bir kullanıcıyı bulmak veya listeden bir veya daha fazla kullanıcı seçmek için **Ara'yı** kullanın. **Ekle'yi** ve ardından **İleri'yi** seçin.
6. **Adli kanıt ilkesi** sayfasında, eklenen kullanıcılar için bir adli kanıt ilkesi seçin. Seçtiğiniz ilke, kullanıcılar için yakalanacak etkinliğin kapsamını belirler.
7. **İleri**'yi seçin.
8. **Gerekçe** sayfasında, **adli kanıt yakalama** metin kutusunu açmak için Gerekçe'ye eklediğiniz kullanıcılar için bu yakalamanın neden etkinleştirilmesini istediğinizi gözden geçirene bildirin. Bu gerekli bir alandır. Tamamlandığında **İleri'yi** seçin.
9. **Email bildirimleri** sayfasında, kullanıcılara kuruluşunuzun ilkelerine uygun olarak cihazlarında adli kanıt yakalamanın açılacağını bildiren bir e-posta göndermek için bir bildirim şablonu kullanabilirsiniz. E-posta yalnızca istekleri onaylandığında kullanıcılara gönderilir.

    **Onaylanan kullanıcılara e-posta bildirimi gönder** onay kutusunu seçin. Var olan bir şablonu seçin ve yeni bir şablon oluşturun. Yeni şablon oluşturmak için **Bildirim şablonu oluştur'u** seçin ve **Yeni e-posta bildirimi şablonu** bölmesinde aşağıdaki gerekli alanları tamamlayın.

10. **İleri**'yi seçin.
11. **Son** sayfasında, isteği göndermeden önce ayarlarınızı gözden geçirin. İstek değerlerinden herhangi birini değiştirmek için **Kullanıcıları düzenle** veya **Gerekçeyi düzenle'yi** seçin veya isteği oluşturup gözden geçirenlere göndermek için **Gönder'i** seçin.

Bekleyen onay isteklerini görüntülemek için **Insider risk yönetimi** > **Adli kanıt (önizleme)****Bekleyen istekler'e** >  gidin. Burada bekleyen istekleri olan kullanıcıları, e-posta adreslerini, istek gönderme tarihini ve onay isteğini gönderenleri görürsünüz. Hiçbir kullanıcı görüntülenmezse, herhangi bir kullanıcı için bekleyen onay isteği yoktur.

*Insider Risk Yönetimi Onaylayanları* rol grubuna atanan kullanıcılar **Adli kanıt isteği (önizleme)** sekmesinde bir kullanıcı seçebilir ve isteği gözden geçirebilir. İsteği gözden geçirdikten sonra, bu kullanıcılar adli kanıt yakalama isteğini onaylayabilir veya reddedebilir. Yakalama isteğinin onaylanması veya reddedilmesi, kullanıcılar için bekleyen isteği bu görünümden kaldırır.

### <a name="approve-or-reject-capturing-requests"></a>Yakalama isteklerini onaylama veya reddetme

İstekler tamamlandıktan sonra *Insider Risk Management Onaylayanları* rol grubuna atanan kullanıcılar onay isteği için bir e-posta bildirimi alır. İstekleri onaylamak veya reddetmek için gözden geçirenlerin aşağıdaki adımları tamamlaması gerekir:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Bekleyen istekler'e** gidin.
2. Gözden geçirmek için bir kullanıcı seçin.
3. **Adli kanıt isteğini gözden geçir (önizleme)** bölmesinde, istek sahibi tarafından gönderilen gerekçeyi gözden geçirin. **Uygun olduğunda Onayla** veya **Reddet'i** seçin.
4. **İstek onaylandı** veya **İstek reddedildi** sayfasında **Kapat'ı** seçin.

![Insider risk yönetimi adli kanıt onayı.](../media/insider-risk-forensic-evidence-approval.png)

### <a name="revoke-capturing-approvals"></a>Yakalama onaylarını iptal etme

Gerekirse, belirli kullanıcıların onayını iptal edebilir ve bunları adli kanıt yakalamanın dışında tutabilirsiniz. Onay iptal edilirse bu kullanıcılar için var olan yakalamalar silinmez veya kaldırılamaz; yalnızca bu kullanıcılar için gelecekte etkinlik yakalama devre dışı bırakılır.

Kullanıcıların onaylarını iptal etmek için *Insider Risk Management Onaylayanları* rol grubuna atanan kullanıcıların aşağıdaki adımları tamamlaması gerekir:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Kullanıcı yönetimi'ne** gidin.
2. **Onaylanan kullanıcılar** sekmesini seçin.
3. Bir kullanıcı seçin ve ardından **Kaldır'ı** seçin.
4. Kaldırma onayı sayfasında, yakalama onayını iptal etmek için **Kaldır'ı** seçin veya onay sayfasını kapatmak için **İptal'i** seçin.

## <a name="creating-and-managing-notification-templates"></a>Bildirim şablonları oluşturma ve yönetme

Kullanıcılara kuruluşunuzun ilkelerine uygun olarak cihazlarında adli kanıt yakalamanın açılacağını bildiren bir e-posta göndermek için bildirim şablonu oluşturabilir ve kullanabilirsiniz. E-posta yalnızca istekleri onaylandığında kullanıcılara gönderilir.

![Insider risk yönetimi adli kanıt bildirimi.](../media/insider-risk-forensic-evidence-notification.png)

Yeni bir bildirim şablonu oluşturmak için aşağıdaki adımları tamamlayın:

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Bildirim şablonları'na** gidin.
2. **Bildirim şablonu oluştur'u** seçin.
3. **Yeni e-posta bildirimi şablonu** bölmesinde aşağıdaki gerekli alanları tamamlayın:
    - Şablon adı
    - Gönderme başlangıç
    - Konu
    - İleti gövdesi
4. **Kaydet'i** seçin

Mevcut bildirim şablonunu silmek için bir şablon seçin ve **Sil'i** seçin.

## <a name="viewing-capture-clips"></a>Yakalama kliplerini görüntüleme

Yalnızca adli kanıt ilkelerinde seçilen göstergeler tarafından tanımlanan etkinlikleri yakalama seçeneğini belirlediyseniz, yakalama klipleri uyarının bir parçası olarak kullanılabilir ve **Uyarılar panosundaki** **Adli kanıt (önizleme)** sekmesinden erişilebilir. Uyarılar daha sonra vakalara yükseltilirse, ilişkili kliplere **Servis Talepleri** panosundaki **Adli kanıt (önizleme)** sekmesinden erişilebilir.

Adli kanıt ilkelerine dahil edilen kullanıcılar tarafından gerçekleştirilen güvenlikle ilgili etkinlikleri yakalama seçeneğini belirlediyseniz, **Kullanıcı etkinlik raporu** panosunda tek tek kullanıcılara yönelik klipleri görüntülersiniz.

>[!IMPORTANT]
>Adli kanıt klipleri, yakalandıktan 120 gün sonra veya önizleme döneminin sonunda (hangisi daha erkense) silinir. Adli kanıt kliplerini silinmeden önce indirebilir veya aktarabilirsiniz.

### <a name="reviewing-capture-clips-included-with-alerts"></a>Uyarılara dahil edilen yakalama kliplerini gözden geçirme

İlkeler tarafından oluşturulan uyarılar için, kullanıcılar için adli kanıt yakalamaları **Uyarılar** panosundaki **Adli kanıt (önizleme)** sekmesinde gözden geçirilebilir. Uyarı için bir veya daha fazla yakalama varsa, bu uyarı üst bilgisini oluşturan etkinlik bölümünde **Adli kanıt görüntüleme** bildirimini de görürsünüz. Etkinlik yakalamalarını gözden geçirmek için bildirim bağlantısını veya **Adli kanıt (önizleme)** sekmesini seçebilirsiniz.

![Insider risk yönetimi adli kanıt kullanıcı etkinliği.](../media/insider-risk-forensic-evidence-user-activity.png)

Genel olarak, adli kanıt yakalamaları içerebilecek riskli olabilecek etkinliklere yönelik bir uyarıyı gözden geçirmek temelde, adli kanıt yakalamaları olmadan bir uyarıyı gözden geçirmekle aynıdır. Önemli fark, geçerli yakalamaların dahil edilmesidir. **Adli kanıt (önizleme)** sekmesi, uyarıyla ilişkili tüm kullanılabilir yakalamalara erişim sağlar. Her yakalama görüntülenir ve aşağıdaki bilgileri içerir:

- **Tarih/saat (UTC)**: Yakalamanın tarihi, saati (UTC) ve süresi.
- **Cihaz**: Windows 10/11'deki cihazın adı.
- **Etkinlik türü**: Yakalamaya dahil edilen insider risk yönetimi etkinlik türü. Bu etkinlikler, ilişkili ilkeye atanan genel ve ilke göstergelerini temel alır.
- **Yakalama olayları**: Her yakalama, incelemenizi yakalama oturumuna yönelik belirli etkinliklere odaklanmanıza yardımcı olmak için yakalama içinde olaylar içerir.

Yakalama klibini görüntülemek için aşağıdaki adımları tamamlayın:

1. Gerekirse, kullanılabilir yakalamalar için filtreleri yapılandırın. **Tarihlere (UTC)** veya **Etkinliğe** göre filtreleyebilirsiniz.
2. Gözden geçirmek için bir klip seçin.
3. Gözden geçirmek için cihaz izleyicisini seçin. Cihaza bağlı her monitör (en fazla 4) adli kanıt yakalama için uygundur ve *Görüntü 1*, *Görüntü 2* vb. olarak listelenir.
4. Video oynatıcı denetimlerini kullanarak klibin tamamını baştan sona gözden geçirmek için *Yürüt denetimini* seçin.
5. İncelemenin kapsamını klipteki belirli bir olayla kapsamak istiyorsanız, video oynatıcının sağındaki **Olayları yakala** listelerinden olayı seçin.

### <a name="reviewing-capture-clips-included-with-cases"></a>Servis talebine dahil edilen yakalama kliplerini gözden geçirme

Uyarılar vakalara yükseltilirse, ilgili tüm adli kanıt yakalamaları olayın bir parçası olarak dahil edilir. Vakalar için adli kanıt yakalamalarını gözden geçirmek, uyarıları incelemenin bir parçası olarak yakalamaları gözden geçirme işlemiyle aynı süreci izler.

### <a name="reviewing-capture-clips-without-alerts"></a>Uyarı olmadan yakalama kliplerini gözden geçirme

Uyarılarla ilişkili olmayan etkinliğin kliplerini görüntülemek için [Kullanıcı etkinliği raporlarını](/microsoft-365/compliance/insider-risk-management-activities#user-activity-reports) kullanacaksınız. Kullanıcı etkinliği raporları, belirli kullanıcılara yönelik etkinlikleri geçici olarak veya açık bir şekilde şirket içi risk yönetimi ilkesine atamak zorunda kalmadan tanımlı bir süre boyunca incelemenize olanak tanır. Bu kullanıcı etkinlikleri adli kanıt yakalama tarafından desteklenen etkinlikleri içerirse, klipler kullanıcı etkinliğine dahil edilir.

Adli kanıt ilkesine dahil olup olmadıklarına bakılmaksızın güvenlikle ilgili tüm kullanıcı etkinliklerini yakalamak için adli kanıt yapılandırdıysanız, **Insider risk yönetimi** > **Kullanıcı etkinlik raporlarını** seçip belirli bir kullanıcıyı seçip **Adli kanıt (önizleme)** sekmesini seçerek bu yakalamaları gözden geçirirsiniz.

## <a name="device-health-report-preview"></a>Cihaz durumu raporu (önizleme)

Cihazlar adli kanıtı destekleyecek şekilde yapılandırıldıktan sonra, **Insider risk yönetimi** > **Adli kanıt (önizleme)** > **Cihaz** durumu'na giderek kuruluşunuzdaki tüm cihazlar için Microsoft Purview İstemcisi sistem durumunu gözden geçirebilirsiniz.

![Insider risk yönetimi adli kanıt cihaz durumu.](../media/insider-risk-forensic-evidence-device-health.png)

Rapor, adli kanıt aracısının yüklü olduğu tüm cihazların durumunu ve durumunu görüntülemenizi sağlar. Rapordaki her rapor pencere öğesi son 24 saate ilişkin bilgileri görüntüler.

- **Çevrimiçi cihazlar**: Şu anda çevrimiçi olan cihazların toplam sayısı.
- **Çevrimdışı cihazlar**: Şu anda çevrimdışı olan cihazların toplam sayısı.
- **Uyarı içeren cihazlar: Uyarı** içeren cihazların toplam sayısı.
- **Hatalı cihazlar**: Hata içeren cihazların toplam sayısı.

Cihaz sistem durumu kuyruğu, kuruluşunuzdaki adli kanıt için yapılandırılmış tüm cihazları listeler. Ayrıca, raporda aşağıdaki cihaz özniteliklerinin durumu listelenir:

- **Cihaz adı**: Cihazın *ComputerName* özniteliği tarafından tanımlanan cihaz adı.
- **Cihaz durumu**: Cihazdaki Microsoft Purview İstemcisi'nin durumu. Durum değerleri aşağıdaki gibidir:
    - ***Sağlıklı***: Cihazdaki istemci düzgün çalışıyor ve adli kanıt yakalama özellikleri tam olarak destekleniyor.
    - ***Uyarı***: Cihazdaki istemcinin bir uyarısı vardır ve adli kanıt yakalama özellikleri tam olarak desteklenmeyebilir.
    - ***Hata***: Cihazdaki istemcide bir hata var ve adli kanıt yakalama özellikleri devre dışı bırakıldı veya tam olarak desteklenmiyor.
- **Durum ayrıntıları**: Cihaz durumu hakkında daha fazla bilgi.
- **Son eşitleme (UTC)**: Cihaz için son durum eşitlemesinin tarihi ve saati.
- **Kullanıcı adı**: Durum eşitlemesi gerçekleştirildiğinde cihazda oturum açan kullanıcının kullanıcı adı.
- **Windows sürümü**: Cihazda yüklü Olan Microsoft Windows sürümü.
- **İstemci sürümü**: Cihazda yüklü Olan Microsoft Purview İstemcisi sürümü.

Cihaz durumu, cihazlarınız ve Microsoft Purview İstemcisi ile ilgili olası sorunlarla ilgili içgörüler sağlar. **Cihaz durumu sayfasındaki Cihaz durumu** sütunu, kullanıcı etkinliğinin yakalanmasını engelleyebilecek cihaz sorunları veya adli kanıt yakalama hacminin neden olağan dışı olduğu konusunda sizi uyarabilir. Cihaz sistem durumu, adli kanıt yakalamaya dahil edilen cihazların iyi durumda olduğunu ve dikkat veya yapılandırma değişikliklerine gerek olmadığını da onaylayabilir. Aşağıdaki tabloda olası durum ayrıntıları iletileri ve uyarıları ve hataları gidermek için gerçekleştirebileceğiniz önerilen eylemler listelenmiştir:

|**Durum Ayrıntıları**|**Durum**|**Önerilen Eylem**|
|:----------|:-------|:-------------------|
| İç sunucu hatası oluştu. Sonuç olarak, yakalama verileri eksik olabilir. | Error | Daha fazla araştırma için Microsoft ile destek bileti oluşturma |
| Karşıya yükleme bant genişliği bu cihazdaki yapılandırılan sınırın %90'ını buldu. Yakalamaların üzerine yakında yazılabilir.  | Uyarı | [Adli kanıt ayarları](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) sayfasında karşıya yükleme bant genişliği sınırını artırın. |
| Bu cihazda yapılandırılan karşıya yükleme bant genişliği sınırına ulaşıldı. Bu gün için başka yakalama karşıya yüklenmeyecek. | Error | [Adli kanıt ayarları](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) sayfasında karşıya yükleme bant genişliği sınırını artırın. |
| Çevrimdışı depolama alanı, bu cihazdaki yapılandırılan sınırın %90'ını aştı. Yakalamaların üzerine yakında yazılabilir.  | Uyarı | [Adli kanıt ayarları](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) sayfasında çevrimdışı yakalama önbelleği sınırını artırın. |
| Yapılandırılan çevrimdışı depolama sınırına bu cihazda ulaşıldı. Sonuç olarak, çevrimdışı yakalamaların üzerine yazılır. | Error | [Adli kanıt ayarları](/microsoft-365/compliance/insider-risk-management-forensic-evidence-configure) sayfasında çevrimdışı yakalama önbelleği sınırını artırın. |
| Cihazdaki CPU kullanımı maksimum eşiği aştı. | Error | Yakalama işlemi durduruldu ve birkaç dakika içinde yeniden başlatılacak. |
| Cihazdaki bellek kullanımı maksimum eşiği aştı. | Error | Yakalama işlemi durduruldu ve birkaç dakika içinde yeniden başlatılacak. |
| Cihazdaki GPU kullanımı maksimum eşiği aştı. | Error | Yakalama işlemi durduruldu ve birkaç dakika içinde yeniden başlatılacak. |
| Cihazda yüklü olan Microsoft Purview İstemcisi, adli kanıt ilkesiyle eşitlenemiyor. | Uyarı | Ağa bağlanma & istemciyi yeniden yükleme |
| Cihazda yüklü olan Microsoft Purview İstemcisi 24 saatten fazla bir süredir adli kanıt ilkesiyle eşitlenmemiş. | Error | Ağa bağlanma & istemciyi yeniden yükleme |
| Microsoft Purview İstemcisi, bu cihazda hiçbir grafik kartı algılanamadığından etkinliği yakalayamıyor. | Error | Grafik kartı ekleme veya cihazı grafik kartı olan bir kartla değiştirme |
| Microsoft Purview İstemcisi, bu cihazda hiçbir görüntü izleyicisi algılanamadığından etkinliği yakalayamıyor. | Error | Bu cihaz için monitör ekle |
| Microsoft Purview İstemcisi, bu cihazdaki monitörler kapatıldığından veya bağlantısı kesildiğinden etkinliği yakalayamıyor. | Error | Cihaz için monitörleri bağlama/açma |
| Cihaz, adli kanıt yakalamalarını depolayan dizine erişemiyor. | Error | İstemciyi bu cihaza yeniden yükleyin |
| Kodlayıcı başlatılamadı.  | Error | İstemciyi bu cihaza yeniden yükleyin. |

Önerilen eylemler istemciyle ilgili sorunları çözmezse Microsoft Desteği başvurun.
