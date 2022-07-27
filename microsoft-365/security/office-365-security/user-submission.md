---
title: İstenmeyen posta, kimlik avı ve kötü amaçlı postalar için kullanıcı tarafından bildirilen e-posta ayarları
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 07/19/2022
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Yöneticiler, kullanıcılar tarafından bildirilen istenmeyen posta ve kimlik avı iletilerini toplamak için özel bir posta kutusunu (kullanıcı gönderimleri posta kutusu olarak da bilinir) nasıl tanımlayacağınızı öğrenebilir. Diğer ayarlar, kullanıcılar iletileri raporladığında raporlama deneyimini tamamlar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c32d4ff27d44600ebe182f0764cb47c638a354c7
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051678"
---
# <a name="user-reported-message-settings"></a>Kullanıcı tarafından bildirilen ileti ayarları

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutularına sahip Microsoft 365 kuruluşlarında, kullanıcılar kötü amaçlı veya kötü amaçlı olmayan iletiler bildirdiğinde _postayı özel posta kutusuna (kullanıcı posta kutusu göndermesi_ olarak da bilinir) yönlendirebilirsiniz. Kullanıcılar desteklenen raporlama seçeneklerini kullanarak e-posta iletilerini raporladığında, yöneticiler kuruluşlarında kullanıcı tarafından bildirilen ileti ayarlarını, bildirilen iletileri kullanıcı gönderimleri posta kutusuna gönderecek şekilde yapılandırabilir. Kullanıcı tarafından bildirilen iletileri kesmek için kullanıcı gönderimleri posta kutusunu yapılandırabilir (yalnızca kullanıcı gönderimleri posta kutusuna gönder) veya kullanıcılar iletileri Microsoft'a bildirdikçe kullanıcı tarafından bildirilen iletilerin kopyalarını alabilirsiniz. Bu ayarlar daha önce _Kullanıcı gönderimleri ilkesi_ olarak biliniyordu.

Kullanıcı tarafından bildirilen ileti ayarları ve kullanıcı gönderimleri posta kutusu aşağıdaki ileti raporlama seçenekleriyle çalışır:

