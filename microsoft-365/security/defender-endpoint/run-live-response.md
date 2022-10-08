---
title: Cihazda canlı yanıt komutlarını çalıştırma
description: Bir cihazda bir dizi canlı yanıt komutu çalıştırmayı öğrenin.
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
- tier2
ms.topic: article
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 205cce10d0f443724b6d99c83d4b2075e8031d4f
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227998"
---
# <a name="run-live-response-commands-on-a-device"></a>Cihazda canlı yanıt komutlarını çalıştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)


[!include[Prerelease information](../../includes/prerelease.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Bir cihazda bir dizi canlı yanıt komutu çalıştırır

## <a name="limitations"></a>Sınırlamalar

1. Bu API'nin hız sınırlamaları dakikada 10 çağrıdır (ek istekler HTTP 429 ile yanıtlanır).

2. Eşzamanlı olarak çalışan 25 oturum (azaltma sınırını aşan istekler "429 - Çok fazla istek" yanıtı alır).

3. Makine kullanılamıyorsa oturum 3 güne kadar kuyruğa alınır.

4. RunScript komutu 10 dakika sonra zaman aşımına ular.

5. Canlı yanıt komutları kuyruğa alınamaz ve aynı anda yalnızca bir tane yürütülebilir.

6. Bu API çağrısını çalıştırmaya çalıştığınız makine, kendisine otomatik düzeltme düzeyi atanmamış bir RBAC cihaz grubundaysa, belirli bir Cihaz Grubu için en azından en düşük Düzeltme Düzeyini etkinleştirmeniz gerekir.
    > [!NOTE]
    > Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

7. Tek bir API çağrısında birden çok canlı yanıt komutu çalıştırılabilir. Ancak canlı yanıt komutu başarısız olduğunda sonraki tüm eylemler yürütülmeyecektir.

## <a name="minimum-requirements"></a>En Düşük Gereksinimler

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
|Uygulama|Machine.LiveResponse|Belirli bir makinede canlı yanıt çalıştırma|
|Temsilci (iş veya okul hesabı)|Machine.LiveResponse|Belirli bir makinede canlı yanıt çalıştırma|

## <a name="http-request"></a>HTTP isteği

```HTTP
POST https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>İstek üst bilgileri

|Name|Tür|Açıklama|
|---|---|---|
|Yetkilendirme|Dize|Taşıyıcı\<token>\. Gerekli.|
|İçerik Türü|Dize|application/json. Gerekli.|

## <a name="request-body"></a>İstek gövdesi

|Parametre|Tür|Açıklama|
|---|---|---|
|Açıklama ekleme|Dize|Eylemle ilişkilendirilecek açıklama.|
|Komut|Dizi|Çalıştırılacak komutlar. İzin verilen değerler PutFile, RunScript, GetFile değerleridir.|

## <a name="commands"></a>Komut

|Komut Türü|Parametre|Açıklama|
|---|---|---|
|PutFile|Anahtar: FileName <p> Değer: \<file name\>|Kitaplıktan cihaza bir dosya yerleştirir. Dosyalar çalışma klasörüne kaydedilir ve cihaz varsayılan olarak yeniden başlatıldığında silinir.
|Runscript|Anahtar: ScriptName <br> Değer: \<Script from library\> <p> Anahtar: Args <br> Değer: \<Script arguments\>|Bir cihazdaki kitaplıktan betik çalıştırır. <p>  Args parametresi betiğinize geçirilir. <p> 10 dakika sonra zaman aşımları.|
|Getfile|Anahtar: Yol <br> Değer: \<File path\>|Bir cihazdan dosya toplayın. NOT: Yoldaki ters eğik çizgilerden kaçınılmalıdır.|

## <a name="response"></a>Yanıt

- Başarılı olursa, bu yöntem 201 Oluşturuldu değerini döndürür.

  Eylem varlığı. Belirtilen kimlikte makine bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

burada isteğin bir örneği verilmiştir.

```HTTP
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

### <a name="response-example"></a>Yanıt örneği

Yanıtın bir örneği aşağıda verilmiştir.

```HTTP
HTTP/1.1 200 Ok
```

İçerik türü: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}
```

## <a name="related-topics"></a>İlgili konular

- [Makine eylem API'si alma](get-machineaction-object.md)
- [Canlı yanıt sonucu al](get-live-response-result.md)
- [Makine eylemini iptal et](cancel-machine-action.md)
