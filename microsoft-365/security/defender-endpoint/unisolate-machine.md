---
title: Cihazı yalıtım API'sinden serbest bırakma
description: Bir cihazı yalıtımdan serbest bırakmakla ilgili çağrılar oluşturmak için bu API'yi kullanın.
keywords: api'ler, graph API'leri, desteklenen API'ler, cihazı yalıtımdan kaldırma
search.product: eADQiWindows 10XVcnh
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
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: a77b156491548e24623e914b5b2cd5ae536078f6
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634992"
---
# <a name="release-device-from-isolation-api"></a>Cihazı yalıtım API'sinden serbest bırakma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Cihaz yalıtımını geri alma.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - tam yalıtım, Windows 10 sürüm 1703'te bulunan cihazlar için kullanılabilir.
> - Seçmeli yalıtım, Windows 10, sürüm 1709 veya sonraki sürümlerde bulunan cihazlar için kullanılabilir.
> - Bir cihazı yalıtırken yalnızca belirli işlemlere ve hedeflere izin verilir. Bu nedenle, tam VPN tünelinin arkasındaki cihazlar, cihaz yalıtıldıktan sonra Uç Nokta için Microsoft Defender bulut hizmetine erişemez. Uç Nokta için Microsoft Defender ve Microsoft Defender Virüsten koruma ile ilgili trafik için bölünmüş tünel VPN kullanmanızı öneririz.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.Isolate|'Makineyi yalıt'
Temsilci (iş veya okul hesabı)|Machine.Isolate|'Makineyi yalıt'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Etkin düzeltme eylemleri' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
:---|:---|:---
Açıklama ekleme|Dize|Eylemle ilişkilendirilecek açıklama. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde 201 - Oluşturulan yanıt kodunu ve [Makine Eylemi'ni](machineaction.md) döndürür.

Aynı cihazın yalıtımını kaldırmak için birden çok API çağrısı gönderirseniz, "bekleyen makine eylemi" veya "Eylem zaten sürüyor" iletisiyle HTTP 400 döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}
```

Cihazı yalıtmak için bkz. [Cihazı yalıtma](isolate-machine.md).
