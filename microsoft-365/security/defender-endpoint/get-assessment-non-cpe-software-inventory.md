---
title: Cihaz başına ürün kodu olmayan yazılım envanteri değerlendirmeyi dışarı aktarma
description: Common Platform Sabit Listesi (CPE) olmayan yazılımlar için DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion'ın her benzersiz bileşimi için bir giriş içeren bir tablo döndürür
keywords: api, API'ler, dışarı aktarma değerlendirmesi, cihaz başına değerlendirme, güvenlik açığı değerlendirme raporu, cihaz güvenlik açığı değerlendirmesi, cihaz güvenlik açığı raporu, güvenli yapılandırma değerlendirmesi, güvenli yapılandırma raporu, yazılım güvenlik açıkları değerlendirmesi, yazılım güvenlik açığı raporu, makineye göre güvenlik açığı raporu,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 869342240c81c1a337b5241a0b5e2e8308f843b5
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68629731"
---
# <a name="export-non-product-code-software-inventory-assessment-per-device"></a>Cihaz başına ürün kodu olmayan yazılım envanteri değerlendirmeyi dışarı aktarma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu API, cihaz başına [ortak platform numaralandırması (CPE)](https://nvd.nist.gov/products/cpe) olmayan yüklü yazılımlara yönelik tüm verileri döndürür. CPE'ye sahip yazılımlara yönelik olarak, bu API tarafından döndürülen bilgiler ve [Yazılım envanteri değerlendirme](get-assessment-non-cpe-software-inventory.md) API'sinin verdiği bilgiler, kuruluşunuzda yüklü olan yazılımlar ve yüklü olduğu cihazlar hakkında tam görünürlük sağlar.

> [!NOTE]
> CPE içermeyen yazılım ürünleri güvenlik açığı yönetimi tarafından desteklenmez. Bunlar yazılım envanteri sayfasında gösterilir, ancak CPE'ler yazılımı tanımlamak için güvenlik açığı yönetimi tarafından kullanıldığından ve güvenlik açıkları, açıklardan yararlanmalar, kullanıma sunulan cihaz sayısı ve zayıflıklar gibi güvenlik açıkları bunlar için kullanılamaz. Daha fazla bilgi için bkz [. Yazılım envanteri](../defender-vulnerability-management/tvm-software-inventory.md).

Farklı API çağrıları farklı veri türleri alır. Veri miktarı büyük olabileceğinden, alınabilmesinin iki yolu vardır:

