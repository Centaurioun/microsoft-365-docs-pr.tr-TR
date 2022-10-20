---
title: Canlı yanıt sonuçlarını alma
description: Dizinine göre belirli bir canlı yanıt komut sonucunu almayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, kitaplığa yükleme
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
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 8e3f9c132daf5b26f110056a77acad5a3da524da
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647551"
---
# <a name="get-live-response-results"></a>Canlı yanıt sonuçlarını alma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Dizinine göre belirli bir canlı yanıt komut sonucunu alır.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="minimum-requirements"></a>Minimum gereksinimler

Bir cihazda oturum başlatabilmeniz için önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:

- **Windows'un desteklenen bir sürümünü çalıştırdığınızı doğrulayın**.

  Cihazlar Windows'un aşağıdaki sürümlerinden birini çalıştırıyor olmalıdır

  - **Windows 11**
  
  - **Windows 10**
    - [Sürüm 1909](/windows/whats-new/whats-new-windows-10-version-1909) veya üzeri
    - [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384) ile [Sürüm 1903](/windows/whats-new/whats-new-windows-10-version-1903)
    - [KB4537818 ile](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) [Sürüm 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809)
    - [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795) ile [Sürüm 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803)
    - [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816) ile [Sürüm 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709)

  - **Windows Server 2019 - Yalnızca Genel önizleme için geçerlidir**
    - Sürüm 1903 veya ( [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384) ile) daha sonra
    - Sürüm 1809 ( [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) ile)
    
  - **Windows Server 2022**  

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz. [Kullanmaya başlama](apis-intro.md).

|İzin türü|Izni|İzin görünen adı|
|---|---|---|
Uygulama|Machine.Read.All|''Tüm makine profillerini oku''
Uygulama|"Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
|Temsilci (iş veya okul hesabı)|Machine.LiveResponse|Belirli bir makinede canlı yanıt çalıştırma|

## <a name="http-request"></a>HTTP isteği

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>İstek üst bilgileri

|Name|Tür|Açıklama|
|---|---|---|
|Yetkilendirme|Dize|Taşıyıcı {token}. Gerekli.|

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem *value* özelliğinde komut sonucunun bağlantısını tutan nesneyle 200 Tamam yanıt kodu döndürür. Bu bağlantı 30 dakika boyunca geçerlidir ve paketi yerel bir depolama alanına indirmek için hemen kullanılmalıdır. Süresi dolmuş bir bağlantı başka bir çağrı tarafından yeniden oluşturulabilir ve canlı yanıtı yeniden çalıştırmaya gerek yoktur.

*Runscript transkript özellikleri:*

|Özellik|Açıklama|
|---|---|
|script_name|Yürütülen betik adı|
|exit_code|Yürütülen betik çıkış kodu|
|script_output|Yürütülen betik standart çıkışı|
|script_errors|Yürütülen betik standart hata çıkışı|

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

HTTP/1.1 200 Tamam

İçerik türü: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Dosya içeriği:*

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_errors":""
}
```

## <a name="related-topics"></a>İlgili konular

- [Makine eylem API'si alma](get-machineaction-object.md)
- [Makine eylemini iptal et](cancel-machine-action.md)
- [Canlı yanıt çalıştır](run-live-response.md) 
