---
title: Information Protection için cihaz proxy ve internet bağlantısı ayarlarını yapılandırma
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Information Protection için cihaz proxy ve internet bağlantısı ayarlarını yapılandırma
ms.openlocfilehash: 2d0bc6484636cffb479ccb96b3458fddf0697cd7
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67679855"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-information-protection"></a>Information Protection için cihaz proxy ve internet bağlantısı ayarlarını yapılandırma

Microsoft Endpoint teknolojileri, verileri raporlamak ve Microsoft uç nokta bulut hizmetiyle iletişim kurmak için Microsoft Windows HTTP (WinHTTP) kullanır. Ekli hizmet, LocalSystem hesabını kullanarak sistem bağlamında çalışır.

> [!TIP]
> İleri proxy'leri İnternet'e ağ geçidi olarak kullanan kuruluşlarda, ara sunucu arkasında araştırma yapmak için ağ korumasını kullanabilirsiniz. Daha fazla bilgi için bkz [. İleri ara sunucuların arkasında gerçekleşen bağlantı olaylarını araştırma](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).

WinHTTP yapılandırma ayarı, Windows İnternet (WinINet) İnternet gözatma proxy ayarlarından bağımsızdır ve yalnızca aşağıdaki otomatik bulma yöntemlerini kullanarak bir ara sunucuyu bulabilir:

- Saydam ara sunucu
- Web Proxy Otomatik Bulma Protokolü (WPAD)

