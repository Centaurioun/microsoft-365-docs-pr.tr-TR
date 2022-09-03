---
title: Saldırı yüzeyi azaltma kurallarıyla ilgili sorunları giderme
description: Uç Nokta için Microsoft Defender saldırı yüzeyi azaltma kurallarıyla ilgili sorunları gidermek için kaynaklar ve örnek kod.
keywords: sorun giderme, hata, düzeltme, windows defender eg, asr, kurallar, kalçalar, sorun giderme, denetim, dışlama, hatalı pozitif, bozuk, engelleme, Uç Nokta için Microsoft Defender
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: ced2de009678bc58ac103a05c53557b6198e52f8
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584253"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Saldırı yüzeyi azaltma kurallarıyla ilgili sorunları giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

[Saldırı yüzeyi azaltma kurallarını](attack-surface-reduction.md) kullandığınızda aşağıdaki gibi sorunlarla karşılaşabilirsiniz:

- Kural bir dosyayı, işlemi engeller veya yapmaması gereken başka bir eylem gerçekleştirir (hatalı pozitif)
- Kural açıklandığı gibi çalışmaz veya olması gereken bir dosyayı veya işlemi engellemez (hatalı negatif)

Bu sorunları gidermenin dört adımı vardır:

1. [Önkoşulları onaylama](#confirm-prerequisites)
2. [Kuralı test etmek için denetim modunu kullanma](#use-audit-mode-to-test-the-rule)
3. [Belirtilen kural için dışlamalar ekleme](#add-exclusions-for-a-false-positive) (hatalı pozitifler için)
4. [Destek günlüklerini gönderme](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Önkoşulları onaylama

Saldırı yüzeyi azaltma kuralları yalnızca aşağıdaki koşullara sahip cihazlarda çalışır:

- Uç noktalar Windows 10 Enterprise sürüm 1709 (Fall Creators Update olarak da bilinir) çalıştırıyor.

- Uç noktalar, tek virüsten koruma uygulaması olarak Microsoft Defender Virüsten Koruma kullanıyor. [Başka bir virüsten koruma uygulamasının kullanılması Microsoft Defender Virüsten Koruma'nın kendisini devre dışı bırakmasına neden olur](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

- [Gerçek zamanlı koruma](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) etkindir.

- Denetim modu etkinleştirilmedi. [Saldırı yüzeyi azaltma kurallarını etkinleştirme](enable-attack-surface-reduction.md) bölümünde açıklandığı gibi kuralı **Devre Dışı** (değer: **0**) olarak ayarlamak için grup ilkesi kullanın.

Bu önkoşulların tümü karşılandıysa, kuralı denetim modunda test etmek için sonraki adıma geçin.

## <a name="use-audit-mode-to-test-the-rule"></a>Kuralı test etmek için denetim modunu kullanma

Sorun yaşadığınız belirli kuralı test [etmek için saldırı yüzeyi azaltma kurallarının nasıl çalıştığını görmek için tanıtım aracını kullanma](evaluate-attack-surface-reduction.md) başlığı altında bu yönergeleri izleyin.

1. Test etmek istediğiniz belirli bir kural için denetim modunu etkinleştirin. [Saldırı yüzeyi azaltma kurallarını etkinleştirme](enable-attack-surface-reduction.md) bölümünde açıklandığı gibi kuralı **Denetim moduna** (değer: **2**) ayarlamak için grup ilkesi kullanın. Denetim modu, kuralın dosyayı veya işlemi raporlamasına izin verir, ancak yine de çalışmasına izin verir.

2. Soruna neden olan etkinliği gerçekleştirin (örneğin, engellenmesi gereken ancak izin verilen dosyayı veya işlemi açın veya yürütin).

3. Kuralın etkin olarak ayarlanmış olması durumunda kuralın dosyayı veya işlemi engelleyip engellemediğini görmek için [saldırı yüzeyi azaltma kuralı olay günlüklerini gözden geçirin](attack-surface-reduction.md)**.**

Kural, beklediğiniz bir dosyayı veya işlemi engellemediyse önce denetim modunun etkinleştirilip etkinleştirilmediğini denetleyin.

Denetim modu başka bir özelliği test etme amacıyla veya otomatik bir PowerShell betiği tarafından etkinleştirilmiş olabilir ve testler tamamlandıktan sonra devre dışı bırakılmamış olabilir.

Kuralı tanıtım aracıyla ve denetim moduyla test ettiyseniz ve saldırı yüzeyi azaltma kuralları önceden yapılandırılmış senaryolar üzerinde çalışıyorsa ancak kural beklendiği gibi çalışmıyorsa, durumunuz temelinde aşağıdaki bölümlerden herhangi biriyle devam edin:

1. Saldırı yüzeyi azaltma kuralı engellememesi gereken bir şeyi engelliyorsa (hatalı pozitif olarak da bilinir), [önce bir saldırı yüzeyi azaltma kuralı dışlaması ekleyebilirsiniz](#add-exclusions-for-a-false-positive).

2. Saldırı yüzeyi azaltma kuralı engellenmesi gereken bir şeyi engelliyorsa (hatalı negatif olarak da bilinir), [tanılama verilerini toplayarak ve sorunu bize göndererek son adıma](#collect-diagnostic-data-for-file-submissions) hemen geçebilirsiniz.

## <a name="add-exclusions-for-a-false-positive"></a>Hatalı pozitif için dışlama ekleme

Saldırı yüzeyi azaltma kuralı engellememesi gereken bir şeyi engelliyorsa (hatalı pozitif olarak da bilinir), saldırı yüzeyi azaltma kurallarının dışlanan dosyaları veya klasörleri değerlendirmesini önlemek için dışlamalar ekleyebilirsiniz.

Dışlama eklemek için bkz [. Saldırı yüzeyini azaltmayı özelleştirme](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules).

> [!IMPORTANT]
> Dışlanacak tek tek dosya ve klasörleri belirtebilirsiniz, ancak tek tek kuralları belirtemezsiniz.
> Bu, dışlanan tüm dosya veya klasörlerin tüm ASR kurallarının dışında tutulacağı anlamına gelir.

## <a name="report-a-false-positive-or-false-negative"></a>Hatalı pozitif veya hatalı negatifi bildirme

Ağ koruması için hatalı negatif veya hatalı pozitif raporlamak için [Windows Defender Güvenlik Zekası web tabanlı gönderim formunu](https://www.microsoft.com/wdsi/filesubmission) kullanın. Windows E5 aboneliğiyle [, ilişkili tüm uyarıların bağlantısını da sağlayabilirsiniz](alerts-queue.md).

## <a name="collect-diagnostic-data-for-file-submissions"></a>Dosya gönderimleri için tanılama verilerini toplama

Saldırı yüzeyi azaltma kurallarıyla ilgili bir sorun bildirdiğinizde, sorunları gidermeye yardımcı olmak için Microsoft destek ve mühendislik ekipleri tarafından kullanılabilecek tanılama verilerini toplayıp göndermeniz istenir.

1. Yükseltilmiş bir komut istemi açın ve Windows Defender dizinine geçin:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Tanılama günlüklerini oluşturmak için şu komutu çalıştırın:

   ```console
   mpcmdrun -getfiles
   ```

3. Varsayılan olarak, öğesine kaydedilirler `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`. Dosyayı gönderme formuna ekleyin.

## <a name="related-articles"></a>İlgili makaleler

- [Saldırı yüzeyini azaltma kuralları](attack-surface-reduction.md)
- [Saldırı yüzeyi azaltma kurallarını etkinleştirme](enable-attack-surface-reduction.md)
- [Saldırı yüzeyi azaltma kurallarını değerlendirme](evaluate-attack-surface-reduction.md)
