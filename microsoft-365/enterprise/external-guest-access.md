---
title: Microsoft 365'te dış işbirliği seçeneklerine genel bakış
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- SPO_Content
ms.localizationpriority: medium
description: Kuruluşunuzun dışındaki kişilerin toplantılar, konuk paylaşımı, sohbet ve işbirliği için Microsoft 365 aboneliğinize nasıl erişebileceğini öğrenin.
ms.openlocfilehash: 988a1ecae8a060cae2334f97ef19bc90ba2be6bc
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2022
ms.locfileid: "66861443"
---
# <a name="overview-of-external-collaboration-options-in-microsoft-365"></a>Microsoft 365'te dış işbirliği seçeneklerine genel bakış

Microsoft 365 ile kullanıcılarınız kuruluşunuzun dışındaki kişilerle çeşitli yollarla işbirliği yapabilir. Kullanıcılar dosyaları paylaşabilir, konukları ekiplere davet edebilir, dış katılımcılarla toplantı yapabilir ve diğer kuruluşlardan kişilerle sohbet edebilir. Bu makale, kullanılabilir dış işbirliği seçeneklerini ve her birini yapılandırmak için ihtiyacınız olan içeriğe bağlantılar içerir.

Aşağıdaki tabloda, kuruluşunuzun dışındaki kişilerin Microsoft 365 kaynaklarınıza erişmesinin birincil yolları gösterilmektedir:

|Etkinlik|Hesap türü|Varsayılan ayar|
|:-------|:-----------|:--------------|
|Kimliği doğrulanmış dosya ve klasör paylaşımı|Konuk hesabı|Etkin|
|Site paylaşımı|Konuk hesabı|Etkin|
|Ekip paylaşımı|Konuk hesabı|Etkin|
|Teams'de paylaşılan kanal|Mevcut Microsoft 365 dış hesabı|Devre dışı|
|Dış sohbet ve toplantılar|Mevcut Microsoft 365 dış hesabı|Etkin|
|Anonim toplantıya katılma|Yok|Etkin|
|Kimliği doğrulanmamış dosya ve klasör paylaşımı|Yok|Etkin|

Kuruluşunuzdaki bir kullanıcı bu etkinliklerden birini başlatmadığı sürece kuruluşunuz dışındaki kişilerin erişimi olmaz. Kuruluşunuzda bu etkinliğe izin vermek istemiyorsanız bu ayarlardan herhangi birini devre dışı bırakabilirsiniz.

## <a name="document-site-and-team-sharing-with-guest-accounts"></a>Konuk hesaplarıyla belge, site ve ekip paylaşımı

Kuruluşunuzun dışındaki kişilerle belge, site ve ekip *paylaşımında konuk hesapları* kullanılır. Konuk hesapları, Azure Active Directory'de [Azure AD B2B işbirliğiyle](/azure/active-directory/external-identities/what-is-b2b) yönetilen bir hesap türüdür. Kuruluşunuzdaki kaynakları e-posta adresi olan herkesle paylaşmak için kullanılabilir. Konuk hesaplarını, kuruluşunuzdaki kullanıcıları yönettiğiniz gibi yönetebilirsiniz. Konuklar, işbirliği özelliklerinin çoğu için lisansa ihtiyaç duymaz. 

Konuklar yalnızca kendileriyle özel olarak paylaştığınız kaynaklara erişebilir.

Konuğun başka bir kuruluşta iş veya okul hesabı veya Microsoft hesabı varsa, normal kullanıcı adı ve parolasıyla oturum açabilir. Gmail hesabı gibi farklı bir hesap türüne sahiplerse, e-posta adreslerine gönderilen tek seferlik bir geçiş kodu kullanarak oturum açabilirler.

Konuklarla yapabilecekleri:

- Kuruluşunuzdaki kişilerle işbirliği yapabilecekleri Microsoft 365 gruplarına, ekiplerine veya SharePoint sitelerine davet edin.
- Verdiğiniz izinlere bağlı olarak görüntüleyebileceği veya düzenleyebileceği tek bir dosyayı veya klasörü onlarla paylaşın.

Microsoft 365'te konuklarla işbirliğini planlama hakkında bilgi için aşağıdaki başvurulara bakın:

