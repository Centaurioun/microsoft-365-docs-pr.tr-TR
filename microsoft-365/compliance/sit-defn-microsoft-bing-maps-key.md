---
title: Microsoft Bing haritalar anahtar varlık tanımı (önizleme)
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
description: Microsoft Bing, önemli hassas bilgi türü varlık tanımını eşler.
ms.openlocfilehash: 6f25ec9716be33a0e2bbe404f12742dddad89250
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989534"
---
# <a name="microsoft-bing-maps-key-preview"></a>Microsoft Bing haritalar anahtarı (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 64 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

64 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- alt çizgiler (_) veya kısa çizgiler (-)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDEabcdefghijklmnopqrstu`

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Bing Haritalar API'sini](/bingmaps/getting-started/bing-maps-dev-center-help/getting-a-bing-maps-key) çağırmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 URL kodlu 384 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey384url"></a>Keyword_SymmetricKey384Url:

- virtualearth
- api/haritalar
- Anahtar
