---
title: Azure SAS varlık tanımı
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
description: Azure SAS hassas bilgi türü varlık tanımı.
ms.openlocfilehash: c7d63497a94204b77f83c5b357700311bf332e8c
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948617"
---
# <a name="azure-sas"></a>Azure SAS

## <a name="format"></a>Biçim

`sig` Dize ve ardından aşağıdaki desende belirtilen karakterler ve dizeler.

## <a name="pattern"></a>Desen

- dize `sig`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- küçük veya büyük harf, rakam veya yüzde işareti (%) olan 43-53 karakter arasında herhangi bir birleşim
- dize `%3d`
- küçük veya büyük harf, rakam veya yüzde işareti (%) olmayan herhangi bir karakter

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureSAS` , desenle eşleşen içeriği bulur.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```
