---
title: VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler
ms.openlocfilehash: e0a31ee619ecc072ce62b7e893526d48b37078fd
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67681919"
---
# <a name="special-considerations-for-stream-and-live-events-in-vpn-environments"></a>VPN ortamlarında Akış ve canlı etkinlikler için özel dikkat edilmesi gerekenler

>[!NOTE]
>Bu makale, uzak kullanıcılar için Microsoft 365 iyileştirmesini ele alan bir makale kümesinin parçasıdır.

>- Uzak kullanıcılar için Microsoft 365 bağlantısını iyileştirmek üzere VPN bölünmüş tünel kullanmaya genel bakış için bkz [. Genel Bakış: Microsoft 365 için VPN bölünmüş tünel oluşturma](microsoft-365-vpn-split-tunnel.md).
>- VPN bölünmüş tüneli uygulama hakkında ayrıntılı yönergeler için bkz. [Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md).
>- VPN bölünmüş tünel senaryolarının ayrıntılı listesi için bkz. [Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md).
>- VPN bölünmüş tünel ortamlarında Teams medya trafiğinin güvenliğini sağlama yönergeleri için bkz. [VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md).
>- Çin'deki kullanıcılar için Microsoft 365 dünya çapında kiracı performansını iyileştirme hakkında bilgi için bkz. [Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md).

Microsoft 365 Canlı Etkinlikler trafiği (Teams tarafından üretilen canlı etkinliklere katılanları ve Teams, Stream veya Yammer aracılığıyla bir dış kodlayıcıyla üretilenleri içerir) ve isteğe bağlı Akış trafiği şu anda [hizmetin URL/IP listesinde](urls-and-ip-address-ranges.md) **Varsayılan** ve **İyileştir** olarak kategorilere ayrılmıştır. Bu uç noktalar, diğer hizmetler tarafından da kullanılabilecek CDN'lerde barındırıldığından **Varsayılan** olarak kategorilere ayrılmıştır. Müşteriler genellikle bu tür trafiğe ara sunuculuk yapmak ve normalde bunlar gibi uç noktalara yapılan tüm güvenlik öğelerini uygulamayı tercih eder.

Birçok müşteri, yüksek hacimli ve gecikmeye duyarlı trafiği VPN altyapısı üzerinden yönlendirmek yerine kullanıcılarını doğrudan yerel internet bağlantılarından Stream/Live Events'e bağlamak için gereken URL/IP verilerini istedi. Genellikle, hem ayrılmış ad alanları hem de uç noktalar için doğru IP bilgileri olmadan bu mümkün değildir. Bu bilgiler **Varsayılan** olarak kategorilere ayrılmış Microsoft 365 uç noktaları için sağlanmaz.

Zorlamalı tünel VPN'i kullanan istemcilerden Stream/Live Events hizmeti için doğrudan bağlantıyı etkinleştirmek için aşağıdaki adımları kullanın. Bu çözüm, müşterilere evden çalışma senaryoları nedeniyle yüksek ağ trafiği varken Canlı Olaylar trafiğini VPN üzerinden yönlendirmekten kaçınma seçeneği sunmak için tasarlanmıştır. Mümkünse, inceleyen bir ara sunucu aracılığıyla hizmete erişmeniz önerilir.

>[!NOTE]
>Bu çözümü kullanarak, sağlanan IP adreslerine çözümlanmayan ve dolayısıyla VPN'yi geçen hizmet öğeleri olabilir, ancak akış verileri gibi yüksek hacimli trafiğin toplu olması gerekir. Canlı Etkinlikler/Akış kapsamı dışında bu yükten yakalanan başka öğeler de olabilir, ancak doğrudan gitmeden önce hem FQDN'yi hem de IP eşleşmesini karşılamaları gerektiğinden bunlar  sınırlı olmalıdır.

>[!IMPORTANT]
>Müşterilerin Canlı Etkinlikler için performans artışı üzerinden VPN'i atlayan daha fazla trafik gönderme riskini tartmaları önerilir.

Teams Live Events ve Stream için zorlamalı tünel özel durumunu uygulamak için aşağıdaki adımlar uygulanmalıdır:

