---
title: İstemci erişim belirteci varlık tanımını Azure AD
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
ms.openlocfilehash: 99c60e5c6ff2f78b2bf4ecf610e860baea7f95d4
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503434"
---
# <a name="azure-ad-client-access-token"></a>Azure AD istemci erişim belirteci

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

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

`eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MX...`



## <a name="credential-example"></a>Kimlik bilgisi örneği 

`Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ing0Nzh4eU9wbHNNMUg3TlhrN1N4MTd4MX...`

> [!IMPORTANT]
> Bu örnek kesildi. Bu SIT'in algılanabilir bir örneği değildir.

## <a name="checksum"></a>Sağlama Toplamı

Evet

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

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

