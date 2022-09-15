---
title: Kuruluş için Microsoft 365 kiracı yönetimi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Microsoft 365 kiracılarınızın planlama, dağıtım ve sürekli çalışmasına genel bakış.
ms.openlocfilehash: 11f0e0306788a48eaa67796030972727969692d8
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730605"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Kuruluş için Microsoft 365 kiracı yönetimi

Bulut bilgi işlemle kuruluşunuzun dijital dönüşümüne yönelik bir yol oluşturmak için çalışanlarınızın üretkenlik, işbirliği, performans, gizlilik, uyumluluk ve güvenlik için güvenebileceği sağlam bir temel gerekir.

Microsoft 365 kiracılarınızın doğru yapılandırılması bu temeli sağlar ve çalışanlarınızın işlerini yapmaya ve BT departmanınızın ek iş değeri sağlayan uçtan uca çözümlere odaklanmasına olanak tanır.

Bu çözüm, aşağıdaki adımlarda bu temelin yapılandırmasında size yol göstermektedir:

1. Kiracılarınızı belirleme
2. Ağınızı iyileştirme
3. Kimliklerinizi eşitleme ve güvenli oturum açma işlemleri uygulama
4. Windows cihazlarınızı, Office istemcilerinizi ve şirket içi Office sunucularınızı ve verilerinizi geçirme
5. Cihaz ve uygulama yönetimini dağıtma

Ancak öncelikle kiracının ne olduğunu ve sağlam bir temel sağlayan bir kiracının nasıl göründüğünü anlamak için biraz zaman ayıralım.

## <a name="a-microsoft-365-tenant-defined"></a>Microsoft 365 kiracısı tanımlı

Microsoft 365 kiracısı, Microsoft 365 hizmetlerinin ve Avrupa veya Kuzey Amerika gibi belirli bir varsayılan konumda depolanan kuruluş verilerinizin ayrılmış bir örneğidir. Bu konum, kuruluşunuz için kiracı oluşturduğunuzda belirtilir. Her Microsoft 365 kiracısı ayrı, benzersiz ve diğer tüm Microsoft 365 kiracılarından ayrıdır. Microsoft'tan Microsoft 365 E3 veya E5 gibi bir veya daha fazla ürün ve her biri için bir lisans kümesi satın aldığınızda bir Microsoft 365 kiracısı oluşturursunuz.

Microsoft 365 kiracınız ayrıca kullanıcı hesapları, gruplar ve diğer nesneler için ayrılmış bir Azure AD örneği olan bir Azure Active Directory (Azure AD) kiracısı içerir. Her Azure AD kiracı ayrı, benzersiz ve diğer tüm Azure AD kiracılardan ayrıdır. Kuruluşunuzun Azure abonelikleriyle ayarlayabileceğiniz birden çok Azure AD kiracısı olsa da, Microsoft 365 kiracıları yalnızca kiracıyı oluşturduğunuzda oluşturulan tek bir Azure AD kiracısını kullanabilir.

Aşağıda bir örnek verilmiştir:

