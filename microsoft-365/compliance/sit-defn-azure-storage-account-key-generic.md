---
title: Azure Depolama hesabı anahtarı (genel) varlık tanımı
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Azure Depolama hesabı anahtarı (genel) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 88139dfe26e654e664d74e8543ea791fd171da63
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948530"
---
# <a name="azure-storage-account-key-generic"></a>Azure Depolama hesabı anahtarı (genel)

## <a name="format"></a>Biçim

86 küçük veya büyük harf, rakam, eğik çizgi (/) veya artı işareti (+) birleşimi, aşağıdaki desende ana hatlarıyla belirtilen karakterlerden önce veya takip eder.

## <a name="pattern"></a>Desen

- sıfır ile büyüktür simgesinden birine (>), kesme işareti ('), eşittir işareti (=), tırnak işareti (") veya sayı işareti (#)
- küçük veya büyük harf, basamak, eğik çizgi (/) veya artı işareti (+) olan 86 karakterden oluşan herhangi bir birleşim
- iki eşittir işareti (=)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureStorageAccountKeyGeneric` , desenle eşleşen içeriği bulur.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```