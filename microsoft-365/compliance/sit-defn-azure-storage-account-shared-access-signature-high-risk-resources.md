---
title: Yüksek riskli kaynaklar için Azure Depolama hesabı paylaşılan erişim imzası varlık tanımı (önizleme)
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
description: Yüksek riskli kaynaklar için Azure Depolama hesabı paylaşılan erişim imzası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: a3413afd4bb397750f75646a7f1d4ba61e8888cc
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476913"
---
# <a name="azure-storage-account-shared-access-signature-for-high-risk-resources-preview"></a>Yüksek riskli kaynaklar için Azure Depolama hesabı paylaşılan erişim imzası (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan en fazla 76 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- eşittir işaretiyle biter (=)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

veya

43 ile 73 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- veya yüzde işaretleri (%)
- son eki '%3d' ile bitiyor (büyük/küçük harfe duyarlı değil)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [sertifikalar, yapılandırmalar veya dağıtım paketleri gibi yüksek riskli Azure Depolama kaynaklarına](/rest/api/storageservices/delegate-access-with-shared-access-signature) kısıtlı erişim hakları vermek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- URL Kodlanmış 256 bit simetrik anahtar desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- Anahtar
- Belirte -ci
- Gizli
- Parola
