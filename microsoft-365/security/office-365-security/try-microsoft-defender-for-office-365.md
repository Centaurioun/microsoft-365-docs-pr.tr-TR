---
title: Office 365 için Defender değerlendirmeyi deneyin
description: Mevcut posta akışınızı etkilemeden Office 365 için Microsoft Defender özelliklerini değerlendirmeyi ve denemeyi öğrenin.
keywords: ''
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ROBOTS: ''
ms.openlocfilehash: ad8c15ef0b5dc56d2df8455341f8bf5e4e6efd94
ms.sourcegitcommit: c6f1486617b39565bfd8f662ee6ad65a9cefd3e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66862099"
---
# <a name="try-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender deneyin

Microsoft 365 Defender portalındaki birleşik **Denemeler** portalı, Office 365 için Microsoft Defender için eski ayrı Deneme ve Değerlendirme deneyimleri için tek bir giriş noktası sağlar. Amaç, Office 365 için Defender Plan 2'nin özelliklerini tam olarak işlemeden önce 90 gün boyunca denemenize olanak sağlamaktır. Ancak değerlendirme deneyimlerinde Microsoft 365 kuruluşunuzun doğasına göre farklılıklar vardır:

- Microsoft 365 posta kutularınız zaten var, ancak şu anda e-posta koruması için üçüncü taraf bir hizmet veya cihaz kullanıyorsunuz. İnternet'ten gelen postalar, Microsoft 365 kuruluşunuza teslim etmeden önce koruma hizmeti aracılığıyla akar. Microsoft 365 koruması mümkün olduğunca düşüktür (hiçbir zaman tamamen kapalı değildir; örneğin, kötü amaçlı yazılım koruması her zaman uygulanır).

  ![Microsoft 365'e teslim etmeden önce İnternet'ten üçüncü taraf koruma hizmeti veya cihazı aracılığıyla posta akışları.](../../media/mdo-migration-before.png)

  Bu ortamlarda yalnızca *denetim* modunda Office 365 için Defender deneyebilirsiniz. Office 365 için Defender denemek için posta akışınızı (MX kayıtları) değiştirmeniz gerekmez.

- Zaten bir Microsoft 365 kuruluşunuz var. İnternet'ten gelen postalar doğrudan Microsoft 365'e akar, ancak geçerli aboneliğinizde yalnızca [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) veya [Plan 1 Office 365 için Defender](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) vardır.

  ![EOP ve/veya Office 365 için Defender Plan 1'e karşı koruma ile posta İnternet'ten Microsoft 365'e akar.](../../media/mdo-trial-mail-flow.png)

  Bu ortamlarda, *denetim* modunda veya *engelleme* modunda Office 365 için Defender deneyebilirsiniz.

Deneme sürümünüzü adresinden Microsoft 365 Defender portalındaki <https://security.microsoft.com>çeşitli Office 365 için Defender özellik konumlarında başlatmaya davet edildiniz. Denemenizi başlatmak için merkezi konum konumundaki **Denemeler** sayfasındadır <https://security.microsoft.com/atpEvaluation>.

Office 365 için Microsoft Defender ile daha kısa sürede daha fazlasını nasıl yapabileceğiniz hakkında daha fazla bilgi edinmek için bu kısa videoyu izleyin.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWMmIe]

Bu makalenin geri kalanında denetim modu engelleme modu, değerlendirmeleri yapılandırma ve diğer ayrıntılar arasındaki fark açıklanmaktadır.

Deneme sürümünüzü kullanma hakkında yardımcı kılavuz için bkz[. Deneme playbook'u: Office 365 için Microsoft Defender](trial-playbook-defender-for-office-365.md).

## <a name="overview-of-defender-for-office-365"></a>Office 365 için Defender genel bakış

Office 365 için Defender, kuruluşların kapsamlı bir yetenekler sunarak kuruluşlarının güvenliğini sağlamalarına yardımcı olur. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender](defender-for-office-365.md).

