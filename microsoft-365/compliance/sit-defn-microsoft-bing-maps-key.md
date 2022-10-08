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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Microsoft Bing, önemli hassas bilgi türü varlık tanımını eşler.
ms.openlocfilehash: 7af473418a192eb6d27236cbe4eaa02c1954b20a
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68381511"
---
# <a name="microsoft-bing-maps-key-preview"></a>Microsoft Bing haritalar anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 64 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

64 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- alt çizgiler (_) veya kısa çizgiler (-)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDEabcdefghijklmnopqrstu`

## <a name="checksum"></a>Sağlama Toplamı

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
