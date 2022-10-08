---
title: Etki alanı kullanıcılarını Microsoft 365 ile eşitleme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Etki alanı denetimli kullanıcıları İş için Microsoft 365 ile eşitleyin.
ms.openlocfilehash: 30bb3d5196ec5aec0d9ddb178e961781f51a7ef9
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166295"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Etki alanı kullanıcılarını Microsoft 365 ile eşitleme

## <a name="1-prepare-for-directory-synchronization"></a>1. Dizin Eşitleme için Hazırlanma 

Kullanıcılarınızı ve bilgisayarlarınızı yerel Active Directory Etki Alanı eşitlemeden önce [Microsoft 365'e dizin eşitlemesi için hazırlanma makalesini](../../enterprise/prepare-for-directory-synchronization.md) gözden geçirin. Özellikle:

   - Dizininizde şu öznitelikler için yineleme olmadığından emin olun: **mail**, **proxyAddresses** ve **userPrincipalName**. Bu değerler benzersiz olmalı ve yinelenen öğeler kaldırılmalıdır.
   
   - Her yerel kullanıcı hesabı için **userPrincipalName** (UPN) özniteliğini lisanslı Microsoft 365 kullanıcısına karşılık gelen birincil e-posta adresiyle eşleşecek şekilde yapılandırmanızı öneririz. Örneğin: *mary@contoso.local yerine mary.shelley@contoso.com* 
   
   - Active Directory etki alanı .*com* veya .*org* gibi bir internet yönlendirilebilir soneki yerine *.local* veya *.lan* gibi yönlendirilebilir olmayan bir soneki ile bitiyorsa, yerel kullanıcı hesaplarının UPN sonekini önce [Dizin eşitlemesi için yönlendirilebilir olmayan bir etki alanı hazırlama](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) bölümünde açıklandığı gibi ayarlayın. 

Aşağıdaki dördüncü (4) adımdaki **IdFix'i çalıştır**, şirket içi Active Directory dizin eşitlemesi için hazır olduğundan da emin olur.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect'i yükleme ve yapılandırma

Kullanıcılarınızı, gruplarınızı ve kişilerinizi yerel Active Directory'den Azure Active Directory'ye eşitlemek için Azure Active Directory Connect'i yükleyin ve dizin eşitlemesini ayarlayın. 

 1. [Yönetim merkezinde](https://go.microsoft.com/fwlink/p/?linkid=2024339) sol gezinti bölmesinde **Kurulum'u** seçin.

 2. **Oturum açma ve güvenlik bölümünde** **Kullanıcıları Microsoft hesabınıza ekle veya eşitle'yi** seçin.

 3. **Microsoft hesabınıza kullanıcı ekleme veya eşitleme** sayfasında **Başlarken'i** seçin.

 4. dizin eşitlemeye hazırlanmak için ilk adımda IdFix aracını çalıştırın.

 5. Azure AD Connect'i indirmek için sihirbaz adımlarını izleyin ve etki alanı denetimli kullanıcılarınızı Microsoft 365 ile eşitlemek için kullanın.


Daha fazla bilgi edinmek için bkz. [Microsoft 365 için dizin eşitlemesini ayarlama](../../enterprise/set-up-directory-synchronization.md) .

Azure AD Connect seçeneklerinizi yapılandırdığınızda, İş için Microsoft 365'te de desteklenen **Parola Eşitleme**, **Sorunsuz Çoklu Oturum Açma** ve **parola geri yazma** özelliğini etkinleştirmenizi öneririz.

> [!NOTE]
> Azure AD Connect'teki onay kutusunun ötesinde parola geri yazma için bazı ek adımlar vardır. Daha fazla bilgi için bkz. [Nasıl yapılır: parola geri yazmayı yapılandırma](/azure/active-directory/authentication/howto-sspr-writeback). 

Etki alanına katılmış Windows 10 cihazları da yönetmek istiyorsanız bkz. Karma Azure AD Join ayarlamak [için etki alanına katılmış Windows 10 cihazların Microsoft 365 İş Ekstra tarafından yönetilmesini etkinleştirme](../../business-premium/m365bp-manage-windows-devices.md).
