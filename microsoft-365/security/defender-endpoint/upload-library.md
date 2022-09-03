---
title: Canlı yanıt kitaplığına dosya yükleme
description: Canlı yanıt kitaplığına dosya yüklemeyi öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, kitaplığa yükleme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: f834add078e36d2439440d1decb4c7f534b5dec7
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67579853"
---
#  <a name="upload-files-to-the-live-response-library"></a>Canlı yanıt kitaplığına dosya yükleme  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[!include[Prerelease information](../../includes/prerelease.md)]

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Dosyayı canlı yanıt kitaplığına yükleyin.

## <a name="limitations"></a>Sınırlamalar

1.  Dosya boyutu üst sınırı 20 MB'tır.

2.  Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Kullanmaya başlama](apis-intro.md).


| İzin türü                    | Izni     | İzin görünen adı        |
|------------------------------------|----------------|--------------------------------|
| Uygulama                        | Library.Manage | Canlı yanıt kitaplığını yönetme |
| Temsilci (iş veya okul hesabı) | Library.Manage | Canlı yanıt kitaplığını yönetme |

## <a name="http-request"></a>HTTP isteği

Yüklemek

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>İstek üst bilgileri

|  Name   |    Tür    |       Açıklama                         |
|-----------------|--------|--------------------------------|
| Yetkilendirme   | Dize | \<token>Taşıyıcı. Gerekli.      |
| İçerik Türü    | Dize | multipart/form-data. Gerekli. |

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir form-data nesnesi sağlayın:

| Parametre         |     Tür         |       Açıklama                                        |
|-----------------------|--------------|------------------------------------------------------------|
| Dosya                  | Dosya içeriği | Canlı yanıt kitaplığına yüklenecek dosya. Gerekli |
| Açıklama           | Dize       | Dosyanın açıklaması.                                  |
| ParametersDescription | Dize       | (İsteğe bağlı) Betiğin çalışması için gereken parametreler. Varsayılan değer boş bir dizedir.                |
| OverrideIfExists      | Boole      | (İsteğe bağlı) Zaten varsa dosyanın geçersiz kılınıp geçersiz kılınmayacağı. Varsayılan değer boş bir dizedir.          |



## <a name="response"></a>Yanıt

-   Başarılı olursa, bu yöntem 200 - Tamam yanıt kodunu ve yanıt gövdesinde karşıya yüklenen canlı yanıt kitaplığı varlığını döndürür.

-   Başarılı olmazsa: Bu yöntem 400 - Hatalı İstek döndürür.  
    Hatalı istek genellikle yanlış gövdeyi gösterir.

## <a name="example"></a>Örnek

Istek

Curl kullanan isteğin bir örneği aşağıda verilmiştir.

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>İlgili konu

-  [Canlı yanıt çalıştır](run-live-response.md) 