---
title: Azure App Service Dağıtım Parolası varlık tanımı (önizleme)
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
description: Azure App Service Dağıtım Parolasına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: 6b8915b64e9b647523838284a996f1fca8721eef
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948463"
---
# <a name="azure-app-service-deployment-password-preview"></a>Azure App Service dağıtım parolası (önizleme)

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 60 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 60 karakterden oluşan herhangi bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEFGHIJKLMNOPQRSTUV`



## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, yerel bir bilgisayardan [Azure App Service dağıtımının](/azure/app-service/deploy-configure-credentials) güvenliğini sağlamak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.

Birkaç birincil kaynak kullanır:

- Base64 ile kodlanmış 360 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey360"></a>Keyword_SymmetricKey360:

- Parola
- Pw
