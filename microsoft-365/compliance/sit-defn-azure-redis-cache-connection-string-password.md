---
title: Azure Redis cache bağlantı dizesi parola varlık tanımı (önizleme)
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
description: Azure Redis önbellek bağlantı dizesi parolaya duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d65ec7a901b7e703279aec4d290718927f09e0d6
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476740"
---
# <a name="azure-redis-cache-connection-string-password-preview"></a>Azure Redis önbellek bağlantı dizesi parolası (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 20.000 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 20.000 karaktere kadar herhangi bir birleşim: 
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- En fazla 2
- eşittir işaretleri (=)

örneğin: 

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

veya

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- eşittir işaretiyle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [Redis için Azure Cache sunuculara](/azure/azure-cache-for-redis/) bağlanmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlanmış dize değişmez değeri desenleri.
- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- Mıı

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey
