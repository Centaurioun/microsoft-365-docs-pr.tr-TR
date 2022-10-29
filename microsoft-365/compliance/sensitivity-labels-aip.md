---
title: Azure Information Protection (AIP) eklentisini Office uygulamaları için yerleşik Microsoft Purview Bilgi Koruması etiketlemeye geçirme
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
search.appverid:
- MOE150
- MET150
description: Office 365 uygulamaları için, hassas verileri korumak için Azure Information Protection (AIP) eklentisinin yerleşik etiketlemeye geçişini anlayın.
ms.openlocfilehash: 0567f90ac308458653ceb1eaec8404a9e8b25a81
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786515"
---
# <a name="migrate-the-azure-information-protection-aip-add-in-to-built-in-labeling-for-office-apps"></a>Azure Information Protection (AIP) eklentisini Office uygulamaları için yerleşik etiketlemeye geçirme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Windows bilgisayarlardaki Microsoft 365 Uygulamaları [duyarlılık etiketlerini](sensitivity-labels.md) kullandığınızda, [Azure Information Protection (AIP) birleşik etiketleme istemcisi](/azure/information-protection/rms-client/aip-clientv2) yüklü olsa bile Office uygulamalarında yerleşik olarak bulunan etiketlemeyi kullanmanızı öneririz. Bundan sonra, Office uygulamalarının en son sürümlerinde AIP eklentisi varsayılan olarak devre dışı bırakılacaktır.

Bu değişikliğe hazırlanmak için, yerleşik etiketleme kullanmanın avantajlarını, hangi ana özelliklerin eşliği olduğunu ve AIP eklentisinden daha yeni etiketleme deneyimine geçişin nasıl denetleneceğini anlamak için bu makaleyi kullanın.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="built-in-labeling-vs-the-aip-client"></a>Yerleşik etiketleme ile AIP istemcisi karşılaştırması

Yerleşik etiketleme[, Microsoft Purview Bilgi Koruması dağıtımının](information-protection-solution.md) temel taşını oluşturur çünkü bu etiketleme teknolojisi platformların (Windows, macOS, iOS, Android ve web) yanı sıra Microsoft uygulamaları ve hizmetleri arasında ve ötesinde genişler. Yerleşik etiketleme ayrıca veri sınıflandırma ve Microsoft Purview Veri Kaybı Önleme (DLP) gibi diğer Microsoft Purview özellikleriyle çalışacak şekilde tasarlanmıştır.

Yerleşik etiketler Office eklentisini kullanmadığından, daha fazla kararlılık ve daha iyi performanstan yararlanırlar. Ayrıca gelişmiş sınıflandırıcılar gibi en son Microsoft Purview özelliklerini de destekler.

Yakın zamana kadar, AIP istemcisi yüklendiğinde Windows için Office uygulamalarında yerleşik etiketleme varsayılan olarak kapatıldı. Bu varsayılan, office'in daha yeni sürümleri için artık geçerli olmayacaktır. [Office uygulamaları için yerleşik etiketlemeyi kullanmak üzere AIP eklentisini devre dışı bırakma](#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps) bölümündeki yönergeleri kullanarak varsayılan davranışı denetleyebilirsiniz. Örneğin, eklentiyi birkaç bilgisayarda ilk test için devre dışı bırakın ve ardından birkaç kullanıcı için bir pilota geçin. Hazır olduğunuzda tüm kullanıcıları daha yeni etiketleme deneyimine geçirin.

AIP istemcisini Office uygulamalarında yüklü ancak devre dışı durumda tuttuğunuzda, AIP istemcisinin diğer özellikleri desteklenmeye devam eder:

- Kullanıcıların tüm dosya türlerine etiket uygulaması için Dosya Gezgini seçeneklerine sağ tıklayın.

- Metin, resim veya PDF belgeleri için şifrelenmiş dosyaları görüntüleyen bir görüntüleyici.

- Şirket içindeki dosyalardaki hassas bilgileri bulmak ve bu dosyalardan etiket ve şifreleme uygulamak veya kaldırmak için bir PowerShell modülü.

- Şirket içi veri depolarında depolanan hassas bilgileri bulmak ve ardından isteğe bağlı olarak bu içeriği etiketlemek için bir tarayıcı.

