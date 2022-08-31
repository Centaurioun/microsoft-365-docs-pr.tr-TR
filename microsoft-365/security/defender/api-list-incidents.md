---
title: Microsoft 365 Defender'de olay API'sini listeleme
description: Microsoft 365 Defender'de olaylar API'sini listelemeyi öğrenin
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: d86c26af54c4cd69e65cd5af952556a2553b728e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483068"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Microsoft 365 Defender'de olay API'sini listeleme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="api-description"></a>API açıklaması

Olayları listeleme API'si, bilinçli bir siber güvenlik yanıtı oluşturmak için olayları sıralamanıza olanak tanır. Ortamınızı saklama ilkenizde belirttiğiniz zaman aralığında ağınızda bayrak eklenmiş bir olay koleksiyonunu kullanıma sunar. En son olaylar listenin en üstünde görüntülenir. Her olay bir dizi ilgili uyarı ve bunların ilgili varlıklarını içerir.

API aşağıdaki **OData** işleçlerini destekler:

- `$filter``lastUpdateTime`, `createdTime`, `status`ve `assignedTo` özelliklerinde
- `$top`, en fazla **100** değerle
- `$skip`

## <a name="limitations"></a>Sınırlamalar

1. Sayfa boyutu üst sınırı **100 olaydır**.
2. İstek sayısı üst sınırı **dakikada 50 çağrı** ve **saatte 1500 çağrıdır**.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Access Microsoft 365 Defender API'leri](api-access.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Incident.Read.All|Tüm olayları okuma
Uygulama|Incident.ReadWrite.All|Tüm olayları okuma ve yazma
Temsilci (iş veya okul hesabı)|Incident.Read|Olayları okuma
Temsilci (iş veya okul hesabı)|Incident.ReadWrite|Olayları okuma ve yazma

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının portaldaki olaylar için görüntüleme iznine sahip olması gerekir.
> - Yanıt yalnızca kullanıcının maruz kaldığı olayları içerir.

## <a name="http-request"></a>HTTP isteği

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**

## <a name="request-body"></a>İstek gövdesi

Hiçbiri.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem döndürür ve yanıt gövdesindeki [olayların](api-incident.md) bir listesini döndürür`200 OK`.

## <a name="schema-mapping"></a>Şema eşleme

### <a name="incident-metadata"></a>Olay meta verileri

Alan adı|Açıklama|Örnek değer
---|---|---
incidentId|Olayı temsil eden benzersiz tanımlayıcı|924565
redirectIncidentId|Yalnızca olay işleme mantığının bir parçası olarak bir olayın başka bir olayla birlikte gruplandırılması durumunda doldurulur.|924569
incidentName|Her olay için kullanılabilen dize değeri.|Fidye yazılımı etkinliği
createdTime|Olayın ilk oluşturulduğu zaman.|2020-09-06T14:46:57.0733333Z
lastUpdateTime|Olayın arka uçta en son güncelleştirildiği saat. <p> Bu alan, olayların alınacağı zaman aralığı için istek parametresini ayarlarken kullanılabilir.|2020-09-06T14:46:57.29Z
Atanan|Olayın sahibi veya sahip atanmamışsa *null* .|secop2@contoso.com
Sınıflandırma|Olayın belirtimi. Özellik değerleri şunlardır: *Unknown*, *FalsePositive*, *TruePositive*|Unknown
Belirlenmesi|Olayın belirlenmesini belirtir. Özellik değerleri şunlardır: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *İstenmeyenSoftware*, *Diğer*|Kullanılamaz
detectionSource|Algılama kaynağını belirtir.|Bulut Uygulamaları için Defender
Durum|Olayları kategorilere ayırın ( *Etkin* veya *Çözüldü* olarak). Olaylara yanıtınızı düzenlemenize ve yönetmenize yardımcı olabilir.|Etkin
Önem|Varlıklar üzerindeki olası etkiyi gösterir. Önem derecesi ne kadar yüksek ise etki o kadar büyük olur. Genellikle daha yüksek önem derecesi öğeleri en acil dikkat gerektirir. <p> Aşağıdaki değerlerden biri: *Bilgilendirici*, *Düşük*, *Orta ve *Yüksek*.|Orta
Etiketler|Bir olayla ilişkili özel etiketler dizisi, örneğin ortak bir özelliğe sahip bir olay grubuna bayrak ekleme.|\[\]
Yorum|Olayı yönetirken secops tarafından oluşturulan açıklama dizisi, örneğin sınıflandırma seçimi hakkında ek bilgiler.|\[\]
Uyarı|Olayla ilgili tüm uyarıların yanı sıra önem derecesi, uyarıya katılan varlıklar ve uyarıların kaynağı gibi diğer bilgileri içeren dizi.|\[\] (aşağıdaki uyarı alanlarıyla ilgili ayrıntılara bakın)

