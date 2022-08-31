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
ms.openlocfilehash: 9202923afc7e86e15a03b03e053e86590f4fae60
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482702"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Pilot Office 365 için Microsoft Defender

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Office 365 için Microsoft Defender için değerlendirme ortamını ayarlama [sürecindeki Adım 3/3'tür](eval-defender-office-365-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-office-365-overview.md) bakın.

Office 365 için Microsoft Defender için pilotu ayarlamak ve yapılandırmak için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Office 365 için Microsoft Defender portalında pilot oluşturma adımları" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [1. Adım: Pilot gruplar oluşturma](#step-1-create-pilot-groups)
- [2. Adım: Korumayı yapılandırma](#step-2-configure-protection)
- [3. Adım: Özellikleri deneyin — Simülasyon, izleme ve ölçümler hakkında bilgi edinin](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Office 365 için Microsoft Defender değerlendirirken, kuruluşunuzun tamamı için ilkeleri etkinleştirmeden ve uygulamadan önce belirli kullanıcılara pilot uygulamayı seçebilirsiniz. Dağıtım grupları oluşturmak, dağıtım işlemlerini yönetmeye yardımcı olabilir. Örneğin, *Office 365 için Defender Kullanıcıları - Standart Koruma*, *Office 365 için Defender Kullanıcılar - Katı Koruma*, *Office 365 için Defender Kullanıcılar - Özel Koruma* gibi gruplar oluşturun veya *Office 365 için Defender Kullanıcıları - Özel Durumlar*.

Bu gruplar için neden "Standart" ve "Katı" terimlerinin kullanıldığı açık olmayabilir, ancak Office 365 için Defender güvenlik ön ayarları hakkında daha fazla bilgi edindiğinizde bu açıkça ortaya çıkacaktır. Grupların "özel" ve "özel durumlar" olarak adlandırılması kendileri için geçerlidir ve kullanıcılarınızın çoğu *standart* ve *katı*, özel ve özel durum grupları risk yönetimiyle ilgili olarak sizin için değerli veriler toplar.

## <a name="step-1-create-pilot-groups"></a>1. Adım: Pilot gruplar oluşturma

Dağıtım grupları doğrudan Exchange Online oluşturulabilir ve tanımlanabilir veya şirket içi Active Directory eşitlenebilir.

1. Alıcı Yöneticisi rolü verilmiş veya grup yönetimi izinleri atanmış bir hesap kullanarak Exchange Yönetici Merkezi'nde (EAC) oturum açın.
2. Gezinti menüsünde *Alıcılar'ı* genişletin ve *Gruplar'ı* seçin.

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" Tıklanacak Gruplar menü öğesi" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. Gruplar panosundan "Grup ekle"yi seçin.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="Tıklanacak grup ekle seçeneği" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. Grup türü için *Dağıtım'ı* seçin ve İleri'ye tıklayın.

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" Grup türü seçin bölümü" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. Gruba bir ad ve açıklama verin ve İleri'ye tıklayın.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="Temel bilgileri ayarlama bölümü" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>2. Adım: Korumayı yapılandırma

Office 365 için Defender'daki bazı özellikler varsayılan olarak yapılandırılır ve açılır, ancak güvenlik işlemleri varsayılan koruma düzeyini yükseltmek isteyebilir.

Bazı özellikler *henüz* yapılandırılmadı. Korumayı yapılandırmak için üç seçeneğiniz vardır:

- **Önceden ayarlanmış güvenlik ilkelerini otomatik olarak atama**— [Önceden ayarlanmış güvenlik ilkeleri](../office-365-security/preset-security-policies.md) , tüm özelliklere hızla tekdüzen bir koruma düzeyi atamak için bir yöntem olarak sağlanır. **_standard_*_ veya _*_strict_** arasından seçim yapabilirsiniz. İyi bir yaklaşım, önceden ayarlanmış güvenlik ilkeleriyle başlamak ve ardından özellikler ve kendi benzersiz tehdit ortamınız hakkında daha fazla bilgi edindikçe ilkelerde ince ayar yapmaktır. Buradaki avantaj, kullanıcı gruplarını daha sonra korumayı ayarlama özelliğiyle mümkün olan en hızlı şekilde korumanızdır. (Bu yöntem önerilir.)
- **Temel korumayı el ile yapılandırma**—Ortamı kendiniz yapılandırmayı tercih ederseniz [Tehditlere karşı koruma](../office-365-security/protect-against-threats.md) yönergelerini izleyerek hızla bir koruma *temeli* elde edebilirsiniz. Bu yaklaşımla yapılandırılabilir ayarlar hakkında daha fazla bilgi edinebilirsiniz. Ayrıca, ilkeleri daha sonra ince ayarlayabilirsiniz.
- ***Özel* koruma ilkelerini yapılandırma**— Ayrıca değerlendirmenizin bir parçası olarak özel koruma ilkeleri oluşturabilir ve atayabilirsiniz. İlkeleri özelleştirmeye başlamadan önce, bu koruma ilkelerinin uygulandığı ve uygulandığı önceliği anlamanız önemlidir. Güvenlik operasyonlarının, güvenli bağlantılar ve güvenli ekler için güvenlik ilkelerini tanımlamak için önceden ayarlanmış olsa bile bazı ilkeler oluşturması gerekir.
> [!IMPORTANT]
> **Özel koruma ilkelerini yapılandırmanız gerekiyorsa**, burada **Standart** ve **Katı** güvenlik tanımlarını oluşturan değerleri incelemeniz gerekir: *[EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](../office-365-security/recommended-settings-for-eop-and-office365.md)*. Herhangi bir yapılandırma gerçekleşmeden önce görüldüğü gibi varsayılan değerler de listelenir. Özel derlemenizin nerede saptığına ait bir elektronik tablo tutun.

### <a name="assign-preset-security-policies"></a>Önceden ayarlanmış güvenlik ilkeleri atama

MDO'yi değerlendirirken *önerilen temel ilkelerle* başlamanız ve ardından değerlendirme döneminiz boyunca gerektiğinde bunları iyileştirmeniz önerilir.

Önerilen EOP ve Office 365 için Defender koruma ilkelerini hızla etkinleştirebilir ve değerlendirmenizin bir parçası olarak bunları belirli pilot kullanıcılara veya tanımlı gruplara atayabilirsiniz. Önceden ayarlanmış ilkeler, bağımsız olarak atanabilen veya birleştirilebilen bir temel **Standart** koruma şablonu veya daha agresif bir **Katı** koruma şablonu sunar.

Aşağıda[, EOP'de önceden ayarlanmış güvenlik ilkeleri ve](../office-365-security/preset-security-policies.md) adımların ana hatlarını içeren Office 365 için Microsoft Defender makale verilmiştir.

1. Microsoft 365 kiracınızda oturum açın. Microsoft 365 Defender portalına erişimi olan, Office 365 Kuruluş Yönetimi rolüne veya Microsoft 365'te Güvenlik Yöneticisi rolüne eklenmiş bir hesap kullanın.
2. Gezinti menüsünden İşbirliği Email & altında *İlkeler & Kuralları'nı* seçin.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" Tıklanacak İlkeler & kuralları menü öğesi" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. İlke & Kuralları panosunda *Tehdit İlkeleri'ne* tıklayın.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" Tıklanacak Tehdit ilkeleri menü öğesi" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. Microsoft 365 Defender portalında gezinti menüsünden Tehdit Yönetimi'ni genişletin ve ardından alt menüden İlke'yi seçin.
5. İlke panosunda *Önceden belirlenmiş güvenlik ilkeleri'ne* tıklayın.

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Tehdit ilkesi türleri" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. Standart ilkeyi ve/veya Katı ilkeyi yapılandırmak ve atamak için *Düzenle'ye* tıklayın.

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Önceden ayarlanmış güvenlik ilkeleri sayfasındaki çeşitli ilkelere uygulanan çeşitli ayarlar" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. Gerektiğinde belirli pilot kullanıcılara veya kullanıcı gruplarına ***EOP** _ korumaları uygulamak için koşullar ekleyin ve devam etmek için _Next* öğesini seçin.

   Örneğin, alıcılar tanımlı Office 365 için Defender *Standart Koruma* grubunun *üyesiyse* ve ardından gruba hesap ekleyerek veya gruptan hesap kaldırarak yönetiliyorsa, pilot değerlendirmeler için Office 365 için Defender bir koşul uygulanabilir.

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="EOP korumaları olarak kabul edilen ilkeler" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. Gerektiğinde belirli pilot kullanıcılara veya kullanıcı gruplarına temel ***MDO** _ korumaları uygulamak için koşullar ekleyin. Devam etmek için _Next* öğesine tıklayın.

   Örneğin, alıcılar tanımlı Office 365 için Defender *Standart Koruma* grubunun *üyesiyse* ve ardından grup aracılığıyla hesap ekleyerek/kaldırarak yönetiliyorsa, pilot değerlendirmeler için Office 365 için Defender bir koşul uygulanabilir.

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Office 365 korumasının savunuldu olduğu ilkeler" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. Önceden ayarlanmış güvenlik ilkeleri atamak için değişikliklerinizi gözden geçirin ve onaylayın.
10. Önceden ayarlanmış koruma ilkeleri, tehdit ilkeleri > > Microsoft 365 Defender portalına > İlkeler & kuralları > ve *Önceden ayarlanmış güvenlik ilkeleri* kutucuğuna tıklanarak yönetilebilir (yeniden yapılandırılabilir, yeniden uygulanabilir, devre dışı bırakılabilir vb.)

### <a name="configure-custom-protection-policies"></a>Özel koruma ilkelerini yapılandırma

Önceden tanımlanmış *Standart* veya *Katı* Office 365 için Defender ilke şablonları, pilot kullanıcılarınıza önerilen temel korumayı verir. Bununla birlikte, değerlendirmenizin bir parçası olarak özel koruma ilkeleri oluşturabilir ve atayabilirsiniz.

Bu koruma ilkelerinin uygulandığında ve uygulandığında uyguladığı önceliklerin farkında olmak *önemlidir*, örneğin [e-posta korumasının sırası ve önceliği - Office 365](../office-365-security/how-policies-and-protections-are-combined.md) açıklanmaktadır.

Aşağıdaki tabloda özel koruma ilkelerini yapılandırmaya ve atamaya yönelik başvurular ve daha fazla rehberlik sağlanır:

<br>

****

|Ilkesi|Açıklama|Başvuru|
|:---:|---|---|
|Bağlantı Filtreleme|İyi veya kötü kaynak e-posta sunucularını IP adreslerine göre tanımlayın.|[EOP'de varsayılan bağlantı filtresi ilkesini yapılandırma](../office-365-security/configure-the-connection-filter-policy.md)|
|Kötü Amaçlı Yazılımdan Koruma|Hangi eylemlerin gerçekleştirilmesi ve kötü amaçlı yazılım algılandığında kime bildirilmesi de dahil olmak üzere kullanıcıları e-posta kötü amaçlı yazılımlarından koruyun.|[EOP'de kötü amaçlı yazılımdan koruma ilkelerini yapılandırma](../office-365-security/configure-anti-malware-policies.md)|
|Kimlik Sahtekarlığına Karşı Koruma|Sahte zeka ve sahte zeka içgörüleri kullanarak kullanıcıları kimlik sahtekarlığına karşı koruyun.|[Office 365 için Defender'de kimlik sahtekarı zekasını yapılandırma](../office-365-security/learn-about-spoof-intelligence.md)|
|Antispam|İstenmeyen posta algılanırsa gerçekleştirecek eylemler de dahil olmak üzere kullanıcıları e-posta istenmeyen postalarına karşı koruyun.|[Office 365 için Defender'da istenmeyen posta önleme ilkelerini yapılandırma](../office-365-security/configure-your-spam-filter-policies.md)|
|Kimlik Avına Karşı Koruma|Kullanıcıları kimlik avı saldırılarına karşı koruma ve şüpheli iletilerde güvenlik ipuçlarını yapılandırma|[Office 365 için Defender'da kimlik avı önleme ilkelerini yapılandırma](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|Güvenli Ekler|Kullanıcıları SharePoint, OneDrive ve Teams'deki e-posta eklerindeki ve dosyalardaki kötü amaçlı içeriklerden koruyun.|[Office 365 için Defender'de güvenli ek ilkelerini ayarlama](../office-365-security/set-up-safe-attachments-policies.md)|
|Güvenli Bağlantılar|Kullanıcıları e-posta iletilerinde veya Office masaüstü uygulamalarında kötü amaçlı bağlantıları açma ve paylaşmaya karşı koruyun.|[Office 365 için Defender'de güvenli bağlantı ilkelerini ayarlama](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>3. Adım: Özellikleri deneyin ve simülasyon, izleme ve ölçümler hakkında bilgi edinin

Artık pilotunuz ayarlanıp yapılandırıldığına göre, Microsoft 365 için Microsoft Defender'a özgü raporlama, izleme ve saldırı simülasyonu araçlarını tanımanız yararlı olacaktır.

<br>

****

|Yeteneği|Açıklama|Daha fazla bilgi|
|---|---|---|
|Tehdit Gezgini|Tehdit Gezgini, Güvenlik Operasyonları ekiplerinin tehditleri araştırmasına ve yanıtlamasına yardımcı olan ve e-postada ve Office 365'deki dosyalarda şüpheli kötü amaçlı yazılım ve kimlik avı hakkındaki bilgileri ve kuruluşunuza yönelik diğer güvenlik tehditleri ve risklerini gösteren, neredeyse gerçek zamanlıya yakın güçlü bir araçtır.|[Tehdit Gezgini'nde görünümler ve gerçek zamanlı algılamalar](../office-365-security/threat-explorer-views.md)|
|Saldırı Simülatörü|Kuruluşunuzda gerçek bir saldırı ortamınızı etkilemeden önce savunmasız kullanıcıları belirlemenize ve bulmanıza yardımcı olan gerçekçi saldırı senaryoları çalıştırmak için Microsoft 365 Defender portalında Saldırı Simülasyonu Eğitimi'ni kullanabilirsiniz.|[Saldırı simülasyonu eğitimini kullanmaya başlama](../office-365-security/attack-simulation-training-get-started.md)|
|Raporlar panosu|Sol gezinti menüsünde Raporlar'a tıklayın ve Email & işbirliği başlığını genişletin. Email & işbirliği raporları, bazıları eyleme geçmenizi sağlayacak güvenlik eğilimlerini belirleme hakkındadır ('Gönderimlere git' gibi düğmeler aracılığıyla) ve Posta akışı durum özeti, En İyi Kötü Amaçlı Yazılım, Kimlik Sahtekarlığı algılamaları, Güvenliği Aşılmış kullanıcılar, Posta gecikme süresi, Güvenli Bağlantılar ve Güvenli ekler raporları gibi eğilimleri gösteren diğer raporlardır. Bu ölçümler otomatik olarak oluşturulur.|[Raporları Görüntüle](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>Sonraki adımlar

[Uç Nokta için Microsoft Defender'ı Değerlendirme](eval-defender-endpoint-overview.md)

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