- [Rapor İletisi eklentisi](enable-the-report-message-add-in.md)
- [Rapor Kimlik Avı eklentisi](enable-the-report-phish-add-in.md)
- [Üçüncü taraf raporlama araçları](#third-party-reporting-tools-options)

Kullanıcı tarafından bildirilen iletilerin doğrudan Microsoft yerine posta kutusuna gönderilmesi, yöneticilerin ileti **göndermeleri** sayfasında iletileri seçerek ve el ile Microsoft'a <https://security.microsoft.com/reportsubmission>bildirmesine olanak tanır. Daha fazla bilgi için bkz. [Yönetici gönderimi](admin-submission.md).

  > [!NOTE]
  > [raporlama Web üzerinde Outlook devre dışı bırakıldıysa](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), burada kullanıcı tarafından bildirilen iletilerin etkinleştirilmesi bu ayarı geçersiz kılar ve kullanıcıların Web üzerinde Outlook'da iletileri yeniden raporlamasına izin verir.

## <a name="configuration-requirements-for-the-user-submissions-mailbox"></a>Kullanıcı gönderme posta kutusu için yapılandırma gereksinimleri

Başlamadan önce yu öğesinin Exchange Online Protection ve Office 365 için Defender yapılandırarak, kullanıcı tarafından bildirilen iletilerin aşağıdaki adımlarda açıklandığı gibi filtrelenmeden kullanıcı gönderimleri posta kutusuna teslim edilmesi gerekir:

- Kullanıcının posta kutusunu SecOps posta kutusu olarak göndermesini belirleyin. Yönergeler için bkz. [Gelişmiş teslim ilkesinde SecOps posta kutularını yapılandırmak için Microsoft 365 Defender portalını kullanma](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy).

- Kullanıcının posta kutusunu göndermesi için aşağıdaki ayarlarla özel bir kötü amaçlı yazılımdan koruma ilkesi oluşturun:

  - Kötü amaçlı yazılım için sıfır saat otomatik temizlemeyi (ZAP) kapatın (**Koruma ayarları** bölümü \> **Kötü amaçlı yazılım için sıfır saat otomatik temizlemeyi etkinleştirme** seçili değil veya `-ZapEnabled $false` PowerShell'de).

  - Sık kullanılan ekler filtrelemesini kapatın (**Koruma ayarları** bölümü \> **Ortak ekler filtresini etkinleştirme filtresi** seçili değil veya `EnableFileFilter $false` PowerShell'de).
  
  Yönergeler için bkz. [Kötü amaçlı yazılımdan koruma ilkesi oluşturma](configure-anti-malware-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-malware-policies).

- Kullanıcı gönderimleri posta kutusunun **Standart** veya **Katı** önceden ayarlanmış güvenlik ilkelerine dahil edilmediğini doğrulayın. Yönergeler için bkz. [Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md).

- **Office 365 için Defender**: Aşağıdaki ek ayarları yapılandırın:

  - Kullanıcı gönderimleri posta kutusunu **Yerleşik koruma** önayarlı güvenlik ilkesinden hariç tutun. Yönergeler için bkz. [Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md).

  - Dinamik Teslim de dahil olmak üzere Güvenli Ekler taramasının kapalı olduğu kullanıcı gönderimleri posta kutusu için Güvenli Ekler ilkesi oluşturun (**Ayarlar** \> **Güvenli Ekler bilinmeyen kötü amaçlı yazılım yanıtı** bölümü \> **Kapalı** veya `-Enable $false` PowerShell'de). Yönergeler için bkz. [Office 365 için Microsoft Defender'da Güvenli Ekler ilkelerini ayarlama](set-up-safe-attachments-policies.md).

  - E-postada Güvenli Bağlantılar taramasının kapalı olduğu kullanıcı gönderimleri posta kutusu için bir Güvenli Bağlantılar ilkesi oluşturun (**URL & koruma ayarlarıNa** \> tıklayın **Açık: Güvenli Bağlantılar, kullanıcılar e-postadaki veya PowerShell'deki bağlantıları tıklattığında bilinen, kötü amaçlı bağlantıların listesini denetler**).`EnableSafeLinksForEmail $false` Yönergeler için bkz. [Office 365 için Microsoft Defender'de Güvenli Bağlantılar ilkelerini ayarlama](set-up-safe-links-policies.md).

Posta kutusunun bu gereksinimleri karşıladığını doğruladıktan sonra, kullanıcı gönderileri posta kutusunu ve diğer kullanıcı tarafından bildirilen ileti ayarlarını belirlemek için bu makaledeki yönergelerin geri kalanını kullanın.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. Doğrudan **Kullanıcı gönderimleri** sayfasına gitmek için kullanın <https://security.microsoft.com/userSubmissionsReportMessage>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Kullanıcı gönderimleri yapılandırmasını değiştirmek için aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:

  - [Microsoft 365 Defender portalındaki İzinler'de](permissions-microsoft-365-security-center.md) **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi**.

- Exchange Online PowerShell'e erişmeniz gerekir. Kullanmaya çalıştığınız hesabın Exchange Online PowerShell'e erişimi yoksa, gönderimler posta kutusunu belirtirken şuna benzer bir hata alırsınız:

  > Etki alanınızda bir e-posta adresi belirtme

  Exchange Online PowerShell'e erişimi etkinleştirme veya devre dışı bırakma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

  - [Exchange Online PowerShell'e erişimi etkinleştirme veya devre dışı bırakma](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Online'da İstemci Erişim Kuralları](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox-for-email"></a>E-posta için kullanıcı gönderimleri posta kutusunu yapılandırmak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>**, İlkeler & kuralları** \> **Tehdit ilkeleri** \> **Diğerleri** bölümünde **Kullanıcı tarafından bildirilen ileti ayarları'na** gidin. Doğrudan **Kullanıcı gönderimleri** sayfasına gitmek için kullanın <https://security.microsoft.com/userSubmissionsReportMessage>.

2. **Kullanıcı gönderimleri** sayfasında, gördükleriniz büyük ölçüde **Microsoft Outlook Rapor İletisi düğmesi** iki durumlu düğmesi tarafından belirlenir:

   - **-Inı** ![ Açık.](../../media/scc-toggle-on.png): Rapor İletisi eklentisini, Rapor Kimlik Avı eklentisini veya Web üzerinde Outlook'deki yerleşik raporlamayı içeren Microsoft tümleşik raporlama deneyimini kullanırsınız.

     Bu ayar, kullanıcıların karantina portalından hatalı pozitif iletiler bildirmesine de olanak tanır.

   - **Kapalı** ![ Geçiş yapın.](../../media/scc-toggle-off.png): Microsoft tümleşik raporlama deneyimi yerine üçüncü taraf ileti raporlama araçlarını kullanırsınız.

İlgili yapılandırma seçenekleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="microsoft-integrated-reporting-experience-options"></a>Microsoft tümleşik raporlama deneyimi seçenekleri

**Microsoft Outlook Rapor İletisi düğmesi**  ![Açık Durumdayken,](../../media/scc-toggle-on.png) **Kullanıcı gönderimleri** sayfasında aşağıdaki ayarlar kullanılabilir:

- **Bildirilen iletileri bölümüne gönderme** : Aşağıdaki seçeneklerden birini belirleyin:

  - **Microsoft**: Kullanıcı gönderileri posta kutusu kullanılmaz (bildirilen tüm iletiler analiz için Microsoft'a gider).

  - **Microsoft ve kuruluşumun posta kutusu**: Görüntülenen kutuya, kullanıcı posta kutusunu gönderdiğinde kullanılacak mevcut bir Exchange Online posta kutusunun e-posta adresini girin. Dağıtım gruplarına izin verilmez. Kullanıcı gönderimleri analiz için Microsoft'a ve bir yöneticinin veya güvenlik operasyonları ekibinin analiz etmek üzere kullanıcı gönderimleri posta kutusuna gider.

  - **Kuruluşumun posta kutusu**: Görüntülenen kutuya var olan bir Exchange Online posta kutusunun e-posta adresini girin. Dağıtım gruplarına izin verilmez. Kullanıcı gönderimleri yalnızca bir yöneticinin veya güvenlik operasyonları ekibinin analiz etmek için kullanıcı gönderimleri posta kutusuna gider. Bir yönetici iletileri el ile göndermediği sürece iletiler analiz için Microsoft'a gitmez.

  > [!IMPORTANT]
  > ABD Kamu kuruluşları (GCC, GCC High ve DoD) kuruluşlarında, **Bildirilen iletileri gönder** bölümünde sağlanan tek seçim **Kuruluşum'un posta kutusudur**. Diğer iki seçenek gri görünür.
  >
  > Web üzerinde Outlook'da gereksiz e-posta raporlamayı devre dışı bırakmak için Web üzerinde Outlook posta [kutusu ilkeleri](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/configure-outlook-web-app-mailbox-policy-properties) kullandıysanız ancak **Microsoft'u** veya **Microsoft'u ve kuruluşumun posta kutusunu** seçerseniz, kullanıcılar Web üzerinde Outlook  Rapor İletisi eklentisini veya Rapor Kimlik Avı eklentisini kullanarak.
  >
  > **Kuruluşum'un posta kutusunu** seçerseniz, bildirilen iletiler konumundaki **Gönderimler** sayfasındaki <https://security.microsoft.com/reportsubmission>**Kullanıcı tarafından bildirilen iletiler** sekmesinde görünür. Ancak iletiler yeniden taranmadığı için bu iletilerin **Sonuç** değeri her zaman boş olacaktır.
  >
  > [Kimlik avı simülasyonları yapmak için Saldırı simülasyonu eğitimi](attack-simulation-training-get-started.md) veya üçüncü taraf bir ürün kullanıyorsanız, bu makalenin önceki bölümlerinde kullanıcı gönderimleri posta kutusu yapılandırma gereksinimleri bölümünde daha önce açıklandığı gibi [kullanıcı gönderimleri posta kutusunu SecOps posta kutusu](#configuration-requirements-for-the-user-submissions-mailbox) olarak yapılandırmanız gerekir. Bunu yapmazsanız, ileti bildiren bir kullanıcı kimlik avı simülasyonu ürününde eğitim atamasını tetikleyebilir.

  Seçiminizden bağımsız olarak, **bildirilen iletileri gönder** bölümünde aşağıdaki ayarlar da kullanılabilir:

  - **Kullanıcıların raporlamak isteyip istemediklerini seçmesine izin ver**: Bu ayar, **Kullanıcıların kullanabileceği raporlama seçeneklerini seçin bölümünde bulunan seçenekleri** denetler:

    - **Kullanıcıların, rapor vermek isteyip istemediklerini seçmesine izin verin** : **Kullanıcıların kullanabileceği raporlama seçeneklerini seçin bölümünde ayarların** bazılarını, tümünü veya hiçbirini seçebilirsiniz.
    - **Kullanıcıların rapor seçmek isteyip istemediklerini seçmesine izin verin** : **Kullanıcılar için kullanılabilir raporlama seçeneklerini belirleyin** bölümünde yalnızca bir ayar seçebilirsiniz.

    - **Kullanıcılar tarafından kullanılabilen raporlama seçeneklerini** belirleyin bölümü:
      - **İletiyi göndermeden önce sor**
      - **İletiyi her zaman bildir**
      - **İletiyi hiçbir zaman bildirmeyin**

- **Kullanıcı raporlama deneyimi** bölümü: Aşağıdaki ayarlar kullanılabilir:

  Sayfada gösterildiği gibi, bildirilen iletileri Microsoft'a gönderen bir seçenek seçerseniz bildirime aşağıdaki metin de eklenir:

  > E-postanız analiz için Olduğu gibi Microsoft'a gönderilir. Bazı e-postalar kişisel veya hassas bilgiler içerebilir.

  - **Raporlamadan önce** sekmesi: **Başlık** ve **İleti gövdesi** kutularına, rapor iletisi eklentisini veya Rapor Kimlik Avı eklentisini kullanarak bir iletiyi bildirmeden önce kullanıcıların gördüğü açıklayıcı metni girin. Gönderi türünü (gereksiz, gereksiz değil, kimlik avı vb.) dahil etmek için değişkenini `%type%` kullanabilirsiniz.
  - **Raporlamadan sonra** sekmesi: **Başlık** ve **Onay ileti** kutularına, kullanıcıların Rapor İletisi eklentisini veya Rapor Kimlik Avı eklentisini kullanarak bir iletiyi bildirdikten sonra görecekleri açıklayıcı metni girin. Gönderim türünü eklemek için değişkenini `%type%` kullanabilirsiniz.

  - **Yalnızca kullanıcı kimlik avı bildirdiğinde görüntüle**: **Raporlamadan önce** ve **Raporlamadan sonra** bildirimlerini yalnızca kullanıcılar iletileri kimlik avı olarak bildirdiğinde görüntülemek için bu seçeneği belirleyin. Aksi takdirde, bildirilen tüm iletiler için bildirimler gösterilir.

- **Yönetici gözden geçirme sonuçları bölümü için Email bildirimleri**: Aşağıdaki ayarlar kullanılabilir:

  - **Gönderen olarak kullanılacak Office 365 e-posta adresini belirtin**: Bu ayarı seçin ve görüntülenen kutuya e-posta adresini girin.
  
  - **Bildirimleri özelleştirme**: Yönetici tarafından incelenip bildirilen iletileri işaretledikten sonra gönderilen e-posta bildirimini özelleştirmek için bu bağlantıya tıklayın.

    Görüntülenen **Onay iletisini özelleştir** açılır penceresinde aşağıdaki ayarları yapılandırın:

    - **Kimlik avı**, **Gereksiz** ve **Tehdit bulunamadı sekmeleri** : Sekmelerden bazılarının, hiçbirinin veya tümünün **Gözden geçirme sonucu metninde** , kullanılacak özel metni girin.
    - **Alt Bilgi** sekmesi: Aşağıdaki seçenekler kullanılabilir:
      - **Alt bilgi metni**: Kullanılacak özel ileti alt bilgisi metnini girin.
      - **Şirket logosunu görüntüle**: Bu seçeneği belirlemeden önce, özel logonuzu karşıya yüklemek [için Microsoft 365 temasını kuruluşunuz için özelleştirme](../../admin/setup/customize-your-organization-theme.md) başlığı altındaki yönergeleri izlemeniz gerekir.

  **Onayı özelleştir iletisi** açılır öğesinde işiniz bittiğinde **Onayla'ya** tıklayın.

- **Karantinadaki olası tehditleri bildirirken kuruluşunuzun deneyimini özelleştirin** bölümü:

  **Rapor iletisini karantinaya al düğmesi**: Bu ayarın **Açık** ![İki Durumlu Düğme'nin açık olduğunu doğrulayın.](../../media/scc-toggle-on.png) kullanıcıların karantinadan gelen iletileri bildirmesine izin vermek için. Aksi takdirde, bu ayarı **Kapat** ![İki durumlu düğmeyi kapat..](../../media/scc-toggle-off.png).

**Kullanıcı gönderimleri** sayfasında işiniz bittiğinde **Kaydet'e** tıklayın. Ayarları hemen önceki değerlerine geri yüklemek için **Geri Yükle'ye** tıklayın.

### <a name="third-party-reporting-tools-options"></a>Üçüncü taraf raporlama araçları seçenekleri

Bildirilen iletileri kullanıcı gönderimleri posta kutusuna göndermek için üçüncü taraf ileti raporlama araçlarını kullanmak için Microsoft tümleşik raporlama deneyimini kapatabilirsiniz.

Tek gereksinim, özgün iletilerin sıkıştırılmamış olarak eklenmesidir. EML veya . Kullanıcı gönderimleri posta kutusuna gönderilen iletilerdeki MSG ekleri. Başka bir deyişle, özgün iletileri yalnızca kullanıcı gönderimleri posta kutusuna iletmeyin.

> [!NOTE]
> İletide birden çok e-posta eki varsa gönderim atılır. İletiyi yalnızca bir e-posta eki ile destekleriz.

İleti biçimlendirme gereksinimleri sonraki bölümde açıklanmıştır. Biçimlendirme isteğe bağlıdır, ancak bildirilen iletiler belirtilen biçime uymaz, bildirilen iletiler her zaman kimlik avı olarak tanımlanır.

**Microsoft Outlook Rapor İletisi düğmesi** **KapalıYken** ![Geçiş Düğmesi kapalıdır.](../../media/scc-toggle-off.png) Kullanıcı **gönderimleri** sayfasında aşağıdaki ayarlar kullanılabilir:

- **Microsoft ve kuruluşumun posta kutusu**: Görüntülenen kutuya, kullanıcı posta kutusunu gönderdiğinde kullanılacak mevcut bir Exchange Online posta kutusunun e-posta adresini girin. Dağıtım gruplarına izin verilmez.

- **Karantinadaki olası tehditleri bildirirken kuruluşunuzun deneyimini özelleştirin** bölümü:

  **Rapor iletisini karantinaya al düğmesi**: Bu ayarın **Açık** ![İki Durumlu Düğme'nin açık olduğunu doğrulayın.](../../media/scc-toggle-on.png) kullanıcıların karantinadan gelen iletileri bildirmesine izin vermek için. Aksi takdirde, bu ayarı **Kapat** ![İki durumlu düğmeyi kapat..](../../media/scc-toggle-off.png).

**Kullanıcı gönderimleri** sayfasında işiniz bittiğinde **Kaydet'e** tıklayın. Ayarları hemen önceki değerlerine geri yüklemek için **Geri Yükle'ye** tıklayın.

#### <a name="message-submission-format"></a>İleti gönderme biçimi

Özgün ekli iletileri doğru şekilde tanımlamak için özel posta kutusuna gönderilen iletiler belirli bir biçimlendirme gerektirir. İletiler bu biçimi kullanmıyorsa, özgün eklenen iletiler her zaman kimlik avı olarak tanımlanır.

Özgün eklenen iletilerin bildirilme nedenini belirtmek için, kullanıcı gönderimleri posta kutusuna gönderilen iletilerin aşağıdaki ölçütlere uyması gerekir:

- Özgün ileti eki değiştirilmedi.
- Kullanıcı gönderimleri posta kutusuna gönderilen iletilerin Konu satırı (Zarf Başlığı) aşağıdaki ön ek değerlerinden biriyle başlamalıdır:
  - `1|`veya .`Junk:`
  - `2|`veya .`Not junk:`
  - `3|`veya .`Phishing:`

  Örneğin:

  - `3|This text in the Subject line is ignored by the system`
  - `Not Junk:This text in the Subject line is also ignored by the system`

  Bu biçimi izlemeyen iletiler, konumundaki <https://security.microsoft.com/reportsubmission>**Gönderimler** sayfasında düzgün görüntülenmez.

## <a name="use-exchange-online-powershell-to-configure-the-user-submissions-mailbox-for-email"></a>Exchange Online PowerShell kullanarak e-posta için kullanıcı gönderimleri posta kutusunu yapılandırma

[Exchange Online PowerShell'e bağlandıktan](/powershell/exchange/connect-to-exchange-online-powershell) sonra, kullanıcı gönderimleri posta kutusunu ve ilgili ayarları yönetmek ve **\*yapılandırmak için -ReportSubmissionPolicy ve -ReportSubmissionRule** cmdlet'lerini kullanırsınız **\***.

Exchange Online PowerShell'de, kullanıcı gönderme posta kutusu ayarlarının temel öğeleri şunlardır:

- **Rapor gönderme ilkesi**: Microsoft tümleşik raporlama deneyimini açar veya kapatır, Bildirilen iletilerin Microsoft'a gönderilmesini açar veya kapatır, bildirilen iletilerin kullanıcıya gönderilen posta kutusuna gönderilmesini açar veya kapatır ve diğer ayarların çoğu.
- **Rapor gönderme kuralı**: Kullanıcının posta kutusu göndermesinin e-posta adresini veya kullanıcı posta kutusu kullanılmadığında boş bir değer belirtir (yalnızca Microsoft'a ileti gönder).

Microsoft 365 Defender portalında kullanıcı gönderimleri posta kutusu ayarlarını yönettiğinizde bu iki öğe arasındaki fark belirgin değildir:

- Varsayılan olarak DefaultReportSubmissionPolicy adlı yalnızca rapor gönderme ilkesi ve DefaultReportSubmissionRule adlı bir rapor gönderme kuralı vardır.

  'a <https://security.microsoft.com/userSubmissionsReportMessage>hiç gitmediyseniz rapor gönderme ilkesi veya rapor gönderme kuralı yoktur (Get-ReportSubmissionPolicy ve Get-ReportSubmissionRule cmdlet'leri hiçbir şey döndürmez).

  Ziyaret ettiğiniz <https://security.microsoft.com/userSubmissionsReportMessage> anda ve ayarları yapılandırmadan önce bile rapor gönderme ilkesi varsayılan değerlerle oluşturulur ve PowerShell'de görünür.

  Kullanıcı gönderimleri posta kutusunu (Microsoft tümleşik raporlama deneyimi veya üçüncü taraf araçları) belirtmek için konumundaki <https://security.microsoft.com/userSubmissionsReportMessage> ayarları yapılandırıp kaydettikten sonra, DefaultReportSubmissionRule adlı rapor gönderme kuralı otomatik olarak oluşturulur. Kuralın PowerShell'de görünmesi birkaç saniye sürer.

- Rapor gönderme kuralını silebilir ve farklı bir adla yeniden oluşturabilirsiniz, ancak kural her zaman adını değiştiremezseniz rapor gönderme ilkesiyle ilişkilendirilir. Bu nedenle, kuralı her oluşturduğunuzda veya yeniden oluşturduğunuzda kuralı DefaultReportSubmissionRule olarak adlandırmanızı öneririz.

- Microsoft 365 Defender portalında kullanıcı gönderimleri posta kutusunun e-posta adresini belirttiğinizde, bu değer öncelikli olarak rapor gönderme kuralında ayarlanır, ancak değer rapor gönderme ilkesindeki ilgili özelliklere de kopyalanır. PowerShell'de, kuralda e-posta adresini ayarladığınızda, değer ilkedeki ilgili özelliklere kopyalanır. Microsoft 365 Defender portalıyla tutarlılık sağlamak ve netlik sağlamak için ilkeye ve kurala e-posta adresini eklemenizi veya güncelleştirmenizi öneririz.

### <a name="use-powershell-to-view-the-report-submission-policy-and-the-report-submission-rule"></a>Rapor gönderme ilkesini ve rapor gönderme kuralını görüntülemek için PowerShell'i kullanma

Rapor gönderme ilkesini görüntülemek için PowerShell Exchange Online de aşağıdaki komutu çalıştırın:

```powershell
Get-ReportSubmissionPolicy
```

Rapor gönderme kuralını görüntülemek için aşağıdaki komutu çalıştırın:

```powershell
Get-ReportSubmissionRule
```

hem ilkeyi hem de kuralı aynı anda görüntülemek için aşağıdaki komutları çalıştırın:

```powershell
Write-Output -InputObject `r`n,"Report Submission Policy","-------------------------------------------------------------------------------------"; Get-ReportSubmissionPolicy; Write-Output -InputObject `r`n,"Report Submission Rule","-------------------------------------------------------------------------------------"; Get-ReportSubmissionRule
```

PowerShell'de rapor gönderme ilkesine veya rapor gönderme kuralına <https://security.microsoft.com/userSubmissionsReportMessage> hiç gitmediyseniz veya el ile oluşturmadıysanız, rapor gönderme ilkesi veya rapor gönderme kuralı olmadığını, dolayısıyla **Get-ReportSubmissionPolicy** ve **Get-ReportSubmissionRule** cmdlet'lerinin hiçbir şey döndürmediğini unutmayın.

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-ReportSubmissionPolicy](/powershell/module/exchange/get-reportsubmissionpolicy) ve [Get-ReportSubmissionRule](/powershell/module/exchange/get-reportsubmissionrule).

### <a name="use-powershell-to-create-the-report-submission-policy-and-the-report-submission-rule"></a>Rapor gönderme ilkesini ve rapor gönderme kuralını oluşturmak için PowerShell kullanma

**Get-ReportSubmissionPolicy** ve **Get-ReportSubmissionRule** cmdlet'leri çıkış döndürmezse, rapor gönderim ilkesini ve rapor gönderme kuralını oluşturabilirsiniz. Bunları zaten var olduklarında oluşturmaya çalışırsanız bir hata alırsınız.

Rapor gönderme ilkesini rapor gönderme kuralında belirttiğinizden, her zaman önce rapor gönderme ilkesini oluşturun.

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-ReportSubmissionPolicy](/powershell/module/exchange/new-reportsubmissionpolicy) ve [New-ReportSubmissionRule](/powershell/module/exchange/new-reportsubmissionrule).

#### <a name="use-powershell-to-enable-the-microsoft-integrated-reporting-experience-with-report-to-microsoft-only"></a>Yalnızca Microsoft'a raporla Microsoft tümleşik raporlama deneyimini etkinleştirmek için PowerShell'i kullanın

Bu örnek, varsayılan ayarlarla (ilk ziyaret <https://security.microsoft.com/userSubmissionsReportMessage>ettiğinizde olduğu gibi, ancak herhangi bir ayarı yapılandırmadan veya kaydetmeden önce aynı ayarlar) rapor gönderme ilkesini oluşturur:

- Microsoft tümleşik raporlama deneyimi açık: **Microsoft Outlook Rapor İletisi düğmesi** iki durumlu düğmesi: **Açık** ![Geçiş açık..](../../media/scc-toggle-on.png).

- Bildirilen iletileri yalnızca Microsoft'a **gönder: Bildirilen iletileri Microsoft'a** \> gönderin.

- Hiçbir kullanıcı gönderimi posta kutusu gerekmez veya belirtilmez, bu nedenle rapor gönderme kuralı oluşturulmaz.

```powershell
New-ReportSubmissionPolicy
```

#### <a name="use-powershell-for-the-microsoft-integrated-reporting-experience-with-report-to-microsoft-and-the-user-submissions-mailbox"></a>Microsoft'a rapor ve kullanıcı gönderme posta kutusu ile Microsoft tümleşik raporlama deneyimi için PowerShell'i kullanma

Bu örnek, aşağıdaki ayarlarla rapor gönderme ilkesini ve rapor gönderme kuralını oluşturur:

- Microsoft tümleşik raporlama deneyimi açık: **Microsoft Outlook Rapor İletisi düğmesi** iki durumlu düğmesi: **Açık** ![Geçiş açık..](../../media/scc-toggle-on.png). **New-ReportSubmissionPolicy** cmdlet'inde _EnableReportToMicrosoft_ parametresinin varsayılan değeri ve `$true` _EnableThirdPartyAddress_ parametresinin varsayılan değeri olur`$false`, bu nedenle bunları kullanmanız gerekmez.

- Bildirilen iletileri Microsoft'a gönderme ve kullanıcı gönderme posta kutusu: **Bildirilen iletileri Microsoft'a** \> **ve kuruluşumun posta kutusuna** gönderin:

  - **New-ReportSubmissionPolicy**: `-ReportJunkToCustomizedAddress $true -ReportJunkAddresses <emailaddress> -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses <emailaddress> -ReportPhishToCustomizedAddress $true -ReportPhishAddresses <emailaddress>`.
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  Bu örnekte, kullanıcı gönderimleri posta kutusunun e-posta adresi Exchange Online reportedmessages@contoso.com (dış e-posta adresi belirtemezsiniz).

  > [!NOTE]
  > Kullanıcı gönderimleri posta kutusunu tanımlayan tüm parametrelerde aynı e-posta adresi değerini kullanmanız gerekir.

Rapor gönderme ilkesini oluşturmak için kalan parametreler gereklidir. Bu örnekte varsayılan değerler kullanılır. Bu örnekte açıklandığı gibi varsayılan değerleri belirtmezseniz ek parametreler ve ayarlar gerekebilir:

- Kullanıcıların seçili (`-DisableUserSubmissionOptions $false`) **olarak rapor vermek isteyip istemediklerini seçmesine izin verin** ve **kullanıcılara sağlanan raporlama seçeneklerini seçin** seçenekleri seçilmez (varsayılan _UserSubmissionOptions_ parametre değeri `0` kullanılır).
- **Kullanıcı raporlama deneyimi** bölümü:
  - **Raporlamadan önce** veya **raporlamadan sonra** sekmelerindeki **Başlık** ve **İleti gövdesi** kutularına hiçbir şey girilir.`-EnableCustomizedMsg $false`
  - **Yalnızca kullanıcı kimlik avı** () seçeneğini bildirdiğinde`-OnlyShowPhishingDisclaimer $true` görüntülenir.
- **Yönetici gözden geçirme sonuçları bölümü için Email bildirimleri**:
  - Gönderenin seçilmediği (`-EnableCustomNotificationSender $false`) **olarak kullanılacak Office 365 e-posta adresini belirtin**.
  - **Bildirimleri özelleştir** bağlantısı \> **Onay** açılır \> **bilgisini özelleştir alt bilgi** sekmesi: **Seçili olmayan şirket logosunu** görüntüle (`-EnableOrganizationBranding $false`).
- **Karantinadaki olası tehditleri bildirirken kuruluşunuzun deneyimini özelleştirin** bölümü:

  **Rapor iletisini karantinaya al düğmesi** iki durumlu düğmesi: **Açık** ![Geçiş açık.](../../media/scc-toggle-on.png) (`-DisableQuarantineReportingOption $false`).

```powershell
$usersub = "reportedmessages@contoso.com"

New-ReportSubmissionPolicy -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub -DisableUserSubmissionOptions $false -EnableCustomizedMsg $false -OnlyShowPhishingDisclaimer $true -EnableCustomNotificationSender $false -EnableOrganizationBranding $false -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

#### <a name="use-powershell-for-the-microsoft-integrated-reporting-experience-with-report-to-the-user-submissions-mailbox-only"></a>Yalnızca kullanıcı gönderimleri posta kutusuna raporla Microsoft tümleşik raporlama deneyimi için PowerShell kullanın

Bu örnek, aşağıdaki ayarlarla rapor gönderme ilkesini ve rapor gönderme kuralını oluşturur:

- Microsoft tümleşik raporlama deneyimi açık: **Microsoft Outlook Rapor İletisi düğmesi** iki durumlu düğmesi: **Açık** ![Geçiş açık..](../../media/scc-toggle-on.png). **New-ReportSubmissionPolicy** cmdlet'inde: `-EnableReportToMicrosoft $false`. _EnableThirdPartyAddress_ parametresinin varsayılan değeri olur`$false`, bu nedenle kullanmanız gerekmez.

- Bildirilen iletileri yalnızca kullanıcı gönderimleri posta kutusuna gönder: **Bildirilen iletileri** **Kuruluşlarım posta kutusuna**\> gönderin:

  - **New-ReportSubmissionPolicy**: `-ReportJunkToCustomizedAddress $true -ReportJunkAddresses <emailaddress> -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses <emailaddress> -ReportPhishToCustomizedAddress $true -ReportPhishAddresses <emailaddress>`.
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  Bu örnekte, kullanıcı gönderimleri posta kutusunun e-posta adresi Exchange Online userreportedmessages@fabrikam.com (dış e-posta adresi belirtemezsiniz).

  > [!NOTE]
  > Kullanıcı gönderimleri posta kutusunu tanımlayan tüm parametrelerde aynı e-posta adresi değerini kullanmanız gerekir.

Önceki örnekte olduğu gibi, rapor gönderme ilkesini oluşturmak için kalan parametrelerin aynısı gereklidir. Önceki örnekte olduğu gibi, bu parametrelerin varsayılan değerleri de kullanılır:

```powershell
$usersub = "userreportedmessages@fabrikam.com"

New-ReportSubmissionPolicy -EnableReportToMicrosoft $false -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub -DisableUserSubmissionOptions $false -EnableCustomizedMsg $false -OnlyShowPhishingDisclaimer $true -EnableCustomNotificationSender $false -EnableOrganizationBranding $false -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

#### <a name="use-powershell-for-third-party-reporting-tools"></a>Üçüncü taraf raporlama araçları için PowerShell kullanma

Bu örnek, aşağıdaki ayarlarla rapor gönderme ilkesini ve rapor gönderme kuralını oluşturur:

- Microsoft tümleşik raporlama deneyimi kapalı: **Microsoft Outlook Rapor İletisi düğmesi** iki durumlu düğmesi: **Kapalı** ![Geçiş kapalı.](../../media/scc-toggle-off.png). **New-ReportSubmissionPolicy** cmdlet'inde: `-EnableReportToMicrosoft $false -EnableThirdPartyAddress $true`.

- Kullanıcı gönderimleri posta kutusunun e-posta adresini belirtmek için aşağıdaki parametreleri kullanın:

  - **New-ReportSubmissionPolicy**: `-ThirdPartyReportAddresses <emailaddress>`
  - **Set-ReportSubmissionRule**: `SentTo <emailaddress>`.

  Bu örnekte, kullanıcı gönderimleri posta kutusunun e-posta adresi Exchange Online thirdpartyreporting@wingtiptoys.com (dış e-posta adresi belirtemezsiniz)

  > [!NOTE]
  > Kullanıcı gönderimleri posta kutusunu tanımlayan tüm parametrelerde aynı e-posta adresi değerini kullanmanız gerekir.

Rapor gönderme ilkesinin başarıyla oluşturulması için kalan parametreler gereklidir. Bu örnekte varsayılan değerler kullanılır. Microsoft tümleşik raporlama deneyimini kapattığınızda rapor gönderme ilkesinde başka seçenek yoktur:

- **Karantinadaki olası tehditleri bildirirken kuruluşunuzun deneyimini özelleştirin** bölümü:

  **Rapor iletisini karantinaya al düğmesi** iki durumlu düğmesi: **Açık** ![Geçiş açık.](../../media/scc-toggle-on.png) (`-DisableQuarantineReportingOption $false`).

```powershell
$usersub = "thirdpartyreporting@wingtiptoys.com"

New-ReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $true -ThirdPartyReportAddresses $usersub -DisableQuarantineReportingOption $false

New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
```

### <a name="use-powershell-to-modify-the-report-submission-policy-and-the-report-submission-rule"></a>Rapor gönderme ilkesini ve rapor gönderme kuralını değiştirmek için PowerShell kullanma

PowerShell'de rapor gönderme ilkesini değiştirdiğinizde, [ilkeyi oluştururken önceki bölümde](#use-powershell-to-create-the-report-submission-policy-and-the-report-submission-rule) açıklandığı gibi aynı ayarlar kullanılabilir. Önemli fark şudur: İlkeyi oluşturmak için gereken ek parametreler (örneğin, _DisableQuarantineReportingOption_) uzun süre gerekli değildir. Ancak, daha önce yapılandırdığınız veya yapılandırmadığınız bazı önemli ayarları geri almak veya geçersiz kılmak zorunda olabilirsiniz. Ayrıca, bir kullanıcı gönderimi posta kutusuna raporlamaya izin vermek veya bunu önlemek için rapor gönderme kuralını oluşturmanız veya silmeniz gerekebilir.

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-ReportSubmissionPolicy](/powershell/module/exchange/set-reportsubmissionpolicy).

Aşağıdaki örneklerde, mevcut ayarlar veya değerler için endişe duymadan kullanıcı raporlama deneyiminin nasıl değiştireceği gösterilir:

- **Microsoft tümleşik raporlama deneyimi \> raporunu yalnızca Microsoft olarak** değiştirin:

  ```powershell
   Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $true -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $false -ReportJunkAddresses $null -ReportNotJunkToCustomizedAddress $false -ReportNotJunkAddresses $null -ReportPhishToCustomizedAddress $false -ReportPhishAddresses $null

  Get-ReportSubmissionRule | Remove-ReportSubmissionRule
  ```

- **Microsoft tümleşik raporlama deneyimi \> raporunu Microsoft'a ve kullanıcının posta kutusunu göndermesine** (örneğin, reportedmessages@contoso.com) değiştirin:

  ```powershell
  $usersub = "reportedmessages@contoso.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $true -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub
  ```

  Aşağıdaki komut yalnızca rapor gönderme kuralına sahip değilseniz gereklidir:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

- **Microsoft tümleşik raporlama deneyimi \> raporuna yalnızca kullanıcı gönderileri posta kutusu** (örneğin, userreportedmessages@fabrikam.com) olarak değiştirin:

  ```powershell
  $usersub = "userreportedmessages@fabrikam.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $false -ThirdPartyReportAddresses $null -ReportJunkToCustomizedAddress $true -ReportJunkAddresses $usersub -ReportNotJunkToCustomizedAddress $true -ReportNotJunkAddresses $usersub -ReportPhishToCustomizedAddress $true -ReportPhishAddresses $usersub
  ```

  Aşağıdaki komut yalnızca rapor gönderme kuralına sahip değilseniz gereklidir:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

- **Üçüncü taraf raporlama araçlarına** (örneğin, thirdpartyreporting@wingtiptoys.com) değiştirin:

  ```powershell
  $usersub = "thirdpartyreporting@wingtiptoys.com"

  Set-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy -EnableReportToMicrosoft $false -EnableThirdPartyAddress $true -ThirdPartyReportAddresses $usersub -ReportJunkToCustomizedAddress $false -ReportJunkAddresses $null -ReportNotJunkToCustomizedAddress $false -ReportNotJunkAddresses $null -ReportPhishToCustomizedAddress $false -ReportPhishAddresses $null
  ```

  Aşağıdaki komut yalnızca rapor gönderme kuralına sahip değilseniz gereklidir:

  ```powershell
  New-ReportSubmissionRule -Name DefaultReportSubmissionRule -ReportSubmissionPolicy DefaultReportSubmissionPolicy -SentTo $usersub
  ```

Rapor gönderme kuralında değiştirebileceğiniz tek anlamlı ayar, kullanıcı gönderimleri posta kutusunun e-posta adresidir ( _SentTo_ parametre değeri). Örneğin:

```powershell
Get-ReportSubmissionRule | Set-ReportSubmissionRule -SentTo newemailaddress@contoso.com
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-ReportSubmissionRule](/powershell/module/exchange/set-reportsubmissionrule).

Kullanıcı gönderimleri posta kutusuna e-posta iletileri göndermeyi (Microsoft tümleşik raporlama deneyimi veya üçüncü taraf araçları) rapor gönderme kuralını değiştirmeden geçici olarak devre dışı bırakmak için [Disable-ReportSubmissionRule](/powershell/module/exchange/disable-reportsubmissionrule) kullanın. Örneğin:

```powershell
Get-ReportSubmissionRule | Disable-ReportSubmissionRule -Confirm:$false
```

Rapor gönderme kuralını yeniden etkinleştirmek için [Enable-ReportSubmissionRule](/powershell/module/exchange/enable-reportsubmissionrule) komutunu kullanın. Örneğin:

```powershell
Get-ReportSubmissionRule | Disable-ReportSubmissionRule -Confirm:$false
```

### <a name="use-powershell-to-remove-the-report-submission-policy-and-the-report-submission-rule"></a>Rapor gönderme ilkesini ve rapor gönderme kuralını kaldırmak için PowerShell'i kullanma

Rapor gönderme ilkesinin varsayılan ayarlarıyla baştan başlamak için, bu ilkeyi silebilir ve yeniden oluşturabilirsiniz. Rapor gönderme ilkesinin kaldırılması rapor gönderme kuralını kaldırmaz ve tam tersi de geçerlidir.

Rapor gönderme ilkesini kaldırmak için PowerShell Exchange Online de aşağıdaki komutu çalıştırın:

```powershell
Remove-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy
```

Rapor gönderme kuralını kaldırmak için aşağıdaki komutu çalıştırın:

```powershell
Get-ReportSubmissionRule | Remove-ReportSubmissionRule
```

Aynı komuttaki hem rapor gönderme ilkesini hem de rapor gönderme kuralını istem olmadan kaldırmak için aşağıdaki komutu çalıştırın:

```powershell
Remove-ReportSubmissionPolicy -Identity DefaultReportSubmissionPolicy; Get-ReportSubmissionRule | Remove-ReportSubmissionRule -Confirm:$false
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-ReportSubmissionPolicy](/powershell/module/exchange/remove-reportsubmissionpolicy) ve [Remove-ReportSubmissionRule](/powershell/module/exchange/remove-reportsubmissionrule).
