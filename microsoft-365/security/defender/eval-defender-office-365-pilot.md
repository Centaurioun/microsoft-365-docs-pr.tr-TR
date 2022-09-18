---
title: Pilot Office 365 için Microsoft Defender, değerlendirmeyi üretim ortamınızda kullanın
description: Office 365 için Microsoft Defender özelliklerini düzgün bir şekilde test etmek için Değerlendirmenizi etkin ve mevcut kullanıcı gruplarıyla pilot uygulama adımları.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.custom: admindeeplinkEXCHANGE
ms.topic: how-to
ms.openlocfilehash: 72197d6543a297bf5b17c48e5d26fb29059e9d64
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67798989"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Pilot Office 365 için Microsoft Defender

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Office 365 için Microsoft Defender için değerlendirme ortamını ayarlama [sürecindeki Adım 3/3'tür](eval-defender-office-365-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-office-365-overview.md) bakın.

Office 365 için Microsoft Defender için pilotu ayarlamak ve yapılandırmak için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Office 365 için Microsoft Defender portalında pilot oluşturma adımları." lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [1. Adım: Pilot gruplar oluşturma](#step-1-create-pilot-groups)
- [2. Adım: Korumayı yapılandırma](#step-2-configure-protection)
- [3. Adım: Özellikleri deneyin — Simülasyon, izleme ve ölçümler hakkında bilgi edinin](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Office 365 için Microsoft Defender değerlendirirken, kuruluşunuzun tamamı için ilkeleri etkinleştirmeden ve zorunlu tutmadan önce belirli kullanıcılara pilot uygulamayı seçebilirsiniz. Dağıtım grupları oluşturmak, dağıtım işlemlerini yönetmeye yardımcı olabilir. Örneğin, *Office 365 için Defender Kullanıcıları - Standart Koruma*, *Office 365 için Defender Kullanıcılar - Katı Koruma*, *Office 365 için Defender Kullanıcılar - Özel Koruma* gibi gruplar oluşturun veya *Office 365 için Defender Kullanıcıları - Özel Durumlar*.

Bu gruplar için neden "Standart" ve "Katı" terimlerinin kullanıldığı açık olmayabilir, ancak Office 365 için Defender güvenlik ön ayarları hakkında daha fazla bilgi edindiğinizde bu durum netleşir. Grupların "özel" ve "özel durumlar" olarak adlandırılması kendileri için geçerlidir ve kullanıcılarınızın çoğu *standart* ve *katı*, özel ve özel durum grupları risk yönetimiyle ilgili olarak sizin için değerli veriler toplar.

## <a name="step-1-create-pilot-groups"></a>1. Adım: Pilot gruplar oluşturma

Dağıtım grupları doğrudan Exchange Online oluşturulabilir ve tanımlanabilir veya şirket içi Active Directory eşitlenebilir.

1. Alıcı Yöneticisi rolü verilmiş veya grup yönetimi izinleri atanmış bir hesabı kullanarak Exchange Yönetici Center'da <https://admin.exchange.microsoft.com> (EAC) oturum açın.
2. **Alıcı Grupları'na** \> gidin.

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" Tıklanacak Gruplar menü öğesi." lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. **Gruplar** sayfasında Grup ekle simgesi'ni seçin![.](../../media/m365-cc-sc-add-internal-icon.png) **Grup ekleyin**.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="Tıklanacak Grup ekle seçeneği." lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. Grup türü için **Dağıtım'ı** seçin ve **İleri'ye** tıklayın.

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" Grup türü seçin bölümü." lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. Gruba bir **Ad** ve isteğe bağlı **Açıklama** verin ve İleri'ye tıklayın.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="Temel bilgileri ayarlama bölümü." lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

6. Kalan sayfalarda bir sahip atayın, gruba üye ekleyin, e-posta adresini, ayrılma kısıtlamalarını ve diğer ayarları ayarlayın.

## <a name="step-2-configure-protection"></a>2. Adım: Korumayı yapılandırma

Office 365 için Defender'daki bazı özellikler varsayılan olarak yapılandırılır ve açılır, ancak güvenlik işlemleri varsayılan koruma düzeyini yükseltmek isteyebilir.

Bazı özellikler *henüz* yapılandırılmadı. Korumayı yapılandırmak için aşağıdaki seçeneklere sahipsiniz:

- **Kullanıcıları önceden belirlenmiş güvenlik ilkelerine atama**: [Önceden ayarlanmış güvenlik ilkeleri](../office-365-security/preset-security-policies.md) , tüm özelliklere hızla tekdüzen bir koruma düzeyi atamak için bir yöntem olarak sağlanır. **Standart** veya **Katı** koruma arasından seçim yapabilirsiniz. Buradaki avantajı, kullanıcı gruplarını mümkün olan en kısa sürede korumanızdır. Buradaki dezavantaj, önceden ayarlanmış güvenlik ilkelerindeki ayarların çoğunu özelleştirememenizdir (örneğin, **alıcıların Gereksiz Email klasörlerine teslim** etme eylemini **Karantina** veya tersi olarak değiştiremezsiniz). Önceden ayarlanmış güvenlik ilkelerinin özel ilkeler öncesinde *her zaman* uygulandığını da unutmayın. Bu nedenle, herhangi bir özel ilke oluşturmak ve kullanmak istiyorsanız, bu özel ilkelerdeki kullanıcıları önceden ayarlanmış güvenlik ilkelerinin dışında tutmanız gerekir.

- ***Özel* koruma ilkelerini yapılandırma**: Ortamı kendiniz yapılandırmayı tercih ederseniz, [Tehditlere karşı koruma](../office-365-security/protect-against-threats.md) bölümündeki yönergeleri izleyerek hızla bir koruma *temeli* elde edebilirsiniz. Bu yaklaşımla yapılandırılabilir ayarlar hakkında daha fazla bilgi edinebilirsiniz. Ayrıca, ilkeleri daha sonra ince ayarlayabilirsiniz.

  Ayrıca değerlendirmenizin bir parçası olarak özel koruma ilkeleri oluşturabilir ve atayabilirsiniz. İlkeleri özelleştirmeye başlamadan önce, bu koruma ilkelerinin uygulandığı ve uygulandığı önceliği anlamanız önemlidir. Ön ayar uygulandığında bile güvenlik işlemlerinin bazı ilkeler oluşturması ve/veya yapılandırması gerekir.

- **Önceden ayarlanmış güvenlik ilkelerini otomatik olarak atama**: [Önceden ayarlanmış güvenlik ilkeleri](../office-365-security/preset-security-policies.md) , tüm özelliklere hızla tekdüzen bir koruma düzeyi atamak için bir yöntem olarak sağlanır. **_Standard_*_ veya _*_Strict_** arasından seçim yapabilirsiniz. İyi bir yaklaşım, önceden ayarlanmış güvenlik ilkeleriyle başlamak ve ardından özellikler ve kendi benzersiz tehdit ortamınız hakkında daha fazla bilgi edindikçe ilkelerde ince ayar yapmaktır. Buradaki avantaj, kullanıcı gruplarını daha sonra korumayı ayarlama özelliğiyle mümkün olan en hızlı şekilde korumanızdır. (Bu yöntem önerilir.)
- **Temel korumayı el ile yapılandırma**: Ortamı kendiniz yapılandırmayı tercih ederseniz, [Tehditlere karşı koruma](../office-365-security/protect-against-threats.md) yönergelerini izleyerek hızla bir koruma *temeli* elde edebilirsiniz. Bu yaklaşımla yapılandırılabilir ayarlar hakkında daha fazla bilgi edinebilirsiniz. Ayrıca, ilkeleri daha sonra ince ayarlayabilirsiniz.
- ***Özel* koruma ilkelerini yapılandırma**: Değerlendirmenizin bir parçası olarak özel koruma ilkeleri oluşturabilir ve atayabilirsiniz. İlkeleri özelleştirmeye başlamadan önce, bu koruma ilkelerinin uygulandığı ve uygulandığı önceliği anlamanız önemlidir. Güvenlik operasyonlarının, güvenli bağlantılar ve güvenli ekler için güvenlik ilkelerini tanımlamak için önceden ayarlanmış olsa bile bazı ilkeler oluşturması gerekir.

> [!IMPORTANT]
> **Özel koruma ilkelerini yapılandırmanız gerekiyorsa**, burada **Standart** ve **Katı** güvenlik tanımlarını oluşturan değerleri incelemeniz gerekir: [EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](../office-365-security/recommended-settings-for-eop-and-office365.md). Herhangi bir yapılandırma gerçekleşmeden önce görüldüğü gibi varsayılan değerler de listelenir. Özel derlemenizin nerede saptığına ait bir elektronik tablo tutun.

### <a name="assign-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkeleri atama

MDO'yi değerlendirirken *önerilen temel ilkelerle* başlamanızı ve değerlendirme döneminiz boyunca gerektiğinde bunları iyileştirmenizi öneririz.

EOP'de önceden ayarlanmış güvenlik ilkelerini etkinleştirebilir ve hızlı Office 365 için Defender ve değerlendirmenizin bir parçası olarak bunları belirli pilot kullanıcılara veya tanımlı gruplara atayabilirsiniz. Önceden ayarlanmış ilkeler, bağımsız olarak atanabilen temel bir **Standart** koruma şablonu veya daha agresif bir **Katı** koruma şablonu sunar.

Örneğin, alıcılar tanımlı bir *EOP Standart Koruma* grubunun *üyesiyse* ve ardından gruba hesap ekleyerek veya gruptan hesap kaldırarak yönetiliyorsa pilot değerlendirmeler için bir EOP koşulu uygulanabilir.

Benzer şekilde, alıcılar tanımlı Office 365 için Defender *Standart Koruma* grubunun *üyesiyse* ve ardından grup aracılığıyla hesap ekleyerek/kaldırarak yönetiliyorsa pilot değerlendirmeler için Office 365 için Defender bir koşul uygulanabilir.

Tam yönergeler için bkz. [kullanıcılara Standart ve Katı önceden ayarlanmış güvenlik ilkeleri atamak için Microsoft 365 Defender portalını kullanma](../office-365-security/preset-security-policies.md#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

### <a name="configure-custom-protection-policies"></a>Özel koruma ilkelerini yapılandırma

Önceden tanımlanmış *Standart* veya *Katı* Office 365 için Defender ilke şablonları, pilot kullanıcılarınıza önerilen temel korumayı verir. Bununla birlikte, değerlendirmenizin bir parçası olarak özel koruma ilkeleri oluşturabilir ve atayabilirsiniz.

Önceden belirlenmiş güvenlik ilkeleri ve diğer ilkeler için [e-posta korumasının sırası ve önceliği - Office 365 ve](../office-365-security/how-policies-and-protections-are-combined.md) Öncelik sırası bölümünde açıklandığı gibi, bu koruma [ilkelerinin uygulandığında ve](../office-365-security/preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies) uygulandığında uyguladığı önceliklerin farkında olmak *önemlidir*.

Aşağıdaki tabloda özel koruma ilkelerini yapılandırmaya ve atamaya yönelik başvurular ve daha fazla rehberlik sağlanır:

|Ilkesi|Açıklama|Ön ayara dahil<br>güvenlik ilkeleri?|Varsayılan ilke<br>Kullanılabilir?|Başvuru|
|---|---|:---:|:---:|---|
|Bağlantı filtresi ilkeleri|İyi veya kötü kaynak e-posta sunucularını IP adresine göre tanımlayın.|Hayır|Evet|[EOP'de varsayılan bağlantı filtresi ilkesini yapılandırma](../office-365-security/configure-the-connection-filter-policy.md)|
|Giden istenmeyen posta filtresi ilkeleri|Giden ileti hızı sınırlarını belirtin ve dış e-posta iletmeyi kontrol edin.|Hayır|Evet|[EOP'de giden istenmeyen posta filtrelemeyi yapılandırma](../office-365-security/configure-the-outbound-spam-policy.md)|
|Kötü amaçlı yazılımdan koruma ilkeleri|Hangi eylemlerin gerçekleştirilmesi ve kötü amaçlı yazılım algılandığında kime bildirilmesi de dahil olmak üzere kullanıcıları e-posta kötü amaçlı yazılımlarından koruyun.|Evet|Evet|[EOP'de kötü amaçlı yazılımdan koruma ilkelerini yapılandırma](../office-365-security/configure-anti-malware-policies.md)|
|İstenmeyen posta önleme ilkeleri|İstenmeyen posta algılanırsa gerçekleştirecek eylemler de dahil olmak üzere kullanıcıları e-posta istenmeyen postalarına karşı koruyun.|Evet|Evet|[Office 365 için Defender'da istenmeyen posta önleme ilkelerini yapılandırma](../office-365-security/configure-your-spam-filter-policies.md)|
|Kimlik sahtekarlığına karşı koruma|Sahte zeka ve sahte zeka içgörüleri kullanarak kullanıcıları kimlik sahtekarlığına karşı koruyun.|Evet|Evet|[Office 365 için Defender'de kimlik sahtekarı zekasını yapılandırma](../office-365-security/learn-about-spoof-intelligence.md) <br><br> [EOP'de kimlik avı önleme ilkelerini yapılandırma](../office-365-security/configure-anti-phishing-policies-eop.md)|
|Kimliğe bürünme koruması|Kullanıcıları kimlik avı saldırılarına karşı koruma ve şüpheli iletilerde güvenlik ipuçlarını yapılandırma|Evet, ancak bazı yapılandırmalar gereklidir.|Evet, ancak bazı yapılandırmalar gereklidir.|[Office 365 için Microsoft Defender kimlik avı önleme ilkelerindeki kimliğe bürünme ayarları](../office-365-security/set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <br><br> [Office 365 için Defender'de kimliğe bürünme içgörüleri](../office-365-security/impersonation-insight.md) <br><br> [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini yapılandırma](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|Güvenli Ekler ilkeleri|Kullanıcıları SharePoint, OneDrive ve Teams'deki e-posta eklerindeki ve dosyalardaki kötü amaçlı içeriklerden koruyun.|Evet|Yerleşik koruma aracılığıyla etkili bir şekilde|[Office 365 için Defender'da Güvenli Ek ilkelerini ayarlama](../office-365-security/set-up-safe-attachments-policies.md)|
|Güvenli Bağlantılar ilkeleri|Kullanıcıları e-posta iletilerinde veya desteklenen Office uygulamalarında kötü amaçlı bağlantıları açma ve paylaşmaya karşı koruyun.|Evet|Yerleşik koruma aracılığıyla etkili bir şekilde|[Office 365 için Defender'da Güvenli Bağlantı ilkelerini ayarlama](../office-365-security/set-up-safe-links-policies.md)|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>3. Adım: Özellikleri deneyin ve simülasyon, izleme ve ölçümler hakkında bilgi edinin

Artık pilotunuz ayarlanıp yapılandırıldığına göre, Microsoft 365 için Microsoft Defender'a özgü raporlama, izleme ve saldırı simülasyonu araçlarını tanımanız yararlı olacaktır.

|Yeteneği|Açıklama|Daha fazla bilgi|
|---|---|---|
|Tehdit Gezgini|Tehdit Gezgini, Güvenlik Operasyonları ekiplerinin tehditleri araştırmasına ve yanıtlamasına yardımcı olan ve e-postada ve Office 365'deki dosyalarda şüpheli kötü amaçlı yazılım ve kimlik avı hakkındaki bilgileri ve kuruluşunuza yönelik diğer güvenlik tehditleri ve risklerini gösteren, neredeyse gerçek zamanlıya yakın güçlü bir araçtır.|[Tehdit Gezgini'nde görünümler ve gerçek zamanlı algılamalar](../office-365-security/threat-explorer-views.md)|
|Saldırı simülasyonu eğitimi|Kuruluşunuzda gerçek bir saldırı ortamınızı etkilemeden önce savunmasız kullanıcıları belirlemenize ve bulmanıza yardımcı olan gerçekçi saldırı senaryoları çalıştırmak için Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi kullanabilirsiniz.|[Saldırı simülasyonu eğitimini kullanmaya başlama](../office-365-security/attack-simulation-training-get-started.md)|
|Raporlar panosu|Sol gezinti menüsünde Raporlar'a tıklayın ve Email & işbirliği başlığını genişletin. Email & işbirliği raporları, güvenlik eğilimlerini belirleme hakkındadır ve bazıları eylem gerçekleştirmenize olanak sağlar ('Gönderimlere git' gibi düğmeler aracılığıyla) ve eğilimleri gösterecek diğerleri. Bu ölçümler otomatik olarak oluşturulur.|[Microsoft 365 Defender portalında e-posta güvenlik raporlarını görüntüleme](../office-365-security/view-email-security-reports.md) <br><br> [Microsoft 365 Defender portalında Office 365 için Defender raporları görüntüleme](../office-365-security/view-reports-for-mdo.md)|

## <a name="next-steps"></a>Sonraki adımlar

[Uç Nokta için Microsoft Defender'ı Değerlendirme](eval-defender-endpoint-overview.md)

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
