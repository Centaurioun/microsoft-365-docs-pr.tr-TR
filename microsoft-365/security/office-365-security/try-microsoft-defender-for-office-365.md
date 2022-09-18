---
title: Office 365 için Defender değerlendirmeyi deneyin
description: Mevcut posta akışınızı etkilemeden Office 365 için Microsoft Defender özelliklerini değerlendirmeyi ve denemeyi öğrenin.
keywords: Try, Evaluate, Trial, Evaluation, Office 365 için Defender
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
ms.subservice: mdo
ms.service: microsoft-365-security
ROBOTS: ''
ms.openlocfilehash: 0dc389f498587c0895399c2a2f2eee4624e1ee3d
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799011"
---
# <a name="try-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender deneyin

Mevcut bir Microsoft 365 müşterisi olarak, Microsoft 365 Defender portalındaki <https://security.microsoft.com> **Denemeler** ve **Değerlendirme** sayfaları, satın almadan önce Office 365 için Microsoft Defender Plan 2'nin özelliklerini denemenize olanak sağlar.

Plan 2 Office 365 için Defender denemeden önce kendinize sormanız gereken bazı önemli sorular vardır:

- Office 365 için Defender Plan 2'nin benim için neler yapabileceğini pasif olarak gözlemlemek mi (*denetim*) yoksa Office 365 için Defender Plan 2'nin bulduğu (*engellenen*) sorunlarda doğrudan eyleme geçmesini mi istiyorum?
- Her iki durumda da, Office 365 için Defender Plan 2'nin benim için ne yaptığını nasıl anlayabilirim?
- Plan 2'yi Office 365 için Defender karar vermem gerekmeden önce ne kadar sürem var?

Bu makale, plan 2'yi kuruluşunuzun gereksinimlerine en uygun şekilde Office 365 için Defender denemeniz için bu soruları yanıtlamanıza yardımcı olur.

Deneme sürümünüzü kullanma hakkında yardımcı kılavuz için bkz[. Deneme playbook'u: Office 365 için Microsoft Defender](trial-playbook-defender-for-office-365.md).

## <a name="overview-of-defender-for-office-365"></a>Office 365 için Defender genel bakış

Office 365 için Defender, kuruluşların kapsamlı bir yetenekler sunarak kuruluşlarının güvenliğini sağlamalarına yardımcı olur. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender](defender-for-office-365.md).

Ayrıca bu [etkileşimli kılavuzda](https://aka.ms/MS365D.InteractiveGuide) Office 365 için Defender hakkında daha fazla bilgi edinebilirsiniz.

![kavramsal diyagramı Office 365 için Microsoft Defender.](../../media/microsoft-defender-for-office-365.png)

Office 365 için Microsoft Defender ile daha kısa sürede daha fazlasını nasıl yapabileceğiniz hakkında daha fazla bilgi edinmek için bu kısa videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMmIe]

## <a name="how-trials-and-evaluations-work-for-defender-for-office-365"></a>Office 365 için Defender için denemeler ve değerlendirmeler nasıl çalışır?

### <a name="policies"></a>İlkeler

Office 365 için Defender, Exchange Online posta kutularına sahip tüm Microsoft 365 kuruluşlarında bulunan Exchange Online Protection (EOP) özelliklerini ve Office 365 için Defender özel özellikleri içerir.

EOP ve Office 365 için Defender koruma özellikleri ilkeler kullanılarak uygulanır. **Office 365 için Defender özel ilkeler gerektiğinde sizin için oluşturulur**:

