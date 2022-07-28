---
title: İzin Verme İzinlerini Algılama ve Düzeltme
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.date: 07/28/2022
ms.localizationpriority: medium
search.appverid:
- MET150
description: Microsoft 365'te yasadışı onay verme saldırısını tanımayı ve düzeltmeyi öğrenin.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 354e32ca01a17be69f0bb144a437fd3e825613ea
ms.sourcegitcommit: 1e53bf8208c30d7b60685896207cc1142bebf34a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2022
ms.locfileid: "67059721"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>İzin Verme İzinlerini Algılama ve Düzeltme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Özet**  Microsoft 365'te yasadışı onay verme saldırısını tanımayı ve düzeltmeyi öğrenin.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>Microsoft 365'te yasadışı izin verme saldırısı nedir?

Yasadışı bir onay verme saldırısında, saldırgan kişi bilgileri, e-posta veya belgeler gibi verilere erişim isteyen Azure'a kayıtlı bir uygulama oluşturur. Saldırgan daha sonra bir son kullanıcıyı, bir kimlik avı saldırısı yoluyla veya güvenilir bir web sitesine yasadışı kod ekleyerek bu uygulamaya verilerine erişim izni vermesi için numaralar. Yasadışı uygulamaya onay verildikten sonra, kuruluş hesabına gerek kalmadan verilere hesap düzeyinde erişime sahip olur. Parolaları ihlal edilen hesaplar için sıfırlama veya hesaplarda Multi-Factor Authentication (MFA) gerektirme gibi normal düzeltme adımları, bu tür saldırılara karşı etkili değildir, çünkü bunlar üçüncü taraf uygulamalardır ve kuruluş dışındadır.

Bu saldırılar, bilgileri çağıran varlığın insan değil otomasyon olduğunu varsayan bir etkileşim modelinden yararlanmaktadır.

> [!IMPORTANT]
> Şu anda bir uygulamadan gelen yasadışı onay vermelerle ilgili sorun yaşadığınızdan mı şüpheleniyorsunuz? Microsoft Defender for Cloud Apps, OAuth uygulamalarınızı algılamak, araştırmak ve düzeltmek için araçlar içerir. Bu Bulut Uygulamaları için Defender makalesinde [, riskli OAuth uygulamalarını araştırma hakkında](/cloud-app-security/investigate-risky-oauth) nasıl gidildiğini gösteren bir öğretici yer alır. Ayrıca, uygulama tarafından istenen izinleri araştırmak, bu uygulamaları hangi kullanıcıların yetkilendirdiği ve bu izin isteklerini geniş çapta onaylamak veya yasaklamak için [OAuth uygulama ilkeleri](/cloud-app-security/app-permission-policy) ayarlayabilirsiniz.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>Microsoft 365'te yasadışı onay verme saldırısı nasıl görünür?

Bu saldırının Risk Altındaki Göstergeler (IOC) olarak da adlandırılan işaretlerini bulmak için **denetim günlüğünde** arama yapmanız gerekir. Birçok Azure kayıtlı uygulaması ve büyük bir kullanıcı tabanı olan kuruluşlar için en iyi yöntem, kuruluşlarına verdiğiniz onayları haftalık olarak gözden geçirmektir.

### <a name="steps-for-finding-signs-of-this-attack"></a>Bu saldırının işaretlerini bulma adımları

1. adresinden Microsoft 365 Defender portalını açın ve **Ardından Denetim'i**<https://security.microsoft.com> seçin. Alternatif olarak, doğrudan **Denetim** sayfasına gitmek için <https://security.microsoft.com/auditlogsearch> seçeneğini kullanın.

2. **Denetim** sayfasında **Ara** sekmesinin seçili olduğunu doğrulayın ve ardından aşağıdaki ayarları yapılandırın:
   - **Tarih ve saat aralığı**
   - **Etkinlikler**: **Tüm etkinlikler için sonuçları göster** seçeneğinin belirlendiğini doğrulayın.

   Bitirdiğinizde, **Ara**'yı tıklayın.

