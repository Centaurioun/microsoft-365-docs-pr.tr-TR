---
title: Microsoft 365 ile Azure tümleştirmesi
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Parola eşitleme veya şirket içi ortamınızla çoklu oturum açma istiyorsanız Microsoft 365'i Azure AD ile tümleştirin.
ms.openlocfilehash: 9369437e556e3faf1691c2af513ace846e0ad944
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68209304"
---
# <a name="azure-integration-with-microsoft-365"></a>Microsoft 365 ile Azure tümleştirmesi

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft 365, arka planda kullanıcı kimliklerini yönetmek için Azure Active Directory (Azure AD) kullanır. Microsoft 365 aboneliğiniz, kullanıcı hesaplarını ve parolaları eşitlemek veya çoklu oturum açmayı ayarlamak için şirket içi Active Directory Etki Alanı Hizmetlerinizi (AD DS) tümleştirebilmeniz için ücretsiz bir Azure AD aboneliği içerir. Ayrıca hesaplarınızı daha iyi yönetmek için gelişmiş özellikler de satın alabilirsiniz.
  
Azure AD, Microsoft 365 aboneliklerinizi genişletmek ve özelleştirmek için kullanabileceğiniz tümleşik uygulamaları yönetme gibi başka işlevler de sunar.
  
Microsoft 365 yönetim merkezi destekli kurulum ve yapılandırma deneyimi için Azure AD dağıtım danışmanlarını kullanabilirsiniz (Microsoft 365'te oturum açmanız gerekir):

 - [Azure AD Connect danışmanı](https://aka.ms/aadconnectpwsync)
 - [AD FS dağıtım danışmanı](https://aka.ms/adfsguidance)
 - [kurulum kılavuzunu Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD sürümleri ve Microsoft 365 kimlik yönetimi

Ücretli Microsoft 365 aboneliğiniz varsa, ücretsiz bir Azure AD aboneliğiniz de vardır. Kullanıcı ve grup hesaplarını oluşturmak ve yönetmek için Azure AD kullanabilirsiniz. Bu aboneliği etkinleştirmek için tek seferlik bir kaydı tamamlamanız gerekir. Daha sonra Microsoft 365 yönetim merkezi Azure AD erişebilirsiniz. 

Ücretsiz Azure AD aboneliğinizi kaydetme yönergeleri için bkz. [Ücretsiz Azure AD aboneliğinizi kullanma](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Kaydolmak için doğrudan azure.microsoft.com gitmeyin; microsoft 365 ile ücretsiz Azure AD aboneliğinizden ayrı bir Microsoft Azure deneme veya ücretli aboneliğiniz olur. 
  
Ücretsiz abonelikle şirket içi dizinlerle eşitleme yapabilir, çoklu oturum açmayı ayarlayabilir ve Salesforce, DropBox gibi birçok hizmet uygulaması olarak yazılımla eşitleyebilirsiniz.
  
Gelişmiş AD DS işlevselliği, çift yönlü eşitleme ve diğer yönetim özelliklerini istiyorsanız ücretsiz aboneliğinizi ücretli premium aboneliğe yükseltebilirsiniz. Ayrıntılar için bkz. [Azure Active Directory sürümleri](https://azure.microsoft.com/pricing/details/active-directory/).
  
Microsoft 365 ve Azure AD hakkında daha fazla bilgi için bkz. [Microsoft 365 kimlik modelleri](deploy-identity-solution-identity-model.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Microsoft 365 kiracınızın özelliklerini genişletme

|**Özellik**|**Açıklama**|
|:-----|:-----|
|Tümleşik uygulamalar  <br/> |Posta, takvimler, kişiler, kullanıcılar, gruplar, dosyalar ve klasörler gibi tek tek uygulamalara Microsoft 365 verilerinize erişim izni vekleyebilirsiniz. Ayrıca bu uygulamaları **Azure AD DC yöneticisi** veya **Genel yönetici** düzeyinde yetkilendirilebilir ve uygulamaları Azure AD kaydederek tüm şirketinizin kullanımına sunabilirsiniz. Daha fazla bilgi için bkz. [Microsoft 365 yöneticileri için Tümleşik Uygulamalar ve Azure AD](integrated-apps-and-azure-ads.md).<br/> Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](/microsoft-365/admin/add-users/about-admin-roles?). <br/> Ayrıca bkz. [Çoklu oturum açma](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|Power Apps  <br/> | Power Apps, SharePoint listeleri ve diğer veri uygulamaları gibi mevcut veri kaynaklarınıza bağlanabilen mobil cihazlar için odaklanmış uygulamalardır. Ayrıntılar [için bkz. SharePoint Online'da liste için Power App oluşturma](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) ve [Power Apps sayfası](https://powerapps.microsoft.com/) .  <br/> |
   
## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Kurumsal genel bakış](microsoft-365-overview.md)
