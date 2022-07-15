---
title: PowerShell kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: PowerShell'i kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetmeyi öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 1064401dee3a25a7d1749db6e4a36a110f21da0b
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824735"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management

## <a name="overview"></a>Genel bakış

[Mavi Yonder için Microsoft Teams Vardiyaları bağlayıcısı](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder), Microsoft Teams'deki Vardiyalar uygulamasını Blue Yonder Workforce Management (Mavi Yonder WFM) ile tümleştirmenize olanak tanır. Bir bağlantı kurduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden Blue Yonder WFM zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bağlantı kurmak için Microsoft 365 yönetim merkezi veya [PowerShell'deki](shifts-connector-blue-yonder-powershell-setup.md) [Vardiyalar bağlayıcı sihirbazını](shifts-connector-wizard.md) kullanabilirsiniz. Bağlantı kurulduktan sonra [, Shifts bağlayıcısı PowerShell cmdlet'lerini](#shifts-connector-cmdlets) kullanarak bunu yönetirsiniz.

Bu makalede, aşağıdakileri yapmak için PowerShell'in nasıl kullanılacağı açıklanmaktadır:

- [Bağlantı kurulum durumunu denetleme](#check-connection-setup-status)
- [Bağlantı için hata raporunu görüntüleme](#view-an-error-report-for-a-connection)
- [Bağlantı hatalarını çözme](#resolve-connection-errors)
- [Bağlantı ayarlarını değiştirme](#change-connection-settings)
- [Ekibin eşlemesini bir bağlantıdan kaldırma ve başka bir bağlantıyla eşleme](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Bağlantı için eşitlemeyi devre dışı bırakma](#disable-sync-for-a-connection)

> [!NOTE]
> Bu makalede, sihirbazı veya PowerShell'i kullanarak Blue Yonder WFM ile zaten bir bağlantı ayarladığınız varsayılır.

## <a name="before-you-begin"></a>Başlamadan önce

[!INCLUDE [shifts-connector-admin-role](includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Ortamınızı ayarlama

> [!NOTE]
> Bu makaledeki komut veya betiklerden herhangi birini çalıştırmadan önce ortamınızı ayarlamak için bu adımları izlediğinizden emin olun.

[!INCLUDE [shifts-connector-set-up-environment](includes/shifts-connector-set-up-environment.md)]

7. Teams'e bağlanın.

    ```powershell
    Connect-MicrosoftTeams
    ```

    İstendiğinde yönetici kimlik bilgilerinizi kullanarak oturum açın. Artık bu makaledeki betikleri ve Shifts bağlayıcısı cmdlet'lerini çalıştıracak şekilde ayarlandınız.

## <a name="check-connection-setup-status"></a>Bağlantı kurulum durumunu denetleme

<a name="setup_status"> </a>

E-postada aldığınız işlem kimliğini kullanarak ayarladığınız bağlantının durumunu denetlemek için:

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Aşağıdaki komutu çalıştırın. Bu komut, bağlantı için ekip eşlemelerinin genel durumunu verir.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Bağlantı için hata raporunu görüntüleme

<a name="error_report"> </a>

Bağlantının hata ayrıntılarını gösteren bir rapor çalıştırabilirsiniz. Raporda başarılı ve başarısız olan ekip ve kullanıcı eşlemeleri listelenir. Ayrıca, bağlantıyla ilişkili hesaplarla ilgili sorunlar hakkında da bilgi sağlar.

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Bağlantı için hata raporlarının listesini alın.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Belirli bir hata raporunu görüntülemek için aşağıdaki komutu çalıştırın:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Bağlantı hatalarını çözme

### <a name="user-mapping-errors"></a>Kullanıcı eşleme hataları

Blue Yonder WFM örneğindeki bir veya daha fazla kullanıcı Teams'de eşlenen ekibin üyesi değilse kullanıcı eşleme hataları oluşabilir. Bu sorunu çözmek için eşlenen takımdaki kullanıcıların Blue Yonder WFM örneğindeki kullanıcılarla eşleştiğinden emin olun.

Eşlenmemiş kullanıcıların ayrıntılarını görüntülemek için [ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Hesap yetkilendirme hataları

Blue Yonder WFM hizmet hesabı veya Microsoft 365 sistem hesabı kimlik bilgileri yanlışsa veya gerekli izinlere sahip değilse hesap yetkilendirme hataları oluşabilir.

Bağlantının Blue Yonder WFM hizmet hesabınızı veya Microsoft 365 sistem hesabı kimlik bilgilerini değiştirmek için [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet'ini çalıştırabilir veya bu makalenin [Bağlantı ayarlarını değiştir](#change-connection-settings) bölümündeki PowerShell betiğini kullanabilirsiniz.

## <a name="change-connection-settings"></a>Bağlantı ayarlarını değiştirme
<a name="change_settings"> </a>

Bağlantı ayarlarını değiştirmek için bu betiği kullanın. Değiştirebileceğiniz ayarlar arasında Blue Yonder WFM hizmet hesabınız ve parolanız, Microsoft 365 sistem hesabınız, ekip eşlemeleri ve eşitleme ayarları yer alır.

Eşitleme ayarları, eşitleme sıklığını (dakika cinsinden) ve Blue Yonder WFM ile Vardiyalar arasında eşitlenen zamanlama verilerini içerir. Zamanlama verileri aşağıdaki parametrelerde tanımlanır. [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) komutunu çalıştırarak görüntüleyebilirsiniz.

- **enabledConnectorScenarios** parametresi, Blue Yonder WFM'dan Shifts'e eşitlenen verileri tanımlar. Seçenekler şunlardır: `Shift`, `SwapRequest`, `UserShiftPreferences``OpenShift`, , `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- **enabledWfiScenarios** parametresi, Shifts ile Blue Yonder WFM eşitlenen verileri tanımlar. Seçenekler : `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Açık vardiyaları eşitlememeyi, vardiya isteklerini açmamayı, değiştirme isteklerini veya Vardiyalar ile Mavi Yonder WFM arasında izin isteklerini değiştirmemeyi seçerseniz, Vardiyalar'da özelliği gizlemek için yapmanız gereken başka bir adım vardır. Bu betiği çalıştırdıktan sonra, bu makalenin devamında [Açık vardiyaları devre dışı bırakma, vardiya isteklerini açma, değiştirme istekleri ve izin istekleri](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) bölümündeki adımları izlediğinize emin olun.

> [!IMPORTANT]
> Değiştirmek istemediğiniz ayarlar için, betik tarafından istendiğinde özgün ayarları yeniden girmeniz gerekir.

[Ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini ve izin isteklerini devre dışı bırakma

> [!IMPORTANT]
> Bu adımları yalnızca bu makalenin önceki bölümlerindeki [Bağlantı ayarlarını değiştir](#change-connection-settings) bölümündeki betiği kullanarak veya [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet'ini kullanarak açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmayı seçtiyseniz izleyin. Bu adımın tamamlanması, Vardiyalar'daki özelliği gizler. Bu ikinci adım olmadan, kullanıcılar özelliği Vardiyalar'da görmeye devam eder ve kullanmaya çalışırlarsa "desteklenmeyen işlem" hata iletisini alır.

Vardiyalarda açık vardiyaları, değiştirme isteklerini ve izin isteklerini gizlemek için Graph API [zamanlama kaynak türünü](/graph/api/resources/schedule) kullanarak bir Blue Yonder WFM örneğine ```false``` eşlediğiniz her takım için aşağıdaki parametreleri olarak ayarlayın:

- Vardiyaları açma: ```openShiftsEnabled```
- Değiştirme istekleri:  ```swapShiftsRequestsEnabled```
- zaman aşımı istekleri: ```timeOffRequestsEnabled```

Vardiyalar'da açık vardiya isteklerini gizlemek için Vardiyalar'daki **Ayarlar'a** gidin ve **Vardiyaları aç** ayarını kapatın.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Ekibin eşlemesini bir bağlantıdan kaldırma ve başka bir bağlantıyla eşleme

> [!NOTE]
> Her iki bağlantı için de Microsoft 365 sistem hesabı aynı olmalıdır. Değilse, "Bu belirlenen aktör profilinin ekip sahipliği ayrıcalıkları yok" hata iletisini alırsınız.

Bir ekibin eşlemesini bir bağlantıdan kaldırmak ve başka bir bağlantıyla eşlemek istiyorsanız:

1. [Ortamınızı ayarlayın](#set-up-your-environment) (henüz ayarlamadıysanız).
1. Bağlantı için tüm ekip eşlemelerinin listesini görüntüleyin.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Bağlantıdan bir ekip eşlemesini kaldırın.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Ekibi başka bir bağlantıyla eşleyin.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Daha fazla bilgi için bkz. [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) ve [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Bağlantı için eşitlemeyi devre dışı bırakma

Bağlantı için eşitlemeyi devre dışı bırakmak için bu betiği kullanın. Bu betiğin bir bağlantıyı kaldırmaz veya silmez. Belirttiğiniz bağlantı için Vardiyalar ile Blue Yonder WFM arasında veri eşitlenmemesi için eşitlemeyi kapatır.

[Ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Shifts bağlayıcı cmdlet'leri

Shifts bağlayıcısı cmdlet'leri ile ilgili yardım için [Teams PowerShell cmdlet başvurusunda](/powershell/teams/intro) **CsTeamsShiftsConnection** araması yapın. Yaygın olarak kullanılan bazı cmdlet'lerin bağlantıları aşağıdadır.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>İlgili makaleler

- [Bağlayıcıları kaydırıyor](shifts-connectors.md)
- [Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management](shifts-connector-wizard.md)
- [PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)
