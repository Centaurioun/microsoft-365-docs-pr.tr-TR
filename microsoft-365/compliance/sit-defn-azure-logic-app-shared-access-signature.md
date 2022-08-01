---
title: Azure Logic App paylaşılan erişim imzası varlık tanımı (önizleme)
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
description: Azure Logic App paylaşılan erişim imzası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: ff777170f9c9cc7ea3865a4a01e794c20137f7db
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948440"
---
# <a name="azure-logic-app-shared-access-signature-preview"></a>Azure Logic App paylaşılan erişim imzası (önizleme) 

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 76 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

43 ile 73 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- veya yüzde işaretleri (%)
- son eki '%3d' ile bitiyor (büyük/küçük harfe duyarlı değil)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Logic Apps'te](/azure/logic-apps/logic-apps-securing-a-logic-app?tabs=azure-portal) bir istek uç noktasına erişim vermek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

URL Kodlanmış 256 bit simetrik anahtar desenleri.
CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
Sözlük sözlüğü

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- Anahtar
- Belirte -ci
- Gizli
- Parola