3. Sonuçları sıralamak için **Etkinlik** sütununa tıklayın ve **Uygulamaya onay ver'i** arayın.

4. Etkinliğin ayrıntılarını görmek için listeden bir girdi seçin. IsAdminConsent değerinin True olarak ayarlandığını denetleyin.

> [!NOTE]
>
> Bir olay oluştuktan sonra ilgili denetim günlüğü girişinin arama sonuçlarında görüntülenmesi 30 dakikadan 24 saate kadar sürebilir.
>
> Denetim kaydının tutulup denetim günlüğünde aranabilir olması, Microsoft 365 aboneliğinize ve özellikle belirli bir kullanıcıya atanan lisansın türüne bağlıdır. Daha fazla bilgi için bkz [. Denetim günlüğü](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Bu değer doğruysa, Genel Yönetici erişimi olan birinin verilere geniş erişim vermiş olabileceğini gösterir. Bu beklenmeyen bir durumsa [, bir saldırıyı onaylamak](#how-to-confirm-an-attack) için gereken adımları uygulayın.

## <a name="how-to-confirm-an-attack"></a>Saldırıyı onaylama

Yukarıda listelenen GÇ'lerin bir veya daha fazla örneğine sahipseniz, saldırının gerçekleştiğini olumlu bir şekilde onaylamak için daha fazla araştırma yapmanız gerekir. Saldırıyı onaylamak için bu üç yöntemden herhangi birini kullanabilirsiniz:

- Azure Active Directory portalını kullanarak uygulamaların ve izinlerinin envanterini oluşturun. Bu yöntem kapsamlıdır, ancak bir kerede yalnızca bir kullanıcıyı denetleyebilirsiniz ve bu da denetlemeniz gereken çok fazla kullanıcı varsa çok zaman alabilir.
- PowerShell kullanarak uygulamaların ve izinlerinin envanterini oluşturun. Bu en hızlı ve en kapsamlı yöntemdir ve ek yük en azdır.
- Kullanıcılarınızın uygulamalarını ve izinlerini tek tek denetlemesini ve sonuçları düzeltme için yöneticilere geri bildirmesini sağlayın.

## <a name="inventory-apps-with-access-in-your-organization"></a>Kuruluşunuzda erişimi olan envanter uygulamaları

Azure Active Directory Portalı veya PowerShell ile kullanıcılarınız için bunu yapabilir veya kullanıcılarınızın uygulama erişimlerini ayrı ayrı listelemesini sağlayabilirsiniz.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory Portalını kullanma adımları

Konumundaki Azure Active Directory Portalını <https://portal.azure.com>kullanarak tek tek herhangi bir kullanıcının izin verdiği uygulamaları arayabilirsiniz.

1. yönetim haklarıyla Azure portal oturum açın.
2. Azure Active Directory dikey penceresini seçin.
3. **Kullanıcılar**’ı seçin.
4. Gözden geçirmek istediğiniz kullanıcıyı seçin.
5. **Uygulamalar**’ı seçin.

Bu, kullanıcıya atanan uygulamaları ve uygulamaların sahip olduğu izinleri gösterir.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Kullanıcılarınızın uygulama erişimlerini listelemesini sağlama adımları

Kullanıcılarınızın oraya gidip <https://myapps.microsoft.com> kendi uygulama erişimini gözden geçirmesini sağlayın. Erişimi olan tüm uygulamaları görebilmeli, bunlarla ilgili ayrıntıları görüntüleyebilmeli (erişim kapsamı dahil) ve şüpheli veya yasadışı uygulamaların ayrıcalıklarını iptal edebilmelidir.

### <a name="steps-for-doing-this-with-powershell"></a>Bunu PowerShell ile gerçekleştirme adımları

Yasadışı Onay Verme saldırısını doğrulamanın en basit yolu [ , kiracınızdaki ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)tüm kullanıcılar için tüm OAuth onaylarının ve OAuth uygulamalarının tek bir .csv dosyasına dökümünü alanGet-AzureADPSPermissions.ps1çalıştırmaktır.

#### <a name="pre-requisites"></a>Önkoşullar

- Azure AD PowerShell kitaplığı yüklü.
- Kiracıda betiğin çalıştırılacağı hakları Genel yönetici.
- Betiklerin çalıştırılacağı bilgisayarda Yerel Yönetici.

> [!IMPORTANT]
> Yönetim hesabınızda çok faktörlü kimlik doğrulaması gerektirmenizi ***kesinlikle öneririz*** . Bu betik MFA kimlik doğrulamayı destekler.

1. Betiği çalıştıracağınız bilgisayarda yerel yönetici haklarıyla oturum açın.

2. [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) betiğini GitHub'dan betiği çalıştıracağınız klasöre indirin veya kopyalayın. Bu, çıkış "permissions.csv" dosyasının yazılacağı klasör olacaktır.

3. Yönetici olarak bir PowerShell oturumu açın ve betiği kaydettiğiniz klasörü açın.

4. [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet'ini kullanarak dizininize bağlanın.

5. Şu PowerShell komutunu çalıştırın:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Betik, Permissions.csv adlı bir dosya oluşturur. Yasadışı uygulama izni vermek için şu adımları izleyin:

1. ConsentType sütununda (G sütunu) "AllPrinciples" değerini arayın. AllPrincipals izni, istemci uygulamasının kiracıdaki herkesin içeriğine erişmesini sağlar. Yerel Microsoft 365 uygulamalarının düzgün çalışması için bu izne sahip olması gerekir. Bu izne sahip Microsoft olmayan her uygulama dikkatle gözden geçirilmelidir.

2. İzin sütununda (F sütunu), temsilci olarak atanan her uygulamanın içerik için sahip olduğu izinleri gözden geçirin. "Okuma" ve "Yazma" iznini veya "Tümü" iznini arayın ve uygun olmayabilecekleri için bunları dikkatle gözden geçirin.

3. İzin verilen belirli kullanıcıları gözden geçirin. Yüksek profilli veya yüksek etkili kullanıcıların uygun olmayan onayları varsa daha fazla araştırmanız gerekir.

4. ClientDisplayName sütununda (C sütunu) şüpheli görünen uygulamaları arayın. Yanlış yazılmış adlar, süper kötü adlar veya bilgisayar korsanı gibi adlara sahip uygulamalar dikkatle gözden geçirilmelidir.

## <a name="determine-the-scope-of-the-attack"></a>Saldırının kapsamını belirleme

Uygulama erişiminin envanterini çıkardıktan sonra, ihlalin tam kapsamını belirlemek için **denetim günlüğünü** gözden geçirin. Etkilenen kullanıcıları, yasadışı uygulamanın kuruluşunuza erişimi olan zaman çerçevelerini ve uygulamanın sahip olduğu izinleri arayın. [Microsoft 365 Defender portalında](../../compliance/search-the-audit-log-in-security-and-compliance.md) **denetim günlüğünde** arama yapabilirsiniz.

> [!IMPORTANT]
> Bu bilgileri alabilmeniz için, posta [kutusu denetimi](../../compliance/enable-mailbox-auditing.md) [ve Yöneticiler ve kullanıcılar için Etkinlik denetimi](../../compliance/turn-audit-log-search-on-or-off.md) saldırıdan önce etkinleştirilmiş olmalıdır.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Yasadışı onay verme saldırısını durdurma ve düzeltme

Yasadışı izinlere sahip bir uygulama belirledikten sonra, bu erişimi kaldırmanın çeşitli yolları vardır.

- Uygulamanın iznini Azure Active Directory Portalı'nda şu şekilde iptal edebilirsiniz:
  1. **Azure Active Directory Kullanıcısı** dikey penceresinde etkilenen kullanıcıya gidin.
  2. **Uygulamalar**’ı seçin.
  3. Yasadışı uygulamayı seçin.
  4. Detaya gitmede **Kaldır'a** tıklayın.

- [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant) içindeki adımları izleyerek PowerShell ile OAuth onay verme işlemini iptal edebilirsiniz.

- [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment) içindeki adımları izleyerek PowerShell ile Hizmet Uygulaması Rol Atamasını iptal edebilirsiniz.

- Ayrıca etkilenen hesap için oturum açmayı tamamen devre dışı bırakabilirsiniz ve bu da bu hesaptaki verilere uygulama erişimini devre dışı bırakır. Bu, elbette son kullanıcının üretkenliği için ideal değildir, ancak etkiyi hızla sınırlamak için çalışıyorsanız, bu uygun bir kısa vadeli düzeltme olabilir.

- Kiracınız için tümleşik uygulamaları kapatabilirsiniz. Bu, son kullanıcıların kiracı genelinde onay verme yeteneğini devre dışı bırakmaya yönelik sert bir adımdır. Bu, kullanıcılarınızın yanlışlıkla kötü amaçlı bir uygulamaya erişim izni vermelerini engeller. Kullanıcılarınızın üçüncü taraf uygulamalarla üretken olma becerisini ciddi ölçüde bozarken bu kesinlikle önerilmez. Bunu yapmak için [Tümleşik Uygulamaları Açma veya Kapatma'daki adımları izleyebilirsiniz](../../admin/misc/user-consent.md).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365'i bir siber güvenlik uzmanı gibi güvenli bir şekilde sağlama

Microsoft 365 aboneliğiniz, verilerinizi ve kullanıcılarınızı korumak için kullanabileceğiniz güçlü bir güvenlik özellikleri kümesiyle birlikte gelir. Microsoft 365 kiracınızın güvenliğini sağlamak için Microsoft tarafından önerilen en iyi yöntemleri uygulamak [için Microsoft 365 güvenlik yol haritası - İlk 30 gün, 90 gün ve sonrasındaki en önemli öncelikleri](security-roadmap.md) kullanın.

- İlk 30 günde gerçekleştirecek görevler. Bunlar hemen etkili olur ve kullanıcılarınız için düşük etkiye sahiptir.
- 90 gün içinde gerçekleştirecek görevler. Bunların planlanıp uygulanması biraz daha zaman alır ancak güvenlik duruşunuzu büyük ölçüde geliştirir.
- 90 günden fazla. Bu geliştirmeler ilk 90 günlük çalışmanızda derlemektedir.

## <a name="see-also"></a>Ayrıca bkz.

- [Uygulamalarım listesindeki beklenmeyen uygulama](/azure/active-directory/application-access-unexpected-application) , yöneticilere verilere erişimi olan beklenmeyen uygulamalar olduğunu fark ettikten sonra yapmak isteyebilecekleri çeşitli eylemlerde yol gösteriyor.
- [Uygulamaları Azure Active Directory ile tümleştirmek](/azure/active-directory/active-directory-apps-permissions-consent) , onay ve izinlere üst düzey bir genel bakıştır.
- [Uygulamamı geliştirme sorunları](/azure/active-directory/active-directory-application-dev-development-content-map) , onayla ilgili çeşitli makalelerin bağlantılarını sağlar.
- [Azure Active Directory'deki (Azure AD) uygulama ve hizmet sorumlusu nesneleri](/azure/active-directory/develop/active-directory-application-objects), uygulama modelinin temeli olan Uygulama ve Hizmet sorumlusu nesnelerine genel bir bakış sağlar.
- [Uygulamalara erişimi yönetme](/azure/active-directory/active-directory-managing-access-to-apps) , yöneticilerin uygulamalara kullanıcı erişimini yönetmek için sahip olduğu özelliklere genel bir bakıştır.
