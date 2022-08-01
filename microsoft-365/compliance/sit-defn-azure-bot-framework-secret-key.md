---
title: Azure Bot Framework gizli anahtar varlık tanımı (önizleme)
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
description: Azure Bot Framework gizli anahtara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: c436436b00dda8a5273939665920ef709ff164c5
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948460"
---
# <a name="azure-bot-framework-secret-key-preview"></a>Azure Bot Framework gizli anahtarı (önizleme)

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

3 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)
- nokta

3 karakterden oluşan bir birleşim:

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


## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Bot hizmetlerinden WebChat kanallarına](/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0) bağlanmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 URL kodlu 328 bit simetrik anahtar desenleri.
- Base64 URL kodlu 360 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey328url"></a>Keyword_SymmetricKey328Url:

- botframework
- Anahtar

### <a name="keyword_symmetrickey360url"></a>Keyword_SymmetricKey360Url:

- botframework
- Anahtar
