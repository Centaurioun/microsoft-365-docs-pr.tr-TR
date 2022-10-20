---
title: machineAction kaynak türü
description: Uç Nokta için Microsoft Defender'de MachineAction kaynak türünün yöntemleri ve özellikleri hakkında bilgi edinin.
keywords: api'ler, desteklenen API'ler, get, machineaction, en son
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
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5b8bf60554d33cc99f59b1949e51d3d3f85a501e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646693"
---
# <a name="machineaction-resource-type"></a>MachineAction kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Daha fazla bilgi için bkz [. Yanıt Eylemleri](respond-machine-alerts.md).

|Yöntem|Dönüş Türü|Açıklama|
|---|---|---|
|[MachineActions Listele](get-machineactions-collection.md)|[Makine Eylemi](machineaction.md)|[Makine Eylemi](machineaction.md) varlıklarını listeleme.|
|[MachineAction Alma](get-machineaction-object.md)|[Makine Eylemi](machineaction.md)|Tek bir [Makine Eylemi](machineaction.md) varlığı alın.|
|[Soruşturma paketini toplayın](collect-investigation-package.md)|[Makine Eylemi](machineaction.md)|[Bir makineden](machine.md) araştırma paketi toplama.|
|[Araştırma paketi SAS URI'lerini al](get-package-sas-uri.md)|[Makine Eylemi](machineaction.md)|Araştırma paketini indirmek için URI'yi alın.|
|[Makineyi izole et](isolate-machine.md)|[Makine Eylemi](machineaction.md)|[Makineyi](machine.md) ağdan yalıtma.|
|[Makineyi izolasyondan çıkar](unisolate-machine.md)|[Makine Eylemi](machineaction.md)|[Makineyi](machine.md) Yalıtım'dan serbest bırakın.|
|[Uygulama yürütmeyi kısıtlayın](restrict-code-execution.md)|[Makine Eylemi](machineaction.md)|Uygulama yürütmeyi kısıtlayın.|
|[Uygulama kısıtlamasını kaldır](unrestrict-code-execution.md)|[Makine Eylemi](machineaction.md)|Uygulama yürütme kısıtlamasını kaldırın.|
|[Antivirüs taraması başlat](run-av-scan.md)|[Makine Eylemi](machineaction.md)|Windows Defender kullanarak bir AV taraması çalıştırın (uygun olduğunda).|
|[Offboard makine](offboard-machine-api.md)|[Makine Eylemi](machineaction.md)|[Makineyi](machine.md) Uç Nokta için Microsoft Defender'dan çıkar.|
|[Dur ve dosyayı karantinaya al](stop-and-quarantine-file.md)|[Makine Eylemi](machineaction.md)|Makinedeki bir dosyanın yürütülmesini durdurun ve silin.|
|[Canlı yanıt çalıştır](run-live-response.md)|[Makine Eylemi](machineaction.md)|Bir cihazda bir dizi canlı yanıt komutu çalıştırır|
|[Canlı yanıt sonucu al](get-live-response-result.md)|URL varlığı|Dizinine göre belirli canlı yanıt komut sonucu indirme bağlantısını alır.|
|[Makine eylemini iptal et](cancel-machine-action.md)|[Makine Eylemi](machineaction.md)|Etkin makine eylemini iptal etme.|

<br>

## <a name="properties"></a>Özellikler

|Özellik|Tür|Açıklama|
|---|---|---|
|Kimlik|Guıd|[Makine Eylemi](machineaction.md) varlığının kimliği.|
|Türü|Enum|Eylemin türü. Olası değerler şunlardır: "RunAntiVirusScan", "Offboard", "Live Response", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" ve "UnrestrictCodeExecution".|
|Kapsam|Dize|Eylemin kapsamı. Yalıtım için "Tam" veya "Seçmeli", Virüsten Koruma taraması için "Hızlı" veya "Tam".|
|Isteyici|Dize|Eylemi yürüten kişinin kimliği.|
|externalID|Dize|Müşterinin özel bağıntı isteğinde gönderebileceği kimlik.|
|requestSource|Dize|Eylemi gönderen kullanıcının/uygulamanın adı.|
|Komut|Dizi|Çalıştırılacak komutlar. İzin verilen değerler PutFile, RunScript, GetFile değerleridir.|
|cancellationRequestor|Dize|Eylemi iptal eden kişinin kimliği.|
|requestorComment|Dize|Eylemi düzenlerken yazılan açıklama.|
|cancellationComment|Dize|Eylem iptal edildiğinde yazılan açıklama.|
|Durum|Enum|Komutun geçerli durumu. Olası değerler şunlardır: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" ve "Cancelled".|
|machineId|Dize|Eylemin yürütüldiği [makinenin](machine.md) kimliği.|
|computerDnsName|Dize|Eylemin yürütüldiği [makinenin](machine.md) adı.|
|creationDateTimeUtc|Datetimeoffset|Eylemin oluşturulduğu tarih ve saat.|
|cancellationDateTimeUtc|Datetimeoffset|Eylemin iptal edildiği tarih ve saat.|
|lastUpdateDateTimeUtc|Datetimeoffset|Eylem durumunun güncelleştirildiği son tarih ve saat.|
|Başlık|Dize|Makine eylemi başlığı.|
|relatedFileInfo|Sınıfı|İki Özellik içerir. dize `fileIdentifier`, Olası değerlerle enum `fileIdentifierType` : "Sha1", "Sha256", ve "Md5".|

## <a name="json-representation"></a>Json gösterimi

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
