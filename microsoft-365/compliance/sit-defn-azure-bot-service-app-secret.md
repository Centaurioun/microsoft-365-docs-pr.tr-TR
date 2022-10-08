---
title: Azure Bot hizmeti uygulaması gizli varlık tanımı (önizleme)
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
description: Azure Bot hizmeti uygulaması gizli diziye duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 67afea4534b81abc6dd58e459e014035a40d8d03
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476121"
---
# <a name="azure-bot-service-app-secret-preview"></a>Azure Bot hizmeti uygulama gizli anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 40 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan en fazla 40 karakterden oluşan bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- tireler (-)
- alt çizgiler (_)
- noktalar (.) 
- veya tilde vurguları (~)

örneğin:

`abc7Q~defghijklmnopqrs0t123456789-_.~`

## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [Azure Botu, WebChat kanalları ve istemci uygulamaları](/azure/bot-service/bot-builder-concept-authentication-types?view=azure-bot-service-4.0) arasında güvenli iletişim kurmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.  

Birkaç birincil kaynak kullanır:

- Belirli biçime sahip İstemci Gizli Dizisi desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_appsecret"></a>Keyword_AppSecret:

- Gizli
- Parola
- Anahtar
