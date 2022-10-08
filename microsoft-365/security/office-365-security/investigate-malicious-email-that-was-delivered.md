---
title: Microsoft 365'te teslim edilen kötü amaçlı e-postaları araştırma, Kötü amaçlı e-posta bulma ve araştırma
keywords: TIMailData-Inline, Güvenlik Olayı, olay, Uç Nokta için Microsoft Defender PowerShell, e-posta kötü amaçlı yazılımı, güvenliği aşılmış kullanıcılar, e-posta kimlik avı, e-posta kötü amaçlı yazılımı, e-posta üst bilgilerini okuma, üst bilgileri okuma, e-posta üst bilgilerini açma,özel eylemler
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- m365-security
description: Kötü amaçlı e-postaları bulmak ve araştırmak için tehdit araştırma ve yanıt özelliklerini kullanmayı öğrenin.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 5affd100b73478d1ee983b83dfdaea394a9d3acd
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68092037"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Microsoft 365'te teslim edilen kötü amaçlı e-postayı araştırma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**

- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365 için Microsoft Defender](defender-for-office-365.md), kuruluşunuzdaki kişileri riske atacak etkinlikleri araştırmanıza ve kuruluşunuzu korumak için eylem gerçekleştirmenize olanak tanır. Örneğin, kuruluşunuzun güvenlik ekibinin bir parçasıysanız, teslim edilen şüpheli e-posta iletilerini bulabilir ve araştırabilirsiniz. Bunu [, Tehdit Gezgini'ne (veya gerçek zamanlı algılamalara)](threat-explorer.md) kullanarak yapabilirsiniz.

> [!NOTE]
> Düzeltme makalesine [buradan](remediate-malicious-email-delivered-office-365.md) atlayın.

## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdaki gereksinimlerin karşılandığından emin olun:

- [Kuruluşunuzda Office 365 için Microsoft Defender](defender-for-office-365.md) ve [lisanslar kullanıcılara atanır](../../admin/manage/assign-licenses-to-users.md).

- Kuruluşunuz için [denetim günlüğü](../../compliance/turn-audit-log-search-on-or-off.md) açık.

- Kuruluşunuzda istenmeyen posta, kötü amaçlı yazılımdan koruma, kimlik avına karşı koruma vb. için tanımlanmış ilkeler vardır. Bkz[. Office 365 tehditlere karşı koruma](protect-against-threats.md).

- Genel yöneticisiniz veya Microsoft 365 Defender portalında Güvenlik Yöneticisi veya Arama ve Temizleme rolü atanmıştır. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md). Bazı eylemler için Önizleme rolü de atanmış olmalıdır.

### <a name="preview-role-permissions"></a>Rol izinlerini önizleme

İleti üst bilgilerini görüntüleme veya e-posta iletisi içeriğini indirme gibi belirli eylemleri gerçekleştirmek için *Önizleme* rolünün başka bir uygun rol grubuna eklenmesi gerekir. Aşağıdaki tabloda gerekli roller ve izinler açıklanır.

|Etkinlik|Rol grubu|Önizleme rolü gerekli mi?|
|---|---|---|
|Tehditleri analiz etmek için Tehdit Gezgini'ni (ve gerçek zamanlı algılamaları) kullanma|Genel Yönetici <p> Güvenlik Yöneticisi <p> Güvenlik Okuyucusu|Hayır|
|Tehdit Gezgini'ni (ve Gerçek zamanlı algılamaları) kullanarak e-posta iletilerinin üst bilgilerini görüntülemenin yanı sıra karantinaya alınmış e-posta iletilerini önizleme ve indirme|Genel Yönetici <p> Güvenlik Yöneticisi <p> Güvenlik Okuyucusu|Hayır|
|Üst bilgileri görüntülemek, e-postayı önizlemek (yalnızca e-posta varlığı sayfasında) ve posta kutularına teslim edilen e-posta iletilerini indirmek için Tehdit Gezgini'ni kullanın|Genel Yönetici <p> Güvenlik Yöneticisi <p> Güvenlik Okuyucusu <p> Önizleme|Evet|

