---
title: Coğrafi konum yöneticisi ekleme veya kaldırma
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection: SPO_Content
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Her coğrafi konum için ayrı yöneticiler yapılandırmanız mı gerekiyor? Microsoft 365 Multi-Geo'da coğrafi yönetici eklemeyi veya kaldırmayı öğrenin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511dcc104eb8898c974c811b87704b3f22d4a2c2
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804674"
---
# <a name="add-or-remove-a-_geography_-administrator-in-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo'da _Coğrafya_ yöneticisi ekleme veya kaldırma

_Kiracınızda_ bulunan her _Coğrafya_ konumu için ayrı yöneticiler yapılandırabilirsiniz. Bu yöneticiler _, Coğrafya_ konumlarına özgü SharePoint Online ve OneDrive ayarlarına erişebilir.

Depo terimi gibi bazı hizmetler _Birincil Sağlanan Coğrafya_ konumundan yönetilir ve _Uydu Coğrafya_ konumlarına çoğaltılır. _Birincil Sağlanan Coğrafya_ konumunun _Coğrafya_ yöneticisi bunlara erişebilirken _, Uydu Coğrafya_ konumları için _Coğrafya_ yöneticilerine erişim yoktur.

Genel yöneticiler ve SharePoint Online yöneticileri _Birincil Sağlanan Coğrafya_ konumu ve tüm _Uydu Coğrafya_ konumlarındaki ayarlara erişmeye devam eder.

## <a name="configuring-_geography_-administrators"></a>_Coğrafya_ yöneticilerini yapılandırma

_Coğrafya_ yöneticilerinin yapılandırılması için SharePoint Online PowerShell modülü gerekir.

[Connect-SPOService'i](/powershell/module/sharepoint-online/Connect-SPOService) kullanarak Coğrafya _yöneticisini_ eklemek istediğiniz _Coğrafya_ konumunun yönetim merkezine bağlanın. (Örneğin, Connect-SPOServicehttps://ContosoEUR-admin.sharepoint.com.)

Bir konumun mevcut _Coğrafya_ yöneticilerini görüntülemek için `Get-SPOGeoAdministrator`

## <a name="adding-a-user-as-a-_geography_-admin"></a>_Coğrafya_ yöneticisi olarak kullanıcı ekleme

Kullanıcıyı _Coğrafya_ yöneticisi olarak eklemek için `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Bir konumun _Coğrafya_ Yönetici olarak bir kullanıcıyı kaldırmak için`Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

## <a name="adding-a-group-as-a-_geography_-admin"></a>_Coğrafya_ yöneticisi olarak grup ekleme

_Coğrafya_ yöneticisi olarak bir güvenlik grubu veya posta etkin bir güvenlik grubu ekleyebilirsiniz. (Dağıtım grupları ve Microsoft 365 Grupları desteklenmez.)

Bir grubu _Coğrafya_ yöneticisi olarak eklemek için `Add-SPOGeoAdministrator -GroupAlias <alias>`

Bir grubu _Coğrafya_ yöneticisi olarak kaldırmak için `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Tüm güvenlik gruplarının bir grup diğer adına sahip olmadığını unutmayın. Diğer adı olmayan bir güvenlik grubu eklemek istiyorsanız, grupların listesini almak için [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) komutunu çalıştırın, güvenlik grubunuzun ObjectID değerini bulun ve şunu çalıştırın:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

ObjectID kullanarak bir grubu kaldırmak için `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>İlgili konular

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Güvenlik grubu için diğer ad (MailNickName) ayarlama](/powershell/module/azuread/set-azureadgroup)
