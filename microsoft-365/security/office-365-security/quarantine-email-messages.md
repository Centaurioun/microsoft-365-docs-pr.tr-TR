---
title: Karantinaya alınan e-posta iletileri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, tehlikeli veya istenmeyen iletilerin bulunduğu Exchange Online Protection (EOP) içinde karantina hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: af99da8ddaddcbf8c9fd746496a66242c57abd5b
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596819"
---
# <a name="quarantined-email-messages-in-eop-and-defender-for-office-365"></a>EOP ve Office 365 için Defender'de karantinaya alınmış e-posta iletileri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, tehlikeli veya istenmeyen iletileri barındırmak için karantina kullanılabilir.

Kötü amaçlı yazılımdan koruma ilkeleri _, herhangi_ bir ekin kötü amaçlı yazılım içerdiği tespit edilirse iletiyi otomatik olarak karantinaya alır. Daha fazla bilgi için bkz. [EOP'de kötü amaçlı yazılımdan koruma ilkelerini yapılandırma](configure-anti-malware-policies.md).

Varsayılan olarak, istenmeyen posta önleme ilkeleri kimlik avı ve yüksek güvenilirlikli kimlik avı iletilerini karantinaya alır ve istenmeyen posta, yüksek güvenilirlikli istenmeyen posta ve toplu e-posta iletilerini kullanıcının Gereksiz Email klasörüne teslim eder. Ancak istenmeyen postaları, yüksek güvenilirlikli istenmeyen postaları ve toplu e-posta iletilerini karantinaya almak için istenmeyen posta önleme ilkeleri oluşturabilir ve özelleştirebilirsiniz. Daha fazla bilgi için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

Hem kullanıcılar hem de yöneticiler karantinaya alınmış iletilerle çalışabilir:

- _Karantina ilkeleri_ , kullanıcıların karantinaya alınan iletilere ne yapmalarına veya yapmalarına izin verilip verilmeyeceğini, iletinin neden karantinaya alındığına (desteklenen özellikler için) göre tanımlar. Varsayılan karantina ilkeleri, aşağıda açıklandığı gibi geçmiş özellikleri zorunlu kılmaktadır. Yöneticiler, kullanıcılar için daha az kısıtlayıcı veya daha kısıtlayıcı özellikler tanımlayan özel karantina ilkeleri oluşturup uygulayabilir ve ayrıca karantina bildirimlerini açabilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).

- Yöneticiler tüm kullanıcılar için tüm karantinaya alınmış ileti türleriyle çalışabilir. Varsayılan olarak, yalnızca yöneticiler kötü amaçlı yazılım, yüksek güvenilirlikli kimlik avı veya posta akışı kuralları (taşıma kuralları olarak da bilinir) nedeniyle karantinaya alınan iletilerle çalışabilir. Daha fazla bilgi için bkz. [Karantinaya alınan iletileri ve dosyaları EOP'de yönetici olarak yönetme](manage-quarantined-messages-and-files.md).

- Varsayılan olarak, kullanıcılar alıcı oldukları ve iletinin istenmeyen posta, toplu e-posta veya kimlik avı (yüksek güvenilirlikli kimlik avı değil) olarak karantinaya alındığı karantinaya alınmış iletilerle çalışabilir. Daha fazla bilgi için bkz. [Karantinaya alınan iletileri EOP'de kullanıcı olarak bulma ve bırakma](find-and-release-quarantined-messages-as-a-user.md).

  Kullanıcıların kendi karantinaya alınan kimlik avı iletilerini yönetmesini önlemek için yöneticiler, istenmeyen posta önleme ilkelerindeki **Kimlik Avı e-posta** filtreleme kararından karantinaya alınan iletilere erişimi reddeden bir karantina ilkesi atayabilir. Daha fazla bilgi için bkz. [İstenmeyen posta önleme ilkelerine karantina ilkeleri atama](quarantine-policies.md#anti-spam-policies)[İlkeleri karantinaya](quarantine-policies.md) alma.

- Yöneticiler ve kullanıcılar karantinada Microsoft'a hatalı pozitif sonuçları bildirebilir.

- Karantinaya alınan iletilerin süresi dolmadan önce karantinada tutulma süresi, iletinin neden karantinaya alındığına bağlı olarak değişir. İletileri karantinaya alan özellikler ve karşılık gelen saklama süreleri aşağıdaki tabloda açıklanmıştır:

  |Karantina nedeni|Varsayılan saklama süresi|Özelleştirilebilir?|Açıklamalar|
  |---|---|:---:|---|
  |İstenmeyen posta önleme ilkeleri tarafından karantinaya alınan iletiler: istenmeyen posta, yüksek güvenilirlikli istenmeyen posta, kimlik avı, yüksek güvenilirlikli kimlik avı veya toplu.|15 gün: <ul><li>Varsayılan istenmeyen posta önleme ilkesinde.</li><li>PowerShell'de oluşturduğunuz istenmeyen posta önleme ilkelerinde.</li></ul> <p> Microsoft 365 Defender portalında oluşturduğunuz istenmeyen posta önleme ilkelerinde 30 gün.|Evet|İstenmeyen posta önleme ilkelerinde bu değeri yapılandırabilirsiniz (daha düşük). Daha fazla bilgi **için İstenmeyen postaları bu kadar gün boyunca karantinada tutma** (_QuarantineRetentionPeriod_) [ayarına bakın](configure-your-spam-filter-policies.md).|
  |Kimlik avı önleme ilkeleri tarafından karantinaya alınan iletiler: EOP'de kimlik sahtekarlığı zekası; Office 365 için Defender kullanıcı kimliğe bürünme, etki alanı kimliğe bürünme veya posta kutusu zekası.|30 gün|Evet|Bu saklama süresi, **istenmeyen postayı bu kadar gün boyunca karantinada tut** (_QuarantineRetentionPeriod_) ayarı ile **de istenmeyen posta** önleme ilkeleri tarafından denetlenmiştir. Kullanılan saklama süresi, alıcının tanımlandığı ilk eşleşen **istenmeyen posta önleme** ilkesindeki değerdir.|
  |Kötü amaçlı yazılımdan koruma ilkeleri (kötü amaçlı yazılım iletileri) tarafından karantinaya alınan iletiler.|30 gün|Hayır||
  |Office 365 için Defender'da Güvenli Ekler ilkeleri tarafından karantinaya alınan iletiler (kötü amaçlı yazılım iletileri).|30 gün|Hayır||
  |Posta akışı kuralları tarafından karantinaya alınan iletiler: eylem, **İletiyi barındırılan karantinaya teslim etme** (_Karantina_) eylemidir.|30 gün|Hayır||
  |SharePoint, OneDrive ve Microsoft Teams (kötü amaçlı yazılım dosyaları) için Güvenli Ekler tarafından karantinaya alınan dosyalar.|30 gün|Hayır||

  Bir iletinin karantina süresi dolduğunda, bu iletiyi kurtaramazsınız.

Karantina hakkında daha fazla bilgi için bkz. [Karantina SSS](quarantine-faq.yml).
