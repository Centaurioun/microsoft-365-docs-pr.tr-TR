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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Azure AD istemci erişim belirteci hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 4a5a61d66316f4dda84d9f3fe93b2ffe113d5d78
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475979"
---
# <a name="azure-ad-client-access-token-preview"></a>Azure AD istemci erişim belirteci (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

Örneğin değişken istemci gizli dizisi veya yenileme belirteci biçimleri. <br> 
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



## <a name="checksum"></a>Sağlama Toplamı

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

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.



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