> [!NOTE]
> **Önizleme** bir rol grubu değil, bir roldür. Önizleme rolü, Microsoft 365 Defender portalında mevcut bir rol grubuna veya yeni bir rol grubuna eklenmelidir. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md).
>
> Genel Yönetici rolüne konumundaki <https://admin.microsoft.com>Microsoft 365 yönetim merkezi atanır. Güvenlik Yöneticisi ve Güvenlik Okuyucusu rolleri Microsoft 365 Defender portalında atanır.

E-posta önizleme ve indirmenin hassas etkinlikler olduğunu anlıyoruz, bu nedenle bu etkinlikler için denetim etkinleştirildi. Bir yönetici bu etkinlikleri e-posta üzerinde gerçekleştirdikten sonra, denetim günlükleri aynı şekilde oluşturulur ve **Denetim** \> **Arama** sekmesindeki Microsoft 365 Defender portalında <https://security.microsoft.com> görülebilir ve **Kullanıcılar** kutusunda yönetici adına filtre uygular. Filtrelenen sonuçlar **AdminMailAccess** etkinliğini gösterir. Önizlemesi veya indirilen e-posta hakkında **daha fazla bilgi** bölümünde ayrıntıları görüntülemek için bir satır seçin.

## <a name="find-suspicious-email-that-was-delivered"></a>Teslim edilen şüpheli e-postayı bulma

Tehdit Gezgini iletileri bulma ve silme, kötü amaçlı bir e-posta gönderenin IP adresini belirleme veya daha fazla araştırma için olay başlatma gibi birçok amaca hizmet eden güçlü bir rapordur. Aşağıdaki yordam, alıcının posta kutularındaki kötü amaçlı e-postaları bulmak ve silmek için Gezgin'i kullanmaya odaklanır.

> [!NOTE]
> Explorer'daki varsayılan aramalar şu anda sıfır saatlik otomatik temizleme (ZAP) ile bulut posta kutusundan kaldırılmış teslim edilen öğeleri içermez. Bu sınırlama tüm görünümler için geçerlidir (örneğin, **Email \> Kötü Amaçlı Yazılım** veya **Email \> Kimlik Avı** görünümleri). ZAP tarafından kaldırılan öğeleri eklemek için, **ZAP tarafından Kaldırılan'ı** içerecek şekilde ayarlanmış bir **Teslim eylemi** eklemeniz gerekir. Tüm seçenekleri eklerseniz, ZAP tarafından kaldırılan öğeler de dahil olmak üzere tüm teslim eylemi sonuçlarını görürsünüz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **Gezgini'ne** gidin. **Doğrudan Gezgin** sayfasına gitmek için kullanın<https://security.microsoft.com/threatexplorer>.

   **Gezgin** sayfasında **Ek eylemler** sütunu, yöneticilere e-posta işlemenin sonucunu gösterir. **Ek eylemler** sütununa **Teslim eylemi** ve **Teslim konumu** ile aynı yerden erişilebilir. Tehdit Gezgini'nin e-posta zaman çizelgesinin sonunda özel eylemler güncelleştirilebilir. Bu, avcılık deneyimini yöneticiler için daha iyi hale getirmeyi amaçlayan yeni bir özelliktir.

