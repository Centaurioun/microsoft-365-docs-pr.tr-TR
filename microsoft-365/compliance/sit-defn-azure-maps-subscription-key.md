---
title: Azure Haritalar abonelik anahtarı varlık tanımı (önizleme)
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
description: abonelik anahtarına duyarlı bilgi türü varlık tanımını Azure Haritalar.
ms.openlocfilehash: d8729175d86ecd37c9bb27f5ee8b1985eabed318
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476847"
---
# <a name="azure-maps-subscription-key-preview"></a>Azure Haritalar abonelik anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 43 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- veya altı çizili (_)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789-_ABCDE`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Haritalar hesaplarındaki](/azure/azure-maps/how-to-manage-authentication) kaynaklara erişmek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 URL kodlu 256 bit simetrik anahtar desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256url"></a>Keyword_SymmetricKey256Url:

- Anahtar
- microsoft.maps
