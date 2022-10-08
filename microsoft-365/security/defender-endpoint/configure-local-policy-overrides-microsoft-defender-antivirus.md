---
title: Microsoft Defender Virüsten Koruma ayarları için yerel geçersiz kılmaları yapılandırma
description: Microsoft Defender Virüsten Koruma'da kullanıcıların ayarları yerel olarak değiştirmesini etkinleştirin veya devre dışı bırakın.
keywords: yerel geçersiz kılma, yerel ilke, grup ilkesi, gpo, kilitleme,birleştirme, listeler
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 08/02/2022
ms.reviewer: ''
manager: dansimp
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 5d1857105c8043a38b486f435506a4dca017fee4
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68172235"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Kullanıcıların Microsoft Defender Virüsten Koruma ilkesi ayarlarını yerel olarak değiştirmesini engelleme veya izin verme


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Varsayılan olarak, ağınızdaki uç noktalara bir grup ilkesi Nesnesi aracılığıyla dağıtılan virüsten koruma ayarlarını Microsoft Defender, kullanıcıların ayarları yerel olarak değiştirmesini engeller. Bazı durumlarda bu yapılandırmayı değiştirebilirsiniz. Örneğin, güvenlik araştırmacıları ve tehdit araştırmacıları gibi belirli kullanıcı gruplarının kullandıkları uç noktalarda tek tek ayarlar üzerinde daha fazla denetim sahibi olmalarına izin vermek gerekebilir.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Microsoft Defender Virüsten Koruma ayarları için yerel geçersiz kılmaları yapılandırma

Bu yerel geçersiz kılma ilkeleri için varsayılan ayar **Devre Dışı'dır**.

İlkeler **Etkin** olarak ayarlanırsa, kullanıcılar Windows Güvenliği uygulamasını, yerel [grup ilkesi](microsoft-defender-security-center-antivirus.md) ayarlarını veya PowerShell cmdlet'lerini (uygun olduğunda) kullanarak cihazlarında ilişkili ayarlarda değişiklik yapabilir.