2. **Görünüm** menüsünde, açılan listeden **Email** \> **Tüm e-postalar'ı** seçin.

    :::image type="content" source="../../media/tp-InvestigateMalEmail-viewmenu.png" alt-text="Kötü Amaçlı Yazılım açılan listesi" lightbox="../../media/tp-InvestigateMalEmail-viewmenu.png":::

    *Kötü Amaçlı Yazılım* görünümü şu anda varsayılandır ve kötü amaçlı yazılım tehdidi algılanan e-postaları yakalar. *Kimlik Avı görünümü, Kimlik Avı* için aynı şekilde çalışır.

    Ancak *Tüm e-posta* görünümü, kuruluş tarafından alınan her postayı (tehditlerin algılanıp algılanmadığı) listeler. Tahmin edebileceğiniz gibi, bu çok fazla veridir, bu nedenle bu görünümde filtrenin uygulanmasını isteyen bir yer tutucu gösterilir. (Bu görünüm yalnızca Office 365 için Defender P2 müşterileri için kullanılabilir.)

    *Gönderimler* görünümü, yönetici veya kullanıcı tarafından gönderilen ve Microsoft'a bildirilen tüm postaları gösterir.

4. **Tehdit Gezgini'nde arama ve filtreleme**: Yöneticilere araştırmalarında yardımcı olmak için arama çubuğunda sayfanın en üstünde filtreler görünür. Aynı anda birden çok filtre uygulanabileceğine ve aramayı daraltmak için filtreye birden çok virgülle ayrılmış değer eklendiğine dikkat edin. Hatırla:

    - Filtreler çoğu filtre koşulunda tam eşleştirme yapar.
    - Konu filtresi bir CONTAINS sorgusu kullanır.
    - URL filtreleri protokollerle veya protokoller olmadan çalışır (ör. https).
    - URL etki alanı, URL yolu ve URL etki alanı ile yol filtreleri filtrelemek için protokol gerektirmez.
    - İlgili sonuçları almak için filtre değerlerini her değiştirdiğinizde Yenile simgesine tıklamanız gerekir.

5. **Gelişmiş filtreler**: Bu filtrelerle karmaşık sorgular oluşturabilir ve veri kümenizi filtreleyebilirsiniz. *Gelişmiş Filtreler'e* tıklanması, seçenekler içeren bir açılır menü açar.

   Gelişmiş filtreleme, arama özelliklerine harika bir ektir. **Alıcı**, **Gönderen** ve **Gönderen etki alanı** filtrelerindeki boole DEĞERI DEĞİl, yöneticilerin değerleri dışlayarak araştırma yapmasına olanak tanır. Bu seçenek **, Seçimin hiçbirinde eşittir seçeneğidir** . Bu seçenek, yöneticilerin istenmeyen posta kutularını araştırmalardan (örneğin, uyarı posta kutuları ve varsayılan yanıt posta kutuları) dışlamalarına olanak tanır ve yöneticilerin Belirli bir konuyu (örneğin, Dikkat) aradığı durumlarda kullanışlıdır ve Burada Alıcı *eşittir hiçbiri: defaultMail@contoso.com* olarak ayarlanabilir. Bu tam bir değer aramasıdır.

   :::image type="content" source="../../media/tp-InvestigateMalEmail-AdvancedFilter.png" alt-text="Alıcılar bölmesi" lightbox="../../media/tp-InvestigateMalEmail-AdvancedFilter.png":::

   Başlangıç tarihine ve bitiş tarihine bir zaman filtresi eklemek, güvenlik ekibinizin hızlı bir şekilde detaya gitmelerine yardımcı olur. İzin verilen en kısa süre 30 dakikadır. Şüpheli eylemi zaman çerçevesine göre daraltabiliyorsanız (örneğin, 3 saat önce gerçekleşti), bu bağlamı sınırlandıracak ve sorunu belirlemeye yardımcı olacaktır.

   :::image type="content" source="../../media/tp-InvestigateMalEmail-FilterbyHours.png" alt-text="Saate göre filtreleme seçeneği" lightbox="../../media/tp-InvestigateMalEmail-FilterbyHours.png":::

