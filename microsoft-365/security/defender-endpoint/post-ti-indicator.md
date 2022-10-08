---
title: Gösterge API'sini Gönderme veya Güncelleştirme
description: Uç Nokta için Microsoft Defender'da yeni bir Gösterge varlığı göndermek veya güncelleştirmek için Göstergeyi Gönder veya Güncelleştir API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'si, desteklenen API'ler, gönderme, ti, gösterge, güncelleştirme
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
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 1afe71e8a25b0c623be2039c471c75d707c5c50a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226547"
---
# <a name="submit-or-update-indicator-api"></a>Gösterge API'sini Gönderme veya Güncelleştirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Yeni [Gösterge](ti-indicator.md) varlığını gönderir veya Güncelleştirmeler.

IP'ler için CIDR gösterimi desteklenmez.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.
2. Kiracı başına 15.000 etkin gösterge sınırı vardır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Başlarken](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Ti.ReadWrite|'Gösterge okuma ve yazma'
Uygulama|Ti.ReadWrite.All|'Tüm Göstergeleri Okuma ve Yazma'
Temsilci (iş veya okul hesabı)|Ti.ReadWrite|'Gösterge okuma ve yazma'

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/indicators
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
indicatorValue|Dize|[Gösterge](ti-indicator.md) varlığının kimliği. **Gerekli**
indicatorType|Enum|Göstergenin türü. Olası değerler şunlardır: "FileSha1", "FileMd5", "CertificateThumbprint", "FileSha256", "IpAddress", "DomainName" ve "Url". **Gerekli**
Eylem|Enum|Gösterge kuruluşta bulunursa gerçekleştirilecek eylem. Olası değerler şunlardır: "Alert", "Warn", "Block", "Audit, "BlockAndRemediate", "AlertAndBlock" ve "Allowed". **Gerekli**. "Audit" ile bir eylem oluşturulurken "GenerateAlert" parametresi "TRUE" olarak ayarlanmalıdır.
Uygulama|Dize|Göstergeyle ilişkili uygulama. Bu alan yalnızca yeni göstergeler için çalışır. Mevcut bir göstergedeki değeri güncelleştirmez. **İsteğe bağlı**
Başlık|Dize|Gösterge uyarı başlığı. **Gerekli**
Açıklama|Dize|Göstergenin açıklaması. **Gerekli**
expirationTime|Datetimeoffset|Göstergenin sona erme zamanı. **İsteğe bağlı**
Önem|Enum|Göstergenin önem derecesi. Olası değerler şunlardır: "Bilgilendirici", "Düşük", "Orta" ve "Yüksek". **İsteğe bağlı**
recommendedActions|Dize|TI göstergesi uyarısı önerilen eylemler. **İsteğe bağlı**
rbacGroupNames|Dize|Göstergenin uygulanacağı RBAC grup adlarının virgülle ayrılmış listesi. **İsteğe bağlı**
educateUrl|Dize|Özel bildirim/destek URL'si. URL göstergeleri için Engelle ve Uyar eylem türleri için desteklenir. **İsteğe bağlı**
generateAlert|Enum|Uyarı oluşturma gerekliyse **True****, bu** gösterge uyarı oluşturmamalıdır.
## <a name="response"></a>Yanıt

- Başarılı olursa, bu yöntem 200 - Tamam yanıt kodunu ve yanıt gövdesinde oluşturulan/güncelleştirilmiş [Gösterge](ti-indicator.md) varlığını döndürür.
- Başarılı olmazsa: Bu yöntem 400 - Hatalı İstek döndürür. Hatalı istek genellikle yanlış gövdeyi gösterir.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>İlgili konu

- [Göstergeleri yönetin](manage-indicators.md)
