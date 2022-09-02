---
title: Tarayıcı uzantılarını dışarı aktarma değerlendirmesi
description: DeviceId, BrowserName, ExtensionID'nin her benzersiz bileşimi için bir giriş içeren bir tablo döndürür.
keywords: api, API'ler, dışarı aktarma değerlendirmesi, cihaz başına değerlendirme, güvenlik açığı değerlendirme raporu, cihaz güvenlik açığı değerlendirmesi, cihaz güvenlik açığı raporu, tarayıcı uzantısı değerlendirmesi
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
ms.openlocfilehash: 2d1313b4632e5b41b07d1f1f8cd09a0320a9ecbc
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523720"
---
# <a name="export-browser-extensions-assessment-per-device"></a>Cihaz başına tarayıcı uzantıları değerlendirmeyi dışarı aktarma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink).

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

Bilinen tüm yüklü tarayıcı uzantılarını ve bunların tüm cihazlara ilişkin ayrıntılarını cihaz başına temelinde döndürür.

Farklı API çağrıları farklı veri türleri alır. Veri miktarı büyük olabileceğinden, alınabilmesinin iki yolu vardır:

- [Tarayıcı uzantılarını dışarı aktarma değerlendirmesi **JSON yanıtı**](#1-export-browser-extensions-assessment-json-response) API, kuruluşunuzdaki tüm verileri Json yanıtları olarak çeker. Bu yöntem, _100 K'den az cihazı olan küçük kuruluşlar_ için en iyisidir. Yanıt sayfalandırılır, böylece yanıttan \@odata.nextLink alanını kullanarak sonraki sonuçları getirebilirsiniz.

- [Tarayıcı uzantıları değerlendirmeyi **dosyalar aracılığıyla** dışarı aktarma](#2-export-browser-extension-assessment-via-files) Bu API çözümü, daha fazla miktarda veriyi daha hızlı ve daha güvenilir bir şekilde çekmenizi sağlar. Bu nedenle, 100 K'den fazla cihazı olan büyük kuruluşlar için önerilir. Bu API, kuruluşunuzdaki tüm verileri indirme dosyaları olarak çeker. Yanıt, Azure Depolama'dan tüm verileri indirmek için URL'ler içerir. Bu API, Azure Depolama'dan tüm verilerinizi aşağıdaki gibi indirmenizi sağlar:
  - Tüm kuruluş verilerinizi içeren indirme URL'lerinin listesini almak için API'yi çağırın.
  - İndirme URL'lerini kullanarak tüm dosyaları indirin ve verileri istediğiniz gibi işleyin.

Toplanan veriler ( _Json yanıtı_ veya _dosyalar aracılığıyla_) geçerli durum anlık görüntüsüdür. Geçmiş verileri içermez. Geçmiş verileri toplamak için müşterilerin verileri kendi veri depolamalarına kaydetmesi gerekir.

> [!NOTE]
> Aksi belirtilmedikçe, listelenen tüm dışarı aktarma değerlendirme yöntemleri **_tam dışarı aktarma_** ve **_cihaza göredir_** ( **_cihaz başına_** olarak da adlandırılır).

## <a name="1-export-browser-extensions-assessment-json-response"></a>1. Tarayıcı uzantıları değerlendirmeyi dışarı aktarma (JSON yanıtı)

### <a name="11-api-method-description"></a>1.1 API yöntemi açıklaması

Bu API yanıtı, cihaz başına yüklenen tarayıcı uzantılarının tüm verilerini içerir. DeviceId, BrowserName, ExtensionId'nin her benzersiz bileşimi için bir giriş içeren bir tablo döndürür.

#### <a name="111-limitations"></a>1.1.1 Sınırlamaları

- En büyük sayfa boyutu 200.000'dir.
- Bu API için hız sınırlamaları dakikada 30 çağrı ve saatte 1000 çağrıdır.

### <a name="12-permissions"></a>1.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Software.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Software.Read|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'

### <a name="13-url"></a>1.3 URL

```http
GET api/Machines/BrowserExtensionsInventoryByMachine
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

****

Özellik (Kimlik)|Veri türü|Açıklama
:---|:---|:---
BrowserName|Dize|Uzantının yüklü olduğu tarayıcının adı.
Deviceıd|Dize|Cihaz için benzersiz tanımlayıcı.
DeviceName|Dize|Cihazın tam etki alanı adı (FQDN).
ExtensionDescription|Dize| Belirli bir tarayıcı uzantısının açıklaması.
ExtensionId|Dize|Belirli bir tarayıcı uzantısı için benzersiz tanımlayıcı.
ExtensionName|Dize|Belirli bir tarayıcı uzantısının adı.
ExtensionRisk|Dize|Tarayıcı uzantısı tarafından oluşturulan en yüksek risk düzeyi. Olası değerler şunlardır: "Yok", "Düşük", "Orta", "Yüksek", "Kritik".
ExtensionVersion|Dize|Belirli bir tarayıcı uzantısının sürüm numarası.
IsActivated|Boole|Tarayıcı uzantısının etkin olup olmadığını gösterir.
RbacGroupId|Tamsayı|Rol tabanlı erişim denetimi (RBAC) grup kimliği.
RbacGroupName|Dize|Rol tabanlı erişim denetimi (RBAC) grubu. Bu cihaz herhangi bir RBAC grubuna atanmamışsa, değer "Atanmamış" olur. Kuruluş herhangi bir RBAC grubu içermiyorsa, değer "Yok" olur.
InstallationTime|Dize|Tarayıcı uzantısının yüklendiği zaman.
İzinler|Dizi[dize]|Belirli bir tarayıcı uzantısı tarafından istenen izin kümesi.

### <a name="16-examples"></a>1.6 Örnekler

#### <a name="161-request-example"></a>1.6.1 İstek örneği

```http
GET https://api.securitycenter.microsoft.com/api/Machines/BrowserExtensionsInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>1.6.2 Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "DeviceId": "1c32162b42e9efa1f5de42f951775f22f435c997",
            "DeviceName": "computerpii_1363c2e016e2225cb03974df58f14e6968067aa8.domainpii_f260e982985f7e8eee198b4332e0ae5b2a069cd6.corp.microsoft.com",
            "RbacGroupId": 86,
            "RbacGroupName": "UnassignedGroup",
            "InstallationTime": "2022-05-26T18:46:27.000Z",
            "BrowserName": "chrome",
            "ExtensionId": "dkpejdfnpdkhifgbancbammdijojoffk",
            "ExtensionName": "Logitech Smooth Scrolling",
            "ExtensionDescription": "Buttery-smooth scrolling for Logitech mice and touchpads.",
            "ExtensionVersion": "6.65.62",
            "ExtensionRisk": "High",
            "IsActivated": true,
            "Permissions": [
                        {
                                    "Id": "tabs",
                                    "IsRequired": true,
                                    "Risk": "High"
                        },
                        {
                                    "Id": http://*/*,
                                    "IsRequired": true,
                                    "Risk": "High"
                        },
                        {
                                    "Id": https://*/*,
                                    "IsRequired": true,
                                    "Risk": "High"
                        }
            ]
}
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/Machines/BrowserExtensionsInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-browser-extension-assessment-via-files"></a>2. Tarayıcı uzantısı değerlendirmeyi dışarı aktarma (dosyalar aracılığıyla)

### <a name="21-api-method-description"></a>2.1 API yöntemi açıklaması

Bu API yanıtı, cihaz başına yüklenen tarayıcı uzantılarının tüm verilerini içerir. DeviceId, BrowserName, ExtensionId'nin her benzersiz bileşimi için bir giriş içeren bir tablo döndürür.

#### <a name="211-limitations"></a>2.1.1 Sınırlamaları

Bu API için hız sınırlamaları dakikada 5 çağrı ve saatte 20 çağrıdır.

### <a name="22-permissions"></a>2.2 İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Software.Read.All|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'
Temsilci (iş veya okul hesabı)|Software.Read|'Tehdit ve Güvenlik Açığı Yönetimi yazılım bilgilerini okuyun'

### <a name="23-url"></a>2.3 URL

```http
GET /api/Machines/BrowserExtensionsInventoryByMachine
```

### <a name="24-parameters"></a>2.4 Parametreler

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

### <a name="26-examples"></a>2.6 Örnekler

#### <a name="261-request-example"></a>2.6.1 İstek örneği

```http
GET https://api.securitycenter.microsoft.com/api/machines/BrowserExtensionsExport
```

#### <a name="262-response-example"></a>2.6.2 Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/BrowserExtensions/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Tarayıcı uzantıları izin bilgilerini alma](get-browser-extensions-permission-info.md)
- [Tarayıcı uzantıları değerlendirmesi](../defender-vulnerability-management/tvm-browser-extensions.md)

## <a name="other-related"></a>Diğer ilgililer

- [Güvenlik açığı yönetimi](../defender-vulnerability-management/defender-vulnerability-management.md)
- [Kuruluşunuzdaki güvenlik açıkları](../defender-vulnerability-management/tvm-weaknesses.md)
