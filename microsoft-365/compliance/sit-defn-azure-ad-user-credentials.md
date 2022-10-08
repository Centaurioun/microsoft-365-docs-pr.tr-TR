---
title: kullanıcı kimlik bilgileri varlık tanımını Azure AD
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
description: Azure AD kullanıcı kimlik bilgilerine duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 80ae30fa7356c549a86d0bbbd053abca48143077
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504578"
---
# <a name="azure-ad-user-credentials"></a>Azure AD kullanıcı kimlik bilgileri

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

*.onmicrosoft.com etki alanıyla ilgili eşleştirilmiş kullanıcı adı ve parola.

veya

Kod parçacıklarında kullanılan düz metin parolası.

veya

XML yapılandırmasında kullanılan düz metin parolası.

## <a name="pattern"></a>Desen

Çeşitli kullanıcı adı ve parola biçimleri, örneğin:

`username=...password=********` <br>
`/user:.../pass:********` <br>
`SharePointOnlineAuthenticatedContext` <br>
`sign_in`<br>


veya

Kod parçacıklarındaki çeşitli parola biçimleri, örneğin:

`new X509Certificates2( ...` <br>
`ConvertTo-SecureString -String ********...`<br>
`password = "********"...` <br>
`"password" : "********"...` <br>
`UserPasswordCredential( ...` <br>

veya

XML'deki çeşitli parola biçimleri, örneğin:


```xml
... <secret>********</secret> ...
... <password>********</password> ...
... <setting name="password" value="********" > ... 
... <setting name="password">********</setting> ... 
... <setting name="password"><value>********</value></setting> ... 
```


## <a name="credential-example"></a>Kimlik bilgisi örneği 

`username=user@tenant.onmicrosoft.com;password=ZYXWVU$1;`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

## <a name="definition"></a>Tanım

Bu SIT, [Azure Active Directory'de](/azure/active-directory/fundamentals/active-directory-users-reset-password-azure-portal) kimlik doğrulaması yapmak için bireysel kullanıcı parolaları olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Azure AD kiracılar için düz metin kullanıcı adı ve parola desenleri.
- Koddaki Parola bağlamı desenleri.
- XML'de Parola bağlamı desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_azureactivedirectorylogincredentials"></a>Keyword_AzureActiveDirectoryLoginCredentials:

- Parola
- Pw
- userpass
- Kimlik bilgi -leri
- cmdkey
- Authenti
- sign_in

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- Anahtar
- x509c
- Kimlik bilgisi
- Parola
- Pw
- Securestring

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml:

- userpass
- Parola
- Pw
- Connectionstring
- Anahtar
- Kimlik bilgisi
- Belirte -ci
- Sas
- Gizli