[Ayarlar bölümünde](#table-of-settings) geçersiz kılma ilkesi ayarları ve yapılandırma yönergeleri listelenir.

Bu ayarları yapılandırmak için:

1. grup ilkesi yönetim bilgisayarınızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesi'ne sağ tıklayın ve düzenle'yi seçin.

2. **Grup İlkesi Yönetimi Düzenleyicisi**'nde **Bilgisayar yapılandırması**'na gidin ve **Yönetim şablonları**'nı seçin.

3. Ağacı **Windows bileşenleri** >  **Microsoft Defender Virüsten Koruma** ve ardından [ayarlar tablosunda](#table-of-settings) belirtilen **Konum** bölümüne (bu makalede) genişletin.

4. Aşağıdaki tabloda belirtilen ilke **Ayarı'na** çift tıklayın ve seçeneği istediğiniz yapılandırmaya ayarlayın. **Tamam'ı** seçin ve diğer ayarlar için yineleyin.

5. grup ilkesi Nesnesini her zamanki gibi dağıtın.

## <a name="table-of-settings"></a>Ayarlar tablosu

| Konum | Ayar | Makale |
|---|---|---|---|
| HARİTALAR |Microsoft MAPS'e raporlama için yerel ayarı geçersiz kılmayı yapılandırma|[Bulut tabanlı korumayı etkinleştirme](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Karantina|Öğelerin Karantina klasöründen kaldırılması için yerel ayarı geçersiz kılmayı yapılandırma|[Taramalar için düzeltmeyi yapılandırma](configure-remediation-microsoft-defender-antivirus.md) |
| Gerçek zamanlı koruma|Bilgisayarınızda dosya ve program etkinliğini izlemek için yerel ayarı geçersiz kılmayı yapılandırma|[Microsoft Defender Virüsten Koruma her zaman açık korumayı ve izlemeyi etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Gerçek zamanlı koruma|Gelen ve giden dosya etkinliği için izleme için yerel ayarı geçersiz kılmayı yapılandırma | [Microsoft Defender Virüsten Koruma her zaman açık korumayı ve izlemeyi etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Gerçek zamanlı koruma|İndirilen tüm dosya ve ekleri taramak için yerel ayarı geçersiz kılmayı yapılandırma|[Microsoft Defender Virüsten Koruma her zaman açık korumayı ve izlemeyi etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Gerçek zamanlı koruma|Davranış izlemeyi açmak için yerel ayarı geçersiz kılmayı yapılandırma|[Microsoft Defender Virüsten Koruma her zaman açık korumayı ve izlemeyi etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Gerçek zamanlı koruma|Gerçek zamanlı korumayı açmak için yerel ayarı geçersiz kılmayı yapılandırma|[Microsoft Defender Virüsten Koruma her zaman açık korumayı ve izlemeyi etkinleştirme ve yapılandırma](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Düzeltme|Düzeltmeyi tamamlamak için zamanlanmış bir tam tarama çalıştırmak üzere günün saati için yerel ayarı geçersiz kılmayı yapılandırma|[Taramalar için düzeltmeyi yapılandırma](configure-remediation-microsoft-defender-antivirus.md) |
| Tarama|Cpu kullanım yüzdesi üst sınırı için yerel ayarı geçersiz kılmayı yapılandırma|[Taramaları yapılandırma ve çalıştırma](run-scan-microsoft-defender-antivirus.md) |
| Tarama|Zamanlama tarama günü için yerel ayarı geçersiz kılmayı yapılandırma|[Zamanlanmış taramaları yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Tarama|Zamanlanmış hızlı tarama süresi için yerel ayarı geçersiz kılmayı yapılandırma|[Zamanlanmış taramaları yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Tarama|Zamanlanmış tarama süresi için yerel ayarı geçersiz kılmayı yapılandırma|[Zamanlanmış taramaları yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Tarama|Zamanlanmış tarama için kullanılacak tarama türü için yerel ayarı geçersiz kılmayı yapılandırma|[Zamanlanmış taramaları yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Yerel ve genel olarak tanımlanmış tehdit düzeltme ve dışlama listelerinin nasıl birleştirilmesini yapılandırma

Ayrıca, yerel olarak tanımlanan listelerin genel olarak tanımlanmış listelerle nasıl birleştirilmesini veya birleştirilmesini yapılandırabilirsiniz. Bu ayar [dışlama listeleri](configure-exclusions-microsoft-defender-antivirus.md), [belirtilen düzeltme listeleri](configure-remediation-microsoft-defender-antivirus.md) ve [saldırı yüzeyini azaltma](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) için geçerlidir.

Varsayılan olarak, yerel grup ilkesinde yapılandırılan listeler ve Windows Güvenliği uygulaması, ağınıza dağıttığınız uygun grup ilkesi Nesnesi tarafından tanımlanan listelerle birleştirilir. Çakışmalar olduğunda, genel olarak tanımlanan liste önceliklidir. Yalnızca genel olarak tanımlanmış listelerin (dağıtılan GPO'lardan gelenler gibi) kullanıldığından emin olmak için bu ayarı devre dışı bırakabilirsiniz.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Yerel liste birleştirmeyi devre dışı bırakmak için grup ilkesi kullanma

1. grup ilkesi yönetim bilgisayarınızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın, yapılandırmak istediğiniz grup ilkesi Nesnesine sağ tıklayın ve **Düzenle'ye** tıklayın.

2. **Grup İlkesi Yönetimi Düzenleyicisi**'nde **Bilgisayar yapılandırması**'na gidin ve **Yönetim şablonları**'nı seçin.

3. Ağacı **Windows bileşenleri** >  **Microsoft Defender Virüsten Koruma** olarak genişletin.

4. **Listeler için yerel yönetici birleştirme davranışını yapılandır'a** çift tıklayın ve seçeneği **Devre Dışı** olarak ayarlayın. Sonra **Tamam**’ı seçin.

### <a name="use-microsoft-endpoint-manager-to-disable-local-list-merging"></a>Yerel liste birleştirmeyi devre dışı bırakmak için Microsoft Endpoint Manager kullanma

1. [Microsoft Endpoint Manager yönetim merkezinde](https://endpoint.microsoft.com) **Uç nokta güvenliği** > **Virüsten Koruma'yı** seçin.

2. **İlke Oluştur'u** seçin veya mevcut Microsoft Defender Virüsten Koruma ilkesini değiştirin.

3. **Yapılandırma ayarları'nın** altında Yerel **Yönetici Birleştirmeyi Devre Dışı Bırak'ın** yanındaki açılan listeyi seçin ve **Yerel Yönetici Birleştirmeyi Devre Dışı Bırak'ı** seçin.

> [!NOTE]
> Yerel liste birleştirmeyi devre dışı bırakırsanız, denetimli klasör erişim ayarlarını geçersiz kılar. Ayrıca, yerel yönetici tarafından ayarlanan tüm korumalı klasörleri veya izin verilen uygulamaları geçersiz kılar. Denetimli klasör erişim ayarları hakkında daha fazla bilgi için bkz. [Windows Güvenliği'de engellenen uygulamaya izin verme](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)

## <a name="related-topics"></a>İlgili konular

- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview)
- [Windows’da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Virüsten Koruma ile son kullanıcı etkileşimlerini yapılandırma](configure-end-user-interaction-microsoft-defender-antivirus.md)
