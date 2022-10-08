---
title: Kuruluşunuzun dışındaki kişilerle işbirliği
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Teams, OneDrive ve SharePoint gibi Microsoft 365 uygulamalarını kuruluşunuz dışındaki kişilerle işbirliği için yapılandırmayı öğrenin.
ms.openlocfilehash: 98ebf62386b948b97c888db23ae887635404ca6c
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67987312"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişilerle işbirliği

Microsoft 365'teki dış paylaşım özellikleri, kuruluşunuzdaki kişilerin dizininizde hesabı olmayan iş ortakları, satıcılar, müşteriler ve diğer kişilerle işbirliği yapma fırsatı sunar. Ekiplerin, kanalların veya sitelerin tamamını kuruluşunuzun dışındaki kişilerle veya yalnızca tek tek dosyalarla paylaşabilirsiniz.

Kuruluşunuzun dışındaki kişilerle işbirliği yapmak şu önemli bileşenlerden oluşur:

- **Paylaşımı etkinleştirme** - Kuruluşunuz için istediğiniz paylaşım düzeyine izin vermek için Azure Active Directory, Teams, Microsoft 365 Grupları ve SharePoint'te paylaşım denetimlerini yapılandırın.
- **Kuruluş ilişkilerini yapılandırma** - Paylaşılan kanallar kullanıyorsanız, işbirliği yapmak istediğiniz her kuruluş için B2B doğrudan bağlantı erişimine izin vermek için Azure Active Directory'de kiracılar arası erişim ayarlarını yapılandırmanız gerekir. (Bu kuruluşların kiracınızla kuruluş ilişkilerini de yapılandırmaları gerekir.)
- **Ek güvenliği etkinleştirme** - Temel paylaşım özellikleri kuruluşunuz dışındaki kişilerin kimlik doğrulaması yapmasını gerektirecek şekilde yapılandırılabilir ancak Microsoft 365, verilerinizi korumanıza ve dış paylaşım yaparken idare ilkelerinizi korumanıza yardımcı olacak birçok ek güvenlik ve uyumluluk özelliği sağlar.

Genel [Microsoft 365 işbirliği kılavuzuyla](/microsoft-365/solutions/setup-secure-collaboration-with-teams) dış paylaşımın nasıl bağlantılı olduğunu öğrenmek için Microsoft 365 ve Microsoft Teams ile güvenli işbirliği ayarlama makalesini okuyun.

## <a name="enable-sharing"></a>Paylaşımı etkinleştirme

Varsayılan olarak, konuk erişimi veya anonim erişim kullanarak kuruluşunuzun dışındaki kişilerle paylaşım etkinleştirilir, ancak paylaşılan kanalların Azure AD kuruluş ilişkileri yapılandırılarak etkinleştirilmesi gerekir. Konuk paylaşım senaryolarının çoğu daha fazla yapılandırma olmadan çalışır. Kullandığınız bir senaryonun ayarlarını onaylamak veya yeni bir senaryoyu etkinleştirmek için aşağıdaki seçeneklerden birini seçin:

- [Belgeler üzerinde işbirliği yapma](collaborate-on-documents.md) - Microsoft 365'i kuruluşunuz dışındaki kişilerle (hem konuklar hem de kimliği doğrulanmamış kullanıcılar) dosya ve klasörler üzerinde paylaşmaya ve işbirliğine izin verecek şekilde yapılandırmayı öğrenin.
- [Sitede işbirliği yapma](collaborate-in-site.md) - SharePoint sitelerini konuklarla paylaşmayı etkinleştirmek için Microsoft 365'i yapılandırmayı öğrenin.
- [Ekip olarak işbirliği yapma](collaborate-as-team.md) - Teams'de konuk işbirliğini etkinleştirmek için Microsoft 365'i yapılandırmayı öğrenin.
- Paylaşılan bir kanalda kuruluş dışındaki kişilerle işbirliği yapmak için [kanaldaki dış katılımcılarla işbirliği](/microsoft-365/solutions/collaborate-teams-direct-connect) yapın.

Microsoft 365'te kullanılabilen konuk paylaşım ayarlarına kapsamlı bir bakış için bkz. [Microsoft 365 konuk paylaşım ayarları başvurusu](microsoft-365-guest-settings.md).

## <a name="enable-additional-security"></a>Ek güvenliği etkinleştirme

Kuruluşunuzun dışındaki kişilerle paylaşmak için kullanmak istediğiniz senaryoyu etkinleştirdikten sonra, içeriğinizi yanlışlıkla veya kasıtlı olarak uygunsuz paylaşımlara karşı korumaya yardımcı olacak ek korumaları göz önünde bulundurun.

- [Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](best-practices-anonymous-sharing.md) - Kimliği doğrulanmamış kullanıcılarla paylaşmaya yönelik en iyi yöntemler hakkında bilgi edinin.
- [Yanlışlıkla açığa çıkma olasılığını sınırlama](share-limit-accidental-exposure.md) - Hassas içerikleri kuruluşunuzun dışındaki kişilerle yanlışlıkla paylaşma olasılığını nasıl azaltacağınızı öğrenin.
- [Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md) - Kuruluşunuz dışındaki kişilerle paylaşımın güvenli ve güvenli bir şekilde yapıldığından ve idare gereksinimlerinizi karşıladığından emin olmak için Microsoft 365'te sağlanan araçlar hakkında bilgi edinin.

## <a name="collaborate-with-partner-companies"></a>İş ortağı şirketlerle işbirliği yapma

Başka bir kuruluştan gelen konukları içeren büyük bir proje üzerinde çalışırken paylaşılan kanalları göz önünde bulundurun. Paylaşılan kanallar konuk hesaplarını kullanmadığından, diğer kuruluştaki kullanıcılar kuruluşunuzda ayrı olarak oturum açmak zorunda kalmadan paylaşılan kanala doğrudan erişebilir.

Konukların sıklıkla değiştiği sürekli bir satıcı ilişkiniz varsa, konuk yönetimini basitleştirmek ve iş ortağı şirketin bu sorumluluğu paylaşmasına izin vermek için Azure Active Directory'de yetkilendirme yönetimini kullanabilirsiniz. Ayrıntılar için bkz. [Yönetilen konuklarla B2B extranet oluşturma](b2b-extranet.md) .

## <a name="limit-sharing"></a>Paylaşımı sınırlayın

Microsoft 365'teki paylaşım özelliklerinden bazıları idare ilkelerinizle çakışıyorsa, paylaşımı sınırlama seçenekleri hakkında bilgi edinmek için [bkz. Microsoft 365'te](microsoft-365-limit-sharing.md) paylaşımı sınırlama.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365'te dosya işbirliğine giriş](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 ile SharePoint'te dosya işbirliğini planlama](/sharepoint/deploy-file-collaboration)
