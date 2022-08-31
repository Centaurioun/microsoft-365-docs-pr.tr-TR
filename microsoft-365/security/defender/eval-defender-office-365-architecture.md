---
title: Office 365 için Microsoft Defender için mimari gereksinimlerini ve planlama kavramlarını gözden geçirin
description: Microsoft 365 Defender'daki Office 365 için Microsoft Defender için teknik diyagram, deneme laboratuvarınızı veya pilot ortamınızı oluşturmadan önce Microsoft 365'teki kimliği anlamanıza yardımcı olur.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: c4bf7a3c2449bd330bebcb6e4fa33dd2c2fb4584
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480525"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Office 365 için Microsoft Defender mimarisi gereksinimlerini ve temel kavramları gözden geçirin


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Office 365 için Microsoft Defender için değerlendirme ortamını ayarlama işleminde [3.Adım 1'dir](eval-defender-office-365-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-office-365-overview.md) bakın.

Office 365 için Defender etkinleştirmeden önce mimariyi anladığınızdan ve gereksinimleri karşılayabildiğinize emin olun. Bu makalede mimari, temel kavramlar ve Exchange Online ortamınızın karşılaması gereken önkoşullar açıklanmaktadır.

## <a name="understand-the-architecture"></a>Mimariyi anlama

Aşağıdaki diyagramda Office için Microsoft Defender'ın üçüncü taraf SMTP ağ geçidi veya şirket içi tümleştirme içerebilen temel mimarisi gösterilmektedir. Karma birlikte kullanım senaryoları (yani üretim posta kutuları hem şirket içi hem de çevrimiçidir) daha karmaşık yapılandırmalar gerektirir ve bu makalede veya değerlendirme kılavuzunda ele alınmaz.

:::image type="content" source="../../media/defender/m365-defender-office-architecture.png" alt-text="Office 365 için Microsoft Defender mimarisi" lightbox="../../media/defender/m365-defender-office-architecture.png":::

Aşağıdaki tabloda bu çizim açıklanmaktadır.

|Açıklama balonu  |Açıklama  |
|---------|---------|
|1     | Dış gönderenin konak sunucusu genellikle bir MX kaydı için genel DNS araması gerçekleştirir ve bu da iletiyi geçirmesi için hedef sunucu sağlar.  Bu başvuru doğrudan Exchange Online (EXO) veya EXO'ya geçiş için yapılandırılmış bir SMTP ağ geçidi olabilir.  |
|2     | Exchange Online Protection gelen bağlantıda anlaşma yapıp doğrular ve hangi ek ilkelerin, etiketlemenin veya işlemenin gerekli olduğunu belirlemek için ileti üst bilgilerini ve içeriğini inceler.  |
|3     | Exchange Online daha gelişmiş tehdit koruması, risk azaltma ve düzeltme sunmak için Office 365 için Microsoft Defender ile tümleştirilir. |
|4     | Kötü amaçlı olmayan, engellenmeyen veya karantinaya alınmayan bir ileti işlenir ve EXO'da alıcıya teslim edilir; burada gereksiz posta, posta kutusu kuralları veya diğer ayarlarla ilgili kullanıcı tercihleri değerlendirilir ve tetiklenir. |
|5     | posta özellikli nesneleri ve hesapları Azure Active Directory'ye eşitlemek ve sağlamak ve sonuçta Exchange Online sağlamak için şirket içi Active Directory ile tümleştirme Azure AD Connect kullanılarak etkinleştirilebilir. |
|6     | Şirket içi ortamı tümleştirirken, postayla ilgili özniteliklerin, ayarların ve yapılandırmaların desteklenen yönetimi ve yönetimi için bir Exchange sunucusu kullanılması teşvik edilir |
|7     | Office 365 için Microsoft Defender, genişletilmiş algılama ve yanıt (XDR) için sinyalleri Microsoft 365 Defender paylaşır.|

Şirket içi tümleştirme yaygın ancak isteğe bağlıdır. Ortamınız yalnızca buluta yönelikse, bu kılavuz sizin için de çalışır.

## <a name="understand-key-concepts"></a>Temel kavramları anlama

Aşağıdaki tabloda MDO değerlendirilirken, yapılandırılırken ve dağıtılırken anlaşılması gereken önemli kavramlar tanımlanmıştır.


|Kavram  |Açıklama |Daha fazla bilgi  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP), kuruluşunuzu istenmeyen postalara ve kötü amaçlı yazılım e-postalarına karşı korumaya yardımcı olan bulut tabanlı filtreleme hizmetidir. EOP, Exchange Online içeren tüm Microsoft 365 lisanslarına dahildir.     |   [Exchange Online Protection’a genel bakış](../office-365-security/exchange-online-protection-overview.md)      |
|Kötü amaçlı yazılımdan koruma     |    EXO'da posta kutuları olan kuruluşlar kötü amaçlı yazılımlara karşı otomatik olarak korunur.     |  [EOP'de kötü amaçlı yazılımdan koruma](../office-365-security/anti-malware-protection.md)       |
|İstenmeyen posta önleme koruma     |   EXO'da posta kutuları olan kuruluşlar, gereksiz posta ve istenmeyen posta ilkelerine karşı otomatik olarak korunur.      |  [EOP'de istenmeyen posta önleme koruması](../office-365-security/anti-spam-protection.md)       |
|Kimlik avından koruma |  MDO, zıpkınla kimlik avı, balina avı, fidye yazılımı ve diğer kötü amaçlı etkinliklerle ilgili daha gelişmiş kimlik avı koruması sunar.   | [Office 365 için Microsoft Defender'de ekstra kimlik avı koruması](../office-365-security/anti-phishing-protection.md)   |
|Kimlik sahtekarlığına karşı koruma     |   EOP, kuruluşunuzu sahte (sahte) gönderenlerden korumaya yardımcı olan özellikler içerir.      |   [EOP'de kimlik sahtekarlığına karşı koruma](../office-365-security/anti-spoofing-protection.md)      |
|Güvenli ekler     |   Güvenli Ekler, e-posta iletilerindeki ekleri teslim etmeden önce denetlemek ve "patlatmak" için bir sanal ortam kullanarak ek bir koruma katmanı sağlar.      |   [Office 365 için Microsoft Defender'da Güvenli Ekler](../office-365-security/safe-attachments.md)      |
|SharePoint, OneDrive ve Microsoft Teams için güvenli ekler     |    Ayrıca, SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler, bulut depolama depolarına yüklenmiş dosyalar için ek bir koruma katmanı sunar.     |  [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|Güvenli Bağlantılar     | Güvenli Bağlantılar, gelen e-posta iletilerinde URL taraması ve yeniden yazma sağlayan ve bu bağlantıların teslim veya tıklanmadan önce doğrulanmasını sağlayan bir özelliktir.        |   [Office 365 için Microsoft Defender'da Güvenli Bağlantılar](../office-365-security/safe-links.md)      |
|    |         |         |

Office için Microsoft Defender'da bulunan özellikler hakkında daha ayrıntılı bilgi için bkz. [Office 365 için Microsoft Defender hizmet açıklaması](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="review-architecture-requirements"></a>Mimari gereksinimleri gözden geçirin
Başarılı bir MDO değerlendirmesi veya üretim pilotu aşağıdaki önkoşulları varsayar:
- Tüm alıcı posta kutularınız şu anda Exchange Online.
- Genel MX kaydınız doğrudan EOP'ye veya bir üçüncü taraf SMTP ağ geçidine çözümlenip gelen dış e-postayı doğrudan EOP'ye aktarır.
- Birincil e-posta etki alanınız Exchange Online *yetkili* olarak yapılandırılır.
- *Dizin Tabanlı Uç Engellemeyi* (DBEB) uygun şekilde başarıyla dağıtıp yapılandırdıysanız. Daha fazla bilgi için bkz. [Geçersiz alıcılara gönderilen iletileri reddetmek için Edge Engelleme Directory-Based kullanma](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

> [!IMPORTANT]
> Bu gereksinimler geçerli değilse veya hala karma bir birlikte kullanım senaryosundaysanız, Office 365 için Microsoft Defender değerlendirmesi bu kılavuzda tam olarak ele alınmayan daha karmaşık veya gelişmiş yapılandırmalar gerektirebilir.

## <a name="siem-integration"></a>SIEM tümleştirmesi

Kuruluşunuz genelindeki güvenlik olaylarını daha kapsamlı bir şekilde analiz etmek ve etkili ve anında yanıt almak için playbook'lar oluşturmak için Office 365 için Microsoft Defender Microsoft Sentinel ile tümleştirebilirsiniz. Daha fazla bilgi için bkz[. Office 365 için Microsoft Defender gelen uyarıları bağlama](/azure/sentinel/connect-office-365-advanced-threat-protection).

Office 365 için Microsoft Defender, [Office 365 Etkinlik Yönetimi API'sini](/office/office-365-management-api/office-365-management-activity-api-reference) kullanarak diğer Güvenlik Bilgileri ve Olay Yönetimi (SIEM) çözümleriyle de tümleştirilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Adım 2 / 3: [Değerlendirme ortamını etkinleştirme Office 365 için Microsoft Defender](eval-defender-office-365-enable-eval.md)

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün 
