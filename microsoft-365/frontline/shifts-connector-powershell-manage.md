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
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: d4b9994f95e6555ae12a5fa56e8f1bf1a4ce4de8
ms.sourcegitcommit: 3d7dd25abcbf923b45eae84ff4d9d2bb95ef4ca4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68777816"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management

## <a name="overview"></a>Genel bakış

[Mavi Yonder için Microsoft Teams Vardiyaları bağlayıcısı](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder), Microsoft Teams'deki Vardiyalar uygulamasını Blue Yonder Workforce Management (Mavi Yonder WFM) ile tümleştirmenize olanak tanır. Bir bağlantı kurduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden Blue Yonder WFM zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bağlantı kurmak için Microsoft 365 yönetim merkezi veya [PowerShell'deki](shifts-connector-blue-yonder-powershell-setup.md) [Vardiyalar bağlayıcı sihirbazını](shifts-connector-wizard.md) kullanabilirsiniz. Bağlantı kurulduktan sonra [Shifts bağlayıcısı PowerShell cmdlet'lerini](#shifts-connector-cmdlets) kullanarak bu bağlantıyı yönetebilirsiniz.

Bu makalede, aşağıdakileri yapmak için PowerShell'in nasıl kullanılacağı açıklanmaktadır:

- [Bağlantı kurulum durumunu denetleme](#check-connection-setup-status)
- [Bağlantı için hata raporunu görüntüleme](#view-an-error-report-for-a-connection)
- [Bağlantı hatalarını çözme](#resolve-connection-errors)
- [Bağlantı ayarlarını değiştirme](#change-connection-settings)
- [Ekibin eşlemesini bir bağlantıdan kaldırma ve başka bir bağlantıyla eşleme](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Bağlantı için eşitlemeyi devre dışı bırakma](#disable-sync-for-a-connection)

Bu makalede, sihirbazı veya PowerShell'i kullanarak Blue Yonder WFM ile zaten bir bağlantı ayarladığınız varsayılır.

> [!NOTE]
> Ayrıca bağlantınızı Microsoft 365 yönetim merkezi yönetebilirsiniz. Örneğin, bağlantı ayarlarını değiştirmek için sistem durumunu denetleyebilir ve sihirbaza erişebilirsiniz. Daha fazla bilgi edinmek için bkz. [Microsoft 365 yönetim merkezi kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-blue-yonder-admin-center-manage.md).

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

[!INCLUDE [shifts-connector-check-setup-status](includes/shifts-connector-check-setup-status.md)]

## <a name="view-an-error-report-for-a-connection"></a>Bağlantı için hata raporunu görüntüleme
<a name="error_report"> </a>

[!INCLUDE [shifts-connector-view-error-report](includes/shifts-connector-view-error-report.md)]

> [!NOTE]
> Hata iletilerinin tam listesi için bu [makalenin devamında yer alan Hata iletilerinin listesi](#list-of-error-messages) bölümüne bakın.

## <a name="resolve-connection-errors"></a>Bağlantı hatalarını çözme

### <a name="user-mapping-errors"></a>Kullanıcı eşleme hataları

WFM örnekteki bir veya daha fazla kullanıcı Teams'de eşlenen ekibin üyesi değilse kullanıcı eşleme hataları oluşabilir. Bu sorunu çözmek için eşlenen takımdaki kullanıcıların WFM örneğindeki kullanıcılarla eşleştiğinden emin olun.

Eşlenmemiş kullanıcıların ayrıntılarını görüntülemek için [ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
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

[!INCLUDE [shifts-connector-account-authorization-errors](includes/shifts-connector-account-authorization-errors.md)]

## <a name="change-connection-settings"></a>Bağlantı ayarlarını değiştirme
<a name="change_settings"> </a>

[!INCLUDE [shifts-connector-change-connection-settings](includes/shifts-connector-change-connection-settings.md)]

[Ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#Update connector instance and mapping script
Write-Host "Update Connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
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
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $BlueYonderId}
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
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
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance `
    -ConnectorInstanceId $InstanceId `
    -ConnectorId $BlueYonderId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $updatedConnectorScenario `
    -EnabledWfiScenario $updatedWfiScenario `
    -Name $UpdatedInstanceName `
    -SyncFrequencyInMin $syncFreq `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificBlueYonderSettingsRequest `
    -Property @{
        AdminApiUrl = $adminApiUrl
        SiteManagerUrl = $siteManagerUrl
        EssApiUrl = $essApiUrl
        RetailWebApiUrl = $retailWebApiUrl
        CookieAuthUrl = $cookieAuthUrl
        FederatedAuthUrl = $federatedAuthUrl
        LoginUserName = $WfmUserName
        LoginPwd = $plainPwd
    }) `
    -IfMatch $Etag
if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
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

[!INCLUDE [shifts-connector-disable-shifts-requests](includes/shifts-connector-disable-shifts-requests.md)]

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Ekibin eşlemesini bir bağlantıdan kaldırma ve başka bir bağlantıyla eşleme

[!INCLUDE [shifts-connector-unmap-a-team](includes/shifts-connector-unmap-a-team.md)]

## <a name="disable-sync-for-a-connection"></a>Bağlantı için eşitlemeyi devre dışı bırakma

Bağlantı için eşitlemeyi devre dışı bırakmak için bu betiği kullanın. Bu betiğin bir bağlantıyı kaldırmaz veya silmez. Eşitlemeyi kapatarak, belirttiğiniz bağlantı için Vardiyalar ile WFM sisteminiz arasında hiçbir veri eşitlenmemesi sağlanır.

[Ortamınızı ayarlayın](#set-up-your-environment) (henüz yapmadıysanız) ve ardından aşağıdaki betiği çalıştırın.

```powershell
#Disable sync script
Write-Host "Disable sync"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.7.0
} catch {
    throw
}

#List connection instances available
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $BlueYonderId}
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

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance `
    -ConnectorInstanceId $InstanceId `
    -ConnectorId $BlueYonderId `
    -ConnectorAdminEmail $ConnectorAdminEmail `
    -DesignatedActorId $DesignatedActorId `
    -EnabledConnectorScenario @() `
    -EnabledWfiScenario @() `
    -Name $UpdatedInstanceName `
    -SyncFrequencyInMin 10 `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificBlueYonderSettingsRequest `
        -Property @{
            AdminApiUrl = $adminApiUrl
            SiteManagerUrl = $siteManagerUrl
            EssApiUrl = $essApiUrl
            RetailWebApiUrl = $retailWebApiUrl
            CookieAuthUrl = $cookieAuthUrl
            FederatedAuthUrl = $federatedAuthUrl
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        }) `
    -IfMatch $Etag

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```
## <a name="list-of-error-messages"></a>Hata iletilerinin listesi

Karşılaşabileceğiniz hata iletilerinin listesi ve bunları çözmenize yardımcı olacak bilgiler aşağıdadır.

|Hata türü |Hata ayrıntıları |Çözüm |
|---------|---------|---------|
|İş gücü yönetim sistemi kimlik doğrulaması yapılamıyor.|Sağladığınız iş gücü yönetim sistemi hesabı kimlik bilgileri geçersiz veya bu hesabın gerekli izinleri yok.|Bağlantı ayarlarında WFM hizmet hesabı kimlik bilgilerinizi güncelleştirin. Bunu yapmak için aşağıdaki yöntemlerden birini kullanın.<ul><li>Microsoft 365 yönetim merkezi Bağlayıcı Yönetimi sayfasında veya bağlantı ayrıntıları sayfasında **Düzenle'yi** seçerek Shifts bağlayıcı sihirbazına gidin.</li><li>[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) veya [Update-CsTeamsShiftsConnectionInstance cmdlet'ini](/powershell/module/teams/update-csteamsshiftsconnectioninstance) kullanın.</li><li>[Bu PowerShell betiğini](#change-connection-settings) kullanın.</li></ul>|
|Graph kimliği doğrulanamıyor. |Kimlik doğrulaması başarısız oldu. Belirlenen aktör için geçerli kimlik bilgileri girdiğinizden ve gerekli izinlere sahip olduğunuzdan emin olun.|Microsoft 365 sistem hesabınızın (belirlenen aktör olarak da bilinir) ekip sahibi olarak eklendiğinden emin olun.<br> Alternatif olarak, bağlantı ayarlarında Microsoft 365 sistem hesabı kimlik bilgilerinizi güncelleştirebilirsiniz.|
|Bazı kullanıcılar doğru eşleme yapamadı|Bazı kullanıcılar için eşleme başarısız oldu: \<X\> başarılı, \<X\> başarısız AAD kullanıcıları ve \<X\> başarısız iş gücü yönetim sistemi kullanıcıları.|Eşlemenin başarısız olduğu kullanıcıları tanımlamak için [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult) cmdlet'ini veya [bu PowerShell betiğini](#user-mapping-errors) kullanın. Eşlenen takımdaki kullanıcıların WFM örneğindeki kullanıcılarla eşleştiğinden emin olun.|
|Bu toplu işte bir ekip veya ekip eşlenemiyor. |Bu belirlenen aktör profilinin ekip sahipliği ayrıcalıkları yok. |Microsoft 365 sistem hesabınızın (belirlenen aktör olarak da bilinir) ekip sahibi olarak eklendiğinden emin olun.<br>Microsoft 365 sistem hesabınızı değiştirdiyseniz, bu hesabı ekip sahibi olarak ekleyin ve bağlantı ayarlarını bu hesabı kullanacak şekilde güncelleştirin.|
|    |Bu ekip zaten mevcut bir bağlayıcı örneğine eşlenmiş durumda. |[Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) cmdlet'ini kullanarak ekibin mevcut bağlantıdan eşlemesini kaldırın. Ya da ekibi yeniden eşlemek için yeni bir bağlantı oluşturun.|
|    |Bu saat dilimi geçersiz. geçirilen saat dilimi tz veritabanı biçimini kullanmıyor.|Saat diliminin doğru olduğundan emin olun ve ardından ekibi yeniden eşleyin.|
|    |Bu bağlayıcı örneğini bulamıyoruz.|Ekibi mevcut bir bağlantıyla eşleyin.|
|    |Bu AAD ekibi bulunamadı.|Ekibin var olduğundan emin olun veya yeni bir ekip oluşturun.|

## <a name="shifts-connector-cmdlets"></a>Shifts bağlayıcı cmdlet'leri

Shifts bağlayıcısı cmdlet'leri ile ilgili yardım için [Teams PowerShell cmdlet başvurusunda](/powershell/teams/intro) **CsTeamsShiftsConnection** araması yapın. Yaygın olarak kullanılan bazı cmdlet'lerin bağlantıları aşağıdadır.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Update-CsTeamsShiftsConnectionInstance](/powershell/module/teams/update-csteamsshiftsconnectioninstance)
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

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management](shifts-connector-wizard.md)
- [PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Microsoft 365 yönetim merkezi kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management](shifts-connector-blue-yonder-admin-center-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)
