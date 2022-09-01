---
title: IP ile ilgili uyarılar API'lerini alma
description: Uç Nokta için Microsoft Defender kullanarak belirli bir IP adresiyle ilgili uyarı koleksiyonunu alma
keywords: api'ler, graf api'leri, desteklenen API'ler, get, ip, related, alerts
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 62a07c08d3b3e86b2b2e501deb2e77cbdbff2d03
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67516016"
---
# <a name="get-ip-related-alerts-api"></a>IP ile ilgili uyarılar API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması
Belirli bir IP adresiyle ilgili bir uyarı koleksiyonunu alır.


## <a name="limitations"></a>Sınırlamalar
1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.


## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Uç Nokta API'leri için Defender'ı kullanma](apis-intro.md)

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
> - Yanıt yalnızca cihaz grubu ayarlarına göre kullanıcının erişimi olan cihazlarla ilişkili uyarıları içerir (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılıysa ve IP varsa - Gövdedeki [uyarı](alerts.md) varlıklarının listesiyle 200 Tamam. IP adresi bilinmiyor ancak geçerliyse boş bir küme döndürür.
IP adresi geçersizse HTTP 400 döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```
