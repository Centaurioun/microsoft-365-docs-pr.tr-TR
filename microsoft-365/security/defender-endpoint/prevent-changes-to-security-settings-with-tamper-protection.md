---
title: Değişiklik korumasıyla güvenlik ayarlarını koruyun
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Kötü amaçlı uygulamaların önemli güvenlik ayarlarını değiştirmesini önlemek için kurcalama koruması kullanın.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: dd0512f66adc012c222bded21bad6904bff884dd
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387165"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Değişiklik korumasıyla güvenlik ayarlarını koruyun

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Kurcalama koruması, Windows'un aşağıdaki sürümlerinden birini çalıştıran cihazlar için kullanılabilir:

- Windows 11
- Çoklu oturum Windows 11 Enterprise 
- Windows 10
- Çoklu oturum Windows 10 Enterprise
- Windows Server 2022
- Windows Server 2019
- Windows Server, sürüm 1803 veya üzeri
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> Windows Server 2012 R2'de kurcalama koruması, modern birleşik çözüm paketi kullanılarak eklenen cihazlar için kullanılabilir. Daha fazla bilgi için bkz. [Windows sunucularını Uç Nokta için Microsoft Defender hizmetine ekleme](/microsoft-365/security/defender-endpoint/configure-server-endpoints).

## <a name="overview"></a>Genel bakış

Bazı siber saldırılar sırasında kötü aktörler, makinelerinizde virüsten koruma gibi güvenlik özelliklerini devre dışı bırakmaya çalışır. Kötü aktörler verilerinize daha kolay erişim elde etmek, kötü amaçlı yazılım yüklemek veya verilerinizi, kimliğinizi ve cihazlarınızı başka bir şekilde kullanmak için güvenlik özelliklerinizi devre dışı bırakmak ister. Kurcalama koruması, bu tür şeylerin oluşmasını önlemeye yardımcı olur. Kurcalama koruması ile kötü amaçlı uygulamaların aşağıdaki gibi eylemler gerçekleştirmesi engellenir:

- Virüs ve tehdit korumasını devre dışı bırakma
- Gerçek zamanlı korumayı devre dışı bırakma
- Davranış izlemeyi kapatma
- IOfficeAntivirus (IOAV) gibi virüsten korumayı devre dışı bırakma
- Bulut tabanlı korumayı devre dışı bırakma
- Güvenlik bilgileri güncelleştirmelerini kaldırma
- Algılanan tehditlerde otomatik eylemleri devre dışı bırakma
- Windows Güvenliği uygulamasında bildirimleri gizleme
- Arşivlerin ve ağ dosyalarının taranmalarını devre dışı bırakma

### <a name="how-it-works"></a>Nasıl çalışır?

Kurcalama koruması temelde Microsoft Defender Virüsten Koruma'yı güvenli, varsayılan değerlerine kilitler ve güvenlik ayarlarınızın uygulamalar ve yöntemler aracılığıyla değiştirilmesini önler:

- Windows cihazınızda Kayıt Defteri Düzenleyicisi'nde ayarları yapılandırma
- PowerShell cmdlet'leri aracılığıyla ayarları değiştirme
- grup ilkesi aracılığıyla güvenlik ayarlarını düzenleme veya kaldırma

Kurcalama koruması, güvenlik ayarlarınızı görüntülemenizi engellemez. Ayrıca, kurcalama koruması Microsoft dışı virüsten koruma uygulamalarının Windows Güvenliği uygulamasına nasıl kaydoldığını etkilemez. Kuruluşunuz Windows 10 Enterprise E5 kullanıyorsa, tek tek kullanıcılar kurcalama koruması ayarını değiştiremez; bu gibi durumlarda, kurcalama koruması güvenlik ekibiniz tarafından yönetilir.

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

