---
title: Azure İşlev Yöneticisi / API anahtarı varlık tanımı
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
description: Azure İşlev Yöneticisi / API anahtarına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: d16072cc3fdeeeb29b0a8bbf148efc91da611e9a
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68506400"
---
# <a name="azure-function-master--api-key"></a>Azure İşlev Yöneticisi / API anahtarı  

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 56 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan en fazla 90 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 54 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- iki eşit işaretle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOP==`

veya

Şunlardan oluşan 54 ile 84 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- veya yüzde işaretleri (%)
- son eki '%3d%3d' ile bitiyor (büyük/küçük harfe duyarlı değil)

örneğin:

abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDEF0123456789%3D%3D


## <a name="credential-example"></a>Kimlik bilgisi örneği 

`https://account.azurewebsites.net/api/function?code=abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDEF0123456789%3D%3D`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

## <a name="definition"></a>Tanım

Bu SIT, yetkilendirme düzeyi anonim dışında bir değer ayarlandığında [Azure İşlevi API'sini](/azure/azure-functions/functions-how-to-use-azure-function-app-settings?tabs=portal) istemek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlu 320 bit simetrik anahtarın desenleri.
- URL Kodlanmış 320 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey320"></a>Keyword_SymmetricKey320:

- code=
- Anahtar

### <a name="keyword_symmetrickey320urlencoded"></a>Keyword_SymmetricKey320UrlEncoded:

- code=
- Anahtar
