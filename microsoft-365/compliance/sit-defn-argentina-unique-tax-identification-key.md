---
title: Arjantin Benzersiz Vergi Tanımlama Anahtarı (CUIT/CUIL) varlık tanımı
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
description: Arjantin Benzersiz Vergi Tanımlama Anahtarı (CUIT/CUIL) hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d38cb0a972add240087c816399abf30d3d9ef670
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948705"
---
# <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Arjantin Benzersiz Vergi Tanımlama Anahtarı (CUIT/CUIL)

## <a name="format"></a>Biçim

Tireli 11 basamak

## <a name="pattern"></a>Desen

Tireli 11 basamak:

- 20, 23, 24, 27, 30, 33 veya 34'te iki basamak
- kısa çizgi (-)
- sekiz basamak
- kısa çizgi (-)
- bir denetim basamalı

## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- İşlev `Func_Argentina_Unique_Tax_Key` , desenle eşleşen içeriği bulur.
- 'den `Keyword_Argentina_Unique_Tax_Key` bir anahtar sözcük bulunur.

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgiler algılandığının orta düzeyde güvenilirliğine sahiptir:

- İşlev `Func_Argentina_Unique_Tax_Key` , desenle eşleşen içeriği bulur.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- benzersiz iş gücü tanımlama kodu
- Clave Única de Identificación Tributaria
- benzersiz iş kimliği kodu
- CUİL
- Benzersiz Vergi Tanımlama Anahtarı
- Benzersiz İş Gücü Kimlik Anahtarı
- Benzersiz İşgücü Anahtarı Belirleme
- Benzersiz İş Tanımlama Kodu
- Benzersiz İş Kodu Tanımlaması
- Benzersiz İş Tanımlama Anahtarı
- Benzersiz İş Anahtarı Belirleme
- Benzersiz Vergi Kodu Belirleme
- Vergi Tanımlamanın Benzersiz Anahtarı
- Benzersiz İşgücü Tanımlama Kodu
- Benzersiz İşgücü Kimlik Kodu
- Benzersiz İşgücü Tanımlama Anahtarı
- Benzersiz İşgücü Anahtarı Belirleme
- vergi kimliği
- taxID #
- taxId
- taxidnumber
- vergi numarası
- vergi no
- Vergi #
- Vergi #
- vergi mükellefi kimliği
- vergi mükellefi numarası
- vergi mükellefi hayır
- Vergi mükellefi #
- Vergi mükellefi #
- vergi kimliği
- vergi belirleme
- Número de Identificación Fiscal
- número de contribuyente