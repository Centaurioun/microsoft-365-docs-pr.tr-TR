---
title: Genel parola varlığı tanımı (önizleme)
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
description: Genel parolaya duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 39a789fed5d0cf1467da4be0e05324dea3d5a12d
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476759"
---
# <a name="general-password-preview"></a>Genel Parola (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

En fazla 20.000 karakterlik harf, rakam ve özel karakter birleşimi.

veya

Komut satırlarında kullanılan oturum açma kimlik bilgileri

veya

Kod parçacıklarında kullanılan düz metin parolası

veya

Betikte kullanılan düz metin parolası

veya

XML yapılandırmasında kullanılan düz metin parolası

veya

Harf, rakam ve özel karakterlerden oluşan 24 karakterden oluşan bir birleşim.

veya

Harf ve rakamlardan oluşan 32 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 32 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

veya

Harflerin, basamakların ve özel karakterlerin 88 karakterlik birleşimi.

## <a name="pattern"></a>Desen

Şunlardan oluşan 20.000 karaktere kadar herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarsız)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- En fazla iki eşittir işareti (=)

örneğin:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

veya

Çeşitli komut satırı oturum açma kimlik bilgileri biçimleri, örneğin: 

`-u username:********`

veya

`-u username -p ********`

veya

`/f ... /p ********`

veya

`-Password ********`

veya

`-U username%********`

veya

`-secrets:********`

örneğin:

`zDbg.DataPuller.exe -secrets:eyJ`

veya

Kod parçacıklarındaki çeşitli parola biçimleri, örneğin:

`new X509Certificates2(`

veya

`ConvertTo-SecureString -String ********`

veya

`password = "********"`

veya

`"password" : "********"`

veya

`UserPasswordCredential(`

örneğin:

`password = "ZYXWVU_1";`

veya

Betikteki çeşitli parola biçimleri, örneğin:

`password = ********`

örneğin:

`password=ZYXWVU_1`

veya

XML'deki çeşitli parola biçimleri, örneğin:

```xml
<secret>********</secret>
<password>********</password>
<setting name="password" value="********" >
<setting name="password">********</setting>
<setting name="password"><value>********</value></setting>
```

örneğin:

`<secret>ZYXWVU_1</secret>`

veya

Şunlardan oluşan 22 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarsız)
- basamaklar, eğik çizgi veya artı işaretleri
- iki eşit işaretle biter (=)

örneğin:

`abcdefgh0123456789/+AB==`

veya

Şunlardan oluşan 32 karakterden oluşan herhangi bir birleşim:

- a-f veya A-F (büyük/küçük harfe duyarlı) veya 0-9

örneğin:

`abcdef0123456789abcdef0123456789`

veya

Şunlardan oluşan 32 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarsız)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)

örneğin:

`abcdefghijklmnopqr0123456789/+AB`

veya

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarsız)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- eşittir işaretiyle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

veya

Şunlardan oluşan 86 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarsız)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- iki eşit işaretle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="description"></a>Açıklama

Bu SIT, genel oturum açma işlemi [kullanıcı oturum açma işleminde](/azure/key-vault/quick-create-portal) kullanılan kullanıcı adları ve parolalar gibi güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. Birkaç birincil kaynak kullanır:

- Base64 kodlanmış dize değişmez değeri desenleri.
- Komut satırında Parola bağlamı desenleri.
- Koddaki Parola bağlamı desenleri.
- Betikteki Parola bağlamı desenleri.
- XML'de Parola bağlamı desenleri.
- Base64 kodlu 128 bit simetrik anahtarın desenleri.
- Onaltılık kodlanmış 128 bit simetrik anahtar desenleri.
- Base64 kodlu 192 bit simetrik anahtarın desenleri.
- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözcük dağarcığı sözcükleri sözlüğü.


Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral

- Mıı

### <a name="keyword_passwordcontextincmdline"></a>Keyword_PasswordContextInCmdLine

- Certutil
- zdbg
- Gizli
- VSTS_TOKEN
- Curl
- PowerShell
- ps1
- -U
- Smc
- Otomatik Oturum Açma
- Ldifde
- Rclone
- --Env
- SignTool
- Winexe
- Net

## <a name="keyword_passwordcontextincode"></a>Keyword_PasswordContextInCode

- Anahtar
- x509c
- Kimlik bilgisi
- Parola
- Pw
- Securestring

### <a name="keyword_passwordcontextinscript"></a>Keyword_PasswordContextInScript

- Gizli
- Parola
- Pw

### <a name="keyword_passwordcontextinxml"></a>Keyword_PasswordContextInXml

- userpass
- Parola
- Pw
- Connectionstring
- Anahtar
- Kimlik bilgisi
- Belirte -ci
- Sas
- Gizli

### <a name="keyword_symmetrickey128"></a>Keyword_SymmetricKey128

- Gizli
- Anahtar
- Parola
- Pw

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex

- Demir
- Anahtar
- Gizli
- Belirte -ci
- Parola
- Pw

### <a name="keyword_symmetrickey192"></a>Keyword_SymmetricKey192

- Parola
- -P
- azurecr

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512

- SharedAccessKey
- AccountKey
