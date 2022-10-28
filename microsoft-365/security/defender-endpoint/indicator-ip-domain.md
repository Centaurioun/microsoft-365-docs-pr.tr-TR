---
title: URL/etki alanı ve IP’ler için göstergeler oluşturun
ms.reviewer: ''
description: VARLıKLARın algılanmasını, önlenmesini ve dışlanmasını tanımlayan IP'ler ve URL'ler/etki alanları için göstergeler oluşturun.
keywords: ip, url, etki alanı, yönetme, izin verilen, engellenen, blok, temiz, kötü amaçlı, dosya karması, IP adresi, URL'ler, etki alanı, IoC önceliği, IoC çakışması,
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
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 8256340228128feef0d3f050f72a7b6ea17be576
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768225"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>URL/etki alanı ve IP’ler için göstergeler oluşturun

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

## <a name="overview"></a>Genel bakış

IP'ler ve URL'ler veya etki alanları için göstergeler oluşturarak artık kendi tehdit zekanıza göre IP'lere, URL'lere veya etki alanlarına izin verebilir veya bunları engelleyebilirsiniz. Riskli bir uygulama açtıklarında kullanıcıları bir istemle de uyarabilirsiniz. İstem, uygulamayı kullanmalarını engellemez, ancak özel bir ileti ve uygulamanın uygun kullanımını açıklayan bir şirket sayfasına bağlantılar sağlayabilirsiniz. Kullanıcılar yine de uyarıyı atlayabilir ve gerekirse uygulamayı kullanmaya devam edebilir.

Kötü amaçlı IP'leri/URL'leri engellemek için (Microsoft tarafından belirlendiği gibi), Uç Nokta için Defender şunları kullanabilir:

- Microsoft tarayıcıları için SmartScreen'i Windows Defender
- Microsoft dışı tarayıcılar veya tarayıcı dışında yapılan çağrılar için Ağ Koruması

Kötü amaçlı IP'leri/URL'leri engellemek için tehdit bilgileri veri kümesi Microsoft tarafından yönetilir.

Bazı grupların diğerlerinden daha fazla veya daha az risk altında olduğunu düşünüyorsanız, ayarlar sayfasından veya makine gruplarına göre kötü amaçlı IP'leri/URL'leri engelleyebilirsiniz.

> [!NOTE]
> IP adresleri için sınıfsız Inter-Domain Yönlendirme (CIDR) gösterimi desteklenmez.

## <a name="before-you-begin"></a>Başlamadan önce

IPS, URL'ler veya etki alanları için göstergeler oluşturmadan önce aşağıdaki önkoşulları anlamak önemlidir:

### <a name="network-protection-requirements"></a>Ağ Koruması gereksinimleri

URL/IP izin verme ve engelleme, Uç Nokta için Microsoft Defender bileşeni _Ağ Koruması'nın_ blok modunda etkinleştirilmesini gerektirir. Ağ Koruması ve yapılandırma yönergeleri hakkında daha fazla bilgi için bkz. [Ağ korumasını etkinleştirme](enable-network-protection.md).

### <a name="supported-operating-systems"></a>Desteklenen işletim sistemleri

- Windows 10, sürüm 1709 veya üzeri
- Windows 11
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2019
- Windows Server 2022
- Android ve iOS cihazları

### <a name="windows-server-2016-and-windows-server-2012-r2-requirements"></a>R2 gereksinimleri Windows Server 2016 ve Windows Server 2012

Windows Server 2016 ve Windows Server 2012 R2[, Windows sunucularını ekleme](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) yönergeleri kullanılarak eklenmelidir.

### <a name="microsoft-defender-antivirus-version-requirements"></a>virüsten koruma sürüm gereksinimlerini Microsoft Defender

_Kötü amaçlı yazılımdan koruma istemcisi sürümü_ 4.18.1906.x veya üzeri olmalıdır.

### <a name="custom-network-indicators-requirements"></a>Özel ağ göstergeleri gereksinimleri

Microsoft 365 Defender **Ayarlar** \> **Gelişmiş özelliklerinde** **Özel ağ göstergelerinin** **etkinleştirildiğinden** \> emin olun. Daha fazla bilgi için bkz [. Gelişmiş özellikler](advanced-features.md).

iOS'ta göstergelerin desteği için bkz. [iOS'ta Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).

Android'de gösterge desteği için bkz. [Android'de Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/android-configure#configure-custom-indicators).

### <a name="ioc-indicator-list-limitations"></a>IoC gösterge listesi sınırlamaları

Gösterge listesine yalnızca dış IP'ler eklenebilir. İç IP'ler için göstergeler oluşturulamaz. Web koruma senaryoları için Microsoft Edge'deki yerleşik özellikleri kullanmanızı öneririz. Microsoft Edge ağ trafiğini incelemek için [Ağ Koruması'nden](network-protection.md) yararlanarak TCP, HTTP ve HTTPS (TLS) bloklarına izin verir.

### <a name="non-microsoft-edge-and-internet-explorer-processes"></a>Microsoft Edge ve Internet Explorer dışı işlemler

Web koruma senaryoları, Microsoft Edge ve Internet Explorer dışındaki işlemler için inceleme ve zorlama için Ağ Koruması'dan yararlanıyor:

