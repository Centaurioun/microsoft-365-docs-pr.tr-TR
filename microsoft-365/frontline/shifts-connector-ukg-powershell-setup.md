---
title: Vardiyaları UKG Boyutlarına bağlamak için PowerShell kullanma
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Shift'leri UKG Boyutları ile tümleştirmek için PowerShell'i kullanmayı öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 0a69dd9b92fb0f71f3dbeb2841dcef62e2bd81bb
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786375"
---
# <a name="use-powershell-to-connect-shifts-to-ukg-dimensions"></a>Vardiyaları UKG Boyutlarına bağlamak için PowerShell kullanma

## <a name="overview"></a>Genel bakış

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[UkG Boyutları için Microsoft Teams Vardiyaları bağlayıcısını](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) kullanarak Microsoft Teams'deki Vardiyalar uygulamasını UKG Boyutları ile tümleştirin. Bağlantı kurulduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden UKG Dimensions'ta zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bu makalede, Bağlayıcıyı Shift'leri UKG Boyutları ile tümleştirecek şekilde ayarlamak ve yapılandırmak için PowerShell'i kullanma konusunda size yol gösteririz.

Bağlantıyı kurmak için bir PowerShell betiği çalıştırırsınız. Betik bağlayıcıyı yapılandırıyor, eşitleme ayarlarını uyguluyor, bağlantıyı oluşturuyor ve UKG Dimensions örneklerini ekiplere eşler. Eşitleme ayarları, Vardiyalar'da etkinleştirilen özellikleri ve UKG Boyutları ile Vardiyalar arasında eşitlenen zamanlama bilgilerini belirler. Eşlemeler, Teams'deki UKG Boyutları örnekleriniz ve ekipleriniz arasındaki eşitleme ilişkisini tanımlar. Mevcut ekiplere ve yeni ekiplere eşleyebilirsiniz.

İki betik sağlıyoruz. Mevcut ekiplere eşlemek veya eşlemek için yeni ekipler oluşturmak istediğinize bağlı olarak betiklerden birini kullanabilirsiniz.

Her birinde farklı eşitleme ayarları olan birden çok bağlantı ayarlayabilirsiniz. Örneğin, kuruluşunuzun farklı zamanlama gereksinimlerine sahip birden çok konumu varsa, her konum için benzersiz eşitleme ayarlarıyla bir bağlantı oluşturun. UkG Dimensions örneğinin herhangi bir anda yalnızca bir ekiple eşlenebileceğini unutmayın. Bir örnek zaten bir takımla eşlenmişse, başka bir takımla eşlenemez.

Kayıt sistemi olarak UKG Dimensions sayesinde ön saha çalışanlarınız zamanlamalarını ve kullanılabilirliklerini cihazlarında Vardiyalar'da verimli bir şekilde yönetebilir. Ön cephe yöneticileri zamanlamaları ayarlamak için UKG Boyutlarını kullanmaya devam edebilir.

> [!NOTE]
> Shift'leri UKG Boyutlarına bağlamak için Microsoft 365 yönetim merkezi Shifts [bağlayıcı sihirbazını](shifts-connector-wizard-ukg.md) da kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

### <a name="prerequisites"></a>Önkoşullar

