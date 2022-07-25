---
title: Azure depolama hesabı anahtarı varlık tanımı
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
description: Azure depolama hesabı anahtarına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 6cea53a555a03fa1007e20b89078e02bd612bfc9
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989441"
---
# <a name="azure-storage-account-key"></a>Azure depolama hesabı anahtarı

## <a name="format"></a>Biçim

Dizenin `DefaultEndpointsProtocol` ardından aşağıdaki desende belirtilen karakterler ve dizeler (dizesi `AccountKey`dahil) vardır.

## <a name="pattern"></a>Desen

- dize `DefaultEndpointsProtocol`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- 1-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- dize `AccountKey`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- küçük veya büyük harf, rakam, eğik çizgi (/) veya artı işareti (+) olan 86 karakterden oluşan herhangi bir birleşim
- iki eşittir işareti (=)

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureStorageAccountKey` , desenle eşleşen içeriği bulur.
- Normal ifade `CEP_AzureEmulatorStorageAccountFilter` , desenle eşleşen içeriği bulmaz.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

Bu hassas bilgi türü, bu anahtar sözcükleri anahtar sözcük listesi değil normal bir ifade kullanarak tanımlar.

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

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