6. **Tehdit Gezgini'ndeki alanlar**: Tehdit Gezgini *Teslim eylemi*, *Teslim konumu*, *Özel eylem*, *Yön bilgisi*, *Geçersiz Kılmalar* ve *URL tehdidi* gibi güvenlikle ilgili çok daha fazla posta bilgisini kullanıma sunar. Ayrıca kuruluşunuzun güvenlik ekibinin daha yüksek bir kesinlikle araştırma yapmasına da olanak tanır.

    *Teslim eylemi* , mevcut ilkeler veya algılamalar nedeniyle bir e-postada gerçekleştirilen eylemdir. Bir e-postanın gerçekleştirebileceği olası eylemler şunlardır:

    - **Teslim edildi** – E-posta bir kullanıcının gelen kutusuna veya klasörüne teslim edildi ve kullanıcı doğrudan erişebilir.
    - **Gereksiz (** Gereksiz postaya teslim edildi)– e-posta kullanıcının gereksiz klasörüne veya silinmiş klasörüne gönderildi ve kullanıcının Gereksiz veya Silinmiş klasöründeki e-posta iletilerine erişimi var.
    - **Engellendi** – karantinaya alınan, başarısız olan veya bırakılan tüm e-posta iletileri.
    - **Değiştirildi** – Kötü amaçlı eklerin, ekin kötü amaçlı olduğunu belirten .txt dosyalarıyla değiştirildiği tüm e-postalar

    **Teslim konumu**: Yöneticilerin şüpheli kötü amaçlı postaların nerede sona erdiği ve bu posta üzerinde hangi eylemlerin gerçekleştirildiğini anlamasına yardımcı olmak için Teslim konumu filtresi kullanılabilir. Sonuçta elde edilen veriler elektronik tabloya aktarılabilir. Olası teslimat konumları şunlardır:

    - **Gelen kutusu veya klasör** – E-posta, e-posta kurallarınıza göre Gelen Kutusu'nda veya belirli bir klasördedir.
    - **Şirket içi veya harici** – Posta kutusu Bulutta değil, şirket içindedir.
    - **Gereksiz klasör** – E-posta kullanıcının Gereksiz posta klasöründedir.
    - **Silinmiş öğeler klasörü** – E-posta kullanıcının Silinmiş öğeler klasöründedir.
    - **Karantina** : Kullanıcının posta kutusunda değil karantinadaki e-posta.
    - **Başarısız** – E-posta posta kutusuna ulaşamadı.
    - **Bırakıldı** – E-posta, posta akışının bir yerinde kayboldu.

    **Yön**: Bu seçenek, güvenlik operasyonları ekibinizin bir postanın geldiği veya gittiği 'yöne' göre filtreleme yapmasına olanak tanır. Yön değerleri *Gelen*, *Giden* ve *Kuruluş İçi* değerleridir (kuruluşunuza dışarıdan gelen, kuruluşunuzdan gönderilen veya sırasıyla kuruluşunuza dahili olarak gönderilen postalara karşılık gelir). Bu bilgiler güvenlik operasyonları ekiplerinin kimlik sahtekarlığı ve kimliğe bürünme tespit etmelerine yardımcı olabilir çünkü Yön değeri (örn. *Gelen*) ve gönderenin etki alanı (iç etki alanı *gibi görünüyor* ) belirgin olacaktır! Yön değeri ayrıdır ve İleti İzleme'den farklı olabilir. Sonuçlar elektronik tabloya aktarılabilir.

    **Geçersiz kılmalar**: Bu filtre postanın ayrıntılar sekmesinde görünen bilgileri alır ve postalara izin vermek ve postaları engellemek için kuruluş veya kullanıcı ilkelerinin nerede *geçersiz kılındığını* göstermek için kullanır. Bu filtrenin en önemli özelliği, kuruluşunuzun güvenlik ekibinin yapılandırma nedeniyle kaç şüpheli e-postanın teslim edildiğini görmesine yardımcı olmasıdır. Bu, onlara gerektiğinde izin ve blokları değiştirme fırsatı verir. Bu filtrenin bu sonuç kümesi elektronik tabloya aktarılabilir.

    |Tehdit Gezgini Geçersiz Kılmaları|Ne anlama gelirler?|
    |---|---|
    |Kuruluş İlkesi tarafından izin verilir|Posta kutusuna kuruluş ilkesi tarafından yönlendirildiği şekilde posta kutusuna izin verildi.|
    |Kuruluş ilkesi tarafından engellendi|Postanın kuruluş ilkesi tarafından yönlendirildiği şekilde posta kutusuna teslim edilmesi engellendi.|
    |Dosya uzantısı Kuruluş İlkesi tarafından engellendi|Dosyanın kuruluş ilkesi tarafından yönlendirildiği şekilde posta kutusuna teslim edilmesi engellendi.|
    |Kullanıcı İlkesi tarafından izin verilir|Posta kutusuna kullanıcı ilkesi tarafından yönlendirildiği şekilde posta kutusuna izin verildi.|
    |Kullanıcı İlkesi tarafından engellendi|Postanın, kullanıcı ilkesi tarafından yönlendirildiği şekilde posta kutusuna teslim edilmesi engellendi.|

    **URL tehdidi**: URL tehdit alanı, bir URL tarafından sunulan tehdidi göstermek için e-postanın *ayrıntılar* sekmesine eklenmiştir. URL tarafından sunulan tehditler *Kötü Amaçlı Yazılım*, *Kimlik Avı* veya *İstenmeyen Posta* içerebilir ve *tehdit içermeyen* bir URL, tehditler bölümünde *Yok* ifadesini söyler.

