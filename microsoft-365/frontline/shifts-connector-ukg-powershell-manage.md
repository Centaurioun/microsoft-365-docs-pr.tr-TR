---
title: PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: PowerShell'i kullanarak UKG Boyutlarına Vardiyalar bağlantınızı yönetmeyi öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 9d3375f41e4fda4cdc4e4be6352e197512729024
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785561"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-ukg-dimensions"></a>PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Genel bakış

[UKG Boyutları için Microsoft Teams Vardiyaları bağlayıcısı, Microsoft](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) Teams'deki Vardiyalar uygulamasını UKG Boyutları ile tümleştirmenize olanak tanır. Bir bağlantı kurduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden UKG Dimensions'ta zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bağlantı kurmak için Microsoft 365 yönetim merkezi veya [PowerShell'deki](shifts-connector-ukg-powershell-setup.md) [Vardiyalar bağlayıcı sihirbazını](shifts-connector-wizard-ukg.md) kullanabilirsiniz. Bağlantı kurulduktan sonra [Shifts bağlayıcısı PowerShell cmdlet'lerini](#shifts-connector-cmdlets) kullanarak bu bağlantıyı yönetebilirsiniz.

Bu makalede, aşağıdakileri yapmak için PowerShell'in nasıl kullanılacağı açıklanmaktadır:

- [Bağlantı kurulum durumunu denetleme](#check-connection-setup-status)
- [Bağlantı için hata raporunu görüntüleme](#view-an-error-report-for-a-connection)
- [Bağlantı hatalarını çözme](#resolve-connection-errors)
- [Bağlantı ayarlarını değiştirme](#change-connection-settings)
- [Ekibin eşlemesini bir bağlantıdan kaldırma ve başka bir bağlantıyla eşleme](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Bağlantı için eşitlemeyi devre dışı bırakma](#disable-sync-for-a-connection)

Bu makalede, sihirbazı veya PowerShell'i kullanarak UKG Boyutları'na bağlantı ayarladığınız varsayılır.

> [!NOTE]
> Ayrıca bağlantınızı Microsoft 365 yönetim merkezi yönetebilirsiniz. Örneğin, bağlantı ayarlarını değiştirmek için sistem durumunu denetleyebilir ve sihirbaza erişebilirsiniz. Daha fazla bilgi edinmek için bkz. [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanma](shifts-connector-ukg-admin-center-manage.md).

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

[!INCLUDE [shifts-connector-check-setup-status](includes/shifts-connector-check-setup-status.md)]

## <a name="view-an-error-report-for-a-connection"></a>Bağlantı için hata raporunu görüntüleme

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
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$Ukg = $connectors | where {$_.Id -match $UkgId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $UkgId}
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
$apiUrl = $Instance.ConnectorSpecificSettingApiUrl
$ssoUrl = $Instance.ConnectorSpecificSettingSsoUrl
$clientId = $Instance.ConnectorSpecificSettingClientId
$syncFreq = Read-Host -Prompt 'Input new sync frequency'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

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
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $updatedConnectorScenario `
    -EnabledWfiScenario $updatedWfiScenario `
    -Name $UpdatedInstanceName `
    -SyncFrequencyInMin $syncFreq `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
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
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance | where {$_.ConnectorId -match $UkgId}
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $apiUrl = $Instance.ConnectorSpecificSettingApiUrl
    $ssoUrl = $Instance.ConnectorSpecificSettingSsoUrl
    $clientId = $Instance.ConnectorSpecificSettingClientId
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$UkgId = "95BF2848-2DDA-4425-B0EE-D62AEED4C0A0"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance `
    -ConnectorInstanceId $InstanceId `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $ConnectorAdminEmail `
    -DesignatedActorId $DesignatedActorId `
    -EnabledConnectorScenario @() `
    -EnabledWfiScenario @() `
    -Name $UpdatedInstanceName `
    -SyncFrequencyInMin 10 `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
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
- [Shifts bağlayıcı sihirbazını kullanarak Shifts'i UKG Boyutlarına bağlama](shifts-connector-wizard-ukg.md)
- [Vardiyaları UKG Boyutlarına bağlamak için PowerShell kullanma](shifts-connector-ukg-powershell-setup.md)
- [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanın](shifts-connector-ukg-admin-center-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)
