---
title: Google API anahtar varlık tanımı
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
description: Google API anahtarı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 399823a0d41c213de2c0a7ac87bee37a7bea6db0
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68505414"
---
# <a name="google-api-key"></a>Google API anahtarı

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 39 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Belirteç ön eki (büyük/küçük harfe duyarlı) 'AIza'

35 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- alt çizgiler (_) veya ters eğik çizgiler (\)

örneğin:

`AIzaefgh0123456789_-ABCDEFGHIJKLMNOPQRS`

## <a name="credential-example"></a>Kimlik bilgisi örneği 

`apiKey=AIzaefgh0123456789_-ABCDEFGHIJKLMNOPQRS;`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

## <a name="definition"></a>Tanım

Bu SIT, api isteklerini projenizle kota ve faturalama için ilişkilendirmek için kullanılan hiçbir sorumlusu olmayan bir [Google REST API istemcisini](https://cloud.google.com/docs/authentication/api-keys) tanımlayan basit bir şifrelenmiş dize olarak kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlu 210 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey210"></a>Keyword_SymmetricKey210:

- AIza
