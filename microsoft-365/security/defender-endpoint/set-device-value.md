---
title: Cihaz değeri API'lerini ayarlama
description: Uç Nokta için Microsoft Defender API'sini kullanarak bir cihazın değerini belirtmeyi öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, etiketler, makine etiketleri
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 219b552eb096e1e1bcc59938f0c360afb0663017
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584495"
---
# <a name="set-device-value-api"></a>Cihaz değeri API'lerini ayarlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Belirli bir [Makinenin](machine.md) cihaz değerini ayarlayın.<br>
Daha fazla bilgi için bkz. [cihaz değerlerini atama](tvm-assign-device-value.md) .

## <a name="limitations"></a>Sınırlamalar

1. Yapılandırdığınız saklama süresine göre en son görülen cihazlarda gönderi gönderebilirsiniz.
2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Güvenlik ayarını yönet'. Daha fazla bilgi için (Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının makine grubu ayarlarına göre makineye erişimi olmalıdır (Daha fazla bilgi için bkz [. Makine grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
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
DeviceValue|Enum|Cihaz değeri. İzin verilen değerler şunlardır: 'Normal', 'Düşük' ve 'Yüksek'. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 - Tamam yanıt kodunu ve yanıt gövdesindeki güncelleştirilmiş Makine'yi döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

Makine etiketi ekleyen bir istek örneği aşağıda verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
