---
title: Makine varlığı API'sini güncelleştirme
description: Bu API'yi kullanarak makine etiketlerini güncelleştirmeyi öğrenin. Etiketleri ve cihaz değeri özelliklerini güncelleştirebilirsiniz.
keywords: api'ler, graf api'si, desteklenen API'ler, alma, uyarı, bilgi, kimlik
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
ms.openlocfilehash: a7f24d69d8be5ce996c902fa00b6fdde05c6905d
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577023"
---
# <a name="update-machine"></a>Makineyi güncelleştir 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Mevcut [Makinenin](machine.md) özelliklerini Güncelleştirmeler.

Güncelleştirilebilir özellikler şunlardır: `machineTags` ve `deviceValue`.

## <a name="limitations"></a>Sınırlamalar

1. API'de kullanılabilen makineleri güncelleştirebilirsiniz. 
2. Güncelleştirme makinesi yalnızca etiket koleksiyonuna etiket ekler. Etiketler varsa, bunlar gövdedeki etiket koleksiyonuna dahil edilmelidir.
3. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.ReadWrite.All|'Tüm makineler için makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Uyarılar araştırması'. Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md).
> - Kullanıcının, cihaz grubu ayarlarına bağlı olarak uyarıyla ilişkilendirilmiş cihaza erişimi olmalıdır. Daha fazla bilgi için bkz. [Cihaz gruplarını oluşturma ve yönetme](machine-groups.md).

## <a name="http-request"></a>HTTP isteği

```http
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde, güncelleştirilmesi gereken ilgili alanların değerlerini sağlayın.

İstek gövdesine dahil edilmeyen mevcut özellikler önceki değerlerini korur veya diğer özellik değerlerinde yapılan değişikliklere göre yeniden hesaplanır.

En iyi performans için değişmemiş mevcut değerleri eklememelisiniz.

Özellik|Tür|Açıklama
:---|:---|:---
machineTags|Dize koleksiyonu|[Makine](machine.md) etiketleri kümesi.
deviceValue|Null Atanabilir Sabit Listesi|[Cihazın değeri](tvm-assign-device-value.md). Olası değerler şunlardır: 'Normal', 'Düşük' ve 'Yüksek'.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 Tamam döndürür ve güncelleştirilmiş özelliklere sahip yanıt gövdesindeki [makine](machine.md) varlığı.

Gövdedeki makine etiketleri koleksiyonu mevcut makine etiketlerini içermiyorsa, tüm etiketleri istek gövdesinde sağlanan etiketlerle değiştirir.

Belirtilen kimlikte makine bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10" "Windows11",
                     "Windows Insider - Fast"
    ]
}
```