[!INCLUDE [shifts-connector-ukg-prerequisites](includes/shifts-connector-ukg-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>PowerShell kullanarak bağlayıcıyı yönetmek için Yönetici rolü

[!INCLUDE [shifts-connector-admin-role](includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Ortamınızı ayarlama

[!INCLUDE [shifts-connector-set-up-environment](includes/shifts-connector-set-up-environment.md)]

## <a name="connect-to-teams"></a>Teams'e bağlanma

Teams'e bağlanmak için aşağıdakileri çalıştırın.

```powershell
Connect-MicrosoftTeams
```

İstendiğinde yönetici kimlik bilgilerinizi kullanarak oturum açın. Artık bu makaledeki betikleri ve Shifts bağlayıcısı cmdlet'lerini çalıştıracak şekilde ayarlandınız.

## <a name="identify-the-teams-you-want-to-map"></a>Eşlemek istediğiniz ekipleri belirleme

> [!NOTE]
> UKG Dimensions örneklerini mevcut ekiplere eşlerseniz bu adımı tamamlayın. Eşleme için yeni ekipler oluşturuyorsanız bu adımı atlayabilirsiniz.

Azure portal, kuruluşunuzdaki ekiplerin TeamId'lerinin listesini almak için [Tüm gruplar](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) sayfasına gidin.

Eşlemek istediğiniz ekiplerin TeamId değerlerini not alın. Betik bu bilgileri girmenizi ister.

> [!NOTE]
> Bir veya daha fazla ekibin mevcut bir zamanlaması varsa, betik bu ekiplerden zamanlamaları kaldırır. Aksi takdirde yinelenen vardiyalar görürsünüz.

## <a name="run-the-script"></a>Betiği çalıştırma

Betiği çalıştırın:

- Bir bağlantı kurmak ve eşlemek üzere yeni ekipler oluşturmak için [bu betiği çalıştırın](#set-up-a-connection-and-create-new-teams-to-map).
- Bağlantı kurmak ve mevcut ekiplere eşlemek için [bu betiği çalıştırın](#set-up-a-connection-and-map-to-existing-teams).

Betik aşağıdaki eylemleri gerçekleştirir. Kurulum ve yapılandırma ayrıntılarını girmeniz istenir.

1. Girdiğiniz UKG Dimensions hizmet hesabı kimlik bilgilerini ve hizmet URL'lerini kullanarak UKG Dimensions bağlantısını test eder ve doğrular.
1. Vardiyalar bağlayıcısını yapılandırıyor.
1. Eşitleme ayarlarını uygular. Bu ayarlar arasında eşitleme sıklığı (dakika cinsinden) ve UKG Boyutları ile Vardiyalar arasında eşitlenen zamanlama verileri yer alır. Zamanlama verileri aşağıdaki parametrelerde tanımlanır:

    - **enabledConnectorScenarios** parametresi, UKG Boyutlarından Shift'lere eşitlenen verileri tanımlar. Seçenekler şunlardır: `Shift`, `SwapRequest`, `UserShiftPreferences``OpenShift`, , `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
    - **enabledWfiScenarios** parametresi, Vardiyalar ile UKG Boyutları arasında eşitlenen verileri tanımlar. Seçenekler : `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    Daha fazla bilgi için bkz. [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance). Her parametre için desteklenen eşitleme seçeneklerinin listesini görmek için [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) komutunu çalıştırın.

    > [!IMPORTANT]
    > Betik, tüm bu seçenekler için eşitlemeyi etkinleştirir. Eşitleme ayarlarını değiştirmek istiyorsanız, bağlantı kurulduktan sonra bunu yapabilirsiniz. Daha fazla bilgi edinmek için bkz. [PowerShell kullanarak UKG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md).

1. Bağlantıyı oluşturur.
1. UKG Dimensions örneklerini ekiplere eşler. Eşlemeler, çalıştırdığınız betike bağlı olarak girdiğiniz UKG Boyutlar örneği kimliklerini ve oluşturduğunuz yeni ekipleri veya oluşturduğunuz TeamId'leri temel alır. Bir ekibin mevcut bir zamanlaması varsa betik, belirttiğiniz tarih ve saat aralığı için zamanlama verilerini kaldırır.

Ekrandaki Başarılı iletisi bağlantınızın başarıyla ayarlandığını gösterir.

## <a name="manage-your-connection"></a>Bağlantınızı yönetme

Bağlantı kurulduktan sonra, Microsoft 365 yönetim merkezi veya PowerShell kullanarak bu bağlantıyı yönetebilir ve bu bağlantıda değişiklik yapabilirsiniz.

### <a name="use-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanma

Bağlayıcı Yönetimi sayfasında, ayarladığınız her bağlantının yanı sıra sistem durumu ve eşitleme aralığı ayrıntıları gibi bilgiler listelenir. Bağlantılarınızdan herhangi birinde değişiklik yapmak için sihirbaza da erişebilirsiniz. Örneğin, eşitleme ayarlarını ve ekip eşlemelerini güncelleştirebilirsiniz.

Daha fazla bilgi edinmek için bkz. [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanma](shifts-connector-ukg-admin-center-manage.md).

### <a name="use-powershell"></a>PowerShell kullanma

PowerShell'i kullanarak hata raporunu görüntüleyebilir, bağlantı ayarlarını değiştirebilir, eşitlemeyi devre dışı bırakabilir ve daha fazlasını yapabilirsiniz. Adım adım yönergeler için bkz. [PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md).

## <a name="scripts"></a>Komut dosyaları

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>Bağlantı kurma ve eşlemek için yeni ekipler oluşturma

```powershell
#Map WFM instances to teams script
Write-Host "Map WFM sites to teams"
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
$enabledConnectorScenario = $Ukg.SupportedScenario
$wfiSupportedScenario = $Ukg.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$apiUrl = Read-Host -Prompt 'Input connector api url'
$ssoUrl = Read-Host -Prompt 'Input connector sso url'
$clientId = Read-Host -Prompt 'Input connector client id'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $UkgId `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
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
        })
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of instances
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if (($WfmTeamIds -ne $NULL) -and ($WfmTeamIds.Count -gt 0)){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#Add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the instance
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>Bağlantı kurma ve mevcut ekiplere eşleme

```powershell
#Map WFM instances to existing teams script
Write-Host "Map WFM sites to existing teams"
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
$ukg = $connectors | where {$_.Id -match $UkgId}
$enabledConnectorScenario = $ukg.SupportedScenario
$wfiSupportedScenario = $ukg.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$apiUrl = Read-Host -Prompt 'Input connector api url'
$ssoUrl = Read-Host -Prompt 'Input connector sso url'
$clientId = Read-Host -Prompt 'Input connector client id'
$AppKey = Read-Host -Prompt 'Input your app key' -AsSecureString
$plainKey =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($AppKey))
$ClientSecret = Read-Host -Prompt 'Input your client secret' -AsSecureString
$plainSecret =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($ClientSecret))

$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $UkgId `
    -ConnectorSpecificSettings (New-Object Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Models.ConnectorSpecificUkgDimensionsSettingsRequest `
        -Property @{
            apiUrl = $apiUrl
            ssoUrl = $ssoUrl
            appKey = $plainKey
            clientId = $clientId
            clientSecret = $plainSecret
            LoginUserName = $WfmUserName
            LoginPwd = $plainPwd
        })
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create a connection instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency. Value should be equal to or more than 10."

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

$InstanceResponse = New-CsTeamsShiftsConnectionInstance `
    -ConnectorId $UkgId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
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
        })
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if (($WfmTeamIds -ne $NULL) -and ($WfmTeamIds.Count -gt 0)){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $teamsUserId

#Create a mapping of the existing team to the instance
Write-Host "Create a mapping of the existing team to the site"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
```

## <a name="shifts-connector-cmdlets"></a>Shifts bağlayıcı cmdlet'leri

Betiklerde kullanılan cmdlet'ler de dahil olmak üzere Shifts bağlayıcı cmdlet'leri ile ilgili yardım için [Teams PowerShell cmdlet başvurusunda](/powershell/teams/intro) **CsTeamsShiftsConnection** araması yapın. Yaygın olarak kullanılan bazı cmdlet'lerin bağlantıları aşağıdadır.

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
- [PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md)
- [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanın](shifts-connector-ukg-admin-center-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)
- [Teams PowerShell cmdlet başvurusu](/powershell/teams/intro)
