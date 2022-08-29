---
title: Gelişmiş Avcılık API'si
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender üzerinde gelişmiş sorgular çalıştırmak için gelişmiş tehdit avcılığı API'sini kullanmayı öğrenin. Sınırlamalar hakkında bilgi edinin ve bir örne bakın.
keywords: api'ler, desteklenen API'ler, gelişmiş avcılık, sorgu
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
ms.openlocfilehash: 8eb2fdc1301b340c0907f3dc71b852488ccb64b6
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331566"
---
# <a name="advanced-hunting-api"></a>Gelişmiş tehdit avcılığı API'si

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> [!NOTE]
> Bu API yalnızca Uç Nokta için Microsoft Defender ait tabloları sorgulayabilir. Diğer Microsoft 365 Defender hizmetlerine ait tablolar [için Microsoft 365 Defender Gelişmiş tehdit avcılığı API'sinin](/microsoft-365/security/defender/api-advanced-hunting) kullanılması gerekir.

## <a name="limitations"></a>Sınırlamalar

1. Sorguyu yalnızca son 30 güne ait veriler üzerinde çalıştırabilirsiniz.

2. Sonuçlar en fazla 100.000 satır içerir.

3. Yürütme sayısı kiracı başına sınırlıdır:
   - API çağrıları: Dakikada en fazla 45 çağrı, saatte en fazla 1500 çağrı.
   - Yürütme süresi: Saatte 10 dakika çalışma süresi ve günde 3 saatlik çalışma süresi.

4. Tek bir isteğin en yüksek yürütme süresi 200 saniyedir.

5. 429 yanıtı, istek sayısına veya CPU'ya göre kota sınırına ulaşmayı temsil eder. Hangi sınıra ulaşıldığını anlamak için yanıt gövdesini okuyun.

6. Tek bir isteğin sorgu sonucu boyutu üst sınırı 124 MB'ı aşamaz. Aşılırsa, "Sorgu yürütme izin verilen sonuç boyutunu aştı. Sonuç sayısını sınırlayarak sorgunuzu iyileştirin ve yeniden deneyin" ifadesi görüntülenir.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|AdvancedQuery.Read.All|'Gelişmiş sorgular çalıştır'
Temsilci (iş veya okul hesabı)|AdvancedQuery.Read|'Gelişmiş sorgular çalıştır'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının 'Verileri Görüntüle' AD rolüne sahip olması gerekir
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>İstek üst bilgileri

Üstbilgi|Değer
:---|:---
Yetkilendirme|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|application/json

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
:---|:---|:---
Sorgu|Metin|Çalıştırılacak sorgu. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde 200 Tamam ve _QueryResponse_ nesnesi döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents
|where InitiatingProcessFileName =~ 'powershell.exe'
|where ProcessCommandLine contains 'appdata'
|project Timestamp, FileName, InitiatingProcessFileName, DeviceId
|limit 2"
}
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

> [!NOTE]
> Burada gösterilen yanıt nesnesi kısa bir süre için kesilebilir. Tüm özellikler gerçek bir çağrıdan döndürülür.

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender API'lere giriş](apis-intro.md)
- [Portaldan Gelişmiş Avcılık](advanced-hunting-query-language.md)
- [PowerShell ile Gelişmiş Av](run-advanced-query-sample-powershell.md)
