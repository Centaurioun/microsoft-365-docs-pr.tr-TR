---
title: Ekipleri temel koruma ile yapılandırma
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- highpri
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
- admindeeplinkTEAMS
- admindeeplinkSPO
recommendations: false
description: Temel koruma düzeyine sahip ekipleri dağıtmayı öğrenin.
ms.openlocfilehash: 253e384f87b7251bb15425b211036a7853eeefb4
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67987268"
---
# <a name="configure-teams-with-baseline-protection"></a>Ekipleri temel koruma ile yapılandırma

Bu makalede, temel koruma düzeyine sahip ekiplerin nasıl dağıtılacağına bakacağız. Bu düzey, kullanıcılara izin yönetimini geliştirirken ve aşırı paylaşıma karşı temel koruma sağlarken işbirliği için çok çeşitli seçenekler sunar. Bu düzey için önerilen korumalar arasında kimlik ve cihaz erişim ilkeleri ile kötü amaçlı yazılımlara karşı koruma yer alır. Ayrıca, gerektiğinde koşullu erişim ilkeleri ve veri kaybı korumaları uygulayabilirsiniz.

## <a name="initial-protections"></a>İlk korumalar

İlk adım olarak, temel kimlik ve cihaz erişim ilkelerini yapılandırmanızı öneririz. Ayrıntılar için bkz. [Teams sohbetlerinin, gruplarının ve dosyalarının güvenliğini sağlamak için ilke önerileri](../security/office-365-security/teams-access-policies.md) .

Ayrıca belgelerde, eklerde ve bağlantılarda kötü amaçlı yazılımlara karşı koruma sağlamak için temel Office 365 için Defender özelliklerini açmanızı öneririz. Aşağıdaki tabloda yer alan seçeneklerin her birini açmanızı öneririz.

