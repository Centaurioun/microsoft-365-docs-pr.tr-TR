---
title: Etki alanıyla ilgili makineler API'lerini alma
description: etki alanıyla ilgili makineleri alma API'sini kullanarak Uç Nokta için Microsoft Defender'daki bir etki alanına veya etki alanından iletişim kuran makineleri nasıl alacağınızı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, etki alanı, ilgili, cihazlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 1bb28ed69e155bf49f138c5b984cb738d1703c31
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638136"
---
# <a name="get-domain-related-machines-api"></a>Etki alanıyla ilgili makineler API'lerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Belirli bir etki alanı adresiyle veya bu adresten iletişim kuran bir [Makine](machine.md) koleksiyonunu alır.

## <a name="limitations"></a>Sınırlamalar

1. Yapılandırdığınız saklama süresine göre en son güncelleştirilen cihazları sorgulayabilirsiniz.
2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.Read.All|'Tüm makine profillerini oku'
Uygulama|Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.Read|'Makine bilgilerini oku'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md)
> - Yanıt, cihaz grubu ayarlarına göre yalnızca kullanıcının erişebileceği cihazları içerir (Daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md)
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

## <a name="http-request"></a>HTTP isteği

```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılıysa ve etki alanı varsa - [Makine](machine.md) varlıklarının listesiyle 200 Tamam. Etki alanı yoksa - Boş bir kümeyle 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
