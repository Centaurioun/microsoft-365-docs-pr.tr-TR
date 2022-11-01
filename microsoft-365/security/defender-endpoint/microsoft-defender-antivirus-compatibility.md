---
title: Microsoft Defender Virüsten Koruma'nın diğer güvenlik ürünleriyle uyumluluğu
description: Diğer güvenlik ürünleri ve işletim sistemleriyle Microsoft Defender Virüsten Koruma hakkında bilgi edinin.
keywords: windows defender, uç nokta için defender, yeni nesil, virüsten koruma, uyumluluk, pasif mod
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 10/31/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: c935c9e6131f602c582edb5a98787cc8871afbec
ms.sourcegitcommit: 4bae15909267a70c8842bd0cd3dceb8459b4cc29
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68798353"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender Virüsten Koruma'nın diğer güvenlik ürünleriyle uyumluluğu

**Şunlar için geçerlidir:**

- Microsoft Defender Virüsten Koruma
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**Platform**
- Windows

Microsoft Defender Virüsten Koruma, aşağıdaki Windows sürümlerini çalıştıran uç noktalara otomatik olarak yüklenir:

- Windows 10 veya daha yenisi
- Windows Server 2022
- Windows Server 2019
- Windows Server, sürüm 1803 veya üzeri
- Windows Server 2016

Microsoft dışı başka bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü kullanıldığında ne olur? Microsoft Defender Virüsten Koruma'nın yanı sıra başka bir virüsten koruma ürünü çalıştırabilir misiniz? Yanıtlar, işletim sisteminiz ve virüsten korumanızla birlikte [Uç Nokta için Microsoft Defender](microsoft-defender-endpoint.md) kullanıp kullanmadığınız gibi çeşitli faktörlere bağlıdır.

Bu makalede, Uç Nokta için Defender ile ve Uç Nokta için Defender olmadan Microsoft Defender Virüsten Koruma ve Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü ile neler olduğu açıklanmaktadır.

> [!IMPORTANT]
> - Microsoft Defender Virüsten Koruma Windows 10 ve 11, Windows Server 2022, Windows Server 2019, Windows Server, sürüm 1803 veya üzeri ve Windows Server 2016 çalıştıran cihazlarda kullanılabilir. 
> - Microsoft Defender Virüsten Koruma, [modern, birleşik çözüm](/microsoft-365/security/defender-endpoint/configure-server-endpoints) kullanılarak eklendiğinde Windows Server 2012 R2'de de kullanılabilir.
> - Windows 8.1'da, Microsoft Endpoint Configuration Manager aracılığıyla yönetilen [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)) olarak kurumsal düzeyde uç nokta virüsten koruma sunulur.
> - Windows Defender kurumsal düzeyde yönetim sağlamasa da [Windows Defender Windows 8.1 üzerindeki tüketici cihazları](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender) için de sunulur.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Uç Nokta için Defender olmadan virüsten koruma

Bu bölümde, Uç Nokta için Defender'a eklenmemiş uç noktalarda Microsoft dışı virüsten koruma/kötü amaçlı yazılımdan koruma ürünlerinin yanı sıra Microsoft Defender Virüsten Koruma kullandığınızda ne olacağı açıklanmaktadır. 

> [!NOTE]
> Genel olarak Microsoft Defender Virüsten Koruma, Uç Nokta için Defender'a eklenmemiş cihazlarda pasif modda çalışmaz.

Aşağıdaki tabloda neler bekleyebileceğiniz özetlenmiştir:

|Windows sürümü|Birincil virüsten koruma/kötü amaçlı yazılımdan koruma çözümü|virüsten koruma durumunu Microsoft Defender|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Microsoft Defender Virüsten Koruma|Etkin mod|
|Windows 10 <br/> Windows 11|Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü|Devre dışı modu (otomatik olarak gerçekleşir)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server, sürüm 1803 veya üzeri <br/> Windows Server 2016 <br/> Windows Server 2012 R2 |Microsoft Defender Virüsten Koruma|Etkin mod|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server, sürüm 1803 veya üzeri <br/> Windows Server 2016 |Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü|Devre dışı (el ile ayarlama) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) Windows Server'da, Microsoft dışı bir virüsten koruma ürünü çalıştırıyorsanız çakışmayı önlemek için Microsoft Defender Virüsten Koruma'yı kaldırabilirsiniz. Cihaz Uç Nokta için Microsoft Defender ekliyse Microsoft Defender Virüsten Koruma'yı pasif modda kullanabilirsiniz (aşağıya bakın).

