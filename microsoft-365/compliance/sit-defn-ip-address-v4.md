---
title: IP adresi v4 varlık tanımı
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
description: IP adresi v4 hassas bilgi türü varlık tanımı.
ms.openlocfilehash: e145b4342c5b276b66d0ed463a2094b7ada47b01
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948690"
---
# <a name="ip-address-v4"></a>IP Adresi v4

## <a name="format"></a>Biçim

IPv4 adreslerinin biçimlendirilmiş (dönemler) ve biçimlendirilmemiş (noktasız) sürümlerini hesaplayan karmaşık desen.

## <a name="pattern"></a>Desen

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `Regex_ipv4_address` , desenle eşleşen içeriği bulur.
- 'den `Keyword_ipaddress` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- Normal ifade `Regex_ipv4_address` , desenle eşleşen içeriği bulur.

```xml
      <!-- IP Address v4-->
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (büyük/küçük harfe duyarlı)
- ip adresi
- ip adresleri
- internet protokolü
- IP-כתובת ה