## <a name="1-configure-external-dns-resolution"></a>1. Dış DNS çözümlemeyi yapılandırma

İstemcilerin, aşağıdaki ana bilgisayar adlarının IP adreslerine çözümlenebilmesi için dış, özyinelemeli DNS çözümlemesinin kullanılabilir olması gerekir.

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** Stream olayları için kullanılır ([kodlayıcıları Microsoft Stream canlı akış için yapılandırma - Microsoft Stream | Microsoft Docs](/stream/live-encoder-setup)).

**\*.media.azure.net** ve **\*.bmc.cdn.office.net** , Teams istemcisinden zamanlanan Teams tarafından üretilen Canlı Etkinlikler (Hızlı Başlangıç olayları RTMP-In desteklenen etkinlikler [Yol Haritası Kimliği 84960]) için kullanılır.

 Bu uç noktalardan bazıları Stream/Live Events dışındaki diğer öğelerle paylaşılır; VPN çözümünüzde teknik olarak mümkün olsa bile (örneğin, IP yerine FQDN'de çalışıyorsa) VPN boşaltmayı yapılandırmak için yalnızca bu FQDN'leri kullanmanız önerilmiyor.

FQDN'ler VPN yapılandırmasında gerekli değildir, yalnızca ILGILI trafiği doğrudan göndermek için IP'lerle birlikte PAC dosyalarında kullanım içindir.

## <a name="2-implement-pac-file-changes-where-required"></a>2. PAC dosyası değişikliklerini uygulama (gerektiğinde)

VPN'deyken trafiği bir ara sunucu üzerinden yönlendirmek için PAC dosyası kullanan kuruluşlarda bu normalde FQDN'ler kullanılarak gerçekleştirilir. Ancak, Stream/Live Events ile, sağlanan konak adları **.azureedge.net gibi\*** joker karakterler içerir ve tam IP listeleri sağlamanın mümkün olmadığı diğer öğeleri de kapsar. Bu nedenle, istek yalnızca DNS joker karakteri eşleşmesine göre doğrudan gönderilirse, bu uç noktalara giden trafik engellenir, aksi takdirde bu makalenin [sonraki 3. adımında](#3-configure-routing-on-the-vpn-to-enable-direct-egress) bu uç noktalara yönelik doğrudan yol üzerinden giden trafik engellenir.

Bunu çözmek için aşağıdaki IP'leri sağlayabilir ve [bunları 1. Adımda](#1-configure-external-dns-resolution) açıklandığı gibi örnek bir PAC dosyasındaki konak adlarıyla birlikte kullanabiliriz. PAC dosyası, URL'nin Stream/Live Events için kullanılanlarla eşleşip eşleşmediğini denetler ve eşleşiyorsa, bir DNS aramasından döndürülen IP'nin hizmet için sağlananlarla eşleşip eşleşmediğini de denetler. _Her ikisi de_ eşleşirse trafik doğrudan yönlendirilir. Herhangi bir öğe (FQDN/IP) eşleşmiyorsa, trafik ara sunucuya gönderilir. Sonuç olarak yapılandırma, hem IP hem de tanımlı ad alanlarının kapsamı dışında bir IP'ye çözümlenen her şeyin vpn üzerinden normal şekilde ara sunucudan geçişini sağlar.

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>GEÇERLI CDN Uç Noktaları listelerini toplama

Canlı Etkinlikler, müşterilere akış sağlamak, en iyi kapsamı, kaliteyi ve dayanıklılığı sağlamak için birden çok CDN sağlayıcısı kullanır. Şu anda hem Microsoft'tan hem de Verizon'dan Azure CDN kullanılmaktadır. Zaman içinde bu durum bölgesel kullanılabilirlik gibi durumlardan dolayı değiştirilebilir. Bu makale, IP aralıklarında güncel kalmanızı sağlayan bir kaynaktır.

Microsoft'tan Azure CDN için, Resmi [Microsoft İndirme Merkezi'nden Azure IP Aralıklarını ve Hizmet Etiketlerini – Genel Bulutu İndir](https://www.microsoft.com/download/details.aspx?id=56519) - listesinden listeyi indirebilirsiniz; JSON'da *AzureFrontdoor.Frontend* hizmet etiketine özel olarak bakmanız gerekir; *addressPrefixes* , IPv4/IPv6 alt ağlarını gösterir. Zaman içinde IP'ler değişebilir, ancak hizmet etiketi listesi kullanılmadan önce her zaman güncelleştirilir.

Verizon'dan Azure CDN (Edgecast) için [Edge Düğümleri - Liste](/rest/api/cdn/edge-nodes/list) ( **Dene'ye** tıklayın) kullanarak kapsamlı bir liste bulabilirsiniz.  **Özel olarak Premium\_Verizon**  bölümüne bakmanız gerekir. Bu API'nin tüm Edgecast IP'lerini (origin ve Anycast) gösterdiğini unutmayın. Şu anda API'nin kaynak ile Anycast arasında ayrım yapma mekanizması yoktur.

Bunu bir PAC dosyasında uygulamak için FQDN aracılığıyla Microsoft 365 En iyi duruma getirme trafiğini doğrudan (en iyi yöntem önerilir) ve FQDN ile döndürülen IP adresinin bir bileşimi aracılığıyla doğrudan kritik Akış/Canlı Olaylar trafiğini gönderen aşağıdaki örneği kullanabilirsiniz. Contoso yer tutucu adının _, contoso'nun_ contoso.onmicrosoft.com 

#### <a name="example-pac-file"></a>Örnek PAC dosyası

PAC dosyalarının nasıl oluşturulacağıyla ilgili bir örnek aşağıda verilmiştir:

1. Aşağıdaki betiği yerel sabit diskinize _Get-TLEPacFile.ps1_ olarak kaydedin.
1. [Verizon URL'sine](/rest/api/cdn/edge-nodes/list#code-try-0) gidin ve sonuçta elde edilen JSON dosyasını indirin (kopyalayıp cdnedgenodes.json gibi bir dosyaya yapıştırın)
1. Dosyayı betikle aynı klasöre yerleştirin.
1. PowerShell penceresinde aşağıdaki komutu çalıştırın. SPO URL'lerini istiyorsanız başka bir şey için kiracı adını değiştirin. Bu Tür 2 olduğundan **İyileştir** ve **İzin Ver** (Tür 1 yalnızca İyileştir'dir).

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac dosyası tüm ad alanlarını ve IP'leri (IPv4/IPv6) içerir.

##### <a name="get-tlepacfileps1"></a>Get-TLEPacFile.ps1

```powershell
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

<#PSScriptInfo

.VERSION 1.0.4

.AUTHOR Microsoft Corporation

.GUID 7f692977-e76c-4582-97d5-9989850a2529

.COMPANYNAME Microsoft

.COPYRIGHT
Copyright (c) Microsoft Corporation. All rights reserved.
Licensed under the MIT License.

.TAGS PAC Microsoft Microsoft365 365

.LICENSEURI

.PROJECTURI http://aka.ms/ipurlws

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

#>

<#

.SYNOPSIS

Create a PAC file for Microsoft 365 prioritized connectivity

.DESCRIPTION

This script will access updated information to create a PAC file to prioritize Microsoft 365 Urls for
better access to the service. This script will allow you to create different types of files depending
on how traffic needs to be prioritized.

.PARAMETER Instance

The service instance inside Microsoft 365.

.PARAMETER ClientRequestId

The client request id to connect to the web service to query up to date Urls.

.PARAMETER DirectProxySettings

The direct proxy settings for priority traffic.

.PARAMETER DefaultProxySettings

The default proxy settings for non priority traffic.

.PARAMETER Type

The type of prioritization to give. Valid values are 1 and 2, which are 2 different modes of operation.
Type 1 will send Optimize traffic to the direct route. Type 2 will send Optimize and Allow traffic to
the direct route.

.PARAMETER Lowercase

Flag this to include lowercase transformation into the PAC file for the host name matching.

.PARAMETER TenantName

The tenant name to replace wildcard Urls in the webservice.

.PARAMETER ServiceAreas

The service areas to filter endpoints by in the webservice.

.PARAMETER FilePath

The file to print the content to.

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type1.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance China -Type 2 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type2.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance WorldWide -Lowercase -TenantName tenantName -ServiceAreas Sharepoint

#>

#Requires -Version 2

[CmdletBinding(SupportsShouldProcess=$True)]
Param (
    [Parameter(Mandatory = $false)]
    [ValidateSet('Worldwide', 'Germany', 'China', 'USGovDoD', 'USGovGCCHigh')]
    [String] $Instance = "Worldwide",

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [guid] $ClientRequestId = [Guid]::NewGuid().Guid,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DirectProxySettings = 'DIRECT',

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DefaultProxySettings = 'PROXY 10.10.10.10:8080',

    [Parameter(Mandatory = $false)]
    [ValidateRange(1, 2)]
    [int] $Type = 1,

    [Parameter(Mandatory = $false)]
    [switch] $Lowercase = $false,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $TenantName,

    [Parameter(Mandatory = $false)]
    [ValidateSet('Exchange', 'SharePoint', 'Common', 'Skype')]
    [string[]] $ServiceAreas,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $FilePath,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $CdnEdgeNodesFilePath
)

##################################################################################################################
### Global constants
##################################################################################################################

$baseServiceUrl = "https://endpoints.office.com/endpoints/$Instance/?ClientRequestId={$ClientRequestId}"
$directProxyVarName = "direct"
$defaultProxyVarName = "proxyServer"
$bl = "`r`n"

##################################################################################################################
### Functions to create PAC files
##################################################################################################################

function Get-PacClauses
{
    param(
        [Parameter(Mandatory = $false)]
        [string[]] $Urls,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $ReturnVarName
    )

    if (!$Urls)
    {
        return ""
    }

    $clauses =  (($Urls | ForEach-Object { "shExpMatch(host, `"$_`")" }) -Join "$bl        || ")

