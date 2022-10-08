---
title: Tek bir PowerShell penceresinde tüm Microsoft 365 hizmetlerine bağlanma
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/23/2021
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Özet: Tek bir PowerShell penceresinde tüm Microsoft 365 hizmetlerine bağlanın.'
ms.openlocfilehash: f252c963d0f3f654f116410f06be2401b2f8a4e0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68199075"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Tek bir PowerShell penceresinde tüm Microsoft 365 hizmetlerine bağlanma

Microsoft 365'i yönetmek için PowerShell kullandığınızda, aynı anda birden çok PowerShell oturumu açabilirsiniz. Kullanıcı hesaplarını, SharePoint Online'ı, Exchange Online, Microsoft Teams'i, Office 365 için Microsoft Defender özelliklerini (güvenlik) ve Microsoft Purview uyumluluk özelliklerini yönetmek için farklı PowerShell pencereleriniz olabilir.

Bu senaryo Microsoft 365'i yönetmek için en uygun senaryo değildir çünkü hizmetler arası yönetim için bu pencereler arasında veri alışverişi yapamazsınız. Bu makalede, Microsoft Purview uyumluluğu Office 365 için Defender Microsoft 365 hesaplarını, Exchange Online, SharePoint Online'ı, Microsoft Teams'i ve özellikleri yönetmek için tek bir PowerShell örneğinin nasıl kullanılacağı açıklanır.

>[!Note]
>Bu makale şu anda yalnızca Dünya Çapında (+GCC) buluta bağlanma komutlarını içerir. Notlar, diğer Microsoft 365 bulutlarına bağlanma hakkındaki makalelerin bağlantılarını sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

PowerShell'in tek bir örneğinden tüm Microsoft 365'i yönetebilmeniz için aşağıdaki önkoşulları göz önünde bulundurun:

- Kullandığınız Microsoft 365 iş veya okul hesabı, Microsoft 365 yönetici rolünün üyesi olmalıdır. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../admin/add-users/about-admin-roles.md). Bu, Microsoft 365 için PowerShell için bir gereksinimdir, ancak diğer tüm Microsoft 365 hizmetleri için zorunlu değildir.

- Windows'un aşağıdaki 64 bit sürümlerini kullanabilirsiniz:
  - Windows 11
  - Windows 10
  - Windows 8.1 veya Windows 8
  - Windows Server 2019
  - Windows Server 2016
  - R2 veya Windows Server 2012 Windows Server 2012
  - Windows 7 Service Pack 1 (SP1)*
  - Windows Server 2008 R2 SP1*

    \*Microsoft .NET Framework 4.5'i yüklemeniz gerekir.*x* ve ardından 3.0 veya 4.0 Windows Management Framework. Daha fazla bilgi için bkz. [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).

- Azure Active Directory (Azure AD), Exchange Online, Office 365 için Defender, Microsoft Purview uyumluluğu, SharePoint Online ve Teams için gereken modülleri yüklemeniz gerekir:

  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Yönetim Kabuğu](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
  - [Teams PowerShell Modülü](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell modülünü yükleme ve koruma](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-module)
  - [Teams PowerShell'e Genel Bakış](/microsoftteams/teams-powershell-overview)

- PowerShell, Exchange Online, Office 365 için Defender ve Microsoft Purview uyumluluğu için imzalı betikleri çalıştıracak şekilde yapılandırılmalıdır. Yükseltilmiş bir PowerShell oturumunda ( **yönetici olarak çalıştırdığınız** bir PowerShell oturumu) aşağıdaki komutu çalıştırın.

   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Yalnızca parola kullanırken bağlantı adımları

Oturum açmak için yalnızca bir parola kullanırken tek bir PowerShell penceresindeki tüm hizmetlere bağlanmak için bu adımları izleyin.

1. Windows PowerShell açın.

2. Bu komutu çalıştırın ve Microsoft 365 iş veya okul hesabı kimlik bilgilerinizi girin.

   ```powershell
   $credential = Get-Credential
   ```

3. Graph için Azure Active Directory PowerShell modülünü kullanarak Azure AD bağlanmak için bu komutu çalıştırın.

   ```powershell
   Connect-AzureAD -Credential $credential
   ```

   Windows PowerShell modülü için Microsoft Azure Active Directory Modülü kullanıyorsanız bu komutu çalıştırın.

   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!NOTE]
   > PowerShell Core, Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü ve adında *Msol* bulunan cmdlet'leri desteklemez. Bu cmdlet'leri PowerShell'den çalıştırmanız gerekir.

4. SharePoint Online'a bağlanmak için bu komutları çalıştırın. Etki alanınız için kuruluş adını belirtin. Örneğin, "litwareinc\.onmicrosoft.com" için kuruluş adı değeri "litwareinc" olur.

   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Exchange Online bağlanmak için bu komutları çalıştırın.

   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Worldwide dışındaki Microsoft 365 bulutlarının Exchange Online bağlanmak için bkz. [Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

6. Güvenlik & Uyumluluk PowerShell'e bağlanmak için bu komutları çalıştırın.

   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!NOTE]
   > Dünya Çapında dışındaki Microsoft 365 bulutları için Güvenlik & Uyumluluğu PowerShell'e bağlanmak için bkz. [Güvenlik & Uyumluluk PowerShell'e bağlanma](/powershell/exchange/connect-to-scc-powershell).

