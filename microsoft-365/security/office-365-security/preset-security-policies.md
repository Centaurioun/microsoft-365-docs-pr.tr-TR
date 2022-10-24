---
title: Önceden ayarlanmış güvenlik ilkeleri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- m365-security
ms.custom: ''
description: Yöneticiler, Exchange Online Protection (EOP) ve Office 365 için Microsoft Defender koruma özellikleri arasında Standart ve Katı ilke ayarlarının nasıl uygulanacağını öğrenebilir
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: b28c315ecfe8ee6513c8f45be6d89953d4908647
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68684764"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP ve Office 365 için Microsoft Defender'da önceden ayarlanmış güvenlik ilkeleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Önceden ayarlanmış güvenlik ilkeleri, önerilen tüm istenmeyen posta, kötü amaçlı yazılım ve kimlik avı ilkelerini kullanıcılara aynı anda uygulamak için merkezi bir konum sağlar. İlke ayarları yapılandırılamaz. Bunun yerine, bunlar bizim tarafımızda ayarlanır ve zararlı içerikleri kullanıcılardan uzak tutmak ve gereksiz kesintilerden kaçınmak arasında bir denge sağlamak için veri merkezlerindeki gözlemlerimize ve deneyimlerimize dayanır.

Bu makalenin geri kalanında önceden ayarlanmış güvenlik ilkeleri ve bunların nasıl yapılandırıldığı açıklanmaktadır.

## <a name="what-preset-security-policies-are-made-of"></a>Önceden ayarlanmış güvenlik ilkelerinin hangilerinden yapıldığı

Önceden ayarlanmış güvenlik ilkeleri aşağıdaki öğelerden oluşur:

- Profil
- İlkeler
- İlke ayarları

Ayrıca, önceden ayarlanmış birden çok güvenlik ilkesi ve diğer ilkeler aynı kişi için geçerliyse öncelik sırası önemlidir.

### <a name="profiles-in-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkelerindeki profiller

Profil, koruma düzeyini belirler. Aşağıdaki profiller kullanılabilir:

- **Standart koruma**: Çoğu kullanıcı için uygun bir temel koruma profili.
- **Katı koruma**: Seçili kullanıcılar için daha agresif bir koruma profili (yüksek değer hedefleri veya öncelikli kullanıcılar).

  **Standart koruma** ve **Katı koruma** için, ilkenin geçerli olduğu iç alıcıları (alıcı koşulları) belirlemek için koşullar ve özel durumlar içeren kurallar kullanırsınız.

  Kullanılabilir koşullar ve özel durumlar şunlardır:

  - **Kullanıcılar**: Belirtilen posta kutuları, posta kullanıcıları veya posta kişileri.
  - **Gruplar**:
    - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
    - Belirtilen Microsoft 365 Grupları.

    > [!NOTE]
    >  Dinamik dağıtım grupları desteklenmez.

  - **Etki alanları**: Kuruluşunuzda belirtilen [kabul edilen etki alanlarındaki](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) tüm alıcılar.

  Bir koşulu veya özel durumu yalnızca bir kez kullanabilirsiniz, ancak koşul veya özel durum için birden çok değer belirtebilirsiniz. Aynı koşula veya özel duruma ait birden çok değer OR mantığını kullanır (örneğin, _\<recipient1\>_ veya _\<recipient2\>_). Farklı koşullar veya özel durumlar AND mantığını kullanır (örneğin, _\<recipient1\>_ ve _\<member of group 1\>_).

  > [!IMPORTANT]
  > Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. Önceden ayarlanmış güvenlik ilkesi _yalnızca_ belirtilen alıcı filtrelerinin _tümüyle_ eşleşen alıcılara uygulanır. Örneğin, ilkede aşağıdaki değerlerle bir alıcı filtresi koşulu yapılandırabilirsiniz:
  >
  > - Kullanıcılar: romain@contoso.com
  > - Gruplar: Yöneticiler
  >
  > İlke, _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse ilke ona uygulanmaz.
  >
  > Benzer şekilde, ilkenin özel durumu olarak aynı alıcı filtresini kullanırsanız, ilke _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, ilke hala onun için geçerlidir.

- **Yerleşik koruma** (yalnızca Office 365 için Defender): Yalnızca Güvenli Bağlantılar ve Güvenli Ekler korumasını etkinleştiren bir profil. Bu profil, hiçbir zaman varsayılan ilkeleri olmayan Güvenli Bağlantılar ve Güvenli Ekler için varsayılan ilkeler sağlar.

  **Yerleşik koruma** için, tüm Office 365 için Defender müşteriler için önceden ayarlanmış güvenlik ilkesi varsayılan olarak açıktır. Bunu önermesek de, korumanın belirli kullanıcılara uygulanmaması için **Kullanıcılar**, **Gruplar** ve **Etki Alanları** temelinde özel durumlar da yapılandırabilirsiniz.

İlkeleri kullanıcılara atayana kadar **, Standart** ve **Katı** önceden ayarlanmış güvenlik ilkeleri kimseye atanamaz. Buna karşılık, **yerleşik koruma** önceden ayarlanmış güvenlik ilkesi varsayılan olarak tüm alıcılara atanır, ancak özel durumları yapılandırabilirsiniz.

### <a name="policies-in-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkelerindeki ilkeler

