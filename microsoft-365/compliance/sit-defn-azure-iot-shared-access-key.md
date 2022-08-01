---
title: Azure IoT paylaşılan erişim anahtarı varlık tanımı
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
description: Azure IoT paylaşılan erişim anahtarına duyarlı bilgi türü varlık tanımı.
ms.openlocfilehash: b619fd6b488727ea9d0c615e354ab19d7eaad34b
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948653"
---
# <a name="azure-iot-shared-access-key"></a>Azure IoT paylaşılan erişim anahtarı  

## <a name="format"></a>Biçim

Desenin parçası olmayan ve eşittir işaretiyle biten harf, rakam ve özel karakterlerden oluşan 44 karakterden oluşan bir birleşim.

## <a name="pattern"></a>Desen

Şunlardan oluşan 43 karakterden oluşan herhangi bir birleşim:

- a-z (büyük/küçük harfe duyarlı değil)
- 0-9
- eğik çizgi (/)
- veya artı işaretleri (+)
- , desenin parçası olmayan eşittir işaretiyle (=) biter.

Örneğin:

`abcdefghijklmnopqrstuvwxyz0123456789/+ABCDE=`

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

Bu SIT, [Azure IoT cihazlarının ve hizmetlerinin](/azure/iot-fundamentals/iot-security-deployment) kimliğini doğrulamak için kullanılan güvenlik bilgileriyle eşleşecek şekilde tasarlanmıştır.

Birkaç birincil kaynak kullanır:

- Base64 kodlu 256 bit simetrik anahtarın desenleri.
- CredentialName, CredentialFeatures, AccountIdentityName, AccountIdentityValue, ResourceType, ResourceName, Id desenleri.
- Mockup değerlerinin, redaction'ların ve yer tutucuların desenleri.
- Sözlük sözlüğü.

Desenler, gerçek kimlik bilgileriyle makul bir güvenle eşleşecek şekilde tasarlanmıştır. Desenler örnek olarak biçimlendirilmiş kimlik bilgileriyle eşleşmiyor. Sahte değerler, yeniden düzenlenmiş değerler ve kimlik bilgisi türü veya kullanım açıklamaları gibi yer tutucular, gerçek bir gizli dizi değerinin bulunmaması gereken konumda eşleştirilmeyecektir.

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="keyword_symmetrickey256"></a>Keyword_SymmetricKey256:

- SharedAccessKey
- AccountKey