7. Teams PowerShell'e bağlanmak için bu komutları çalıştırın.

   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   > [!NOTE]
   > Skype Kurumsal Online Connector şu anda en son Teams PowerShell modülünün bir parçasıdır. En son Teams PowerShell genel sürümünü kullanıyorsanız Skype Kurumsal Çevrimiçi Bağlayıcısı'nı yüklemeniz gerekmez.
   >
   > *Worldwide* dışındaki Microsoft Teams bulutlarına bağlanmak için bkz [. Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).

### <a name="azure-active-directory-powershell-for-graph-module-when-using-just-a-password"></a>Yalnızca parola kullanırken Graph için Azure Active Directory PowerShell modülü

Graph için Azure Active Directory PowerShell modülünü kullandığınızda tek bir bloktaki tüm hizmetlere yönelik komutlar aşağıdadır. Oturum açma için etki alanı konağınızın adını ve UPN'sini belirtin ve hepsini aynı anda çalıştırın.

```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-just-a-password"></a>Yalnızca parola kullanırken Windows PowerShell modülü için Microsoft Azure Active Directory Modülü

Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü kullandığınızda tek bir bloktaki tüm hizmetlere yönelik komutlar aşağıdadır. Oturum açma için etki alanı konağınızın adını ve UPN'sini belirtin ve hepsini tek seferde çalıştırın.

```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Çok faktörlü kimlik doğrulaması kullanırken bağlantı adımları

### <a name="azure-active-directory-powershell-for-graph-module-when-using-mfa"></a>MFA kullanırken Graph için Azure Active Directory PowerShell modülü

Graph için Azure Active Directory PowerShell modülüyle çok faktörlü kimlik doğrulaması kullandığınızda birden çok Microsoft 365 hizmetlerine bağlanmak için tek bir bloktaki tüm komutları aşağıda bulabilirsiniz.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-mfa"></a>MFA kullanırken Windows PowerShell modülü için Microsoft Azure Active Directory Modülü

Windows PowerShell modülü için Microsoft Azure Active Directory Modülü ile çok faktörlü kimlik doğrulaması kullandığınızda birden çok Microsoft 365 hizmetlerine bağlanmak için tek bir bloktaki tüm komutları aşağıda bulabilirsiniz.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>PowerShell penceresini kapatma

PowerShell penceresini kapatmak için şu komutu çalıştırarak SharePoint Online, Teams, Office 365 için Defender ve Microsoft Purview uyumluluğundaki etkin oturumları kaldırın:

```powershell
Disconnect-SPOService; Disconnect-MicrosoftTeams; Disconnect-ExchangeOnline
```

## <a name="see-also"></a>Ayrıca bkz.

- [PowerShell ile Microsoft 365’e bağlanma](connect-to-microsoft-365-powershell.md)
- [SharePoint Online'i PowerShell ile yönetme](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [PowerShell ile Microsoft 365 kullanıcı hesaplarını, lisanslarını ve gruplarını yönetme](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
