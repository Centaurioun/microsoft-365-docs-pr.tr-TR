---
title: Uç Nokta için Microsoft Defender dağıtımı ayarlama
description: Uç Nokta için Microsoft Defender için dağıtımı ayarlamayı öğrenin
keywords: dağıtma, kurulum, lisans doğrulama, kiracı yapılandırması, ağ yapılandırması
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
- highpri
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 42d369e1f1dc399600c76e4361147687f4365d89
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694027"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Uç Nokta için Microsoft Defender dağıtımı ayarlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Defender'ın dağıtılması üç aşamalı bir işlemdir:

|[![dağıtım aşaması - hazırlama.](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[Aşama 1: Hazırlık](prepare-deployment.md) | ![dağıtım aşaması - kurulum](images/phase-diagrams/setup.png#lightbox)<br>Aşama 2: Kurulum | [![dağıtım aşaması - ekleme](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[Aşama 3: Katılım](onboarding.md)|
|---|---|---|
||*Buradasınız!*||

Şu anda kurulum aşamasındasınız.

Bu dağıtım senaryosunda aşağıdaki adımlarda size yol gösterilir:

- Lisans doğrulama
- Kiracı yapılandırması
- Ağ yapılandırması

> [!NOTE]
> Tipik bir dağıtımda size yol göstermek amacıyla, bu senaryo yalnızca Microsoft Endpoint Configuration Manager kullanımını kapsar. Uç Nokta için Defender diğer ekleme araçlarının kullanımını destekler ancak dağıtım kılavuzunda bu senaryoları kapsamaz. Daha fazla bilgi için bkz[. Cihazları Uç Nokta için Microsoft Defender ekleme](onboard-configure.md).

## <a name="check-license-state"></a>Lisans durumunu denetleme

Lisans durumunu ve doğru şekilde sağlanıp sağlanmadığını denetleme işlemi yönetim merkezi veya **Microsoft Azure portal** aracılığıyla yapılabilir.

1. Lisanslarınızı görüntülemek için **Microsoft Azure portal** ve [Microsoft Azure portal lisansı bölümüne](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products) gidin.

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="Azure Lisanslama sayfası" lightbox="images/atp-licensing-azure-portal.png":::

1. Alternatif olarak, yönetim merkezinde **Faturalama** \> **Abonelikleri'ne** gidin.

    Ekranda sağlanan tüm lisansları ve geçerli **Durumlarını** görürsünüz.

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="Faturalama lisansları sayfası" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>Bulut Hizmeti Sağlayıcısı doğrulaması

Şirketinize sağlanan lisanslara erişmek ve lisansların durumunu denetlemek için yönetim merkezine gidin.

1. **İş ortağı portalından** **Hizmetleri > Office 365 yönet'i** seçin.

2. **İş ortağı portalı** bağlantısına tıklanması **, Yönetici adına** seçeneğini açar ve müşteri yönetim merkezine erişmenizi sağlar.

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="Office 365 yönetim portalı" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>Kiracı Yapılandırması

Uç Nokta için Microsoft Defender eklemek kolaydır. Gezinti menüsünde Uç Noktalar bölümünden herhangi bir öğeyi veya ekleme işlemini başlatmak için Olaylar, Tehdit Avcılığı, İşlem merkezi veya Tehdit analizi gibi herhangi bir Microsoft 365 Defender özelliğini seçin.

Web tarayıcısından <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin.

## <a name="data-center-location"></a>Veri merkezi konumu
Uç Nokta için Microsoft Defender verileri [Microsoft 365 Defender tarafından kullanılan konumda](/microsoft-365/security/defender/m365d-enable) depolar ve işler. Microsoft 365 Defender henüz açılmadıysa, Uç Nokta için Microsoft Defender'a ekleme işlemi de Microsoft 365 Defender açar ve etkin Microsoft 365 güvenlik hizmetlerinin konumuna bağlı olarak yeni bir veri merkezi konumu otomatik olarak seçilir. Seçili veri merkezi konumu ekranda gösterilir.

## <a name="network-configuration"></a>Ağ yapılandırması

Kuruluş, uç noktaların İnternet'e erişmek için Ara Sunucu kullanmasını gerektirmiyorsa bu bölümü atlayın.

Uç Nokta için Microsoft Defender algılayıcısı, algılayıcı verilerini raporlamak ve Uç Nokta için Microsoft Defender hizmetiyle iletişim kurmak için Microsoft Windows HTTP (WinHTTP) gerektirir. Ekli Uç Nokta için Microsoft Defender algılayıcısı LocalSystem hesabını kullanarak sistem bağlamında çalışır. Algılayıcı, Uç Nokta için Microsoft Defender bulut hizmetiyle iletişimi etkinleştirmek için Microsoft Windows HTTP Hizmetleri'ni (WinHTTP) kullanır. WinHTTP yapılandırma ayarı, Windows internet (WinINet) internet gözatma proxy ayarlarından bağımsızdır ve yalnızca aşağıdaki bulma yöntemlerini kullanarak bir ara sunucuyu bulabilir:

- **Otomatik bulma yöntemleri**:
  - Saydam ara sunucu
  - Web Proxy Otomatik Bulma Protokolü (WPAD)

  Ağ topolojisinde Saydam ara sunucu veya WPAD uygulanmışsa, özel yapılandırma ayarlarına gerek yoktur. Proxy'de URL dışlamaları Uç Nokta için Microsoft Defender hakkında daha fazla bilgi için, izin veren URL'ler listesi için bu belgedeki [Ara Sunucu Hizmeti URL'leri](production-deployment.md#proxy-service-urls) bölümüne veya [Cihaz ara sunucusu ve İnternet bağlantısı ayarlarını yapılandırma](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) bölümüne bakın.

- **El ile statik proxy yapılandırması**:
  - Kayıt defteri tabanlı yapılandırma
  - netsh komutu kullanılarak yapılandırılan WinHTTP

    Yalnızca kararlı bir topolojideki masaüstleri için uygundur (örneğin: aynı proxy'nin arkasındaki şirket ağında bir masaüstü).

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Ara sunucuyu kayıt defteri tabanlı statik proxy kullanarak el ile yapılandırma

Bir bilgisayarın İnternet'e bağlanmasına izin verilmiyorsa, yalnızca Uç Nokta için Microsoft Defender algılayıcının tanılama verilerini raporlamasına ve Uç Nokta için Microsoft Defender hizmetleriyle iletişim kurmasına izin verecek şekilde kayıt defteri tabanlı statik proxy yapılandırın. Statik proxy, grup ilkesi (GP) aracılığıyla yapılandırılabilir. Grup ilkesi aşağıdakiler altında bulunabilir:

- Yönetim Şablonları \> Windows Bileşenleri \> Veri Toplama ve Önizleme Derlemeleri \> Bağlı Kullanıcı Deneyimi ve Telemetri Hizmeti için Kimliği Doğrulanmış Proxy kullanımını yapılandırma
- **Etkin** olarak ayarlayın ve **Kimliği Doğrulanmış Proxy kullanımını devre dışı bırak'ı** seçin

1. Grup İlkesi Yönetim Konsolu'nu açın.
2. Kuruluş uygulamalarını temel alarak bir ilke oluşturun veya mevcut bir ilkeyi düzenleyin.
3. grup ilkesi düzenleyin ve **Bağlı Kullanıcı Deneyimi ve Telemetri Hizmeti için Yönetim Şablonları \> Windows Bileşenleri \> Veri Toplama ve Önizleme Derlemeleri \> Kimliği Doğrulanmış Proxy kullanımını yapılandır'a** gidin.

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="Kullanım ilkesinin yapılandırmasıyla ilgili seçenekler" lightbox="images/atp-gpo-proxy1.png":::

4. **Etkin**'i seçin.
5. **Kimliği Doğrulanmış Proxy kullanımını devre dışı bırak'ı** seçin.
6. **Yönetim Şablonları \> Windows Bileşenleri \> Veri Toplama ve Önizleme Derlemeleri \> Bağlı kullanıcı deneyimlerini ve telemetrisini yapılandır'a** gidin.

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="Bağlı kullanıcı deneyiminin ve telemetrinin yapılandırmasıyla ilgili seçenekler" lightbox="images/atp-gpo-proxy2.png":::

7. **Etkin**'i seçin.
8. **Ara Sunucu Adı'nı** girin.

İlke, iki kayıt defteri değerini `TelemetryProxyServer` REG_SZ ve `DisableEnterpriseAuthProxy` kayıt defteri anahtarı `HKLM\Software\Policies\Microsoft\Windows\DataCollection`altında REG_DWORD olarak ayarlar.

Kayıt defteri değeri `TelemetryProxyServer` aşağıdaki dize biçimini alır:

```text
<server name or ip>:<port>
```

Örneğin: 10.0.0.6:8080

Kayıt defteri değeri `DisableEnterpriseAuthProxy` 1 olarak ayarlanmalıdır.

### <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Netsh komutunu kullanarak ara sunucuyu el ile yapılandırma

Sistem genelinde statik ara sunucuyu yapılandırmak için netsh kullanın.

> [!NOTE]
>
> - Bu, varsayılan proxy ile WinHTTP kullanan Windows hizmetleri de dahil olmak üzere tüm uygulamaları etkiler.
> - Topolojiyi değiştiren dizüstü bilgisayarlar (örneğin: ofisten eve) netsh ile arızalanır. Kayıt defteri tabanlı statik proxy yapılandırmasını kullanın.

1. Yükseltilmiş bir komut satırı açın:
    1. **Başlangıç'a** gidin ve **cmd** yazın.
    1. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Örneğin: netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>Alt düzey cihazlar için Ara Sunucu Yapılandırması

Down-Level cihazlar Windows 7 SP1 ve Windows 8.1 iş istasyonlarının yanı sıra Windows Server 2008 R2 ve daha önce Microsoft Monitoring Agent kullanılarak eklenmiş olan diğer sunucu işletim sistemlerini içerir. Bu işletim sistemleri, uç noktadan Azure'a iletişimi işlemek için Microsoft Yönetim Aracısı'nın bir parçası olarak yapılandırılmış ara sunucuya sahip olacaktır. Bir proxy'nin bu cihazlarda nasıl yapılandırıldığı hakkında bilgi için Microsoft Yönetim Aracısı Hızlı Dağıtım Kılavuzu'na bakın.

### <a name="proxy-service-urls"></a>Proxy Hizmeti URL'leri

Bunlara v20 içeren URL'ler yalnızca Windows 10, sürüm 1803 veya Windows 11 cihazlarınız varsa gereklidir. Örneğin, `us-v20.events.data.microsoft.com` yalnızca cihaz Windows 10, sürüm 1803 veya Windows 11 ise gereklidir.

Uç Nokta için Microsoft Defender algılayıcısı sistem bağlamından bağlandığından bir ara sunucu veya güvenlik duvarı anonim trafiği engelliyorsa, listelenen URL'lerde anonim trafiğe izin verildiğinden emin olun.

Aşağıdaki indirilebilir elektronik tablo, ağınızın bağlanabilmesi gereken hizmetleri ve bunların ilişkili URL'lerini listeler. Bu URL'lere erişimi reddedecek bir güvenlik duvarı veya ağ filtreleme kuralı olmadığından emin olun veya bunlar için özel olarak bir *izin verme* kuralı oluşturmanız gerekebilir.

<br>

****


|Etki alanları listesinin elektronik tablosu| Açıklama|
|---|---|
|Ticari müşteriler için Uç Nokta için Microsoft Defender URL listesi| Ticari müşteriler için hizmet konumları, coğrafi konumlar ve işletim sistemi için belirli DNS kayıtlarının elektronik tablosu. <p> [Elektronik tabloyu buradan indirin.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD için Uç Nokta için Microsoft Defender URL listesi | Gov/GCC/DoD müşterileri için hizmet konumları, coğrafi konumlar ve işletim sistemi için belirli DNS kayıtlarının elektronik tablosu. <p> [Elektronik tabloyu buradan indirin.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

## <a name="next-step"></a>Sonraki adım

[![**Aşama 3: Ekleme**.](images/onboard.png#lightbox)] <br> [3. Aşama: Ekleme](onboarding.md): Uç Nokta için Microsoft Defender hizmetinin algılayıcı verilerini alabilmesi için cihazları hizmete ekleme.
