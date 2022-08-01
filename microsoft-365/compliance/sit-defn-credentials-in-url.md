---
title: URL'de Crednetial
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
description: URL hassas bilgi türü varlık tanımındaki kimlik bilgileri.
ms.openlocfilehash: f7a363539ec9bdd7fa0ddaab30ac7e2d20afb69b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948545"
---
# <a name="credentials-in-url"></a>URL'deki kimlik bilgileri

## <a name="format"></a>Biçim

URL'de kullanılan eşleştirilmiş kullanıcı adı ve parola

veya

Betikte kullanılan düz metin parolası

## <a name="pattern"></a>Desen

Çeşitli URL kullanıcı adı ve parola biçimleri, örneğin: 

`https://username:********@contoso.com/...`
`ftp://username:********@contoso.com:20/...`

örneğin: `https://myuser:mypassword@localhost`

veya

Betikteki çeşitli parola biçimleri, örneğin: 

`password = ********...`

örneğin:

`password=ZYXWVU_1`

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="description"></a>Açıklama

Bu SIT, istemci doğrulama veya [kullanıcı oturum açma işlemini](/azure/key-vault/quick-create-portal) tanımlamak için URL'de belirteç olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. Birkaç birincil kaynak kullanır:

- URL'deki Kullanıcı Oturum Açma Kimlik Bilgilerinin Desenleri.
- Betikteki Parola bağlamı desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_logincredentialsinurl"></a>Keyword_LoginCredentialsInUrl

- ://

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- Gizli
- Parola
- Pw