@"
    if($clauses)
    {
        return $ReturnVarName;
    }
"@
}

function Get-PacString
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [array[]] $MapVarUrls
    )

@"
// This PAC file will provide proxy config to Microsoft 365 services
//  using data from the public web service for all endpoints
function FindProxyForURL(url, host)
{
    var $directProxyVarName = "$DirectProxySettings";
    var $defaultProxyVarName = "$DefaultProxySettings";

$( if ($Lowercase) { "    host = host.toLowerCase();" })

$( ($MapVarUrls | ForEach-Object { Get-PACClauses -ReturnVarName $_.Item1 -Urls $_.Item2 }) -Join "$bl$bl" )

$( if (!$ServiceAreas -or $ServiceAreas.Contains('Skype')) { Get-TLEPacConfiguration })

    return $defaultProxyVarName;
}
"@ -replace "($bl){3,}","$bl$bl" # Collapse more than one blank line in the PAC file so it looks better.
}

##################################################################################################################
### Functions to get and filter endpoints
##################################################################################################################

function Get-TLEPacConfiguration {
    param ()
    $PreBlock = @"
    // Don't Proxy Teams Live Events traffic

    if(shExpMatch(host, "*.azureedge.net")
    || shExpMatch(host, "*.bmc.cdn.office.net")
    || shExpMatch(host, "*.media.azure.net"))
    {
        var resolved_ip = dnsResolveEx(host);

"@
    $TLESb = New-Object 'System.Text.StringBuilder'
    $TLESb.Append($PreBlock) | Out-Null

    if (![string]::IsNullOrEmpty($CdnEdgeNodesFilePath) -and (Test-Path -Path $CdnEdgeNodesFilePath)) {
        $CdnData = Get-Content -Path $CdnEdgeNodesFilePath -Raw -ErrorAction SilentlyContinue | ConvertFrom-Json | Select-Object -ExpandProperty value | 
            Where-Object { $_.name -eq 'Premium_Verizon'} | Select-Object -First 1 -ExpandProperty properties | 
            Select-Object -ExpandProperty ipAddressGroups
        $CdnData | Select-Object -ExpandProperty ipv4Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
        $CdnData | Select-Object -ExpandProperty ipv6Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
    }
    $AzureIPsUrl = Invoke-WebRequest -Uri "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" -UseBasicParsing -ErrorAction SilentlyContinue  | 
            Select-Object -ExpandProperty Links | Select-Object -ExpandProperty href | 
            Where-Object { $_.EndsWith('.json') -and $_ -match 'ServiceTags' } | Select-Object -First 1
    if ($AzureIPsUrl) {
        Invoke-RestMethod -Uri $AzureIPsUrl -ErrorAction SilentlyContinue | Select-Object -ExpandProperty values | 
            Where-Object { $_.name -eq 'AzureFrontDoor.Frontend' } | Select-Object -First 1 -ExpandProperty properties |
            Select-Object -ExpandProperty addressPrefixes | ForEach-Object {
                if ($TLESb.Length -eq $PreBlock.Length) {
                    $TLESb.Append("        if(") | Out-Null
                }
                else {
                    $TLESb.AppendLine() | Out-Null
                    $TLESb.Append("        || ") | Out-Null
                }
                $TLESb.Append("isInNetEx(resolved_ip, `"$_`")") | Out-Null
            }
    }
    if ($TLESb.Length -gt $PreBlock.Length) {
        $TLESb.AppendLine(")") | Out-Null
        $TLESb.AppendLine("        {") | Out-Null
        $TLESb.AppendLine("            return $directProxyVarName;") | Out-Null
        $TLESb.AppendLine("        }") | Out-Null
    }
    else {
        $TLESb.AppendLine("        // no addresses found for service via script") | Out-Null
    }
    $TLESb.AppendLine("    }") | Out-Null
    return $TLESb.ToString()
}

function Get-Regex
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $Fqdn
    )

    return "^" + $Fqdn.Replace(".", "\.").Replace("*", ".*").Replace("?", ".?") + "$"
}

function Match-RegexList
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $ToMatch,

        [Parameter(Mandatory = $false)]
        [string[]] $MatchList
    )

    if (!$MatchList)
    {
        return $false
    }
    foreach ($regex in $MatchList)
    {
        if ($regex -ne $ToMatch -and $ToMatch -match (Get-Regex $regex))
        {
            return $true
        }
    }
    return $false
}

function Get-Endpoints
{
    $url = $baseServiceUrl
    if ($TenantName)
    {
        $url += "&TenantName=$TenantName"
    }
    if ($ServiceAreas)
    {
        $url += "&ServiceAreas=" + ($ServiceAreas -Join ",")
    }
    return Invoke-RestMethod -Uri $url
}

function Get-Urls
{
    param(
        [Parameter(Mandatory = $false)]
        [psobject[]] $Endpoints
    )

    if ($Endpoints)
    {
        return $Endpoints | Where-Object { $_.urls } | ForEach-Object { $_.urls } | Sort-Object -Unique
    }
    return @()
}

function Get-UrlVarTuple
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $VarName,

        [Parameter(Mandatory = $false)]
        [string[]] $Urls
    )
    return New-Object 'Tuple[string,string[]]'($VarName, $Urls)
}

function Get-MapVarUrls
{
    Write-Verbose "Retrieving all endpoints for instance $Instance from web service."
    $Endpoints = Get-Endpoints

    if ($Type -eq 1)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -eq "Optimize" })
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -ne "Optimize" }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
    elseif ($Type -eq 2)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -in @("Optimize", "Allow")})
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -notin @("Optimize", "Allow") }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
}

##################################################################################################################
### Main script
##################################################################################################################

$content = Get-PacString (Get-MapVarUrls)

if ($FilePath)
{
    $content | Out-File -FilePath $FilePath -Encoding ascii
}
else
{
    $content
}
```

Betik, Azure listesini **azurefrontdoor.frontend** dosyasının [indirme URL'sine](https://www.microsoft.com/download/details.aspx?id=56519) ve anahtarlarına göre otomatik olarak ayrıştırır, bu nedenle el ile almanıza gerek yoktur.

Ayrıca, yalnızca FQDN'leri kullanarak VPN boşaltması gerçekleştirmeniz önerilmiyor; işlevindeki **hem FQDN'lerin hem de** IP adreslerinin kullanılması, bu yük boşaltmanın kapsamını Canlı Etkinlikler/Akış gibi sınırlı bir uç nokta kümesiyle sınırlandırmaya yardımcı olur. İşlevin yapılandırılma şekli, FQDN için doğrudan istemci tarafından listelenenlerle eşleşen bir DNS araması yapılmasına neden olur; diğer bir deyişle, kalan ad alanlarının DNS çözümlemesi değişmeden kalır.

Canlı Etkinlikler ve Akış ile ilgili olmayan uç noktaları boşaltma riskini sınırlamak isterseniz, .azureedge.net etki alanını yapılandırmadan kaldırabilirsiniz. Bu, tüm Azure CDN müşterileri için kullanılan paylaşılan bir etki alanı olduğu için bu riskin büyük bir kısmının bulunduğu yapılandırmadan kaldırabilirsiniz **\***. Bunun dezavantajı, dış kodlayıcı kullanan herhangi bir etkinliğin iyileştirilmeyeceği ancak Teams'de üretilen/düzenlenen etkinliklerin olmasıdır.

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. Doğrudan çıkışı etkinleştirmek için VPN'de yönlendirmeyi yapılandırma

Son adım, trafiğin zorlamalı tünel üzerinden VPN'ye gönderilmediğinden emin olmak için **GEÇERLI CDN Uç Noktaları listelerini** VPN yapılandırmasına toplama bölümünde açıklanan Canlı Etkinlik IP'leri için doğrudan bir yol eklemektir. Microsoft 365 İyileştirme uç noktaları için bunun nasıl gerçekleştirileceği hakkında ayrıntılı bilgi, [Microsoft 365 için VPN bölünmüş tüneli uygulama'nın VPN bölünmüş tüneli](microsoft-365-vpn-implement-split-tunnel.md) uygulama bölümünde bulunabilir.[](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) İşlem, bu belgede listelenen Stream/Live Events IP'leri için tamamen aynıdır.

VPN yapılandırması için yalnızca [GEÇERLI CDN Uç Noktaları listelerini toplama bölümünden](#gathering-the-current-lists-of-cdn-endpoints) IP'lerin (FQDN'ler değil) kullanılması gerektiğini unutmayın.

## <a name="faq"></a>SSS

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>Bu işlem tüm trafiğimi doğrudan hizmete gönderir mi?

Hayır, bu bir Canlı Etkinlik veya Akış videosu doğrudan için gecikmeye duyarlı akış trafiği gönderir; yayımlanan IP'lere çözümlenmezse diğer tüm trafik VPN tünelini kullanmaya devam eder.

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>IPv6 Adreslerini kullanmam gerekiyor mu?

Hayır, bağlantı yalnızca gerektiğinde IPv4 olabilir.

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>Bu IP'ler neden Microsoft 365 URL/IP hizmetinde yayımlanmaz?

Microsoft, müşterilerin uç nokta kategorisine göre güvenli ve en iyi yönlendirmeyi uygulamak için bilgileri güvenilir bir şekilde kullanabilmesini sağlamak için hizmetteki bilgilerin biçimi ve türüyle ilgili sıkı denetimlere sahiptir.

**Varsayılan** uç nokta kategorisinde çok sayıda nedenden dolayı IP bilgisi sağlanmadı (Varsayılan uç noktalar Microsoft'un denetiminin dışında olabilir, çok sık değişebilir veya diğer öğelerle paylaşılan bloklarda olabilir). Bu nedenle Varsayılan uç noktalar, normal web trafiği gibi FQDN aracılığıyla incelenen bir ara sunucuya gönderilecek şekilde tasarlanmıştır.

Bu durumda, yukarıdaki uç noktalar Canlı Etkinlikler veya Stream dışında Microsoft tarafından denetlenmeyen öğeler tarafından kullanılabilecek CDN'lerdir ve bu nedenle trafiğin doğrudan gönderilmesi, bu IP'lere çözümlenen başka bir şeyin de istemciden doğrudan gönderileceği anlamına gelir. Mevcut küresel krizin benzersiz doğası ve müşterilerimizin kısa vadeli ihtiyaçlarını karşılamak için Microsoft, müşterilerin uygun gördükleri şekilde kullanabilmeleri için yukarıdaki bilgileri sağlamıştır.

Microsoft, Canlı Etkinlikler uç noktalarını gelecekte İzin Ver/İyileştir uç nokta kategorilerine dahil edilebilmeleri için yeniden yapılandırmaya çalışmaktadır.

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>Yalnızca bu IP'lere erişime izin vermem mi gerekiyor?

Hayır, HIZMETIN çalışması için [URL/IP hizmetindeki](urls-and-ip-address-ranges.md) **Gerekli** işaretli uç noktaların tümüne erişim önemlidir. Buna ek olarak, Stream (ID 41-45) için işaretlenmiş herhangi bir İsteğe bağlı uç nokta gereklidir.

### <a name="what-scenarios-will-this-advice-cover"></a>Bu öneri hangi senaryoları kapsar?

1. Teams Uygulamasında oluşturulan canlı etkinlikler
2. Stream'de barındırılan içeriği görüntüleme
3. Harici cihaz (kodlayıcı) tarafından üretilen olaylar

### <a name="does-this-advice-cover-presenter-traffic"></a>Bu öneri sunucu trafiğini kapsıyor mu?

Bunu yapmaz, yukarıdaki öneriler yalnızca hizmeti kullananlar içindir. Teams'in içinden sunum yapılırken sunucunun url/IP hizmeti satırı 11'de listelenen İşaretli UDP uç noktalarına akan trafiği ve [Microsoft 365 için](microsoft-365-vpn-implement-split-tunnel.md) [VPN bölünmüş tüneli uygulama bölümündeki AYRıNTıLı VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) boşaltma önerisi gösterilir.

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>Bu yapılandırma, Canlı Etkinlik &amp; Akışı dışındaki trafiğin doğrudan gönderilmesine neden oluyor mu?

Evet, hizmetin bazı öğeleri için kullanılan paylaşılan FQDN'ler nedeniyle bu kaçınılmazdır. Bu trafik normalde inceleme uygulayabilen bir şirket ara sunucusu aracılığıyla gönderilir. VPN bölünmüş tünel senaryosunda, hem FQDN'leri hem de IP'leri kullanmak bu riskin kapsamını en düşük düzeyde azaltacaktır, ancak yine de mevcut olacaktır. Müşteriler .azureedge.net etki alanını yük boşaltma yapılandırmasından kaldırabilir **\*** ve bu riski en aza indirebilir, ancak bu, Stream tarafından desteklenen Canlı Etkinliklerin (Teams tarafından zamanlanan, dış kodlayıcı olayları, Teams'de oluşturulan Yammer olayları, Yammer zamanlanmış dış kodlayıcı olayları ve Stream'den zamanlanmış etkinlikleri veya isteğe bağlı görüntüleme) yükünü kaldırır. Teams'te zamanlanan ve oluşturulan etkinlikler etkilenmez.

## <a name="related-articles"></a>İlgili makaleler

[Genel bakış: Microsoft 365 için VPN bölünmüş tüneli](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365 için VPN bölünmüş tüneli uygulama](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 için yaygın VPN bölünmüş tünel senaryoları](microsoft-365-vpn-common-scenarios.md)

[VPN bölünmüş tüneli için Teams medya trafiğinin güvenliğini sağlama](microsoft-365-vpn-securing-teams.md)

[Çin kullanıcıları için Microsoft 365 performans iyileştirmesi](microsoft-365-networking-china.md)

[Microsoft 365 Ağ Bağlantı İlkeleri](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ağ bağlantısını değerlendirme](assessing-network-connectivity.md)

[Microsoft 365 ağ ve performans ayarlama](network-planning-and-performance.md)

[Günümüzün benzersiz uzaktan çalışma senaryolarında modern güvenlik denetimleri elde etmek için güvenlik uzmanları ve BT için alternatif yollar (Microsoft Güvenlik Ekibi blogu)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft'ta VPN performansını geliştirme: otomatik bağlantılara izin vermek için Windows 10 VPN profillerini kullanma](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN üzerinde çalıştırma: Microsoft uzak iş gücünü nasıl bağlı tutuyor?](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft küresel ağı](/azure/networking/microsoft-global-network)
