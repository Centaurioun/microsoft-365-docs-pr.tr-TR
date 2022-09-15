---
title: Kullanıcıyla ilgili makineler API'lerini alma
description: Uç Nokta için Microsoft Defender'da kullanıcı kimliğiyle ilgili bir cihaz koleksiyonunu almak için Kullanıcıyla ilgili makineleri alma API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, kullanıcı, kullanıcıyla ilgili uyarılar
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
search.appverid: met150
ms.openlocfilehash: b9f452d719dee0f7116a9ce46f04884ba3367e37
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67697589"
---
# <a name="get-user-related-machines-api"></a>Kullanıcıyla ilgili makineler API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması
Belirli bir kullanıcı kimliğiyle ilgili cihaz koleksiyonunu alır.

## <a name="limitations"></a>Sınırlamalar

Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama |Machine.Read.All|'Tüm makine profillerini oku'
Uygulama |Machine.ReadWrite.All |'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı) | Machine.Read | 'Makine bilgilerini oku'
Temsilci (iş veya okul hesabı) | Machine.ReadWrite | 'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle'. Daha fazla bilgi için bkz. [Rol oluşturma ve yönetme](user-roles.md)
> - Yanıt, cihaz grubu ayarlarına bağlı olarak yalnızca kullanıcının erişebileceği cihazları içerir. Daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md).

## <a name="http-request"></a>HTTP isteği

```http
GET /api/users/{id}/machines
```

**Kimlik tam UPN değil, yalnızca kullanıcı adıdır. (örneğin, user1@contoso.com için makineleri almak için /api/users/user1/machines kullanın)**

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı ve kullanıcı varsa - Gövdedeki [makine](machine.md) varlıklarının listesiyle 200 Tamam. Kullanıcı yoksa - Boş bir kümeyle 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
