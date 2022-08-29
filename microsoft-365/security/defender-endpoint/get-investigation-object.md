---
title: Araştırma nesnesi API'lerini alma
description: Araştırma nesnesini almakla ilgili çağrılar oluşturmak için bu API'yi kullanın
keywords: api'ler, graf api'leri, desteklenen API'ler, Araştırma nesnesi
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: d086ffb524038ea7a487508d1fbe387c859220b2
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326595"
---
# <a name="get-investigation-api"></a>Araştırma API'si alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API açıklaması
Kimliğine göre belirli [Bir Araştırmayı](investigation.md) alır.
<br> Kimlik, araştırma kimliği veya uyarı kimliğini tetikleyen araştırma olabilir.


## <a name="limitations"></a>Sınırlamalar
1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.


## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Alert.Read.All|'Tüm uyarıları oku'
Uygulama|Alert.ReadWrite.All|'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı) | Alert.Read | 'Uyarıları okuma'
Temsilci (iş veya okul hesabı) | Alert.ReadWrite | 'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem [Bir Araştırma](investigation.md) varlığıyla 200, Tamam yanıt kodu döndürür.

