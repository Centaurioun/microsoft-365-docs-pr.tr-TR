---
title: Makine API'lerini yalıtma
description: Uç Nokta için Microsoft Defender'da bir cihazı dış ağa erişimini yalıtmak için Makine YALıT API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, cihazı yalıtma
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
ms.openlocfilehash: 727389e9d6b1d21662e7ca0b8a1753fa242ec56e
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67704688"
---
# <a name="isolate-machine-api"></a>Makine API'lerini yalıtma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Bir cihazı dış ağa erişmeye karşı yalıtıyor.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - tam yalıtım, Windows 10, sürüm 1703 ve Windows 11 cihazlarda kullanılabilir.
> - Seçmeli yalıtım, Windows 10, sürüm 1709 veya üzeri ve Windows 11 cihazlarda kullanılabilir.
> - Bir cihazı yalıtırken yalnızca belirli işlemlere ve hedeflere izin verilir. Bu nedenle, tam VPN tünelinin arkasındaki cihazlar, cihaz yalıtıldıktan sonra Uç Nokta için Microsoft Defender bulut hizmetine erişemez. Uç Nokta için Microsoft Defender ve Microsoft Defender Virüsten Koruma bulut tabanlı korumayla ilgili trafik için bölünmüş tünel VPN kullanmanızı öneririz.

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

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
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
IsolationType|Dize|Yalıtımın türü. İzin verilen değerler şunlardır: 'Tam' veya 'Seçmeli'.

**IsolationType** gerçekleştirilecek yalıtım türünü denetler ve aşağıdakilerden biri olabilir:

- Tam: Tam yalıtım
- Seçmeli: Yalnızca sınırlı uygulama kümesinin ağa erişimini kısıtlayın (daha fazla ayrıntı için bkz [. Cihazları ağdan yalıtma](respond-machine-alerts.md#isolate-devices-from-the-network) )

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde 201 - Oluşturulan yanıt kodunu ve [Makine Eylemi'ni](machineaction.md) döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- Bir cihazı yalıtımdan serbest bırakmak için bkz. [Cihazı yalıtımdan serbest bırakma](unisolate-machine.md).
