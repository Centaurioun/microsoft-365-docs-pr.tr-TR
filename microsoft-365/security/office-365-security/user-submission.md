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
ms.openlocfilehash: e09b5f7d6f34ac1daa98430f1bc868b4ca644777
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276316"
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

Başlamadan önce, Exchange Online Protection ve Office 365 için Defender yapılandırmanız gerekir, böylece kullanıcı tarafından bildirilen iletiler aşağıdaki adımlarda açıklandığı gibi filtrelenmeden kullanıcı gönderimleri posta kutusuna teslim edilir:

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

  - **Microsoft**: Kullanıcı raporları analiz için doğrudan Microsoft'a gider. Yalnızca gönderen, alıcı, raporlayan ve kullanıcı raporlarından ileti ayrıntıları gibi meta veriler kiracı yöneticisine Microsoft 365 Defender portalı üzerinden sağlanır.

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
