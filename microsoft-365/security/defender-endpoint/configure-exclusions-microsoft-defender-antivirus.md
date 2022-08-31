---
title: Microsoft Defender Virüsten Koruma taramaları için dışlamaları ayarlama
description: Dosyaları (belirtilen işlemler tarafından değiştirilen dosyalar dahil) ve klasörlerin Microsoft Defender Virüsten Koruma tarafından taranmasını dışlayabilirsiniz. Dışlamalarınızı PowerShell ile doğrulayın.
keywords: ''
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.subservice: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 354cb5e08845d275cf6517ec8badf4fb2c3635f8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481536"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Microsoft Defender Virüsten Koruma taramaları için dışlamaları yapılandırma ve doğrulama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma taramalarından belirli dosyaları, klasörleri, işlemleri ve işlem açılan dosyaları hariç tutabilirsiniz. Bu tür dışlamalar [zamanlanmış taramalar](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [isteğe bağlı taramalar](run-scan-microsoft-defender-antivirus.md) ve [her zaman açık gerçek zamanlı koruma ve izleme](configure-real-time-protection-microsoft-defender-antivirus.md) için geçerlidir. İşlemle açılan dosyalar için dışlamalar yalnızca gerçek zamanlı koruma için geçerlidir.

## <a name="configure-and-validate-exclusions"></a>Dışlamaları yapılandırın ve doğrulayın

Dışlamaları yapılandırmak ve doğrulamak için aşağıdakilere bakın:

- [Dosya adı, uzantı ve klasör konumu temelinde dışlamaları yapılandırın ve doğrulayın](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Dosyaları, dosya uzantısına, dosya adına veya konumuna göre Microsoft Defender Virüsten Koruma taramalarının dışında tutabilirsiniz.

- [İşlemler tarafından açılan dosyalar için dışlamaları yapılandırın ve doğrulayın](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Dosyaları belirli bir işlem tarafından açılmış taramaların dışında tutabilirsiniz.

## <a name="recommendations-for-defining-exclusions"></a>Dışlamaları tanımlama önerileri

> [!IMPORTANT]
> Microsoft Defender Virüsten Koruma, kuruluş yönetiminde, veritabanı yönetiminde ve diğer kurumsal senaryolarda ve durumlarda kullanılanlar gibi bilinen işletim sistemi davranışlarına ve tipik yönetim dosyalarına dayalı birçok otomatik dışlama içerir.
>
> Dışlamaların tanımlanması, Microsoft Defender Virüsten Koruma tarafından sunulan korumayı düşürür. Dışlamaları uygulamayla ilişkili riskleri her zaman değerlendirmeli ve yalnızca kötü amaçlı olmadığından emin olduğunuz dosyaları hariç tutmalısınız.

Dışlamaları tanımlarken aşağıdaki noktaları göz önünde bulundurun:

- Dışlamalar teknik olarak bir koruma açığıdır. Dışlamaları tanımlarken tüm seçeneklerinizi göz önünde bulundurun. Diğer seçenekler, dışlanan konumun uygun erişim denetimi listelerine (ACL' ler) sahip olduğundan emin olmak veya ilkeleri önce denetim moduna ayarlamak kadar basit olabilir.

- Dışlamaları düzenli aralıklarla gözden geçirin. Gözden geçirme işleminizin bir parçası olarak azaltmaları yeniden denetleyin ve yeniden uygulayın.

- İdeal olarak, proaktif olmak için dışlamaları tanımlamaktan kaçının. Örneğin, gelecekte bir sorun olabileceğini düşündüğünüz için bir şeyi dışlamayın. Dışlamaları yalnızca performansla ilgili sorunlar veya dışlamaların azaltabileceği uygulama uyumluluğu gibi belirli sorunlar için kullanın.

- Dışlama listenizdeki değişiklikleri gözden geçirin ve denetleyin. Güvenlik ekibiniz daha sonra karışıklığı önlemek için belirli bir dışlamanın neden eklendiğine ilişkin bağlamı korumalıdır. Güvenlik ekibiniz dışlamaların neden mevcut olduğuyla ilgili sorulara özel yanıtlar sağlayabilmelidir.

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

- [Windows Server 2016'de Microsoft Defender Virüsten Koruma dışlamaları](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Dışlamaları tanımlarken kaçınılması gereken yaygın hatalar](common-exclusion-mistakes-microsoft-defender-antivirus.md)