- [Ürün kodu olmayan yazılım envanteri değerlendirmesi **JSON yanıtlarını** dışarı aktarma](#1-export-non-product-code-software-inventory-assessment-json-response) API, kuruluşunuzdaki tüm verileri Json yanıtları olarak çeker. Bu yöntem, _100 K'den az cihazı olan küçük kuruluşlar_ için en iyisidir. Yanıt sayfalandırılır, böylece yanıttan \@odata.nextLink alanını kullanarak sonraki sonuçları getirebilirsiniz.

- [**Dosyalar aracılığıyla** ürün kodu olmayan yazılım envanteri değerlendirmelerini dışarı aktarma](#2-export-non-product-code-software-inventory-assessment-via-files)  Bu API çözümü, daha fazla miktarda veriyi daha hızlı ve daha güvenilir bir şekilde çekmenizi sağlar. Bu nedenle, 100 K'den fazla cihazı olan büyük kuruluşlar için önerilir. Bu API, kuruluşunuzdaki tüm verileri indirme dosyaları olarak çeker. Yanıt, Azure Depolama'dan tüm verileri indirmek için URL'ler içerir. Bu API, Azure Depolama'dan tüm verilerinizi aşağıdaki gibi indirmenizi sağlar:
  - Tüm kuruluş verilerinizi içeren indirme URL'lerinin listesini almak için API'yi çağırın.
  - İndirme URL'lerini kullanarak tüm dosyaları indirin ve verileri istediğiniz gibi işleyin.

Toplanan veriler ( _Json yanıtı_ veya _dosyalar aracılığıyla_) geçerli durum anlık görüntüsüdür. Geçmiş verileri içermez. Geçmiş verileri toplamak için müşterilerin verileri kendi veri depolamalarına kaydetmesi gerekir.

> [!NOTE]
> Aksi belirtilmedikçe, listelenen tüm dışarı aktarma değerlendirme yöntemleri **_tam dışarı aktarma_** ve **_cihaza göredir_** ( **_cihaz başına_** olarak da adlandırılır).

## <a name="1-export-non-product-code-software-inventory-assessment-json-response"></a>1. Dışarı aktarma ürün kodu olmayan yazılım envanteri değerlendirmesi (JSON yanıtı)

### <a name="11-api-method-description"></a>1.1 API yöntemi açıklaması

Bu API yanıtı, cihaz başına [Ortak Platform Numaralandırması (CPE)](https://nvd.nist.gov/products/cpe) içermeyen yüklü yazılımların tüm verilerini içerir. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion'ın her benzersiz bileşimi için bir giriş içeren bir tablo döndürür.

#### <a name="limitations"></a>Sınırlamalar

- En büyük sayfa boyutu 200.000'dir.
- Bu API için hız sınırlamaları dakikada 30 çağrı ve saatte 1000 çağrıdır.

### <a name="12-permissions"></a>1.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Software.Read.All|\'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun\'
Temsilci (iş veya okul hesabı)|Software.Read|\'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryNoProductCodeByMachine
```

### <a name="14-parameters"></a>1.4 Parametreler

- pageSize (varsayılan = 50.000): Yanıt olarak sonuç sayısı.
- $top: Döndürülecek sonuç sayısı (@odata.nextLink döndürmez ve bu nedenle tüm verileri çekmez)

### <a name="15-properties"></a>1.5 Özellikleri

> [!NOTE]
>
> - Her kayıt yaklaşık 0,5 KB veridir. Sizin için doğru pageSize parametresini seçerken bunu dikkate almanız gerekir.
> - Aşağıdaki tabloda tanımlanan özellikler, özellik kimliğine göre alfabetik olarak listelenir. Bu API'yi çalıştırırken, sonuçta elde edilen çıktının bu tabloda listelenen sırayla döndürülmesi gerekmez.
> - Yanıtta bazı ek sütunlar döndürülebilir. Bu sütunlar geçicidir ve kaldırılabilir, lütfen yalnızca belgelenmiş sütunları kullanın.

<br>

Özellik (Kimlik)|Veri türü|Açıklama
:---|:---|:---
Deviceıd|Dize|Hizmetteki cihaz için benzersiz tanımlayıcı.
DeviceName|Dize|Cihazın tam etki alanı adı (FQDN).
OSPlatform|Dize|Cihazda çalışan işletim sisteminin platformu. Bunlar, Windows 10 ve Windows 11 gibi aynı aile içinde varyasyonları olan belirli işletim sistemleridir. Ayrıntılar için [bkz. Desteklenen işletim sistemleri, platformlar ve özellikler](../defender-vulnerability-management/tvm-supported-os.md) .
RbacGroupName|Dize|Rol tabanlı erişim denetimi (RBAC) grubu. Bu cihaz herhangi bir RBAC grubuna atanmamışsa, değer "Atanmamış" olur. Kuruluş herhangi bir RBAC grubu içermiyorsa, değer "Yok" olur.
RbacGroupId|Dize|Rol tabanlı erişim denetimi (RBAC) grup kimliği.
SoftwareLastSeenTimestamp|Dize|Bu yazılımın cihazda son görüldüğü zaman.
SoftwareName|Dize|Yazılım ürününün adı.
SoftwareVendor|Dize|Yazılım satıcısının adı.
SoftwareVersion|Dize|Yazılım ürününün sürüm numarası.

### <a name="16-examples"></a>1.6 Örnekler

#### <a name="161-request-example"></a>1.6.1 İstek örneği

```http
https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pageSize=3  &sinceTime=2021-05-19
```

#### <a name="162-response-example"></a>1.6.2 Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetNonCpeSoftware)",
    "value": [
        {
           "deviceId": "1234512345123451234512345",
            "rbacGroupId": 11,
            "rbacGroupName": "London",
            "deviceName": "Device1",
            "osPlatform": "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "vs_communitymsi",
            "softwareVersion": "11.11.31111.1",
            "softwareLastSeenTimestamp": "2021-01-30 11:31:12.271"
        },
        {
            "deviceId": "232323232323232322323232323",
            "rbacGroupId": 23,
            "rbacGroupName": "Tokyo",
            "deviceName": "Device23",
            "osPlatform": "Windows10",
            "softwareVendor": "intel",
            "softwareName": "intel®_software_installer",
            "softwareVersion": "22.20.2.2",
            "softwareLastSeenTimestamp": "2022-05-30 15:35:12.271"
        },
        {
            "deviceId": "6565656565",
            "rbacGroupId": 65,
            "rbacGroupName": "Center",
            "deviceName": "Device56",
            "osPlatform": "Windows10",
            "softwareVendor": "Lob Apps",
            "softwareName": "Headtrax",
            "softwareVersion": "60.273.3",
            "softwareLastSeenTimestamp": "2022-05-05 15:35:12.271"
        },
    ],
        "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pagesize=3%20%20&sincetime=2021-05-19&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMi0wNS0zMC8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}

```

## <a name="2-export-non-product-code-software-inventory-assessment-via-files"></a>2. Ürün kodu olmayan yazılım envanteri değerlendirmeyi dışarı aktarma (dosyalar aracılığıyla)

### <a name="21-api-method-description"></a>2.1 API yöntemi açıklaması

Bu API yanıtı, cihaz başına [Ortak Platform Numaralandırması (CPE)](https://nvd.nist.gov/products/cpe) içermeyen yüklü yazılımların tüm verilerini içerir. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion'ın her benzersiz bileşimi için bir giriş içeren bir tablo döndürür.

#### <a name="211-limitations"></a>2.1.1 Sınırlamaları

Bu API için hız sınırlamaları dakikada 5 çağrı ve saatte 20 çağrıdır.

### <a name="22-permissions"></a>2.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Software.Read.All|\'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun\'
Temsilci (iş veya okul hesabı)|Software.Read|\'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/Api/Machines/SoftwareInventoryNonCpeExport
```

### <a name="parameters"></a>Parametre

- sasValidHours: İndirme URL'lerinin geçerli olacağı saat sayısı (En fazla 24 saat)

### <a name="25-properties"></a>2.5 Özellikleri

> [!NOTE]
>
> - Dosyalar çok satırlı JSON biçiminde gzip sıkıştırılmış &.
> - İndirme URL'leri yalnızca 3 saat geçerlidir. Aksi takdirde parametresini kullanabilirsiniz.
> - Verilerinizin en yüksek indirme hızı için, verilerinizin bulunduğu Azure bölgesinden indirme yaptığınızdan emin olabilirsiniz.

<br>

****

Özellik (Kimlik)|Veri türü|Açıklama|Döndürülen değer örneği
:---|:---|:---|:---
Dosyaları dışarı aktarma|dizi\[dizesi\]|Kuruluşun geçerli anlık görüntüsünü tutan dosyalar için indirme URL'lerinin listesi|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|Dize|Dışarı aktarmanın oluşturulduğu zaman.|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 Örnekler

#### <a name="261-request-example"></a>2.6.1 İstek örneği

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNonCpeExport
```

#### <a name="262-response-example"></a>2.6.2 Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00337-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=aHnmuOKlIvpR0PsdamYfmCCDZ1nhpuXBzK2%2FkJ9xTpg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00338-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=0fQg%2Ft469x26KvPLmvctLl0g6DC38CNM3lXYi9dnFfo%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00339-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=P6HGHoLXXipMauBpLueoQVrwHL7qmvLoCjcij6ERx8o%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00340-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=VnpVct%2F8vdiIFTf2xXP9DF7ngWv1Zqew30q2jBPVghg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00341-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=GY0zxMfEmr9v9fZBWYyKEtT2k%2F0ELQIlOP0ct%2B6SdGU%3D",
    ],
    "generatedTime": "2022-05-30T11:01:00Z"
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Cihaz başına yazılım değerlendirmeyi dışarı aktarma](get-assessment-software-inventory.md)
- [Cihaz başına değerlendirme yöntemlerini ve özelliklerini dışarı aktarma](get-assessment-methods-properties.md)
- [Cihaz başına güvenli yapılandırma değerlendirmelerini dışarı aktarma](get-assessment-secure-config.md)
- [Cihaz başına yazılım güvenlik açıkları değerlendirmesi dışarı aktarma](get-assessment-software-vulnerabilities.md)

Diğer ilgililer
- [Microsoft Defender Güvenlik Açığı Yönetimi](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Kuruluşunuzdaki güvenlik açıkları](tvm-weaknesses.md)
