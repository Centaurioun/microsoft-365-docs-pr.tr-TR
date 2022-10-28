---
title: Microsoft Defender Virüsten Koruma Cihaz Durumu dışarı aktarma cihazı virüsten koruma sistem durumu raporlama
description: Microsoft Defender Virüsten Koruma cihaz durumu ayrıntılarını almak için yöntemler sunar.
keywords: api'ler, graf api'leri, desteklenen API'ler, get, cihaz durumu API'si, Uç Nokta için Microsoft Defender rapor api'si microsoft defender reports api, uç nokta raporlama API'si için microsoft defender, windows defender raporlama API'si, uç nokta raporlama api'leri için defender, windows defender rapor api'si
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 09/01/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 76e200022f01836195d82d46f159d35701f77a29
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770337"
---
<!-- v-jweston/jweston-1 is scheduled to resume authorship Apr/May 2023.-->

# <a name="export-device-antivirus-health-report"></a>Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

Bu API,virüsten koruma cihazı virüsten koruma sistem durumu ayrıntılarını Microsoft Defender almak için iki yönteme sahiptir:

- **Birinci yöntem:** [1 Sistem durumu raporlama \(**JSON yanıtını**\) dışarı aktarma](#1-export-health-reporting-json-response) Yöntemi, kuruluşunuzdaki tüm verileri JSON yanıtları olarak çeker. Bu yöntem, _100 K'den az cihazı olan küçük kuruluşlar_ için en iyisidir. Yanıt sayfalandırılır, böylece yanıttan \@odata.nextLink alanını kullanarak sonraki sonuçları getirebilirsiniz.

- **İkinci yöntem:** [2 Sistem durumu raporlamasını \(**dosyalar**\) aracılığıyla dışarı aktarma](#2-export-health-reporting-via-files) Bu yöntem, daha büyük miktarlardaki verilerin daha hızlı ve daha güvenilir bir şekilde çekilmesini sağlar. Bu nedenle, 100 K'den fazla cihazı olan büyük kuruluşlar için önerilir. Bu API, kuruluşunuzdaki tüm verileri indirme dosyaları olarak çeker. Yanıt, Azure Depolama'dan tüm verileri indirmek için URL'ler içerir. Bu API, Azure Depolama'dan tüm verilerinizi aşağıdaki gibi indirmenizi sağlar:
  - Tüm kuruluş verilerinizi içeren indirme URL'lerinin listesini almak için API'yi çağırın.
  - İndirme URL'lerini kullanarak tüm dosyaları indirin ve verileri istediğiniz gibi işleyin.

'_JSON yanıtı_ veya _dosyalar aracılığıyla_' kullanılarak toplanan veriler, geçerli durumu gösteren geçerli anlık görüntüdür. Geçmiş verileri içermez. Geçmiş verileri toplamak için müşterilerin verileri kendi veri depolamalarına kaydetmesi gerekir. Bkz [. Cihaz durumu ayrıntılarını DıŞARı aktarma API yöntemleri ve özellikleri](device-health-api-methods-properties.md).

> [!IMPORTANT]
>
> Şu anda yalnızca **Virüsten Koruma Durumu JSON Yanıtı** genel kullanıma sunulmuştur. **Dosyalar aracılığıyla Virüsten Koruma Sistem Durumu API'sini** şu anda yalnızca genel önizlemede kullanabilirsiniz.
>
> **Gelişmiş Tehdit Avcılığı özel sorgusu** şu anda sorgular hala görünür olsa bile yalnızca genel önizlemede kullanılabilir.

> [!IMPORTANT]
>
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

> [!NOTE]
>
> Microsoft 365 Güvenlik panosunda **Cihaz durumu ve virüsten koruma uyumluluk** raporlama aracını kullanma hakkında bilgi için bkz. [Uç Nokta için Microsoft Defender'da cihaz durumu ve virüsten koruma uyumluluk raporu](machine-reports.md).
>

## <a name="1-export-health-reporting-json-response"></a>1 Sistem durumu raporlamayı dışarı aktarma (JSON yanıtı)

### <a name="11-api-method-description"></a>1.1 API yöntemi açıklaması

Bu API, Microsoft Defender Virüsten Koruma cihazı virüsten koruma sistem durumu ayrıntılarının listesini alır. Her benzersiz bileşimi için bir giriş içeren bir tablo döndürür:

- Deviceıd
- Cihaz adı
- AV modu
- Güncel durum
- Tarama sonuçları

#### <a name="111-limitations"></a>1.1.1 Sınırlamaları

- en büyük sayfa boyutu 200.000'dir
- Bu API için hız sınırlamaları şunlardır (**_dakika_** başına 30 çağrı ve hour._ başına 1000 çağrı)

#### <a name="odata-supported-operators"></a>OData tarafından desteklenen işleçler

- `$filter`on: `machineId`, `computerDnsName`, `osKind`, , `osPlatform`, `osVersion`, `avMode`, , `avSignatureVersion`, `avEngineVersion`, `avPlatformVersion`, `quickScanResult`, `quickScanError`, `fullScanResult`, , `fullScanError`, `avIsSignatureUpToDate``avIsEngineUpToDate`, `avIsPlatformUpToDate``rbacGroupId`
- `$top` 10.000 maksimum değere sahip.
- `$skip`

### <a name="12-permissions"></a>1.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.

| İzin türü | Izni | İzin görünen adı |
|:---|:---|:---|
| Uygulama | Machine.Read.All | 'Tüm makine profillerini oku' |
|Temsilci (iş veya okul hesabı) | Machine.Read | 'Makine bilgilerini oku' |

### <a name="13-url-http-request"></a>1.3 URL 'si (HTTP isteği)

```http
URL: GET: /api/deviceavinfo
```

#### <a name="131-request-headers"></a>1.3.1 İstek üst bilgileri

| Name | Tür | Açıklama |
|:---|:---|:---|
| Yetkilendirme | Dize | Taşıyıcı {token}. Gerekli. |

#### <a name="132-request-body"></a>1.3.2 İstek gövdesi

Boş

#### <a name="133-response"></a>1.3.3 Yanıtı

Başarılı olursa, bu yöntem cihaz durumu ayrıntılarının listesiyle birlikte 200 Tamam döndürür.

### <a name="14-parameters"></a>1.4 Parametreler

- Varsayılan sayfa boyutu 20'dir
- [Uç Nokta için Microsoft Defender ile OData sorgularında örneklere](exposed-apis-odata-samples.md) bakın.

### <a name="15-properties"></a>1.5 Özellikleri

Bkz. [1.2 Cihaz virüsten koruma sistem durumu ayrıntılarını dışarı aktarma API özellikleri (JSON yanıtı)](device-health-api-methods-properties.md#12-export-device-antivirus-health-details-api-properties-json-response)

[OData V4 sorgularını](https://www.odata.org/documentation/) destekler.

### <a name="16-example"></a>1.6 Örnek

#### <a name="request-example"></a>İstek örneği

Örnek bir istek aşağıda verilmişti:

```http
GET https://api.securitycenter.microsoft.com/api/deviceavinfo
```

#### <a name="response-example"></a>Yanıt örneği

Aşağıda örnek bir yanıt verilmişti:

```json
{

    @odata.context: "https://api.securitycenter.microsoft.com/api/$metadata#DeviceAvInfo",

"value": [{

            "id": "Sample Guid",

            "machineId": "Sample Machine Guid",

            "computerDnsName": "appblockstg1",

            "osKind": "windows",

            "osPlatform": "Windows10",

            "osVersion": "10.0.19044.1865",

            "avMode": "0",

            "avSignatureVersion": "1.371.1279.0",

            "avEngineVersion": "1.1.19428.0",

            "avPlatformVersion": "4.18.2206.108",

            "lastSeenTime": "2022-08-02T19:40:45Z",

            "quickScanResult": "Completed",

            "quickScanError": "",

            "quickScanTime": "2022-08-02T18:40:15.882Z",

            "fullScanResult": "",

            "fullScanError": "",

            "fullScanTime": null,

            "dataRefreshTimestamp": "2022-08-02T21:16:23Z",

            "avEngineUpdateTime": "2022-08-02T00:03:39Z",

            "avSignatureUpdateTime": "2022-08-02T00:03:39Z",

            "avPlatformUpdateTime": "2022-06-20T16:59:35Z",

            "avIsSignatureUpToDate": "True",

            "avIsEngineUpToDate": "True",

            "avIsPlatformUpToDate": "True",

            "avSignaturePublishTime": "2022-08-02T00:03:39Z",

            "rbacGroupName": "TVM1",

            "rbacGroupId": 4415

        },

        ...

     ]

}
```

## <a name="2-export-health-reporting-via-files"></a>2 Sistem durumu raporlamayı dışarı aktarma (dosyalar aracılığıyla)

> [!IMPORTANT]
> Bu bölümdeki bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

### <a name="21-api-method-description"></a>2.1 API yöntemi açıklaması

Bu API yanıtı, cihaz başına virüsten koruma durumunun ve durumunun tüm verilerini içerir. Her benzersiz bileşimi için bir giriş içeren bir tablo döndürür:

- Deviceıd
- cihaz adı
- AV modu
- Güncel durum
- Tarama sonuçları

#### <a name="212-limitations"></a>2.1.2 Sınırlamaları

- En büyük sayfa boyutu 200.000'dir.
- Bu API için hız sınırlamaları dakikada 30 çağrı ve saatte 1000 çağrıdır.

### <a name="22-permissions"></a>2.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir.

| İzin türü | Izni | İzin görünen adı |
|:---|:---|:---|
| Uygulama | Vulnerability.Read.All | '"Tehdit ve Güvenlik Açığı Yönetimi" güvenlik açığı bilgilerini okuyun' |
| Temsilci (iş veya okul hesabı) | Vulnerability.Read | '"Tehdit ve Güvenlik Açığı Yönetimi" güvenlik açığı bilgilerini okuyun' |

İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma](apis-intro.md).

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/InfoGatheringExport
```

### <a name="24-parameters"></a>2.4 Parametreler

- `sasValidHours`: İndirme URL'lerinin geçerli olacağı saat sayısı (En fazla 24 saat).

### <a name="25-properties"></a>2.5 Özellikleri

Bkz. [1.3 Dosyalar aracılığıyla\) cihaz virüsten koruma sistem durumu ayrıntılarını API özelliklerini \(dışarı aktarma](device-health-api-methods-properties.md#13-export-device-antivirus-health-details-api-properties-via-files).

### <a name="26-examples"></a>2.6 Örnekler

#### <a name="261-request-example"></a>2.6.1 İstek örneği

Örnek bir istek aşağıda verilmişti:

```HTTP
GET https://api-us.securitycenter.contoso.com/api/machines/InfoGatheringExport
```

#### <a name="262-response-example"></a>2.6.2 Yanıt örneği

Aşağıda örnek bir yanıt verilmişti:

```json
{

   "@odata.context": "https://api-us.securitycenter.windows.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",

   "exportFiles": [

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=..",

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=.."

   ],


   "generatedTime": "2022-08-02T22:01:00Z"


}
```

## <a name="see-also"></a>Ayrıca bkz.

[Cihaz sistem durumu yöntemlerini ve özelliklerini dışarı aktarma](device-health-api-methods-properties.md)

[Cihaz durumu ve uyumluluk raporlaması](device-health-reports.md)
