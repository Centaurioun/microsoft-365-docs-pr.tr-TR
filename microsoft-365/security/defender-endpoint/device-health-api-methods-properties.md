---
title: Microsoft Defender Virüsten koruma dışarı aktarma cihazı virüsten koruma sistem durumu ayrıntıları API yöntemleri ve özellikleri
description: Microsoft Defender Virüsten Koruma cihaz durumu ayrıntılarının listesini dışarı aktarmayı öğrenin.
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
- ContentEngagementFY23
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: d2056fc380aa1d133c68b8a4ddfe697fd76283a0
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621196"
---
# <a name="export-device-antivirus-health-details-api-methods-and-properties"></a>Cihaz virüsten koruma sistem durumu ayrıntılarını API yöntemleri ve özelliklerini dışarı aktarma

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="export-device-antivirus-health-details-api-description"></a>Cihaz virüsten koruma sistem durumu ayrıntılarını dışarı aktarma API'si açıklaması

Microsoft Defender Virüsten Koruma cihaz durumu ayrıntılarının listesini alır. Bu API'nin farklı veri türlerini almak için farklı API çağrıları (yöntemleri) vardır. Veri miktarı büyük olabileceğinden, alınabilmesinin iki yolu vardır:

- **JSON yanıtı**  API, kuruluşunuzdaki tüm verileri JSON yanıtları olarak çeker. Bu yöntem, _100 K'den az cihazı olan küçük kuruluşlar_ için en iyisidir. Yanıt sayfalandırılır, böylece yanıttan \@odata.nextLink alanını kullanarak sonraki sonuçları getirebilirsiniz.

- **dosyalar aracılığıyla** Bu API çözümü, daha fazla miktarda veriyi daha hızlı ve daha güvenilir bir şekilde çekmenizi sağlar. Bu nedenle, 100 K'den fazla cihazı olan büyük kuruluşlar için önerilir. Bu API, kuruluşunuzdaki tüm verileri indirme dosyaları olarak çeker. Yanıt, Azure Depolama'dan tüm verileri indirmek için URL'ler içerir. Bu API, Azure Depolama'dan tüm verilerinizi aşağıdaki gibi indirmenizi sağlar:
  - Tüm kuruluş verilerinizi içeren indirme URL'lerinin listesini almak için API'yi çağırın.
  - İndirme URL'lerini kullanarak tüm dosyaları indirin ve verileri istediğiniz gibi işleyin.

'_JSON yanıtı_ veya _dosyalar aracılığıyla_' kullanılarak toplanan veriler, geçerli durumu gösteren geçerli anlık görüntüdür. Geçmiş verileri içermez. Geçmiş verileri toplamak için müşterilerin verileri kendi veri depolamalarına kaydetmesi gerekir.

