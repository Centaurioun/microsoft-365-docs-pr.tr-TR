---
title: Microsoft 365 için sürekli erişim değerlendirmesi - Kuruluş için Microsoft 365
description: Microsoft 365 ve Azure AD için koşullu erişim değerlendirmesinin etkin kullanıcı oturumlarını proaktif olarak nasıl sonlandırdığı ve kiracı ilkesi değişikliklerini neredeyse gerçek zamanlı olarak nasıl zorunlu kıldığı açıklanır.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.service: microsoft-365-security
ms.topic: conceptual
audience: Admin
f1.keywords:
- NOCSH
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- m365solution-identitydevice
- m365solution-scenario
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: a3f531aa8782878b69a5c61a763c01e974e0e069
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68624939"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>Microsoft 365 için sürekli erişim değerlendirmesi

Kimlik doğrulaması için OAuth 2.0 kullanan modern bulut hizmetleri, kullanıcı hesabının erişimini iptal etmek için geleneksel olarak erişim belirteci süre sonunu kullanır. Uygulamada bu, yönetici bir kullanıcı hesabının erişimini iptal etse bile erişim belirtecinin süresi dolana kadar erişime devam edeceği anlamına gelir. Bu, varsayılan olarak Microsoft 365 için ilk iptal olayından bir saat sonrasına kadar kullanılmıştır.

Microsoft 365 ve Azure Active Directory (Azure AD) için koşullu erişim değerlendirmesi, etkin kullanıcı oturumlarını proaktif olarak sonlandırır ve erişim belirteci süre sonu yerine kiracı ilkesi değişikliklerini neredeyse gerçek zamanlı olarak zorunlu tutar. Azure AD, kullanıcı hesabı veya kiracı, kullanıcı hesabının kimlik doğrulama durumunun yeniden değerlendirilmesini gerektirecek şekilde değiştiğinde sürekli erişim değerlendirmesi etkinleştirilmiş Microsoft 365 hizmetlerini (SharePoint, Teams ve Exchange gibi) bildirir.

Outlook gibi sürekli erişim değerlendirmesi etkinleştirilmiş bir istemci var olan bir erişim belirteci ile Exchange'e erişmeye çalıştığında, belirteç hizmet tarafından reddedilir ve yeni bir Azure AD kimlik doğrulaması istenir. Sonuç, kullanıcı hesabı ve ilke değişikliklerinin neredeyse gerçek zamanlı olarak uygulanmasıdır.

Bazı ek avantajlar şunlardır:

- Kuruluşunuzun dışında geçerli bir erişim belirtecini kopyalayıp dışarı aktaran kötü niyetli bir insider için, sürekli erişim değerlendirmesi Azure AD IP adresi konumu ilkesi aracılığıyla bu belirtecin kullanımını engeller. Sürekli erişim değerlendirmesiyle Azure AD ilkeleri desteklenen Microsoft 365 hizmetleriyle eşitler, böylece erişim belirteci ilkedeki IP adresi aralığının dışından hizmete erişmeye çalıştığında hizmet belirteci reddeder.

- Sürekli erişim değerlendirmesi, daha az belirteç yenilemesi gerektirerek dayanıklılığı artırır. Destek hizmetleri yeniden kimlik doğrulaması gerektirme hakkında proaktif bildirimler aldığından, Azure AD örneğin bir saatten uzun süreli belirteçler verebilir. Daha uzun süreli belirteçlerle, istemcilerin Azure AD sık sık belirteç yenilemesi istemesi gerekmez, bu nedenle kullanıcı deneyimi daha dayanıklıdır.

Aşağıda, sürekli erişim değerlendirmesinin kullanıcı erişim denetimi güvenliğini geliştirdiği durumlara bazı örnekler verilmiştir:

- Bir kullanıcı hesabının parolası tehlikeye atıldığı için yönetici tüm mevcut oturumları geçersiz kılıp parolasını Microsoft 365 yönetim merkezi sıfırlar. Neredeyse gerçek zamanlı olarak, Microsoft 365 hizmetleriyle var olan tüm kullanıcı oturumları geçersiz kılındı.

- Word'de bir belge üzerinde çalışan bir kullanıcı, tabletini yönetici tanımlı ve onaylı bir IP adresi aralığında olmayan genel bir kafeye götürür. Kahve dükkanında kullanıcının belgeye erişimi hemen engellenir.