7. **Email zaman çizelgesi görünümü**: Güvenlik operasyonları ekibinizin daha fazla araştırma yapmak için e-posta ayrıntılarını ayrıntılı olarak incelemesi gerekebilir. E-posta zaman çizelgesi, yöneticilerin teslimden teslim sonrası e-postaya kadar bir e-postada gerçekleştirilen eylemleri görüntülemesine olanak tanır. E-posta zaman çizelgesini görüntülemek için, bir e-posta iletisinin konusuna tıklayın ve ardından zaman çizelgesini Email tıklayın. (Paneldeki Özet veya Ayrıntılar gibi diğer başlıklar arasında görünür.) Bu sonuçlar elektronik tabloya aktarılabilir.

    Email zaman çizelgesi, e-posta için tüm teslim ve teslim sonrası olayları gösteren bir tabloya açılır. E-postada başka eylem yoksa, özgün teslim için, *Kimlik Avı* gibi bir kararla *Engellendi* gibi bir sonuç belirten tek bir olay görmeniz gerekir. Yöneticiler, sekmedeki ve e-postadaki tüm ayrıntılar (Konu, Gönderen, Alıcı, Ağ ve İleti Kimliği gibi) dahil olmak üzere e-posta zaman çizelgesinin tamamını dışarı aktarabilir. E-posta geldiğinden bu yana gerçekleşen olayları anlamak için farklı konumları denetlemek için harcanan zaman az olduğundan, e-posta zaman çizelgesi rastgele zamanlamayı azaltıyor. Bir e-postada aynı anda birden çok olay gerçekleştiğinde veya bu olaylara yakın olduğunda, bu olaylar zaman çizelgesi görünümünde gösterilir.