Önceden ayarlanmış güvenlik ilkeleri, EOP ve Office 365 için Microsoft Defender'deki çeşitli koruma özelliklerine karşılık gelen ilkeleri kullanır. Bu ilkeler, kullanıcılara **Standart koruma** veya **Katı koruma** önayarlı güvenlik ilkeleri _atandıktan sonra_ oluşturulur. Bu ilkelerdeki ayarları değiştiremezsiniz.

- **Exchange Online Protection (EOP) ilkeleri**: Bu ilkeler, Exchange Online posta kutularına ve Exchange Online posta kutusu olmayan tek başına EOP kuruluşlarına sahip tüm Microsoft 365 kuruluşlarında bulunur:

  - **Standart Önceden Ayarlanmış Güvenlik İlkesi** ve **Katı Önceden Ayarlanmış Güvenlik İlkesi** adlı [istenmeyen posta önleme ilkeleri](configure-your-spam-filter-policies.md).
  - **Standart Önceden Ayarlanmış Güvenlik İlkesi** ve **Katı Ön Ayarlı Güvenlik İlkesi** adlı [kötü amaçlı yazılımdan koruma ilkeleri](configure-anti-malware-policies.md).
  - **Standart Önceden Ayarlanmış Güvenlik İlkesi ve Katı Ön Ayarlı Güvenlik İlkesi** (kimlik sahtekarlığı ayarları)  adlı [kimlik avı önleme ilkeleri](set-up-anti-phishing-policies.md#spoof-settings) (kimlik sahtekarlığı koruması).

  > [!NOTE]
  > Giden istenmeyen posta ilkeleri önceden ayarlanmış güvenlik ilkelerinin bir parçası değildir. Varsayılan giden istenmeyen posta ilkesi, önceden ayarlanmış güvenlik ilkelerinin üyelerini otomatik olarak korur. Alternatif olarak, önceden ayarlanmış güvenlik ilkelerinin üyeleri için korumayı özelleştirmek için özel giden istenmeyen posta ilkeleri oluşturabilirsiniz. Daha fazla bilgi için bkz. [EOP'de giden istenmeyen posta filtrelemeyi yapılandırma](configure-the-outbound-spam-policy.md).

- **Office 365 için Microsoft Defender ilkeleri**: Bu ilkeler, Microsoft 365 E5 veya Office 365 için Defender eklenti abonelikleri olan kuruluşlarda bulunur:
  - standart **önayar güvenlik ilkesi** ve **katı önceden ayarlanmış güvenlik** ilkesi adlı Office 365 için Defender kimlik avı önleme ilkeleri, şunlardır:
    - EOP kimlik avı önleme ilkelerinde kullanılabilen kimlik sahtekarlığı [ayarlarının](set-up-anti-phishing-policies.md#spoof-settings) aynısı.
    - [Kimliğe bürünme ayarları](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Gelişmiş kimlik avı eşikleri](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - **Standart Önceden Ayarlanmış Güvenlik İlkesi**, **Katı Önceden Ayarlanmış Güvenlik İlkesi** ve **Yerleşik Koruma İlkesi** adlı [Güvenli Bağlantılar ilkeleri](set-up-safe-links-policies.md).
  - **Standart Önceden Ayarlanmış Güvenlik İlkesi**, **Katı Önceden Ayarlanmış Güvenlik İlkesi** ve **Yerleşik Koruma İlkesi** adlı [Güvenli Ekler ilkeleri](set-up-safe-attachments-policies.md).

EOP korumalarını Office 365 için Defender korumalardan farklı kullanıcılara uygulayabilir veya aynı alıcılara EOP ve Office 365 için Defender uygulayabilirsiniz.

### <a name="policy-settings-in-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkelerindeki ilke ayarları

Koruma profillerindeki ilke ayarlarını değiştiremezsiniz. **Standart**, **Katı** ve **Yerleşik koruma** ilkesi ayarı değerleri [, EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](recommended-settings-for-eop-and-office365.md) bölümünde açıklanmıştır.

> [!NOTE]
> Office 365 için Defender korumalarında, [kullanıcı kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) için gönderenleri ve [etki alanı kimliğe bürünme](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) koruması için iç veya dış etki alanlarını tanımlamanız gerekir.
>
> Sahip olduğunuz tüm etki alanları ([kabul edilen etki alanları](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)), önceden ayarlanmış güvenlik ilkelerinde etki alanı kimliğe bürünme korumasını otomatik olarak alır.
>
> Tüm alıcılar, önceden ayarlanmış güvenlik ilkelerinde [posta kutusu zekasından](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) otomatik olarak kimliğe bürünme koruması alır.

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Önceden ayarlanmış güvenlik ilkeleri ve diğer ilkeler için öncelik sırası

Kullanıcıya birden çok ilke uygulandığında, aşağıdaki sıra en yüksek öncelikliden en düşük önceliğe uygulanır:

1. Kesin önceden ayarlanmış güvenlik ilkesi.
2. Standart önceden ayarlanmış güvenlik ilkesi.
3. Özel ilkeler. Özel ilkeler, ilkenin öncelik değerine göre uygulanır.
4. Güvenli Bağlantılar ve Güvenli Ekler için yerleşik koruma önceden ayarlanmış güvenlik ilkesi; kötü amaçlı yazılımdan koruma, istenmeyen posta önleme ve kimlik avı önleme için varsayılan ilkeler.

Başka bir deyişle, **Katı** önceden ayarlanmış güvenlik ilkesinin ayarları **Standart önceden ayarlanmış** güvenlik ilkesinin ayarlarını geçersiz kılar. Bu ilkeler, Güvenli Bağlantılar ve Güvenli Ekler için **yerleşik koruma** önceden ayarlanmış güvenlik ilkesinin ayarlarını ve istenmeyen posta, kötü amaçlı yazılımdan koruma ve kimlik avı önleme için varsayılan ilkeleri geçersiz kılar.

Örneğin, **Standart korumada** bir güvenlik ayarı vardır ve yönetici **Standart koruma** için bir kullanıcı belirtir. **Standart koruma** ayarı, özel bir ilkede veya aynı kullanıcı için varsayılan ilkede bu ayar için yapılandırılan ayar yerine kullanıcıya uygulanır.

**Standart** veya **Katı** ön ayarlı güvenlik ilkelerini kullanıcıların bir alt kümesine uygulamak ve belirli gereksinimleri karşılamak için kuruluşunuzdaki diğer kullanıcılara özel ilkeler uygulamak isteyebilirsiniz. Bu gereksinimi karşılamak için aşağıdaki adımları uygulayın:

- **Standart** önceden ayarlanmış güvenlik ilkesinin ve özel ilkelerin ayarlarını alması gereken kullanıcıları **Katı** ön ayarlı güvenlik ilkesinde özel durumlar olarak yapılandırın.
- Özel ilkelerin ayarlarını alması gereken kullanıcıları **Standart** önceden ayarlanmış güvenlik ilkesinde özel durumlar olarak yapılandırın.

**Yerleşik koruma** , mevcut Güvenli Bağlantılar veya Güvenli Ekler ilkelerindeki alıcıları etkilemez. **Standart koruma**, **Katı koruma** veya özel Güvenli Bağlantılar veya Güvenli Ekler ilkelerini zaten yapılandırdıysanız, bu ilkeler _her zaman_ **Yerleşik korumadan** _önce_ uygulanır, bu nedenle bu önceden ayarlanmış veya özel ilkelerde zaten tanımlanmış olan alıcıları etkilemez.

## <a name="assign-preset-security-policies-to-users"></a>Kullanıcılara önceden ayarlanmış güvenlik ilkeleri atama

### <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. **Önceden ayarlanmış güvenlik ilkeleri** sayfasına doğrudan gitmek için kullanın<https://security.microsoft.com/presetSecurityPolicies>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Bu makaledeki yordamları gerçekleştirebilmeniz için **önce Exchange Online'de** izinlerin atanmış olması gerekir:
  - Önceden ayarlanmış güvenlik ilkelerini yapılandırmak için **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol gruplarının üyesi olmanız gerekir.
  - Önceden ayarlanmış güvenlik ilkelerine salt okunur erişim için **Genel Okuyucu** rol grubunun üyesi olmanız gerekir.

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  **Not**: kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri _ve_ izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users"></a>Kullanıcılara Standart ve Katı önceden ayarlanmış güvenlik ilkeleri atamak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>**, Şablonlu ilkeler** bölümündeki **Email & İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Önceden Ayarlanmış Güvenlik İlkeleri'ne** gidin. **Önceden ayarlanmış güvenlik ilkeleri** sayfasına doğrudan gitmek için kullanın<https://security.microsoft.com/presetSecurityPolicies>.

2. **Önceden ayarlanmış güvenlik ilkeleri** sayfasında **, Standart koruma** veya **Katı koruma** bölümlerinde **Yönet'e** tıklayın.

3. **Standart koruma uygulama** veya **Katı koruma uygulama** sihirbazı açılır öğede başlar.

   **Exchange Online Protection Uygula** sayfasında, [EOP korumalarının uygulandığı iç alıcıları](#policies-in-preset-security-policies) tanımlayın (alıcı koşulları):
   - **Tüm alıcılar**
   - **Belirli alıcılar**:
     - **Kullanıcılar**
     - **Gruplar**:
       - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
       - Belirtilen Microsoft 365 Grupları.

       Dinamik dağıtım grupları desteklenmez.

   - **Etki alanları**

     Uygun kutuya tıklayın, bir değer yazmaya başlayın ve sonuçlardan istediğiniz değeri seçin. Bu işlemi gerektiği kadar tekrarlayın. Mevcut bir değeri kaldırmak için Kaldır'a tıklayın ![Kaldır simgesi.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.

     Kullanıcılar veya gruplar için çoğu tanımlayıcıyı (ad, görünen ad, diğer ad, e-posta adresi, hesap adı vb.) kullanabilirsiniz, ancak sonuçlarda ilgili görünen ad gösterilir. Kullanıcılar için, tüm kullanılabilir değerleri görmek için tek başına bir yıldız işareti (\*) girin.

   - **Yok**

   - **Bu alıcıları dışla**: İlkenin geçerli olduğu iç alıcılara özel durumlar eklemek için (alıcı özel durumları), bu seçeneği belirleyin ve özel durumları yapılandırın. Ayarlar ve davranış, koşullara tam olarak benzer.

   İşiniz bittiğinde **İleri'ye** tıklayın.

   > [!NOTE]
   > Office 365 için Defender olmayan kuruluşlarda **İleri'ye** tıklamak sizi **Gözden Geçir** sayfasına götürür. **Gözden Geçir** sayfasından önceki kalan adımlar/sayfalar yalnızca Office 365 için Defender sahip kuruluşlarda kullanılabilir.

4. **Office 365 için Defender korumasını uygula** sayfasında, [Office 365 için Defender korumalarının](#policies-in-preset-security-policies) geçerli olduğu iç alıcıları (alıcı koşulları) tanımlayın.

   Ayarlar ve davranış, önceki adımda **EOP korumalarının uygulandığı sayfaya** tam olarak benzer.

   Önceki sayfada EOP koruması için seçtiğiniz **alıcıları** kullanmak için Önceden seçilen alıcılar'ı da seçebilirsiniz.

   İşiniz bittiğinde **İleri'ye** tıklayın.

5. **Kimliğe Bürünme koruması** sayfasında **İleri'ye** tıklayın.

6. **Saldırganlar tarafından kimliğe bürünüldiğinde bayrak eklemek için e-posta adresleri ekleyin** sayfasında, [kullanıcı kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) tarafından korunan iç ve dış gönderenleri ekleyin.

   > [!NOTE]
   > Tüm alıcılar, önceden ayarlanmış güvenlik ilkelerinde [posta kutusu zekasından](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) otomatik olarak kimliğe bürünme koruması alır.

   Her giriş bir görünen ad ve bir e-posta adresinden oluşur. Kutulara her değeri girin ve **Ekle'ye** tıklayın. Bu adımı gerektiği kadar tekrarlayın.

   En fazla 301 kullanıcı belirtebilir ve birden çok ilkedeki kullanıcı kimliğe bürünme koruması ayarlarında aynı kullanıcıyı belirtemezsiniz.

   Listeden var olan bir girdiyi kaldırmak için ![Kullanıcıyı kimliğe bürünme koruması simgesinden kaldırın.](../../media/m365-cc-sc-remove.png).

   İşiniz bittiğinde **İleri'ye** tıklayın.

7. **Saldırganlar tarafından kimliğe bürünüldiğinde bayrak eklemek için etki alanları ekle** sayfasında, [etki alanı kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) tarafından korunan iç ve dış etki alanları ekleyin.

   > [!NOTE]
   > Sahip olduğunuz tüm etki alanları ([kabul edilen etki alanları](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)), önceden ayarlanmış güvenlik ilkelerinde etki alanı kimliğe bürünme korumasını otomatik olarak alır.

   Belirtilen etki alanlarındaki tüm gönderenler etki alanı kimliğe bürünme koruması tarafından korunur.

   Kutuya etki alanını girin ve **Ekle'ye** tıklayın. Bu adımı gerektiği kadar tekrarlayın.

   Listeden var olan bir girdiyi kaldırmak için girdiyi seçin ve ardından ![Kimliğe bürünme koruması simgesinden etki alanını kaldırın.](../../media/m365-cc-sc-remove.png).

   Tüm kimlik avı önleme ilkelerinde etki alanı kimliğe bürünme koruması için belirtebileceğiniz en fazla etki alanı sayısı 50'dir.

   İşiniz bittiğinde **İleri'ye** tıklayın.

8. **Kimliğe bürünme olarak işaretlememek için güvenilen e-posta adresleri ve etki alanları ekle sayfasında, kimliğe bürünme** korumasının dışında tutulmasını istediğiniz gönderen e-posta adreslerini ve etki alanlarını girin. Bu gönderenlerden gelen iletiler hiçbir zaman kimliğe bürünme saldırısı olarak işaretlenmez, ancak gönderenler EOP ve Office 365 için Defender'deki diğer filtreler tarafından taramaya devam eder.

   Kutuya e-posta adresini veya etki alanını girin ve **Ekle'ye** tıklayın. Bu adımı gerektiği kadar tekrarlayın.

   Listeden var olan bir girdiyi kaldırmak için girdiyi seçin ve ardından ![Kimliğe bürünme koruması simgesinin özel durumlarını kaldırın.](../../media/m365-cc-sc-remove.png).

   İşiniz bittiğinde **İleri'ye** tıklayın.

9. **Bu ilkeyi gözden geçir ve onayla** sayfasında seçimlerinizi doğrulayın ve **onayla'ya** tıklayın.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-standard-and-strict-preset-security-policies"></a>Standart ve Katı önceden ayarlanmış güvenlik ilkelerinin atamalarını değiştirmek için Microsoft 365 Defender portalını kullanın

**Standart koruma** veya **Katı koruma** önayarlı güvenlik ilkesinin atamasını değiştirme adımları, [kullanıcılara önceden ayarlanmış güvenlik ilkelerini ilk atadığınız](#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users) zamanki adımlarla aynıdır.

Mevcut koşulları ve özel durumları korurken **Standart koruma** veya **Katı koruma** önayarlı güvenlik ilkelerini devre dışı bırakmak için iki **durumlu düğmeyi Devre Dışı** ![Geçiş Kapalı.](../../media/scc-toggle-off.png). İlkeleri etkinleştirmek için iki **durumlu düğmeyi Etkin İki Durumlu** ![Düğme Açık](../../media/scc-toggle-on.png) olarak kaydırın.

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-the-built-in-protection-preset-security-policy"></a>Yerleşik koruma önceden ayarlanmış güvenlik ilkesinin atamalarını değiştirmek için Microsoft 365 Defender portalını kullanın

**Yerleşik koruma** önayarlı güvenlik ilkesinin tüm alıcılara atandığını ve **Standart koruma** veya **Katı** koruma önayarlı güvenlik ilkeleri ya da özel Güvenli Bağlantılar veya Güvenli Ekler ilkelerinde tanımlanan alıcıları etkilemediği unutmayın.

Bu nedenle, **genellikle Yerleşik koruma** önayarlı güvenlik ilkesi için özel durumlar önermeyiz.

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>**, Şablonlu ilkeler** bölümündeki **Email & İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Önceden Ayarlanmış Güvenlik İlkeleri'ne** gidin. **Önceden ayarlanmış güvenlik ilkeleri** sayfasına doğrudan gitmek için kullanın<https://security.microsoft.com/presetSecurityPolicies>.

2. **Önceden ayarlanmış güvenlik ilkeleri** sayfasında **Yerleşik koruma** bölümünde **Dışlama ekle (önerilmez)** seçeneğini belirleyin.

3. Görüntülenen **Yerleşik korumanın dışında bırak** açılır penceresinde, yerleşik Güvenli Bağlantılar ve Güvenli Ekler korumasının dışında tutulan iç alıcıları tanımlayın:
   - **Kullanıcılar**
   - **Gruplar**:
       - Belirtilen dağıtım gruplarının veya posta özellikli güvenlik gruplarının üyeleri.
       - Belirtilen Microsoft 365 Grupları.

     Dinamik dağıtım grupları desteklenmez.

   - **Etki alanları**

   Uygun kutuya tıklayın, bir değer yazmaya başlayın ve sonuçlardan istediğiniz değeri seçin. Bu işlemi gerektiği kadar tekrarlayın. Mevcut bir değeri kaldırmak için Kaldır'a tıklayın ![Yerleşik koruma simgesinden dışlamaları kaldırın.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.

   Kullanıcılar veya gruplar için çoğu tanımlayıcıyı (ad, görünen ad, diğer ad, e-posta adresi, hesap adı vb.) kullanabilirsiniz, ancak sonuçlarda ilgili görünen ad gösterilir. Kullanıcılar için, tüm kullanılabilir değerleri görmek için tek başına bir yıldız işareti (\*) girin.

   Bitirdiğinizde, **Kaydet**'i tıklatın.

### <a name="how-do-you-know-these-procedures-worked"></a>Bu yordamların işe yaramış olduğunu nasıl anlarsınız?

Kullanıcıya **Standart koruma** veya **Katı koruma** güvenlik ilkesini başarıyla atadığınızdan emin olmak için, varsayılan değerin **Standart koruma** ayarından farklı olduğu ve **Katı koruma** ayarından farklı olduğu bir koruma ayarı kullanın.

Örneğin, istenmeyen posta (yüksek güvenilir istenmeyen posta değil) olarak algılanan e-postalar için, iletinin **Standart koruma** kullanıcıları için Gereksiz Email klasörüne teslim edilmiş ve **Katı koruma** kullanıcıları için karantinaya alınmış olduğunu doğrulayın.

Ya da [toplu posta](bulk-complaint-level-values.md) için, BCL değerinin 6 veya üzerinin iletiyi **Standart koruma** kullanıcıları için Gereksiz Email klasörüne teslim ettiğini ve BCL değeri 4 veya üzerinin iletiyi **Katı koruma** kullanıcıları için karantinaya alındığını doğrulayın.

## <a name="preset-security-policies-in-exchange-online-powershell"></a>Exchange Online PowerShell'de önceden ayarlanmış güvenlik ilkeleri

PowerShell'de önceden ayarlanmış güvenlik ilkeleri aşağıdaki öğelerden oluşur:

- **Bireysel güvenlik ilkeleri**: Örneğin kötü amaçlı yazılımdan koruma ilkeleri, istenmeyen posta önleme ilkeleri, kimlik avı önleme ilkeleri, Güvenli Bağlantılar ilkeleri ve Güvenli Ekler ilkeleri.

  > [!WARNING]
  > Önceden ayarlanmış güvenlik ilkeleriyle ilişkili tek tek güvenlik ilkelerini oluşturmayı, değiştirmeyi veya kaldırmayı denemeyin. Standart veya Katı önceden belirlenmiş güvenlik ilkeleri için tek tek güvenlik ilkeleri oluşturmak için desteklenen tek yöntem, Microsoft 365 Defender portalında önceden ayarlanmış güvenlik ilkesini ilk kez açmaktır.

- **Kurallar**: Standart önceden ayarlanmış güvenlik ilkesi, Katı önceden ayarlanmış güvenlik ilkesi ve Yerleşik koruma önayarlı güvenlik ilkesi için ayrı kurallar, ilkeler için alıcı koşullarını ve özel durumlarını tanımlar (ilke korumalarının uygulandığı alıcıları belirleyin).

  Standart ve Katı önceden belirlenmiş güvenlik ilkeleri için bu kurallar, Microsoft 365 Defender portalında önceden ayarlanmış güvenlik ilkesini ilk kez açtığınızda oluşturulur. Önceden ayarlanmış güvenlik ilkesini hiç açmıyorsanız ilişkili kurallar mevcut değildir. Daha sonra önceden ayarlanmış güvenlik ilkesini kapatmak ilişkili kuralları silmez.

  Yerleşik koruma önceden ayarlanmış güvenlik ilkesi, ilkenin varsayılan Güvenli Bağlantılar ve Güvenli Ekler koruması özel durumlarını denetleen tek bir kurala sahiptir.

  Standart ve Katı önceden ayarlanmış güvenlik ilkeleri aşağıdaki kurallara sahiptir:

  - **Exchange Online Protection (EOP) korumaları için kurallar**: Standart Ön Ayar güvenlik ilkesi kuralı ve Katı önceden ayarlanmış güvenlik ilkesi kuralı, ilkedeki EOP korumalarının (kötü amaçlı yazılımdan koruma, istenmeyen posta ve kimlik avı önleme) kime uygulanacağını denetler (EOP korumaları için alıcı koşulları ve özel durumları).
  - **Office 365 için Defender koruma kuralları**: Standart Önceden Ayarlanmış güvenlik ilkesi kuralı ve Katı önceden ayarlanmış güvenlik ilkesi kuralı, ilkedeki Office 365 için Defender korumalarının (Güvenli Bağlantılar ve Güvenli Ekler) kime uygulanacağını denetler (alıcı koşulları ve özel durumları Office 365 için Defender korumalar).

  Standart ve Katı önceden belirlenmiş güvenlik ilkeleri kuralları, ilkelerle ilişkili kuralları etkinleştirerek veya devre dışı bırakarak önceden ayarlanmış güvenlik ilkesini açmanıza veya açmanıza da olanak tanır.

  Önceden ayarlanmış güvenlik ilkelerine yönelik kurallar, tek tek güvenlik ilkeleri için çalışan normal kural cmdlet'lerinde kullanılamaz (örneğin, **Get-AntiPhishRule**). Bunun yerine aşağıdaki cmdlet'ler gereklidir:

  - Yerleşik koruma önceden ayarlanmış güvenlik ilkesi: **\*-ATPBuiltInProtectionRule** cmdlet'leri.
  - Standart ve katı önceden ayarlanmış güvenlik ilkeleri: **\*-EOPProtectionPolicyRule** ve **\*-ATPProtectionPolicyRule** cmdlet'leri.

Aşağıdaki bölümlerde, **desteklenen senaryolarda** bu cmdlet'lerin nasıl kullanılacağı açıklanmaktadır.

Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="use-powershell-to-view-individual-security-policies-for-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkeleri için tek tek güvenlik ilkelerini görüntülemek için PowerShell kullanma

Microsoft 365 Defender portalında Standart önceden ayarlanmış güvenlik ilkesini veya Katı ön ayarlı güvenlik ilkesini hiç etkinleştirmediyseniz, önceden ayarlanmış güvenlik ilkesi için ilişkili güvenlik ilkelerinin mevcut olmadığını unutmayın.

> [!WARNING]
> Önceden ayarlanmış güvenlik ilkeleriyle ilişkili tek tek güvenlik ilkelerini oluşturmayı, değiştirmeyi veya kaldırmayı denemeyin. Standart veya Katı önceden belirlenmiş güvenlik ilkeleri için tek tek güvenlik ilkeleri oluşturmak için desteklenen tek yöntem, Microsoft 365 Defender portalında önceden ayarlanmış güvenlik ilkesini ilk kez açmaktır.

- **Yerleşik koruma önceden ayarlanmış güvenlik ilkesi**: İlişkili ilkeler Built-In Koruma İlkesi olarak adlandırılır. Bu ilkeler için IsBuiltInProtection özellik değeri True değeridir.

  Yerleşik koruma önceden ayarlanmış güvenlik ilkesinin tek tek güvenlik ilkelerini görüntülemek için aşağıdaki komutu çalıştırın:

  ```powershell
  Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy -Identity "Built-In Protection Policy" | Format-List; Write-Output -InputObject ("`r`n"*3),"Built-in protection Safe Links policy",("-"*79);Get-SafeLinksPolicy -Identity "Built-In Protection Policy" | Format-List
  ```

- **Standart önceden ayarlanmış güvenlik ilkesi**: İlişkili ilkeler olarak adlandırılır `Standard Preset Security Policy<13-digit number>`. Örneğin, `Standard Preset Security Policy1622650008019`. RecommendPolicyType özellik değeri Standart'tır.

  - **Microsoft 365 için Defender içermeyen kuruluşlar**:

    Microsoft 365 için Defender olmayan kuruluşlarda Standart önceden ayarlanmış güvenlik ilkesinin tek tek güvenlik ilkelerini görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

  - **Microsoft 365 için Defender'a sahip kuruluşlar**:

    Microsoft 365 için Defender'a sahip kuruluşlarda Standart önceden ayarlanmış güvenlik ilkesinin tek tek güvenlik ilkelerini görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Standard anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"; Write-Output -InputObject ("`r`n"*3),"Standard Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Standard"
    ```

- **Kesin önceden ayarlanmış güvenlik ilkesi**: İlişkili ilkeler olarak adlandırılır `Strict Preset Security Policy<13-digit number>`. Örneğin, `Strict Preset Security Policy1642034872546`. RecommendPolicyType özellik değeri Strict değeridir.

  - **Microsoft 365 için Defender içermeyen kuruluşlar**:

    - Microsoft 365 için Defender olmayan kuruluşlarda Katı önceden ayarlanmış güvenlik ilkesinin tek tek güvenlik ilkelerini görüntülemek için aşağıdaki komutu çalıştırın:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
      ```

  - **Microsoft 365 için Defender'a sahip kuruluşlar**:

    - Microsoft 365 için Defender'a sahip kuruluşlarda Katı önceden ayarlanmış güvenlik ilkesinin tek tek güvenlik ilkelerini görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"Strict anti-malware policy",("-"*79);Get-MalwareFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-spam policy",("-"*79);Get-HostedContentFilterPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict anti-phishing policy",("-"*79);Get-AntiPhishPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Attachments policy",("-"*79);Get-SafeAttachmentPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"; Write-Output -InputObject ("`r`n"*3),"Strict Safe Links policy",("-"*79);Get-SafeLinksPolicy | Where-Object -Property RecommendedPolicyType -eq -Value "Strict"
    ```

### <a name="use-powershell-to-view-rules-for-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkelerine yönelik kuralları görüntülemek için PowerShell kullanma

Microsoft 365 Defender portalında Standart önceden ayarlanmış güvenlik ilkesini veya Katı ön ayarlı güvenlik ilkesini hiç etkinleştirmediyseniz, bu ilkelerle ilişkili kuralların mevcut olmadığını unutmayın.

- **Yerleşik koruma önceden ayarlanmış güvenlik ilkesi**: İlişkili kural ATP Built-In Koruma Kuralı olarak adlandırılır.

  Yerleşik koruma önceden ayarlanmış güvenlik ilkesiyle ilişkili kuralı görüntülemek için aşağıdaki komutu çalıştırın:

  ```powershell
  Get-ATPBuiltInProtectionRule
  ```

  Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-ATPBuiltInProtectionRule](/powershell/module/exchange/get-atpbuiltinprotectionrule).

- **Standart önceden ayarlanmış güvenlik ilkesi**: İlişkili kurallar Standart Önceden Ayarlanmış Güvenlik İlkesi olarak adlandırılır.

  Standart önceden ayarlanmış güvenlik ilkesiyle ilişkili kuralları görüntülemek için aşağıdaki komutları kullanın:

  - Standart önceden ayarlanmış güvenlik ilkesinde EOP korumalarıyla ilişkili kuralı görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - Standart önceden ayarlanmış güvenlik ilkesinde Office 365 için Defender korumalarıyla ilişkili kuralı görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

  - Her iki kuralı da aynı anda görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Standard preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
    ```

- **Katı önceden ayarlanmış güvenlik ilkesi**: İlişkili kurallar Katı Önceden Belirlenmiş Güvenlik İlkesi olarak adlandırılır.

  Katı önceden ayarlanmış güvenlik ilkesiyle ilişkili kuralları görüntülemek için aşağıdaki komutları kullanın:

  - Katı önceden ayarlanmış güvenlik ilkesinde EOP korumalarıyla ilişkili kuralı görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - Katı önceden ayarlanmış güvenlik ilkesinde Office 365 için Defender korumalarıyla ilişkili kuralı görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

  - Her iki kuralı da aynı anda görüntülemek için aşağıdaki komutu çalıştırın:

    ```powershell
    Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*79);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Write-Output -InputObject ("`r`n"*3),"Defender for Office 365 rule - Strict preset security policy",("-"*79);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
    ```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-EOPProtectionPolicyRule](/powershell/module/exchange/get-eopprotectionpolicyrule) ve [Get-ATPProtectionPolicyRule](/powershell/module/exchange/get-atpprotectionpolicyrule).

### <a name="use-powershell-to-turn-on-or-turn-off-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkelerini açmak veya kapatmak için PowerShell kullanma

Daha önce açıklandığı gibi, Standart veya Katı önceden ayarlanmış güvenlik ilkelerini açmak veya kapatmak için, ilkeyle ilişkili kuralları etkinleştirir veya devre dışı bırakırsınız. Kuralın State özellik değeri, kuralın Etkin mi yoksa Devre Dışı mı olduğunu gösterir.

Kuruluşunuzun Office 365 için Defender sahip olup olmamasına bağlı olarak, önceden ayarlanmış güvenlik ilkesini açmak veya kapatmak için bir kuralı (EOP korumaları kuralı) veya iki kuralı (EOP korumaları için bir kural ve Office 365 için Defender korumalar için bir kural) etkinleştirmeniz veya devre dışı bırakmanız gerekebilir.

- **Standart önceden ayarlanmış güvenlik ilkesi**:

  - **Office 365 için Defender olmayan kuruluşlar**:

    - Office 365 için Defender olmayan kuruluşlarda, Standart önayar ilkesi kuralının şu anda etkin mi yoksa devre dışı mı olduğunu belirlemek için aşağıdaki komutu çalıştırın:

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - Açıksa Standart önceden ayarlanmış güvenlik ilkesini kapatmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - Kapalıysa Standart önceden ayarlanmış güvenlik ilkesini açmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

  - **Office 365 için Defender olan kuruluşlar**:

    - Office 365 için Defender olan kuruluşlarda, Standart önayar ilkesi kurallarının şu anda etkin mi yoksa devre dışı mı olduğunu belirlemek için aşağıdaki komutu çalıştırın:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Standard preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Standard preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy" | Format-Table Name,State
      ```

    - Açıksa Standart önceden ayarlanmış güvenlik ilkesini kapatmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

    - Kapalıysa Standart önceden ayarlanmış güvenlik ilkesini açmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy"
      ```

- **Kesin önceden ayarlanmış güvenlik ilkesi**:

  - **Office 365 için Defender olmayan kuruluşlar**:

    - Office 365 için Defender olan kuruluşlarda, Katı önayar ilkesi kuralının şu anda etkin mi yoksa devre dışı mı olduğunu belirlemek için aşağıdaki komutu çalıştırın:

      ```powershell
      Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - Açıksa Katı önceden ayarlanmış güvenlik ilkesini kapatmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - Kapalıysa Katı önceden ayarlanmış güvenlik ilkesini açmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

  - **Office 365 için Defender olan kuruluşlar**:

    - Office 365 için Defender olan kuruluşlarda, Katı önceden ayarlanmış ilke kurallarının şu anda etkin mi yoksa devre dışı mı olduğunu belirlemek için aşağıdaki komutu çalıştırın:

      ```powershell
      Write-Output -InputObject ("`r`n"*3),"EOP rule - Strict preset security policy",("-"*63);Get-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State; Write-Output -InputObject `r`n,"Defender for Office 365 rule - Strict preset security policy",("-"*63);Get-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy" | Format-Table Name,State
      ```

    - Açıksa Katı önceden ayarlanmış güvenlik ilkesini kapatmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Disable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Disable-ATPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

    - Kapalıysa Katı önceden ayarlanmış güvenlik ilkesini açmak için aşağıdaki komutu çalıştırın:

      ```powershell
      Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"; Enable-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy"
      ```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Enable-EOPProtectionPolicyRule](/powershell/module/exchange/enable-eopprotectionpolicyrule), [Enable-ATPProtectionPolicyRule](/powershell/module/exchange/enable-atpprotectionpolicyrule), [Disable-EOPProtectionPolicyRule](/powershell/module/exchange/disable-eopprotectionpolicyrule) ve [Disable-ATPProtectionPolicyRule](/powershell/module/exchange/disable-atpprotectionpolicyrule).

### <a name="use-powershell-to-specify-recipient-conditions-and-exceptions-for-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkeleri için alıcı koşullarını ve özel durumlarını belirtmek için PowerShell kullanma

> [!IMPORTANT]
  > Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. Önceden ayarlanmış güvenlik ilkesi _yalnızca_ belirtilen alıcı filtrelerinin _tümüyle_ eşleşen alıcılara uygulanır. Örneğin, ilkede aşağıdaki değerlerle bir alıcı filtresi koşulu yapılandırabilirsiniz:
  >
  > - Kullanıcılar: romain@contoso.com
  > - Gruplar: Yöneticiler
  >
  > İlke, _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse ilke ona uygulanmaz.
  >
  > Benzer şekilde, ilkenin özel durumu olarak aynı alıcı filtresini kullanırsanız, ilke _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, ilke hala onun için geçerlidir.

Yerleşik koruma önceden ayarlanmış güvenlik ilkesi için yalnızca alıcı özel durumlarını belirtebilirsiniz. Tüm özel durum parametresi değerleri boşsa (`$null` ), ilkede özel durum yoktur.

Standart ve Katı önceden ayarlanmış güvenlik ilkeleri için, EOP korumaları ve Office 365 için Defender korumaları için alıcı koşullarını ve özel durumlarını belirtebilirsiniz. Tüm koşullar ve özel durum parametresi değerleri boşsa (`$null` ), Standart veya Katı önceden ayarlanmış güvenlik ilkelerinin alıcı koşulları veya özel durumları yoktur.

Önceden ayarlanmış bir güvenlik ilkesine hiçbir alıcı koşulu veya özel durum uygulanmamış olsa bile, ilkenin tüm alıcılara uygulanıp uygulanmadığı, bu makalede daha önce açıklandığı gibi [ilkelerin öncelik sırasına](#order-of-precedence-for-preset-security-policies-and-other-policies) bağlıdır.

- **Yerleşik koruma önceden ayarlanmış güvenlik ilkesi**:

  Aşağıdaki sözdizimini kullanın:

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null>
  ```

  Bu örnek, yerleşik koruma önceden ayarlanmış güvenlik ilkesinden tüm alıcı özel durumlarını kaldırır.

  ```powershell
  Set-ATPBuiltInProtectionRule -Identity "ATP Built-In Protection Rule" -ExceptIfRecipientDomainIs $null -ExceptIfSentTo $null -ExceptIfSentToMemberOf $null
  ```

  Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-ATPBuiltInProtectionRule](/powershell/module/exchange/set-atpbuiltinprotectionrule).

- **Standart veya Katı önceden ayarlanmış güvenlik ilkeleri**

  Aşağıdaki sözdizimini kullanın:

  ```powershell
  <Set-EOPProtectionPolicyRule | SetAtpProtectionPolicyRule> -Identity "<Standard Preset Security Policy | Strict Preset Security Policy>" -SentTo <"user1","user2",... | $null> -ExceptIfSentTo <"user1","user2",... | $null> -SentToMemberOf <"group1","group2",... | $null> -ExceptIfSentToMemberOf <"group1","group2",... | $null> -RecipientDomainIs <"domain1","domain2",... | $null> -ExceptIfRecipientDomainIs <"domain1","domain2",... | $null>
  ```

  Bu örnekte, Yöneticiler adlı dağıtım grubunun üyeleri için Standart önceden ayarlanmış güvenlik ilkesindeki EOP korumalarından özel durumlar yapılandırılır.

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Standard Preset Security Policy" -ExceptIfSentToMemberOf Executives
  ```

  Bu örnekte, belirtilen güvenlik işlemleri (SecOps) posta kutuları için Katı önceden ayarlanmış güvenlik ilkesindeki Office 365 için Defender korumalarından özel durumlar yapılandırılır.

  ```powershell
  Set-EOPProtectionPolicyRule -Identity "Strict Preset Security Policy" -ExceptIfSentTo "SecOps1","SecOps2"
  ```

  Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Set-EOPProtectionPolicyRule](/powershell/module/exchange/set-eopprotectionpolicyrule) ve [Set-ATPProtectionPolicyRule](/powershell/module/exchange/Set-atpprotectionpolicyrule).
