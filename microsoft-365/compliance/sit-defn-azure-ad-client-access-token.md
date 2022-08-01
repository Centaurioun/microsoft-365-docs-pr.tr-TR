---
title: Azure AD istemci erişim belirteci varlık tanımı (önizleme)
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
description: Azure AD istemci erişim belirteci hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a59848511cde3778c373f55c18e794e81db1f80e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948474"
---
# <a name="azure-ad-client-access-token-preview"></a>Azure AD istemci erişim belirteci (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 10.000 karakterden oluşan bir birleşim.

veya

OAuth2.0 protokolünde kullanılan bir istemci gizli dizisi veya yenileme belirteci.

veya

Harf, rakam ve özel karakterlerden oluşan en fazla 1.000 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Herhangi bir bileşimi:
 
- en fazla 10.000 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- En fazla 2
- eşittir işaretleri (=)

örneğin:

`"VersionProfile": null, "TokenCache": { "CacheData": 
"AgAAAAIAAACZAWh0dHBzOi8vbG9naW4ubWljcm9zb2`

veya

Değişken istemci gizli anahtarı veya yenileme belirteci biçimleri; örneğin <br> 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

veya

3 harf: eyJ (büyük/küçük harfe duyarlı)

Ve

En fazla 1.000 karakterden oluşan bir birleşim

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- alt çizgiler (_)
- veya noktalar (.)

örneğin:

`eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MXVwYyIsImtpZCI6Ing0Nzh4`



## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, Azure kaynaklarına verilen izinleri tanımlamak için [Azure Active Directory B2C'de](/azure/active-directory-b2c/active-directory-b2c-access-tokens) (Azure AD B2C) kullanabileceği talepleri içeren güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Azure PowerShell Belirteci Önbelleği Desenleri
- İstemci gizli bağlamı desenleri
- Json Web Belirteci Desenleri
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri
- Sözlük sözlüğü

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.



## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- tokencache

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- Gizli
- Belirte -ci
- Auth
- Securestring
- Anahtar

### <a name="keyword_jsonwebtoken"></a>Keyword_JsonWebToken:

- eyJ

