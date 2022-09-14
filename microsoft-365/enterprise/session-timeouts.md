---
title: Microsoft 365 için oturum zaman aşımları
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Microsoft 365 istemci uygulamalarında güvenlik ve erişim kolaylığını dengelemek için oturum zaman aşımlarının nasıl kullanıldığını öğrenin.
ms.openlocfilehash: 910c0eaed754c7d41329741ecb24f15b9ac7364c
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67669089"
---
# <a name="session-timeouts-for-microsoft-365"></a>Microsoft 365 için oturum zaman aşımları

Oturum ömrü, Microsoft 365 kimlik doğrulamasının önemli bir parçasıdır ve güvenliğin dengelenmesinde önemli bir bileşendir ve kullanıcıların kimlik bilgilerini isteme sayısıdır.

## <a name="session-times-for-microsoft-365-services"></a>Microsoft 365 hizmetleri için oturum süreleri

Kullanıcılar Microsoft 365 web uygulamalarından veya mobil uygulamalarından herhangi birinde kimlik doğrulaması yaparken bir oturum oluşturulur. Oturum süresi boyunca kullanıcıların yeniden kimlik doğrulaması yapmalarına gerek kalmaz. Kullanıcılar etkin olmadığında, tarayıcıyı veya sekmeyi kapattıklarında veya parolalarının sıfırlanması gibi diğer nedenlerle kimlik doğrulama belirteçlerinin süresi dolduğunda oturumların süresi dolabilir. Microsoft 365 hizmetleri, her hizmetin tipik kullanımına karşılık gelen farklı oturum zaman aşımlarına sahiptir.

Aşağıdaki tabloda Microsoft 365 hizmetlerinin oturum ömrü listelenmektedir:

| Microsoft 365 hizmeti | Oturum zaman aşımı |
|:-----|:-----|
|Microsoft 365 yönetici merkezi  <br/> |Her 8 saatte bir yönetim merkezi için kimlik bilgileri sağlamanız istenir.  <br/> |
|SharePoint Online  <br/> |Kullanıcılar **Oturumumu açık tut'u** seçtiği sürece 5 günlük işlem yapılmaz. Kullanıcı, önceki oturum açmadan 24 veya daha fazla saat geçtikten sonra SharePoint Online'a yeniden erişirse, zaman aşımı değeri 5 güne sıfırlanır.  <br/> |
|Outlook Web App  <br/> |6 saat.  <br/> [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) _cmdlet'indeki ActivityBasedAuthenticationTimeoutInterval_ parametresini kullanarak bu değeri değiştirebilirsiniz.  <br/> |
|Azure Active Directory  <br/> (Modern kimlik doğrulaması etkinleştirilmiş Windows istemcilerinde Office ve Microsoft 365 uygulamaları tarafından kullanılır)  <br/> | Modern kimlik doğrulaması, Azure Active Directory kullanarak kullanıcıya Microsoft 365 kaynaklarına erişim vermek için erişim belirteçlerini ve yenileme belirteçlerini kullanır. Erişim belirteci, başarılı bir kimlik doğrulaması sonrasında sağlanan bir JSON Web Belirtecidir ve 1 saat geçerlidir. Daha uzun ömürlü bir yenileme belirteci de sağlanır. Erişim belirteçlerinin süresi dolduğunda, Office istemcileri yeni bir erişim belirteci almak için geçerli bir yenileme belirteci kullanır. Kullanıcının ilk kimlik doğrulaması hala geçerliyse bu değişim başarılı olur.  <br/>  Yenileme belirteçleri 90 gün boyunca geçerlidir ve sürekli kullanımla iptal edilene kadar geçerli olabilir.  <br/>  Yenileme belirteçleri aşağıdakiler gibi çeşitli olaylar tarafından geçersiz kılınabilir:  <br/>  Yenileme belirteci verildikten sonra kullanıcının parolası değişti.  <br/>  Yönetici, kullanıcının erişmeye çalıştığı kaynağa erişimi kısıtlayan koşullu erişim ilkeleri uygulayabilir.  <br/> |
|Android, iOS ve Windows 10 için SharePoint ve OneDrive mobil uygulamaları  <br/> |Erişim belirteci için varsayılan yaşam süresi 1 saattir. Yenileme belirtecinin varsayılan en uzun etkin olmayan süresi 90 gündür.  <br/> [Belirteçler ve belirteç yaşamlarını yapılandırma hakkında daha fazla bilgi edinin](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Yenileme belirtecini iptal etmek için kullanıcının Microsoft 365 parolasını sıfırlayabilirsiniz  <br/> |
|Microsoft 365 Sign-In ile Yammer  <br/> |Tarayıcının ömrü. Kullanıcılar tarayıcıyı kapatır ve Yammer'a yeni bir tarayıcıda erişirse, Yammer bu kullanıcıların kimliğini Microsoft 365 ile yeniden doğrular. Kullanıcılar tanımlama bilgilerini önbelleğe alan üçüncü taraf tarayıcılar kullanıyorsa, tarayıcıyı yeniden açtıklarında yeniden kimlik doğrulamasına gerek duymayabilirler.  <br/> > [!NOTE]> Bu yalnızca Yammer için Microsoft 365 Sign-In kullanan ağlar için geçerlidir.           |