> [!NOTE]
> Ağ topolojinizde Saydam proxy veya WPAD kullanıyorsanız özel yapılandırma ayarlarına ihtiyacınız yoktur. Ara sunucudaki Uç Nokta için Defender URL dışlamaları hakkında daha fazla bilgi için bkz. [Ara sunucudaki Uç Nokta DLP bulut hizmeti URL'lerine erişimi etkinleştirme](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).

- El ile statik proxy yapılandırması:
  - Kayıt defteri tabanlı yapılandırma
  - Netsh komutu kullanılarak yapılandırılan WinHTTP – Yalnızca kararlı bir topolojideki masaüstleri için uygundur (örneğin: aynı proxy'nin arkasındaki kurumsal ağdaki bir masaüstü)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Ara sunucuyu kayıt defteri tabanlı statik proxy kullanarak el ile yapılandırma

İnternet'e bağlanmasına izin verilmemiş uç nokta cihazları için kayıt defteri tabanlı statik proxy yapılandırmanız gerekir. Bunu yalnızca Microsoft Endpoint DLP'nin tanılama verilerini raporlamasına ve Microsoft uç nokta bulut hizmetiyle iletişim kurmasına izin verecek şekilde yapılandırmanız gerekir.

Statik proxy, grup ilkesi (GP) aracılığıyla yapılandırılabilir. Grup ilkesi aşağıdakiler altında bulunabilir:

1. **Bağlı Kullanıcı Deneyimi ve Telemetri Hizmeti için Kimliği Doğrulanmış Proxy kullanımını yapılandırmak > Windows Bileşenleri > Veri Toplama ve Önizleme Derlemeleri > Yönetim Şablonları'nı** açın

2. **Etkin** olarak ayarlayın ve **Kimliği Doğrulanmış Proxy kullanımını devre dışı bırak'ı** seçin:

   ![Grup ilkesi ayarlarının resmi 1.](../media/atp-gpo-proxy1.png)

3. **Bağlı kullanıcı deneyimlerini ve telemetrisini yapılandırma > Windows Bileşenleri > Veri Toplama ve Önizleme Derlemeleri > Yönetim Şablonları'nı** açın:

   Ara sunucuyu yapılandırma

   ![Grup ilkesi ayarlarının görüntüsü 2.](../media/atp-gpo-proxy2.png)

   İlke, iki kayıt defteri değerini `TelemetryProxyServer` REG_SZ ve `DisableEnterpriseAuthProxy` kayıt defteri anahtarı `HKLM\Software\Policies\Microsoft\Windows\DataCollection`altında REG_DWORD olarak ayarlar.

   TelemetryProxyServer kayıt defteri değeri şu biçimdedir\<server name or ip\>:\<port\> Örneğin: **10.0.0.6:8080**

   Kayıt defteri değeri `DisableEnterpriseAuthProxy` 1 olarak ayarlanmalıdır.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Ara sunucuyu "netsh" komutunu kullanarak el ile yapılandırma

Sistem genelinde statik ara sunucuyu yapılandırmak için netsh kullanın.

> [!NOTE]
> Bu, varsayılan proxy ile WinHTTP kullanan Windows hizmetleri de dahil olmak üzere tüm uygulamaları etkiler. - Topolojiyi değiştiren dizüstü bilgisayarlar (örneğin: ofisten eve) netsh ile arızalanır. Kayıt defteri tabanlı statik proxy yapılandırmasını kullanın.

1. Yükseltilmiş bir komut satırı açın:
    1. **Başlangıç'a** gidin ve **cmd** yazın
    2. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   `netsh winhttp set proxy <proxy>:<port>`

   Örneğin: **netsh winhttp set proxy 10.0.0.6:8080**

3. Winhttp proxy'yi sıfırlamak için aşağıdaki komutu girin ve **Enter tuşuna** basın:

   `netsh winhttp reset proxy`

Daha fazla bilgi için bkz. [Netsh Komut Söz Dizimi, Bağlamlar ve Biçimlendirme](/windows-server/networking/technologies/netsh/netsh-contexts) .

## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>Ara sunucudaki Uç Nokta DLP bulut hizmeti URL'lerine erişimi etkinleştirme

Ara sunucu veya güvenlik duvarı varsayılan olarak tüm trafiği engelliyorsa ve yalnızca belirli etki alanlarının geçmesine izin veriliyorsa, indirilebilir sayfada listelenen etki alanlarını izin verilen etki alanları listesine ekleyin.

Bu [indirilebilir elektronik tablo](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) , ağınızın bağlanabilmesi gereken hizmetleri ve bunların ilişkili URL'lerini listeler. Bu URL'lere erişimi reddedecek bir güvenlik duvarı veya ağ filtreleme kuralı olmadığından emin olmalısınız veya bunlar için özel olarak bir izin verme kuralı oluşturmanız gerekebilir.

Bir ara sunucuda veya güvenlik duvarında HTTPS taraması (SSL incelemesi) etkinse, yukarıdaki tabloda listelenen etki alanlarını HTTPS taramasının dışında tutun.
Uç Nokta DLP'si sistem bağlamından bağlandığından bir ara sunucu veya güvenlik duvarı anonim trafiği engelliyorsa, önceden listelenen URL'lerde anonim trafiğe izin verildiğinden emin olun.

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>Microsoft bulut hizmeti URL'lerine istemci bağlantısını doğrulama

Proxy yapılandırmasının başarıyla tamamlandığını, WinHTTP'nin ortamınızdaki proxy sunucusunu bulup iletişim kurabildiğini ve ara sunucunun Uç Nokta için Defender hizmet URL'lerine trafiğe izin verdiğinden emin olun.

1. [MDATP İstemci Çözümleyicisi aracını](https://aka.ms/mdatpanalyzer) Endpoint DLP'nin çalıştığı bilgisayara indirin.
2. Cihazdaki MDATPClientAnalyzer.zip içeriğini ayıklayın.
3. Yükseltilmiş bir komut satırı açın:
    1. **Başlangıç'a** gidin ve **cmd** yazın.
    1. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.
4. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   `HardDrivePath\MDATPClientAnalyzer.cmd`

   *HardDrivePath'i* MDATPClientAnalyzer aracının indirildiği yolla değiştirin, örneğin

   **C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**

5. **_HardDrivePath*** içinde kullanılan klasörde araç tarafından oluşturulanMDATPClientAnalyzerResult.zip_ dosyasını ayıklayın.

6. **MDATPClientAnalyzerResult.txt** açın ve sunucu bulmayı ve hizmet URL'lerine erişimi etkinleştirmek için ara sunucu yapılandırma adımlarını gerçekleştirdiğinizden emin olun.  Araç, Uç Nokta için Defender istemcisinin etkileşim kuracak şekilde yapılandırıldığı Uç Nokta için Defender hizmet URL'lerinin bağlantısını denetler. Ardından sonuçları uç nokta için Defender hizmetleriyle iletişim kurmak için kullanılabilecek her URL için **MDATPClientAnalyzerResult.txt** dosyasına yazdırır. Örneğin:

   ```DOS
   Testing URL: https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command-line proxy: Doesn't exist
   ```

Bağlantı seçeneklerinden en az biri (200) durumu döndürürse, Uç Nokta için Defender istemcisi bu bağlantı yöntemini kullanarak test edilen URL ile düzgün bir şekilde iletişim kurabilir.

Ancak, bağlantı denetimi sonuçları bir hata gösteriyorsa, bir HTTP hatası görüntülenir (bkz. HTTP Durum Kodları). Ardından [ara sunucudaki Uç Nokta DLP bulut hizmeti URL'lerine erişimi etkinleştirme bölümünde gösterilen tablodaki URL'leri](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server) kullanabilirsiniz. Kullanacağınız URL'ler, ekleme yordamı sırasında seçilen bölgeye bağlıdır.

> [!NOTE]
>
> Bağlantı Çözümleyicisi aracı, [PSExec ve WMI komutlarından kaynaklanan blok işlemi oluşturma](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-reference#block-process-creations-originating-from-psexec-and-wmi-commands) saldırı yüzeyi azaltma kuralıyla uyumlu değildir. Bağlantı aracını çalıştırmak için bu kuralı geçici olarak devre dışı bırakmanız gerekir.
>
> TelemetryProxyServer ayarlandığında, Kayıt Defteri'nde veya grup ilkesi aracılığıyla, uç nokta için Defender tanımlı ara sunucuya erişemezse doğrudan sunucuya geri döner. İlgili konular:
>
> - Windows 10 cihazları ekleme
> - Microsoft Endpoint DLP ekleme sorunlarını giderme

## <a name="see-also"></a>Ayrıca bkz.

- [Uç nokta veri kaybı önleme hakkında daha fazla bilgi edinme](endpoint-dlp-learn-about.md)
- [Uç noktada veri kaybı önlemeyi kullanma](endpoint-dlp-using.md)
- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md)
- [Bir DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md)
- [Etkinlik gezginini kullanmaya başlama](data-classification-activity-explorer.md)
- [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/)
- [Windows 10 makineleri için ekleme araçları ve yöntemleri](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 aboneliği](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Birleştirilmiş cihazları Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium tabanlı yeni Microsoft Edge'i indirin](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
