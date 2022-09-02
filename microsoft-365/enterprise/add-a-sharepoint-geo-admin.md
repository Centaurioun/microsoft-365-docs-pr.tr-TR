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
ms.openlocfilehash: 259c04b70aedd13430a06ce1307aa900e62fcb96
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67556380"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo'da coğrafi yönetici ekleme veya kaldırma

Kiracınızdaki her coğrafi konum için ayrı yöneticiler yapılandırabilirsiniz. Bu yöneticiler, coğrafi konumlarına özgü SharePoint Online ve OneDrive ayarlarına erişebilir.

Depo terimi gibi bazı hizmetler merkezi konumdan yönetilir ve uydu konumlarına çoğaltılır. Merkezi konumun coğrafi yöneticisi bunlara erişime sahipken, uydu konumları için coğrafi yöneticiler erişime sahip değildir.

Genel yöneticiler ve SharePoint Online yöneticileri, merkezi konumdaki ve tüm uydu konumlarındaki ayarlara erişmeye devam eder.

## <a name="configuring-geo-administrators"></a>Coğrafi yöneticileri yapılandırma

Coğrafi yöneticileri yapılandırmak için SharePoint Online PowerShell modülü gerekir.

Coğrafi yöneticiyi eklemek istediğiniz coğrafi konumun yönetim merkezine bağlanmak için [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) kullanın. (Örneğin, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

Bir konumun mevcut coğrafi yöneticilerini görüntülemek için `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Coğrafi yönetici olarak kullanıcı ekleme

Kullanıcıyı coğrafi yönetici olarak eklemek için `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Bir kullanıcıyı konumun Coğrafi Yönetici olarak kaldırmak için`Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Coğrafi yönetici olarak grup ekleme

Coğrafi yönetici olarak bir güvenlik grubu veya posta özellikli bir güvenlik grubu ekleyebilirsiniz. (Dağıtım grupları ve Microsoft 365 Grupları desteklenmez.)

Bir grubu coğrafi yönetici olarak eklemek için `Add-SPOGeoAdministrator -GroupAlias <alias>`

Bir grubu coğrafi yönetici olarak kaldırmak için `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Tüm güvenlik gruplarının bir grup diğer adına sahip olmadığını unutmayın. Diğer adı olmayan bir güvenlik grubu eklemek istiyorsanız, grupların listesini almak için [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) komutunu çalıştırın, güvenlik grubunuzun ObjectID değerini bulun ve şunu çalıştırın:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

ObjectID kullanarak bir grubu kaldırmak için `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>İlgili konular

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Güvenlik grubu için diğer ad (MailNickName) ayarlama](/powershell/module/azuread/set-azureadgroup)