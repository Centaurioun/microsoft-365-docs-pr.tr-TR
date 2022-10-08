---
title: Amazon S3 istemci gizli anahtarı erişim anahtarı varlık tanımı (önizleme)
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
description: Amazon S3 istemci gizli anahtarı erişim anahtarı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 6a3df751075a58b257532f9cff8d41143f325c51
ms.sourcegitcommit: edc9d4dec92ca81cff39bbf9590f1cd3a75ec436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68484574"
---
# <a name="amazon-s3-client-secret-access-key-preview"></a>Amazon S3 istemci gizli erişim anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan 40 karakterden oluşan bir birleşim. 

## <a name="pattern"></a>Desen

13 basamaklı sayı:

Şunlardan oluşan 40 karakterden oluşan bir birleşim: 

- a-z (büyük/küçük harfe duyarsız) 
- 0-9 
- eğik çizgi (/) veya artı işareti (+) 

örneğin: 

`AWS Secret: abcdefghijklmnopqrst0123456789/+ABCDEFGH;`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Amazon Web Services'e](/toolkit-for-eclipse/v1/user-guide/setup-credentials.html) erişmek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.


Birkaç birincil kaynak kullanır: 
 
- Base64 kodlu 240 bit simetrik anahtarın desenleri. 
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri. 
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri. 
- Sözcük dağarcığı sözcükleri sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular. 

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey240"></a>Keyword_SymmetricKey240: 

- Gizli 
- Anahtar 
