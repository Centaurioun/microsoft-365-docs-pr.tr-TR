---
title: PowerShell'de model açıklamalarını anlama belgesiyle çalışma
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: medium
description: PowerShell'de Microsoft Syntex belge anlama modeli açıklamalarıyla çalışma hakkında bilgi edinin.
ms.openlocfilehash: c2ffc7493e91adc4e990da56e5a29408121eded2
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564706"
---
# <a name="work-with-document-understanding-model-explanations-in-powershell"></a>PowerShell'de model açıklamalarını anlama belgesiyle çalışma

> [!IMPORTANT]
> Microsoft Syntex PowerShell cmdlet'leri ve diğer tüm PnP bileşenleri, destek sağlayan etkin bir topluluk tarafından desteklenen açık kaynak araçlardır. Resmi Microsoft destek kanallarından açık kaynak araç desteği için SLA yoktur.

Özel açıklama şablonları, içerik merkezi içindeki bir listede depolanır. Bu açıklamalar liste öğeleri olarak depolandığından, PowerShell bunlarla etkileşime geçmek için kullanılabilir.

## <a name="list-saved-explanations"></a>Kaydedilen açıklamaları listeleme

Bu örnekte, belirli bir içerik merkezine kaydedilmiş tüm özel açıklama şablonlarının nasıl görüntülendiği gösterilmektedir.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list and items
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"
$explanations = Get-PnPListItem -List $explanationTemplatesList -Fields "Id", "Title", "ExplanationName", "ExplanationType", "ExplanationDescription","ExplanationContent"

# Extract explanation components
$explanationValues = $explanations.fieldvalues 
$explanationOutput = @()

foreach ($explanation in $explanationValues) {
    $content = $explanation.ExplanationContent
    $content = $content.replace('false','"false"')
    $content = $content.replace('true','"true"')
    $contentArray = $content | ConvertFrom-Json

    $output = New-Object -TypeName PSObject
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Name" -Value $explanation.ExplanationName
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Description" -Value $explanation.ExplanationDescription
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Explanation Type" -Value $contentArray.kind
    Add-Member -InputObject $output -MemberType NoteProperty -Name "RegEx Pattern" -Value $contentArray.pattern
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Phrase List" -Value $contentArray.ngrams
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Case Sensitive" -Value $contentArray.caseSensitive
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Ignore Digit Identity" -Value $contentArray.ignoreDigitIdentity
    Add-Member -InputObject $output -MemberType NoteProperty -Name "Ignore Letter Identity" -Value $contentArray.ignoreLetterIdentity

    $explanationOutput += $output
}

$explanationOutput
```

## <a name="create-a-phrase-list-explanation"></a>Tümcecik listesi açıklaması oluşturma

Bu örnekte özel tümcecik listesi açıklama şablonunun nasıl oluşturulacağı gösterilmektedir.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$explanationName = "Phrase Explanation A"
$explanationDescription = "This is my explanation"
$phrases = "Phrase 1", "Phrase 2"
$caseSensitive = $false
$ignoreDigitIdentity= $false
$ignoreLetterIdentity = $false

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

#Format phrase list
$phrases = $phrases -join "`",`""

#Convert booleans to lower case strings
$caseSensitive = ($caseSensitive.ToString()).ToLower()
$ignoreDigitIdentity= ($ignoreDigitIdentity.ToString()).ToLower()
$ignoreLetterIdentity = ($ignoreLetterIdentity.ToString()).ToLower()

# Build explanation content
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"dictionaryFeature`",`"name`":`"$explanationName`",`"active`":true,`"nGrams`":[`"$phrases`"],`"caseSensitive`":$caseSensitive,`"ignoreDigitIdentity`":$ignoreDigitIdentity,`"ignoreLetterIdentity`":$ignoreLetterIdentity}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```

## <a name="create-a-regular-expression-explanation"></a>Normal ifade açıklaması oluşturma

Bu örnekte özel bir normal ifade açıklama şablonunun nasıl oluşturulacağı gösterilmektedir.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$explanationName = "RegEx Explanation A"
$explanationDescription = "This is my explanation"
$pattern = "\b(https?):\/\/\S+"

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

# Build explanation content
$pattern = $pattern.Replace('\','\\')
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"regexFeature`",`"name`":`"$explanationName`",`"active`":true,`"pattern`":`"$pattern`"}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```

## <a name="create-a-phrase-list-explanation-based-on-a-term-set"></a>Terim kümesini temel alan tümcecik listesi açıklaması oluşturma

Bu örnekte, bir terim kümesindeki değerleri alarak özel tümcecik listesi açıklama şablonunun nasıl oluşturulacağı gösterilmektedir. Bu, tercih edilen terim adlarını ve tüm eş anlamlıları içerir.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourContentCenter"
$termSetName = "Terms"
$termGroupName = "GroupA"
$explanationName = "MMS Explanation A"
$explanationDescription = "This is my explanation"
$caseSensitive = $false
$ignoreDigitIdentity= $false
$ignoreLetterIdentity = $false

# Connect to content center
Connect-PnPOnline -url $contentCenterURL

# Load explanation templates list
$explanationTemplatesList = Get-PnPList -Identity "/Explanations"

#Generate GUID for explanation
$guid = New-Guid

#Get term set, including preferred labels and synonyms
$terms = Get-PnPTerm -TermGroup $termGroupName -TermSet $termSetName -Includes Labels
$phrases = $terms.labels.value

#Format phrase list
$phrases = $phrases -join "`",`""

#Convert booleans to lower case strings
$caseSensitive = ($caseSensitive.ToString()).ToLower()
$ignoreDigitIdentity= ($ignoreDigitIdentity.ToString()).ToLower()
$ignoreLetterIdentity = ($ignoreLetterIdentity.ToString()).ToLower()

# Build explanation content
$explanationContent = "{`"id`":`"$guid`",`"kind`":`"dictionaryFeature`",`"name`":`"$explanationName`",`"active`":true,`"nGrams`":[`"$phrases`"],`"caseSensitive`":$caseSensitive,`"ignoreDigitIdentity`":$ignoreDigitIdentity,`"ignoreLetterIdentity`":$ignoreLetterIdentity}"

# Create item in explanation list
Add-PnPListItem -List $explanationTemplatesList -Values @{"Title"= $explanationName; "ExplanationName" = $explanationName; "ExplanationDescription" = $explanationDescription; "ExplanationContent" = $explanationContent}
```
