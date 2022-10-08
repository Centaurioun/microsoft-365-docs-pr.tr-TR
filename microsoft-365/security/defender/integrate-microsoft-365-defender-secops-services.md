---
title: Adım 3. SOC hizmet kataloğunuzla Microsoft 365 Defender tümleştirmeyi planlama
description: Microsoft 365 Defender hizmet güvenlik işlemleri kataloğunuzla tümleştirmenin temelleri.
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
- m365-security
- m365solution-m365dsecops
- tier2
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9013f89e38bae603f73039191d256aa19ed47b2
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051577"
---
# <a name="step-3-plan-for-microsoft-365-defender-integration-with-your-soc-catalog-of-services"></a>Adım 3. SOC hizmet kataloğunuzla Microsoft 365 Defender tümleştirmeyi planlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Yerleşik bir Güvenlik İşlemLeri Merkezi'nin (SOC) şunları içerebilecek bir hizmet kataloğu olmalıdır:

- İzinsiz giriş & kötü amaçlı yazılım analizi
- Atıf & tersine mühendislik
- Tehdit bilgileri
- Analytics
- Avcılık araştırması
- Adli tıp
- Olay yanıtı 
- Bilgisayar Güvenlik Olayı Yanıt Ekibi (CSIRT) (SOC'den ayrılmış olabilir) 
- Uyumluluk testi
- Insider tehdit & sahtekarlık izleme
- Güvenlik olayı & olay izleme 
- Güvenlik açığı taraması
- Genişletilmiş Algılama ve Yanıt (XDR)/Güvenlik Düzenlemesi, Otomasyon ve Yanıt (SOAR)
- Kimlik Avı
- Veri kaybı önleme
- Marka izleme

Microsoft 365 Defender teknolojiler çeşitli işlevlere yayıldığından, SOC ekibinizin Microsoft 365 Defender her bileşenini yönetmek ve hizmet işlevine uyum sağlamak için en uygun rolleri ve sorumlulukları belirlemesi gerekir.

Microsoft 365 Defender bileşenleri şunlardır:

- **Kimlik için Microsoft Defender** (eski adıyla Azure Gelişmiş Tehdit Koruması, Azure ATP olarak da bilinir), gelişmiş tehditleri, güvenliği aşılmış kimlikleri ve yönlendirilen kötü amaçlı insider eylemlerini tanımlamak, algılamak ve araştırmak için Active Directory Domain Services (AD DS) sinyallerini kullanan bulut tabanlı bir güvenlik çözümüdür Kuruluş.

- **Uç Nokta için Microsoft Defender**, risk tabanlı güvenlik açığı yönetimi ve değerlendirmesi, saldırı yüzeyi azaltma, davranış tabanlı ve bulut destekli yeni nesil koruma, uç nokta algılama ve yanıt (EDR), otomatik araştırma ve düzeltme, yönetilen avcılık hizmetleri, zengin API'ler ve birleşik güvenlik yönetimi içeren cihazlar için bütünsel, bulut tarafından sunulan bir uç nokta güvenlik çözümüdür .

 - **Office 365 için Microsoft Defender**, sağlam sıfır gün koruması sağlayarak kuruluşların bilinmeyen kötü amaçlı yazılımlara ve virüslere karşı korunmasına yardımcı olan bulut tabanlı bir e-posta filtreleme hizmetidir ve kuruluşları gerçek zamanlı olarak zararlı bağlantılardan korumaya yönelik özellikler içerir. Ayrıca kapsamlı bir araştırma ve avcılık, yanıt ve düzeltme, farkındalık ve eğitim ve güvenli duruş özellikleri sunar.

- **Microsoft Defender for Cloud Apps** günlük toplama, API bağlayıcıları ve ters ara sunucu gibi çeşitli dağıtım modlarını destekleyen bir bulut erişim güvenlik aracısıdır (CASB). Tüm Microsoft ve üçüncü taraf bulut hizmetlerinde siber tehditleri belirlemek ve mücadele etmek için zengin görünürlük, veri seyahati üzerinde denetim ve gelişmiş analiz sağlar.

Microsoft 365 Defender bileşenler ve teknolojiler çeşitli işlevlere yayıldığından, SOC ekibinizin Microsoft 365 Defender her bileşenini yönetmek ve hizmet işlevine uyum sağlamak için en uygun rolleri ve sorumlulukları belirlemesi gerekir.

Microsoft 365 Defender özelliklerini tümleştirmek için SOC hizmetlerini geliştirmeniz gerekir. Microsoft 365 Defender özellikleri hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Uç Nokta için Microsoft Defender nedir?](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
- [Kimlik için Microsoft Defender nedir?](/defender-for-identity/what-is)
- [Office 365 için Defender nedir?](/microsoft-365/security/defender/microsoft-365-defender)
- [Bulut Uygulamaları için Microsoft Defender nedir?](/cloud-app-security/what-is-cloud-app-security)

## <a name="next-step"></a>Sonraki adım

[4. Adım. Microsoft 365 Defender rollerini, sorumluluklarını ve gözetimlerini tanımlama](integrate-microsoft-365-defender-secops-roles.md)
