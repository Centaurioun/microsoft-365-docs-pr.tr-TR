---
title: Http yetkilendirme üst bilgisi varlık tanımı (önizleme)
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
description: Http yetkilendirme üst bilgisi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: b72934a88f85c0245320baa4b774d3c69196eb47
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948973"
---
# <a name="http-authorization-header-preview"></a>Http yetkilendirme üst bilgisi (önizleme)

## <a name="format"></a>Biçim

HTTP isteğinde kullanılan yetkilendirme üst bilgisi.

## <a name="pattern"></a>Desen

Çeşitli kimlik doğrulama üst bilgisi biçimleri örneğin:
 
`authorization: basic ********` <br>
`authorization: bearer ********` <br>
`authorization: digest ********` <br>
`authorization: negotiate ********` <br>

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [kimlik doğrulaması ve yetkilendirme için bir HTTP isteğinin](/dotnet/api/system.net.http.headers.httprequestheaders.authorization?view=netframework-4.8) üst bilgisinde kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır. 

Birkaç birincil kaynak kullanır:

- Http yetkilendirme üst bilgisi desenleri.
- CredentialName, CredentialFeatures, ResourceType desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Gerçek bir gizli dizi değerinin bulunmaması gereken konumdaki sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_httpauthorizationheader"></a>Keyword_HttpAuthorizationHeader:

- Yetkilendirme

