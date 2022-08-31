---
title: Kimlik için Microsoft Defender için mimari gereksinimlerini ve teknik çerçeveyi gözden geçirin
description: Microsoft 365 Defender'daki Kimlik için Microsoft Defender için teknik diyagram, deneme laboratuvarınızı veya pilot ortamınızı oluşturmadan önce Microsoft 365'teki kimliği anlamanıza yardımcı olur.
search.product: eADQiWindows 10XVcnh
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
ms.date: 07/09/2021
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
ms.openlocfilehash: a8ba7bffcba998ac2fcfd45c25688c610a1561dc
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482196"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Kimlik için Microsoft Defender için mimari gereksinimlerini ve temel kavramları gözden geçirin


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Kimlik için Microsoft Defender için değerlendirme ortamını ayarlama sürecindeki [Adım 1/3'tür](eval-defender-identity-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-identity-overview.md) bakın.

Kimlik için Microsoft Defender etkinleştirmeden önce mimariyi anladığınızdan ve gereksinimleri karşılayabildiğinize emin olun.

Kimlik için Microsoft Defender, şirket içi ağınızdaki saldırıları belirlemek ve bulut kimlikleriyle ilişkili kullanıcı oturum açma risklerini algılamak ve proaktif olarak önlemek için makine öğrenmesi ve davranış analizi kullanır. Daha fazla bilgi için bkz. [Kimlik için Microsoft Defender nedir?](/defender-for-identity/what-is)

Kimlik için Defender, Şirket içi Active Directory kullanıcılarınızı ve/veya Azure Active Directory 'nizle eşitlenen kullanıcılarınızı (Azure AD) korur. Yalnızca Azure AD kullanıcılardan oluşan bir ortamı korumak için bkz. [kimlik koruması Azure AD](/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="understand-the-architecture"></a>Mimariyi anlama

Aşağıdaki diyagramda Kimlik için Defender'ın temel mimarisi gösterilmektedir. 

:::image type="content" source="../../media/defender/m365-defender-identity-architecture.png" alt-text="Kimlik için Microsoft Defender için kimlik mimarisi" lightbox="../../media/defender/m365-defender-identity-architecture.png":::

Bu çizimde:

- AD etki alanı denetleyicilerine yüklenen algılayıcılar günlükleri ve ağ trafiğini ayrıştırarak analiz ve raporlama için Kimlik için Microsoft Defender gönderir.
-  Algılayıcılar, Azure AD federasyon kimlik doğrulamasını kullanacak şekilde yapılandırıldığında da Active Directory Federasyon Hizmetleri (AD FS) (AD FS) ayrıştırabilir (çizimde noktalı çizgi). 
- Kimlik için Microsoft Defender, genişletilmiş algılama ve yanıt (XDR) için sinyalleri Microsoft 365 Defender paylaşır.

Kimlik için Defender algılayıcıları doğrudan aşağıdaki sunuculara yüklenebilir:

- Etki alanı denetleyicileri: Algılayıcı, ayrılmış sunucuya veya bağlantı noktası yansıtma yapılandırmasına gerek kalmadan etki alanı denetleyicisi trafiğini doğrudan izler.
- AD FS: Algılayıcı ağ trafiğini ve kimlik doğrulama olaylarını doğrudan izler.

Cloud Apps için Defender ile tümleştirme de dahil olmak üzere Kimlik için Defender mimarisine daha ayrıntılı bir bakış için bkz. [Kimlik için Microsoft Defender mimarisi](/defender-for-identity/architecture).


## <a name="understand-key-concepts"></a>Temel kavramları anlama

Aşağıdaki tabloda, Kimlik için Microsoft Defender değerlendirilirken, yapılandırılırken ve dağıtılırken anlaşılması gereken önemli kavramlar tanımlanmıştır.

|Kavram  |Açıklama |Daha fazla bilgi  |
|---------|---------|---------|
| İzlenen etkinlikler | Kimlik için Defender, şüpheli veya kötü amaçlı etkinlikleri algılamak için kuruluşunuzun içinden oluşturulan sinyalleri izler ve etkili bir şekilde önceliklendirmek ve yanıt vermek için her olası tehdidin geçerliliğini belirlemenize yardımcı olur.  |  [İzlenen etkinlikleri Kimlik için Microsoft Defender](/defender-for-identity/monitored-activities)       |
| Güvenlik uyarıları    | Kimlik için Defender güvenlik uyarıları, ağınızdaki algılayıcılar tarafından algılanan şüpheli etkinlikleri ve her tehditte yer alan aktörleri ve bilgisayarları açıklar.   | [güvenlik uyarılarını Kimlik için Microsoft Defender](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| Varlık profilleri    | Varlık profilleri kullanıcıların, bilgisayarların, cihazların ve kaynakların yanı sıra erişim geçmişine yönelik kapsamlı bir ayrıntılı araştırma sağlar.   | [Varlık profillerini anlama](/defender-for-identity/entity-profiles)  |
| Yanal hareket yolları    | MDI güvenlik içgörülerinin önemli bir bileşeni, bir saldırganın ağınızdaki hassas hesaplara veya makinelere erişim kazanmak için hassas olmayan hesapları kullandığı yanal hareket yollarını belirlemektir.  | [Kimlik için Microsoft Defender YanAl Hareket Yolları (LMP' ler)](/defender-for-identity/use-case-lateral-movement-path)  |
| Ağ Adı Çözümlemesi    |  Ağ Adı Çözümlemesi (NNR), ağ trafiğine, Windows olaylarına, ETW'ye vb. dayalı etkinlikleri yakalayan ve bu ham verileri her etkinlikte yer alan ilgili bilgisayarlarla ilişkilendiren MDI işlevselliğinin bir bileşenidir.       | [Ağ Adı Çözümleme nedir?](/defender-for-identity/nnr-policy)      |
| Raporlar    | Kimlik için Defender raporları, sistem ve varlık durumu bilgilerini sağlayan raporları zamanlamanıza veya hemen oluşturmanıza ve indirmenize olanak sağlar.  Ortamınızda algılanan sistem durumu, güvenlik uyarıları ve olası yanal hareket yolları hakkında raporlar oluşturabilirsiniz.   | [raporları Kimlik için Microsoft Defender](/defender-for-identity/reports)       |
| Rol grupları    | Kimlik için Defender, kuruluşunuzun Yöneticiler, Kullanıcılar ve Görüntüleyiciler dahil olmak üzere özel güvenlik ve uyumluluk gereksinimlerine göre verileri korumak için rol tabanlı gruplar ve temsilci erişimi sunar.        |  [rol gruplarını Kimlik için Microsoft Defender](/defender-for-identity/role-groups)       |
| Yönetim portalı    |  Microsoft 365 Defender portalına ek olarak, Kimlik için Defender portalı şüpheli etkinlikleri izlemek ve yanıtlamak için kullanılabilir.      | [Kimlik için Microsoft Defender portalıyla çalışma](/defender-for-identity/workspace-portal)        |
| Microsoft Defender for Cloud Apps tümleştirmesi   | Microsoft Defender for Cloud Apps, karma bir ortamda kullanıcı varlığı davranış analizi (UEBA) sağlamak için hem bulut uygulaması hem de şirket içi Kimlik için Microsoft Defender tümleştirir   | Kimlik için Microsoft Defender tümleştirmesi  |

## <a name="review-prerequisites"></a>Önkoşulları gözden geçirme

Kimlik için Defender, şirket içi kimlik ve ağ bileşenlerinizin en düşük gereksinimleri karşıladığından emin olmak için bazı önkoşul çalışmalarını gerektirir. Ortamınızın hazır olduğundan emin olmak için bu makaleyi denetim listesi olarak kullanın: [önkoşulları Kimlik için Microsoft Defender](/defender-for-identity/prerequisites).


## <a name="next-steps"></a>Sonraki adımlar

Adım 2 / 3: [Kimlik için Defender değerlendirme ortamını etkinleştirme](eval-defender-identity-enable-eval.md)

[Değerlendirme Kimlik için Microsoft Defender](eval-defender-identity-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün 