- [Dış işbirliğini planlayın](/microsoft-365/solutions/plan-external-collaboration)
- [Microsoft Teams ile güvenli dosya paylaşımı ve işbirliği ayarlama](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

Konuklarla işbirliği için Microsoft 365'i ayarlama hakkında bilgi için aşağıdaki başvurulara bakın:

- [Belge üzerinde konuklarla işbirliği yapma](/microsoft-365/solutions/collaborate-on-documents)
- [Sitedeki konuklarla işbirliği yapma](/microsoft-365/solutions/collaborate-in-site)
- [Ekipteki konuklarla işbirliği yapma](/microsoft-365/solutions/collaborate-as-team)
 
## <a name="shared-channels"></a>Paylaşılan kanallar

Paylaşılan kanallar, diğer Microsoft 365 kuruluşlarındaki kişiler de dahil olmak üzere ekip dışındaki kişilerle paylaşmanızı sağlayan bir Teams kanalı türüdür. Teams'de paylaşılan kanallar varsayılan olarak açık olsa da, paylaşılan kanallarla dış işbirliği varsayılan olarak devre dışı bırakılır. Paylaşılan kanallarla dış işbirliği, konuk hesabı oluşturmaya gerek kalmadan diğer Microsoft 365 kuruluşlarından kişileri Teams kanallarına eklemenize olanak tanıyan [Azure AD B2B doğrudan bağlantı](/azure/active-directory/external-identities/b2b-direct-connect-overview) kullanır.

Paylaşılan kanallar, dış katılımcıların Teams masaüstü istemcisinde kuruluş değiştirmesini veya kuruluşunuzda oturum açmasını gerektirmemesi nedeniyle konuk hesaplarına göre belirli bir avantaja sahiptir. Kuruluşlarında oturum açmış olarak kalabilir ve kanala doğrudan erişebilirler.

Kanalları kuruluşunuzun dışındaki kişilerle paylaşmak için kuruluşunuzun ve dış kuruluşun [B2B Direct Connect'Azure AD](/azure/active-directory/external-identities/b2b-direct-connect-overview) bir kuruluş ilişkisi yapılandırması gerekir.

Paylaşılan kanallarla dış işbirliği için Microsoft 365'i ayarlama hakkında bilgi için aşağıdaki başvurulara bakın:

- [Dış işbirliğini planlayın](/microsoft-365/solutions/plan-external-collaboration)
- [Microsoft Teams'de paylaşılan kanallar](/MicrosoftTeams/shared-channels)
- [Kanaldaki dış katılımcılarla işbirliği yapma](/microsoft-365/solutions/collaborate-teams-direct-connect)

## <a name="external-chat-and-meetings"></a>Dış sohbet ve toplantılar

Kuruluşunuzdaki kullanıcılar dış Microsoft 365 kuruluşlarındaki kullanıcılarla Teams'de sohbet edebilir, toplantılara kullanıcı ekleyebilir ve sesli veya görüntülü konferans kullanabilir. Varsayılan olarak, kuruluşunuzdaki kullanıcılar diğer tüm Microsoft 365 etki alanlarıyla bu şekilde iletişim kurabilir. Diğer kuruluşlardaki kişiler, kullanıcının e-posta adresini biliyorsa, kullanıcılarınızla bu şekilde iletişim kurabilir. Özelliği devre dışı bırakmak istiyorsanız belirli etki alanlarına izin verebilir veya bunları engelleyebilir ya da tüm etki alanlarını engelleyebilirsiniz.

Ayrıca, kuruluşunuzdaki kullanıcıların kuruluşunuzun dışından, bir kuruluş tarafından yönetilmeyen Teams hesaplarını, Skype Kurumsal (çevrimiçi ve şirket içi) ve Skype kullanıcılarını kullanan kişilerle iletişim kurmasına da izin vekleyebilirsiniz.

Konuk hesapları dış sohbet ve toplantıların bir parçası olarak kullanılmaz. Dış katılımcılar kendi kuruluşlarında veya Skype'ta oturum açmış durumda kalır ve kuruluşunuzdaki kişilerle doğrudan iletişim kurabilir. Ekiplerinize veya kanallarınıza erişimi yoktur.

Dış sohbet ve toplantılar için Microsoft 365'i ayarlama hakkında bilgi için aşağıdaki başvurulara bakın:

- [Kuruluşunuzun dışındaki kişilerle işbirliği yapmak için konuk erişimini ve dış erişimi kullanma](/microsoftteams/communicate-with-users-from-other-organizations)
- [Microsoft Teams'de dış erişimi yönetin](/microsoftteams/manage-external-access).

## <a name="anonymous-meeting-join"></a>Anonim toplantıya katılma 

Kuruluşunuzun dışındaki kişiler toplantılara aşağıdaki yollarla katılabilir:

- Kuruluşunuzda bir konuk hesabıyla oturum açmışlarsa, toplantılara konuk olarak katılırlar.
- İş veya okul hesabıyla farklı bir kuruluşta oturum açtıysa ve kuruluşunuz dış erişimi etkinleştirdiyse, toplantılara dış katılımcı olarak katılır.
- Konuk veya dış katılımcı değilse, toplantılara anonim olarak katılmaları gerekir.

Anonim katılma ayarı kuruluşunuz için etkinleştirildiyse, anonim kullanıcılar yalnızca kendileriyle paylaşılan bir toplantı bağlantısını (toplantı davetindeki bağlantı gibi) kullanarak toplantıya katılabilir. Toplantıya anonim olarak katılırken seçtikleri görünen adı girmeleri istenir. Lobi ayarlarına bağlı olarak, anonim kullanıcı toplantıya otomatik olarak kabul edilebilir veya toplantı düzenleyicisinin (veya sunucu rolüne sahip toplantı katılımcılarının) toplantıya erişim izni verebileceği veya erişimi reddedebileceği bir lobiye eklenebilir. 

Toplantı öncesinde, sırasında veya sonrasında anonim kullanıcıların kimliğini doğrulamak mümkün değildir. 

Anonim kullanıcıların toplantılara katılma becerisini kuruluş düzeyinde denetleyebilirsiniz. Kuruluş için etkinleştirildiyse, toplantı düzenleyicileri toplantı ilkesi ayarları aracılığıyla anonim katılımı denetleyebilir.

Toplantılar için anonim katılımı yapılandırma hakkında bilgi için bkz. [Microsoft Teams'de toplantı ayarlarını yönetme](/microsoftteams/meeting-settings-in-teams).

## <a name="unauthenticated-file-and-folder-access"></a>Kimliği doğrulanmamış dosya ve klasör erişimi

Microsoft 365'te Teams, SharePoint ve OneDrive'daki dosya ve klasörler kimliği doğrulanmamış veya *Herkes* bağlantıları kullanılarak paylaşılabilir. Herkes bağlantısı, bağlantıya sahip olan herkese paylaşılan öğeye erişim verir. Herhangi bir bağlantı başkalarıyla paylaşılabilir ve bu kişiler dosyaya veya klasöre erişebilir.

Herkes bağlantısı kullanan kişilerin kimlik doğrulaması yapması gerekmez ve erişimleri denetlenemez. Dosya ve klasör sahipleri, bağlantıyı silerek erişimi istedikleri zaman iptal edebilir.

Teams paylaşılan kanal sitesindeki dosyalarla herkes bağlantısı kullanılamaz.

Anonim dosya ve klasör paylaşımıyla çalışma hakkında bilgi için aşağıdaki başvurulara bakın:

- [Paylaşım ayarlarını yönetme](/sharepoint/turn-external-sharing-on-or-off)
- [Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](/microsoft-365/solutions/best-practices-anonymous-sharing)

## <a name="related-topics"></a>İlgili konular

[SharePoint tarafından desteklenen Microsoft 365'te dosya işbirliğine giriş](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 ile SharePoint'te dosya işbirliği](/sharepoint/deploy-file-collaboration)

[Kuruluşunuzun dışındaki kişilerle işbirliği yapmak için konuk erişimini ve dış erişimi kullanma](/microsoftteams/communicate-with-users-from-other-organizations)

[Konuk paylaşımını belirli kuruluşlarla sınırlayın](/microsoft-365/solutions/limit-guest-sharing-to-specific-organization)

[Kullanıcıların konuk hesaplarına sahip olabileceği kuruluşları sınırlama](/microsoft-365/solutions/limit-organizations-where-users-have-guest-accounts)