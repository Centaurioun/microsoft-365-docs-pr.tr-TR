---
title: Azure Bot Framework gizli anahtar varlık tanımı
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
description: Azure Bot Framework gizli anahtara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: bb515b37f16dfe4e810ea38ef30a09563b966693
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503416"
---
# <a name="azure-bot-framework-secret-key"></a>Azure Bot Framework gizli anahtarı

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 55 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 63 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

55 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- alt çizgiler (_)
- veya noktalar (.)


`abcdefghijklmnopqrstuvwxyz.0123456789_ABCDEabcdefghijkl`

veya 63 karakter için

11 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)
- nokta

Üç karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)
- nokta

Üç karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)
- nokta

43 karakterden oluşan bir birleşim

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)

örneğin:

`abcdefghijk.lmn.opq.rstuvwxyz0123456789-_ABCDEFGHIJKLMNOPQRSTUV`


## <a name="credential-example"></a>Kimlik bilgisi örneği 

`host: webchat.botframework.com/?s=abcdefghijklmnopqrstuvwxyz.0123456789_ABCDEabcdefghijkl&`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

## <a name="definition"></a>Tanım

Bu SIT, [Azure Bot hizmetlerinden WebChat kanallarına](/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0) bağlanmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 URL kodlu 328 bit simetrik anahtarın desenleri.
- Base64 URL kodlu 360 bit simetrik anahtar desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey328url"></a>Keyword_SymmetricKey328Url:

- botframework
- Anahtar

### <a name="keyword_symmetrickey360url"></a>Keyword_SymmetricKey360Url:

- botframework
- Anahtar
