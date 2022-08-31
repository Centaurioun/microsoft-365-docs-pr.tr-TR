---
title: Adım 2. Sıfır Güven Framework kullanarak SOC tümleştirme hazırlığı değerlendirmesi gerçekleştirme
description: Microsoft 365 Defender güvenlik işlemlerinizle tümleştirirken Sıfır Güven Framework kullanarak SOC tümleştirme hazırlığı değerlendirmesi gerçekleştirmenin temelleri.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı, secops, güvenlik işlemleri, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7f67deb65b6add98a4a3a5b6953a4bf9f4a7ca63
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481272"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>Adım 2. Sıfır Güven Framework kullanarak SOC tümleştirme hazırlığı değerlendirmesi gerçekleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Güvenlik İşlemleri Merkezi (SOC) ekibinin temel işlevleri tanımlandıktan sonra, kuruluşunuz için bir sonraki adım Microsoft 365 Defender [Sıfır Güven bir yaklaşımla](/security/zero-trust/) benimsenmeye hazırlanmaktır. Benimseme, modern sektör lideri uygulamaları kullanarak Microsoft 365 Defender dağıtmak için gereken gereksinimleri belirlemenize yardımcı olurken Microsoft 365 Defender özelliklerini ortamınıza göre değerlendirmenize yardımcı olabilir.

Bu yaklaşım güçlü bir koruma temelini temel alır ve kimlik, uç noktalar (cihazlar), veriler, uygulamalar, altyapı ve ağ gibi önemli alanları içerir. Hazırlık Değerlendirmesi ekibi, Microsoft 365 Defender etkinleştirmeye yönelik temel gereksinimin henüz karşılanmadığı ve düzeltilmesi gereken alanları belirler.

SoC'nin SOC'deki işlemleri tamamen iyileştirmesi için düzeltilmesi gereken öğelerden bazıları şunlardır:

- **Kimlik:** Eski şirket içi Active Directory Etki Alanı Hizmetleri (AD DS) etki alanları, MFA planı yok, ayrıcalıklı hesap envanteri yok ve diğerleri.
- **Uç noktalar (cihazlar):** Çok sayıda eski işletim sistemi, sınırlı cihaz envanteri ve diğerleri.
- **Veriler ve uygulamalar:**  Veri idare standartlarının olmaması, tümleştirilmeyecek özel uygulamaların envanterinin olmaması.
- **Altyapı:** Çok sayıda tasdik edilmemiş SaaS lisansı, kapsayıcı güvenliği yok ve diğerleri.
- **Ağ:** Düşük bant genişliği, düz ağ, kablosuz güvenlik sorunları ve diğerleri nedeniyle performans sorunları.

Kuruluşlar ayrıca temel yapılandırma gereksinimleri kümesini yakalamak için Microsoft 365 Defender makalesini [açma](m365d-enable.md) adımlarını izlemelidir. Bu adımlar, kullanım örneklerini etkili bir şekilde geliştirmek için SOC ekiplerinin gerçekleştirmesi gereken düzeltme etkinliklerini de belirler. 

Benimseme yordamları ve kullanım örneği oluşturma, 3. ve 4. Adımlarda açıklanmıştır.

## <a name="next-step"></a>Sonraki adım

[3. Adım. SOC hizmet kataloğunuzla Microsoft 365 Defender tümleştirmeyi planlama](integrate-microsoft-365-defender-secops-services.md)