- [Kimlik avı önleme ilkelerinde kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [E-posta iletileri için Güvenli Ekler](safe-attachments.md)
- [E-posta iletileri ve Microsoft Teams için Güvenli Bağlantılar](safe-links.md)
  - Güvenli Bağlantılar, posta akışı sırasında URL'leri patlatıyor. Belirli URL'lerin patlamasını önlemek için Kiracı İzin Ver/Engelle Listesindeki URL'ler için izin ver girişlerini kullanın. Daha fazla bilgi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](manage-tenant-allow-block-list.md).
  - Güvenli Bağlantılar, e-posta iletisi gövdelerindeki URL bağlantılarını sarmalamaz.

Değerlendirme veya deneme için uygunluğunuz, zaten EOP'niz olduğu anlamına gelir. **Office 365 için Defender Plan 2 değerlendirmeniz veya denemeniz için yeni veya özel EOP ilkeleri oluşturulmaz**. Microsoft 365 kuruluşunuzdaki mevcut EOP ilkeleri iletiler üzerinde işlem yapabilir (örneğin, Önemsiz Email klasörüne ileti gönderebilir veya karantinaya alıyabilir):

- [Kötü amaçlı yazılımdan koruma ilkeleri](anti-malware-protection.md)
- [Gelen istenmeyen posta önleme koruması](anti-spam-protection.md)
- [Kimlik avı önleme ilkelerinde kimlik sahtekarlığı önleme koruması](set-up-anti-phishing-policies.md#spoof-settings)

Bu EOP özellikleri için varsayılan ilkeler her zaman açıktır, tüm alıcılara uygulanır ve herhangi bir özel ilkeden sonra her zaman en son uygulanır.

### <a name="audit-mode-vs-blocking-mode-for-defender-for-office-365"></a>Denetim modu ile Office 365 için Defender için engelleme modu karşılaştırması

Office 365 için Defender deneyiminizin etkin mi yoksa pasif mi olmasını istiyorsunuz? Şunlar arasından seçim yapabileceğiniz iki mod vardır:

- **Denetim modu**: Kimlik avı önleme (kimliğe bürünme koruması, Güvenli Ekler ve Güvenli Bağlantılar dahil) için özel *değerlendirme ilkeleri* oluşturulur. Bu değerlendirme ilkeleri yalnızca tehditleri *algılamak* için yapılandırılır. Office 365 için Defender, raporlama için zararlı iletileri algılar, ancak iletiler üzerinde işlem gerçekleştirilmiyor (örneğin, algılanan iletiler karantinaya alınmıyor). Bu değerlendirme ilkelerinin ayarları, bu makalenin devamında [denetim modunda ilkeler](#policies-in-audit-mode) bölümünde açıklanmaktadır.

  Denetim modu, konumundaki **Değerlendirme modu** sayfasında<https://security.microsoft.com/atpEvaluation> Office 365 için Defender tarafından algılanan tehditler için özelleştirilmiş raporlara erişim sağlar.

- **Engelleme modu**: [Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md) için Standart şablon açılır ve deneme sürümü için kullanılır ve deneme sürümüne dahil etmek için belirttiğiniz kullanıcılar Standart önceden ayarlanmış güvenlik ilkesine eklenir. Office 365 için Defender zararlı iletileri *algılar* ve *üzerinde işlem uygular* (örneğin, algılanan iletiler karantinaya alınır).

  Varsayılan ve önerilen seçim, bu Office 365 için Defender ilkelerini kuruluştaki tüm kullanıcılara kapsamaktır. Ancak deneme sürümünüzün kurulumu sırasında veya sonrasında, ilke atamasını Microsoft 365 Defender portalında veya Exchange Online [PowerShell'de](#policy-settings-associated-with-defender-for-office-365-trials) belirli kullanıcılara, gruplara veya e-posta etki alanlarına değiştirebilirsiniz.

  Engelleme modu, Office 365 için Defender tarafından algılanan tehditler için özelleştirilmiş raporlar sağlamaz. Bunun yerine, bilgiler Office 365 için Defender Plan 2'nin normal raporlarında ve araştırma özelliklerinde kullanılabilir.

E-postanın Microsoft 365 kuruluşunuza nasıl teslim edilmesi denetim modunda ve engelleme modunda önemli bir faktördür:

- İnternet'ten gelen postalar doğrudan Microsoft 365'e akar, ancak geçerli aboneliğinizde yalnızca [Exchange Online Protection (EOP)](exchange-online-protection-overview.md) veya [Plan 1 Office 365 için Defender](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) vardır.

  ![EOP ve/veya Office 365 için Defender Plan 1'e karşı koruma ile posta İnternet'ten Microsoft 365'e akar.](../../media/mdo-trial-mail-flow.png)

  Bu ortamlarda **denetim modunu** veya **engelleme modunu** seçebilirsiniz.

- Şu anda Microsoft 365 posta kutularınızın e-posta koruması için üçüncü taraf bir hizmet veya cihaz kullanıyorsunuz. İnternet'ten gelen postalar, Microsoft 365 kuruluşunuza teslim etmeden önce koruma hizmeti aracılığıyla akar. Microsoft 365 koruması mümkün olduğunca düşüktür (hiçbir zaman tamamen kapalı değildir; örneğin, kötü amaçlı yazılım koruması her zaman uygulanır).

  ![Microsoft 365'e teslim etmeden önce İnternet'ten üçüncü taraf koruma hizmeti veya cihazı aracılığıyla posta akışları.](../../media/mdo-migration-before.png)

  Bu ortamlarda yalnızca **denetim modunu** seçebilirsiniz. Posta akışınızı (MX kayıtları) değiştirmeniz gerekmez.

### <a name="evaluation-vs-trial-for-defender-for-office-365"></a>Office 365 için Defender için değerlendirme ve deneme karşılaştırması

Office 365 için Defender Plan 2'nin değerlendirmesiyle deneme sürümü arasındaki fark nedir? Aynı şey değil mi? Evet ve hayır. Bilmeniz gerekenler şunlardır:

- Office 365 için Defender Plan 2 lisanslarınız yoksa (örneğin, tek başına EOP, Microsoft 365 E3, Microsoft 365 İş Ekstra veya Office 365 için Defender Plan 1) deneme sürümünüzü **Microsoft 365'ten başlatabilirsiniz denemeler** sayfası <https://security.microsoft.com/trialHorizontalHub> veya Microsoft 365 Defender portalındaki **Değerlendirme modu** sayfası<https://security.microsoft.com/atpEvaluation>. Her iki konumda da daha önce açıklandığı gibi **izin verme modunu** (Standart önceden ayarlanmış güvenlik ilkesi) veya **engelleme modunu** (değerlendirme ilkeleri) seçebilirsiniz.

  Hangi konumu kullandığınızdan bağımsız olarak, kaydolduysanız sizin için gerekli Office 365 için Defender Plan 2 deneme lisanslarını otomatik olarak sağlayacağız. Microsoft 365 yönetim merkezi Plan 2 lisanslarını almak ve atamak için el ile veya dış adımlar artık gerekli değildir. Deneme lisansları 90 gün boyunca geçerlidir:

  - Office 365 için Defender olmayan kuruluşlar için (örneğin, tek başına EOP veya Microsoft 365 E3) Office 365 için Defender özellikleri (özellikle, ilkeler) deneme süresi boyunca kullanımınıza sunulur.

  - Office 365 için Defender Plan 1'e sahip kuruluşlar (örneğin Microsoft 365 İş Ekstra veya eklenti abonelikleri) Office 365 için Defender sahip kuruluşlarla tam olarak aynı ilkelere sahiptir  Plan 2 (kimlik avı önleme ilkelerinde kimliğe bürünme koruması, Güvenli Ekler ilkeleri ve Güvenli Bağlantılar ilkeleri). **İzin verme modundan** (Standart önceden ayarlanmış güvenlik ilkesi) veya **engelleme modundan** (değerlendirme ilkeleri) güvenlik ilkelerinin süresi dolmaz veya 90 gün sonra çalışmaz. Bu kuruluşlar için 90 gün sonra biten, Plan 2'nin Plan 1'de bulunmayan [otomasyon, araştırma, düzeltme ve eğitim özellikleridir](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) .

- Zaten Office 365 için Defender Plan 2'niz varsa (örneğin, bir Microsoft 365 E5 aboneliğinin parçası olarak), konumundaki **Microsoft 365 denemeleri** sayfasında <https://security.microsoft.com/trialHorizontalHub>**hiçbir zaman Office 365 için Defender** görmezsiniz. Bunun yerine, Office 365 için Defender Planla değerlendirmenizi **Değerlendirme modu** sayfasında <https://security.microsoft.com/atpEvaluation> **izin verme modunda** (Standart ön ayarlı güvenlik ilkesi) veya **engelleme modunda** (değerlendirme ilkeleri) başlatırsınız.

  Tanım gereği, bu kuruluşlar Office 365 için Defender Plan 2 deneme lisansı gerektirmez, bu nedenle değerlendirmeleri süresi sınırsızdır.

Önceki listede yer alan bilgiler aşağıdaki tabloda özetlenmiş:

|Organizasyon|Kullanılabilir modlar|Kayıt için<br/>Değerlendirme sayfası mı?|Kayıt için<br/>Denemeler sayfası?|Değerlendirme<br/>Dönem|
|---|---|:---:|:---:|---|
|Tek başına EOP<br/>(Exchange Online posta kutusu yok) <br/><br/> Microsoft 365 E3|Denetim modu <br/> Engelleme modu|Evet|Evet|90 gün|
|Office 365 için Defender Plan 1 <br/><br/> Microsoft 365 Business Premium|Denetim modu <br/> Engelleme modu|Evet|Evet|Sınırsız<sup>\*</sup>|
|Microsoft 365 E5|Denetim modu <br/> Engelleme modu|Evet|Hayır|Sınırsız|

<sup>\*</sup>**İzin verme modundan** (Standart önceden ayarlanmış güvenlik ilkesi) veya **engelleme modundan** (değerlendirme ilkeleri) güvenlik ilkelerinin süresi dolmaz veya 90 gün sonra çalışmaz. Yalnızca Office 365 için Defender Plan 2'ye özel [otomasyon, araştırma, düzeltme ve eğitim özellikleri](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 90 gün sonra çalışmayı durdurur.

## <a name="set-up-an-evaluation-or-trial-in-audit-mode"></a>Denetim modunda değerlendirme veya deneme ayarlama

Office 365 için Defender denetim modunda değerlendirdiğinizde, Office 365 için Defender tehditleri algılayabilmesi için özel değerlendirme ilkeleri oluşturulduğunu unutmayın. Bu değerlendirme ilkelerinin ayarları, bu makalenin devamında [denetim modunda ilkeler](#policies-in-audit-mode) bölümünde açıklanmaktadır.

1. Değerlendirmeyi adresinden Microsoft 365 Defender portalındaki <https://security.microsoft.com>kullanılabilir konumlardan herhangi birinde başlatın. Örneğin:
   - Herhangi bir Office 365 için Defender özellik sayfasının üst kısmındaki başlıkta **Ücretsiz denemeyi başlat'a** tıklayın.
   - konumundaki **Microsoft 365 denemeleri** sayfasında <https://security.microsoft.com/trialHorizontalHub>**Office 365 için Defender** bulun ve seçin.
   - konumundaki **Değerlendirme modu** sayfasında <https://security.microsoft.com/atpEvaluation>**Değerlendirmeyi başlat'a** tıklayın.

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
   > Deneme sürümünü ayarlamayı bitirdikten sonra [, Deneme sürümünüzü yönetme](#manage-your-evaluation-or-trial-of-defender-for-office-365) bölümünde açıklandığı gibi bu seçimleri değiştirebilirsiniz.
   >
   > Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. Değerlendirme veya deneme *yalnızca* belirtilen alıcı filtrelerinin *tümüyle* eşleşen alıcılara uygulanır. Örneğin, aşağıdaki değerlerle bir koşul yapılandırabilirsiniz:
   >
   > - **Kullanıcılar**: romain@contoso.com
   > - **Gruplar**: Yöneticiler
   >
   > Değerlendirme veya deneme, *romain@contoso.com yalnızca* Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse, değerlendirme veya deneme ona uygulanmaz.
   >
   > Benzer şekilde, özel durum olarak aynı alıcı filtresini kullanırsanız, değerlendirme veya deneme romain@contoso.com *yalnızca* Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, değerlendirme veya deneme onun için geçerli olmaya devam eder.

   İşiniz bittiğinde **Devam'a** tıklayın.

4. **Posta akışınızı anlamamıza yardımcı olun** iletişim kutusunda aşağıdaki seçenekleri yapılandırın:

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

            Microsoft 365'e akan e-postanın önünde üçüncü taraf bir hizmet veya cihaz durduğunda Bağlayıcılar için Gelişmiş Filtreleme İnternet iletilerinin kaynağını doğru şekilde tanımlar ve Microsoft filtreleme yığınının doğruluğunu (özellikle kimlik [sahtekarlığı zekasının](anti-spoofing-protection.md) yanı sıra [Tehdit Gezgini](threat-explorer.md) ve [Otomatik Araştırma & Yanıtı'ndaki (AIR)](automated-investigation-response-office.md) ihlal sonrası özellikleri büyük ölçüde geliştirir.

          - **İletilerinizin geçtiği her ağ geçidi IP adresini listeleyin**: Bu ayar yalnızca **Üçüncü taraf bir hizmet sağlayıcısı seçin** için **Diğer'i** seçtiyseniz kullanılabilir. Microsoft 365'e posta göndermek için üçüncü taraf koruma hizmeti veya cihazı tarafından kullanılan IP adreslerinin virgülle ayrılmış bir listesini girin.

          İşiniz bittiğinde **İleri'ye** tıklayın.

       2. **Exchange posta akışı kuralları** iletişim kutusunda, üçüncü taraf koruma hizmetinden veya cihazından gelen iletiler için istenmeyen posta filtrelemeyi atlayan bir Exchange Online posta akışı kuralına (aktarım kuralı olarak da bilinir) ihtiyacınız olup olmadığını belirleyin.

          Exchange Online'de koruma hizmetinden gelen tüm postaların Microsoft 365 filtrelemesini atlamasına (çoğu) izin veren bir SCL=-1 posta akışı kuralınız olabilir. Birçok koruma hizmeti, hizmetlerini kullanan Microsoft 365 müşterileri için bu istenmeyen posta güven düzeyi (SCL) posta akışı kuralı yöntemini teşvik eder.

          Önceki adımda açıklandığı gibi, Bağlayıcılar için Gelişmiş Filtreleme, koruma hizmetinden posta kaynağı olarak belirttiğiniz bağlayıcıda otomatik olarak yapılandırılır.

          Koruma hizmetinden gelen postalar için SCL=-1 kuralı olmadan Bağlayıcılar için Gelişmiş Filtreleme özelliğinin etkinleştirilmesi, kimlik [sahtekarlık zekası](anti-spoofing-protection.md) gibi EOP koruma özelliklerinin algılama özelliklerini büyük ölçüde geliştirir ve yeni algılanan iletilerin teslimini etkileyebilir (örneğin, Gereksiz Email klasörüne veya karantinaya almak için). Bu etki EOP ilkeleriyle sınırlıdır; daha önce açıklandığı gibi, Office 365 için Defender ilkeleri denetim modunda oluşturulur.

          SCL=-1 posta akışı kuralı oluşturmak veya mevcut kurallarınızı gözden geçirmek için sayfadaki **Exchange yönetim merkezine git** düğmesine tıklayın. Daha fazla bilgi için bkz. [Exchange Online iletilerde istenmeyen posta güvenilirlik düzeyini (SCL) ayarlamak için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

          İşiniz bittiğinde **Son'a** tıklayın.

     - **Yalnızca Microsoft Exchange Online kullanıyorum**: Etki alanınızın MX kayıtları Microsoft 365'e işaret etti. Yapılandıracak bir şey kalmadığından **Son'a** tıklayın.

   - **Microsoft ile veri paylaşma**: Bu seçenek varsayılan olarak seçili değildir, ancak isterseniz onay kutusunu seçebilirsiniz.

5. Değerlendirmeniz ayarlanırken bir ilerleme durumu iletişim kutusu görüntülenir. Kurulum tamamlandığında **Bitti'ye** tıklayın.

## <a name="set-up-an-evaluation-or-trial-in-blocking-mode"></a>Engelleme modunda değerlendirme veya deneme ayarlama

Engelleme modunda Office 365 için Defender denediğinizde Standart ön ayarlı güvenliğin açık olduğunu ve belirtilen kullanıcıların (bazıları veya herkes) Standart önceden ayarlanmış güvenlik ilkesine dahil olduğunu unutmayın. Standart önceden ayarlanmış güvenlik ilkesi hakkında daha fazla bilgi için bkz. [Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md).

1. Deneme sürümünü adresinden Microsoft 365 Defender portalındaki <https://security.microsoft.com>kullanılabilir konumlardan herhangi birinde başlatın. Örneğin:
   - Herhangi bir Office 365 için Defender özellik sayfasının üst kısmındaki başlıkta **Ücretsiz denemeyi başlat'a** tıklayın.
   - konumundaki **Microsoft 365 denemeleri** sayfasında <https://security.microsoft.com/trialHorizontalHub>**Office 365 için Defender** bulun ve seçin.
   - konumundaki **Değerlendirme modu** sayfasında <https://security.microsoft.com/atpEvaluation>**Değerlendirmeyi başlat'a** tıklayın.

2. **Korumayı aç** iletişim kutusunda **Evet, tehditleri engelleyerek kuruluşumu koru'yu** seçin ve **devam'a** tıklayın.

3. **Eklemek istediğiniz kullanıcıları seçin** iletişim kutusunda aşağıdaki ayarları yapılandırın:

   - **Tüm kullanıcılar**: Bu varsayılan ve önerilen seçenektir.
   - **Kullanıcıları seçin**: Bu seçeneği belirlerseniz, deneme sürümünün geçerli olduğu dahili alıcıları seçmeniz gerekir:
     - **Kullanıcılar**: Belirtilen posta kutuları, posta kullanıcıları veya posta kişileri.
     - **Gruplar**:
       - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
       - Belirtilen Microsoft 365 Grupları.
     - **Etki alanları**: Kuruluşunuzda belirtilen [kabul edilen etki alanlarındaki](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) tüm alıcılar.

     Uygun kutuya tıklayın, bir değer yazmaya başlayın ve sonuçlardan istediğiniz değeri seçin. Bu işlemi gerektiği kadar tekrarlayın. Mevcut bir değeri kaldırmak için Kaldır'a tıklayın ![Kaldır simgesi.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.

     Kullanıcılar veya gruplar için çoğu tanımlayıcıyı (ad, görünen ad, diğer ad, e-posta adresi, hesap adı vb.) kullanabilirsiniz, ancak sonuçlarda ilgili görünen ad gösterilir. Kullanıcılar için, tüm kullanılabilir değerleri görmek için tek başına bir yıldız işareti (\*) girin.

   > [!NOTE]
   > Deneme sürümünü ayarlamayı bitirdikten sonra [, Deneme sürümünüzü yönetme](#manage-your-evaluation-or-trial-of-defender-for-office-365) bölümünde açıklandığı gibi bu seçimleri değiştirebilirsiniz.
   >
   > Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. Değerlendirme veya deneme *yalnızca* belirtilen alıcı filtrelerinin *tümüyle* eşleşen alıcılara uygulanır. Örneğin, aşağıdaki değerlerle bir koşul yapılandırabilirsiniz:
   >
   > - **Kullanıcılar**: romain@contoso.com
   > - **Gruplar**: Yöneticiler
   >
   > Değerlendirme veya deneme, *romain@contoso.com yalnızca* Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse, değerlendirme veya deneme ona uygulanmaz.
   >
   > Benzer şekilde, özel durum olarak aynı alıcı filtresini kullanırsanız, değerlendirme veya deneme romain@contoso.com *yalnızca* Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, değerlendirme veya deneme onun için geçerli olmaya devam eder.

   İşiniz bittiğinde **Devam'a** tıklayın.

4. Değerlendirmeniz ayarlanırken bir ilerleme durumu iletişim kutusu görüntülenir. Kurulum tamamlandığında **Bitti'ye** tıklayın.

## <a name="manage-your-evaluation-or-trial-of-defender-for-office-365"></a>değerlendirmenizi veya Office 365 için Defender denemenizi yönetme

Değerlendirme veya denemenizi denetim modunda veya engelleme modunda ayarladıktan sonra, Plan 2'yi deneme hakkında bilgi için konumundaki <https://security.microsoft.com/atpEvaluation> **Değerlendirme modu** sayfası Office 365 için Defender.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **İlkeleri & kuralları** \> **Tehdit ilkeleri'ne** \> gidin ve **Diğerleri** bölümünde **Değerlendirme modu'nu** seçin. Veya doğrudan **Office 365 için Microsoft Defender değerlendirme** sayfasına gitmek için kullanın<https://security.microsoft.com/atpEvaluation>.

2. **Office 365 için Microsoft Defender değerlendirme** sayfasında aşağıdaki görevleri gerçekleştirebilirsiniz:

   - Office 365 için Defender Plan 2'yi satın almak için **Ücretli abonelik satın al'a** tıklayın.

   - **Yönet'e** tıklayın. Görüntülenen **Office 365 için Microsoft Defender değerlendirme** açılır öğesinde aşağıdaki görevleri gerçekleştirebilirsiniz:

     - Değerlendirme veya deneme sürümünün hangi kişilere uygulanacağı, daha önce [Denetim modunda değerlendirme veya deneme ayarlama](#set-up-an-evaluation-or-trial-in-audit-mode) ve [Engelleme modunda değerlendirme veya deneme ayarlama](#set-up-an-evaluation-or-trial-in-blocking-mode) bölümünde açıklandığı gibi değiştirin.

     - **Denetim modundan** (değerlendirme ilkeleri) engelleme moduna (Standart ön ayarlı güvenlik ilkesi) geçmek **için Standart korumaya dönüştür'e** tıklayın ve ardından **Önceden ayarlanmış güvenlik ilkeleri** sayfasındaki **Standart koruma uygula** sihirbazına alınmış gibi görünen iletişim kutusunda **Devam'a** tıklayın. Dahil edilen ve dışlanan mevcut alıcılar kopyalanır. Daha fazla bilgi için bkz. [Kullanıcılara Standart ve Katı önceden ayarlanmış güvenlik ilkeleri atamak için Microsoft 365 Defender portalını kullanma](preset-security-policies.md#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

       **Notlar**:

       - Standart önceden ayarlanmış güvenlik ilkesindeki ilkeler, değerlendirme ilkelerinden daha yüksek önceliğe sahiptir. Bu, Standart önceden ayarlanmış güvenlikteki ilkelerin her ikisi de mevcut ve açık olsa bile her zaman değerlendirme *ilkelerinden önce* uygulandığı anlamına gelir. Değerlendirme ilkelerini kapatmak için **Kapat** düğmesini kullanın.
       - **Engelleme modundan** **denetim** moduna geçmenin otomatik bir yolu yoktur. El ile uygulanan adımlar şunlardır:
         1. Önceden ayarlanmış güvenlik ilkeleri sayfasında Standart önceden **ayarlanmış güvenlik ilkesini** kapatın.
         2. **Office 365 için Microsoft Defender değerlendirme** sayfasında **Yönet'e** tıkladıktan sonra, değerlendirme ilkelerinin açık olduğunu gösteren **Kapat** düğmesinin varlığını doğrulayın. **Aç** düğmesini görüyorsanız, değerlendirme ilkelerini açmak için bu düğmeye tıklayın.
         3. Değerlendirmenin geçerli olduğu kullanıcıları doğrulayın.

     - Değerlendirme ilkelerini kapatmak için **Kapat'a** tıklayın. Yeniden açmak için **Aç'a** tıklayın.

     Açılır öğeyi bitirdiğinizde **Kaydet'e** tıklayın.

## <a name="reports-for-your-evaluation-or-trial-of-defender-for-office-365"></a>Office 365 için Defender değerlendirmeniz veya denemeniz için raporlar

Bu bölümde, denetim modunda ve engelleme modunda kullanılabilen raporlar açıklanmaktadır.

### <a name="reports-for-blocking-mode"></a>Engelleme modu raporları

**Engelleme modunda**, aşağıdaki raporlar Office 365 için Defender göre algılamaları gösterir:

- [Posta akışı durum raporu için Posta Akışı görünümü](view-email-security-reports.md#mailflow-view-for-the-mailflow-status-report):

  - Kimlik avı önleme ilkeleri tarafından kullanıcı kimliğe bürünme veya etki alanı kimliğe bürünme olarak algılanan iletiler **Kimliğe Bürünme bloğunda** görünür.
  - Güvenli Ekler ilkeleri veya Güvenli Bağlantılar ilkeleri tarafından dosya veya URL'nin patlatılması sırasında algılanan iletiler **, Patlama bloğunda** görünür.

- [Tehdit koruması durum raporu](view-email-security-reports.md#threat-protection-status-report):

  - [Genel Bakış'a göre verileri görüntüleme](view-email-security-reports.md#view-data-by-overview):

    Office 365 için Defender etkilerini görmek için çoğu görünümü **Protected by** değeri **MDO'ya** göre filtreleyebilirsiniz.

  - [Algılama Teknolojisine göre kimlik avı ve grafik dökümünü Email \> verileri görüntüleme](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

    - [Kampanyalar](campaigns.md) tarafından algılanan iletiler **Kampanya'da** görünür.
    - Güvenli Ekler tarafından algılanan iletiler **, Dosya patlama ve Dosya** patlama **saygınlığı** içinde görünür.
    - Kimlik avı önleme ilkelerinde kullanıcı kimliğe bürünme koruması tarafından algılanan iletiler **Kimliğe Bürünme etki alanı**, **Kimliğe Bürünme kullanıcısı** ve **Posta kutusu zekası kimliğe bürünme** bölümünde görünür.
    - Güvenli Bağlantılar tarafından algılanan iletiler **, URL'nin patlatılması** ve **URL'nin patlatılması saygınlığında** görünür.

  - [Email Kötü Amaçlı Yazılıma göre verileri \> görüntüleme ve Algılama Teknolojisine göre grafik dökümü](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)

    - [Kampanyalar](campaigns.md) tarafından algılanan iletiler **Kampanya'da** görünür.
    - Güvenli Ekler tarafından algılanan iletiler **, Dosya patlama ve Dosya** patlama **saygınlığı** içinde görünür.
    - Güvenli Bağlantılar tarafından algılanan iletiler **, URL'nin patlatılması** ve **URL'nin patlatılması saygınlığında** görünür.

  - [Algılama Teknolojisine göre Email \> İstenmeyen Posta ve Grafik dökümlerine göre verileri görüntüleme](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)

    Güvenli Bağlantılar tarafından algılanan iletiler **URL kötü amaçlı saygınlığında** görünür.

  - [İlke türüne göre grafik dökümü](view-email-security-reports.md#chart-breakdown-by-policy-type)

    Güvenli Ekler tarafından algılanan iletiler **Güvenli Ekler'de** görüntülenir

  - [İçerik \> Kötü Amaçlı Yazılımlarına göre verileri görüntüleme](view-email-security-reports.md#view-data-by-content--malware)

    [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler](turn-on-mdo-for-spo-odb-and-teams.md) tarafından algılanan kötü amaçlı dosyalar **MDO patlamasında** görünür.

  - [En çok gönderenler ve alıcılar raporu](view-email-security-reports.md#top-senders-and-recipients-report)

    **En iyi kötü amaçlı yazılım alıcıları (MDO)** için **verileri göster ve En iyi kimlik avı alıcıları (MDO) için verileri göster**.

  - [URL koruma raporu](view-reports-for-mdo.md#url-protection-report)

### <a name="reports-for-audit-mode"></a>Denetim modu raporları

**Denetim modunda**, aşağıdaki raporlar Office 365 için Defender göre algılamaları gösterir:

- [Tehdit koruması durum raporu](view-email-security-reports.md#threat-protection-status-report) **Değerlendirmeye sahip: Evet/Hayır**, aşağıdaki görünümlerde filtrelenebilir bir özellik olarak:
  - [Algılama Teknolojisine göre kimlik avı ve grafik dökümünü Email \> verileri görüntüleme](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)
  - [Email Kötü Amaçlı Yazılıma göre verileri \> görüntüleme ve Algılama Teknolojisine göre grafik dökümü](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Algılama Teknolojisine göre Email \> İstenmeyen Posta ve Grafik dökümlerine göre verileri görüntüleme](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)

- [Tehdit Gezgini](threat-explorer.md)**, Hatalı ek**, **istenmeyen posta url'si + kötü amaçlı yazılım**, **Kimlik avı URL'si** ve Office 365 için Defender değerlendirmesi tarafından algılanan **kimliğe bürünme** iletileri için **Analiz** sekmesindeki ileti algılama ayrıntılarında aşağıdaki başlığı girdinin ayrıntılarında gösterir:

  ![İletideki bildirim başlığı, Office 365 için Defender değerlendirmesinin kötü amaçlı bir e-posta iletisi algıladığını gösterir.](../../media/evalv2-detection-banner.png)

konumundaki **Office 365 için Microsoft Defender değerlendirme** sayfası<https://security.microsoft.com/atpEvaluation>, değerlendirmedeki ilkeler için raporlamayı birleştirir:

- Güvenli Bağlantılar
- Güvenli Ekler
- Kimlik avı önleme ilkelerinde kimliğe bürünme koruması

Varsayılan olarak, grafikler son 30 güne ilişkin verileri gösterir, ancak Takvim simgesine tıklayarak ![tarih aralığını filtreleyebilirsiniz.](../../media/m365-cc-sc-add-internal-icon.png) **30 gün ve 30** günden az olan aşağıdaki ek değerler arasından seçim yapın:

- 24 saat
- 7 gün
- 14 gün
- Özel tarih aralığı

İndir simgesine tıklayabilirsiniz ![.](../../media/m365-cc-sc-download-icon.png) Grafik verilerini bir .csv dosyasına indirmek için **indirin**.

## <a name="required-permissions"></a>Gerekli izinler

Microsoft 365 için Defender'ın değerlendirmesini veya deneme sürümünü ayarlamak için **Azure AD'de** aşağıdaki izinler gereklidir:

- **Değerlendirme veya deneme oluşturma, değiştirme veya silme**: Güvenlik Yöneticisi veya Genel Yönetici.
- **Değerlendirme ilkelerini ve raporlarını denetim modunda görüntüleyin**: Güvenlik Yöneticisi veya Güvenlik Okuyucusu.

Microsoft 365 Defender portalındaki Azure AD izinleri hakkında daha fazla bilgi için bkz. [Microsoft 365 Defender portalında Azure AD rolleri](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="q-do-i-need-to-manually-get-or-activate-trial-licenses"></a>S: Deneme lisanslarını el ile edinmem veya etkinleştirmem gerekiyor mu?

C: Hayır. Deneme sürümü, daha önce açıklandığı gibi ihtiyacınız varsa Office 365 için Defender Plan 2 lisanslarını otomatik olarak sağlar.

### <a name="q-how-do-i-extend-the-trial"></a>S: Deneme süresini uzatmak Nasıl yaparım??

Y: Bkz. [Deneme sürenizi uzatma](/microsoft-365/commerce/try-or-buy-microsoft-365#extend-your-trial).

### <a name="q-what-happens-to-my-data-after-the-trial-expires"></a>S: Deneme süresi dolduktan sonra verilerime ne olur?

Y: Deneme süreniz dolduktan sonra, deneme verilerinize (daha önce sahip olmadığınız Office 365 için Defender özelliklerden gelen veriler) 30 gün boyunca erişebilirsiniz. Bu 30 günlük süreden sonra, Office 365 için Defender deneme sürümüyle ilişkili tüm ilkeler ve veriler silinir.

### <a name="q-how-many-times-can-i-use-the-defender-for-office-365-trial-in-my-organization"></a>S: Kuruluşumda Office 365 için Defender deneme sürümünü kaç kez kullanabilirim?

Y: En fazla 2 kez. İlk deneme süreniz dolarsa, Office 365 için Defender deneme sürümüne yeniden kaydolmak için son kullanma tarihinden sonra en az 30 gün beklemeniz gerekir. İkinci denemenizden sonra başka bir deneme sürümüne kaydolamazsınız.

### <a name="q-in-audit-mode-are-there-scenarios-where-defender-for-office-365-will-act-on-messages"></a>S: Denetim modunda, Office 365 için Defender iletiler üzerinde işlem yapacağı senaryolar var mı?

A: Evet. Herhangi bir program veya SKU'daki hiç kimse, hizmet tarafından kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı olarak sınıflandırılan iletiler üzerinde işlem gerçekleştirmeyi devre dışı bırakabilir veya atlayabilir.

Denetim modunda [, EOP'de kimlik sahtekarlığı önleme koruması](set-up-anti-phishing-policies.md#spoof-settings) iletilerde de eyleme geçer. Kimlik sahtekarlığı önleme korumasının iletilerde etkili olmasını önlemek için, gelen e-postanın atlanabilir tüm filtreleme türlerini atladığı bir Exchange posta akışı kuralı (aktarım kuralı olarak da bilinir) oluşturun (kimlik sahtekarlığı önleme koruması dahil). Yönergeler için bkz. [Exchange Online iletilerde istenmeyen posta güvenilirlik düzeyini (SCL) ayarlamak için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

### <a name="q-in-what-order-are-policies-evaluated"></a>S: İlkeler hangi sırayla değerlendirilir?

Y: Önceden [ayarlanmış güvenlik ilkeleri ve diğer ilkeler için öncelik sırası](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies) bölümüne bakın.

## <a name="reference"></a>Başvuru

### <a name="policy-settings-associated-with-defender-for-office-365-trials"></a>Office 365 için Defender denemeleriyle ilişkili ilke ayarları

#### <a name="policies-in-audit-mode"></a>Denetim modunda ilkeler

> [!WARNING]
> Office 365 için Defender değerlendirmesiyle ilişkili tek tek güvenlik ilkelerini oluşturmayı, değiştirmeyi veya kaldırmayı denemeyin. Değerlendirme için tek tek güvenlik ilkelerini oluşturmak için desteklenen tek yöntem, değerlendirmeyi veya denemeyi Microsoft 365 Defender portalında ilk kez denetim modunda başlatmaktır.

[Daha önce açıklandığı gibi](#audit-mode-vs-blocking-mode-for-defender-for-office-365), değerlendirmeniz veya denemeniz için denetim modunu seçtiğinizde, gözlemlemek için gerekli ayarları içeren ancak iletilerde işlem yapılmayan değerlendirme ilkeleri otomatik olarak oluşturulur.

Bu ilkeleri ve ayarlarını görmek için [PowerShell'Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki komutu çalıştırın:

```powershell
Write-Output -InputObject ("`r`n"*3),"Evaluation anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"; Write-Output -InputObject ("`r`n"*3),"Evaluation Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"; Write-Output -InputObject ("`r`n"*3),"Evaluation Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Evaluation"
```

Ayarlar aşağıdaki tablolarda da açıklanmıştır.

##### <a name="anti-phishing-evaluation-policy-settings"></a>Kimlik avı önleme değerlendirme ilkesi ayarları

|Ayar|Değer|
|---|---|
|Name|Değerlendirme İlkesi|
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
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|ImpersonationProtectionState|El ile|
|Isdefault|False|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|PhishThresholdLevel|1|
|İlke Etiketi|Boş|
|RecommendedPolicyType|Değerlendirme|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainsToProtect|{}|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|TargetedUsersToProtect|{}|

##### <a name="safe-attachments-evaluation-policy-settings"></a>Güvenli Ekler değerlendirme ilkesi ayarları

|Ayar|Değer|
|---|---|
|Name|Değerlendirme İlkesi|
|Eylem|İzin ver|
|ActionOnError|True|
|Admindisplayname|Değerlendirme İlkesi|
|ConfidenceLevelThreshold|80|
|Etkinleştirmek|True|
|EnableOrganizationBranding|False|
|IsBuiltInProtection|False|
|Isdefault|False|
|OperationMode|Gecikme|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|Değerlendirme|
|Yönlendirme|False|
|RedirectAddress|Boş|
|ScanTimeout|30|

##### <a name="safe-links-evaluation-policy-settings"></a>Güvenli Bağlantılar değerlendirme ilkesi ayarları

|Ayar|Değer|
|---|---|
|Name|Değerlendirme İlkesi|
|Admindisplayname|Değerlendirme İlkesi|
|AllowClickThrough|True|
|CustomNotificationText|Boş|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|False|
|EnableSafeLinksForTeams|False|
|IsBuiltInProtection|False|
|LocalizedNotificationTextList|{}|
|RecommendedPolicyType|Değerlendirme|
|ScanUrls|True|
|TrackClicks|True|

##### <a name="use-powershell-to-configure-recipient-conditions-and-exceptions-to-the-evaluation-in-audit-mode"></a>Denetim modunda değerlendirme için alıcı koşullarını ve özel durumlarını yapılandırmak için PowerShell kullanma

Office 365 için Defender değerlendirme ilkeleriyle ilişkili bir kural, değerlendirmenin alıcı koşullarını ve özel durumlarını denetler.

Değerlendirmeyle ilişkili kuralı görüntülemek için PowerShell'Exchange Online aşağıdaki komutu çalıştırın:

```powershell
Get-ATPEvaluationRule
```

Değerlendirmenin uygulanacağı kişiyi değiştirmek için powershell Exchange Online kullanmak için aşağıdaki söz dizimini kullanın:

```powershell
Set-ATPEvaluationRule -Identity "Evaluation Rule" -SentTo <"user1","user2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -SentToMemberOf <"group1","group2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null> -RecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null>
```

Bu örnekte, belirtilen güvenlik işlemleri (SecOps) posta kutuları için değerlendirmeden özel durumlar yapılandırılır.

```powershell
Set-ATPEvaluationRule -Identity "Evaluation Rule" -ExceptIfSentTo "SecOps1","SecOps2"
```

##### <a name="use-powershell-to-turn-on-or-turn-off-the-evaluation-in-audit-mode"></a>Denetim modunda değerlendirmeyi açmak veya kapatmak için PowerShell kullanma

Değerlendirmeyi denetim modunda açmak veya kapatmak için, değerlendirmeyle ilişkili kuralı etkinleştirir veya devre dışı bırakırsınız. Değerlendirme kuralının State özellik değeri, kuralın Etkin mi yoksa Devre Dışı mı olduğunu gösterir.

Değerlendirmenin şu anda etkin mi yoksa devre dışı mı olduğunu belirlemek için aşağıdaki komutu çalıştırın:

```powershell
Get-ATPEvaluationRule -Identity "Evaluation Rule" | Format-Table Name,State
```

Açıksa değerlendirmeyi kapatmak için aşağıdaki komutu çalıştırın:

```powershell
Disable-ATPEvaluationRule -Identity "Evaluation Rule"
```

Kapalıysa değerlendirmeyi açmak için aşağıdaki komutu çalıştırın:

```powershell
Enable-ATPEvaluationRule -Identity "Evaluation Rule"
```

#### <a name="policies-and-rules-in-block-mode"></a>Blok modunda ilkeler ve kurallar

[Daha önce açıklandığı gibi](#audit-mode-vs-blocking-mode-for-defender-for-office-365), deneme sürümünüz için engelleme modunu seçtiğinizde ilkeler [önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md) için Standart şablon kullanılarak oluşturulur.

Exchange Online PowerShell kullanarak Standart önceden ayarlanmış güvenlik ilkesiyle ilişkili tek tek güvenlik ilkelerini görüntülemek ve önceden ayarlanmış güvenlik ilkesi için alıcı koşullarını ve özel durumlarını görüntülemek ve yapılandırmak üzere Exchange Online PowerShell kullanmak için bkz. [PowerShell'de önceden ayarlanmış güvenlik ilkeleri Exchange Online](preset-security-policies.md#preset-security-policies-in-exchange-online-powershell).