Etiketlemeyi Office uygulamalarının ötesine genişleten bu özellikler hakkında daha fazla bilgi için AIP belgelerindeki [Azure Information Protection birleşik etiketleme istemci yöneticisi kılavuzuna](/azure/information-protection/rms-client/clientv2-admin-guide) bakın.

Etiketlemeden bağımsız olarak, şifreleme hizmetinin kiracı düzeyinde yönetimi için [AIPService](/powershell/module/aipservice) PowerShell modülünü kullanmaya devam edebilirsiniz. Örneğin, veri kurtarma için şifrelemeyi kaldırmanız gerektiğinde süper kullanıcı erişimini yapılandırın, AIP istemcisi tarafından açılmış belgeleri izleyin ve iptal edin ve çevrimdışı erişim için kullanım lisansı geçerlilik süresini yapılandırın. Daha fazla bilgi için bkz. [PowerShell kullanarak Azure Information Protection korumasını yönetme](/azure/information-protection/administer-powershell).

> [!NOTE]
> Yerleşik etiketler, Office uygulamalarının abonelik sürümünü gerektirir. Office'in bazen "Office Perpetual" olarak da adlandırılan tek başına sürümleriniz varsa, en son etiketleme özelliklerinden yararlanmak için Kurumsal için Microsoft 365 Uygulamaları sürümüne yükseltin.

## <a name="benefits-of-using-built-in-labeling-for-office-apps-vs-the-aip-add-in"></a>Office uygulamaları ve AIP eklentisi için yerleşik etiketleme kullanmanın avantajları

AIP istemcisi [bakım modunda](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-aip-unified-labeling-client-maintenance-mode-and/ba-p/3043613) ve aşağıdaki nedenlerle Office uygulamaları için AIP eklentisini kullanmanızı önermeyiz:

