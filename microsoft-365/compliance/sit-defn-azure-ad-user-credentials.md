---
title: Azure AD kullanıcı kimlik bilgileri varlık tanımı (önizleme)
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
description: Azure AD kullanıcı kimlik bilgilerine duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 5b27f2a5c700770df65be74f0cebb23351de77bc
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948470"
---
# <a name="azure-ad-user-credentials-preview"></a>kullanıcı kimlik bilgilerini Azure AD (önizleme)

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


## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Active Directory'de](/azure/active-directory/fundamentals/active-directory-users-reset-password-azure-portal) kimlik doğrulaması yapmak için bireysel kullanıcı parolaları olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Azure AD kiracı için düz metin kullanıcı adı ve parola desenleri.
- Koddaki Parola bağlamı desenleri.
- XML'de Parola bağlamı desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.


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

