---
title: Adım 3. Kimlikleri koruyun
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, insan tarafından çalıştırılan fidye yazılımı, HumOR, gasp saldırısı, fidye yazılımı saldırısı, şifreleme, kriptoviroloji, sıfır güven
description: Microsoft 365 kaynaklarınızı fidye yazılımı saldırılarına karşı korumak için güvenli oturum açma işlemlerini ve Koşullu Erişim'i kullanın.
ms.openlocfilehash: 33559370794de182addee0ea40ccadfe0cca0bf0
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985487"
---
# <a name="step-3-protect-identities"></a>Adım 3. Kimlikleri koruyun

Kuruluşunuzu genellikle daha büyük bir fidye yazılımı saldırısının ilk aşaması olan kimlik bilgileri güvenliğinin aşılmasına karşı korumak için aşağıdaki bölümleri kullanın.

## <a name="increase-sign-in-security"></a>Oturum açma güvenliğini artırın

Azure Active Directory'deki (Azure AD) kullanıcı hesapları için [parolasız kimlik doğrulamasını](/azure/active-directory/authentication/howto-authentication-passwordless-deployment) kullanın.

Parolasız kimlik doğrulamasına geçiş sırasında, parola kimlik doğrulamasını kullanmaya devam eden kullanıcı hesapları için şu en iyi yöntemleri kullanın:

- [Azure AD Parola Koruması](/azure/active-directory/authentication/concept-password-ban-bad) ile bilinen zayıf ve özel parolaları engelleyin.
- Azure AD Parola Koruması ile bilinen zayıf ve özel parolaların engellenmesini [şirket içi Active Directory Etki Alanı Hizmetlerinize (AD DS)](/azure/active-directory/authentication/concept-password-ban-bad-on-premises) genişletin.
- [Self Servis Parola Sıfırlama (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks) ile kullanıcılarınızın kendi parolalarını değiştirmesine izin verin.

Ardından [, Ortak kimlik ve cihaz erişim ilkelerini](/microsoft-365/security/office-365-security/identity-access-policies) uygulayın. Bu ilkeler, Microsoft 365 bulut hizmetlerine erişim için daha yüksek güvenlik sağlar. 

Kullanıcı oturum açma işlemleri için bu ilkeler şunlardır:

- [Öncelikli hesaplar](/microsoft-365/admin/setup/priority-accounts) (hemen) ve sonunda tüm kullanıcı hesapları için çok faktörlü kimlik doğrulaması (MFA) gerektirme.
- MFA kullanmak için yüksek riskli oturum açma işlemleri gerektirme.
- Yüksek riskli oturum açma işlemleri olan yüksek riskli kullanıcıların parolalarını değiştirmesini zorunlu kıl.

## <a name="prevent-privilege-escalation"></a>Ayrıcalık yükseltmesini önleme

Şu en iyi yöntemleri kullanın:

- [En az ayrıcalık](/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models) ilkesini uygulayın ve oturum açma işlemleri için parola kullanmaya devam eden kullanıcı hesapları için [oturum açma güvenliğini artırma](#increase-sign-in-security) bölümünde açıklandığı gibi parola koruması kullanın. 
- Etki alanı genelinde, yönetici düzeyinde hizmet hesaplarını kullanmaktan kaçının. 
- Uzaktan Erişim Truva Atları (RAT) ve diğer istenmeyen uygulamaların yüklenmesini sınırlandırmak için yerel yönetim ayrıcalıklarını kısıtlayın.
- Yönetim portallarına erişime izin vermeden önce kullanıcıların ve iş istasyonlarının güvenini açıkça doğrulamak için Azure AD Koşullu Erişim'i kullanın. Azure portal için [bu örne](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management) bakın.
- Yerel Yönetici parola yönetimini etkinleştirin.
- Yüksek ayrıcalıklı hesapların nerede oturum açıp kimlik bilgilerini açığa çıkarttığını belirleyin. İş istasyonlarında yüksek ayrıcalıklı hesaplar bulunmamalıdır.
- Parolaların ve kimlik bilgilerinin yerel depolamasını devre dışı bırakın.

## <a name="impact-on-users-and-change-management"></a>Kullanıcılar ve değişiklik yönetimi üzerindeki etkisi

Kuruluşunuzdaki kullanıcıları aşağıdakilerden haberdar etmeniz gerekir:

- Daha güçlü parolalar için yeni gereksinimler.
- MFA'nın gerekli kullanımı ve MFA ikincil kimlik doğrulama yöntemi kaydı gibi oturum açma işlemlerindeki değişiklikler.
- SSPR ile parola bakımı kullanımı. Örneğin, parola sıfırlama için yardım masasına başka çağrı yapılmaz.
- Riskli olduğu belirlenen oturum açma işlemleri için MFA veya parola değişikliği gerektirme istemi.

## <a name="resulting-configuration"></a>Sonuçta elde edilen yapılandırma

1-3 arası adımlar için kiracınız için fidye yazılımı koruması aşağıdadır.

![3. Adımdan sonra Microsoft 365 kiracınız için fidye yazılımı koruması](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step3.png)

## <a name="next-step"></a>Sonraki adım

[![Microsoft 365 ile fidye yazılımı koruması için 4. Adım](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step4.png)](ransomware-protection-microsoft-365-devices.md)

Microsoft 365 kiracınızdaki cihazları (uç noktaları) korumak için [4. Adımla](ransomware-protection-microsoft-365-devices.md) devam edin. 
