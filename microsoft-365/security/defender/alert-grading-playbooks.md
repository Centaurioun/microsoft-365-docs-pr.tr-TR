---
title: Taktik defterini notlandırma uyarısı
description: İyi bilinen saldırılara yönelik uyarıları gözden geçirin ve saldırıyı düzeltmek ve ağınızı korumak için önerilen eylemleri gerçekleştirin.
keywords: olaylar, uyarılar, araştırma, analiz etme, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
search.appverid: met150
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
- tier2
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: bdb8acc0e3b56d59f6afb6fcbf8a3f6c4c538874
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089157"
---
# <a name="alert-grading-playbooks"></a>Taktik defterini notlandırma uyarısı

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Uyarı notlama playbook'ları, uyarıları iyi bilinen saldırılar için yöntemsel olarak gözden geçirmenize ve hızla sınıflandırmanıza ve saldırıyı düzeltmek ve ağınızı korumak için önerilen eylemleri gerçekleştirmenize olanak tanır. Uyarı notları, olayın genelini düzgün sınıflandırmaya da yardımcı olur.

Bir güvenlik araştırmacısı veya güvenlik operasyonları merkezi (SOC) analisti olarak şunları yapmak için Microsoft 365 Defender portalına erişiminiz olmalıdır:

- Oluşturulan uyarıları ve ilişkili olayları değerlendirin ve gözden geçirin. Bkz [. Uyarıları araştırma](investigate-alerts.md).
- Kiracınızın güvenlik sinyali verilerini arayın ve olası tehditleri ve şüpheli etkinlikleri denetleyin. Bkz. [gelişmiş avcılık](advanced-hunting-overview.md).

>[!Note]
>Microsoft'a yalnızca araştırmanın sonunda değil, aynı zamanda araştırma süreci sırasında da gerçek pozitif ve hatalı pozitif uyarılar hakkında geri bildirim sağlayabilirsiniz. Bu, Microsoft'un güvenlik olaylarının gelecekteki analizi ve sınıflandırması konusunda yardımcı olabilir.
>

## <a name="microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender

[Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365), kuruluşunuzu e-posta iletileri, bağlantılar (URL'ler) ve işbirliği araçları tarafından ortaya konan kötü amaçlı tehditlere karşı korur. Office 365 için Defender şunları içerir:

- Tehdit koruma ilkeleri

   Kuruluşunuz için uygun koruma düzeyini ayarlamak için tehdit koruma ilkeleri tanımlayın.

- Raporlar

  Kuruluşunuzdaki Office 365 için Defender performansını izlemek için gerçek zamanlı raporları görüntüleyin.

- Tehdit araştırması ve yanıt özellikleri

  Tehditleri araştırmak, anlamak, benzetimini yapmak ve önlemek için önde gelen araçları kullanın.

- Otomatik araştırma ve yanıt özellikleri

  Tehditleri araştırmak ve azaltmak için zaman ve çabadan tasarruf edin.

Office 365 için Defender uyarıları şu şekilde sınıflandırılabilir: 

- Doğrulanmış kötü amaçlı etkinlik için gerçek pozitif (TP). 
- Doğrulanmış kötü amaçlı olmayan etkinlikler için hatalı pozitif (FP).

>[!Note]
>Microsoft 365 Defender portalı[https://security.microsoft.com](https://security.microsoft.com), mevcut Microsoft güvenlik portallarından işlevleri bir araya getirir. Microsoft 365 Defender portalı bilgilere hızlı erişimi, daha basit düzenleri vurgular ve daha kolay kullanım için ilgili bilgileri bir araya getirir.
>

## <a name="microsoft-defender-for-cloud-apps"></a>Bulut Uygulamaları için Microsoft Defender

[Microsoft Defender for Cloud Apps](/defender-cloud-apps) günlük toplama, API bağlayıcıları ve ters ara sunucu gibi çeşitli dağıtım modlarını destekleyen bir Bulut Erişim Güvenlik Aracısıdır (CASB). Tüm Microsoft ve üçüncü taraf bulut hizmetlerinizde siber tehditleri belirlemek ve bununla mücadele etmek için zengin görünürlük, veri seyahati üzerinde denetim ve gelişmiş analiz sağlar.

Cloud Apps için Defender, önde gelen Microsoft çözümleriyle yerel olarak tümleştirilir ve güvenlik uzmanları göz önünde bulundurularak tasarlanmıştır. Basit dağıtım, merkezi yönetim ve yenilikçi otomasyon özellikleri sağlar.

Cloud Apps için Defender çerçevesi, ağınızı siber tehditlere ve anomalilere karşı koruma, fidye yazılımlarını, güvenliği aşılmış kullanıcıları veya sahte uygulamaları tanımlamak için bulut uygulamaları genelinde olağan dışı davranışları algılama özelliğini içerir. Yüksek riskli kullanımın analizini sağlar ve riski kuruluşunuzla sınırlamak için otomatik olarak düzeltebilir.

Cloud Apps için Defender uyarıları şu şekilde sınıflandırılabilir: 

- Doğrulanmış kötü amaçlı etkinlik için TP. 
- Sızma testi veya başka bir yetkili şüpheli eylem gibi şüpheli ancak kötü amaçlı olmayan etkinlikler için zararsız gerçek pozitif (B-TP). 
- Onaylanan kötü amaçlı olmayan etkinlikler için FP.

## <a name="alert-grading-playbooks"></a>Taktik defterini notlandırma uyarısı

Aşağıdaki tehditler için uyarıları daha hızlı not alma adımları için bu playbook'lara bakın:

- [Şüpheli e-posta iletme etkinliği](alert-grading-playbook-email-forwarding.md)
- [Şüpheli gelen kutusu işleme kuralları](alert-grading-playbook-inbox-manipulation-rules.md)
- [Şüpheli gelen kutusu iletme kuralları](alert-grading-playbook-inbox-forwarding-rules.md)

Microsoft 365 Defender portalıyla uyarıları inceleme hakkında bilgi için bkz. Uyarıları [araştırma](investigate-alerts.md).
