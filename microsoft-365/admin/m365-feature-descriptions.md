---
title: Microsoft 365 hizmet açıklamaları
ms.author: office365servicedesc
author: pebaum
manager: scotv
audience: ITPro
ms.topic: reference
f1_keywords:
- microsoft-365-and-office-365-general-information
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- Adm_ServiceDesc
- Adm_ServiceDesc_top
ms.assetid: 721676a0-5108-488e-ae0c-7316617d0006
description: Microsoft 365 özellik açıklamaları için sağlanan bilgiler hakkında bilgi edinin.
ms.openlocfilehash: b2594cdf869073730c5483f995b3ee13259c579b
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67812040"
---
# <a name="microsoft-365-feature-descriptions"></a>Microsoft 365 hizmet açıklamaları

# <a name="user-account-management"></a>[**Kullanıcı hesabı yönetimi**](#tab/User-account-management)

## <a name="user-account-management"></a>Kullanıcı hesabı yönetimi

Microsoft, kullanıcıları oluşturmak, yönetmek ve kimliklerini doğrulamak için aşağıdaki yöntemleri destekler. Ancak bu konu, tek tek Microsoft kaynaklarına erişime izin veren veya erişimi yasaklayan güvenlik özellikleri hakkında bilgi içermez (örneğin, Microsoft Exchange Online rol tabanlı erişim denetimi veya Microsoft Office SharePoint Online'de güvenliği yapılandırma). Bu özellikler hakkında ayrıntılı bilgi için [**Exchange Online hizmet açıklamasına**](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) ve [**SharePoint Online hizmet açıklamasına**](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) bakın. Yönetim görevlerini gerçekleştirmenize yardımcı olabilecek araçlar hakkında bilgiye ihtiyacınız varsa bkz. [Microsoft hesaplarını yönetme araçları](/office365/enterprise/manage-office-365-accounts). Günlük yönetim görevlerinin nasıl gerçekleştirildiğini öğrenmek için bkz. [Ortak yönetim görevleri](/office365/admin/manage/manage).
  
**Oturum açma, aboneliğinizi yükleme veya kaldırma ya da iptal etme konusunda yardıma mı ihtiyacınız var?** Yardım alma: [Office'i](https://support.office.com/article/where-to-sign-in-to-office-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) |  | [yükleme veya kaldırma](https://support.office.com/article/download-and-install-or-reinstall-office-365-or-office-2019-on-a-pc-or-mac-4414eaaf-0478-48be-9c42-23adc4716658)[Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)
  
Diğer sorunlar için [Microsoft destek merkezini](https://support.microsoft.com/contactus/) ziyaret edin. Çin'de 21Vianet tarafından sağlanan Office 365 için destek almak için [21Vianet destek ekibine](https://support.office.com/article/Get-technical-billing-and-subscription-support-for-Office-365-operated-by-21Vianet-671FB12E-F5D8-4CDF-B3E9-E8068A9AA496) başvurun.
  
**Oturum açma seçenekleri:** Microsoft'un kullanıcı kimlikleri için kullanılabilecek iki sistemi vardır: **İş veya okul hesabı (bulut kimliği)** ve **Federasyon hesabı (federasyon kimliği)**. Kimlik türü, kullanıcı deneyimini ve kullanıcı hesabı yönetimi seçeneklerinin yanı sıra donanım ve yazılım gereksinimlerini ve diğer dağıtım konularını etkiler.

**İş veya okul hesabı (bulut kimliği)** - Kullanıcılar, Microsoft bulut hizmetlerinde oturum açmak için diğer masaüstü veya kurumsal kimlik bilgilerinden ayrı olarak Azure Active Directory bulut kimlik bilgilerini alır. Bu varsayılan kimliktir ve dağıtım karmaşıklığını en aza indirmek için önerilir. İş veya okul hesaplarının parolaları Azure Active Directory [parola ilkesini](/previous-versions/azure/jj943764(v=azure.100)) kullanır.

**Federasyon hesabı (federasyon kimliği)** - Çoklu oturum açma (SSO) kullanan şirket içi Active Directory sahip kuruluşlardaki tüm abonelikler için, kullanıcılar Active Directory kimlik bilgilerini kullanarak Microsoft hizmetlerinde oturum açabilir. Kurumsal Active Directory, parola ilkesini depolar ve denetler. SSO hakkında bilgi için bkz. [Çoklu oturum açma yol haritası](/previous-versions/azure/azure-services/hh967643(v=azure.100)).

**Çoklu oturum açma:** Çoklu oturum açma kullanan kuruluşlar için, bir etki alanındaki tüm kullanıcıların aynı kimlik sistemini kullanması gerekir: bulut kimliği veya federasyon kimliği. Örneğin, şirket içi sistemlere erişmedikleri için yalnızca bulut kimliğine ihtiyaç duyan bir kullanıcı grubunuz ve Microsoft ile şirket içi sistemleri kullanan başka bir kullanıcı grubunuz olabilir. Office 365 **contractors.contoso.com ve** **staff.contoso.com** gibi iki etki alanı ekleyebilir ve bunlardan yalnızca biri için SSO ayarlayabilirsiniz. Etki alanının tamamı bulut kimliğinden federasyon kimliğine veya federasyon kimliğinden bulut kimliğine dönüştürülebilir.

**Kimlik doğrulama:** SharePoint Online ile oluşturulan anonim erişim için İnternet siteleri dışında, Microsoft hizmetlerine erişirken kullanıcıların kimlik doğrulaması yapılmalıdır. **Modern kimlik doğrulaması**, **Bulut kimliği kimlik doğrulaması** ve **Federasyon kimliği kimlik doğrulaması**. Microsoft form tabanlı kimlik doğrulaması kullanır ve ağ üzerinden kimlik doğrulama trafiği her zaman 443 numaralı bağlantı noktası kullanılarak TLS/SSL ile şifrelenir. Kimlik doğrulama trafiği, Microsoft hizmetleri için önemsiz bir bant genişliği yüzdesi kullanır.

**Modern kimlik doğrulaması** - Modern kimlik doğrulaması, Microsoft Kimlik Doğrulama Kitaplığı tabanlı oturum açmayı farklı platformlardaki Office istemci uygulamalarına getirir. Bu, Multi-Factor Authentication (MFA), Office istemci uygulamalarıyla SAML tabanlı üçüncü taraf kimlik sağlayıcıları ve akıllı kart ve sertifika tabanlı kimlik doğrulaması gibi oturum açma özelliklerini etkinleştirir. Ayrıca Microsoft Outlook'un temel kimlik doğrulama protokollerini kullanma gereksinimini de ortadan kaldırır. Office uygulamalarında modern kimlik doğrulamasının kullanılabilirliği de dahil olmak üzere daha fazla bilgi için bkz. [Office 2013 ve Office 2016 istemci uygulamaları için modern kimlik doğrulaması nasıl çalışır](/office365/enterprise/modern-auth-for-office-2013-and-2016)? Modern kimlik doğrulaması, Exchange Online için varsayılan olarak açıktır. Nasıl açacağınızı veya kapatacağınızı öğrenmek için bkz[. Exchange Online modern kimlik doğrulamasını etkinleştirme](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

**Bulut kimliği kimlik doğrulaması** - Bulut kimliklerine sahip kullanıcıların kimliği geleneksel sınama/yanıt kullanılarak doğrulanır. Web tarayıcısı, iş veya okul hesabınızın kullanıcı adını ve parolasını yazdığınız Microsoft oturum açma hizmetine yönlendirilir. Oturum açma hizmeti kimlik bilgilerinizi doğrular ve web tarayıcısının istenen hizmete gönderip oturum açtığı bir hizmet belirteci oluşturur.

**Federasyon kimliği kimlik doğrulaması** - Federasyon kimliklerine sahip kullanıcıların kimliği Active Directory Federasyon Hizmetleri (AD FS) (AD FS) 2.0 veya diğer Güvenlik Belirteci Hizmetleri kullanılarak doğrulanır. Web tarayıcısı Microsoft oturum açma hizmetine yönlendirilir; burada şirket kimliğinizi kullanıcı asıl adı (UPN) biçiminde yazarsınız; örneğin: _isabel@contoso.com_. Oturum açma hizmeti, federasyon etki alanının parçası olduğunuzu belirler ve kimlik doğrulaması için sizi şirket içi Federasyon Sunucusu'na yönlendirmeyi teklif eder. Masaüstünde oturum açtıysanız (etki alanına katılmış), kimliğiniz doğrulanır (Kerberos veya NTLMv2 kullanarak) ve şirket içi Güvenlik Belirteci Hizmeti, web tarayıcısının Microsoft oturum açma hizmetine gönderdiği bir oturum açma belirteci oluşturur. Oturum açma belirtecini kullanarak, oturum açma hizmeti web tarayıcısının istenen hizmete gönderip oturum açtığı bir hizmet belirteci oluşturur. Kullanılabilir Güvenlik Belirteci Hizmetlerinin listesi için bkz. [Çoklu oturum açma yol haritası](/previous-versions/azure/azure-services/hh967643(v=azure.100)).

**Multi-Factor Authentication:** Multi-Factor Authentication ile, kullanıcıların parolalarını doğru girdikten sonra akıllı telefonlarında bir telefon araması, kısa mesaj veya uygulama bildirimini kabul etmeleri gerekir. Yalnızca bu ikinci kimlik doğrulamasından sonra kullanıcı oturum açabilir. Microsoft yöneticileri, kullanıcıları Microsoft 365 yönetim merkezi çok faktörlü kimlik doğrulaması için kaydedebilir. [Multi-Factor Authentication](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) hakkında daha fazla bilgi edinin.

**Zengin istemci kimlik doğrulaması:** Microsoft Office masaüstü uygulamaları gibi zengin istemciler için kimlik doğrulaması iki şekilde gerçekleşebilir: **Microsoft Online Services Sign-In Yardımcısı** ve **SSL üzerinden Temel/proxy kimlik doğrulaması**. Microsoft hizmetlerinin düzgün bulunmasını ve kimlik doğrulamasını sağlamak için, yöneticilerin zengin istemciler kullanan (Microsoft Office 2010 gibi) ve Office 365 bağlanan her iş istasyonuna bir dizi bileşen ve güncelleştirme uygulaması gerekir. Masaüstü kurulumu, iş istasyonlarını gerekli güncelleştirmelerle yapılandırmak için otomatik bir araçtır. Daha fazla bilgi için bkz. [Geçerli Office masaüstü uygulamalarımı kullanma](https://support.office.com/article/3324b8b8-dceb-45e2-ac24-c642720108f7).

**Microsoft Online Services Sign-In Yardımcısı** - Masaüstü kurulumu tarafından yüklenen Oturum açma yardımcısı, oturum açma hizmetinden bir hizmet belirteci alıp zengin istemciye döndüren bir istemci hizmeti içerir. Bulut kimliğiniz varsa, istemci hizmetinin kimlik doğrulaması için oturum açma hizmetine gönderdiği (WS-Trust kullanarak) kimlik bilgileri istemi alırsınız. Federasyon kimliğiniz varsa, istemci hizmeti kimlik bilgilerinin kimliğini doğrulamak (Kerberos veya NTLMv2 kullanarak) ve oturum açma hizmetine (WS-Federation ve WS-Trust kullanarak) gönderilen bir oturum açma belirteci almak için önce AD FS 2.0 sunucusuyla iletişim kurar.

**SSL üzerinden temel/proxy kimlik doğrulaması** - Outlook istemcisi temel kimlik doğrulama kimlik bilgilerini SSL üzerinden Exchange Online geçirir. Exchange Online kimlik doğrulama isteğini kimlik platformuna ve ardından Federasyon Sunucusu'na (SSO için) şirket içi Active Directory.

**Oturum açma deneyimi:** Oturum açma deneyimi, kullanılan kimliğin türüne bağlı olarak değişir:
  
| Hizmet | Bulut kimliği | Federasyon kimliği |
|:-----|:-----|:-----|
| Outlook 2016 |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| Outlook 2013 |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| Windows 7 üzerinde Outlook 2010 veya Office 2007 |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| Windows Vista'da Outlook 2010 veya Office Outlook 2007 |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| Microsoft Exchange ActiveSync |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| POP, IMAP, Mac için Outlook |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |
| Web deneyimleri: Microsoft 365 yönetim merkezi/Web üzerinde Outlook/SharePoint Online/Web için Office |Her tarayıcı oturumunda oturum açma<sup>4</sup> |Her oturumda oturum açma <sup>3</sup> |
| SharePoint Online kullanarak Office 2010 veya Office 2007 |Her SharePoint Online oturumunda oturum açma <sup>4</sup> |Her SharePoint Online<sup>oturumunda oturum açma 3</sup> |
| Skype Kurumsal Çevrimiçi |Her oturumda oturum açma <sup>1</sup> |İstem yok |
| Mac için Outlook |Her oturumda oturum açma <sup>1</sup> |Her oturumda oturum açma <sup>2</sup> |

<sup>1</sup> İlk sorulduğunda, parolanızı gelecekte kullanmak üzere kaydedebilirsiniz. Parolayı değiştirene kadar başka bir istem almazsınız. <br/> 
<sup>2</sup> Kurumsal kimlik bilgilerinizi girersiniz. Parolanızı kaydedebilirsiniz ve parolanız değişene kadar bir daha istenmez. <br/> 
<sup>3</sup> Tüm uygulamalar oturum açmak için kullanıcı adınızı girmenizi veya seçmenizi gerektirir. Bilgisayarınız etki alanına katılmışsa parolanız istenmez. **Oturumumu açık tut'u** seçerseniz, oturumu kapatana kadar sizden bir daha istenmez. <br/> 
<sup>4</sup> **Oturumumu açık tut'u** seçerseniz, oturumu kapatana kadar sizden bir daha istenmez.

**Kullanıcı hesapları oluşturma:** Kullanıcı eklemenin birden çok yolu vardır. Daha fazla bilgi için bkz. [Kullanıcıları tek tek veya toplu olarak ekleme - Yardım Yönetici](/office365/admin/add-users/add-users) [ve Kullanıcı ekleme ve lisans atama - Microsoft 365 yönetici | Microsoft Docs](/microsoft-365/admin/add-users/add-users). Çin'de 21Vianet tarafından sağlanan Office 365 kullanıyorsanız yardım [Yönetici 21Vianet tarafından sağlanan Office 365 kullanıcı hesapları oluşturma veya düzenleme](/office365/admin/add-users/add-users) bölümüne bakın.

**Kullanıcı hesaplarını silme:** Hesapları nasıl sildiğiniz, dizin eşitlemesi kullanıp kullanmadığınıza bağlıdır. Dizin eşitlemesi kullanmıyorsanız, hesaplar yönetici sayfası veya Windows PowerShell kullanılarak silinebilir. Dizin eşitlemesi kullanıyorsanız, kullanıcıları Office 365 yerine yerel Active Directory'den silmeniz gerekir.

**Silinen hesaplar:** Bir hesap silindiğinde devre dışı bırakılır. Hesabı sildikten yaklaşık 30 gün sonra geri yükleyebilirsiniz. Hesapları silme ve geri yükleme hakkında daha fazla bilgi için bkz. [Kullanıcıları silme](/office365/admin/add-users/delete-a-user) ve [Kullanıcıları geri yükleme](/office365/admin/add-users/restore-user) veya Çin'de 21Vianet tarafından sağlanan Office 365 kullanıyorsanız, [bkz. 21Vianet tarafından sağlanan Office 365 kullanıcı hesapları oluşturma veya düzenleme - Yardım Yönetici](/office365/admin/add-users/add-users).

**Parola yönetimi:** Parola yönetimi ilkeleri ve yordamları kimlik sistemine bağlıdır.

**Bulut kimliği parola yönetimi:** Bulut kimlikleri kullanılırken, hesap oluşturulduğunda parolalar otomatik olarak oluşturulur. Bulut kimliği parola gücü gereksinimleri için bkz. [parola ilkesi](/previous-versions/azure/jj943764(v=azure.100)). Güvenliği artırmak için kullanıcıların Microsoft hizmetlerine ilk erişirken parolalarını değiştirmeleri gerekir. Sonuç olarak, kullanıcıların Microsoft hizmetlerine erişebilmesi için önce parolalarını değiştirmelerinin istendiği Microsoft 365 yönetim merkezi oturum açmaları gerekir. Yöneticiler parola süre sonu ilkesini ayarlayabilir. Daha fazla bilgi için bkz. [Kullanıcının parola süre sonu ilkesini ayarlama](/office365/admin/manage/set-password-expiration-policy).

**Bulut kimliği parola sıfırlama:** Bulut kimlikleri olan kullanıcıların parolalarını sıfırlamak için çeşitli araçlar vardır: **Yönetici parolayı sıfırlar,** **Kullanıcı parolaları Web üzerinde Outlook ile değiştirir**, **Rol tabanlı parola sıfırlama hakları** ve **Windows PowerShell kullanarak parolaları sıfırla**.

**Yönetici parolayı sıfırlar** - Kullanıcılar parolalarını kaybederse veya unutursa, yöneticiler yönetici merkezinde veya Windows PowerShell kullanarak kullanıcıların parolalarını sıfırlayabilir. Kullanıcılar yalnızca mevcut parolalarını biliyorsa kendi parolalarını değiştirebilir. Kurumsal planlarda, yöneticiler parolalarını kaybederse veya unutursa, Genel Yönetici rolüne sahip farklı bir yönetici Microsoft 365 yönetim merkezi veya Windows PowerShell kullanarak yöneticilerin parolalarını sıfırlayabilir. Daha fazla bilgi için bkz. [Yöneticiler için parolaları sıfırlama](/office365/admin/add-users/reset-passwords). Çin'de 21Vianet tarafından sağlanan Office 365 çalışıyorsanız bkz. [21Vianet tarafından sağlanan Office 365 parolaları değiştirme veya sıfırlama](https://support.office.com/article/change-or-reset-your-password-in-office-365-operated-by-21vianet-d8eb5b62-9d0e-4267-a9bf-2aa491ee6d0b).

**Kullanıcı parolaları Web üzerinde Outlook ile değiştirir** - Web üzerinde Outlook seçenekleri sayfasında, kullanıcıları **Parolayı Değiştir** sayfasına yönlendiren Parolayı değiştir köprüsü bulunur. Kullanıcının önceki parolasını bilmesi gerekir. Daha fazla bilgi için bkz. [Parolayı değiştirme](https://support.office.com/article/change-password-in-outlook-web-app-50bb1309-6f53-4c24-8bfd-ed24ca9e872c). Çin'de 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [21Vianet tarafından sağlanan Office 365 parolaları değiştirme veya sıfırlama](https://support.office.com/article/change-or-reset-your-password-in-office-365-operated-by-21vianet-d8eb5b62-9d0e-4267-a9bf-2aa491ee6d0b).

**Rol tabanlı parola sıfırlama hakları** - Kurumsal planlar için, yardım masası personeli gibi yetkili kullanıcılara Tam hizmet yöneticisi olmadan önceden tanımlanmış veya özel roller kullanarak parolaları değiştirme ve **Parola sıfırlama** hakkı atanabilir. Kurumsal planlarda varsayılan olarak, Genel Yönetici, Parola Yöneticisi veya Kullanıcı Yönetimi Yöneticisi rolüne sahip yöneticiler parolaları değiştirebilir. Daha fazla bilgi için bkz. [Yönetici rolleri atama](/office365/admin/add-users/assign-admin-roles).

**Windows PowerShell kullanarak parolaları sıfırlama** - Hizmet yöneticileri parolaları sıfırlamak için Windows PowerShell kullanabilir.

**Federasyon kimliği parola yönetimi:** Federasyon kimlikleri kullanılırken, parolalar Active Directory'de yönetilir. Şirket içi Güvenlik Belirteci Hizmeti, kullanıcıların yerel Active Directory parolalarını İnternet üzerinden Office 365 geçirmeden Federasyon Ağ Geçidi ile kimlik doğrulaması anlaşması gerçekleştirir. Yerel parola ilkeleri veya web istemcileri için iki öğeli kimlik kullanılır. Web üzerinde Outlook ParolaYı Değiştir köprüsü içermez. Kullanıcılar standart, şirket içi araçları veya masaüstü bilgisayar oturum açma seçenekleri aracılığıyla parolalarını değiştirir.

**Dizin Eşitleme:** Kuruluş ortamınızda [çoklu oturum açma (SSO) ile Dizin Eşitleme](/previous-versions/azure/azure-services/dn441213(v=azure.100)) etkinleştirilmişse ve federasyon kimlik sağlayıcınızı etkileyen bir kesinti varsa, Federasyon Oturum Açma için Parola Eşitleme Yedeklemesi, etki alanınızı el ile Parola Eşitleme'ye geçirme seçeneği sağlar. Parola Eşitleme'yi kullanmak, kesinti düzeltilirken kullanıcılarınızın erişmesine izin verir. [Tek Sign-On'den Parola Eşitleme'ye geçmeyi](https://go.microsoft.com/fwlink/p/?LinkId=509832) öğrenin.

**Lisans yönetimi:** Lisans, kullanıcıya bir dizi Microsoft hizmeti için erişim verir. Yönetici, erişmesi gereken hizmet için her kullanıcıya bir lisans atar. Örneğin, Skype Kurumsal Online'a kullanıcı erişimi atayabilirsiniz ancak SharePoint Online'a atanamaz.

**Fatura:** Microsoft faturalama yöneticileri, abonelik ayrıntılarında kullanıcı lisansı sayısı ve şirketinizin kullandığı ek hizmetlerin sayısı gibi değişiklikler yapabilir. [Lisans atama veya kaldırma'ya](/office365/admin/subscriptions-and-billing/assign-licenses-to-users) göz atın. 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [21Vianet tarafından sağlanan Office 365 lisans atama veya kaldırma](/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

**Grup yönetimi:** SharePoint Online'da sitelere erişimi denetlemek için güvenlik grupları kullanılır. Güvenlik grupları Microsoft 365 yönetim merkezi oluşturulabilir. Güvenlik grupları hakkında daha fazla bilgi için bkz. [Güvenlik grubu oluşturma, düzenleme veya silme](/office365/admin/email/create-edit-or-delete-a-security-group).

**Azure Active Directory hizmetleri:** Azure Active Directory (AD), Office 365 kapsamlı kimlik ve erişim yönetimi özellikleri getirir. Dizin hizmetlerini, gelişmiş kimlik idaresini, uygulama erişim yönetimini ve geliştiriciler için zengin standartlara dayalı bir platformu birleştirir. Office 365'daki AD özellikleri hakkında daha fazla bilgi edinmek için bkz[. Oturum açma sayfası markası ve bulut kullanıcısı self servis parola sıfırlama](https://go.microsoft.com/fwlink/?linkid=2144147). [Azure Active Directory'nin Ücretsiz, Temel ve Premium sürümleri](/previous-versions/azure/dn532272(v=azure.100)) hakkında daha fazla bilgi edinin.

# <a name="support-help-and-training"></a>[**Destek, yardım ve eğitim**](#tab/Support)

## <a name="support"></a>Destek

Kurumsal, iş, ön hat, eğitim ve kamu için her Microsoft 365 ve Office 365 aboneliğiyle Microsoft Desteği küresel teknik, ön satış, faturalama ve abonelik desteği sağlar. Hem ücretli hem de deneme abonelikleri için hem çevrimiçi hem de telefonla Microsoft 365 yönetim merkezi destek sağlanır. Daha fazla bilgi için bkz. [Microsoft Desteği Seçenekleri](/Office365/Admin/contact-support-for-business-products). Teknik desteğe başvurmak için bkz. [**İş için Microsoft 365 desteğine başvurun**](/Office365/Admin/contact-support-for-business-products). Teknik Destek, üçüncü taraf hizmetlerde veya eklentilerde sorun gidermeyi içermez. [**Microsoft Topluluğu'ndaki**](https://answers.microsoft.com/) diğer müşterilerin yanıtlarını bulma hakkında bilgi edinin.

**Destek:** Microsoft geliştirme ve operasyon ekipleri, müşterilere iş sürekliliği sağlama konusunda önemli bir rol oynayan özel bir destek kuruluşu tarafından tamamlanır. Destek personeli, hizmet ve ilişkili uygulamaları hakkında derin bilgi sahibidir ve mimari, geliştirme ve test konusunda Microsoft uzmanlarına doğrudan erişim sağlar. Destek kuruluşu, operasyonlar ve ürün geliştirmeyle yakından uyum sağlar, hızlı çözünürlük süreleri sunar ve müşterilerin seslerinin duyulması için bir kanal sağlar. Müşterilerden gelen geri bildirimler planlama, geliştirme ve operasyon süreçlerine giriş sağlar. Destek hakkında daha fazla bilgi için [Destek](/office365/servicedescriptions/office-365-platform-service-description/support) makalesine bakın.

**Çevrimiçi sorun izleme desteği:** Müşterilerin sorunlarının giderildiğini bilmesi ve zamanında çözümü izleyebilmeleri gerekir. Microsoft 365 yönetim merkezi, destek için tek bir web tabanlı arabirim sağlar. Müşteriler, hizmet isteklerini eklemek ve izlemek ve Microsoft destek ekiplerinden geri bildirim almak için portalı kullanabilir.

**Sürekli personel desteği tarafından desteklenen Kendi kendine yardım desteği:** Microsoft, müşterilerin Microsoft desteğine gerek kalmadan hizmetle ilgili sorunları çözmelerine yardımcı olabilecek çok çeşitli kendi kendine yardım kaynakları ve araçları sunar. Müşteriler hizmet isteklerine girmeden önce, en yaygın sorunlarla ilgili anında yardım sağlayan bilgi bankası makalelere ve SSS'lere erişebilir. Bu kaynaklar, bilinen sorunlara çözüm sağlayarak gecikmeleri önlemeye yardımcı olan en son bilgilerle sürekli olarak güncelleştirilir. Ancak, bir destek uzmanının yardımına ihtiyaç duyan bir sorun ortaya çıktığında; personel üyeleri, telefonla ve haftanın 7 günü, günün 24 saati yönetim portalı aracılığıyla anında yardım için kullanılabilir.

**Yönetici desteği:** Yetkili yöneticiler, hizmet isteklerini çevrimiçi olarak göndermek, destek telefon numaralarına erişmek ve tüm açık ve yakın zamanda kapatılan hizmet isteklerini görüntülemek için Microsoft 365 yönetim merkezi kullanabilir. Yönetim merkezinde gönderilen hizmet istekleri, istek kapatıldıktan sonra 14 güne kadar yeniden açılabilir. Yönergeler için bkz. [İş için Microsoft 365 desteğine başvurun](/Office365/Admin/contact-support-for-business-products).

**Microsoft 365 desteği:** Microsoft 365 teknik destek ekibi yalnızca Microsoft 365 ve Office 365 ile ilgili sorunları giderir. Müşteri ağlarından kaynaklanan sorunlar destek sınırlarının dışında kalır ve bu durumlarda müşterilerin yardım için ağ ekibiyle birlikte çalışması veya [Microsoft Ağ ekibiyle etkileşim kurması](https://support.microsoft.com/gp/contactus81?Audience=Commercial) gerekir.

**Topluluk ve self servis destek seçenekleri:** Self servis desteği tüm planlar için kullanılabilir ve [Microsoft 365 topluluğundaki](https://go.microsoft.com/fwlink/p/?LinkID=279811) sorun giderme araçları ve videoları, yardım makaleleri ve videolarının yanı sıra forumları ve wiki'leri içerir. Self servis destek kaynakları hakkında daha fazla bilgi için [Yardım ve eğitim](/office365/servicedescriptions/office-365-platform-service-description/help-and-training) hizmeti açıklamasına bakın.

**Satış öncesi destek:** Satış öncesi destek abonelik özellikleri ve avantajları, plan karşılaştırmaları, fiyatlandırma ve lisanslama konusunda yardım sağlar ve iş gereksinimlerinizi karşılamak için doğru çözümü belirlemenize yardımcı olur. Ayrıca, satış öncesi desteği sayesinde bir İş Ortağı bulabilir, abonelik satın alabilir ve deneme sürümüne kaydolabilirsiniz. Pazartesi ve Cuma günleri arasında, yerel çalışma saatleri boyunca arayabilirsiniz. Satış öncesi desteğine, teknik destekle aynı telefon numarasını kullanarak erişebilirsiniz. Destek telefon numarası, ücretsiz deneme sürümünün yönetim merkezinde bulunabilir. Yönergeler için bkz. [İş için Microsoft 365 desteğine başvurun](/Office365/Admin/contact-support-for-business-products).

**Faturalama ve abonelik yönetimi desteği:** Faturalama ve abonelik yönetimi sorunları için yardım, pazartesiden cumaya kadar yerel iş saatlerinde çevrimiçi veya telefonla sağlanır. Fatura ve abonelik yönetimi desteğine, teknik destek telefon numarasıyla veya aynı çevrimiçi servis isteği sürecini uygulayarak ulaşabilirsiniz. Destek telefon numarası yönetim merkezinde bulunabilir. Yönergeler için bkz. [İş için Microsoft 365 desteğine başvurun](/Office365/Admin/contact-support-for-business-products). Faturalama ve abonelik yönetimi sorunlarının bazı örnekleri şunlardır: Deneme sürümüne kaydolma veya abonelik satın alma, Deneme aboneliğinden ücretli aboneliğe dönüştürme, Faturayı anlama, Aboneliği yenileme, Lisans ekleme veya kaldırma ve Ücretli aboneliği iptal etme.

**Teknik destek:** Microsoft 365 abonelikleri için teknik destek, temel yükleme, kurulum ve genel teknik kullanım konusunda yardım sağlar. Aşağıdaki tabloda bu konulara ilişkin bazı örnekler listelenmiştir.

| Destek kategorisi | Örnekler |
|:-----|:-----|
|Yükleme ve kurulum  <br/> | Exchange Online:  <br/>  Posta kutusu geçişi  <br/>  Alıcı yapılandırma (posta kutusu izinleri, posta iletmeyi yapılandırma, paylaşılan posta kutusunu yapılandırma)  <br/>  Otomatik bulmayı yapılandırma  <br/>  SharePoint Online:  <br/>  İzinler ve kullanıcı grupları  <br/>  Konukların yapılandırması  <br/>  Skype Kurumsal Online:  <br/>  Yükleme ve kişi oluşturma  <br/>  Kurumlar için Microsoft 365 Uygulamaları: Yükleme ve kurulum yardımı  <br/> |
|Yapılandırma  <br/> | Hizmet yapılandırma hatası sorunları  <br/>  Sağlama sorunları  <br/>  Etki alanı kurulumu ve yeniden temsilci seçme  <br/>  Hizmet yapılandırma sorunları  <br/>  Çoklu oturum açma (SSO)  <br/>  Active Directory eşitlemesi  <br/> |

**Teknik destek olayı işleme:** Microsoft, sorun türü ve müşteri etkisi değerlendirmesine bağlı olarak açıldığında servis talebine bir önem derecesi atar. Sorun türlerine ve önem düzeylerine ilişkin örnekler aşağıdaki tabloda gösterilmektedir.

| Önem düzeyi | İşlemler ve destek açıklaması | Örnekler |
|:-----|:-----|:-----|
|Önem A (Kritik)  <br/> |Bir ya da daha fazla hizmete erişilemiyor veya bu hizmetler kullanılamıyor. Üretim, operasyon veya dağıtım son tarihleri ciddi bir şekilde etkilenmiş veya üretim ya da karlılık üzerinde ciddi bir etki bekleniyor. Birden fazla kullanıcı veya hizmet etkilenmiş.  <br/> | Posta gönderme veya almaya ilişkin yaygın sorunlar.  <br/>  SharePoint sitesi devre dışı.  <br/>  Tüm kullanıcılar anlık iletiler gönderemez, Skype Kurumsal Toplantılarına katılamaz veya bu toplantıları planlayamaz ya da Skype Kurumsal aramaları yapamaz.  <br/> |
|Önem B (Yüksek)  <br/> |Hizmet, engelli kullanıcılara özel tasarlanmıştır. Bu durumun işletmeye etkisi orta düzeydedir ve çalışma saatleri içerisinde ele alınabilir. Tek bir kullanıcı, müşteri veya hizmet kısmen etkilenmektedir.  <br/> | Outlook’taki Gönder düğmesi çalışmıyor.  <br/>  EAC'den (Exchange Yönetici Center) ayar mümkün değildir, ancak PowerShell'de mümkündür.  <br/> |
|Önem C (Kritik olmayan)  <br/> |Durumun işletmeye etkisi düşük düzeydedir. Sorun önemlidir, ancak müşteri için önemli bir geçerli hizmet veya üretkenlik etkisine sahip değildir. Tek bir kullanıcı kısmı kesinti yaşıyor, ancak kabul edilebilir bir geçici çözüm var.  <br/> | Süresi dolmayan kullanıcı parolası ayarlama.  <br/>  Kullanıcı, Exchange Online’daki kişi bilgilerini silemiyor.  <br/> |

**Teknik destek ilk yanıt süreleri:** İlk yanıt süresi, yukarıda açıklanan önem derecesi düzeylerine ve aboneliğin türüne bağlıdır. Yanıt süresi hedefleri aşağıdaki tabloda açıklanmıştır.

| Önem düzeyi | Microsoft 365 İş Temel <sup>1</sup><br> İş için Microsoft 365 Uygulamaları <sup>1</sup><br> Microsoft 365 İş Standart <sup>1</sup><br> Microsoft 365 İş Ekstra <sup>1</sup> | Tüm Microsoft 365 ve Office 365 Kurumsal (E),<br/> Ön Cephe (F),<br/> Kamu (G) ve<br/> Eğitim (A) planları | Yükseltilmiş destek seçenekleri<sup>3</sup> |
|:-----|:-----|:-----|:-----|
| Önem A (Kritik)  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: bir saat  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: bir saat  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: bir saat  <br/> |
|Önem B (Yüksek)  <br/> |Kullanılabilir: iş saatleri  <br/> Yanıt süresi: taahhüt yok  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: sonraki gün  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: 2 saat  <br/> |
|Önem C (Orta)  <br/> |Kullanılabilir: iş saatleri  <br/> Yanıt süresi: taahhüt yok  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: taahhüt yok  <br/> |Uygun: 7/24<sup>4</sup> <br/> Yanıt süresi: 4 saat  <br/> |

<sup>1</sup> İş planları, kritik olmayan tüm sorunlar için iş saatleri desteğini ve Microsoft'un 7/24 telefon desteğini içerir.<br/>
<sup>2</sup> Kurumsal planlar, tüm sorunlar için Microsoft'un 7/24 telefon desteğini içerir.<br/>
<sup>3</sup> Yükseltilmiş destek seçeneklerinin açıklamaları için bkz. [Ek destek seçenekleri](/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-office-365-general-information?tabs=Support).<br/>
<sup>4</sup> Çağrı ve hizmet isteği çoğu ülke ve bölgede haftanın yedi günü olmak üzere günde 24 saat işlenir.

**Tek başına planlar için destek:** Ücretli tek başına planlar için destek, Kurumsal hizmet ailesindeki planlarla aynı düzeyde destek ve yanıt süresi hedefleriyle işlenir. Tek başına planların listesi için bkz. [Tek başına hizmetler](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#standalone-services).

**Teknik destek dilleri:** Konuma ve dile bağlı olarak, destek mühendisleri çoğu bölgesel iş saatlerinde ve bazı durumlarda 24 saat temelinde kullanılabilir. Daha fazla bilgi için bkz. [Uluslararası Telefon Numaraları](/Office365/Admin/contact-support-for-business-products) ve [Microsoft Desteği Seçenekleri](https://products.office.com/business/office-365-for-business-support-options). Ek çeviri yardımı gerekiyorsa, destek mühendisleri hatta kalabilir ve aramaya katılmak için bir çevirmen ayarlayabilir.

**Microsoft 365 için İşletme Yardımı:** Microsoft 365 için İşletme Yardımı, küçük işletmeler için size ve çalışanlarınıza, işinizi büyütürken, işe eklemeden gündelik kullanıma kadar küçük işletme uzmanlarına 24 saat erişim sağlamak üzere tasarlanmıştır. [Microsoft 365 için İşletme Yardımı'da](/microsoft-365/admin/misc/business-assist) daha fazla bilgi edinin.

**Paylaşılan destek sorumlulukları:** Microsoft, nitelikli uzmanlardan zamanında teknik destek almanın bulut hizmetlerinin önemli bir yönü olduğunu anlar. Müşterinin BT bölümünün kullanıcıların desteğinde oynadığı kritik rol aynı derecede önemlidir.

**Yönetici sorumlulukları:** Microsoft yönetici rolleriyle Kişiler, müşterinin kuruluşunda yönetim merkezinin **Yönetici** bölümüne erişme ve hizmet istekleriyle ilgili doğrudan Microsoft ile iletişim kurarak hizmet isteklerini Microsoft'a gönderme yetkisi olan tek roldür. Kurumsal ve Microsoft 365 Uygulamaları Planı için Office 365 ile farklı işlevlere hizmet eden çeşitli yönetici türleri belirleyebilirsiniz. Bu hizmet açıklamasında, tüm yönetici kategorileri için genel olarak yönetici ifadesi kullanılır. Yönetici rolü türleri hakkında daha fazla bilgi için bkz. [Yönetici rolleri atama](/office365/admin/add-users/assign-admin-roles).

**Yönetici rolü**: Yönetici, her hizmet kullanıcısını ayarlayan ve destekleyen birincil kişidir. Yönetici, hizmet yönetimi ve hesap bakımıyla sorumludur ve kullanıcıların hizmetlere erişmesine izin vermek, istemci bağlantısı, istemci yazılımı ve mobil yükleme sorunlarını gidermek, müşterinin kuruluş kapsamı içindeki hizmet kullanılabilirliği sorunlarını gidermek, destek sorunlarını çözmek için Microsoft'un self servis destek kaynaklarını kullanmak için kullanıcı hesabı kurulumu ve yapılandırması sağlar. Müşterinin kullanıcılarına yönelik ilk desteği yöneticinin sağlaması beklenir. Ancak, yönetici self servis destek kaynaklarının yardımıyla ilgili sorunları çözemezse [Teknik desteğe](/office365/servicedescriptions/office-365-platform-service-description/support#technical-support) başvurmalıdır.

kuruluş için Office 365 rol tabanlı erişim denetimi (RBAC) modelini izler: izinler ve yetenekler yönetim rolleri tarafından tanımlanır. Kuruluşu için Office 365 kaydolan kişi otomatik olarak genel yönetici veya üst düzey yönetici olur. Beş yönetici rolü vardır: genel yönetici, faturalama yöneticisi, parola yöneticisi, hizmet yöneticisi ve kullanıcı yönetimi yöneticisi. Exchange Online, SharePoint Online ve Skype Kurumsal Online yönetimine nasıl uygulandıkları da dahil olmak üzere kuruluş için Office 365 yönetici rolleri hakkında daha fazla bilgi için bkz. [Yönetici rolleri atama](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj878348(v=ws.11)). Çin'de 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [İş için Office 365 yönetici rolleri atama](/office365/admin/add-users/assign-admin-roles).

**İş ortakları için temsilcili yönetim ve destek:** İş ortakları, hesapları müşteriler adına yönetme yetkisine sahip olabilir. Müşteri, iş ortaklarının kullanması için bir kullanıcı hesabı gerektirmez ve temsilci yönetim yetkilisi verirken lisans kullanmaz. İş ortakları, kuruluşlarındaki kullanıcılara tam veya sınırlı erişim atayabilir. Sınırlı erişim parola sıfırlama, hizmet isteklerini yönetme ve hizmet durumunu izleme haklarını içerir (temsilci yönetici olarak iş ortağı kullanma ve belirtme özelliği bölgeye göre değişir).

**Microsoft destek rolü:** Microsoft desteğinin rolü, müşteri sorunları ve yükseltmeleriyle ilgili sorunları gidermek ve sağlamak, belirli hizmet istekleriyle ilgili bilgileri toplamak ve doğrulamak, sorun koordinasyonu ve çözüm yönetimi sağlamak, sorunların sürekli olarak ele alınmasına yardımcı olmak için yöneticilerle iletişimi sürdürmek, lisanslama, faturalama ve abonelik sorguları konusunda yardım sağlamak, satın alma ve deneme sorguları için yardım sağlamak,  ve anketler aracılığıyla hizmeti nasıl geliştireceklerine ilişkin müşteri geri bildirimlerini sürekli olarak toplayın.

**Yükseltilmiş destek seçenekleri:** Microsoft'un içerdiği destek hizmetleri birçok müşterinin gereksinimlerini karşılasa da, daha gelişmiş gereksinimleri veya karmaşık ortamları olan müşteriler Microsoft'un ücretli destek seçeneklerini göz önünde bulundurmalıdır. Bu yükseltilmiş destek teklifleri arasında daha hızlı yanıt hedefleri, sorun önem düzeyini ayarlama yeteneği ve ek teknik kaynaklara ve destek hesabı yönetimine erişim yer alır. Yükseltilmiş destek örnekleri şunlardır: Hizmet güncelleştirme yönetimi; istemciler ve hizmetler için uçtan uca destek; gelişmiş mühendislerden reaktif ve danışmanlık hizmetleri; ve olay yönetimi ve yerinde atölyeler.

**Ek destek hizmetleri:** Birkaç tür ek destek hizmeti vardır: Office 365 geçişlerini desteklemek üzere tam yaşam döngüsü hizmeti arayan büyük kurumsal müşteriler için, çevrimiçi hizmete erişmek için hem Microsoft'u hem de şirket içi teknolojileri kapsayan yönetilen bir destek hizmeti arayan büyük kurumsal müşterilere yönelik seçenekler için [bkz. Çalışanlarınızı daha üretken hale](https://www.microsoft.com/en-us/microsoftservices/cloud-productivity.aspx) getirmek için güçlendirme.  Bkz. [Premier Destek](https://www.microsoft.com/enterprise/services/support): Birleşik Devletler, Kanada ve Birleşik Krallık'taki daha küçük kurumsal müşteriler için seçenekler için bkz. [Profesyonel Doğrudan Destek](https://support.microsoft.com/help/4341255/support-for-business).

**Ortak:** Hizmet isteği biletleri oluşturmak da dahil olmak üzere bir Microsoft iş ortağı seçebilir ve yönetim işlevlerini devredebilirsiniz. Daha fazla bilgi için [İş Ortakları](/office365/servicedescriptions/office-365-platform-service-description/partners) hizmet açıklamasına ve [Abonelik danışmanı iş ortağı ekleme, değiştirme veya silme](/office365/admin/misc/add-partner) konularını inceleyin.

**Geliştiriciler:** Geliştiriciler [, MSDN Microsoft Geliştirici Ağı'nda](https://developer.microsoft.com/office/docs) Office ve SharePoint uygulamaları geliştirme hakkında daha fazla bilgi edinebilir. Geliştirici Desteği, geliştirici topluluğundaki çevrimiçi bloglar ve forumlar, Premier veya İş Ortağı destek kaynakları veya doğrudan Microsoft aracılığıyla kullanılabilir. Geliştirici Desteği seçeneklerinin bağlantıları için bkz. [Destek Kaynakları](https://developer.microsoft.com/office/docs).

**Toplu lisanslama: Toplu lisanslama** programı kapsamında Zaten Microsoft'tan lisans satın aldıysanız, destek için şu yere gidebilirsiniz: Lisanslar ve anahtarları bulmayla ilgili destek için [Toplu Lisanslama Hizmet Merkezi'ne](https://www.microsoft.com/licensing/servicecenter/default.aspx) gidin; teknik destek için bkz [. Teknik destek](/office365/servicedescriptions/office-365-platform-service-description/support#technical-support); faturalama soruları için bkz [. Faturalama ve abonelik yönetimi desteği](/office365/servicedescriptions/office-365-platform-service-description/support#billing-and-subscription-management-support); toplu lisanslama hakkında genel bilgi için [Toplu Lisanslama'ya](https://www.microsoft.com/licensing/default) gidin.

> [!NOTE]
>
> Microsoft ekibi betikleri desteklemez (örneğin JavaScript, VBScript vb. gibi betik oluşturma teknikleri veya VBA). Betiklerle ilgili yardıma ihtiyacınız varsa [**Microsoft Desteği**](https://support.microsoft.com/) başvurun. Office uygulamaları kullanım desteği için bkz. [**Aboneler için Microsoft Office uygulaması sorunları için destek seçenekleri**](https://support.office.com/article/support-options-for-microsoft-office-application-issues-for-office-365-subscribers-0a02cd18-19be-4cfa-b430-3b53ea26920f).

## <a name="help-and-training"></a>Yardım ve eğitim

Microsoft Office 365 aşağıdaki yardım ve eğitim kaynaklarını sağlar. Topluluk kaynakları Office 365 dünya çapındaki sürümleri için geçerlidir. 21Vianet tarafından sağlanan Office 365 kullanıyorsanız WeChat'i kullanabilirsiniz. [**Bkz. 21Vianet tarafından sağlanan Office 365 için teknik, faturalama ve abonelik desteği alma**](/microsoft-365/admin/contact-support-for-business-products) ve QR kodu için sayfanın en altına gitme.

**Çevrimiçi yardım:** Yardım makaleleri ve videoları, Office 365 portalın üst gezinti çubuğundaki yardım simgesi ve Microsoft 365 yönetim merkezi dahil olmak üzere hizmetteki tüm satır içi yardım bağlantılarından edinilebilir. Ayrıca, üzerinde tüm Office 365 yardımlarını [https://office.microsoft.com](https://go.microsoft.com/fwlink/p/?LinkId=272056)da arayabilirsiniz.

**Eğitim:** Eğitim videolar, kaydedilen canlı etkinlikler ve sertifikasyona yol açan sınıflar aracılığıyla sağlanır. Daha fazla bilgi için bkz. [Microsoft 365 temel video eğitimi](https://support.microsoft.com/office/microsoft-365-basics-video-training-396b8d9e-e118-42d0-8a0d-87d1f2f055fb), [Yöneticiler ve BT Uzmanları için](/training/m365/) [Microsoft 365 Eğitimi](https://support.microsoft.com/training), [küçük işletmeler için](/microsoft-365/admin/admin-video-library) [tam öğrenme kataloğuna göz atma](/training/browse/), [Microsoft sertifikalı olma](/certifications/), [tüm öğrenme seçeneklerine göz atma](/training/browse/) ve [canlı ve kayıtlı etkinlikleri izleme](/training/tv/).

**Comunity:** Office 365 Topluluğu, kendi kendine yardım desteği bilgileri için tek bir hedeftir. Destek forumları, wiki'ler ve bloglar aracılığıyla müşterilerin çeşitli teknik, faturalama ve hizmet sorularına yanıt bulmasına yardımcı olacak en son bilgilere sahiptir. Destek forumları, Microsoft Desteği aracıları tarafından yönetilir ve personel tarafından yönetilir. Office 365 Topluluğu giriş sayfasından müşteriler şu kaynaklara erişebilir: Forumlar, Wiki'ler, Bloglar. Daha fazla bilgi için [Office 365 topluluğuna ziyaret edin](https://techcommunity.microsoft.com/).

**Forum:** Forumlar, topluluk katılımcılarına teknik destek soruları gönderebilecekleri ve Office 365 hizmetleriyle ilgili konuları tartışabilecekleri çevrimiçi bir hedef sağlamak için tasarlanmıştır. Kullanılabilir forumlar şunlardır: Office 365 dağıtma, Dizin tümleştirme hizmetleri, Office 365 etki alanları, İndirmeler, Email ve takvim, anlık ileti, toplantılar ve konferans, Yönetme Office 365, Projeleri yönetme, Mobil erişim, Mac için Office 365, Office uygulamaları, Siteler ve belge paylaşımı, Güven Merkezi belgeleri, Office 365, Yammer'a yükseltme

**Wikis:** Wiki'ler, Microsoft çalışanları ve kimliği doğrulanmış topluluk üyeleri tarafından oluşturulan wiki sayfalarını içerir. Bu işbirliğine dayalı site, belirli Office 365 teknik senaryolarla ilgili en son toplu içeriği kapsar. Her wiki sayfası genellikle ilgili teknik senaryoyla ilgili web sitelerine, web yayınlarına, sorun giderme videolarına, SSS sayfalarına, belgelere ve indirmelere bağlantılar içerir. Her düzeltme tarihi ve yazar diğer adının geçmiş izlemesinin yanı sıra sürümleri karşılaştırma özelliği sağlanır.

**Bloglar**: Office 365 Teknik Blogu, Office 365 çevrimiçi hizmetler hakkında güncel bilgileri almak ve Office 365 özelliklerin ve işlevlerin avantajları hakkında bilgi edinmek için iyi bir kaynaktır. Konu başlıkları arasında ürün içgörüleri, yeni ürün duyuruları, müşteri görüşmeleri ve bir konuk blog serisi yer alır.

**Office 365 kılavuzunu yönetme:** Büyük kuruluşların BT uzmanları Office 365 belgeleri yönet giriş sayfasını ziyaret edebilir. Bu sayfa, büyük kuruluşlara yönelik karmaşık dağıtım kılavuzuna bağlantılar sağlar. Daha fazla bilgi için [Office 365 yönetme](/Office365/) sayfasını ziyaret edin.

**Diğer kendi kendine yardım kaynakları:** Office 365 Topluluğu ve çevrimiçi yardıma ek olarak, Office 365 aşağıdaki kendi kendine yardım kaynaklarını içerir: Office 365 için sorun giderme aracı, Teknik destek videoları, Sosyal medya

**Office 365 için sorun giderme aracı** Sorununuzla ilgili bir dizi kısa soruyu yanıtladıktan sonra, Office 365 için Sorun Giderme aracı yanıtlarınıza göre yararlı araçlar ve bilgiler önerir. Aracı kullanmak için, Office 365 Topluluğu'nun [Yöneticiler ve BT uzmanları için Office sorun giderme](/office365/troubleshoot/) sayfasına gidin.

**Teknik destek videoları** Müşterilerden en sık sorulan sorulara göre yalnızca İngilizce eğitimle ilgili sorun giderme videoları geliştirilmiştir. Her hafta 35'ten fazla video ve daha fazlası geliyor. Konular, BlackBerry® Yönetim Merkezi'ne genel bakıştan dizin eşitlemesini etkinleştirmeye ve geçirmeye kadar uzanır. Bu videoları görüntülemek için Office 365 Topluluğu sitesine gidin ve videoları arayın. Müşterilerin topluluk portalı aracılığıyla video isteği göndermeleri önerilir. Müşteriler Office 365 [YouTube](https://go.microsoft.com/fwlink/?LinkId=272059) ve [Vitrin](/office365/servicedescriptions/office-365-service-descriptions-technet-library) kanallarına da gidebilir.

**Sosyal medya** [Facebook](https://go.microsoft.com/fwlink/?LinkId=272061), [Twitter](https://go.microsoft.com/fwlink/?LinkId=272062) ve [LinkedIn'de](https://www.linkedin.com/groups/Microsoft-Office-365-3724282?itemaction=mclk&anetid=3724282&impid=&pgkey=anet_search_results&actpref=anetsrch_name&trk=anetsrch_name&goback=%2Egdr_1307137875158_1) Office 365 takip etmek, müşterilerin ve iş ortaklarının Office 365 hakkında daha fazla eğitim almak için bir yol sağlar. Office 365 hakkında bilgi edinmenin bu hızlı ve kolay yolu, müşterilerin başkalarının söylediklerini dinlemesine ve kendi yorumlarını ve tweet'lerini ekleyebilmesine olanak tanır. Microsoft destek uzmanları, destekle ilgili tüm sorulara yardımcı olmak için Microsoft ile ilgili Facebook ve Twitter etkinliklerini izler. En güncel Facebook akışlarını ve en son tweet'leri bulmak için, müşteriler ve iş ortakları arasındaki günlük tartışmaları dinlemek için Office 365 Topluluğu giriş sayfasının en altına gidin.

**Diller:** Çevrimiçi Yardım Makaleleri, Wiki'ler ve Bloglar, Forumlar, Teknoloji Merkezleri ve Sorun Giderme çeşitli dillerde sağlanır.

**Çevrimiçi Yardım Makaleleri için Diller:** Bulgarca, Çince-Basitleştirilmiş, Çince-Geleneksel, Çekçe, Danca, Felemenkçe, Estonca, Fince, Fransızca, Almanca, Yunanca, Macarca, İtalyanca, Japonca, Korece, Letonca, Litvanca, Norveççe, Lehçe, Portekizce, Portekizce-Brezilya, Rumence, Rusça, Sırp, Slovakça, Slovence, İspanyolca, İsveççe, Tayca, Türkçe ve Ukraynaca.

**Wiki'ler ve Bloglar için Diller:** Arapça, Çince-Basitleştirilmiş, Geleneksel Çince, Danca, Felemenkçe, Fransızca, Almanca, İtalyanca, Japonca, Korece, Norveççe, Lehçe, Portekizce-Brezilya, Rusça, İspanyolca ve İsveççe.

**Forumlar için Diller:** Çince-Basitleştirilmiş, Geleneksel Çince, Fransızca, Almanca, İtalyanca, Japonca, Korece, Lehçe, Portekizce-Brezilya, Rusça ve İspanyolca.

**Teknoloji Merkezi dilleri:** Çince-Basitleştirilmiş, Geleneksel Çince, Fransızca, Almanca, İtalyanca, Japonca, Korece, Portekizce-Brezilya, Rusça ve İspanyolca.

**Sorun Giderme Dilleri:** Çince-Basitleştirilmiş, Geleneksel Çince, Fransızca, Almanca, İtalyanca, Japonca, Korece, Lehçe, Portekizce-Brezilya, Rusça ve İspanyolca.

# <a name="domains-networking-and-partners"></a>[**Etki alanları, ağ ve iş ortakları**](#tab/Domains)

## <a name="domains"></a>Etki alanları

**Etki alanları**: Etki alanı eklediğinizde, adım adım bir sihirbaz kullanıcıları eklemenize ve e-posta adreslerinizi ve diğer hizmetlerinizi işletme adınıza dönüştürmenize yardımcı olur. Sihirbazı tamamladıktan sonra, iş e-postanız geçerli e-posta sağlayıcınıza gitmek yerine Microsoft'a gelmeye başlar. Daha fazla bilgi edinmek için bkz. [Kullanıcılarınızı ve etki alanlarınızı Microsoft'a ekleme](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611). 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [Etki alanınızı doğrulama](/office365/admin/setup/add-domain).

**Özel etki alanları:** Aboneliğinize en fazla 5000 etki alanı ekleyebilirsiniz (alt etki alanları dahil). Zaten başka bir Microsoft bulut hizmetinde kullanmakta olduğunuz bir etki alanını Microsoft 365'e ekleyemezsiniz. Bu kısıtlama aynı etki alanının birden çok aboneliğe eklenebileceği anlamına da gelir. Daha fazla bilgi için bkz [. Etki Alanları SSS](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

Yeni bir kullanıcı oluşturduğunuzda, kullanıcının oturum açma adı ve e-posta adresi Microsoft 365 yönetim merkezi ayarlandığı gibi varsayılan etki alanına atanır. Daha fazla bilgi için bkz. [Kullanıcılarınızı ve etki alanınızı ekleme](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611). Varsayılan olarak abonelik, hesapla oluşturulan <*şirket* **adını.onmicrosoft.com**> etki alanını kullanır. Office 365 etki alanları hakkında daha fazla bilgi için [Etki alanları](/office365/servicedescriptions/office-365-platform-service-description/domains) hizmet açıklamasına bakın. Çin'de 21Vianet tarafından sağlanan Office 365 kullanıyorsanız, varsayılan etki alanı *companyname.onmsChina.cn*> **<**.

**Etki alanları ekleme:** **onmicrosoft.com** etki alanını korumak yerine Microsoft'a bir veya daha fazla özel etki alanı ekleyebilir ve kullanıcıları doğrulanmış etki alanlarından herhangi biriyle oturum açmaları için atayabilirsiniz. Her kullanıcının atanan etki alanı, gönderilen ve alınan e-posta iletilerinde görünecek e-posta adresidir. Her birinde farklı bir ad alanıyla temsil edilen en fazla 900 kayıtlı İnternet etki alanını barındırabilirsiniz.

**İkinci ve üçüncü düzey etki alanları:** Office 365 Kurumsal ve İş için Microsoft 365 Uygulamaları ile, marketing.contoso.com gibi üçüncü düzey etki alanları da dahil olmak üzere herhangi bir düzey etki alanı ekleyebilirsiniz. Bkz. [Microsoft'a özel alt etki alanları veya birden çok etki alanı ekleme](/office365/admin/setup/domains-faq). 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [21Vianet tarafından sağlanan Office 365 özel alt etki alanları veya birden çok etki alanı ekleme](/office365/admin/setup/domains-faq).

**Etki alanı doğrulama DNS kayıtları:** Microsoft 365 ile DNS barındırma sağlayıcınızda tüm DNS kayıtlarınızı yönetebilir veya Microsoft'un etki alanınızın DNS kayıtlarını sizin için ayarlamasını ve yönetmesini seçebilirsiniz. Kayıtları yönetmeye devam ederseniz, belirli kayıtları gerektiği gibi Microsoft hizmetlerine işaret eden şekilde değiştirirsiniz. Etki alanınızın DNS kayıtlarını sizin yerinize Microsoft yönetiyorsa, önce etki alanınızın ad sunucusu kayıtlarını Microsoft'a işaret etmek üzere değiştirmelisiniz, ardından Microsoft hizmetlerinizi ayarlar ve ardından etki alanınızın DNS kayıtları Microsoft'ta yönetilir.

**Etki alanı kayıt şirketleri:** Kayıtları eklemek için her kayıt için kullanılacak belirli değerler de dahil olmak üzere adım adım yol tarifleri sağladığımız etki alanı kayıt şirketleri listesi için bkz. [DNS kayıtları oluşturma](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) veya 21Vianet tarafından sağlanan Office 365 kullanıyorsanız, bkz. 21Vianet tarafından sağlanan Office 365 için herhangi bir sağlayıcıda DNS kayıtları oluşturma. Etki alanınız GoDaddy'de kayıtlıysa Microsoft, GoDaddy'de sizin için gerekli kayıtları oluşturabilir.

**DNS kayıtlarını yönetme:** DNS kayıtlarınızın nerede barındırıldığı fark etsin, DNS kayıtlarını Microsoft'ta veya farklı bir barındırma sağlayıcısında barındırılan genel bir web sitesinin URL'si için etki alanınızı kullanacak şekilde ayarlayabilirsiniz. Microsoft, DNS sorunlarını bulmak ve düzeltmeye yardımcı olmak için DNS kayıtlarınızı proaktif olarak denetler. DNS kayıtlarınız beklediğiniz kayıtlarla eşleşmiyorsa, Microsoft 365 yönetim merkezi bir bildirim alırsınız ve tanımlanan olası sorunların nasıl çözüldüğünü bildiren bilgilerle birlikte size bildirilir. Daha fazla bilgi için bkz. [Microsoft DNS kayıtlarını nasıl yönetir](/office365/admin/setup/domains-faq) veya 21Vianet tarafından sağlanan Office 365 için bkz. [DNS kayıtlarınızı yönetirken Office 365 için DNS kayıtları oluşturma](/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records).

**Etki alanını paylaşma:** Microsoft'ta bir etki alanı için bazı e-posta adreslerini, bazılarını da önceki e-posta sağlayıcınızda kullanabilirsiniz. Ek kurulum adımları gerektirdiği ve Microsoft hizmetleri için bazı sınırlamaları olduğu için bu yalnızca pilot aşamasında kullanılması önerilir. Daha fazla bilgi için bkz. [Küçük bir işletme için Microsoft 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7) pilotu ve [Uygunluk - FastTrack – Microsoft 365](/fasttrack/eligibility).

## <a name="networking"></a>Ağ

Microsoft aşağıdaki ağ özelliklerini destekler.

**Bağlantı noktaları, protokoller ve IP adresleri:** Microsoft, IPv4 ve IPv6 adreslerini kullanır. IPv6 adresleme kullanımı isteğe bağlıdır ve Office 365 ile bağlantı için gerekli değildir. Tüm Microsoft 365 özellikleri IPv6 kullanılarak tam olarak etkinleştirilmez. Ipv6 desteği hakkında daha fazla bilgi için bkz. [Microsoft hizmetlerinde IPv6 desteği](/office365/enterprise/ipv6-support).

**IP adresleri:** Microsoft, Microsoft yardımında izin verilen IP adreslerinin listesini tutar. Daha fazla bilgi için bkz. [URL'ler ve IP adresi aralıkları](/office365/enterprise/urls-and-ip-address-ranges). 21Vianet tarafından sağlanan Office 365 için bkz. [21Vianet tarafından sağlanan Office 365 için URL'ler ve IP Adresleri](/office365/enterprise/managing-office-365-endpoints).

> [!IMPORTANT]
>
> Belirli IP adresi alt ağlarına yönlendirmek yerine yukarıdaki makalelerde (*.Outlook.com, *.MicrosoftOnline.com ve *.SharePoint.com gibi) listelenen kök etki alanı adlarına yönlendirmeyi etkinleştirmenizi kesinlikle öneririz. IP adresi alt ağlarına güvenmek, değişiklikler yapıldıktan sonra kullanıcılarınız için kesinti riski oluşturur.

**Bant genişliği gereksinimleri:** Bant genişliği gereksinimleri hakkında bilgi için bkz. [İnternet bant genişliği planlaması](/office365/enterprise/network-planning-and-performance).

**Microsoft'a bağlanma:** Microsoft'a yönelik tüm bağlantılar genel İnternet üzerinden veya özel bir Azure ExpressRoute bağlantısı üzerinden yapılır ve uygun şekilde SSL ile güvenli hale getirilir. Azure ExpressRoute, İnternet'i atlayarak doğrudan genel Microsoft ağına bağlanmaya olanak tanır. Microsoft ağ iş ortağı, genel Microsoft ağına bağlantı sağlar. Azure ExpressRoute hakkında daha fazla bilgi için bkz. [Office 365 için Azure ExpressRoute](/microsoft-365/enterprise/azure-expressroute).

**WAN hızlandırıcıları:** Microsoft, Office 365 ile müşteriye ait WAN hızlandırma ve önbelleğe alma cihazları için destek sağlamaz. Yüksek gecikme süresi veya düşük bant genişliği koşulları altında performansı geliştirmek için WAN iyileştirme denetleyicisi kullanmaya karar verirseniz, Microsoft ile hizmet isteklerinde sorun giderirken devre dışı bırakmanız ve cihaz desteği için cihaz satıcınızla birlikte çalışmanız gerekir. Daha fazla bilgi için bkz[. WAN Hızlandırma ve Office 365 ile cihazları önbelleğe alma](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

**Microsoft Global Network:** Microsoft ağ altyapısı, hizmetlerin küresel dağıtımını sağlamak için veri merkezleri, sunucular, içerik dağıtım ağları, uç bilgi işlem düğümleri ve fiber optik ağlardan oluşan büyük bir küresel portföyden oluşur. Gelişmiş hizmet izleme ve izleme, ortaya çıkan kesintilerin nedenini saptamaya, tanılamaya ve yönetmeye yardımcı olmak için veri merkezi, ağ omurgası, internet değişimleri ve ötesinde görünürlük sağlayarak her bileşenle en derin düzeylerde tümleştirilir. Ağ, performans düşüşü olmadan büyük ölçekli ağ kesintileri için bile yeterli kapasiteyi korumak için oluşturulmuş. Daha fazla bilgi için bkz. [Microsoft Global Network](/azure/networking/microsoft-global-network).

**Tüketici hizmetleri ağları:** Microsoft, müşteri verilerinin gizliliğini ve bütünlüğünü korumak için tüketici hizmetleri ağlarını Microsoft ağlarından ayrı tutar. Fiziksel ayırma, mantıksal ayırma, Güvenlik duvarları ve protokol kısıtlamaları dahil ancak bunlarla sınırlı olmamak üzere bilgi akışlarını denetlemek için birden çok teknik kullanılır. Daha fazla bilgi için bkz. [Office 365 Güven Merkezi](https://www.microsoft.com/trust-center).

**Fiziksel ayrım:** Ağ kesimleri, belirli iletişim desenlerini önlemek için yapılandırılmış yönlendiricilerle fiziksel olarak ayrılır.

**Mantıksal ayırma:** Sanal LAN (VLAN) teknolojisi, iletişimi daha da ayırmak için kullanılır.

**Güvenlik duvar -ları:** Güvenlik duvarları ve diğer ağ güvenlik zorlama noktaları, İnternet'e açık sistemlerle veri alışverişlerini sınırlamak ve sistemleri Microsoft tarafından yönetilen arka uç sistemlerinden yalıtmak için kullanılır.

## <a name="partners"></a>Ortak

Yetkili bir Microsoft iş ortağı olarak Microsoft Office 365 size müşteri tabanınızı büyütme ve onlarla kalıcı ilişkiler kurma fırsatı sunar. Müşterileriniz, size ödenen aylık veya yıllık ücret karşılığında bulut tabanlı hizmetleri kullanabilir ve böylece veri yedeklemelerini, sunucu donanımlarını ve sunucu güncelleştirmelerini yönetmek zorunda değildir. Kullanabileceğiniz hizmetler, sağlama yetkisine sahip olduğunuz hizmet türlerine bağlıdır.

**İş ortağı özellikleri:** İş ortağı özelliklerini kullanma hakkında daha fazla bilgi için bkz. [**İşletmenizi oluşturma ve Office 365 iş ortağı aboneliğinizi yönetme**](https://go.microsoft.com/fwlink/?LinkID=271614&clcid=0x409) ve iş ortağı özellikleri sunusunu gözden geçirme. İş ortağı özelliklerine erişim elde etmek için [**Microsoft Online Services İş Ortağı Sözleşmesi'ni**](https://go.microsoft.com/fwlink/p/?LinkId=285473) imzalayarak Cloud Essentials'a katılabilirsiniz.

> [!NOTE]
>
> Aşağıda açıklandığı gibi iş ortağı özellikleri 21Vianet tarafından sağlanan Office 365 henüz sunulmamaktadır.

**Deneme davetleri ve satın alma siparişleri oluşturun:** Müşterileriniz Office 365 İş **ortağına genel bakış** sayfasını kullanarak Office 365 deneyebilmeleri için deneme davetleri oluşturabilir ve müşterilerinize gönderebilirsiniz. Davet, teklife bağlı olarak bir veya daha fazla hizmet içerebilir. Temsilcili yönetim sunma yetkiniz varsa, deneme davetine hesabı müşteriniz adına yönetmenizi sağlayan bir seçenek ekleyebilirsiniz. Bu, müşterinizin Office 365 denemesini kolaylaştırır.

**Deneme daveti:** Bir müşteriye Office 365 için bir deneme daveti gönderdikten sonra, müşterinizin ihtiyaçlarına uyacak şekilde özelleştirilmiş bir satın alma teklifi oluşturup göndererek, müşterinizin ihtiyaç duyduğu hizmetler ve lisans sayısı gibi işlemleri takip edebilirsiniz. Temsilcili yönetim sunma sertifikalıysanız, satın alma teklifine müşteriniz adına hesabı yönetmenizi sağlayan seçeneği ekleyebilirsiniz.

**Temsilcili yönetim sağlayın:** Temsilcili yönetim, bir iş ortağının tüm müşteri hizmetleri ve aboneliklerine tam yönetici erişimine sahip olmasını sağlar. Bu, müşteriler adına yönetim görevlerini gerçekleştirebileceğiniz anlamına gelir (posta kutularını ayarlama, kullanıcı ve grup ekleme veya kaldırma, veri geçişi ve Hizmet isteklerini Microsoft Müşteri Hizmetleri ve Desteği'ne gönderme dahil). Temsilcili yönetim özelliği yalnızca Cloud Essentials, Cloud Accelerate veya Bulut Dağıtımı programlarına kayıtlı iş ortakları için sunulur.

**Yönetici temsilcisi:** Müşterinin hesabını yönetmeye başlayabilmeniz için önce müşterinin sizi yönetici temsilcisi olarak yetkilendirmesi gerekir. Müşteri onayı almak için, temsilci yönetimi için bir teklif gönderirsiniz. Bu teklifi deneme daveti veya satın alma teklifiyle birlikte ekleyebilirsiniz. Müşteri, iş ortağının davet e-postasına yanıt vererek Temsilci Yönetim iş ortağını yetkilendirilir. Müşteri, bir iş ortağına kendi adına yönetim görevleri gerçekleştirme yetkisi verse bile, doğrudan Microsoft desteğine başvurabilir ve hizmet istekleri gönderebilir.

**Temsilcili iş ortağı:** Her müşterinin bir temsilci yönetim iş ortağına sahip olması gerekir. Bu iş ortağı aynı zamanda müşterinin Kayıt İş Ortağı (POR) olabilir ancak olması gerekmez. POR ve temsilci yönetim iş ortaklarının rolleri ayrıdır ve müşteri bunları ayrı olarak belirtir. Bu, müşterinin satın alma önerisi için bir iş ortağı ve uygulama veya yönetilen hizmetler için başka bir iş ortağı seçmesini sağlar. Ayrıca, iş ortaklarının bu rollerden birinde veya her ikisinde de uzmanlık alanı olan bir işletme oluşturmayı seçmesine olanak tanır.

**Office 365 Market'teki müşterilerle ve diğer iş ortaklarıyla bağlantı kurma:** Office 365 Market, müşterilere iş ortağı hizmetlerini ve uzmanlığını bulma fırsatı sunar. Daha fazla bilgi için bkz. [Kayıt veya sonraki pencere öğesi aracılığıyla müşterilerle bağlantı kurma](/dynamics365/sales/connect-with-customers) ve [Diğer iş ortaklarıyla çalışma - İş Ortağı Merkezi](/partner-center/work-with-other-partners).

**Microsoft iş ortağı ağı:** Microsoft İş Ortağı Ağı, iş ortaklarımızın ihtiyaçlarına hizmet etmeye kararlıdır. Ağa katılmak ve Microsoft'un iş ortaklarına nasıl hizmet verdiğine bakmak için bkz. [Microsoft İş Ortağı Ağı](https://go.microsoft.com/fwlink/?LinkID=272021&clcid=0x409).

# <a name="privacy-security-rights-and-sla"></a>[**Gizlilik, güvenlik, haklar ve SLA**](#tab/Privacy)

## <a name="privacy-security-and-transparency"></a>Gizlilik, güvenlik ve saydamlık

Microsoft, müşterilerimizle olan iş ortaklıklarına değer verir ve müşteri verilerinin gizliliğini ve güvenliğini korumaya büyük önem verir. Daha fazla bilgi için bkz. [Microsoft Güven Merkezi](https://go.microsoft.com/fwlink/?LinkID=717951&clcid=0x409). Bu makaledeki bilgiler dünya çapındaki Office 365 sürümleri için geçerlidir. ABD Kamu Office 365 dahil olmak üzere ulusal bir Office 365 bulut örneği ve 21Vianet tarafından sağlanan Office 365 kullanıyorsanız bkz. [**Microsoft National Clouds**](https://go.microsoft.com/fwlink/?linkid=841582).

**Gizli -lik:** Microsoft Office 365 verilerinizin gizliliğini nasıl koruduğu hakkında bilgi edinmek için [Gizlilik](https://go.microsoft.com/fwlink/?LinkID=717953&clcid=0x409) sayfasına bakın. Yöneticilerin Kurumsal, İş, Kamu ve Eğitim için Office 365 gizlilik ayarlarını yapılandırmak üzere atacakları belirli adımlarda bkz. [Yöneticiler için Gelişmiş Gizlilik Seçenekleri](https://go.microsoft.com/fwlink/p/?LinkID=285202).

**Diğer hizmetler için güvenlik ve gizlilik:** Kurumlar için Microsoft 365 Uygulamaları dahil olmak üzere diğer Microsoft hizmetlerinin güvenliği ve gizliliği hakkında bilgi için bkz. [Güven Merkezi hangi çevrimiçi hizmetler uygulanır?](https://www.microsoft.com/trustcenter/default.aspx)

**Güvenlik:** Microsoft'un Office 365 hizmetlerini nasıl güvenli ve güvenilir bir şekilde teslimdiğini öğrenmek için bkz [. Güvenlik](https://go.microsoft.com/fwlink/?LinkID=717954&clcid=0x409).

**Saydam -lık:** Müşteri olarak verilerinizin nerede bulunduğunu, Microsoft'ta kimlerin erişebileceğini ve bu bilgilerle şirket içinde neler yapabileceğimizi öğrenebilirsiniz. Daha fazla bilgi için bkz [. Saydamlık](https://go.microsoft.com/fwlink/?LinkID=717955&clcid=0x409).

**Advanced eDiscovery:** Elektronik bulma veya eBulma, yasal davalarda kanıt olarak kullanılabilecek elektronik bilgileri tanımlama ve teslim etme işlemidir. Advanced eDiscovery, Office 365'daki mevcut eBulma özellikleri kümesini temel alır ve büyük, yapılandırılmamış veri kümelerini analiz edip yasal bir davayla ilgili veri miktarını azaltmanıza olanak sağlar. Office 365 Uyumluluk Merkezi'ndeki Arama özelliğini kullanarak kuruluşunuzdaki tüm içerik kaynaklarının ilk aramasını yaparak belirli bir yasal davayla ilgili olabilecek verileri tanımlayabilir ve toplayabilirsiniz. Daha sonra Advanced eDiscovery metin analizi, makine öğrenmesi ve ilgi/tahmine dayalı kodlama özelliklerini uygulayarak bu verileri analiz edebilirsiniz. Daha fazla bilgi için bkz. [Advanced eDiscovery](/microsoft-365/compliance/overview-ediscovery-20).

**Müşteri Kasası:** Microsoft yöneticisi olarak, Bir Microsoft destek mühendisinin yardım oturumu sırasında verilerinize nasıl erişebileceğini denetlemek için Müşteri Kasası'na erişebilirsiniz. Mühendisin bir sorunu gidermek ve düzeltmek için verilerinize erişmesi gereken durumlarda, Müşteri Kasası erişim isteğini onaylamanıza veya reddetmenize olanak tanır. Onaylarsanız mühendis verilere erişebilir. Her isteğin bir süre sonu vardır ve sorun çözüldükten sonra istek kapatılır ve erişim iptal edilir. Müşteri Kasası Office 365 Kurumsal 5 planına dahil edilir veya başka bir Office 365 Kurumsal planıyla ayrı bir abonelik satın alabilirsiniz. Daha fazla bilgi için bkz. [Office 365 Müşteri Kasası İstekleri](/microsoft-365/compliance/customer-lockbox-requests).

**Office 365 için Microsoft Defender:** Office 365 için Defender kuruluşunuzu kötü amaçlı yazılımlara ve virüslere karşı korumaya yardımcı olur. Office 365 için Defender [Güvenli Bağlantılar](/office365/securitycompliance/atp-safe-links), [Güvenli Ekler](/office365/securitycompliance/atp-safe-attachments), [Kimlik avı önleme](/office365/securitycompliance/atp-anti-phishing) ve [Kimlik sahtekarlığı zekası](/office365/securitycompliance/learn-about-spoof-intelligence) özelliklerini içerir. Office 365 için Defender hakkında daha fazla bilgi için bkz. [Office 365 için Microsoft Defender hizmet açıklaması](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

[**Güvenli Bağlantılar**](/office365/securitycompliance/atp-safe-links) **ve** [**Güvenli Ekler**](/office365/securitycompliance/atp-safe-attachments)**:** Güvenli Bağlantılar, kullanıcılarınızı iletideki kötü amaçlı köprülerden proaktif olarak korur ve bağlantı her seçildiğinde koruma sağlar. Güvenli Ekler bilinmeyen kötü amaçlı yazılımlara ve virüslere karşı koruma sağlar ve bilinen bir virüs/kötü amaçlı yazılım imzası olmayan tüm iletileri ve ekleri Office 365 için Defender kötü amaçlı amacı algıladığı özel bir ortama yönlendirir.

## <a name="product-use-rights"></a>Ürün kullanım hakları

**Microsoft Online Services ürün kullanım hakları:** Microsoft Çevrimiçi Abonelik Sözleşmenize uyuyorsanız, [lisanslama kaynakları ve belgeleri](https://www.microsoft.com/licensing/docs) altında açıkça izin verilen çevrimiçi hizmetler ve ilgili yazılımları kullanabilirsiniz.

**Office 365 21Vianet tarafından sağlanan ürün kullanım hakları:** [Bkz. 21Vianet Hizmet Düzeyi Sözleşmesi](https://go.microsoft.com/fwlink/?linkid=846729), [Çevrimiçi Hizmetler Standart Sözleşmesi](https://www.21vbluecloud.com/office365/O365-AgreeWebDir/) ve 21Vianet tarafından sağlanan Office 365 için [Kullanım Koşulları](https://www.21vbluecloud.com/office365/O365-TOU/). 21Vianet tarafından sağlanan Office 365 sadece Çin'de sunulan ve çalıştırılan bir hizmettir. Bu hizmet, Microsoft'un 21Vianet lisansına sahip olduğu teknolojiyle desteklenir. Daha fazla bilgi için bkz. [**21Vianet tarafından sağlanan Office 365 hakkında bilgi edinin**](/microsoft-365/admin/services-in-china/services-in-china?viewFallbackFrom=o365-worldwide).

**Lisans:** Kuruluşunuzun lisans programları hakkında bilgi edinmek için bkz. [Toplu Lisanslama](https://go.microsoft.com/fwlink/?LinkId=393693).

## <a name="service-level-agreement"></a>Hizmet düzeyi sözleşmesi

**Microsoft Online Services Düzey Sözleşmesi:** Her hizmet için hizmet düzeylerini elde etme ve koruma taahhüdümüze finansal destek sağlarız. Hizmet Düzeyi Sözleşmesi'nde açıklandığı gibi her hizmet için hizmet düzeylerini elde etmez ve korumazsak, aylık hizmet ücretlerinizin bir kısmına kredi almak için uygun olabilirsiniz. Hizmetlere yönelik Hizmet Düzeyi Sözleşmelerimiz hakkında daha fazla bilgi edinmek için [Microsoft Çevrimiçi Hizmetler için Hizmet Düzeyi Sözleşmesi'ni](https://go.microsoft.com/fwlink/?linkid=272026) indirin. Sistem çalışma zamanlarının yanı sıra güvenlik, gizlilik ve uyumluluk bilgileri hakkında genel bakış bilgileri için bkz. [Office 365 saydam işlemler](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).

**Hizmet güncelleştirmeleri:** Güncelleştirmeler ve yükseltmeler müşterilere coğrafya, dil, veri merkezi ve abonelik gibi birçok faktöre göre dağıtılır. Bu, tüm güncelleştirmelerin mevcut müşteriler tarafından hemen kullanılamadığı anlamına gelir. Yeni yayımlanan veya kullanıma sunulmak üzere olan özellikler hakkında bilgi edinmek için [Microsoft 365 Yol Haritası'na](https://go.microsoft.com/fwlink/?LinkId=509914) göz atın. Bu konu, 21Vianet tarafından sağlanan Office 365 için geçerli değildir. Hizmet güncelleştirmeleri hakkında bilgi edinmek için bkz. [**21Vianet tarafından sağlanan Office 365 için teknik, faturalama ve abonelik desteği alma**](/microsoft-365/admin/contact-support-for-business-products).

**Hedeflenen sürüm:** Hedefli sürüm ile, kuruluşunuz veya kullanıcılarınızdan oluşan bir grup, standart sürüm sürecimize başlamadan yaklaşık bir hafta önce belirli bir hizmet güncelleştirmeleri kümesi alır. Daha fazla bilgi için bkz. [Microsoft sürüm seçenekleri](/office365/admin/manage/release-options-in-office-365).

**Güncelleştirme bildirimleri:** Microsoft, yöneticinin hizmetin normal çalışmasını sağlamak için işlem gerçekleştirmesini gerektiren herhangi bir değişikliği müşterilere önceden bildirmeye çalışır. Aksi belirtilmediği sürece Microsoft, bir güncelleştirmenin yönetici eylemi gerektirebileceği durumlarda [İleti Merkezi](/office365/admin/manage/message-center) aracılığıyla en az 30 gün gelişmiş bildirim sağlar. Hizmet güncelleştirmelerinin çoğu müşteri adına sıfır eylem gerektiren hata düzeltmeleri, performans iyileştirmeleri ve güvenlik güncelleştirmeleridir. İş [için Microsoft 365 yol haritasında](https://roadmap.office.com/) yeni ve geliştirilmiş özellikler bulunur. Microsoft [, Çevrimiçi Yaşam Döngüsü İlkesi'ni izler](https://support.microsoft.com/lifecycle#gp/osslpolicy).

---

**Özellik kullanılabilirliği:** Planlarda özellik kullanılabilirliğini görüntülemek için bkz. [Microsoft 365 ve Office 365 platform hizmeti açıklaması](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description).
