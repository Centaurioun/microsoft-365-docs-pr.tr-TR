---
title: PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Shift'leri Blue Yonder Workforce Management ile tümleştirmek için PowerShell'i kullanmayı öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 0d04dfc056271bbc09d93269c90f637b865169be
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68786021"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management

## <a name="overview"></a>Genel bakış

[Microsoft Teams'deki Vardiyalar uygulamasını Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) Workforce Management (Blue Yonder WFM) ile tümleştirmek için Blue Yonder için Microsoft Teams Vardiyaları bağlayıcısını kullanın. Bağlantı kurulduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden Blue Yonder WFM zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bu makalede, Bağlayıcıyı Ayarlama ve Yapılandırma için PowerShell'in nasıl kullanılacağı konusunda size yol gösteririz. Bu makalede, Shift'leri Blue Yonder WFM ile tümleştirmek için bağlayıcıyı ayarlama ve yapılandırma.

Bağlantıyı kurmak için bir PowerShell betiği çalıştırırsınız. Betik bağlayıcıyı yapılandırıyor, eşitleme ayarlarını uyguluyor, bağlantıyı oluşturuyor ve Blue Yonder WFM örneklerini ekiplere eşler. Eşitleme ayarları, Vardiyalar'da etkinleştirilen özellikleri ve Blue Yonder WFM ile Vardiyalar arasında eşitlenen zamanlama bilgilerini belirler. Eşlemeler, Teams'deki Blue Yonder WFM örnekleriniz ve ekipleriniz arasındaki eşitleme ilişkisini tanımlar. Mevcut ekiplere ve yeni ekiplere eşleyebilirsiniz.

İki betik sağlıyoruz. Mevcut ekiplere eşlemek veya eşlemek için yeni ekipler oluşturmak istediğinize bağlı olarak betiklerden birini kullanabilirsiniz.

Her birinde farklı eşitleme ayarları olan birden çok bağlantı ayarlayabilirsiniz. Örneğin, kuruluşunuzun farklı zamanlama gereksinimlerine sahip birden çok konumu varsa, her konum için benzersiz eşitleme ayarlarıyla bir bağlantı oluşturun. Blue Yonder WFM örneğinin herhangi bir anda yalnızca bir ekiple eşlenebileceğini unutmayın. Bir örnek zaten bir takımla eşlenmişse, başka bir takımla eşlenemez.

Kayıt sistemi olarak Blue Yonder WFM, ön cephe çalışanlarınız kendi cihazlarında Vardiyalar'da zamanlamalarını ve kullanılabilirliklerini verimli bir şekilde yönetebilir. Ön cephe yöneticileri, zamanlamaları ayarlamak için Blue Yonder WFM kullanmaya devam edebilir.

> [!NOTE]
> [Ayrıca, Microsoft 365 yönetim merkezi'deki Vardiyalar bağlayıcı sihirbazını](shifts-connector-wizard.md) kullanarak Shift'leri Mavi Yonder WFM bağlayabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

### <a name="prerequisites"></a>Önkoşullar

[!INCLUDE [shifts-connector-prerequisites](includes/shifts-connector-prerequisites.md)]

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
> Blue Yonder WFM örneklerini mevcut ekiplere eşlerseniz bu adımı tamamlayın. Eşleme için yeni ekipler oluşturuyorsanız bu adımı atlayabilirsiniz.

Azure portal, kuruluşunuzdaki ekiplerin TeamId'lerinin listesini almak için [Tüm gruplar](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) sayfasına gidin.

Eşlemek istediğiniz ekiplerin TeamId değerlerini not alın. Betik bu bilgileri girmenizi ister.

> [!NOTE]
> Bir veya daha fazla ekibin mevcut bir zamanlaması varsa, betik bu ekiplerden zamanlamaları kaldırır. Aksi takdirde yinelenen vardiyalar görürsünüz.

## <a name="run-the-script"></a>Betiği çalıştırma

Betiği çalıştırın:

- Bir bağlantı kurmak ve eşlemek üzere yeni ekipler oluşturmak için [bu betiği çalıştırın](#set-up-a-connection-and-create-new-teams-to-map).
- Bağlantı kurmak ve mevcut ekiplere eşlemek için [bu betiği çalıştırın](#set-up-a-connection-and-map-to-existing-teams).

Betik aşağıdaki eylemleri gerçekleştirir. Kurulum ve yapılandırma ayrıntılarını girmeniz istenir.

1. Girdiğiniz Blue Yonder WFM hizmet hesabı kimlik bilgilerini ve hizmet URL'lerini kullanarak Blue Yonder WFM bağlantısını test eder ve doğrular.
1. Vardiyalar bağlayıcısını yapılandırıyor.
1. Eşitleme ayarlarını uygular. Bu ayarlar arasında eşitleme sıklığı (dakika cinsinden) ve Blue Yonder WFM ile Vardiyalar arasında eşitlenen zamanlama verileri bulunur. Zamanlama verileri aşağıdaki parametrelerde tanımlanır:

    - **enabledConnectorScenarios** parametresi, Blue Yonder WFM'dan Shifts'e eşitlenen verileri tanımlar. Seçenekler şunlardır: `Shift`, `SwapRequest`, `UserShiftPreferences``OpenShift`, , `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
    - **enabledWfiScenarios** parametresi, Shifts ile Blue Yonder WFM eşitlenen verileri tanımlar. Seçenekler : `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    Daha fazla bilgi için bkz. [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance). Her parametre için desteklenen eşitleme seçeneklerinin listesini görmek için [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) komutunu çalıştırın.

    > [!IMPORTANT]
    > Betik, tüm bu seçenekler için eşitlemeyi etkinleştirir. Eşitleme ayarlarını değiştirmek istiyorsanız, bağlantı kurulduktan sonra bunu yapabilirsiniz. Daha fazla bilgi edinmek için bkz. [PowerShell kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-powershell-manage.md).

1. Bağlantıyı oluşturur.
1. Mavi Yonder WFM örneklerini ekiplerle eşler. Eşlemeler, çalıştırdığınız betike bağlı olarak girdiğiniz Mavi Yonder WFM örnek kimliklerini ve oluşturduğunuz yeni takımları temel alır. Bir ekibin mevcut bir zamanlaması varsa betik, belirttiğiniz tarih ve saat aralığı için zamanlama verilerini kaldırır.

Ekrandaki Başarılı iletisi bağlantınızın başarıyla ayarlandığını gösterir.

## <a name="manage-your-connection"></a>Bağlantınızı yönetme

Bağlantı kurulduktan sonra, Microsoft 365 yönetim merkezi veya PowerShell kullanarak bu bağlantıyı yönetebilir ve bu bağlantıda değişiklik yapabilirsiniz.

### <a name="use-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanma

Bağlayıcı Yönetimi sayfasında, ayarladığınız her bağlantının yanı sıra sistem durumu ve eşitleme aralığı ayrıntıları gibi bilgiler listelenir. Bağlantılarınızdan herhangi birinde değişiklik yapmak için sihirbaza da erişebilirsiniz. Örneğin, eşitleme ayarlarını ve ekip eşlemelerini güncelleştirebilirsiniz.

Daha fazla bilgi edinmek için bkz. [Microsoft 365 yönetim merkezi kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-blue-yonder-admin-center-manage.md).

### <a name="use-powershell"></a>PowerShell kullanma

PowerShell'i kullanarak hata raporunu görüntüleyebilir, bağlantı ayarlarını değiştirebilir, eşitlemeyi devre dışı bırakabilir ve daha fazlasını yapabilirsiniz. Adım adım yönergeler için bkz. [PowerShell kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-powershell-manage.md).

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
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $BlueYonderId `
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
    -ConnectorId $BlueYonderId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
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
#Map WFM sites to existing teams script
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
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate `
    -Name $InstanceName `
    -ConnectorId $BlueYonderId `
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
        })
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
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
    -ConnectorId $BlueYonderId `
    -ConnectorAdminEmail $AdminEmailList `
    -DesignatedActorId $teamsUserId `
    -EnabledConnectorScenario $enabledConnectorScenario `
    -EnabledWfiScenario $wfiSupportedScenario `
    -Name $InstanceName `
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
- [PowerShell kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management](shifts-connector-powershell-manage.md)
- [Microsoft 365 yönetim merkezi kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management](shifts-connector-blue-yonder-admin-center-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams PowerShell'e genel bakış](/microsoftteams/teams-powershell-overview)
- [Teams PowerShell cmdlet başvurusu](/powershell/teams/intro)
