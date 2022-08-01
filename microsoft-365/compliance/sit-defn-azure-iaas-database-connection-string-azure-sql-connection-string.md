---
title: Azure IAAS veritabanı bağlantı dizesi ve Azure SQL bağlantı dizesi varlık tanımı
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
description: Azure IAAS veritabanı bağlantı dizesi ve Azure SQL bağlantı dizesi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 894a849c318ad15ab9baac8343192428d633ce1b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948538"
---
# <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS veritabanı bağlantısı dizesi ve Azure SQL bağlantısı dizesi

## <a name="format"></a>Biçim

dize `Server`veya `server`veya ile dize veya veya `data source` dahil olmak üzere `cloudapp.azure.net` `cloudapp.azure.com` `database.windows.net`, aşağıdaki desende belirtilen karakter ve dizelerin ardından , veya dizesi `Password` veya .`pwd``password`

## <a name="pattern"></a>Desen

- , `server`veya dizesi `Server``data source`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- 1-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net" veya "database.windows.<!--no-hyperlink-->net"
- 1-300 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- , `password`veya dizesi `Password``pwd`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- noktalı virgül (;), tırnak işareti (") veya kesme işareti (') olmayan bir veya daha fazla karakter
- noktalı virgül (;), tırnak işareti (") veya kesme işareti (')

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureConnectionString` , desenle eşleşen içeriği bulur.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

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
