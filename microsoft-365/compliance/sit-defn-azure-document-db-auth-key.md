---
title: Azure DocumentDB kimlik doğrulama anahtarı varlık tanımı
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
description: Azure DocumentDB kimlik doğrulaması anahtarına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: e499d185b0a1752960f71f659a212aa0422154f4
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948443"
---
# <a name="azure-documentdb-auth-key"></a>Azure DocumentDB kimlik doğrulaması anahtarı

## <a name="format"></a>Biçim

`DocumentDb` Dize ve ardından aşağıdaki desende belirtilen karakterler ve dizeler.

## <a name="pattern"></a>Desen

- Dize `DocumentDb`
- 3-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- Büyüktür simgesi (>), eşittir işareti (=), tırnak işareti (") veya kesme işareti (')
- 86 küçük veya büyük harf, basamak, eğik çizgi (/) veya artı işareti (+) birleşimi
- İki eşittir işareti (=)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureDocumentDBAuthKey` , desenle eşleşen içeriği bulur.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

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