8. **Önizleme/indirme**: Tehdit Gezgini, güvenlik operasyonları ekibinize şüpheli e-postayı araştırmak için gereken ayrıntıları verir. Güvenlik operasyonları ekibiniz aşağıdakilerden birini yapabilir:

    - [Teslim eylemini ve konumunu denetleyin](#check-the-delivery-action-and-location).

    - [E-postanızın zaman çizelgesini görüntüleyin](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Teslim eylemini ve konumunu denetleme

[Tehdit Gezgini'nde (ve gerçek zamanlı algılamalar)](threat-explorer.md) artık eski **Teslim Durumu** sütunu yerine **Teslim Eylemi** ve **Teslim Konumu** sütunlarına sahipsiniz. Bu, e-posta iletilerinizin nereye indiğiyle ilgili daha eksiksiz bir resim oluşturur. Bu değişikliğin amacının bir parçası, güvenlik operasyonları ekipleri için araştırma yapmayı kolaylaştırmaktır, ancak net sonuç olarak sorun e-posta iletilerinin konumunu bir bakışta bilmek elde edilir.

Teslim Durumu artık iki sütuna ayrılmıştır:

- **Teslim eylemi** - Bu e-postanın durumu nedir?
- **Teslim konumu** - Sonuç olarak bu e-posta nereye yönlendirildi?

Teslim eylemi, mevcut ilkeler veya algılamalar nedeniyle bir e-postada gerçekleştirilen eylemdir. Bir e-postanın gerçekleştirebileceği olası eylemler şunlardır:

- **Teslim edildi** – E-posta bir kullanıcının gelen kutusuna veya klasörüne teslim edildi ve kullanıcı doğrudan erişebilir.
- **Gereksiz-** e-posta kullanıcının gereksiz klasörüne veya silinmiş klasörüne gönderildi ve kullanıcının Gereksiz veya Silinmiş klasöründeki e-posta iletilerine erişimi var.
- **Engellendi** – karantinaya alınan, başarısız olan veya bırakılan tüm e-posta iletileri.
- **Değiştirildi** – Kötü amaçlı eklerin, ekin kötü amaçlı olduğunu belirten .txt dosyalarıyla değiştirildiği tüm e-postalar.

Teslim konumu, teslim sonrası çalışan ilkelerin ve algılamaların sonuçlarını gösterir. Bir Teslim Eylemi ile bağlantılıdır. Bu alan, sorun postası bulunduğunda gerçekleştirilen eylem hakkında içgörü sağlamak için eklendi. Teslimat konumunun olası değerleri şunlardır:

- **Gelen kutusu veya klasör** – E-posta gelen kutusunda veya bir klasördedir (e-posta kurallarınıza göre).
- **Şirket içi veya dış** – Posta kutusu bulutta yoktur, ancak şirket içindedir.
- **Gereksiz klasör** – E-posta kullanıcının Gereksiz klasöründedir.
- **Silinmiş öğeler klasörü** – E-posta kullanıcının Silinmiş öğeler klasöründedir.
- **Karantina** : Kullanıcının posta kutusunda değil karantinadaki e-posta.
- **Başarısız** – E-posta posta kutusuna ulaşamadı.
- **Bırakılan** : E-posta, posta akışının bir yerinde kaybolur.

### <a name="view-the-timeline-of-your-email"></a>E-postanızın zaman çizelgesini görüntüleme

**Email Zaman Çizelgesi**, Tehdit Gezgini'nde güvenlik operasyonları ekibiniz için avcılığı kolaylaştıran bir alandır. Bir e-postada aynı anda veya yakın zamanda birden çok olay gerçekleştiğinde, bu olaylar zaman çizelgesi görünümünde gösterilir. E-postaya teslim sonrasında gerçekleşen bazı olaylar **Özel eylemler** sütununda yakalanır. Bir e-posta iletisinin zaman çizelgesindeki bilgileri teslim sonrası gerçekleştirilen özel eylemlerle birleştirmek, yöneticilere ilkeler ve tehdit işleme (postanın nereye yönlendirildiği ve bazı durumlarda son değerlendirmenin ne olduğu gibi) hakkında içgörü sağlar.

> [!IMPORTANT]
> [Burada](remediate-malicious-email-delivered-office-365.md) bir düzeltme konusuna atlayın.

## <a name="related-topics"></a>İlgili konular

[Office 365'te teslim edilen kötü amaçlı e-postaları düzeltme](remediate-malicious-email-delivered-office-365.md)

[Office 365 için Microsoft Defender](office-365-ti.md)

[Office 365 tehditlere karşı koruma](protect-against-threats.md)

[Office 365 için Defender için raporları görüntüleme](view-reports-for-mdo.md)
