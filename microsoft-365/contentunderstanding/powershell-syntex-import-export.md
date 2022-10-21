---
title: PowerShell ile yapılandırılmamış belge işleme modellerini dışarı ve içeri aktarma
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
description: Microsoft Syntex'te PowerShell ile modelleri dışarı ve içeri aktarma hakkında bilgi edinin.
ms.openlocfilehash: 975a4f463d80c273f31912c30c70c5e7c07fd6c9
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662105"
---
# <a name="export-and-import-unstructured-document-processing-models-with-powershell"></a>PowerShell ile yapılandırılmamış belge işleme modellerini dışarı ve içeri aktarma

<sup>**Şunlar için geçerlidir:**  &ensp; Yapılandırılmamış belge işlemeyi &#10003;</sup>

> [!IMPORTANT]
> Microsoft Syntex PowerShell cmdlet'leri ve diğer tüm PnP bileşenleri, destek sağlayan etkin bir topluluk tarafından desteklenen açık kaynak araçlardır. Resmi Microsoft destek kanallarından açık kaynak araç desteği için SLA yoktur.

Syntex modelleri PnP şablonları olarak dışarı aktarılabilir ve böylece içerik merkezleri veya kiracılar arasında yeniden kullanılabilir.

## <a name="export-all-models-in-a-content-center"></a>İçerik merkezindeki tüm modelleri dışarı aktarma

bir içerik merkezindeki tüm yapılandırılmamış belge işleme modellerini tek bir PnP şablonuna aktarmak için aşağıdaki [PnP PowerShell](https://pnp.github.io/powershell/) cmdlet'lerini kullanın:

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>Belirli modelleri dışarı aktarma

Belirli yapılandırılmamış belge işleme modellerini bir içerik merkezinden PnP şablonuna aktarmak için aşağıdaki [PnP PowerShell](https://pnp.github.io/powershell/) cmdlet'lerini kullanın:

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

extract.json, hangi modelleri dışarı aktarmak istediğinizi tanımlar ve modeli ada veya kimliğe göre belirtmeye ve isteğe bağlı olarak eğitim verilerini ayıklamamak için yapılandırmaya olanak tanır.

### <a name="example---specify-model-by-name"></a>Örnek - Modeli ada göre belirtme

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "name": "Sample - benefits change notice.classifier"
            }
        ]
    }
}
```

### <a name="example---specify-model-by-id"></a>Örnek - Model kimliğine göre belirtme

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "id": 3,
                "excludeTrainingData": true
            }
        ]
    }
}
```

"includeTrainingData" özelliğini dahil etmezseniz, varsayılan davranış eklemektir.

> [!NOTE]
> Modelin hedef içerik merkezine aktarıldığında düzenlenebilir olması için eğitim verileri gereklidir.

## <a name="import-models-to-a-content-center"></a>Modelleri içerik merkezine aktarma

PnP şablonlarına aktarılmış yapılandırılmamış belge işleme modelleri herhangi bir kiracıdaki bir içerik merkezine aktarılabilir. Dışarı aktarma işlemi eğitim verilerini de içerdiyse, model içeri aktarıldıktan sonra düzenlenebilir.

Modeli içeri aktarmak için aşağıdaki komutları kullanın:

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