> [!TIP]
> Windows Server 2016 Microsoft Defender *Virüsten Koruma* yerine *Windows Defender Virüsten Koruma'yı* görebilirsiniz.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender Virüsten Koruma ve Microsoft dışı virüsten koruma/kötü amaçlı yazılımdan koruma çözümleri

> [!NOTE]
> Genel olarak, Microsoft Defender Virüsten Koruma yalnızca Uç Nokta için Defender'a eklenen uç noktalarda pasif moda ayarlanabilir.

Microsoft Defender Virüsten Koruma'nın etkin modda mı, pasif modda mı yoksa devre dışı mı çalıştırıldığında aşağıdakiler gibi çeşitli faktörlere bağlıdır:

- Bir uç noktaya hangi Windows sürümü yüklü
- Microsoft Defender Virüsten Koruma'nın uç nokta üzerindeki birincil virüsten koruma/kötü amaçlı yazılımdan koruma çözümü olup olmadığı
- Uç noktanın Uç Nokta için Defender'a eklenip eklenmediği

Aşağıdaki tabloda, çeşitli senaryolarda Microsoft Defender Virüsten Koruma'nın durumu özetlemektedir. 

| Windows sürümü   | Virüsten koruma/kötü amaçlı yazılımdan koruma çözümü  | Ekleme tarihi: <br/> Uç Nokta için Defender mı? | virüsten koruma durumunu Microsoft Defender     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Microsoft Defender Virüsten Koruma | Evet  | Etkin mod | 
| Windows 10 <br/> Windows 11 | Microsoft Defender Virüsten Koruma | Hayır   | Etkin mod |
| Windows 10 <br/> Windows 11  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Evet  | Pasif mod (otomatik olarak) |
| Windows 10 <br/> Windows 11  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Hayır   | Devre dışı modu (otomatik olarak)    |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows Server, sürüm 1803 veya üzeri  | Microsoft Defender Virüsten Koruma  | Evet |         Etkin mod  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows Server, sürüm 1803 veya üzeri   | Microsoft Defender Virüsten Koruma | Hayır  | Etkin mod |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, sürüm 1803 veya üzeri  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Evet  | Microsoft Defender Virüsten Koruma pasif moda ayarlanmalıdır (el ile) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server, sürüm 1803 veya üzeri  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Hayır  | Microsoft Defender Virüsten Koruma devre dışı bırakılmalıdır (el ile) <sup>[[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Microsoft Defender Virüsten Koruma | Evet | Etkin mod |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft Defender Virüsten Koruma | Hayır | Etkin mod |
| Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Evet | Microsoft Defender Virüsten Koruma pasif moda ayarlanmalıdır (el ile) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft dışı bir virüsten koruma/kötü amaçlı yazılımdan koruma çözümü | Hayır | Microsoft Defender Virüsten Koruma devre dışı bırakılmalıdır (el ile) <sup>[[3](#fn3)]<sup> |

(<a id="fn2">2</a>) Windows Server 2019, Windows Server, sürüm 1803 veya üzeri, Windows Server 2016 veya Windows Server 2012 R2'de, Microsoft Defender Virüsten Koruma, Microsoft dışı bir virüsten koruma ürünü yüklediğinizde otomatik olarak pasif moda girmez. Bu gibi durumlarda, bir sunucuda birden çok virüsten koruma ürününün yüklü olmasından kaynaklanan sorunları önlemek için virüsten koruma Microsoft Defender pasif moda ayarlayın. Microsoft Defender Virüsten Koruma'yı aşağıdaki gibi bir kayıt defteri anahtarı kullanarak pasif moda ayarlayabilirsiniz:
- Yolu: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Ad: `ForceDefenderPassiveMode`
- Türü: `REG_DWORD`
- Değer: `1`

[Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) komutunu kullanarak PowerShell'de koruma durumunuzu görüntüleyebilirsiniz. değerini `AMRunningMode`denetleyin. Uç noktada virüsten koruma Microsoft Defender etkinse **Normal**, **Pasif** veya **EDR Blok Modu'nu** görmeniz gerekir. 

 > [!NOTE]
 > Pasif modun Windows Server 2016 ve Windows Server 2012 R2 çalıştıran uç noktalarda çalışması için, bu uç noktaların [Windows sunucularını ekleme](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) bölümünde açıklanan modern, birleşik çözümle eklenmesi gerekir. 

(<a id="fn3">3</a>) Windows Server 2016, Windows Server 2012 R2, Windows Server sürüm 1803 veya üzeri, Windows Server 2019 ve Windows Server 2022'de, Uç Nokta için Microsoft Defender *eklenmemiş* bir uç noktada Microsoft dışı bir virüsten koruma ürünü kullanıyorsanız, devre dışı bırakın/ bir sunucuda birden çok virüsten koruma ürününün yüklü olmasından kaynaklanan sorunları önlemek için virüsten koruma Microsoft Defender el ile kaldırın.

> [!TIP]
> Windows Server 2016 Microsoft Defender *Virüsten Koruma* yerine *Windows Defender Virüsten Koruma'yı* görebilirsiniz.

Uç Nokta için Defender, uç noktanıza yüklenen virüsten korumayı daha da genişleten özellikler içerir. Microsoft Defender Virüsten Koruma'nın yanı sıra başka bir virüsten koruma çözümü çalıştırma avantajından yararlanabilirsiniz.

Örneğin, [blok modunda uç nokta algılama ve yanıt (EDR),](edr-in-block-mode.md) Microsoft Defender Virüsten Koruma birincil virüsten koruma ürünü olmasa bile kötü amaçlı yapıtlara karşı ek koruma sağlar. Bu tür özellikler, Microsoft Defender Virüsten Koruma'nın pasif modda veya etkin modda yüklenmesini ve çalıştırılmasını gerektirir.

## <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>Microsoft Defender Virüsten Koruma'nın pasif modda çalışması için gereksinimler

Microsoft Defender Virüsten Koruma'nın pasif modda çalışması için uç noktaların aşağıdaki gereksinimleri karşılaması gerekir:

- İşletim sistemi: Windows 10 veya daha yenisi; Windows Server 2022, Windows Server 2019 veya Windows Server, sürüm 1803 veya üzeri <br/>(Windows Server 2012 R2 ve Windows Server 2016 modern[, birleşik çözüm](/microsoft-365/security/defender-endpoint/configure-server-endpoints) kullanılarak eklenirse). 
- Microsoft Defender Virüsten Koruma yüklenmelidir. 
- Microsoft dışı başka bir virüsten koruma/kötü amaçlı yazılımdan koruma ürünü yüklenmeli ve birincil virüsten koruma çözümü olarak kullanılmalıdır. 
- Uç noktalar, Uç Nokta için Defender'a eklenmelidir. 

> [!IMPORTANT]
> - Microsoft Defender Virüsten Koruma yalnızca Windows 10 ve 11, Windows Server 2022, Windows Server 2016, Windows Server 2019, Windows Server, sürüm 1803 veya daha yeni, Windows Server 2016 ve çalıştıran cihazlarda kullanılabilir R2 Windows Server 2012.
> - Pasif mod yalnızca cihaz [modern, birleşik çözüm](/microsoft-365/security/defender-endpoint/configure-server-endpoints) kullanılarak eklendiğinde Windows Server 2012 R2 & 2016'da desteklenir. 
> - Windows 8.1'da, Microsoft Endpoint Configuration Manager aracılığıyla yönetilen [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)) olarak kurumsal düzeyde uç nokta virüsten koruma sunulmaktadır.
> - Windows Defender kurumsal düzeyde yönetim sağlamasa da [Windows Defender Windows 8.1 üzerindeki tüketici cihazları](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender) için de sunulur.

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender Virüsten Koruma, Uç Nokta için Defender işlevini nasıl etkiler?

Uç Nokta için Defender, Microsoft Defender Virüsten Koruma'nın pasif modda çalışıp çalışmayacağını etkiler. Ayrıca, Microsoft Defender Virüsten Koruma'nın durumu Uç Nokta için Defender'daki belirli özellikleri etkileyebilir. Örneğin, Microsoft Defender Virüsten Koruma etkin veya pasif moddayken gerçek zamanlı koruma çalışır ancak Microsoft Defender Virüsten Koruma devre dışı bırakıldığında veya kaldırıldığında çalışmaz.

> [!IMPORTANT]
> - Bu bölümdeki tabloda, Microsoft Defender Virüsten Koruma'nın etkin modda mı, pasif modda mı yoksa devre dışı mı yoksa kaldırılmış mı olduğuna göre etkin olarak çalışan veya çalışmayan özellikler ve özellikler özetlenmiştir. Bu tablo yalnızca bilgilendirici olacak şekilde tasarlanmıştır.   
> - Pasif modda Microsoft Defender Virüsten Koruma kullanıyorsanız veya blok [modunda EDR](edr-in-block-mode.md) kullanıyorsanız, ihlal sonrası algılanan kötü amaçlı yapıtları algılamak ve düzeltmek için arka planda çalışan gerçek zamanlı koruma, bulut tabanlı koruma veya sınırlı düzenli tarama gibi **özellikleri kapatmayın**.

| Koruma | Microsoft Defender Virüsten Koruma <br/>(*Etkin mod*) | Microsoft Defender Virüsten Koruma <br/>(*Pasif mod*) | Microsoft Defender Virüsten Koruma <br/>(*Devre dışı veya kaldırıldı*) | [Engelleme modunda EDR ](edr-in-block-mode.md) | 
|:---|:---|:---|:---|:---| 
| [Gerçek zamanlı koruma](configure-real-time-protection-microsoft-defender-antivirus.md) | Evet | Bkz. not <sup>[[4](#fn4)]</sup> | Hayır | Hayır | 
| [Bulut tabanlı koruma](enable-cloud-protection-microsoft-defender-antivirus.md) | Evet | Hayır  | Hayır | Hayır | 
| [Ağ koruması](network-protection.md)  | Evet | Hayır | Hayır | Hayır | 
| [Saldırı yüzeyini azaltma kuralları](attack-surface-reduction.md)  | Evet | Hayır | Hayır  | Hayır | 
| [Sınırlı düzenli tarama kullanılabilirliği](limited-periodic-scanning-microsoft-defender-antivirus.md) | Hayır | Evet | Hayır | Hayır | 
| [Dosya tarama ve algılama bilgileri](review-scan-results-microsoft-defender-antivirus.md) | Evet | Evet <sup>[[5](#fn5)]</sup> | Hayır | Evet | 
| [Tehdit düzeltme](configure-remediation-microsoft-defender-antivirus.md) | Evet | Bkz. not <sup>[[6](#fn6)]</sup> | Hayır | Evet | 
| [Güvenlik bilgileri güncelleştirmeleri](manage-updates-baselines-microsoft-defender-antivirus.md) | Evet | Evet <sup>[[7](#fn7)]</sup> | Hayır | Evet <sup>[[7](#fn7)]</sup> | 
| [Veri Kaybı Önleme](../../compliance/endpoint-dlp-learn-about.md) | Evet | Evet | Hayır | Hayır |
| [Denetimli klasör erişimi](controlled-folders.md) | Evet |Hayır | Hayır | Hayır |
| [Web içeriği filtreleme](web-content-filtering.md) | Evet | Bkz. not <sup>[[8](#fn8)]</sup> | Hayır | Hayır |
| [Cihaz denetimi](device-control-report.md) | Evet | Evet | Hayır | Hayır |
| [PUA koruması](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Evet | Hayır | Hayır | Hayır |

(<a id="fn4">4</a>) Genel olarak, Microsoft Defender Virüsten Koruma pasif moddayken, gerçek zamanlı koruma etkin ve pasif modda olsa bile herhangi bir engelleme veya zorlama sağlamaz.

(<a id="fn5">5</a>) Microsoft Defender Virüsten Koruma pasif moddayken taramalar zamanlanır.

(<a id="fn6">6</a>) Microsoft Defender Virüsten Koruma pasif moddayken tehditleri düzeltmez. Ancak tehditler [, blok modunda Uç nokta algılama ve yanıt (EDR)](edr-in-block-mode.md) ile düzeltilebilir. Bu durumda, Microsoft Defender Virüsten Koruma pasif modda olsa bile kaynak olarak Microsoft Defender Virüsten Koruma'yı gösteren uyarılar görebilirsiniz.

(<a id="fn7">7</a>) Güvenlik bilgileri güncelleştirme temposu yalnızca Windows Update ayarları tarafından denetlenilir. Defender'a özgü güncelleştirme zamanlayıcıları (belirli bir zamanda günlük/haftalık, aralık tabanlı) ayarları yalnızca Microsoft Defender Virüsten Koruma etkin moddayken çalışır. Pasif modda yok sayılırlar.

(<a id="fn8">8</a>) Microsoft Defender Virüsten Koruma pasif moddayken, web içeriği filtreleme yalnızca Microsoft Edge tarayıcısıyla çalışır. 

> [!IMPORTANT]
> - Microsoft Defender Virüsten Koruma etkin veya pasif moddayken [uç nokta veri kaybı önleme](/microsoft-365/compliance/endpoint-dlp-learn-about) koruması normal çalışmaya devam eder.
>
> - Microsoft Defender Virüsten Koruma, Uç Nokta için Defender veya Windows Güvenliği uygulaması tarafından kullanılan ilişkili hizmetleri devre dışı bırakma, durdurma veya değiştirme. Bu öneri *wscsvc*, *SecurityHealthService*, *MsSense*, *Sense*, *WinDefend* veya *MsMpEng* hizmet ve işlemlerini içerir. Bu hizmetleri el ile değiştirmek cihazlarınızda ciddi kararsızlıklara neden olabilir ve ağınızı savunmasız hale getirebilir. Bu hizmetlerin devre dışı bırakılması, durdurulması veya değiştirilmesi, Microsoft dışı virüsten koruma çözümleri kullanılırken ve bilgilerinin [Windows Güvenliği uygulamasında](microsoft-defender-security-center-antivirus.md) nasıl görüntülendiği konusunda da sorunlara neden olabilir.
>
> - Birincil virüsten koruma çözümünüz Microsoft Defender Virüsten Koruma olmasa bile Uç Nokta için Defender'da EDR'yi blok modunda açabilirsiniz. Blok modundaki EDR, cihazda bulunan kötü amaçlı öğeleri algılar ve düzelter (ihlal sonrası). Daha fazla bilgi için bkz. [Blok modunda EDR](edr-in-block-mode.md).

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma'nın durumunu onaylama

Microsoft Defender Virüsten Koruma'nın durumunu onaylamak için çeşitli yöntemlerden birini kullanabilirsiniz. Şunları yapabilirsiniz:

- [Virüsten koruma uygulamanızı tanımlamak için Windows Güvenliği uygulamasını kullanın](#use-the-windows-security-app-to-identify-your-antivirus-app).
- [Microsoft Defender Virüsten Koruma'nın çalıştığını onaylamak için Görev Yöneticisi'ni kullanın](#use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running).
- [Microsoft Defender Virüsten Koruma'nın çalıştığını onaylamak için Windows PowerShell kullanın](#use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running).
- [Virüsten korumanın çalıştığını onaylamak için Windows PowerShell kullanın](#use-windows-powershell-to-confirm-that-antivirus-protection-is-running).

> [!IMPORTANT]
> [Platform sürümü 4.18.2208.0 ve sonraki](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions) sürümlerle başlayarak: Bir sunucu Uç Nokta için Microsoft Defender eklendiyse, "Windows Defender kapat" [grup ilkesi](configure-endpoints-gp.md#update-endpoint-protection-configuration) ayarı artık virüsten koruma Windows Defender tamamen devre dışı bırakmaz R2 ve üzerini Windows Server 2012. Bunun yerine pasif moda yerleştirir. Buna ek olarak, [kurcalama koruması](prevent-changes-to-security-settings-with-tamper-protection.md) özelliği etkin moda geçişe izin verir ancak pasif moda geçmez.
> 
> - Uç Nokta için Microsoft Defender'a eklemeden önce "Windows Defender kapat" zaten varsa, değişiklik olmaz ve Defender Virüsten Koruma devre dışı kalır.
> - Defender Virüsten Koruma'yı eklemeden önce devre dışı bırakılmış olsa bile pasif moda geçmek için [ForceDefenderPassiveMode yapılandırmasını](switch-to-mde-phase-2.md#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) değeriyle `1`uygulayabilirsiniz. Etkin moda yerleştirmek için bunun yerine bu değeri olarak `0` değiştirin.
> 
> Kurcalama korumasının etkinleştirildiği zaman için `ForceDefenderPassiveMode` değiştirilen mantığa dikkat edin: Microsoft Defender Virüsten Koruma etkin moda geçirildikten sonra, kurcalama koruması olarak ayarlandığında `1`bile `ForceDefenderPassiveMode` pasif moda geri dönmesini engeller.

### <a name="use-the-windows-security-app-to-identify-your-antivirus-app"></a>Virüsten koruma uygulamanızı tanımlamak için Windows Güvenliği uygulamasını kullanma

1. Windows cihazında Windows Güvenliği uygulamasını açın.

2. **Virüs ve tehdit koruması**’nı seçin.

3. **Beni kim koruyor?** bölümünde **Sağlayıcıları yönet'i** seçin.

4. **Güvenlik sağlayıcıları** sayfasındaki **Virüsten Koruma'nın** altında **Virüsten Koruma'nın açık Microsoft Defender** görmeniz gerekir.

### <a name="use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running"></a>Microsoft Defender Virüsten Koruma'nın çalıştığını onaylamak için Görev Yöneticisi'ni kullanma

1. Windows cihazında Görev Yöneticisi uygulamasını açın.

2. **Ayrıntılar** sekmesini seçin.

3. Listede **MsMpEng.exe** arayın.

### <a name="use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running"></a>Microsoft Defender Virüsten Koruma'nın çalıştığını onaylamak için Windows PowerShell kullanın

> [!NOTE]
> Bu yordamı yalnızca Microsoft Defender Antirivus'un bir uç noktada çalışıp çalışmadığını onaylamak için kullanın.

1. Windows cihazında Windows PowerShell açın. 

2. Aşağıdaki PowerShell cmdlet'ini çalıştırın: `Get-Process`.

3. Sonuçları gözden geçirin. **virüsten koruma Microsoft Defender** etkinseMsMpEng.exegörmeniz gerekir.

### <a name="use-windows-powershell-to-confirm-that-antivirus-protection-is-running"></a>Virüsten korumanın çalıştığını onaylamak için Windows PowerShell kullanın

> [!NOTE]
> Bu yordamı yalnızca bir uç noktada virüsten korumanın etkinleştirilip etkinleştirilmediğini onaylamak için kullanın.

1. Windows cihazında Windows PowerShell açın.

2. Aşağıdaki PowerShell cmdlet'ini çalıştırın: `Get-MpComputerStatus | select AMRunningMode`.

3. Sonuçları gözden geçirin. Uç noktada virüsten koruma etkinse **Normal**, **Pasif** veya **EDR Blok Modu'nu** görmeniz gerekir. 

> [!NOTE]
> Bu yordamın yalnızca bir uç noktada virüsten korumanın etkinleştirilip etkinleştirilmediğini onaylamak için olduğunu unutmayın.

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Microsoft Defender Virüsten Koruma durumları hakkında daha fazla ayrıntı

Aşağıdaki bölümlerde virüsten koruma Microsoft Defender ne bekleyebileceğiniz açıklanmaktadır:

- [Etkin modda](#active-mode)
- [Pasif modda veya blok modunda EDR açık olduğunda](#passive-mode-or-edr-block-mode)
- [Devre dışı bırakılmış veya kaldırılmış](#disabled-or-uninstalled)

### <a name="active-mode"></a>Etkin mod

Etkin modda Microsoft Defender Virüsten Koruma, makinede virüsten koruma uygulaması olarak kullanılır. Configuration Manager, grup ilkesi, Microsoft Intune veya diğer yönetim ürünleri kullanılarak yapılandırılan ayarlar uygulanır. Dosyalar taranır, tehditler düzeltilir ve algılama bilgileri yapılandırma aracınızda (örneğin, Microsoft Endpoint Manager yönetim merkezinde veya uç noktadaki Microsoft Defender Virüsten Koruma uygulamasında) bildirilir.  

### <a name="passive-mode-or-edr-block-mode"></a>Pasif mod veya EDR Blok modu

Pasif modda virüsten koruma uygulaması olarak Microsoft Defender Virüsten Koruma kullanılmaz ve tehditler Microsoft Defender Virüsten Koruma tarafından *düzeltılmaz*. Ancak tehditler [, blok modunda Uç nokta algılama ve yanıt (EDR)](edr-in-block-mode.md) ile düzeltilebilir. Dosyalar EDR tarafından taranır ve uç nokta için Defender hizmetiyle paylaşılan tehdit algılamaları için raporlar sağlanır. Microsoft Defender Virüsten Koruma pasif modda olsa bile kaynak olarak Microsoft Defender Virüsten Koruma'yı gösteren uyarılar görebilirsiniz. 

Microsoft Defender Virüsten Koruma pasif moddayken [Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetmeye](manage-updates-baselines-microsoft-defender-antivirus.md) devam edebilirsiniz; ancak cihazlarınızda kötü amaçlı yazılımlardan gerçek zamanlı koruma sağlayan Microsoft dışı bir virüsten koruma ürünü varsa Virüsten Koruma'yı etkin moda Microsoft Defender taşıyamazsınız.

**Microsoft Defender Virüsten Koruma pasif modda çalışıyor olsa bile virüsten koruma ve kötü amaçlı yazılımdan koruma güncelleştirmelerinizi aldığınızdan emin olun**. Bkz[. Microsoft Defender Virüsten Koruma güncelleştirmelerini yönetme ve temelleri uygulama](manage-updates-baselines-microsoft-defender-antivirus.md).<br/><br/>Pasif modun yalnızca makine [modern, birleşik çözüm](/microsoft-365/security/defender-endpoint/configure-server-endpoints) kullanılarak eklendiğinde Windows Server 2012 R2 & 2016'da desteklendiğini unutmayın. 

### <a name="disabled-or-uninstalled"></a>Devre dışı bırakılmış veya kaldırılmış

Devre dışı bırakıldığında veya kaldırıldığında virüsten koruma uygulaması olarak Microsoft Defender Virüsten Koruma kullanılmaz. Dosyalar taranmıyor ve tehditler düzeltilmemiş. Microsoft Defender Virüsten Koruma'nın devre dışı bırakılması veya kaldırılması genel olarak önerilmez; mümkünse, Microsoft dışı kötü amaçlı yazılımdan koruma/virüsten koruma çözümü kullanıyorsanız Virüsten Koruma'yı pasif modda Microsoft Defender tutun.

Microsoft Defender Virüsten Koruma'nın otomatik olarak devre dışı bırakıldığı durumlarda, Microsoft dışı virüsten koruma/kötü amaçlı yazılımdan koruma ürününün süresi dolarsa, kaldırılırsa veya virüslere, kötü amaçlı yazılımlara veya diğer tehditlere karşı gerçek zamanlı koruma sağlamayı durdurursa otomatik olarak yeniden etkinleştirilebilir. Microsoft Defender Virüsten Koruma'nın otomatik olarak yeniden etkinleştirilmesi, uç noktalarınızda virüsten korumanın korunmasına yardımcı olur.

Microsoft dışı bir virüsten koruma uygulaması kullanıyorsanız tehditleri düzenli aralıklarla denetlemek için Microsoft Defender Virüsten Koruma altyapısıyla birlikte çalışan [sınırlı düzenli tarama](limited-periodic-scanning-microsoft-defender-antivirus.md) da kullanabilirsiniz.  | 

## <a name="what-about-non-windows-devices"></a>Windows olmayan cihazlar ne olacak?

 Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:

- [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
- [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
- [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
- [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
- [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Windows istemcilerinde virüsten koruma Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
- [Engelleme modunda EDR ](edr-in-block-mode.md)
- [Uç nokta veri kaybı önleme hakkında daha fazla bilgi edinme](/microsoft-365/compliance/endpoint-dlp-learn-about)
