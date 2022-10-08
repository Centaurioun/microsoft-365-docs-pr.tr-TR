---
title: X.509 sertifikası özel anahtar varlık tanımı (önizleme)
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
description: X.509 sertifikası özel anahtar hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 144eff9826dcbb3bcfc03930442a4d4e3a36e22c
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476143"
---
# <a name="x509-certificate-private-key-preview"></a>X.509 sertifika özel anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 20.000 karakterden oluşan bir birleşim.

veya

Büyük harf, boşluk ve kısa çizgilerden oluşan en fazla 40 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

En fazla 20.000 karakterden oluşan bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)

En fazla iki eşittir işareti (==)

örneğin:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

veya

beş tire (-)

En fazla 30 karakterden oluşan bir birleşim:

- A-Z (büyük/küçük harfe duyarlı) 
- Boşluk
- 5 tire (-)

örneğin:

`-----BEGIN PRIVATE KEY-----`


## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [SSL sertifikalarında](/azure/key-vault/certificate-scenarios) özel bileşen olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlanmış dize değişmez değeri desenleri.
- Sertifika özel anahtar üst bilgisinin desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- Mıı

### <a name="keyword_certificateprivatekeyheader"></a>Keyword_CertificatePrivateKeyHeader:

- Anahtar
