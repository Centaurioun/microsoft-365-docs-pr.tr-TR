---
title: Azure IoT bağlantı dizesi varlık tanımı (önizleme)
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
description: Azure IoT bağlantı dizesi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 89d2ab0170000285dc2c274f50ff9a5106b5bc59
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948942"
---
# <a name="azure-iot-connection-string-preview"></a>Azure IoT bağlantı dizesi (önizleme)

### <a name="format"></a>Biçim

Dizenin `HostName` ardından, ve dizeleri de dahil olmak üzere aşağıdaki desende özetlenen karakterler ve `SharedAccessKey`dizeler bulunur`azure-devices.net`.

## <a name="pattern"></a>Desen

- dize `HostName`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- 1-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- "azure-devices.<!--no-hyperlink-->net"
- 1-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- dize `SharedAccessKey`
- sıfırdan iki boşluk karakterine
- eşittir işareti (=)
- sıfırdan iki boşluk karakterine
- 43 küçük veya büyük harf, basamak, eğik çizgi (/) veya artı işareti (+) birleşimi
- eşittir işareti (=)

## <a name="checksum"></a>Sağlama toplamı

Hayır

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_AzureIoTConnectionString` , desenle eşleşen içeriği bulur.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
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
