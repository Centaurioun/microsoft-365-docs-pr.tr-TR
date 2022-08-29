---
title: Makineyle ilgili uyarıları alma API'si
description: Makineyle ilgili uyarıları alma API'sini kullanmayı öğrenin. Bu API, Uç Nokta için Microsoft Defender belirli bir cihazla ilgili tüm uyarıları almanıza olanak tanır.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, cihazlar, ilgili, uyarılar
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
ms.openlocfilehash: d5a7673ef10e374a830c5410ec96a057d150b36d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326529"
---
# <a name="get-machine-related-alerts--api"></a>Makineyle ilgili uyarıları alma API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Belirli bir cihazla ilgili tüm [Uyarıları](alerts.md) alır.

## <a name="limitations"></a>Sınırlamalar

1. Yapılandırdığınız saklama süresine göre en son güncelleştirilen cihazları sorgulayabilirsiniz.
2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Alert.Read.All|'Tüm uyarıları oku'
Uygulama|Alert.ReadWrite.All|'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı) | Alert.Read | 'Uyarıları okuma'
Temsilci (iş veya okul hesabı) | Alert.ReadWrite | 'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle'. İzinler hakkında daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md).
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır. Cihaz grubu ayarları hakkında daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md).

## <a name="http-request"></a>HTTP isteği

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı ve cihaz varsa: Gövdedeki [uyarı](alerts.md) varlıklarının listesiyle 200 Tamam. Cihaz bulunamadıysa: 404 Bulunamadı.
