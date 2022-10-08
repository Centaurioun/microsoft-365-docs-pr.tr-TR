---
title: Genel Simetrik anahtar varlık tanımı
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
description: Genel Simetrik anahtara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 827e23c31dcfcacd6121f3792d0b47cba7e29b0d
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68505432"
---
# <a name="general-symmetric-key"></a>Genel Simetrik anahtar

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 88 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

43 karakterden oluşan bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- eşittir işaretiyle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

veya

86 karakterden oluşan bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/) veya artı işaretleri (+)
- iki eşit işaretle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="credential-example"></a>Kimlik bilgisi örneği 

`key=abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=;`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

## <a name="definition"></a>Tanım

Bu SIT, [genel kimlik doğrulama işleminde](/dotnet/api/system.security.cryptography.aes?view=net-5.0) kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