- IP, üç protokol için de desteklenir (TCP, HTTP ve HTTPS (TLS))
- Özel göstergelerde yalnızca tek IP adresleri desteklenir (CIDR blokları veya IP aralıkları yoktur)
- Şifrelenmiş URL'ler (tam yol) yalnızca birinci taraf tarayıcılarda engellenebilir (Internet Explorer, Edge)
- Şifrelenmiş URL'ler (yalnızca FQDN) üçüncü taraf tarayıcılarda engellenebilir (örneğin, Internet Explorer, Edge dışında)
- Şifrelenmemiş URL'ler için tam URL yol blokları uygulanabilir
- Çakışan URL göstergesi ilkeleri varsa, daha uzun yol uygulanır. Örneğin, URL göstergesi ilkesi `https://support.microsoft.com/office` URL göstergesi ilkesinden `https://support.microsoft.com`önceliklidir.
Eylemin gerçekleştirilişi ile URL ve IP'nin engellenmesi arasında 2 saate kadar gecikme süresi (genellikle daha az) olabilir.

### <a name="warn-mode-controls"></a>Uyarı modu denetimleri

Uyarı modunu kullanırken aşağıdaki denetimleri yapılandırabilirsiniz:

- **Atlama özelliği**
  - Edge'de İzin Ver düğmesi
  - Bildirimdeki İzin Ver düğmesi (Microsoft dışı tarayıcılar)
  - Göstergedeki atlama süresi parametresi
  - Microsoft ve Microsoft dışı tarayıcılarda zorlamayı atlama

- **Yeniden yönlendirme URL'si**
  - Göstergedeki yeniden yönlendirme URL'si parametresi
  - Edge'de URL'yi yeniden yönlendirme
  - Bildirimde yeniden yönlendirme URL'si (Microsoft dışı tarayıcılar)

Daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender tarafından bulunan uygulamaları yönetme](/cloud-app-security/mde-govern).

## <a name="ioc-ip-url-and-domain-policy-conflict-handling-order"></a>IoC IP URL'si ve etki alanı ilkesi çakışması işleme sırası

İlke çakışması işleme aşağıdaki sırayı izler:

- MDCA, tüm kullanıcılar için tasdik edilmemiş bir gösterge oluşturur, ancak belirli bir cihaz grubu için URL'ye izin verilir, belirli cihaz grubu URL'ye erişimi engellenir.
- IP, URL/Etki Alanı'na izin veriliyorsa
- IP, URL/Etki Alanı'na izin verilmiyorsa
- IP, URL/Etki Alanı'na izin veriliyorsa
- IP, URL/Etki Alanı'na izin verilmiyorsa
- IP, URL/Etki Alanı'na izin veriliyorsa

Aynı zorlama türüne ve hedefe sahip çakışan dosya IoC ilkeleri varsa, daha güvenli olan ilke uygulanır.

Etki alanları/URL'ler/IP adresleri için ilke çakışması işleme, Sertifikalar için ilke çakışması işlemesinden farklıdır.

Tehdit ve güvenlik açığı yönetiminin güvenlik açığı olan uygulama özelliklerini engellemesi, zorlama için dosya ICS'lerini kullanır ve yukarıdaki çakışma işleme sırasını izler.

## <a name="policy-precedence"></a>İlke önceliği

Uç Nokta için Microsoft Defender ilkesi Microsoft Defender Virüsten Koruma ilkesine göre önceliklidir. Uç Nokta için **Defender'ın İzin Ver** olarak ayarlandığı ancak virüsten koruma Microsoft Defender **Engelle** olarak ayarlandığı durumlarda, ilke varsayılan olarak **İzin Ver** olarak ayarlanır.

### <a name="precedence-for-multiple-active-policies"></a>Birden çok etkin ilke için öncelik

Aynı cihaza birden çok farklı web içeriği filtreleme ilkesi uygulanması, her kategori için daha kısıtlayıcı ilkenin uygulanmasına neden olur. Aşağıdaki senaryoyu inceleyin:

- **İlke 1** , 1 ve 2 kategorilerini engeller ve gerisini denetler
- **İlke 2** , 3 ve 4 kategorilerini engeller ve gerisini denetler

Sonuç, 1-4 kategorilerinin tümünün engellenmesidir. Bu, aşağıdaki görüntüde gösterilmiştir.

:::image type="content" source="images/web-content-filtering-policies-mode-precedence.png" alt-text="Web içeriği filtreleme ilkesi engelleme modunun denetim moduna göre önceliğini gösteren diyagram.":::

## <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Ayarlar sayfasından IP'ler, URL'ler veya etki alanları için bir gösterge oluşturma

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Göstergeleri'ni** seçin ( **Kurallar'ın** altında).

2. **IP adresleri veya URL'ler/Etki Alanları** sekmesini seçin.

3. **Öğe ekle'yi** seçin.

4. Aşağıdaki ayrıntıları belirtin:
   - Gösterge - Varlık ayrıntılarını belirtin ve göstergenin süre sonunu tanımlayın.
   - Eylem - Gerçekleştirilecek eylemi belirtin ve bir açıklama sağlayın.
   - Kapsam - Makine grubunun kapsamını tanımlayın.

5. Özet sekmesinde ayrıntıları gözden geçirin ve **Kaydet'e** tıklayın.

## <a name="related-topics"></a>İlgili konular

- [Göstergeleri oluşturun](manage-indicators.md)
- [Dosyalar için göstergeler oluşturun](indicator-file.md)
- [Sertifikaları temel alan göstergeler oluşturma](indicator-certificates.md)
- [Göstergeleri yönetin](indicator-manage.md)
