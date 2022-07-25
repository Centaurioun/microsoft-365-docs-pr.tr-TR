---
title: Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP) varlık tanımı
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
description: Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 806f7e9b0d2dd797b17ad848d160c6f74c04e1e2
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989537"
---
# <a name="mexico-unique-population-registry-code-curp"></a>Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP)

## <a name="format"></a>Biçim

18 karakterli alfasayısal desen

## <a name="pattern"></a>Desen

- dört harf (büyük/küçük harfe duyarsız)
- geçerli bir tarihi gösteren altı basamak
- a letter - H/h veya M/m
- Geçerli bir Meksika eyalet kodunu gösteren iki harf
- üç harf
- bir harf veya rakam
- bir basamak

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_mexico_population_registry_code` , desenle eşleşen içeriği bulur.
- 'den `Keyword_mexico_population_registry_code` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_mexico_population_registry_code` , desenle eşleşen içeriği bulur.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Benzersiz Nüfus Kayıt Defteri Kodu
- benzersiz nüfus kodu
- CURP
- Kişisel Kimlik
- Benzersiz Kimlik
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave kişisel Identidad
- kişisel Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad