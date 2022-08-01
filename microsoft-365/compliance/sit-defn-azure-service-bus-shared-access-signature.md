---
title: Azure service bus paylaşılan erişim imzası varlık tanımı (önizleme)
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
description: Azure service bus paylaşılan erişim imzası hassas bilgi türü varlık tanımı.
ms.openlocfilehash: f9464bb2700bc4e4e186d33e451a2b286acca54f
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948509"
---
# <a name="azure-service-bus-shared-access-signature-preview"></a>Azure service bus paylaşılan erişim imzası (önizleme)

## <a name="format"></a>Biçim

Desenin parçası olmayan eşittir işaretiyle (=) biten harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

veya

Desenin parçası olmayan eşittir işaretiyle (=) biten harf, rakam ve özel karakterlerden oluşan en fazla 76 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:
 
- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- desenin parçası olmayan eşittir işaretiyle (=) biter

örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

veya

43 ile 73 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- veya yüzde işaretleri (%)
- son eki '%3d' ile bitiyor (büyük/küçük harfe duyarlı değil)

örneğin: 

`abcdefghijklmnopqrstuvwxyz0123456789%2F%2BABCDE%3D`

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, kullanıcıya belirli haklara sahip [Azure Service Bus kaynaklara](/azure/service-bus-messaging/service-bus-authentication-and-authorization) erişim vermek için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.

Birkaç birincil kaynak kullanır:

- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- URL Kodlanmış 256 bit simetrik anahtar desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey

### <a name="keyword_symmetrickey256urlencoded"></a>Keyword_SymmetricKey256UrlEncoded:

- sig=
- Anahtar
- Belirte -ci
- Gizli
- Parola
