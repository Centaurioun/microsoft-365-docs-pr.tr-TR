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
ms.openlocfilehash: 03ea2782272b961522c40a1f8e43ebf9da548cd4
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948447"
---
# <a name="azure-devops-app-secret-preview"></a>Azure DevOps uygulama gizli anahtarı (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 52 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 52 karakterden oluşan herhangi bir birleşim:
 
- a-z veya A-Z (büyük/küçük harfe duyarlı)
- veya 2-7

örneğin:

`ntpi2ch67ci2vjzcohglogyygwo5fuyl365n2zdowwxhsys6jnoa`


## <a name="checksum"></a>Sağlama toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, [Azure DevOps REST API erişimi](/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops) için web uygulaması kullanıcılarının kimliğini doğrulamak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base32 kodlamalı 256 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256b32"></a>Keyword_SymmetricKey256B32:

- pat
- Belirte -ci
- Ado
- vsts
- azuredevops
- visualstudio.com
- dev.azure.com
