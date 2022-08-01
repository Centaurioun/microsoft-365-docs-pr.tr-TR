---
title: IP adresi varlık tanımı
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
description: IP adresi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 19c883cccdc45682514bcd553f1b8e4a09d90e12
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948686"
---
# <a name="ip-address"></a>IP adresi

## <a name="format"></a>Biçim

### <a name="ipv4"></a>IPv4:
IPv4 adreslerinin biçimlendirilmiş (dönemler) ve biçimlendirilmemiş (noktasız) sürümlerini hesaplayan karmaşık desen

### <a name="ipv6"></a>IPv6:
Biçimlendirilmiş IPv6 sayılarını (iki nokta üst üste dahil) hesaplayan karmaşık desen

## <a name="pattern"></a>Desen

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

IPv6 için bir DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının yüksek güveni vardır:

- Normal ifade `Regex_ipv6_address` , desenle eşleşen içeriği bulur.
- anahtar `Keyword_ipaddress` sözcüğü bulunamadı.

IPv4 için, bir DLP ilkesi, 300 karaktere yakınsa bu tür hassas bilgiler algılamıştır:

- Normal ifade `Regex_ipv4_address` , desenle eşleşen içeriği bulur.
- 'den `Keyword_ipaddress` bir anahtar sözcük bulunur.

IPv6 için bir DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının yüksek güveni vardır:

- Normal ifade `Regex_ipv6_address` , desenle eşleşen içeriği bulur.
- anahtar `Keyword_ipaddress` sözcüğü bulunamadı.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (bu anahtar sözcük büyük/küçük harfe duyarlıdır)
- ip adresi
- ip adresleri
- internet protokolü
- IP-כתובת ה