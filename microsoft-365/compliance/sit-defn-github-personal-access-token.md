---
title: GitHub kişisel erişim belirteci varlık tanımı
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
ms.openlocfilehash: 9a887ec28d5e90ffc61a16a2a1975aa2d6f8e366
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504050"
---
# <a name="github-personal-access-token"></a>GitHub kişisel erişim belirteci

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

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

## <a name="credential-example"></a>Kimlik bilgisi örneği 

`pat=ghp_abcdefghijklmnopqrstuvwxyzABCD012345`

## <a name="checksum"></a>Sağlama Toplamı

Evet

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

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
