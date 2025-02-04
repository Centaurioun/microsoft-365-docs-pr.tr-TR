---
title: Azure yayımlama ayarı parola varlığı tanımı
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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Azure yayımlama ayarı parolaya duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: bb26108257a1105d5a3ce1a90bf30fc1b39fe252
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68298704"
---
# <a name="azure-publish-setting-password"></a>Azure yayımlama ayarı parolası

### <a name="format"></a>Biçim

Dize `userpwd=` ve ardından alfasayısal dize.

### <a name="pattern"></a>Desen

- dize `userpwd=`
- 60 küçük harf veya basamak birleşimi
- tırnak işareti (")

### <a name="checksum"></a>Sağlama Toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- Normal ifade `CEP_Regex_AzurePublishSettingPasswords` , desenle eşleşen içeriği bulur.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Anahtar Sözcükler

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

Bu hassas bilgi türü, bu anahtar sözcükleri anahtar sözcük listesi değil normal bir ifade kullanarak tanımlar.

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->Net
