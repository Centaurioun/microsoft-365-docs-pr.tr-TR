---
title: Azure Bilişsel arama API'si anahtar varlık tanımı (önizleme)
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
description: Azure Bilişsel Arama API'sinde anahtara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 8d4b5ca6c968468c5d084e6adb44eaf921553e21
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948457"
---
# <a name="azure-cognitive-search-api-key-preview"></a>Azure Bilişsel Arama API anahtarı (önizleme) 

## <a name="format"></a>Biçim

Harf ve rakamlardan oluşan 32 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 32 karakterden oluşan bir birleşim:

- a-f veya A-F (büyük/küçük harfe duyarlı)
- veya 0-9

örneğin:

`abcdef0123456789abcdef0123456789`


## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Bilişsel Arama API'lere](/azure/search/search-security-api-keys) gelen isteklerin kimliğini doğrulamak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

Onaltılık kodlanmış 128 bit simetrik anahtar desenleri.
CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey128hex"></a>Keyword_SymmetricKey128Hex:

- Demir
- Anahtar
- Gizli
- Belirte -ci
- Parola
- Pw
