---
title: Slack erişim belirteci varlık tanımı (önizleme)
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
description: Slack erişim belirteci hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 18e6654abe83bcbde40a832a74ec451c24f744b0
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948641"
---
# <a name="slack-access-token-preview"></a>Slack erişim belirteci (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 34 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

'xoxp-', 'xoxb-', 'xoxa-', 'xoxr-', 'xoxr-', 'xoxo-', 'xoxs-' veya 'xoxe-' belirteç ön eki (büyük/küçük harfe duyarlı)

En fazla 29 karakterden oluşan bir birleşim:

- 29 a-z (büyük/küçük harfe duyarlı değil)
- 0-9 veya kısa çizgiler (-)

örneğin:

`xoxp-abcdef-abcdef-abcdef-abcdef` 

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Slack platformu işlevlerine](https://api.slack.com/docs/token-type) erişmek için kullanılan güvenlik bilgileriyle (örneğin Bot belirteçleri, Kullanıcı belirteçleri ve Uygulama düzeyi belirteçler) eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Slack kullanıcı/bot/çalışma alanı belirteci desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_slacktokens"></a>Keyword_SlackTokens:

- Xox