Microsoft 365 için sürekli erişim değerlendirmesi şu anda aşağıdakiler tarafından desteklenmektedir:

- Exchange, SharePoint ve Teams hizmetleri.
- Web tarayıcısında ve Win32, iOS, Android ve Mac istemcileri için Outlook, Teams, Office ve OneDrive.

Microsoft, sürekli erişim değerlendirmesini desteklemek için ek Microsoft 365 hizmetleri ve istemcileri üzerinde çalışmaktadır.

Sürekli erişim değerlendirmesi, Office 365 ve Microsoft 365'in tüm sürümlerine dahil edilecek. Koşullu Erişim ilkelerinin yapılandırılması, tüm Microsoft 365 sürümlerinde yer alan Azure AD Premium P1 gerektirir.

> [!NOTE]
> Sürekli erişim değerlendirmesinin sınırlamaları için [bu makaleye](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) bakın.

## <a name="scenarios-supported-by-microsoft-365"></a>Microsoft 365 tarafından desteklenen senaryolar

Sürekli erişim değerlendirmesi iki tür olayı destekler:

- Kritik olaylar, kullanıcının erişimini kaybetmesi gereken olaylardır.
- Koşullu Erişim ilkesi değerlendirmesi, bir kullanıcının yönetici tanımlı bir ilkeye göre kaynağa erişimini kaybetmesi gerektiğinde gerçekleşir.

Kritik olaylar şunlardır:

- Kullanıcı hesabı devre dışı bırakıldı
- Parola değiştirildi
- Kullanıcı oturumları iptal edilir
- Kullanıcı için çok faktörlü kimlik doğrulaması etkinleştirildi
- [Azure AD Kimlik Koruması'ndan](/azure/active-directory/identity-protection/overview-identity-protection) erişimin değerlendirilmesine bağlı olarak hesap riski artırıldı

Koşullu Erişim ilkesi değerlendirmesi, kullanıcı hesabı artık güvenilir bir ağdan bağlanmadığında gerçekleşir.

Aşağıdaki Microsoft 365 hizmetleri şu anda Azure AD olayları dinleyerek sürekli erişim değerlendirmesini destekler.

|Zorlama türü|Exchange|SharePoint|Teams|
|---|---|---|---|
|**Kritik olaylar:**||||
|Kullanıcı iptali|Destekleniyor|Destekleniyor|Destekleniyor|
|Kullanıcı riski|Destekleniyor|Desteklenmiyor|Destekleniyor|
|**Koşullu Erişim ilkesi değerlendirmesi:**||||
|IP adresi konum ilkesi|Destekleniyor|Desteklenen\*|Desteklenen\**|

\* SharePoint Office web tarayıcısı erişimi, katı modu etkinleştirerek anında IP ilkesi zorlamayı destekler. Katı mod olmadan erişim belirteci ömrü bir saattir.

\** Teams'deki aramalar, toplantılar ve sohbetler IP tabanlı Koşullu Erişim ilkelerine uymaz.

Koşullu Erişim ilkesi ayarlama hakkında daha fazla bilgi için [bu makaleye](/azure/active-directory/conditional-access/overview) bakın.

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Sürekli erişim değerlendirmesini destekleyen Microsoft 365 istemcileri

Microsoft 365 için sürekli erişim değerlendirme özellikli istemciler, önbelleğe alınmış bir kullanıcı belirteci sürekli erişim değerlendirmesi etkinleştirilmiş bir Microsoft 365 hizmeti tarafından reddedildiğinde kullanıcı oturumunun yeniden kimlik doğrulaması için Azure AD yönlendirmesi olan talep sınamasını destekler.

Aşağıdaki istemciler web, Win32, iOS, Android ve Mac'te sürekli erişim değerlendirmesini destekler:

- Outlook
- Teams
- Office\*
- SharePoint
- OneDrive

\* Talep sınaması Web için Office'te desteklenmez.

Sürekli erişim değerlendirmesini desteklemeyen istemciler için Microsoft 365'e erişim belirteci ömrü varsayılan olarak bir saat olarak kalır.

## <a name="see-also"></a>Ayrıca bkz.

- [Sürekli erişim değerlendirmesi](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [Koşullu Erişim belgeleri](/azure/active-directory/conditional-access/overview)
- [Azure AD Kimlik Koruması belgeleri](/azure/active-directory/identity-protection/overview-identity-protection)
