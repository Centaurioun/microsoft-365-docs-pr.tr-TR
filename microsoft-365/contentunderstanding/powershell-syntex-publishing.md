---
title: PowerShell ile özel modeller yayımlama
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: medium
description: PowerShell kullanarak Microsoft Syntex özel modellerini yayımlamayı öğrenin.
ms.openlocfilehash: 46724246d1a4c85676f1722c643968a09f843c79
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68661317"
---
# <a name="publish-custom-models-with-powershell"></a>PowerShell ile özel modeller yayımlama

<sup>**Şunlar için geçerlidir:**  &ensp; Tüm özel modelleri &#10003;</sup>

> [!IMPORTANT]
> Microsoft Syntex PowerShell cmdlet'leri ve diğer tüm PnP bileşenleri, destek sağlayan etkin bir topluluk tarafından desteklenen açık kaynak araçlardır. Resmi Microsoft destek kanallarından açık kaynak araç desteği için SLA yoktur.

Syntex modelleri genellikle kiracınızdaki belge kitaplıklarına dağıtılır. Bu, içerik merkezi sitesi kullanılarak yapılabilir, ancak bu makalede açıklandığı gibi [PnP PowerShell](https://pnp.github.io/powershell/) kullanılarak da yapılabilir.

## <a name="listing-the-available-models-in-a-content-center"></a>İçerik merkezinde kullanılabilir modelleri listeleme

Geçerli Syntex içerik merkezi sitesine eklenen modellere genel bir bakış elde etmek için [Get-PnPSyntexModel cmdlet'ini](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html) kullanın:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>Kitaplığa model uygulama

Bir kitaplığa model uygulamak için [Publish-PnPSyntexModel cmdlet'ini](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html) kullanın:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>Modelin nerede kullanıldığını anlama

Bir modeli birçok kitaplıkta dağıttıktan sonra, modelinizi kullanarak kitaplık listesini gözden geçirmek isteyebilirsiniz. Bu, [Get-PnPSyntexModelPublication](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html) cmdlet'i kullanılarak yapılabilir:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>Bir modeli kitaplıktan kaldırma

Bir modeli kitaplıktan kaldırmak, uygulama ile aynı deseni izler ve [Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) cmdlet'i etkileşimli olarak veya birden çok eylem toplu işlemi olarak kullanılabilir.

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>Modelleri toplu olarak uygulama

Birden çok kitaplıkta birden çok model yayımlamak istiyorsanız modelleri ve hedef konumları listeleyen bir giriş CSV dosyası oluşturun:

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

Bu CSV dosyası daha sonra, listelenen modelleri uygun kitaplıklarda yayımlayacak bir betikte giriş olarak kullanılabilir. Aşağıdaki örnekte, isteklerin verimliliğini artırmak için toplu işlem kullanılır.

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourSite"
$targetsCSV = "./Publish-SyntexModelBulk.csv"

Connect-PnPOnline -url $contentCenterURL

$targetLibraries = Import-Csv -Path $targetsCSV

$batch = New-PnPBatch

foreach ($target in $targetLibraries) {
    Publish-PnPSyntexModel -Model $target.ModelName -TargetSiteUrl $target.TargetSiteUrl -TargetWebServerRelativeUrl $target.TargetWebServerRelativeUrl -TargetLibraryServerRelativeUrl $target.TargetLibraryServerRelativeUrl -Batch $batch
}

Invoke-PnPBatch -Batch $batch
```
