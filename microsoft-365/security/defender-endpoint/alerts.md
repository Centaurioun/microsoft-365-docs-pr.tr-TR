---
title: Uyarı alma API'si
description: Uç Nokta için Microsoft Defender'da Uyarı kaynak türünün yöntemleri ve özellikleri hakkında bilgi edinin.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 9b30c6180bbdffa2538bb78f2a4d0a75bdc8266b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701685"
---
# <a name="alert-resource-type"></a>Uyarı kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="methods"></a>Yöntemler

|Yöntem|Dönüş Türü|Açıklama|
|---|---|---|
|[Uyarı alma](get-alert-info-by-id.md)|[Uyarı](alerts.md)|Tek bir [uyarı](alerts.md) nesnesi alın.|
|[Uyarıları listele](get-alerts.md)|[Uyarı](alerts.md) koleksiyonu|[Uyarı](alerts.md) koleksiyonunu listeleme.|
|[Uyarıyı güncelleştirme](update-alert.md)|[Uyarı](alerts.md)|Belirli [bir uyarıyı](alerts.md) güncelleştirin.|
|[Grup güncelleştirme uyarıları](batch-update-alerts.md)||Bir grup [uyarıyı](alerts.md) güncelleştirin.|
|[Uyarı oluştur](create-alert-by-reference.md)|[Uyarı](alerts.md)|[Gelişmiş Tehdit Avcılığı'ndan](run-advanced-query-api.md) alınan olay verilerini temel alan bir uyarı oluşturun.|
|[İlgili etki alanlarını listeleme](get-alert-related-domain-info.md)|Etki alanı koleksiyonu|Uyarıyla ilişkili URL'leri listeleyin.|
|[İlgili dosyaları listeleme](get-alert-related-files-info.md)|[Dosya](files.md) koleksiyonu|[Uyarıyla](alerts.md) ilişkili [dosya](files.md) varlıklarını listeleyin.|
|[İlgili IP'leri listeleme](get-alert-related-ip-info.md)|IP koleksiyonu|Uyarıyla ilişkili IP'leri listeleyin.|
|[İlgili makineleri alma](get-alert-related-machine-info.md)|[Makine](machine.md)|[Uyarıyla](alerts.md) ilişkili [makine](machine.md).|
|[İlgili kullanıcıları alma](get-alert-related-user-info.md)|[Kullanıcı](user.md)|[Uyarıyla](alerts.md) ilişkili [kullanıcı](user.md).|

## <a name="properties"></a>Özellikler

|Özellik|Tür|Açıklama|
|---|---|---|
|Kimliği|Dize|Uyarı Kimliği.|
|Başlık|Dize|Uyarı başlığı.|
|Açıklama|Dize|Uyarı açıklaması.|
|alertCreationTime|Null Atanabilir DateTimeOffset|Uyarının oluşturulduğu tarih ve saat (UTC olarak).|
|lastEventTime|Null Atanabilir DateTimeOffset|Aynı cihazda uyarıyı tetikleyen olayın son oluşumu.|
|firstEventTime|Null Atanabilir DateTimeOffset|Bu cihazda uyarıyı tetikleyen olayın ilk oluşumu.|
|lastUpdateTime|Null Atanabilir DateTimeOffset|Uyarının son güncelleştirildiği tarih ve saat (UTC olarak).|
|resolvedTime|Null Atanabilir DateTimeOffset|Uyarının durumunun 'Çözüldü' olarak değiştirildiği tarih ve saat.|
|incidentId|Boş Değer Atanabilir Uzun|Uyarının [Olay](view-incidents-queue.md) Kimliği.|
|investigationId|Boş Değer Atanabilir Uzun|Uyarı ile ilgili [Araştırma](automated-investigations.md) Kimliği.|
|investigationState|Null Atanabilir Sabit Listesi|[Araştırmanın](automated-investigations.md) geçerli durumu. Olası değerler şunlardır: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.|
|Atanan|Dize|Uyarının sahibi.|
|rbacGroupName|Dize|RBAC cihaz grubu adı.|
|mitreTechniques|Dize|Mitre Enterprise teknik kimliği.|
|relatedUser|Dize|Belirli bir uyarıyla ilgili kullanıcının ayrıntıları.|
|Önem|Enum|Uyarının önem derecesi. Olası değerler şunlardır: 'Belirtilmemiş', 'Bilgilendirici', 'Düşük', 'Orta' ve 'Yüksek'.|
|Durum|Enum|Uyarının geçerli durumunu belirtir. Olası değerler şunlardır: 'Unknown', 'New', 'InProgress' ve 'Resolved'.|
|Sınıflandırma|Null Atanabilir Sabit Listesi|Uyarının belirtimi. Olası değerler şunlardır: 'Unknown', 'FalsePositive', 'TruePositive'.|
|Belirlenmesi|Null Atanabilir Sabit Listesi|Uyarının belirlenmesini belirtir. Olası değerler şunlardır: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'İstenmeyenSoftware', 'Diğer'.|
|Kategori|Dize|Uyarı kategorisi.|
|detectionSource|Dize|Algılama kaynağı.|
|threatFamilyName|Dize|Tehdit ailesi.|
|threatName|Dize|Tehdit adı.|
|machineId|Dize|Uyarıyla ilişkilendirilmiş bir [makine](machine.md) varlığının kimliği.|
|computerDnsName|Dize|[makine](machine.md) tam adı.|
|aadTenantId|Dize|Azure Active Directory Kimliği.|
|detectorId|Dize|Uyarıyı tetikleyen algılayıcının kimliği.|
|Yorum|Uyarı açıklamalarının listesi|Uyarı Açıklaması nesnesi şunları içerir: açıklama dizesi, createdBy dizesi ve createTime tarih saati.|
|Kanıt|Uyarı kanıtı listesi|Uyarıyla ilgili kanıt. Aşağıdaki örniğe bakın.|

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacak.

### <a name="response-example-for-getting-single-alert"></a>Tek bir uyarı almak için yanıt örneği:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "DOMAIN"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "name",
            "domainName": "DOMAIN",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
