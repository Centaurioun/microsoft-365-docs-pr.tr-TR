---
title: İstemci gizli dizisi / API anahtarı varlık tanımı (önizleme)
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
description: İstemci gizli dizisi / API anahtarına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 25bd50de2193abaa926d09475cc9ff537432fc62
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66989382"
---
# <a name="client-secret--api-key-preview"></a>İstemci gizli anahtarı / API anahtarı (önizleme)

## <a name="format"></a>Biçim

OAuth 2.0 protokolünde kullanılan bir istemci gizli dizisi veya yenileme belirteci.

veya

Harf, rakam ve özel karakterlerden oluşan 24 karakterden oluşan bir birleşim.

veya

Harf ve rakamlardan oluşan 32 karakterden oluşan bir birleşim.

veya

Harf ve rakamlardan oluşan 40 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 56 karakterden oluşan bir birleşim

veya

Harf, rakam ve özel karakterlerden oluşan 88 karakterden oluşan bir birleşim.


## <a name="pattern"></a>Desen

Çeşitli istemci gizli dizisi veya yenileme belirteci biçimleri örneğin:
 
`ClientSecret:********` <br>
`AppSecret=********` <br>
`ConsumerKey:=********` <br>
`Refresh_Token:********` <br>

veya

22 karakterden oluşan bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- basamaklar, eğik çizgi veya artı işaretleri
- iki eşit işaretle biter (=)

örneğin:

`abcdefgh0123456789/+AB==`

veya

32 karakterden oluşan bir birleşim:

- a-f veya A-F (büyük/küçük harfe duyarlı)
- veya 0-9

örneğin:

`abcdef0123456789abcdef0123456789`

veya

40 karakterden oluşan bir birleşim:

- a-f veya A-F (büyük/küçük harfe duyarlı)

veya

- 0-9

örneğin:

`abcdef0123456789abcdef0123456789abcdef01`

veya

43 karakterden oluşan bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- eşittir işaretiyle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

veya

54 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- iki eşit işaretle biter (==)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

veya

86 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- iki eşit işaretle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`


## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, yalnızca OAuth uygulaması ve çalışma zamanında erişim belirteci [değişimi için yetkilendirme sunucusuyla](/azure/active-directory/develop/active-directory-how-applications-are-added) bilinen güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- İstemci gizli bağlamının desenleri.
- Base64 kodlu 128 bit simetrik anahtarın desenleri.
- Onaltılık kodlanmış 128 bit simetrik anahtar desenleri.
- Onaltılık kodlanmış 160 bit Simetrik Anahtar desenleri.
- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- Base64 kodlu 320 bit simetrik anahtarın desenleri.
- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_clientsecretcontext"></a>Keyword_ClientSecretContext:

- Gizli
- Belirte -ci
- Auth
- Securestring
- Anahtar

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128:

- Gizli
- Anahtar
- Parola
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- Demir
- Anahtar
- Gizli
- Belirte -ci
- Parola
- Pw

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- Belirte -ci

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- Anahtar

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
