---
title: Azure depolama hesabı erişim anahtarı varlık tanımı (önizleme)
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
description: Azure depolama hesabı erişim anahtarı hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 726eb03906aaa946e3fa89138c5d0c66351efec1
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476719"
---
# <a name="azure-storage-account-access-key-preview"></a>Azure depolama hesabı erişim anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

Harf, rakam ve özel karakterlerden oluşan en fazla 20.000 karakterden oluşan bir birleşim.

veya

Harf, rakam ve özel karakterlerden oluşan 88 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 20.000 karaktere kadar herhangi bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- En fazla 2
- eşittir işaretleri (=)

örneğin:

`MIIKcQIBAzCCCi0GCSqGSIb3DQEHAaCCCh4EggoaMIIKFjCCBg8GCSqGSIb3DQEHAaCCBgAEggX8MIIF+DCCBfQGCyqGSIb3DQEM` Veya

Şunlardan oluşan 86 karakterden oluşan herhangi bir birleşim:

a-z (büyük/küçük harfe duyarlı değil) 0-9 eğik çizgi (/) veya artı işareti (+) iki eşit işaretle (=) biter

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDEabcdefghijklmnopqrstuvwxyz0123456789/+ABCDE==`


## <a name="checksum"></a>Sağlama Toplamı

Evet

## <a name="definition"></a>Tanım

Bu SIT, Blob, Kuyruk, Tablo ve Dosya [hizmetleri gibi Azure Depolama hizmetlerinde](/rest/api/storageservices/authorize-with-shared-key) istekte bulunmak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Base64 kodlanmış dize değişmez değeri desenleri.
- Base64 kodlu 512 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id, AccountName desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_base64encodedstringliteral"></a>Keyword_Base64EncodedStringLiteral:

- Mıı

### <a name="keyword_symmetrickey512"></a>Keyword_SymmetricKey512:

- SharedAccessKey
- AccountKey