|Seçeneği|Bilgi|
|:------|:-----------|
|SPO, OneDrive ve Teams için Güvenli Ekler|[Güvenli Ekleri Kaydetme](../security/office-365-security/safe-attachments.md) <p> [Office 365 için Defender - SharePoint, OneDrive ve Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|Güvenli Belgeler|[Office 365 için Microsoft Defender'da Güvenli Belgeler](../security/office-365-security/safe-docs.md)|
|Teams için Güvenli Bağlantılar|[Teams'de Güvenli Bağlantıları Office 365](../security/office-365-security/safe-links.md) <p> [Güvenli Bağlantılar](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a>Teams konuk paylaşımı

Katmanların her birinde, kuruluşunuzun dışındaki kişilerle paylaşma seçeneğiniz vardır. Hassas ve son derece hassas katmanlar için duyarlılık etiketlerini kullanarak ekip düzeyinde konuk paylaşımını kapatma seçeneğine sahip olacağız. Ancak Teams'de konuk paylaşımının çalışması için kuruluş düzeyinde konuk paylaşımı ayarının açık olması gerekir.

![Teams konuk erişimi iki durumlu düğmesinin ekran görüntüsü.](../media/teams-guest-access-toggle-on.png)

Teams konuk erişim ayarlarını ayarlamak için

1. konumundaki Microsoft 365 yönetim merkezi oturum [https://admin.microsoft.com](https://admin.microsoft.com)açın.
2. Sol gezinti bölmesinde **Tümünü göster'e** tıklayın.
3. **Yönetici merkezleri'nin** altında **Teams'e** tıklayın.
4. Teams yönetim merkezinde, sol gezinti bölmesinde **Kuruluş genelinde ayarlar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Konuk erişimi'ni**</a> genişletin.
5. **Teams'de konuk erişimine izin ver seçeneğinin** **Açık** olarak ayarlandığından emin olun.
6. Ek konuk ayarlarında istediğiniz değişiklikleri yapın ve **kaydet'e** tıklayın.

> [!NOTE]
> Teams konuk ayarını açtıktan sonra etkin hale gelmesi yirmi dört saat kadar sürebilir.

Konuk paylaşımı, Office 365 grupları ve SharePoint için varsayılan olarak açıktır, ancak kuruluşunuz için konuk paylaşım ayarlarından herhangi birini daha önce değiştirdiyseniz, Teams'de konuk paylaşımının kullanılabilir olduğundan emin olmak için [Ekipteki konuklarla işbirliği](./collaborate-as-team.md) yapma bölümünü gözden geçirmenizi öneririz.

## <a name="site-and-file-sharing"></a>Site ve dosya paylaşımı

Kuruluşunuz dışındaki kişilerle yanlışlıkla dosya veya klasör paylaşma riskini azaltmak için SharePoint için varsayılan paylaşım bağlantısını *Yalnızca kuruluşunuzdaki kişiler olarak değiştirmenizi* öneririz. (Kullanıcıların harici olarak paylaşması gerekiyorsa ve konuk paylaşımını etkinleştirdiyseniz, paylaşım yaptıklarında bağlantı türünü değiştirebilirler.)

Varsayılan paylaşım bağlantısını değiştirmek için

1. SharePoint yönetim merkezini açın, **İlkeler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
1. **Dosya ve klasör** **bağlantıları'nın altında Yalnızca kuruluşunuzdaki kişiler'i** seçin.
1. **Kaydet**'i seçin.

En iyi konuk paylaşımı deneyimi için, [Azure AD B2B ile SharePoint ve OneDrive tümleştirmesini](/sharepoint/sharepoint-azureb2b-integration-preview) etkinleştirmenizi de öneririz.

## <a name="create-a-team"></a>Ekip oluşturma

Temel koruma düzeyi için ek yapılandırma, bir ekiple ilişkilendirilmiş SharePoint sitesinde yapılır. Sonraki bölüme geçmeden önce [genel veya özel bir ekip oluşturun](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

## <a name="site-sharing-settings"></a>Site paylaşım ayarları

Varsayılan olarak, SharePoint sitesinin üyeleri başkalarını siteye davet edebilir. Site bir ekibin parçası olduğunda, ekip üyeleri site üyesi olarak dahil edilir. Ancak doğrudan siteye eklenen kişilerin ekibin geri kalanına erişimi yoktur. Bu nedenle, izinleri yalnızca ekip aracılığıyla yönetmenizi öneririz.

İzin yönetimine yardımcı olmak için, ilişkili siteyi yalnızca sahiplerin siteyi tek başına paylaşmasına izin verecek şekilde yapılandırmanızı öneririz. Bu, izin yönetimini basitleştirir ve ekip sahibinin bilgisi olmayan kişilerin erişimini engellemeye yardımcı olur. Temel koruma gerektiren her ekip için bunu yapın.

Site paylaşım ayarlarını güncelleştirmek için
1. Ekibin araç çubuğunda **Dosyalar'a** tıklayın.
2. **SharePoint'te Aç'a** tıklayın.
3. SharePoint sitesinin araç çubuğunda ayarlar simgesine ve ardından **Site izinleri'ne** tıklayın.
4. **Site izinleri** bölmesinde, **Site paylaşımı'nın** altında Üyelerin **paylaşım şeklini değiştir'e** tıklayın.
5. **Paylaşım izinleri'nin** altında **Site sahipleri ve üyeleri'ni seçin ve Düzenleme izinleri olan kişiler dosya ve klasörleri paylaşabilir, ancak siteyi yalnızca site sahipleri paylaşabilir** ve kaydet'e tıklayın.

## <a name="additional-protections"></a>Ek korumalar

Microsoft 365, içeriğinizin güvenliğini sağlamak için ek yöntemler sunar. Aşağıdaki seçeneklerin kuruluşunuzun güvenliğini artırmaya yardımcı olup olmadığını göz önünde bulundurun.

- Konukların [kullanım koşullarını kabul etmelerini](/azure/active-directory/conditional-access/terms-of-use) sağlayın.
- Konuklar için [oturum zaman aşımı ilkesi](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) yapılandırın.
- [Hassas bilgi türleri oluşturun ve hassas bilgilere](../compliance/sensitive-information-type-learn-about.md) erişimle ilgili ilkeler ayarlamak için [veri kaybı koruması](../compliance/dlp-learn-about-dlp.md) kullanın.

## <a name="see-also"></a>Ayrıca Bkz

[Teams'de toplantı ilkelerini yönetme](/microsoftteams/meeting-policies-in-teams)

[İçeriden risk yönetimini kullanmaya başlama](../compliance/insider-risk-management-configure.md)