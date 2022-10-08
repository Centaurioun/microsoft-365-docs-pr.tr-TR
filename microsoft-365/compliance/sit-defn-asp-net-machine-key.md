---
title: ASP.NET makine anahtarı varlık tanımı (önizleme)
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
description: Makine anahtarına duyarlı bilgi türü varlık tanımını ASP.NET.
ms.openlocfilehash: 1fe8616229bca7a00581d026a318db4029fc2200
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68476407"
---
# <a name="aspnet-machine-key-preview"></a>ASP.NET makine anahtarı (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

XML yapılandırmasında simetrik anahtarlar.

## <a name="pattern"></a>Desen

XML'deki çeşitli simetrik anahtar biçimleri, örneğin:

```xml
<machineKey decryptionKey="******** </br> 
<machineKey validationKey="********
```
## <a name="checksum"></a>Sağlama Toplamı

Hayır

## <a name="definition"></a>Tanım


Bu SIT, [ASP.NET form kimlik](/dotnet/api/system.web.security.machinekey?view=netframework-4.8) doğrulaması ve görüntüleme durumunda verileri şifrelemek veya karma hale getirmek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Xml dosyalarındaki Simetrik anahtar bağlamının desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.


## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickeycontextinxml"></a>Keyword_SymmetricKeyContextInXml:

- Parola
- Anahtar
- Connectionstring

