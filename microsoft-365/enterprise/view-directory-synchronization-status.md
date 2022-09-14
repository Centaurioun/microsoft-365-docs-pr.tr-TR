---
title: Microsoft 365'te dizin eşitleme durumunu görüntüleme
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: Bu makalede, Office 365'da dizin eşitlemenizin durumunu nasıl denetleyeceğinizi öğrenin.
ms.openlocfilehash: 050c4f4abfb8e4d925af3d65117d6c9ae8cb26e7
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670487"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Microsoft 365'te dizin eşitleme durumunu görüntüleme

Şirket içi ortamınızı Microsoft 365 ile eşitleyerek şirket içi Active Directory Etki Alanı Hizmetlerinizi (AD DS) Azure Active Directory (Azure AD) ile tümleştirdiyseniz, eşitlemenizin durumunu da de kontrol edebilirsiniz.
  
## <a name="view-directory-synchronization-status"></a>Dizin eşitleme durumunu görüntüleme

- [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın ve giriş sayfasında **DirSync Durumu'nu** seçin.
- Alternatif olarak, **Kullanıcılar** \> **Etkin kullanıcılar'a** gidebilir ve **Etkin kullanıcılar** sayfasında **Elipse** \> **Directory eşitlemesini** seçebilirsiniz. **Dizin Eşitleme** bölmesinde **DirSync yönetimine git'i** seçin.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Dizin eşitlemesini yönet sayfasındaki bilgiler

Aşağıdaki tabloda, sayfada hakkında bilgi alabileceğiniz özellikler listelenmiştir.
  
Dizin eşitlemenizle ilgili bir sorun varsa, hatalar bu sayfada da listelenir. Karşılaşabileceğiniz farklı hatalar hakkında daha fazla bilgi için bkz. [Microsoft 365'te dizin eşitleme hatalarını tanımlama](identify-directory-synchronization-errors.md).
  
|Öğe|Kullanım amacı|
|:-----|:-----|
|**Doğrulanan etki alanları** | Microsoft 365 kiracınızda sahip olduğunuzu doğruladığınız etki alanı sayısı. |
|**Etki alanları doğrulanmadı** | Eklediğiniz ancak doğrulanmamış etki alanları. |
|**Dizin eşitleme etkin** |Doğru veya Yanlış. Dizin eşitlemeyi etkinleştirip etkinleştirmediğiniz belirtir. |
|**En son dizin eşitleme** | Dizin eşitlemenin son çalıştırışı. Son eşitleme üç günden uzun bir süre önceyse bir uyarı ve sorun giderme aracının bağlantısını görüntüler. |
|**Parola eşitleme etkin** | Doğru veya Yanlış. Şirket içi ile Microsoft 365 kiracınız arasında parola karması eşitlemesi yapıp yapmadığınızı belirtir. |
|**Son Parola Eşitleme** | Parola karması eşitlemenin son çalıştırışı. Son eşitleme üç günden uzun bir süre önceyse bir uyarı ve sorun giderme aracının bağlantısını görüntüler. |
|**Dizin eşitleme istemcisi sürümü** | Azure AD Connect'in yeni bir sürümü yayımlandıysa bir indirme bağlantısı içerir. |
|**Dizin eşitleme hizmeti hesabı** | Microsoft 365 dizin eşitleme hizmeti hesabınızın adını görüntüler. |
|||

## <a name="monitor-synchronization-health"></a>Eşitleme durumunu izleme

Bu bölümde, kimlik altyapınızı ve Azure AD Connect tarafından sağlanan eşitleme hizmetlerini izlemek için şirket içi AD DS etki alanı denetleyicilerinizin her birine bir Azure AD Connect Health aracısı yükleyeceksiniz. İzleme bilgileri, uyarıları, performans izlemeyi, kullanım analizini ve diğer bilgileri görüntüleyebileceğiniz bir Azure AD Connect Health portalında sağlanır.

Azure AD Connect Health'in nasıl kullanılacağına ilişkin temel tasarım kararı, Azure AD Connect'i nasıl kullandığınıza bağlıdır:

- **Yönetilen kimlik doğrulama** seçeneğini kullanıyorsanız connect health Azure AD anlamak ve yapılandırmak için [Eşitleme ile Azure AD Connect Health'i kullanma](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) ile başlayın.
- Active Directory Federasyon Hizmetleri (AD FS) (AD FS) ile **federasyon kimlik doğrulamasını** kullanarak hesapların ve grupların yalnızca adlarını eşitlerseniz, Azure AD Connect Health'i anlamak ve yapılandırmak için [AD FS ile Azure AD Connect Health kullanma](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) ile başlayın.

Tamamlandığında şunları yapacaksınız:

- Şirket içi kimlik sağlayıcısı sunucularınızda yüklü Azure AD Connect Health aracısı.
- Microsoft 365 aboneliğinizin Azure AD kiracısıyla şirket içi altyapınızın ve eşitleme etkinliklerinizin geçerli durumunu görüntüleyen Azure AD Connect Health portalı.
