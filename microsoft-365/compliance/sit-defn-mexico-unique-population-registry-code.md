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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 20afce26f7769e1a322c21109a8b934dbf14ca3d
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384085"
---
# <a name="mexico-unique-population-registry-code-curp"></a>Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair yüksek düzeyde güvene sahiptir:

- İşlev `Func_mexico_population_registry_code`, desenle eşleşen içeriği bulur.
- `Keyword_mexico_population_registry_code` içinden bir anahtar sözcük bulundu.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığına dair orta düzeyde güvene sahiptir:

- İşlev `Func_mexico_population_registry_code`, desenle eşleşen içeriği bulur.

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
