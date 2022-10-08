---
title: Kullanıcı oturum açma kimlik bilgileri varlık tanımı (önizleme)
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
description: Kullanıcı oturum açma kimlik bilgileri hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 36c18f64531256013d4866a7e52afdbd16f40e00
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68472310"
---
# <a name="user-login-credentials-preview"></a>Kullanıcı oturum açma kimlik bilgileri (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Genel kimlik doğrulama işleminde kullanılan eşleştirilmiş kullanıcı adı ve parola.

veya

PuTTY bağlantı yöneticisinde kullanılan eşleştirilmiş kullanıcı adı ve parola.

veya

Kod parçacıklarında kullanılan düz metin parolası.

veya

Harf, rakam ve özel karakterlerden oluşan 88 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Çeşitli kullanıcı adı ve parola biçimleri, örneğin:
 
`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>

veya

```xml
An XML element <login>
An embeded XML element <login>
Inner XML content
An embeded XML element </login>
An embeded XML element <password>
Inner XML content
An embeded XML element </password>
An XML element </login>
```

örneğin

`<login> <login>ZYXWVU_1</login> <password>ZY…`

veya

Kod parçacıklarındaki çeşitli parola biçimleri, örneğin:

`new X509Certificates2(` <br>
`ConvertTo-SecureString -String ********` <br>
`password = "********"` <br>
`"password" : "********"`<br>
`UserPasswordCredential(` <br>

veya

86 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- iki eşit işaretle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, genel [kullanıcı oturum açma işleminde](/azure/key-vault/quick-create-portal) kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Düz metin kullanıcı adı ve parola desenleri.
- PuTTYcm veritabanı dosyasında düz metin kullanıcı adı ve parola desenleri.
- Koddaki Parola bağlamı desenleri.
- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- Parola
- Pw
- Db_

### <a name="keyword_logincredentialsputty"></a>Keyword_LoginCredentialsPutty:

- Oturum açma

### <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode:

- Anahtar
- x509c
- Kimlik bilgisi
- Parola
- Pw
- Securestring

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
