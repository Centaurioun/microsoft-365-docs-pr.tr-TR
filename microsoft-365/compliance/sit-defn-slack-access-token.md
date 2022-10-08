---
title: Slack erişim belirteci varlık tanımı
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
description: Slack erişim belirteci hassas bilgi türü varlık tanımı.
ms.openlocfilehash: e92abbabd1f968f1b7d725e7d86f13cfeb379d7a
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504448"
---
# <a name="slack-access-token"></a>Slack erişim belirteci

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 34 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

'xoxp-', 'xoxb-', 'xoxa-', 'xoxr-', 'xoxr-', 'xoxo-', 'xoxs-' veya 'xoxe-' belirteç ön eki (büyük/küçük harfe duyarlı)

En fazla 29 karakterden oluşan bir birleşim:

- 29 a-z (büyük/küçük harfe duyarlı değil)
- 0-9 veya kısa çizgiler (-)

örneğin:

`xoxp-abcdef-abcdef-abcdef-abcdef` 

## <a name="credential-example"></a>Kimlik bilgisi örneği 

`slack_token= xoxp-abcdef-abcdef-abcdef-abcdef;`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

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
