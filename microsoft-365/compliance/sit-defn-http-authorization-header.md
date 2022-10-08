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
- tier3
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Http yetkilendirme üst bilgisi hassas bilgi türü varlık tanımı.
ms.openlocfilehash: 7cbb492d06551152adc2aac874310426a56d4485
ms.sourcegitcommit: be2334dbcd4e1bf309349d981a68a30e06de0297
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68379930"
---
# <a name="http-authorization-header-preview"></a>Http yetkilendirme üst bilgisi (önizleme)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="format"></a>Biçim

HTTP isteğinde kullanılan yetkilendirme üst bilgisi.

## <a name="pattern"></a>Desen

Çeşitli kimlik doğrulama üst bilgisi biçimleri örneğin:
 
`authorization: basic ********` <br>
`authorization: bearer ********` <br>
`authorization: digest ********` <br>
`authorization: negotiate ********` <br>

## <a name="checksum"></a>Sağlama Toplamı

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

