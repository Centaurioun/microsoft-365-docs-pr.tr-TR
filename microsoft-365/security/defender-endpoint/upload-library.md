---
title: Upload yanıt kitaplığına dosya ekleme
description: Canlı yanıt kitaplığına dosyanın nasıl yük olduğunu öğrenin.
keywords: api'ler, grafik api'leri, desteklenen api'ler, kitaplı kitaplara yükleme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 84ec7e361cccdc886650b0710f738a4315c4db8d
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2022
ms.locfileid: "63705602"
---
#  <a name="upload-files-to-the-live-response-library"></a>Upload yanıt kitaplığına dosya ekleme  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aşağıdakiler için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Uç Nokta için Microsoft Defender'ı mı deneyimliysiniz? [Ücretsiz deneme için kaydol'](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Upload yanıt kitaplığına kaydedin.

## <a name="limitations"></a>Sınırlamalar

1.  Dosya en fazla boyut sınırlaması 20 MB'dır.

2.  Bu API için fiyat sınırlamaları, dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağrı yapmak için aşağıdaki izinlerden biri gerekir. İzinleri seçme de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Başlama](apis-intro.md).


| İzin türü                    | İzin     | İzin görünen adı        |
|------------------------------------|----------------|--------------------------------|
| Uygulama                        | Library.Manage | Canlı yanıt kitaplığını yönetme |
| Temsilcili (iş veya okul hesabı) | Library.Manage | Canlı yanıt kitaplığını yönetme |

## <a name="http-request"></a>HTTP isteği

Upload

```HTTP
POST https://api.securitycenter.microsoft.com/api/libraryfiles
```

## <a name="request-headers"></a>Üstbilgi isteği

|  Name   |    Tür    |       Açıklama                         |
|-----------------|--------|--------------------------------|
| Yetkilendirme   | Dize | \<token>Taşıyıcı. Gerekli.      |
| İçerik Türü    | dize | multipart/form-data. Gerekli. |

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde, aşağıdaki parametreleriyle bir form-veri nesnesi girin:

| Parametre         |     Tür         |       Açıklama                                        |
|-----------------------|--------------|------------------------------------------------------------|
| Dosya                  | Dosya içeriği | Canlı yanıt kitaplığına yüklenmek istediğiniz dosya. Gerekli |
| Açıklama           | Dize       | Dosyanın açıklaması.                                  |
| ParametersDescription | Dize       | (İsteğe bağlı) Betiğin çalışması için gereken parametreler. Varsayılan değer boş dizedir.                |
| OverrideIfExists      | Boole      | (İsteğe bağlı) Dosya zaten varsa geçersiz kılınıp geçersiz kılınmayamaz. Varsayılan değer boş dizedir.          |



## <a name="response"></a>Yanıt

-   Başarılı olursa, bu yöntem yanıt gövdesinde 200 - Tamam yanıt kodu ve karşıya yüklenen canlı yanıt kitaplığı varlığı döndürür.

-   Başarılı değil: Bu yöntem 400 - Kötü İstek döndürür.  
    Hatalı istek genellikle yanlış gövdeyi gösterir.

## <a name="example"></a>Örnek

İstek

Burada, kıvrık kullanılarak isteğin bir örneği ve kullanımı ve kullanımı açık edilmektedir.

```CURL
curl -X POST https://api.securitycenter.microsoft.com/api/libraryfiles -H
"Authorization: Bearer \$token" -F "file=\@mdatp1.png" -F
"ParametersDescription=test"  
-F "HasParameters=true" -F "OverrideIfExists=true" -F "Description=test
description"
```

## <a name="related-topic"></a>İlgili konu

-  [Canlı yanıt çalıştır](run-live-response.md) 