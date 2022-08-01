---
title: Azure SQL bağlantı dizesi varlık tanımı (önizleme)
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
description: bağlantı dizesine duyarlı bilgi türü varlık tanımını Azure SQL.
ms.openlocfilehash: 7091c50d96f22370358f5743a3992a10025ea29f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948506"
---
# <a name="azure-sql-connection-string-preview"></a>Azure SQL bağlantı dizesi (önizleme)

## <a name="format"></a>Biçim

En fazla 20.000 karakterlik harf, rakam ve özel karakter birleşimi.

veya

Genel kimlik doğrulama işleminde kullanılan bir çift kullanıcı adı ve parola.


## <a name="pattern"></a>Desen

Şunlardan oluşan 20.000 karaktere kadar herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- En fazla 2
- eşittir işaretleri (=)

örneğin: 

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM`

veya

Değişken kullanıcı adı ve parola biçimleri, örneğin:

`username=...;password=********;` <br>
`user id=...;password=********;` <br>
`uid=...;pwd=********;` <br>
`DB_USER=...;DB_PASS=********;` <br>
`Service Account=...;Password=********;` <br>


## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [Azure SQL Veritabanlarına](/azure/sql-database/sql-database-aad-authentication-configure) bağlanmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.

Birkaç birincil kaynak kullanır:

- Base64 kodlanmış dize değişmez değeri desenleri.
- Düz metin kullanıcı adı ve parola desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- MII

### <a name="keyword_logincredentials"></a>Keyword_LoginCredentials:

- Parola
- Pw
- DB_
