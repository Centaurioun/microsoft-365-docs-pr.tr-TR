---
title: Dosya kaynak türü
description: Dosyalarla ilgili son Uç Nokta için Microsoft Defender uyarılarını alın.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
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
ms.openlocfilehash: 85ce81f3d99aa789c68e9967f6bcafb68ca681f2
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67323452"
---
# <a name="file-resource-type"></a>Dosya kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Uç Nokta için Defender'da bir dosya varlığını temsil eder.

## <a name="methods"></a>Yöntemler

Yöntem|Dönüş Türü |Açıklama
:---|:---|:---
[Dosya al](get-file-information.md) | [Dosya](files.md) | Tek bir dosya alma 
[Dosyayla ilgili uyarıları listeleme](get-file-related-alerts.md) | [uyarı](alerts.md) koleksiyonu | Dosyayla ilişkili [uyarı](alerts.md) varlıklarını alın.
[Dosyayla ilgili makineleri listeleme](get-file-related-machines.md) | [makine](machine.md) koleksiyonu | Uyarıyla ilişkili [makine](machine.md) varlıklarını alın.
[dosya istatistikleri](get-file-statistics.md) | İstatistik özeti | Verilen dosya için yaygınlığı alır.


## <a name="properties"></a>Özellikler

|Özellik | Tür | Açıklama |
|:---|:---|:---|
|sha1 | Dize | Dosya içeriğinin Sha1 karması |
|sha256 | Dize | Dosya içeriğinin Sha256 karması |
|globalPrevalence | Boş değer atanabilir uzun | Kuruluş genelinde dosya yaygınlığı |
|globalFirstObserved | Datetimeoffset | Dosya ilk kez gözlemlendi |
|globalLastObserved | Datetimeoffset | Dosyanın son gözlemlenme zamanı |
|Boyutu | Boş değer atanabilir uzun | Dosyanın boyutu |
|Filetype | Dize | Dosyanın türü |
|isPeFile | Boole | Dosya taşınabilir yürütülebilir dosyaysa true (ör. "DLL", "EXE", vb.) |
|filePublisher | Dize | Dosya yayımcısı |
|fileProductName | Dize | Ürün adı |
|Imzala -yan | Dize | Dosya imzalayan |
|Veren | Dize | Dosya veren |
|signerHash | Dize | İmzalama sertifikası karması |
|isValidCertificate | Boole | sertifikayı imzalama Uç Nokta için Microsoft Defender aracısı tarafından başarıyla doğrulandı |
|determinType | Dize | Dosyanın belirleme türü |
|determinationValue | Dize | Belirleme değeri |

## <a name="json-representation"></a>Json gösterimi

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