Ayrıca bu [etkileşimli kılavuzda](https://aka.ms/MS365D.InteractiveGuide) Office 365 için Defender hakkında daha fazla bilgi edinebilirsiniz.

![kavramsal diyagramı Office 365 için Microsoft Defender.](../../media/microsoft-defender-for-office-365.png)

## <a name="policies-in-blocking-mode-or-audit-mode"></a>Engelleme modunda veya denetim modunda ilkeler

Office 365 için Defender değerlendirdiğinizde, Microsoft 365'teki koruma özelliklerini denetleye ilkeler bulunur:

- **Exchange Online Protection (EOP)**: Yeni veya özel ilke oluşturulmaz. Var olan EOP ilkeleri iletiler üzerinde işlem yapabilir (örneğin, gereksiz Email klasörüne ileti gönderebilir veya karantinaya alıyabiliyor):

  - [Kötü amaçlı yazılımdan koruma ilkeleri](anti-malware-protection.md)
  - [Gelen istenmeyen posta önleme koruması](anti-spam-protection.md)
  - [Kimlik avı önleme ilkelerinde kimlik sahtekarlığı önleme koruması](set-up-anti-phishing-policies.md#spoof-settings)

  Bu özellikler için varsayılan ilkeler her zaman açıktır, tüm alıcılara uygulanır ve her zaman en son uygulanır (herhangi bir özel ilkeden sonra).

- **Office 365 için Defender**: Office 365 için Defender özel ilkeler, Office 365 için Defender değerlendirmeniz için oluşturulur:

  - [Kimlik avı önleme ilkelerinde kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [E-posta iletileri için Güvenli Ekler](safe-attachments.md)
  - [E-posta iletileri ve Microsoft Teams için Güvenli Bağlantılar](safe-links.md)

  Ancak, bu ilkelerin yapısı engelleme modunda ve denetim modunda farklıdır:

  - **Denetim modu**: Normal ilkeler oluşturulur, ancak ilkeler yalnızca tehditleri *algılamak* için yapılandırılır. Office 365 için Defender, raporlama için zararlı iletileri algılar, ancak iletiler üzerinde işlem gerçekleştirilmiyor (örneğin, algılanan iletiler karantinaya alınmıyor).

  - **Engelleme modu**: İlkeler [, önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md) için Standart şablon kullanılarak oluşturulur. Office 365 için Defender zararlı iletileri *algılar* ve *üzerinde işlem uygular* (örneğin, algılanan iletiler karantinaya alınır).

  Varsayılan ve önerilen seçim, bu Office 365 için Defender ilkelerini kuruluştaki tüm kullanıcılara kapsamaktır. Ancak kurulum sırasında veya sonrasında ilke atamasını belirli kullanıcılara, gruplara veya e-posta etki alanlarına değiştirebilirsiniz.

**Notlar**:

- Güvenli Bağlantılar, posta akışında URL'leri patlatacaktır. Belirli URL'lerin patlamasını önlemek için Kiracı İzin Ver/Engelle Listesini kullanın. Daha fazla bilgi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](tenant-allow-block-list.md).
- Güvenli Bağlantılar, e-posta iletisi gövdelerindeki URL bağlantılarını sarmalamaz.
- Değerlendirme ilkesi ayarları, bu makalenin devamında yer alan [Değerlendirme ilkesi ayarları](#evaluation-policy-settings) bölümünde açıklanmıştır.

## <a name="set-up-an-evaluation-in-audit-mode"></a>Denetim modunda değerlendirme ayarlama

1. **Değerlendirmeyi başlat'a** tıklayın.

2. **Korumayı aç** iletişim kutusunda **Hayır, yalnızca raporlamak istiyorum'u** seçin ve **ardından Devam'a** tıklayın.

3. **Eklemek istediğiniz kullanıcıları seçin** iletişim kutusunda aşağıdaki ayarları yapılandırın:

   - **Tüm kullanıcılar**: Bu varsayılan ve önerilen seçenektir.
   - **Kullanıcıları seçin**: Bu seçeneği belirlerseniz, değerlendirmenin geçerli olduğu iç alıcıları seçmeniz gerekir:
     - **Kullanıcılar**: Belirtilen posta kutuları, posta kullanıcıları veya posta kişileri.
     - **Gruplar**:
       - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
       - Belirtilen Microsoft 365 Grupları.
       - **Etki alanları**: Kuruluşunuzda belirtilen [kabul edilen etki alanlarındaki](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) tüm alıcılar.

     Uygun kutuya tıklayın, bir değer yazmaya başlayın ve sonuçlardan istediğiniz değeri seçin. Bu işlemi gerektiği kadar tekrarlayın. Mevcut bir değeri kaldırmak için Kaldır'a tıklayın ![Kaldır simgesi.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.

     Kullanıcılar veya gruplar için çoğu tanımlayıcıyı (ad, görünen ad, diğer ad, e-posta adresi, hesap adı vb.) kullanabilirsiniz, ancak sonuçlarda ilgili görünen ad gösterilir. Kullanıcılar için, tüm kullanılabilir değerleri görmek için tek başına bir yıldız işareti (\*) girin.

   > [!NOTE]
   > Değerlendirmeyi ayarlamayı tamamladıktan sonra bu seçimleri değiştirebilirsiniz.

   İşiniz bittiğinde **Devam'a** tıklayın.

4. **Posta akışınızı anlamamıza yardımcı olun** iletişim kutusunda aşağıdaki seçenekleri yapılandırın:

   - **Microsoft ile veri paylaşma**: Bu seçenek varsayılan olarak seçilidir, ancak isterseniz onay kutusunu temizleyebilirsiniz.

   - Etki alanınız için MX kaydını algılamamıza bağlı olarak aşağıdaki seçeneklerden biri otomatik olarak seçilir:

     - **Üçüncü taraf ve/veya şirket içi hizmet sağlayıcısı kullanıyorum**: Microsoft 365 dışında bir yerde etki alanınızın MX kaydı. Bu seçim **, İleri'ye** tıkladıktan sonra aşağıdaki ek ayarları gerektirir:

       1. **Üçüncü taraf veya şirket içi ayarlar** iletişim kutusunda aşağıdaki ayarları yapılandırın:

          - **Bir üçüncü taraf hizmet sağlayıcısı seçin**: Aşağıdaki değerlerden birini seçin:
            - **Barracuda**
            - **IronPort**
            - **Mimecast**
            - **Yazım Denetleme Noktası**
            - **Sophos**
            - **Symantec**
            - **Trend Micro**
            - **Diğer**

          - **Bu değerlendirmenin uygulanacağı bağlayıcı**: Microsoft 365'e posta akışı için kullanılan bağlayıcıyı seçin.

            [Bağlayıcılar için Gelişmiş Filtreleme](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ( *liste atlama* olarak da bilinir) belirttiğiniz bağlayıcıda otomatik olarak yapılandırılır.

            Microsoft 365'in önünde üçüncü taraf bir hizmet veya cihaz durduğunda Bağlayıcılar için Gelişmiş Filtreleme, İnternet iletilerinin kaynağını doğru şekilde tanımlar ve Microsoft filtreleme yığınının doğruluğunu büyük ölçüde artırır (özellikle kimlik [sahtekarlığı zekası](anti-spoofing-protection.md) ve [Tehdit Gezgini](threat-explorer.md) ve [Otomatik Araştırma & Yanıtı(AIR)](automated-investigation-response-office.md)'daki ihlal sonrası özellikler).

          - **İletilerinizin geçtiği her ağ geçidi IP adresini listeleyin**: Bu ayar yalnızca **Üçüncü taraf bir hizmet sağlayıcısı seçin** için **Diğer'i** seçtiyseniz kullanılabilir. Microsoft 365'e posta göndermek için üçüncü taraf koruma hizmeti veya cihazı tarafından kullanılan IP adreslerinin virgülle ayrılmış bir listesini girin.

          İşiniz bittiğinde **İleri'ye** tıklayın.

       2. **Exchange posta akışı kuralları** iletişim kutusunda, üçüncü taraf koruma hizmetinden veya cihazından gelen iletiler için istenmeyen posta filtrelemeyi atlayan bir Exchange Online posta akışı kuralına (aktarım kuralı olarak da bilinir) ihtiyacınız olup olmadığını belirleyin.

          Exchange Online'de koruma hizmetinden gelen tüm postaların Microsoft 365 filtrelemesini atlamasına (çoğu) izin veren bir SCL=-1 posta akışı kuralınız olabilir. Birçok koruma hizmeti, hizmetlerini kullanan Microsoft 365 müşterileri için bu istenmeyen posta güven düzeyi (SCL) posta akışı kuralı yöntemini teşvik eder.

          Önceki adımda açıklandığı gibi, Bağlayıcılar için Gelişmiş Filtreleme, koruma hizmetinden posta kaynağı olarak belirttiğiniz bağlayıcıda otomatik olarak yapılandırılır.

          Koruma hizmetinden gelen postalar için SCL=-1 kuralı olmadan Bağlayıcılar için Gelişmiş Filtreleme özelliğinin etkinleştirilmesi, kimlik [sahtekarlık zekası](anti-spoofing-protection.md) gibi EOP koruma özelliklerinin algılama özelliklerini büyük ölçüde geliştirir ve yeni algılanan iletilerin teslimini etkileyebilir (örneğin, Gereksiz Email klasörüne veya karantinaya almak için). Bu etki EOP ilkeleriyle sınırlıdır; daha önce açıklandığı gibi, Office 365 için Defender ilkeleri denetim modunda oluşturulur.

          SCL=-1 posta akışı kuralı oluşturmak veya mevcut kurallarınızı gözden geçirmek için sayfadaki **Exchange yönetim merkezine git** düğmesine tıklayın. Daha fazla bilgi için bkz. [Exchange Online iletilerde istenmeyen posta güvenilirlik düzeyini (SCL) ayarlamak için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          İşiniz bittiğinde **Son'a** tıklayın.

     - **Yalnızca Microsoft Exchange Online kullanıyorum**: Etki alanınızın MX kayıtları Microsoft 365'e işaret etti. Yapılandıracak bir şey kalmadığından **Son'a** tıklayın.

5. Değerlendirmeniz ayarlanırken bir ilerleme durumu iletişim kutusu görüntülenir. Kurulum tamamlandığında **Bitti'ye** tıklayın.

## <a name="set-up-an-evaluation-in-blocking-mode"></a>Engelleme modunda değerlendirme ayarlama

1. **Değerlendirmeyi başlat'a** tıklayın.

2. **Korumayı aç** iletişim kutusunda **Evet, tehditleri engelleyerek kuruluşumu koru'yu** seçin ve **devam'a** tıklayın.

3. **Eklemek istediğiniz kullanıcıları seçin** iletişim kutusunda aşağıdaki ayarları yapılandırın:

   - **Tüm kullanıcılar**: Bu varsayılan ve önerilen seçenektir.
   - **Kullanıcıları seçin**: Bu seçeneği belirlerseniz, değerlendirmenin geçerli olduğu iç alıcıları seçmeniz gerekir:
     - **Kullanıcılar**: Belirtilen posta kutuları, posta kullanıcıları veya posta kişileri.
     - **Gruplar**:
       - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
       - Belirtilen Microsoft 365 Grupları.
     - **Etki alanları**: Kuruluşunuzda belirtilen [kabul edilen etki alanlarındaki](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) tüm alıcılar.

     Uygun kutuya tıklayın, bir değer yazmaya başlayın ve sonuçlardan istediğiniz değeri seçin. Bu işlemi gerektiği kadar tekrarlayın. Mevcut bir değeri kaldırmak için Kaldır'a tıklayın ![Kaldır simgesi.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.

     Kullanıcılar veya gruplar için çoğu tanımlayıcıyı (ad, görünen ad, diğer ad, e-posta adresi, hesap adı vb.) kullanabilirsiniz, ancak sonuçlarda ilgili görünen ad gösterilir. Kullanıcılar için, tüm kullanılabilir değerleri görmek için tek başına bir yıldız işareti (\*) girin.

   > [!NOTE]
   > Değerlendirmeyi ayarlamayı tamamladıktan sonra bu seçimleri değiştirebilirsiniz.

   İşiniz bittiğinde **Devam'a** tıklayın.

4. Değerlendirmeniz ayarlanırken bir ilerleme durumu iletişim kutusu görüntülenir. Kurulum tamamlandığında **Bitti'ye** tıklayın.

## <a name="reporting-in-audit-mode"></a>Denetim modunda raporlama

- [Tehdit koruması durum raporu](view-email-security-reports.md#threat-protection-status-report), aşağıdaki görünümlerde Office 365 için Defender göre algılamaları gösterir:
  - [Email Kötü Amaçlı Yazılıma göre verileri \> görüntüleme ve Algılama Teknolojisine göre grafik dökümü](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Algılama Teknolojisine göre kimlik avı ve grafik dökümünü Email \> verileri görüntüleme](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- [Tehdit Gezgini'nde](threat-explorer.md), Office 365 için Defender değerlendirmesi tarafından algılanan iletiler girişin ayrıntılarında aşağıdaki başlığı gösterir:

  ![İletideki bildirim başlığı, Office 365 için Defender değerlendirmesinin kötü amaçlı bir e-posta iletisi algıladığını gösterir.](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

konumundaki **Office 365 için Microsoft Defender değerlendirme** sayfası<https://security.microsoft.com/atpEvaluation>, değerlendirmedeki ilkeler için raporlamayı birleştirir:

- Kimlik avı önleme ilkelerinde kimliğe bürünme koruması
- Güvenli Bağlantılar
- Güvenli Ekler

Varsayılan olarak, grafikler son 30 güne ilişkin verileri gösterir, ancak Takvim simgesine tıklayarak ![tarih aralığını filtreleyebilirsiniz.](../../media/m365-cc-sc-add-internal-icon.png) **30 gün ve 30** günden az olan aşağıdaki ek değerler arasından seçim yapın:

- 24 saat
- 7 gün
- 14 gün
- Özel tarih aralığı

İndir simgesine tıklayabilirsiniz ![.](../../media/m365-cc-sc-download-icon.png) Grafik verilerini bir .csv dosyasına indirmek için **indirin**.

## <a name="required-permissions"></a>Gerekli izinler

Microsoft 365 için Defender değerlendirmesini ayarlamak için **Azure AD** gereken izinler aşağıdaki listede açıklanmıştır:

- **Değerlendirme oluşturma, değiştirme veya silme**: Güvenlik Yöneticisi veya Genel Yönetici.
- **Değerlendirme ilkelerini ve raporlarını görüntüleme**: Güvenlik Yöneticisi veya Güvenlik Okuyucusu.

Microsoft 365 Defender portalındaki Azure AD izinleri hakkında daha fazla bilgi için bkz. [Microsoft 365 Defender portalında Azure AD rolleri](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)

## <a name="evaluation-policy-settings"></a>Değerlendirme ilkesi ayarları

Değerlendirme için özel olarak oluşturulan Office 365 için Defender ayarları aşağıdaki tablolarda açıklanmıştır:

**Kimlik avı önleme değerlendirme ilkesi ayarları**:

|Ayar|Değer|
|---|---|
|Admindisplayname|Değerlendirme İlkesi|
|AuthenticationFailAction|MoveToJmf|
|Etkin|True|
|EnableFirstContactSafetyTips|False|
|EnableMailboxIntelligence|True|
|EnableMailboxIntelligenceProtection|True|
|EnableOrganizationDomainsProtection|False|
|EnableSimilarDomainsSafetyTips|False|
|EnableSimilarUsersSafetyTips|False|
|EnableSpoofIntelligence|True|
|EnableSuspiciousSafetyTip|False|
|EnableTargetedDomainsProtection|False|
|EnableTargetedUserProtection|False|
|EnableUnauthenticatedSender|True|
|EnableUnusualCharactersSafetyTips|False|
|EnableViaTag|True|
|Guıd|GUID değeri|
|ImpersonationProtectionState|El ile|
|Isdefault|False|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|Name|Değerlendirme İlkesi|
|PhishThresholdLevel|1|
|RecommendedPolicyType|Değerlendirme|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|||
|AntiPhishPolicyLevelDataList|Boş|
|AntiSpoofEnforcementType|Yüksek|
|AuthenticationSafetyTipText|Boş|
|AuthenticationSoftPassSafetyTipText|Boş|
|EnableAuthenticationSafetyTip|False|
|EnableAuthenticationSoftPassSafetyTip|False|
|İlke Etiketi|Boş|
|SimilarUsersSafetyTipsCustomText|Boş|
|TreatSoftPassAsAuthenticated|True|
|UnusualCharactersSafetyTipsCustomText|Boş|
|||
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|TargetedDomainsToProtect|{}|
|TargetedUsersToProtect|{}|

**Güvenli Ekler değerlendirme ilkesi ayarları**:

|Ayar|Değer|
|---|---|
|Eylem|İzin ver|
|ActionOnError|True|
|Admindisplayname|Değerlendirme İlkesi|
|ConfidenceLevelThreshold|80|
|Etkinleştirmek|True|
|EnableOrganizationBranding|False|
|Guıd|GUID değeri|
|IsBuiltInProtection|False|
|Isdefault|False|
|Name|Değerlendirme İlkesi|
|OperationMode|Gecikme|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Değerlendirme|
|Yönlendirme|False|
|RedirectAddress|{}|
|ScanTimeout|30|

**Güvenli Bağlantılar değerlendirme ilkesi ayarları**:

|Ayar|Değer|
|---|---|
|Admindisplayname|Değerlendirme İlkesi|
|AllowClickThrough|False|
|CustomNotificationText|Boş|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForTeams|True|
|Guıd|GUID değeri|
|IsBuiltInProtection|False|
|Isdefault|False|
|Isenabled|True|
|LocalizedNotificationTextList|{}|
|Name|"EvaluationPolicy"|
|RecommendedPolicyType|Değerlendirme|
|ScanUrls|True|
|TrackClicks|True|
|||
|DoNotAllowClickThrough|Boş|
|DoNotTrackUserClicks|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|True|
|ExcludedUrls|{}|
|WhiteListedUrls|Boş|
