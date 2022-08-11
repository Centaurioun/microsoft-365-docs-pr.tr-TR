---
title: Azure DevOps uygulama gizli varlık tanımı (önizleme)
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
description: Azure DevOps uygulaması gizli dizi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: d689cb184cd329d1d5686a5dde486305b5375078
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309361"
---
# <a name="azure-devops-app-secret-preview"></a>Azure DevOps uygulama gizli anahtarı (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 52 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 52 karakterden oluşan herhangi bir birleşim:
 
- a-z veya A-Z (büyük/küçük harfe duyarlı)
- veya 2-7

örneğin:

`abcdefghijklmnopqrstuvwxyz234567abcdefghijklmnopqrst`


## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [Azure DevOps REST API erişimi](/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops) için web uygulaması kullanıcılarının kimliğini doğrulamak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base32 kodlu 256 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256b32"></a>Keyword_SymmetricKey256B32:

- pat
- Belirte -ci
- Ado
- vsts
- azuredevops
- visualstudio.com
- dev.azure.com
