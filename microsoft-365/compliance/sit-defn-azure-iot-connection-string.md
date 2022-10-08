---
title: Azure IoT bağlantı dizesi varlık tanımı
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
description: Azure IoT bağlantı dizesi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 555ea8bd8a96afc46d5078e7fe30703ed86c8f92
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68506334"
---
# <a name="azure-iot-connection-string"></a>Azure IoT bağlantı dizesi

#<a name="this-sit-is-also-included-in-the-all-credentials-bundled-sit"></a>Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Dizenin `HostName` ardından, ve dizeleri de dahil olmak üzere aşağıdaki desende özetlenen karakterler ve `SharedAccessKey`dizeler bulunur`azure-devices.net`.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

## <a name="credential-example"></a>Kimlik bilgisi örneği 

`HostName=account.azure-devices.net;SharedAccessKeyName=key;SharedAccessKey=abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

### <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

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