- Yeni etiketleme özellikleri desteklenmeyecektir.
- Eklentiler, Office uygulamalarının kilitlenmesine, kilitlenmesine veya eklentinin otomatik olarak devre dışı bırakılmasına neden olabilecek diğer eklentilerle çakışabileceğinden daha az kararlıdır.
- Eklenti olarak [daha yavaş](/deployoffice/fieldnotes/performance-recommendations#office-add-ins) çalışır ve etiketleme gereksinimlerini atlamak için kullanıcılar tarafından devre dışı bırakılabilir.
- Tüm hata düzeltmeleri için Azure Information Protection istemcisinin yeniden yüklenmesi gerekir.
- Kullanıcılar için etiketleme deneyimi, kullanıcıların diğer cihazlarında (macOS, iOS, Android) ve Web için Office kullandıkları yerleşik etiketlerden biraz farklıdır. Bu fark, eğitim ve destek maliyetlerini artırabilir.
- [Yalnızca yerleşik etiketleme tarafından desteklenen](#features-supported-only-by-built-in-labeling-for-office-apps) yeni Office etiketleme özellikleri kullanıma sunuldu ve liste sürekli büyüyor.

Windows Office uygulamalarınız için AIP eklentisini yalnızca kullanıcılara zaten dağıttıysanız ve bunları yerleşik etiketlemeye geçirmek için zamana ihtiyacınız varsa kullanın. Ya da kullanıcıların ihtiyaç duyduğu önemli bir özellik varsa, henüz Office güncelleştirme kanalında mevcut değildir.

## <a name="features-supported-only-by-built-in-labeling-for-office-apps"></a>Yalnızca Office uygulamaları için yerleşik etiketleme tarafından desteklenen özellikler

> [!NOTE]
> Birçok yeni etiketleme özelliği planlama veya geliştirme aşamasındadır, bu nedenle bu bölümdeki listenin zaman içinde büyümesi beklenir.

Bazı özellikler yalnızca Office uygulamaları için yerleşik etiketleme tarafından desteklenir ve AIP eklentisi tarafından desteklenmez. Şunlar dahildir:

- Otomatik ve önerilen etiketleme için:
    - [Eğitilebilir sınıflandırıcılar](classifier-learn-about.md), [tam veri eşleşmesi (EDM)](sit-learn-about-exact-data-match-based-sits.md) ve [adlandırılmış varlıklar](named-entities-learn.md) içeren akıllı sınıflandırma hizmetlerine erişim
    - Kullanıcılar metni girerken hassas bilgilerin algılanması
    - Word'de, kullanıcılar tanımlanan hassas içeriği gözden geçirebilir ve kaldırabilir
- Mevcut kullanıcı iş akışlarıyla tümleştirilmiş [duyarlılık çubuğu](sensitivity-labels-office-apps.md#sensitivity-bar)
- [PDF desteği](sensitivity-labels-office-apps.md#pdf-support)
- Kullanıcıların izin atamasına izin veren etiketler için kullanıcılara veya gruplara farklı izinler (Okuma veya Değiştirme) verilebilir
- E-postalar için Encrypt-Only
- Hesap değiştirme desteği
- Kullanıcılar etiketlemeyi devre dışı bırakamıyor

Bu özelliklerden bazılarını çalışır durumda görmek için kısa bir tanıtım izleyin:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE58yhH]

Yerleşik etiketleme için yeni etiketleme özellikleri kullanıma sunulduğunda haberdar olmak için bkz. [Microsoft Purview'daki yenilikler](whats-new.md) ve **Duyarlılık etiketleri** bölümleri.

## <a name="how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps"></a>Office uygulamaları için yerleşik etiketlemeyi kullanmak için AIP eklentisini devre dışı bırakma

En son Office uygulamaları için, AIP eklentisi varsayılan olarak devre dışıdır, bu nedenle yapılandırabileceğiniz hiçbir şey yoktur:

- **Derleme 16.0.15716.0+**: Şu anda [Beta Kanalında](https://office.com/insider)
- **Güncel Kanal** ve **Aylık Kurumsal Kanal**: Sürüm 2211+ (henüz yayımlanmadı)
- **Altı Aylık Kanal**: Sürüm 2301+ (henüz yayımlanmadı)

Bu sürümlerden birine sahipseniz ve yerleşik etiketleme yerine AIP eklentisini kullanmanız gerekiyorsa, [varsayılanı geçersiz kılmak için yeni bir ayar yapılandırmanız](#how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in) gerekir.

> [!IMPORTANT]
> Daha önce Office uygulamalarında varsayılan etiketleme istemcisi olarak AIP eklentisini kullandıysanız ve bu bölümde listelenen Office sürümlerini kullandıysanız, AIP eklentisi otomatik olarak devre dışı bırakılır ve yerleşik etiketlemeyle değiştirilir.

Eski sürümlerde AIP eklentisini devre dışı bırakmak için sonraki bölüme bakın.

AIP eklentisi devre dışı bırakıldığında etiketlemeyi Office uygulamalarının ötesine genişletmek için AIP istemcisini kullanmaya devam edebilirsiniz.

### <a name="how-to-configure-older-versions-of-office-to-disable-the-aip-add-in"></a>AIP eklentisini devre dışı bırakmak için Office'in eski sürümlerini yapılandırma

Önceki bölümde listelenen sürümlerden eski Office uygulamaları için, AIP eklentisinin Office uygulamalarında yüklenmesini önlemek için, [Office 2013 ve Office 2016 programlarının grup ilkesi ayarları nedeniyle Yüklü Eklenti Yok](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off) bölümünde belgelendiği gibi yönetilen eklentiler **listesi** grup ilkesi ayarını kullanın.

Yerleşik etiketlemeyi destekleyen Windows Office uygulamalarınız için Microsoft Word 2016, Excel 2016, PowerPoint 2016 ve Outlook 2016 yapılandırmasını kullanın, AIP istemcisi için aşağıdaki programlı tanımlayıcıları (ProgID) belirtin ve seçeneği 0 olarak ayarlayın **: Eklenti her zaman devre dışıdır (engellenir)**

|Uygulama  |Progıd  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 

Grup ilkesi kullanarak veya [Microsoft 365 için Bulut İlkesi hizmetini](/DeployOffice/overview-office-cloud-policy-service) kullanarak bu ayarı dağıtın.

> [!IMPORTANT]
> **Duyarlılık etiketlerini uygulamak ve görüntülemek için Office'te Duyarlılık özelliğini kullan** grup ilkesi ayarını kullanıyorsanız ve bunu **1** olarak ayarlarsanız, AIP eklentisinin Office uygulamalarında hala yüklenebileceği bazı durumlar vardır. Eklentinin her uygulamada yüklenmesini engellemek, bunun olmasını önler.

Alternatif olarak, **Microsoft Azure Information Protection** Office Eklentisini Word, Excel, PowerPoint ve Outlook'tan etkileşimli olarak devre dışı bırakabilir veya kaldırabilirsiniz. Bu yöntem tek bir bilgisayar ve geçici test için uygundur. Yönergeler için bkz. [Office programlarında eklentileri görüntüleme, yönetme ve yükleme](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d).

Hangi yöntemi seçerseniz seçin, Office uygulamaları yeniden başlatıldığında değişiklikler geçerli olur.

Bu değişiklikleri yaptıktan sonra **Duyarlılık** düğmesi Office şeridinde görüntülenmiyorsa, Duyarlılık **etiketlerini uygulamak ve görüntülemek için Office'teki Duyarlılık özelliğini kullan ayarıyla duyarlılık etiketlemesinin** [kapalı](sensitivity-labels-office-apps.md#if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows) olup olmadığını denetleyin. Bu, Office uygulamaları için varsayılan yapılandırma olmasa da, bir yönetici grup ilkesi kullanarak veya doğrudan kayıt defterini düzenleyerek bu yapılandırmayı açıkça ayarlamış olabilir.

### <a name="how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in"></a>AIP eklentisini etkinleştirmek için Office'in daha yeni sürümlerini yapılandırma

> [!CAUTION]
> Daha önce **Duyarlılık etiketlerini uygulamak ve görüntülemek için Office'teki Duyarlılık özelliğini kullan özelliğinin** değerini **0** olarak ayarladıysanız (veya AIP eklentisini kullanmak istediğiniz için yerleşik etiketlemeyi devre dışı bırakmak için **UseOfficeForLabelling'in** eşdeğer kayıt defteri anahtarını kullandıysanız): Bundan sonra, bu bölümde açıklanan yeni ayarı yapılandırmazsanız, duyarlılık etiketlemesini AIP eklentisi veya yerleşik etiketleme ile kullanamazsınız.

[Office'in daha yeni sürümlerinde](#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps), AIP eklentisi varsayılan olarak devre dışıdır. Bunu etkinleştirmek için **Kullanıcı Yapılandırması/Yönetim Şablonları/Microsoft Office 2016/Güvenlik Ayarları** altında yeni bir Office ayarı yapılandırmanız gerekir:

- **Duyarlılık etiketlemesi için Azure Information Protection eklentisini kullanın**. Değeri **1** olarak ayarlayın.

Bu yeni ayar hala kullanıma sunulmaya devam ediyor. Henüz görmüyorsanız birkaç gün daha bekleyin ve yeniden deneyin.

Grup ilkesi kullanarak veya [Microsoft 365 için Bulut İlkesi hizmetini](/DeployOffice/overview-office-cloud-policy-service) kullanarak bu ayarı dağıtın.

Yapılandırmanız gereken ek Office ayarları:

1. **Duyarlılık etiketlerini uygulamak ve görüntülemek için Office'te Duyarlılık özelliğini kullan** güvenlik ayarı **0** olmalıdır veya yapılandırılmamalıdır.

2. Yönetilen eklentiler listesi, önceki bölümde açıklandığı gibi AIP eklentisini engelliyorsa, AIP eklentisi için bu girişleri kaldırmanız veya değerlerini 1 olarak ayarlamanız gerekir **: Eklenti her zaman etkindir.** 

## <a name="feature-parity-for-built-in-labeling-and-the-aip-add-in-for-office-apps"></a>Yerleşik etiketleme için özellik eşliği ve Office uygulamaları için AIP eklentisi

AIP eklentisi tarafından desteklenen etiketleme özelliklerinin çoğu artık yerleşik etiketleme tarafından desteklenmektedir. Kullanılabilir özelliklerin daha ayrıntılı listesi, gerekli olabilecek en düşük sürümler ve yapılandırma bilgileri için bkz. [Office uygulamalarında duyarlılık etiketlerini yönetme](sensitivity-labels-office-apps.md). Belirli bir özelliği desteklemek için [Office güncelleştirme kanalınızı](/deployoffice/overview-update-channels) değiştirmeniz gerekebilir.
 
Daha fazla özellik planlanıyor ve geliştiriliyor. İlgilendiğiniz belirli bir özellik varsa [Microsoft 365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) gözden geçirin ve [Office Özel Önizleme'de Microsoft Bilgi Koruması](https://aka.ms/MIP/PreviewRing) katılmayı düşünün.

AIP eklentisiyle kullandığınız özelliklerin şu anda yerleşik etiketleme ile kullanılabilir olup olmadığını belirlemenize yardımcı olması için aşağıdaki bilgileri kullanın. Henüz kullanıma sunulmamış ancak planlama veya dağıtımda olan özellikler kullanıcılar için son geçişinizi geciktirebilir, ancak daha sonraki bir geçişi hızlandırmak için diğer özellikleri test etmeye başlayabilirsiniz.

|AIP eklentisi özelliği veya özelliği|Yerleşik etiketleme |
|:-------------------------------|:----------------:|
|**Kategori: Genel** ||
|Merkezi raporlama ve denetim|![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels-office-apps.md#auditing-labeling-activities) |
|Kamu Bulutu|![Desteklenir.](../media/yes-icon.png)|
|Yönetici tüm uygulamalar için etiketlemeyi devre dışı bırakabilir|  ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels-office-apps.md#if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows)|
|**Kategori: Kullanıcı Deneyimi** ||
|Şeritteki etiketleme düğmesi|![Desteklenir.](../media/yes-icon.png)|
|Etiket adları ve araç ipuçları için çok dilli destek| ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](create-sensitivity-labels.md#example-configuration-to-configure-a-sensitivity-label-for-different-languages) |
|Araç çubuğunda etiketlerin görünürlüğü| [Önizlemede](sensitivity-labels-office-apps.md#sensitivity-bar) |
|Etiket renkleri| [Önizlemede](sensitivity-labels-office-apps.md#label-colors) |
|**Kategori: Etiketleme eylemleri** ||
|El ile etiketleme |  ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) |
|Zorunlu etiketleme | ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels.md#what-label-policies-can-do)|
|Varsayılan etiketleme <br> - Yeni ve mevcut öğeler <br> - E-posta için ayrı ayarlar|  ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels.md#what-label-policies-can-do) |
|Önerilen veya otomatik |![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) |
|Eski sürüme düşürme gerekçesi |  ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels.md#what-label-policies-can-do)|
| **Kategori: Görsel işaretler** | |
|Üst bilgiler, alt bilgiler, filigran| ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels.md#what-label-policies-can-do)|
|Dinamik işaretler| ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)|
|Uygulama görseli işaretleme başına| ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels-office-apps.md#setting-different-visual-markings-for-word-excel-powerpoint-and-outlook)|
| **Kategori: Şifreleme** | |
|Yönetici tanımlı izinler | ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](encryption-sensitivity-labels.md#assign-permissions-now) |
|Kullanıcı tanımlı izinler <br> - Outlook için İletme <br> - Word, Excel, PowerPoint için kullanıcı ve grup özel izinleri| ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](encryption-sensitivity-labels.md#let-users-assign-permissions)|
|Kullanıcı tanımlı izinler <br> - Word, Excel, PowerPoint için etki alanları belirterek kuruluş genelindeki özel izinler | [Önizlemede](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions) |
|Birlikte yazma ve Otomatik Kaydetme | ![Desteklenen.](../media/yes-icon.png) <br>[Daha fazla bilgi edinin](sensitivity-labels-coauthoring.md) |
| | |

Geliştirmedeki yeni özellikleri belirlemek ve izlemek için [Microsoft 365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) kullanmayı unutmayın.

### <a name="support-for-powershell-advanced-settings"></a>PowerShell gelişmiş ayarları desteği

AIP istemcisi [, PowerShell gelişmiş ayarlarını](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#configuring-advanced-settings-for-the-client-via-powershell) kullanarak birçok özelleştirmeyi destekler. Yerleşik etiketleme tarafından da desteklenen Office uygulamalarına uygulanan gelişmiş ayarlar için [New-Label veya Set-Label](/powershell/module/exchange/new-label) içindeki listeye ve [New-LabelPolicy veya Set-LabelPolicy'deki](/powershell/module/exchange/new-labelpolicy) listeye bakın.[](/powershell/module/exchange/set-labelpolicy)[](/powershell/module/exchange/set-label)

Ancak, Microsoft Purview uyumluluk portalı standart yapılandırmaya dahil olduklarından desteklenen ayarları yapılandırmak için PowerShell kullanmanız gerekmeyebilir. Örneğin, etiket renklerini seçmek ve Outlook için zorunlu etiketlemeyi kapatmak için kullanıcı arabirimi yapılandırması.

AIP eklentisinden henüz yerleşik etiketleme tarafından desteklenmeyen aşağıdaki yapılandırmalar şunlardır:

- [E-posta eklerinden etiket devralma](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#for-email-messages-with-attachments-apply-a-label-that-matches-the-highest-classification-of-those-attachments)
- [Outlook için S/MIME](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#configure-a-label-to-apply-smime-protection-in-outlook)
    - Bu ayar [tüm platformlarda yerleşik etiketleme için önizlemede kullanıma sunulmaya](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) başlanıyor
- [Outlook için açılan iletileri fazla paylaşma](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#implement-pop-up-messages-in-outlook-that-warn-justify-or-block-emails-being-sent)
- [Üst etiket için varsayılan alt etiket](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#specify-a-default-sublabel-for-a-parent-label)
- [Dış içerik işaretlerini kaldırma](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#remove-headers-and-footers-from-other-labeling-solution )

## <a name="features-not-planned-to-be-supported-by-built-in-labeling-for-office-apps"></a>Office uygulamaları için yerleşik etiketleme tarafından desteklenmesi planlanmayacak özellikler

Yerleşik etiketlemeye yönelik yeni özellikler her zaman eklense de, AIP Office eklentisi, yerleşik etiketleme için gelecek sürümlerde kullanıma sunulması planlanmayan aşağıdaki özellikleri destekler:

- Etiketlerin .doc dosyaları gibi Microsoft Office 97-2003 biçimlerine uygulanması
- Windows olay günlüğüne yerel kullanım günlüğü
- Kalıcı olarak bağlantısı kesilmiş bilgisayarlar
- Abonelik tabanlı değil, Office'in tek başına sürümleri ("Office Kalıcı" olarak da adlandırılır)

## <a name="migration-planning-for-the-aip-add-in-for-office-apps"></a>Office uygulamaları için AIP eklentisi için geçiş planlaması

Office uygulamaları için yerleşik etiketlemeyi kullanmaya sorunsuz bir şekilde geçmek için bu sayfadaki bilgileri kullanarak aşağıdaki görevleri içeren bir geçiş planı hazırlayın:

- Şu anda kullandığınız özellikleri belirleyin ve yapılandırmayı ve kullanıcı deneyimini anladığınızdan emin olmak için bunları yerleşik etiketlemeyle test edin.

- Kullanmak istediğiniz yeni özellikleri belirleyin ve bunları geçişe mi yoksa daha sonraki bir aşamada mı dahil etmeye karar verin.

- Kurumsal için Microsoft 365 Uygulamaları gibi tüm bağımlılıkların doğru güncelleştirme kanalıyla dağıtıldığından ve AIP eklentisinin devre dışı [bırakıldığından ve kullanıcılara doğru lisansların atandığından](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-information-protection-sensitivity-labeling) emin olun.

- Tüm iç belgeleri ve eğitimi güncelleştirin ve yardım masanızı ve kullanıcılarınızı değişikliğe hazırlayın.

Geçiş yolculuğunuzda size yardımcı olmak için [Microsoft Purview Müşteri Deneyimi Mühendisliği'nden (CxE) geçiş kılavuzunu ve playbook'unu](https://microsoft.github.io/ComplianceCxE/playbooks/AIP2MIPPlaybook) öneririz.