> [!IMPORTANT]
>
> Şu anda yalnızca **Virüsten Koruma Durumu JSON Yanıtı** genel kullanıma sunulmuştur. **Dosyalar aracılığıyla Virüsten Koruma Sistem Durumu API'sini** şu anda yalnızca genel önizlemede kullanabilirsiniz.
>
> **Gelişmiş Tehdit Avcılığı özel sorgusu** şu anda sorgular hala görünür olsa bile yalnızca genel önizlemede kullanılabilir.
>
> Windows Server 2012 R2 ve Windows Server 2016 cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).
>
> Microsoft 365 Güvenlik panosunda **Cihaz durumu ve virüsten koruma uyumluluk** raporlama aracını kullanma hakkında bilgi için bkz. [Uç Nokta için Microsoft Defender'de cihaz durumu ve virüsten koruma raporu](device-health-reports.md).

### <a name="11-export-device-antivirus-health-details-api-methods"></a>1.1 Cihaz virüsten koruma sistem durumu ayrıntılarını dışarı aktarma API yöntemleri

Yöntem|Veri türü|Açıklama
:---|:---|:---
**(JSON yanıtı)**|Microsoft Defender Cihaz koleksiyonu başına virüsten koruma durumu. Bkz. [1.2 Cihaz virüsten koruma sistem durumu ayrıntılarını dışarı aktarma API özellikleri (JSON yanıtı)](#12-export-device-antivirus-health-details-api-properties-json-response)|DeviceId, ConfigurationId'nin her benzersiz bileşimi için bir giriş içeren bir tablo döndürür. | API, kuruluşunuzdaki tüm verileri JSON yanıtları olarak çeker. Bu yöntem, 100 K'den az cihazı olan küçük kuruluşlar için en iyisidir. Yanıt sayfalandırılır, böylece yanıttan @odata.nextLink alanını kullanarak sonraki sonuçları getirebilirsiniz.
**(dosyalar aracılığıyla)**|Microsoft Defender Cihaz koleksiyonu başına virüsten koruma durumu. Bkz. [1.3 Dosyalar aracılığıyla\) cihaz virüsten koruma sistem durumu ayrıntılarını API özelliklerini \(dışarı aktarma](#13-export-device-antivirus-health-details-api-properties-via-files)|DeviceId, ConfigurationId'nin her benzersiz bileşimi için bir giriş içeren bir tablo döndürür. |Bu API çözümü, daha fazla miktarda veriyi daha hızlı ve daha güvenilir bir şekilde çekmenizi sağlar. Bu nedenle, 100 K'den fazla cihazı olan büyük kuruluşlar için önerilir. Bu API, kuruluşunuzdaki tüm verileri indirme dosyaları olarak çeker. Yanıt, Azure Depolama'dan tüm verileri indirmek için URL'ler içerir. Bu API, Azure Depolama'dan tüm verilerinizi aşağıdaki gibi indirmenizi sağlar: <ol><li>Tüm kuruluş verilerinizi içeren indirme URL'lerinin listesini almak için API'yi çağırın.</li><li>İndirme URL'lerini kullanarak tüm dosyaları indirin ve verileri istediğiniz gibi işleyin.</li></ol>

### <a name="12-export-device-antivirus-health-details-api-properties-json-response"></a>1.2 Cihaz virüsten koruma sistem durumu ayrıntıları API özelliklerini dışarı aktarma (JSON yanıtı)

> [!NOTE]
>
> - Aşağıdaki tabloda tanımlanan özellikler, özellik kimliğine göre alfabetik olarak listelenir. Bu API'yi çalıştırırken, sonuçta elde edilen çıktının bu tabloda listelenen sırayla döndürülmesi gerekmez.
> - Yanıtta bazı ek sütunlar döndürülebilir. Bu sütunlar geçicidir ve kaldırılabilir; lütfen yalnızca belgelenmiş sütunları kullanın.

| Özellik (Kimlik) | Veri türü | Açıklama | Döndürülen değer örneği |
|:----|:----|:----|:----|
| avEngineUpdateTime | Datetimeoffset | AV altyapısının cihazda en son güncelleştirildiği tarih saat | "2022-08-04T12:44:02Z" |
| avEngineVersion | Dize | Virüsten koruma altyapısı sürümü | "1.1.19400.3" |
| avIsEngineUpToDate | Dize | AV altyapısının güncel durumu | "True", "False", "Unknown" |
| avIsPlatformUpToDate | Dize | AV platformunun güncel durumu | "True", "False", "Unknown" |
| avIsSignatureUpToDate | Dize | AV imzasının güncel durumu | "True", "False", "Unknown" |
| avMode | Dize | Virüsten koruma modu. | Her mod, 0 ile 5 arasında bir dize türündeki tamsayı değeri olacaktır. Değerinin anlamını görmek için aşağıdaki eşlemeye bakın: <ul><li>'' = Diğer</li><li> '0' = Etkin</li><li> '1' = Pasif</li><li> '2' = Devre Dışı</li><li> '3' = Diğer</li><li> '4' = EDRBlocked</li><li>'5' = PassiveAudit</li></ul> |
| avPlatformUpdateTime | Datetimeoffset | AV platformlarının cihazda en son güncelleştirildiği tarih saat | "2022-08-04T12:44:02Z" |
| avPlatformVersion | Dize | Virüsten koruma platformu sürümü | "4.18.2203.5" |
| avSignaturePublishTime | Datetimeoffset | AV güvenlik zekası derlemesi yayımlandığında tarih saat | "2022-08-04T12:44:02Z" |
| avSignatureUpdateTime | Datetimeoffset | AV güvenlik zekası cihazda en son ne zaman güncelleştirildi? | "2022-08-04T12:44:02Z" |
| avSignatureVersion | Dize | Virüsten koruma güvenlik bilgileri sürümü | "1.371.1323.0" |
| computerDnsName | Dize | DNS adı | "SampleDns" |
| dataRefreshTimestamp | Datetimeoffset | Bu rapor için verilerin yenilendiği tarih saat | "2022-08-04T12:44:02Z" |
| fullScanError | Dize | Tam taramadan hata kodları | "0x80508023" |
| fullScanResult | Dize | Bu cihazın tam tarama sonucu | "Tamamlandı" <br> "İptal edildi" <br>"Başarısız" |
| fullScanTime | Datetimeoffset | Tam tarama tamamlandığında tarih saat | "2022-08-04T12:44:02Z" |
| Kimliği | Dize | Makine GUID'i | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| lastSeenTime | Datetimeoffset | Bu makinenin son görüldüğü tarih saati | "2022-08-04T12:44:02Z" |
| machineId | Dize | Makine GUID'i | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| osKind | Dize | İşletim sistemi türü | "windows", "mac", "linux" |
| osPlatform | Dize | İşletim sistemi ana sürüm adı | Windows 10, macOs |
| osVersion | Dize | İşletim sistemi sürümü | 10.0.18363.1440, 12.4.0.0 |
| quickScanError | Dize | Hızlı taramadan hata kodları | "0x80508023" |
| quickScanResult | Dize | Bu cihazın hızlı tarama sonucu | "Tamamlandı" <br>"İptal edildi" <br>"Başarısız" |
| quickScanTime | Datetimeoffset | Hızlı taramanın tamamlandığı tarih saat | "2022-08-04T12:44:02Z" |
| rbacGroupId | Uzun | Bu makinenin ait olduğu cihaz grubu kimliği | 712 |
| rbacGroupName | Dize | Bu makinenin ait olduğu cihaz grubunun adı | "SampleGroup" |

### <a name="13-export-device-antivirus-health-details-api-properties-via-files"></a>1.3 Cihaz virüsten koruma sistem durumu ayrıntıları API özelliklerini dışarı aktarma (dosyalar aracılığıyla)

> [!IMPORTANT]
> Bu bölümdeki bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

> [!NOTE]
>
> - Dosyalar çok satırlı Json biçiminde gzip sıkıştırılmış &.
> - İndirme URL'leri yalnızca 3 saat geçerlidir; aksi takdirde parametresini kullanabilirsiniz.
> - Verilerinizin en yüksek indirme hızı için, verilerinizin bulunduğu Azure bölgesinden indirme yaptığınızdan emin olabilirsiniz.
> - Her kayıt yaklaşık 1 KB veridir. Sizin için doğru pageSize parametresini seçerken bunu dikkate almanız gerekir.
> - Yanıtta bazı ek sütunlar döndürülebilir. Bu sütunlar geçicidir ve kaldırılabilir, lütfen yalnızca belgelenmiş sütunları kullanın.

| Özellik (Kimlik) | Veri türü | Açıklama | Döndürülen değer örneği |
|:----|:----|:----|:----|
| Dosyaları dışarı aktarma | array[string] | Kuruluşun geçerli anlık görüntüsünü içeren dosyalar için indirme URL'lerinin listesi. | ["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"] |
| GeneratedTime | Dize | Dışarı aktarmanın oluşturulduğu zaman. | 2022-05-20T08:00:00Z |

> [!NOTE]
> Dosyaların her birinde Virüsten Koruma bilgileriyle ilgili verileri içeren "DeviceGatheredInfo" özelliği bulunabilir. Özniteliklerinin her biri size cihazın durumu ve durumu hakkında bilgi sağlayabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Cihaz virüsten koruma sistem durumu raporunu dışarı aktarma](device-health-export-antivirus-health-report-api.md)

[Cihaz durumu ve uyumluluk raporlaması](device-health-reports.md)
