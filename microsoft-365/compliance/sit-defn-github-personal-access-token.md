---
title: GitHub kişisel erişim belirteci varlık tanımı (önizleme)
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
description: GitHub kişisel erişim belirteci hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 65106dfc50be2335106a2b8e53f9fc9e5518b8bf
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68378544"
---
# <a name="github-personal-access-token-preview"></a>GitHub kişisel erişim belirteci (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 40 karakterden oluşan bir birleşim.

veya

URL'de kullanılan eşleştirilmiş kullanıcı adı ve parola.

veya

Harf ve rakamlardan oluşan 40 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

- 'ghp_', 'gho_', 'ghu_', 'ghs_' veya 'ghr_' belirteç ön eki (büyük/küçük harfe duyarlı)
- 36'nın herhangi bir bileşimi 
- a-z (büyük/küçük harfe duyarlı değil) veya 0-9

örneğin:

`ghp_abcdefghijklmnopqrstuvwxyzABCD012345`

veya

Çeşitli URL kullanıcı adı ve parola biçimleri örneğin:
 
`https://username:********@contoso.com/` <br>

`ftp://username:********@contoso.com:20/`<br>


veya

40 karakterden oluşan bir birleşim:

- a-f veya A-F (büyük/küçük harfe duyarlı) veya 0-9

örneğin:

`abcdef0123456789abcdef0123456789abcdef01`

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [GitHub API'sini veya komut satırını](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) kullanırken GitHub kimlik doğrulaması için alternatif parola olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Tanımlanabilir GitHub PAT desenleri.
- URL'deki Kullanıcı Oturum Açma Kimlik Bilgilerinin Desenleri.
- Onaltılık kodlanmış 160 bit Simetrik Anahtar desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_githubpatidentifiablesecret"></a>Keyword_GitHubPatIdentifiableSecret:

- gh_

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl:

- ://

### <a name="keyword_symmetrickey160hex"></a>Keyword_SymmetricKey160Hex:

- Belirte -ci
