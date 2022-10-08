---
title: makine anahtarı varlık tanımını ASP.NET
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
ms.openlocfilehash: 5ecc447cea65e0d5e375edcea5d6eba6e00792db
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2022
ms.locfileid: "68504568"
---
# <a name="aspnet-machine-key"></a>makine anahtarını ASP.NET

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

Bu SIT, [Tüm kimlik bilgileri](sit-defn-all-creds.md) paketlenmiş SIT'e de dahildir.

 ## <a name="format"></a>Biçim

XML yapılandırmasında simetrik anahtarlar.

## <a name="pattern"></a>Desen

XML'deki çeşitli simetrik anahtar biçimleri, örneğin:

```xml
<machineKey decryptionKey="******** </br> 
<machineKey validationKey="********
```
## <a name="credential-example"></a>Kimlik bilgisi örneği 

`<machineKey validationKey="ABCDEF0123456789ABCDEF0123456789ABCDEF0123456789" decryptionKey="ABCDEF0123456789ABCDEF0123456789ABCDEF0123456789"`

## <a name="checksum"></a>Sağlama Toplamı

Hayır

Sağlama toplamları olan SID'ler, bilgilerin geçerli olup olmadığını denetlemek için benzersiz bir hesaplama kullanır. Bu, **Sağlama Toplamı** değeri **Evet** olduğunda hizmetin yalnızca hassas verileri temel alarak pozitif bir algılama gerçekleştirebileceği anlamına gelir. **Sağlama Toplamı** değeri Ek (ikincil) öğe **olmadığında**, hizmetin pozitif bir algılama yapması için de algılanması gerekir.

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