![Azure AD kiracısı olan örnek bir Microsoft 365 kiracısı.](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Kiracı yönetimi* , Microsoft 365 kiracılarınızın planlama, dağıtım ve devam eden işlemidir.

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>İyi tasarlanmış ve çalışan bir kiracının öznitelikleri

Kiracınız için doğru adın ve konumun ötesinde, Microsoft Teams gibi bulut üretkenlik uygulamalarıyla&mdash;kullanıcı deneyimlerinizin etkili, güvenli ve performanslı olmasını sağlamak için planlamanız, dağıtmanız ve yönetmeniz Exchange Online gereken&mdash; ek öğeler vardır.

Öğeler şunlardır:

- Doğru ürün (abonelik) ve lisans kümesine sahipsiniz.
  - Ürün kümesi işletmenize, BT'ye ve güvenlik gereksinimlerinize uygun.
  - Çalışanlarınız için yeterli sayıda lisans ve personelde beklenen değişiklikler vardır.
- Ağ için:
  - Doğru DNS etki alanı adlarını yapılandırmışsınız.
  - Kurumsal ağlar için, şirket içi çalışanlar için Microsoft ağına yönelik ağ trafiğini iyileştirdiniz.
  - VPN istemcisi kullanan uzak çalışanlar için ağ trafiğini iyileştirdiniz.
- Active Directory Domain Services (AD DS) hesaplarınızı, gruplarınızı ve diğer nesneleri eşitlediniz.
  - Azure AD kiracı hesaplarınız, e-posta adresleri için doğru DNS etki alanlarına sahip Exchange Online posta kutularıyla eşlenir.
  - Kullanıcı hesaplarınıza doğru satın alınan ürünlerden (Microsoft 365 E3 veya E5 gibi) doğru lisanslar atanmıştır.
- Güçlü kimlik ve erişim yönetimi yapılandırmışsınız.
  - Parolasız veya çok faktörlü kimlik doğrulaması (MFA) ile güvenli kullanıcı oturum açması istiyorsunuz.
  - Daha yüksek güvenlik düzeyleri için oturum açma gereksinimlerini ve kısıtlamalarını zorunlu kılan Koşullu Erişim ilkeleriniz vardır.
- Şirket içi Office sunucuları ve verileri bulut uygulamalarına geçirilmiş veya karma bir yapılandırmada kullanılıyor.
- Microsoft 365'e yerleşik Intune veya Temel Mobilite ve Güvenlik ile cihaz yönetimi yapıyorsunuz.
  - Kuruluşunuza ait cihazlar kaydedilir ve yönetilir.
  - Kişisel cihazlar için uygulamalar yönetilir.

Burada, tüm bu öğelerin olduğu bir Microsoft 365 kiracısı örneği verilmiştir.

![Örnek bir Microsoft 365 kiracısı.](../media/tenant-management-overview/tenant-management-tenant-config.png)

Bu çizimde, Microsoft 365 kiracısı şunları içerir:

- Microsoft 365 E3 ve E5 için ürünler ve lisanslar.
- Microsoft 365 üretkenlik uygulamaları.
- Kayıtlı cihazlar ve cihaz ve uygulama ilkeleriyle Intune.
- Eşitlenmiş kullanıcı hesabı (gruplar ve diğer dizin nesneleri gösterilmez), etki alanları ve Koşullu Erişim ilkelerine sahip bir Azure AD kiracısı.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Kuruluş için Microsoft 365 kiracı özellikleri

Aşağıdaki bölümlerde ve tabloda, bu çözümdeki adımlar için temel özellikler ve lisanslama listelenir.

### <a name="tenant"></a>Kiracı

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|Birden çok kiracı|Her Microsoft 365 kiracısı ayrı, benzersiz ve diğer tüm Microsoft 365 kiracılarından ayrıdır. Birden çok kiracıda, bunları yönetirken ve kullanıcılarınıza hizmet sağlarken kısıtlamalar ve dikkat edilmesi gereken ek noktalar vardır.|Microsoft 365 E3 veya E5|
|Kiracılar arası posta kutusu geçişi|Kiracı yöneticileri, şirket içi sistemlerinde en az altyapı bağımlılığı olan kiracılar arasında posta kutularını taşıyabilir. Bu, posta kutularının kullanıma dışı ve ekleme gereksinimini ortadan kaldırır.|Microsoft 365 E3 veya E5|
|Multi-Geo|Kiracınız bekleyen verileri, veri yerleşimi gereksinimlerini karşılamak için seçtiğiniz diğer veri merkezi coğrafi konumlarında depolayabilir.|Microsoft 365 E3 veya E5|
|Temel verileri yeni bir veri merkezi coğrafi konumuna taşıma|Microsoft ek kapasite ve işlem kaynakları için yeni veri merkezi coğrafi alanları ekledikten sonra, temel müşteri verileriniz için coğrafi veri yerleşimi için veri merkezi coğrafi taşıma isteğinde bulunabilirsiniz.|Microsoft 365 E3 veya E5|
||||

### <a name="networking"></a>Ağ

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|Ağ İçgörüleri|Microsoft 365 kiracınızdan toplanan ağ performansı ölçümleri, ofis konumlarınız için ağ çevreleri tasarlamanıza yardımcı olur.|Microsoft 365 E3 veya E5|
|Uç nokta güncelleştirmelerini otomatikleştirme|İstemci PAC dosyalarınızda ve ağ cihazlarınızda ve hizmetlerinizde Microsoft 365 uç noktaları için yapılandırmayı ve devam eden güncelleştirmeleri otomatikleştirin.|Microsoft 365 E3 veya E5|
||||

### <a name="identity"></a>Kimlik

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|şirket içi Active Directory Domain Services'i (AD DS) Azure AD kiracınızla eşitleme|Kullanıcı hesapları, gruplar ve diğer nesneler için şirket içi kimlik sağlayıcınızdan yararlanın.|Microsoft 365 E3 veya E5|
|Güvenlik varsayılanlarıyla zorunlu kılınan MFA|Oturum açma işlemleri için ikinci bir kimlik doğrulaması biçimi gerektirerek güvenliği aşılmış kimliklere ve cihazlara karşı koruma sağlayın. Güvenlik varsayılanları tüm kullanıcı hesapları için MFA gerektirir.|Microsoft 365 E3 veya E5|
|Koşullu Erişim ile zorunlu kılınan MFA|Koşullu Erişim ilkeleriyle oturum açma özniteliklerine göre MFA gerektir.|Microsoft 365 E3 veya E5|
|Risk tabanlı Koşullu Erişim ile zorunlu kılınan MFA|kullanıcının Kimlik için Microsoft Defender ile oturum açma riskine bağlı olarak MFA gerektirme.|Azure AD Premium P2 lisansları olan Microsoft 365 E5 veya E3|
|parola sıfırlamayı (SSPR) Self-Service|Kullanıcılarınızın parolalarını veya hesaplarını sıfırlamasına veya kilidini açmasına izin verin.|Microsoft 365 E3 veya E5|
||||

### <a name="migration"></a>Geçiş

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|Windows 10 geçiş|Windows 7 veya Windows 8.1 çalıştıran cihazlarınızı Windows 10 Enterprise'a geçirin.|Microsoft 365 E3 veya E5'e dahil Windows 10 Enterprise lisansları|
|Kurumlar için Microsoft 365 Uygulamaları geçiş|Word ve PowerPoint gibi Office istemci uygulamalarınızı buluttan yüklenen ve yeni özelliklerle güncelleştirilen sürümlere geçirin.|Microsoft 365 E3 veya E5|
|Şirket içi sunucuları ve verileri Microsoft 365'e geçirme|Exchange posta kutularınızı, SharePoint sitelerinizi ve Skype Kurumsal Online'ı Microsoft 365 bulut hizmetlerine geçirin.|Microsoft 365 E3 veya E5|
||||

### <a name="device-and-app-management"></a>Cihaz ve uygulama yönetimi

|Yetenek veya özellik|Açıklama|Lisanslama|
|---|---|---|
|Microsoft Intune|Cep telefonları, tabletler ve dizüstü bilgisayarlar dahil olmak üzere kuruluşunuzun uygulamasının ve cihazların nasıl kullanıldığını denetlemek için mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sağlayan bulut tabanlı bir hizmet.|Microsoft 365 E3 veya E5|
|Temel Hareketlilik ve Güvenlik|Bu yerleşik hizmetle iPhone, iPad, Android ve Windows telefonlar gibi kullanıcılarınızın mobil cihazlarının güvenliğini sağlayın ve yönetin.|Microsoft 365 E3 veya E5|
||||

## <a name="next-steps"></a>Sonraki adımlar

Microsoft 365 kiracılarınızı ayarlamak ve yönetmek için bu adımları kullanın.

1. [Kiracılarınızı belirleme](tenant-management-tenants.md)
2. [Ağınızı iyileştirme](tenant-management-networking.md)
3. [Kimliklerinizi eşitleme ve güvenli oturum açma işlemleri uygulama](tenant-management-identity.md)
4. [Şirket içi Office sunucularınızı ve verilerinizi geçirme](tenant-management-migration.md)
5. [Cihaz ve uygulama yönetimini dağıtma](tenant-management-device-management.md)

[![Microsoft 365 kiracısını dağıtma ve yönetme adımları.](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Her adım dağıtım seçeneklerini açıklar, sonuçları ve devam eden bakım görevlerini özetler.

Kurgusal ama temsili çok uluslu bir kuruluşun Microsoft 365 kiracısının öğelerini nasıl dağıtmış olduğunu anlamak için [contoso örnek olay incelemesine](../enterprise/contoso-case-study.md) bakın.