### <a name="alerts-metadata"></a>Uyarı meta verileri

Alan adı|Açıklama|Örnek değer
---|---|---
alertId|Uyarıyı temsil eden benzersiz tanımlayıcı|caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId|Bu uyarının ilişkili olduğu olayı temsil eden benzersiz tanımlayıcı|924565
serviceSource|Uç Nokta için Microsoft Defender, Microsoft Defender for Cloud Apps, Kimlik için Microsoft Defender veya Office 365 için Microsoft Defender.|MicrosoftCloudAppSecurity
creationTime|Uyarının ilk oluşturulduğu zaman.|2020-09-06T14:46:55.7182276Z
Lastupdatedtime|Uyarının arka uçta en son güncelleştirildiği saat.|2020-09-06T14:46:57.2433333Z
resolvedTime|Uyarının çözümlenme zamanı.|2020-09-10T05:22:59Z
firstActivity|Uyarının arka uçta etkinliğin güncelleştirildiğini ilk bildirdiği zaman.|2020-09-04T05:22:59Z
Başlık|Her uyarı için kullanılabilen kısa tanımlayıcı dize değeri.|Fidye yazılımı etkinliği
Açıklama|Her uyarıyı açıklayan dize değeri.|Test Kullanıcısı2 (testUser2@contoso.com) kullanıcısı, yaygın olmayan *herunterladen* uzantısıyla biten birden çok uzantıya sahip 99 dosyayı işledi. Bu, olağan dışı sayıda dosya işlemedir ve olası bir fidye yazılımı saldırısının göstergesidir.
Kategori|Saldırının sonlandırma zinciri boyunca ne kadar ilerlediğini gösteren görsel ve sayısal görünüm. [MITRE ATT&CK™ çerçevesine](https://attack.mitre.org/) hizalanır.|Etki
Durum|Uyarıları kategorilere ayırın ( *Yeni*, *Etkin* veya *Çözüldü* olarak). Uyarılara yanıtınızı düzenlemenize ve yönetmenize yardımcı olabilir.|Yeni
Önem|Varlıklar üzerindeki olası etkiyi gösterir. Önem derecesi ne kadar yüksek ise etki o kadar büyük olur. Genellikle daha yüksek önem derecesi öğeleri en acil dikkat gerektirir.<br>Aşağıdaki değerlerden biri: *Bilgilendirici*, *Düşük*, *Orta* ve *Yüksek*.|Orta
investigationId|Bu uyarı tarafından tetiklenen otomatik araştırma kimliği.|1234
investigationState|Araştırmanın geçerli durumuyla ilgili bilgiler. Aşağıdaki değerlerden biri: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.|DesteklenmeyenAlertType
Sınıflandırma|Olayın belirtimi. Özellik değerleri şunlardır: *Unknown*, *FalsePositive*, *TruePositive* veya *null*|Unknown
Belirlenmesi|Olayın belirlenmesini belirtir. Özellik değerleri şunlardır: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *İstenmeyenSoftware*, *Diğer* veya  *null*|Apt
Atanan|Olayın sahibi veya sahip atanmamışsa *null* .|secop2@contoso.com
actorName|Varsa, bu uyarıyla ilişkili etkinlik grubu.|BOR
threatFamilyName|Bu uyarıyla ilişkili tehdit ailesi.|Null
mitreTechniques|[MITRE ATT&CK](https://attack.mitre.org/)™ çerçevesiyle uyumlu saldırı teknikleri.|\[\]
Aygıtları|Olayla ilgili uyarıların gönderildiği tüm cihazlar.|\[\] (aşağıdaki varlık alanlarıyla ilgili ayrıntılara bakın)

### <a name="device-format"></a>Cihaz biçimi

Alan adı|Açıklama|Örnek değer
---|---|---
Deviceıd|Uç Nokta için Microsoft Defender'de belirtilen cihaz kimliği.|24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId|[Azure Active Directory'de](/azure/active-directory/fundamentals/active-directory-whatis) belirlenen cihaz kimliği. Yalnızca etki alanına katılmış cihazlar için kullanılabilir.|Null
deviceDnsName|Cihazın tam etki alanı adı.|user5cx.middleeast.corp.contoso.com
osPlatform|Cihazın çalıştırılan işletim sistemi platformu.|WindowsServer2016
osBuild|Cihazın çalıştırılan işletim sistemi için derleme sürümü.|14393
rbacGroupName|Cihazla ilişkili [rol tabanlı erişim denetimi](/azure/role-based-access-control/overview) (RBAC) grubu.|WDATP-Ring0
firstSeen|Cihazın ilk görüldüğü zaman.|2020-02-06T14:16:01.9330135Z
healthStatus|Cihazın sistem durumu.|Etkin
riskScore|Cihazın risk puanı.|Yüksek
Varlık|Belirli bir uyarının parçası veya ilgili olduğu belirlenen tüm varlıklar.|\[\] (aşağıdaki varlık alanlarıyla ilgili ayrıntılara bakın)

### <a name="entity-format"></a>Varlık Biçimi

Alan adı|Açıklama|Örnek değer
---|---|---
Entitytype|Belirli bir uyarının parçası olduğu veya ilgili olduğu belirlenen varlıklar.<br>Özellik değerleri şunlardır: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*|Kullanıcı
sha1|entityType *Dosya* ise kullanılabilir.<br>Bir dosya veya işlemle ilişkili uyarılar için dosya karması.|5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256|entityType *Dosya* ise kullanılabilir.<br>Bir dosya veya işlemle ilişkili uyarılar için dosya karması.|28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
Dosyaadı|entityType *Dosya* ise kullanılabilir.<br>Bir dosya veya işlemle ilişkili uyarıların dosya adı|Detector.UnitTests.dll
Filepath|entityType *Dosya* ise kullanılabilir.<br>Bir dosya veya işlemle ilişkili uyarıların dosya yolu|C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
Processıd|entityType *İşlem* ise kullanılabilir.|24348
processCommandLine|entityType *İşlem* ise kullanılabilir.|"Dosyanız1911150169.exe İndirmeye\_ Hazır"
processCreationTime|entityType *İşlem* ise kullanılabilir.|2020-07-18T03:25:38.5269993Z
parentProcessId|entityType *İşlem* ise kullanılabilir.|16840
parentProcessCreationTime|entityType *İşlem* ise kullanılabilir.|2020-07-18T02:12:32.8616797Z
ıpaddress|entityType *Ip* ise kullanılabilir. <br>*Kötü amaçlı bir ağ hedefine iletişim* gibi ağ olaylarıyla ilişkili uyarıların IP adresi.|62.216.203.204
Url|entityType *Url* ise kullanılabilir. <br>*Kötü amaçlı bir ağ hedefine iletişim* gibi ağ olaylarıyla ilişkili uyarıların URL'si.|down.esales360.cn
Accountname|entityType *Kullanıcı* ise kullanılabilir.|testUser2
Etkialanıadı|entityType *Kullanıcı* ise kullanılabilir.|europe.corp.contoso
userSid|entityType *Kullanıcı* ise kullanılabilir.|S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId|entityType *Kullanıcı* ise kullanılabilir.|fc8f7484-f813-4db2-afab-bc1507913fb6
Userprincipalname|entityType *, User*/*MailBox*/*MailMessage* ise kullanılabilir.|testUser2@contoso.com
mailboxDisplayName|entityType *MailBox* ise kullanılabilir.|test Kullanıcısı2
mailboxAddress|entityType *, User*/*MailBox*/*MailMessage* ise kullanılabilir.|testUser2@contoso.com
clusterBy|entityType  *MailCluster* ise kullanılabilir.|Konu; P2SenderDomain; Contenttype
Gönderen|entityType *, User*/*MailBox*/*MailMessage* ise kullanılabilir.|user.abc@mail.contoso.co.in
Alıcı|entityType *MailMessage* ise kullanılabilir.|testUser2@contoso.com
Konu|entityType *MailMessage* ise kullanılabilir.|\[DıŞ\] Dikkat
deliveryAction|entityType *MailMessage* ise kullanılabilir.|Teslim
securityGroupId|entityType  *SecurityGroup* ise kullanılabilir.|301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName|entityType  *SecurityGroup* ise kullanılabilir.|Ağ Yapılandırma İşleçleri
Registryhive|entityType  *Kayıt Defteri* ise kullanılabilir.|HKEY\_YEREL\_MAKINESI|
registryKey|entityType  *Kayıt Defteri* ise kullanılabilir.|SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType|entityType  *Kayıt Defteri* ise kullanılabilir.|Dize
registryValue|entityType  *Kayıt Defteri* ise kullanılabilir.|31-00-00-00
Deviceıd|Varsa, varlıkla ilgili cihazın kimliği.|986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response-example"></a>Yanıt örneği

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Microsoft Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- [API sınırları ve lisanslama hakkında bilgi edinin](api-terms.md)
- [Hata kodlarını anlama](api-error-codes.md)
- [Olaylara genel bakış](incidents-overview.md)
- [Olay API'leri](api-incident.md)
- [Olay API'sini güncelleştirme](api-update-incidents.md)
