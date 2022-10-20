---
title: Blok modunda uç nokta algılama ve yanıt
description: Blok modunda uç nokta algılama ve yanıt hakkında bilgi edinin
keywords: Uç Nokta için Microsoft Defender, mde, blok modunda EDR, pasif mod engelleme
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.date: 08/19/2022
ms.collection:
- m365-security
- tier2
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 6f9c88b4edde50f4a23d20784d8dbd64a52f15b9
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643085"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Blok modunda uç nokta algılama ve yanıt (EDR)

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender Virüsten Koruma

**Platform**

- Windows

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Blok modunda EDR nedir?

Blok modunda [uç nokta algılama ve yanıt](overview-endpoint-detection-response.md) (EDR), Microsoft Defender Virüsten Koruma (MDAV) birincil virüsten koruma ürünü olmadığında ve pasif modda çalıştığında kötü amaçlı yapıtlara karşı ek koruma sağlar. Blok modundaki EDR, EDR özellikleri tarafından algılanan kötü amaçlı yapıtları düzeltmek için arka planda çalışır. Bu tür yapıtlar birincil, Microsoft dışı virüsten koruma ürünü tarafından kaçırılmış olabilir. Blok modunda EDR, Microsoft Defender Virüsten Koruma'nın ihlal sonrası, davranışsal EDR algılamaları üzerinde eylemler gerçekleştirmesine olanak tanır. **Sık sorulan sorular** bölümündeki [Virüsten Koruma Microsoft Defender EDR'yi blok modunda açmam gerekiyor mu?](#do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices) bölümüne bakın.

> [!IMPORTANT]
> Blok modundaki EDR, Microsoft Defender Virüsten Koruma gerçek zamanlı koruması etkinleştirildiğinde kullanılabilen tüm korumayı sağlamaz. Microsoft Defender Virüsten Koruma'nın etkin virüsten koruma çözümü olması gereken bazı özellikler çalışmaz, örneğin aşağıdaki örnekler:
>
> - Microsoft Defender Virüsten Koruma pasif moddayken, erişim içi tarama da dahil olmak üzere gerçek zamanlı koruma kullanılamaz. Gerçek zamanlı koruma ilkesi ayarları hakkında daha fazla bilgi edinmek için bkz. **[Microsoft Defender Virüsten Koruma'yı her zaman açık korumayı etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md)**.
> - **[Ağ koruması](network-protection.md)** ve **[saldırı yüzeyi azaltma kuralları](attack-surface-reduction.md)** gibi özellikler yalnızca Microsoft Defender Virüsten Koruma etkin modda çalışırken kullanılabilir.
>
> Microsoft dışı virüsten koruma çözümünüzün bu özellikleri içermesi beklenir.

Blok modundaki EDR, [tehdit & güvenlik açığı yönetimi](next-gen-threat-and-vuln-mgt.md) özellikleriyle tümleşiktir. Kuruluşunuzun güvenlik ekibi, henüz etkinleştirilmemişse EDR'yi blok modunda açmak için bir [güvenlik önerisi](tvm-security-recommendation.md) alır. Bu öneri öncelikli olarak etkin bir Microsoft dışı virüsten koruma çözümü kullanan cihazlara yöneliktir (pasif modda Microsoft Defender Virüsten Koruma ile). Microsoft Defender Virüsten Koruma, cihazlarda birincil virüsten koruma çözümü olduğunda blok modunda EDR'yi etkinleştirmenin çok az avantajı vardır.

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="Blok modunda EDR'yi açma önerisi" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> En iyi korumayı elde etmek için **[Uç Nokta için Microsoft Defender taban çizgilerini dağıttığınıza](configure-machines-security-baseline.md)** emin olun.

Blok modunda uç nokta algılama ve yanıtının (EDR) neden ve nasıl açacağınızı, davranış engellemeyi etkinleştireceğinizi ve ihlal öncesi aşamadan ihlal sonrası aşamalara kadar her aşamada kapsamanın neden ve nasıl açacağınızı öğrenmek için bu videoyu izleyin.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HjW2]

## <a name="what-happens-when-something-is-detected"></a>Bir şey algılandığında ne olur?

Blok modunda EDR açık olduğunda ve kötü amaçlı bir yapıt algılandığında Uç Nokta için Defender bu yapıtı düzelter. Güvenlik operasyonları ekibiniz algılama durumunu [İşlem merkezinde](respond-machine-alerts.md#check-activity-details-in-action-center) **Engellendi** veya **Engellendi** olarak görür ve tamamlanmış eylemler olarak listelenir. Aşağıdaki görüntüde, blok modunda EDR aracılığıyla algılanan ve düzeltilen istenmeyen yazılımların bir örneği gösterilmektedir:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="Blok modunda EDR tarafından algılama" lightbox="images/edr-in-block-mode-detection.png":::

## <a name="enable-edr-in-block-mode"></a>Blok modunda EDR'yi etkinleştirme

> [!IMPORTANT]
> Platform sürümü 4.18.2202.X'den başlayarak, artık EDR'yi blok modunda Intune CSP'leri kullanarak belirli cihaz gruplarını hedefleyecek şekilde ayarlayabilirsiniz. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> EDR'yi blok modu kiracı genelinde ayarlamaya devam edebilirsiniz. Blok modunda EDR öncelikli olarak pasif modda Microsoft Defender Virüsten Koruma çalıştıran cihazlar için önerilir (cihazda Microsoft dışı bir virüsten koruma çözümü yüklü ve etkindir).

> [!TIP]
> Blok modunda EDR'yi açmadan önce [gereksinimlerin](#requirements-for-edr-in-block-mode) karşılandığından emin olun.

> [!NOTE]
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

### <a name="security-portal"></a>Güvenlik Portalı

1. Microsoft 365 Defender portalına ([https://security.microsoft.com/](https://security.microsoft.com/)) gidin ve oturum açın.
1. **Ayarlar** \> **Uç Noktaları** \> **Genel** \> **Gelişmiş özellikler'i** seçin.
1. Ekranı aşağı kaydırın ve ardından **Blok modunda EDR'yi etkinleştir'i** açın.

### <a name="intune"></a>Intune

Intune'da özel ilke oluşturmak için bkz. [Intune aracılığıyla csp'yi hedeflemek için OMA-URIs dağıtma ve şirket içiyle karşılaştırma](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune).

Blok modunda EDR için kullanılan Defender CSP hakkında daha fazla bilgi için [Defender CSP'nin](/windows/client-management/mdm/defender-csp) altındaki "Configuration/PassiveRemediation" bölümüne bakın.

## <a name="requirements-for-edr-in-block-mode"></a>Blok modunda EDR gereksinimleri

Aşağıdaki tabloda blok modunda EDR gereksinimleri listelenmiştir:

|Gereksinim|Ayrıntılar|
|---|---|
|İzinler|[Azure Active Directory'de](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Genel Yönetici veya Güvenlik Yöneticisi rolü atanmış olmalıdır. Daha fazla bilgi için bkz. [Temel izinler](basic-permissions.md).|
|İşletim sistemi|Cihazların Windows'un aşağıdaki sürümlerinden birini çalıştırıyor olması gerekir: <ul><li>Windows 11</li><li>Windows 10 (tüm sürümler)</li><li>Windows Server 2019 veya üzeri</li><li>Windows Server, sürüm 1803 veya üzeri</li><li>[Yeni birleşik istemci çözümüyle](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) R2'yi \(Windows Server 2016 ve Windows Server 2012\)</li></ul>|
|Uç Nokta için Microsoft Defender|Cihazların Uç Nokta için Defender'a eklenmelidir. Aşağıdaki makalelere bakın: <br/>- [Uç Nokta için Microsoft Defender için en düşük gereksinimler](minimum-requirements.md)<br/>- [Cihazları ekleme ve Uç Nokta için Microsoft Defender özelliklerini yapılandırma](onboard-configure.md)<br/>- [Windows sunucularını Uç Nokta için Defender hizmetine ekleme](configure-server-endpoints.md)<br/>- [Modern birleşik çözümde yeni Windows Server 2012 R2 ve 2016 işlevselliği (Önizleme)](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) |
|Microsoft Defender Virüsten Koruma|Cihazlarda Microsoft Defender Virüsten Koruma'nın yüklü olması ve etkin modda veya pasif modda çalıştırılması gerekir. [Microsoft Defender Virüsten Koruma'nın etkin veya pasif modda olduğunu onaylayın](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode).|
|Bulut tabanlı koruma|Microsoft Defender Virüsten Koruma[, bulut tabanlı koruma etkinleştirilecek](enable-cloud-protection-microsoft-defender-antivirus.md) şekilde yapılandırılmalıdır.|
|Microsoft Defender Virüsten Koruma platformu|Cihazların güncel olması gerekir. Onaylamak için PowerShell kullanarak [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet'ini yönetici olarak çalıştırın. **AMProductVersion** satırında **4.18.2001.10** veya üzerini görmeniz gerekir. <p> Daha fazla bilgi için [Microsoft Defender Virüsten Koruma güncelleştirmelerine bakın ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).|
|Microsoft Defender Virüsten Koruma altyapısı|Cihazların güncel olması gerekir. Onaylamak için PowerShell kullanarak [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet'ini yönetici olarak çalıştırın. **AMEngineVersion** satırında **1.1.16700.2** veya üzerini görmeniz gerekir. <p> Daha fazla bilgi için [Microsoft Defender Virüsten Koruma güncelleştirmelerine bakın ve temelleri uygulayın](manage-updates-baselines-microsoft-defender-antivirus.md).|

(<a id="fn1">1</a>) Bkz. [EDR Windows Server 2016 ve Windows Server 2012 R2'de blok modunda destekleniyor mu?](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)

> [!IMPORTANT]
> En iyi koruma değerini elde etmek için virüsten koruma çözümünüzün düzenli güncelleştirmeleri ve temel özellikleri alacak şekilde yapılandırıldığından ve [dışlamalarınızın yapılandırıldığından](configure-exclusions-microsoft-defender-antivirus.md) emin olun. Blok modunda EDR, Microsoft Defender Virüsten Koruma için tanımlanan dışlamaları dikkate alır, ancak Uç Nokta için Microsoft Defender için tanımlanan [göstergelere](manage-indicators.md) dikkat etmemektedir.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>Blok modunda EDR için dışlamalar belirtebilir miyim?

Hatalı pozitif sonuç aldığınızda, dosyayı [Microsoft Güvenlik Zekası gönderim sitesinde](https://www.microsoft.com/en-us/wdsi/filesubmission) analiz için gönderebilirsiniz.

Microsoft Defender Virüsten Koruma için bir dışlama da tanımlayabilirsiniz. Bkz[. Microsoft Defender Virüsten Koruma taramaları için dışlamaları yapılandırma ve doğrulama](configure-exclusions-microsoft-defender-antivirus.md).

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>Cihazlarda çalışan Microsoft Defender Virüsten Koruma özelliğine sahipsem EDR'yi blok modunda açmam gerekiyor mu?

Blok modunda EDR'nin birincil amacı, Microsoft dışı bir virüsten koruma ürünü tarafından kaçırılan ihlal sonrası algılamaları düzeltmektir. Microsoft Defender Virüsten Koruma etkin moddayken blok modunda EDR'yi etkinleştirmenin en düşük avantajı vardır çünkü gerçek zamanlı korumanın önce algılamaları yakalaması ve düzeltmesi beklenir. Virüsten Koruma için Microsoft Defender pasif modda çalıştığı uç noktalarda EDR'yi blok modunda etkinleştirmenizi öneririz. EDR algılamaları [PUA koruması](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) veya blok modunda [otomatik araştırma & düzeltme özellikleriyle](automated-investigations.md) otomatik olarak düzeltilebilir.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>Blok modundaki EDR, kullanıcının virüsten korumasını etkiler mi?

Blok modundaki EDR, kullanıcıların cihazlarında çalışan üçüncü taraf virüsten korumasını etkilemez. Blok modunda EDR, birincil virüsten koruma çözümü bir şeyi kaçırırsa veya ihlal sonrası algılama varsa çalışır. Blok modundaki EDR, pasif modda Microsoft Defender Virüsten Koruma gibi çalışır; blok modundaki EDR'nin algılanan kötü amaçlı yapıtları veya davranışları da engellemesi ve düzeltmesi dışında.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Virüsten Koruma'Microsoft Defender neden güncel tutmam gerekiyor?

Microsoft Defender Virüsten Koruma kötü amaçlı öğeleri algılayıp düzeltdiğinden, bu öğeleri güncel tutmak önemlidir. Blok modundaki EDR'nin etkili olması için en son cihaz öğrenmesi modellerini, davranış algılamalarını ve buluşsal yöntemleri kullanır. [Uç Nokta için Defender](microsoft-defender-endpoint.md) özellik yığını tümleşik bir şekilde çalışır. En iyi koruma değerini elde etmek için virüsten koruma Microsoft Defender güncel tutmalısınız. Bkz[. Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="why-do-we-need-cloud-protection-maps-on"></a>Neden bulut korumasına (MAPS) ihtiyacımız var?

Cihazdaki özelliği açmak için bulut koruması gerekir. Bulut koruması [, Uç Nokta için Defender'ın](microsoft-defender-endpoint.md) davranış ve cihaz öğrenmesi modellerinin yanı sıra güvenlik zekasının genişliğine ve derinliğine göre en son ve en büyük korumayı sunmasını sağlar.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>Etkin ve pasif mod arasındaki fark nedir?

Microsoft Defender Virüsten Koruma etkin moddayken Windows 10, Windows 11, Windows Server, sürüm 1803 veya üzeri, Windows Server 2019 veya Windows Server 2022 çalıştıran uç noktalar için cihazda birincil virüsten koruma olarak kullanılır. Pasif modda çalışırken, Microsoft Defender Virüsten Koruma birincil virüsten koruma ürünü değildir. Bu durumda tehditler Microsoft Defender Virüsten Koruma tarafından gerçek zamanlı olarak düzeltilmemiştir.

> [!NOTE]
> Microsoft Defender Virüsten Koruma yalnızca cihaz Uç Nokta için Microsoft Defender eklendiğinde pasif modda çalıştırılabilir.

Daha fazla bilgi için bkz[. virüsten koruma uyumluluğu Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Virüsten Koruma'nın etkin veya pasif modda Microsoft Defender onaylıyor Nasıl yaparım??

Microsoft Defender Virüsten Koruma'nın etkin veya pasif modda çalışıp çalışmadığını onaylamak için, Windows çalıştıran bir cihazda Komut İstemi veya PowerShell kullanabilirsiniz.

|Yöntem|Yordam|
|---|---|
|PowerShell|1. Başlat menüsünü seçin, yazmaya `PowerShell`başlayın ve sonuçlarda Windows PowerShell açın.<br/><br/>2. yazın `Get-MpComputerStatus`.<br/><br/>3. Sonuç listesinde, **AMRunningMode** satırında aşağıdaki değerlerden birini arayın:<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>Daha fazla bilgi için bkz [. Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).|
|Komut|<ol><li>Başlat menüsünü seçin, yazmaya `Command Prompt`başlayın ve sonuçlarda Windows Komut İstemi'ni açın.</li><li>`sc query windefend` yazın.</li><li>Sonuç listesinde, **STATE** satırında hizmetin çalıştığını onaylayın.</li></ol>|

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Nasıl yaparım? pasif modda Microsoft Defender Virüsten Koruma ile blok modunda EDR'nin açık olduğunu onaylıyor musunuz?

PowerShell'i kullanarak pasif modda çalışan Microsoft Defender Virüsten Koruma ile blok modunda EDR'nin açık olduğunu onaylayabilirsiniz.

1. Başlat menüsünü seçin, yazmaya `PowerShell`başlayın ve sonuçlarda Windows PowerShell açın.

2. `Get-MPComputerStatus|select AMRunningMode` yazın.

3. sonucunun `EDR Block Mode`görüntülendiğini onaylayın.

   > [!TIP]
   > Microsoft Defender Virüsten Koruma etkin moddaysa yerine öğesini görürsünüz `Normal` `EDR Block Mode`. Daha fazla bilgi için bkz [. Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>EDR Windows Server 2016 ve Windows Server 2012 R2'de blok modunda destekleniyor mu?

Microsoft Defender Virüsten Koruma etkin modda veya pasif modda çalışıyorsa, blok modunda EDR aşağıdaki Windows sürümlerinde desteklenir:

- Windows 11
- Windows 10 (tüm sürümler)
- Windows Server, sürüm 1803 veya üzeri
- Windows Server 2022
- Windows Server 2019
- Windows Server 2016 ve Windows Server 2012 R2 ([yeni birleşik istemci çözümüyle](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution))

Windows Server 2016 ve Windows Server 2012 R2 için [yeni birleşik istemci çözümüyle](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution), EDR'yi pasif modda veya etkin modda blok modunda çalıştırabilirsiniz.

> [!NOTE]
> Windows Server 2016 ve Windows Server 2012 R2, bu özelliğin çalışması için [Windows sunucularını ekleme](configure-server-endpoints.md) yönergeleri kullanılarak eklenmelidir.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Blok modunda EDR'nin devre dışı bırakılması ne kadar sürer?

Blok modunda EDR'yi devre dışı bırakmayı seçerseniz, sistemin bu özelliği devre dışı bırakması 30 dakika kadar sürebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Teknoloji Topluluğu blogu: Blok modunda EDR tanıtımı: İzlerinde saldırıları durdurma](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [Davranışsal engelleme ve kapsama](behavioral-blocking-containment.md)