|Bu görevi gerçekleştirmek için...|Bu bölüme bakın...|
|---|---|
|Kiracınız genelinde kurcalama korumasını yönetme <p> Kurcalama korumasını açmak veya kapatmak için Microsoft 365 Defender portalını kullanma|[Microsoft 365 Defender kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-microsoft-365-defender.md)|
|Kuruluşunuzda kurcalama koruması ayarlarına ince ayar yapma <p> Kurcalama korumasını açmak veya kapatmak için Intune (Microsoft Endpoint Manager) kullanın. Bu yöntemle bazı veya tüm kullanıcılar için kurcalama korumasını yapılandırabilirsiniz.|[Microsoft Endpoint Manager kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-microsoft-endpoint-manager.md)|
|Configuration Manager ile kuruluşunuz için kurcalama korumasını açma (veya kapatma)|[Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-configuration-manager.md)|
|Tek bir cihaz için kurcalama korumasını açma (veya kapatma)|[Tek bir cihazda kurcalama korumasını yönetme](manage-tamper-protection-individual-device.md)|
|Cihazlardaki kurcalama girişimleriyle ilgili ayrıntıları görüntüleme|[Kurcalama girişimleri hakkındaki bilgileri görüntüleme](#view-information-about-tampering-attempts)|
|Güvenlik önerilerinizi gözden geçirin|[Güvenlik önerilerini gözden geçirme](#review-your-security-recommendations)|
|Sık sorulan soruların listesini gözden geçirin (SSS)|[SSS'lere göz atın](faqs-tamper-protection.md)|

## <a name="potential-dependency-on-cloud-protection"></a>Bulut korumasına olası bağımlılık  
  
Kurcalama korumasını etkinleştirmek için kullandığınız yönteme veya yönetim aracına bağlı olarak [, bulut tabanlı koruma](cloud-protection-microsoft-defender-antivirus.md) bağımlılığı olabilir. Bulut tabanlı koruma, bulut koruması veya Microsoft Gelişmiş Koruma Hizmeti (MAPS) olarak da adlandırılır.

Aşağıdaki tabloda yöntemler, araçlar ve bağımlılıklar hakkında ayrıntılar sağlanır.

| Kurcalama koruması nasıl etkinleştirilir? | Bulut korumasına bağımlılık |
|---|---|
|Microsoft Intune|Hayır|
|Kiracı Ekleme ile Microsoft Endpoint Configuration Manager|Hayır|
|Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com))|Evet|

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>Windows Server 2012 R2, 2016 veya Windows sürüm 1709, 1803 veya 1809 mu kullanıyorsunuz?

Windows Server 2012 R2'yi modern birleşik çözüm Windows Server 2016 Windows 10 sürüm 1709, 1803 veya [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) kullanarak kullanıyorsanız, Windows Güvenliği uygulamasında **Kurcalama Koruması'nı** görmezsiniz. Bunun yerine, kurcalama korumasının etkinleştirilip etkinleştirilmediğini belirlemek için PowerShell'i kullanabilirsiniz.

Windows Server 2016'da Ayarlar uygulaması, kurcalama koruması etkinleştirildiğinde gerçek zamanlı korumanın durumunu doğru yansıtmaz.

### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>Kurcalama korumasının ve gerçek zamanlı korumanın açık olup olmadığını belirlemek için PowerShell kullanma

1. Windows PowerShell uygulamasını açın.

2. [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet'ini kullanın.

3. Sonuç listesinde veya `RealTimeProtectionEnabled`öğesini arayın`IsTamperProtected`. ( *True* değeri, kurcalama korumasının etkinleştirildiği anlamına gelir.)

## <a name="view-information-about-tampering-attempts"></a>Kurcalama girişimleri hakkındaki bilgileri görüntüleme

Kurcalama girişimleri genellikle daha büyük siber saldırılara işaret eder. Kötü aktörler, kalıcı hale getirmek ve algılanmamış kalmak için güvenlik ayarlarını değiştirmeye çalışır. Kuruluşunuzun güvenlik ekibinin bir parçasıysanız, bu tür girişimlerle ilgili bilgileri görüntüleyebilir ve ardından tehditleri azaltmak için uygun eylemleri gerçekleştirebilirsiniz.

Kurcalama girişimi algılandığında, [Microsoft 365 Defender portalında](/microsoft-365/security/defender-endpoint/portal-overview) ([https://security.microsoft.com](https://security.microsoft.com)) bir uyarı oluşturulur.

[Uç Nokta için Microsoft Defender'da uç nokta algılama ve yanıt](overview-endpoint-detection-response.md) ile [gelişmiş tehdit avcılığı](advanced-hunting-overview.md) özelliklerini kullanarak güvenlik operasyonları ekibiniz bu tür girişimleri araştırabilir ve ele alabilir.

## <a name="review-your-security-recommendations"></a>Güvenlik önerilerinizi gözden geçirin

Kurcalama koruması[, Microsoft Defender Güvenlik Açığı Yönetimi](next-gen-threat-and-vuln-mgt.md) özellikleriyle tümleştirilir. [Kurcalama](tvm-security-recommendation.md) korumasının açık olduğundan emin olmak güvenlik önerileridir. Örneğin, *kurcalama* sırasında arama yapabilirsiniz. Sonuçlarda, Daha fazla bilgi edinmek ve açmak için **Kurcalama Koruması'nı** aç'ı seçebilirsiniz.

Microsoft Defender Güvenlik Açığı Yönetimi hakkında daha fazla bilgi edinmek için bkz. [Pano içgörüleri - Defender Güvenlik Açığı Yönetimi](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management).


> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Intune için Endpoint Protection ile Windows bilgisayarlarının güvenliğini sağlamaya yardımcı olun](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Uç Nokta için Microsoft Defender genel bakışını edinin](/microsoft-365/security/defender-endpoint)
- [Birlikte daha iyi: Microsoft Defender Virüsten Koruma ve Uç Nokta için Microsoft Defender](why-use-microsoft-defender-antivirus.md)
- [Sorun giderme modunu etkinleştirme](enable-troubleshooting-mode.md)
- [Sorun giderme modu senaryoları](troubleshooting-mode-scenarios.md)
