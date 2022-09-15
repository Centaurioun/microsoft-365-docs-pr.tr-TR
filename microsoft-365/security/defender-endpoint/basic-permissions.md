---
title: Microsoft Defender Güvenlik Merkezi erişmek için temel izinleri kullanma
description: Uç Nokta için Microsoft Defender portalına erişmek için temel izinleri kullanmayı öğrenin.
keywords: kullanıcı rolleri atama, okuma ve yazma erişimi atama, salt okunur erişim atama, kullanıcı, kullanıcı rolleri, roller
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
search.appverid: met150
ms.openlocfilehash: 2b5590dd2e66a0b86c067e11b1fce5f9b85893b6
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702456"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Portala erişmek için temel izinleri kullanın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Azure Active Directory
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-basicaccess-abovefoldlink)

Temel izin yönetimini kullanmak için aşağıdaki yönergelere bakın.

Aşağıdaki çözümlerden birini kullanabilirsiniz:

- Azure PowerShell
- Azure portal

İzinler üzerinde ayrıntılı denetim [için rol tabanlı erişim denetimine geçin](rbac.md).

## <a name="assign-user-access-using-azure-powershell"></a>Azure PowerShell kullanarak kullanıcı erişimi atama

Aşağıdaki izin düzeylerinden birine sahip kullanıcıları atayabilirsiniz:

- Tam erişim (Okuma ve Yazma)
- Salt okunur erişim

### <a name="before-you-begin"></a>Başlamadan önce

- Azure PowerShell yükleyin. Daha fazla bilgi için bkz. [Azure PowerShell yükleme ve yapılandırma](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).

  > [!NOTE]
  > PowerShell cmdlet'lerini yükseltilmiş bir komut satırında çalıştırmanız gerekir.

- Azure Active Directory'nize bağlanın. Daha fazla bilgi için bkz [. Connect-MsolService](/powershell/module/msonline/connect-msolservice).

  - **Tam erişim**: Tam erişimi olan kullanıcılar oturum açabilir, tüm sistem bilgilerini görüntüleyebilir ve uyarıları çözümleyebilir, ayrıntılı analiz için dosya gönderebilir ve ekleme paketini indirebilir. Tam erişim hakları atamak için kullanıcıların "Güvenlik Yöneticisi" veya "Genel Yönetici" AAD yerleşik rollerine eklenmesi gerekir.
  - **Salt okunur erişim**: Salt okunur erişimi olan kullanıcılar oturum açabilir, tüm uyarıları ve ilgili bilgileri görüntüleyebilir.

    Bu kişiler uyarı durumlarını değiştiremez, derin analiz için dosya gönderemez veya durum değiştirme işlemleri gerçekleştiremez.

    Salt okunur erişim hakları atamak için kullanıcıların "Güvenlik Okuyucusu" Azure AD yerleşik rolüne eklenmesi gerekir.

Güvenlik rolleri atamak için aşağıdaki adımları kullanın:

- **Okuma ve yazma** erişimi için, aşağıdaki komutu kullanarak kullanıcıları güvenlik yöneticisi rolüne atayın:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```

- **Salt okunur** erişim için, aşağıdaki komutu kullanarak kullanıcıları güvenlik okuyucusu rolüne atayın:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Daha fazla bilgi için bkz. [Azure Active Directory kullanarak grup üyeleri ekleme veya kaldırma](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Azure portal kullanarak kullanıcı erişimi atama

Daha fazla bilgi için bkz. [Azure Active Directory ile kullanıcılara yönetici ve yönetici olmayan roller atama](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="related-topic"></a>İlgili konu

- [RBAC kullanarak portal erişimini yönetin](rbac.md)
