---
title: Tarayıcı uzantıları izin bilgilerini alma
description: Tarayıcı uzantısı için gereken tüm izinlerin listesini alır
keywords: api'ler, graf api'leri, desteklenen API'ler, get, tarayıcı uzantısı bilgileri, Uç Nokta için Microsoft Defender, Microsoft Defender Güvenlik Açığı Yönetimi
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0dd9498e5ff126e8b91a8cb70cf352f6720db686
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67499068"
---
# <a name="get-browser-extensions-permission-information"></a>Tarayıcı uzantıları izin bilgilerini alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink).

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API açıklaması

Belirli bir tarayıcı uzantısı tarafından istenen tüm izinlerin listesini alır. Bu statik bir veri açıklamasıdır ve çoğunlukla [Tarayıcı uzantılarını dışarı aktarma değerlendirme API'sinin](get-assessment-browser-extensions.md) döndüreceği verileri geliştirmek için kullanılır.

Bu API'leri birleştirerek Tarayıcı uzantılarını dışarı aktarma değerlendirme sonuçlarında açılan tarayıcı uzantıları tarafından istenen [izinlerin](get-assessment-browser-extensions.md) açıklamasını görebilirsiniz.

<br>[OData V4 sorgularını](https://www.odata.org/documentation/) destekler.
<br>OData tarafından desteklenen işleçler:
<br>```$filter``` üzerinde:  ```id```, ```name```, ```description```, ```cvssV3```, ```publishedOn```, , ```severity```ve ```updatedOn``` özellikleri.
<br>```$top``` 10.000 maksimum değere sahip.
<br>```$skip```.
<br>[Uç Nokta için Microsoft Defender ile OData sorgularında örneklere](exposed-apis-odata-samples.md) bakın.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için ayrıntılar için bkz. [Uç Nokta için Microsoft Defender API'lerini kullanma](apis-intro.md).

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Software.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Software.Read|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'

## <a name="http-request"></a>HTTP isteği

```http
GET api/browserextensions/permissionsinfo
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem gövdedeki bir tarayıcı uzantısı tarafından istenen tüm izinlerin listesiyle 200 Tamam döndürür.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/browserextensions/permissionsinfo
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#BrowserExtension",
    "value": [
{
  "value": [
    {
      "key": "audioCapture",
      "permissionName": "Capture audio from attached mic or webcam",
      "description": "Capture audio from attached mic or webcam. Could be used to listen in on use."
    },
    {
      "key": "app.window.fullscreen.overrideEsc",
      "permissionName": "Prevent escape button from exiting fullscreen",
      "description": "Can prevent escape button from exiting fullscreen."
    },
    {
      "key": "browsingData",
      "permissionName": "Clear browsing data",
      "description": "Clears browsing data which could result in a forensics/logging issues."
    },
    {
      "key": "content_security_policy",
      "permissionName": "Can manipulate default Content Security Policy (CSP)",
      "description": "CSP works as a block/allow listing mechanism for resources loaded or executed by your extensions. Can manipulate default CSP."
    }

            ]
}
    ]
```

## <a name="see-also"></a>Ayrıca bkz.

- [Tarayıcı uzantıları izin bilgilerini alma](get-assessment-browser-extensions.md)
- [Tarayıcı uzantıları değerlendirmesi](../defender-vulnerability-management/tvm-browser-extensions.md)

## <a name="other-related"></a>Diğer ilgililer

- [Güvenlik açığı yönetimi](../defender-vulnerability-management/defender-vulnerability-management.md)
- [Kuruluşunuzdaki güvenlik açıkları](../defender-vulnerability-management/tvm-weaknesses.md)