---
title: Özel bir model tarafından işleme isteğinde bulunmak için PowerShell kullanma
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
description: Microsoft Syntex özel modeli tarafından işleme isteğinde bulunmak için PowerShell'i kullanmayı öğrenin.
ms.openlocfilehash: b28bc8945c4704354d351185a5ff2cf1c72031ea
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662083"
---
# <a name="use-powershell-to-request-processing-by-a-custom-model"></a>Özel bir model tarafından işleme isteğinde bulunmak için PowerShell kullanma

<sup>**Şunlar için geçerlidir:**  &ensp; Tüm özel modelleri &#10003;</sup>

> [!IMPORTANT]
> Microsoft Syntex PowerShell cmdlet'leri ve diğer tüm PnP bileşenleri, destek sağlayan etkin bir topluluk tarafından desteklenen açık kaynak araçlardır. Resmi Microsoft destek kanallarından açık kaynak araç desteği için SLA yoktur.

Özel modeller, yeni yüklenen dosyaları kitaplığa işler. Kullanıcı arabiriminde işlemeyi el ile istemek de mümkündür. Ancak PowerShell aracılığıyla işlemeyi tetiklemenin daha verimli olduğu senaryolar olabilir.

## <a name="request-processing-of-all-items-that-havent-been-previously-classified"></a>Daha önce sınıflandırılmamış tüm öğelerin işlenmesini isteme

Bu komutu kullanarak kitaplıktaki daha önce sınıflandırılmamış tüm öğeler için işleme isteğinde bulunabilirsiniz:

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

Düşük öncelikli işleme için, kiracınızın bulunduğu iş saatleri dışında işlenmek üzere dosyaları kuyruğa alan -OffPeak parametresini de kullanmayı düşünebilirsiniz. Daha fazla bilgi için bkz [. Request-PnPSyntexClassifyAndExtract](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html).

## <a name="request-processing-of-all-items-in-a-library"></a>Kitaplıktaki tüm öğelerin işlenmesini isteme

Daha önce sınıflandırılmış olsalar bile kitaplıktaki tüm dosyaların işlenmesini isteyebilirsiniz. Bu adım, bir modeli güncelleştirdiyseniz veya kitaplığa başka bir model eklediyseniz yararlı olabilir.

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents" -Force
```

> [!NOTE]
> -Force seçeneğinin 5000'den fazla öğeyle kullanılması otomatik olarak yoğun olmayan işlemeyi etkinleştirir.

## <a name="request-processing-of-all-items-based-on-a-property"></a>Bir özelliğe göre tüm öğelerin işlenmesini isteme

İşlemeyi bir kitaplıktaki öğelerin belirli bir alt kümesiyle sınırlamak istiyorsanız, belirli bir dosya grubunu seçmek için betik kullanabilirsiniz. Aşağıdaki örnekte betik, bir alanın seçilmesine ve filtreleme ölçütü olarak bir alan değerine izin verir. [Get-PnPListItem](https://pnp.github.io/powershell/cmdlets/Get-PnPListItem.html) kullanılarak daha karmaşık sorgular tamamlanabilir.

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"
$list = Get-PnPList -Identity "Documents"
# Set the field name to filter items by
$fieldName = "Vendor"
# Set the field value to filter by
$fieldFilter = "Fabrikam"

$listItems = (Get-PnPListItem -List $list -fields $fieldName).fieldValues
$targetItems = $listItems | Where-Object -Property Provider -EQ -Value $fieldFilter

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
foreach ($listItem in $targetItems) {
    Request-PnPSyntexClassifyAndExtract -FileUrl $listItem.FileRef -Batch $classifyBatch
}

# Execute batch
Invoke-PnPBatch -Batch $batch
```

## <a name="request-processing-of-specific-files"></a>Belirli dosyaların işlenmesini isteme

belirli dosyalar için işleme de istenebilir.

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx"
```

Dosya modeline göre dosya, toplu işlemi de destekler:

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx" -Batch $batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/relecloud contract.docx" -Batch $batch

# Execute batch
Invoke-PnPBatch -Batch $batch
```
