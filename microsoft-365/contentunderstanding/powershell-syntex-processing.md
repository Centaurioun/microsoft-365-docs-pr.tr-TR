---
title: Belge anlama modeliyle işleme isteğinde bulunmak için PowerShell kullanma
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
description: SharePoint Syntex belge anlama modeliyle işlem isteğinde bulunmak için PowerShell'i kullanmayı öğrenin.
ms.openlocfilehash: a0806910e268585f27f320e541bb8f30c2bec7db
ms.sourcegitcommit: cbb9a89499d42f4a029e18780bee408946e1671d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68026018"
---
# <a name="use-powershell-to-request-processing-by-a-document-understanding-model"></a>Belge anlama modeliyle işleme isteğinde bulunmak için PowerShell kullanma

> [!IMPORTANT]
> SharePoint Syntex PowerShell cmdlet'leri ve diğer tüm PnP bileşenleri, bunlar için destek sağlayan etkin bir topluluk tarafından desteklenen açık kaynak araçlardır. Resmi Microsoft destek kanallarından açık kaynak araç desteği için SLA yoktur.

Belge anlama modelleri, kitaplığa yeni yüklenen dosyaları işler. Kullanıcı arabiriminde işlemeyi el ile istemek de mümkündür. Ancak, PowerShell aracılığıyla işlemeyi tetiklemenin daha verimli olduğu senaryolar olabilir.

## <a name="request-processing-of-all-items-that-have-not-been-previously-classified"></a>Daha önce sınıflandırılmamış tüm öğelerin işlenmesini isteme

Bu komutu kullanarak kitaplıktaki daha önce sınıflandırılmamış tüm öğeler için işleme isteğinde bulunabilirsiniz:

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

Düşük öncelikli işleme için, kiracınızın bulunduğu iş saatleri dışında işlenmek üzere dosyaları kuyruğa alan -OffPeak parametresini de kullanmayı düşünebilirsiniz. Diğer ayrıntılar için bkz. [Request-PnPSyntexClassifyAndExtract](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html) .

## <a name="request-processing-of-all-items-in-a-library"></a>Kitaplıktaki tüm öğelerin işlenmesini isteme

Daha önce sınıflandırılmış olsalar bile kitaplıktaki tüm dosyaların işlenmesini isteyebilirsiniz. Bu, bir modeli güncelleştirdiyseniz veya kitaplığa başka bir model eklediyseniz yararlı olabilir.

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
