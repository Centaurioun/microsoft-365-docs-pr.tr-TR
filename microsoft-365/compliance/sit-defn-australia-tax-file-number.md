---
title: Avustralya vergi dosya numarası varlık tanımı
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
description: Avustralya vergi dosya numarası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 155bdbd2142d0c6c097907b0ab651ff74cfac46d
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948813"
---
# <a name="australia-tax-file-number"></a>Avustralya vergi dosyası numarası

## <a name="format"></a>Biçim

sekiz ila dokuz basamak

## <a name="pattern"></a>Desen

sekiz ila dokuz basamak genellikle aşağıdaki gibi boşluklarla gösterilir:

- üç basamak
- isteğe bağlı bir alan
- üç basamak
- isteğe bağlı bir alan
- son basamak bir denetim basamağı olduğunda iki ile üç basamak

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev Func_australian_tax_file_number desenle eşleşen içeriği bulur.
- Keyword_Australia_Tax_File_Number veya Keyword_number_exclusions anahtar sözcüğü bulunamadı.
- Sağlama toplamı geçer.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- avustralya iş numarası
- marjinal vergi oranı
- medicare levy
- portföy numarası
- hizmet gazileri
- stopaj vergisi
- bireysel vergi iadesi
- vergi dosyası numarası
- Tfn
