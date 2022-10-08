---
title: Azure Machine Learning web hizmeti API'si anahtar varlık tanımı (önizleme)
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
description: Azure Machine Learning web hizmeti API'sinde anahtara duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 531befbda54224cddc4a1d4d391469a2ef1b2ff8
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476935"
---
# <a name="azure-machine-learning-web-service-api-key-preview"></a>Azure Machine Learning web hizmeti API anahtarı (önizleme) 

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

İki eşittir işaretiyle (==) biten harf, rakam ve özel karakterlerden oluşan 88 karakterin birleşimi.

## <a name="pattern"></a>Desen

86 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure Machine Learning Web hizmetlerine](/azure/machine-learning/classic/consume-web-services) bağlanmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, ID, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
