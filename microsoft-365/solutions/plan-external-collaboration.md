---
title: Kanal konuşmaları, dosya işbirliği ve paylaşılan uygulamalarla dış işbirliği planlama
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- highpri
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Teams'de konuk işbirliği ile paylaşılan kanallar arasındaki farkı ve hangisinin kullanılacağını seçmeyi öğrenin.
ms.openlocfilehash: 57499660183de73356c1f2ba44243f183972d67b
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985531"
---
# <a name="plan-external-collaboration-with-channel-conversations-file-collaboration-and-shared-apps"></a>Kanal konuşmaları, dosya işbirliği ve paylaşılan uygulamalarla dış işbirliği planlama

Microsoft 365, kuruluşunuzun dışındaki kişilerle işbirliği yapmak için çeşitli seçenekler sunar:

- 1:1 ve Teams'de kuruluşunuzun dışındaki kişilerle grup sohbeti
- Kuruluşunuzun dışındaki kişilerle Teams toplantıları
- Tek tek dosyaları veya klasörleri kuruluşunuzun dışındaki kişilerle paylaşma
- Kanal konuşmaları, dosya işbirliği ve paylaşılan uygulamalarla ekipte işbirliği

Bu makalede dördüncü seçenek, kanal konuşmalarıyla grup işbirliği, dosya işbirliği ve paylaşılan uygulamalar yer alır. (Tüm seçeneklere genel bakış için bkz. [Microsoft 365'te dış işbirliği seçeneklerine genel bakış](/microsoft-365/enterprise/external-guest-access).)

## <a name="terms"></a>Terim

- **Azure AD B2B işbirliği** – Kullanıcıların kuruluşunuzun dışındaki kişilerle dosya, klasör, site, grup ve ekip paylaşmasına olanak tanıyan bir özellik. Bu kişiler, dizininizdeki konuk hesaplarını kullanarak paylaşılan kaynaklara erişer.
- **Azure AD B2B doğrudan bağlantı** – Kullanıcıların kuruluşunuzdaki kaynakları diğer Azure AD kuruluşlarından kişilerle paylaşmasına olanak tanıyan bir özellik. Bu kişiler kendi iş veya okul hesabını kullanarak paylaşılan kaynaklara erişer. Kuruluşunuzda hiçbir konuk hesabı oluşturulmaz.
- **Dış katılımcı** – Kuruluşunuzun dışından gelen ve dizininizdeki bir konuk hesabını değil kendi kimliğini kullanarak paylaşılan bir kanal gibi bir kaynağa katılan kişi.
- **Dış kuruluş** – Kaynakları paylaştığınız başka bir kuruluş.
- **Konuk** : Kuruluşunuzun dışından, dizininizdeki bir konuk hesabında oturum açarak paylaşılan kaynaklara erişen kişi.
- **Konak kuruluş** – Paylaşılan bir kaynağı barındıran kuruluş (paylaşılan kanal gibi).
- **Paylaşılan kanal** : Ekip dışındaki kişilerle paylaşılabilen bir Teams kanalı. Bu kişiler kuruluşunuzun içinde veya diğer Azure AD kuruluşlarından olabilir.
- **Paylaşım bağlantıları** – Bu dosya veya klasörü başkalarıyla paylaşmak için kullanılan bir dosya veya klasöre yönelik izinlere sahip bağlantılar. Paylaşılan kişiler kuruluşunuzun içinde veya dışında olabilir.

## <a name="options-for-collaboration-in-a-team"></a>Ekipte işbirliği seçenekleri

Kuruluşunuz dışındaki kişilerle bir ekipte işbirliği yaparken, bu kişilerin kendileriyle paylaştığınız kaynaklara nasıl eriştiğine ilişkin iki seçenek vardır.

### <a name="guest-sharing"></a>Konuk paylaşımı

Konuk paylaşımı, her bir kişi için Azure AD bir konuk hesabı ekleyerek kuruluşunuzun dışındaki kişilerle paylaşıma ve işbirliğine olanak sağlamak için Azure AD B2B işbirliğini kullanır. Konuk hesapları aşağıdakiler için kullanılabilir:

- Ekiplerde, SharePoint sitelerinde ve Microsoft 365 gruplarında konuk üyeliği
- Tek tek dosya ve klasör paylaşımı

Ekipteki konuklar, normal ekip üyelerine benzer özelliklere sahiptir.

### <a name="external-participants-in-shared-channels"></a>Paylaşılan kanallardaki dış katılımcılar

Dış katılımcılar kendi Azure AD veya Microsoft 365 kimliklerini kullanarak kuruluşunuzdaki paylaşılan kaynaklara erişebilir. Bu, B2B'nin her iki kuruluş tarafından yapılandırılmış bir kuruluş ilişkisi aracılığıyla doğrudan bağlanma Azure AD tarafından etkinleştirilir. Konuk hesapları bu ilişkide kullanılmaz.

Paylaşılan kanallardaki dış katılımcıların konuk paylaşımına kıyasla birincil avantajı, kuruluşunuzun dışındaki kişilerin kullanıcı bağlamlarını değiştirmek zorunda kalmadan Teams'de kullanıcılarınızla işbirliği yapmalarını sağlamaktır. Konuk hesaplarını kullanırken, kullanıcıların iş veya okul hesaplarıyla Teams oturumunu kapatması ve konuk hesabını kullanarak yeniden oturum açması gerekir. Alternatif olarak, özel bir tarayıcı oturumunda çalışan teams'in ayrı bir kopyasına sahip olabilirler. Kuruluşlar arasında geçiş yapmak zaman alır ve kullanıcıların belirli bir kuruluşun oturumunun kapatılması sırasında önemli iletişimleri kaçırmasına neden olabilir.

Paylaşılan kanallarla, kullanıcılar kendi kuruluşlarında oturum açmış olarak kalabilir ve diğer kuruluşlardan kendileriyle paylaşılan kanallara erişebilir. Diğer kuruluşların paylaşılan kanalları, teams ve kuruluşunuzdaki kanalların yanı sıra Teams'de de kullanılabilir. Kuruluşlar arasında geçiş yapmanıza gerek yoktur.

## <a name="feature-comparison"></a>Özellik karşılaştırması

Aşağıdaki tabloda, kullanılan hesabın türüne bağlı olarak kullanılabilir deneyimler açıklanmaktadır.

|Özellik|Kullanıcı (kuruluşunuz)|Konuk (Azure AD işbirliği)|Dış katılımcı (doğrudan bağlanma Azure AD)|
|:-----|:-----|:------|:-------|
|Ekip erişimi|E|E|N|
|Paylaşılan kanal erişimi|E|N|E|
|Dosya paylaşım bağlantıları üzerinden izinler|E|E|N|
|Paylaşılan kanalları kullanma|E|N|E|
|Özel kanalları kullanma|E|E|N|
|Dizininizdeki hesap|E|E|N|
|Erişim gözden geçirmeleri|E|E|E|

## <a name="planning-considerations"></a>Planlama konuları

Çoğu kuruluş hem konuk paylaşımını hem de dış katılımcılarla paylaşılan kanalları kullanır.

Konuk paylaşımı, Azure AD ve Microsoft 365'te (Teams, Microsoft 365 Grupları ve SharePoint) varsayılan olarak etkindir. Bu, kullanıcıların BT'den yardım istemek zorunda kalmadan konukları ekiplere ve sitelere davet etmesine ve onlarla dosya paylaşmasına olanak tanır.

Aşağıdakiler durumunda konuk paylaşımını kullanmanız gerekir:

- Tek tek kanallar yerine kuruluşunuzun dışından kişileri ekise davet etmek istiyorsunuz
- Kanaldaki dosya veya klasörleri, kuruluşunuzun dışındaki ve kanalda olmayan kişilerle paylaşmak istiyorsunuz
- Kuruluşunuzun dışındaki iş veya okul hesabı olmayan kişilerle işbirliği yapmak istiyorsunuz.

Paylaşılan kanallar Teams'de varsayılan olarak açık olsa da, paylaşılan kanallarla dış işbirliği için Azure AD yöneticisinin kuruluşunuzla paylaşmak istediğiniz diğer kuruluşlar arasında kiracılar arası erişim ayarlaması gerekir. Diğer kuruluşlar da kendi uçlarında kiracılar arası erişim ayarlamalıdır.

Paylaşılan kanalları diğer kuruluşlarla kullanmayı planlıyorsanız, self servis modeliyle isteğe göre model arasında seçim yapabilirsiniz.

- Self servis – Diğer tüm Azure AD kuruluşlara gelen ve giden erişime izin vermek için kiracılar arası erişimi yapılandırabilirsiniz. Alternatif olarak, kullanıcılarınızın paylaşmasını istemediğiniz kuruluşların listesini engelleyebilir ve diğer tüm kuruluşları kullanabilirsiniz. Bu, kullanıcılarınızın yardım masanıza veya BT departmanınıza başvurmak zorunda kalmadan kuruluş dışındaki kişileri paylaşılan kanallara katılmaya davet etmesine olanak tanır.
- İsteğe göre : Paylaşılan kanallara izin vermek istediğiniz her bir kuruluş için kiracılar arası erişimi yapılandırabilirsiniz. Bu modeli seçerken, kullanıcılarınızın başka bir kuruluşla kiracılar arası erişim istemek için izleyebilecekleri belgelenmiş bir iş sürecine sahip olmak önemlidir.

## <a name="compliance-in-shared-channels"></a>Paylaşılan kanallarda uyumluluk

Paylaşılan kanallar Microsoft Purview özellikleriyle tümleşiktir.

### <a name="communications-compliance"></a>İletişim uyumluluğu

Yöneticiler kanaldaki tüm kullanıcıların içeriğini izlemek için ilkeler ayarlayabilir. Paylaşılan kanallar dahil olmak üzere kanallardaki tüm ileti içeriği [iletişim uyumluluk ilkeleri](/microsoft-365/compliance/communication-compliance) kapsamındadır. Paylaşılan kanallar, konak kuruluşun ilkesini devralır.

### <a name="conditional-access"></a>Koşullu erişim

Konak kuruluştan desteklenen [koşullu erişim ilkeleri](/azure/active-directory/conditional-access/overview) B2B doğrudan bağlantı kullanıcılarına uygulanabilir. (Dış kuruluşun ilkeleri kullanılmaz.) Aşağıdaki koşullu erişim ilkesi türleri paylaşılan kanallarda desteklenir:

- **Kapsamı Tüm konuk ve dış kullanıcılar ve** **Office 365 SharePoint Online** bulut uygulaması olan ilkeler.
- MFA, uyumlu bir cihaz veya karma Azure AD katılmış cihaz gerektiren Erişim denetimleri verin.

IP tabanlı ilkeler SharePoint dosya düzeyinde desteklenir. Bu nedenle, dış katılımcı paylaşılan kanala kısıtlı bir konumdan erişebilir, ancak bir dosyayı açmaya çalışırken engellenebilir.

Dış kimlikler için koşullu erişim hakkında daha fazla bilgi için bkz. [Dış Kimlikler için Kimlik Doğrulaması ve Koşullu Erişim](/azure/active-directory/external-identities/authentication-conditional-access).

### <a name="data-loss-prevention-dlp"></a>Veri kaybı önleme (DLP)

Yöneticiler [Microsoft Purview DLP ilkelerini](/microsoft-365/compliance/dlp-policy-design) , paylaşılan kanallar da dahil olmak üzere tüm kanalların ilkeyi devraldığı bir takıma uygulayabilir. Paylaşılan kanallar, konak kuruluşun ilkesini devralır.

### <a name="retention-policy"></a>Bekletme ilkesi

Yöneticiler, paylaşılan kanallar da dahil olmak üzere tüm kanalların [bekletme ilkesini](/microsoft-365/compliance/retention) devraldığı bir takıma bekletme ilkesi uygulayabilir. Paylaşılan kanallar üst ekibin ilkesini devralır.

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri

Paylaşılan kanal sitesindeki belgelere uygulanabilecek tek etiketler konak kuruluşta bulunan [duyarlılık etiketleridir](/microsoft-365/compliance/sensitivity-labels). Duyarlılık etiketiyle şifrelenen bir dosya, izinler verilmediği sürece dış katılımcılar tarafından açılamaz. Otomatik etiketleme kullanılmaz.

Paylaşılan kanallar ve ilişkili SharePoint siteleri etiketi üst ekipten devralır.

### <a name="information-barriers"></a>Bilgi engelleri

[Bilgi engeli](/microsoftteams/information-barriers-in-teams) ilkelerine göre iletişim kurmasına izin verilmeyen kullanıcılar paylaşılan kanalın parçası olamaz. Bilgi engeli ilkeleri yalnızca konak kuruluştaki kullanıcılar için geçerlidir. Kullanıcılar başka bir kuruluşun paylaşılan kanalında dış katılımcılarsa, bilgi engeli ilkeleri uygulanmaz.

### <a name="ediscovery"></a>Ediscovery

Yöneticiler kanaldaki tüm kullanıcılar için arama yapabilir. Paylaşılan kanal da dahil olmak üzere tüm kanallar bulunabilir. Verileri kim eklemiş olursa olsun kanaldaki tüm ileti verileri uyumluluk yöneticisi tarafından bulunabilir.

### <a name="legal-hold"></a>Yasal tutma

Yöneticiler, konak kuruluşundan ekibin bir parçası olmayan yalnızca kanal üyelerini beklemeye alabilir. Ayrıca [ekibin tamamını beklemeye](/MicrosoftTeams/legal-hold) alabilirler. Yöneticiler dış katılımcıyı beklemeye alamaz.

### <a name="audit-logs"></a>Denetim günlükleri

[Mevcut denetim olayları](/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) için gerçekleştirilen tüm eylemler paylaşılan kanallarda denetlenmektedir.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365'te dosya işbirliğine giriş](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 ile SharePoint'te dosya işbirliğini planlama](/sharepoint/deploy-file-collaboration)
