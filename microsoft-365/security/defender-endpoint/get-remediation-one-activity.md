---
title: Kimlikle bir düzeltme etkinliği al
description: Belirtilen düzeltme etkinliğine ilişkin bilgileri döndürür.
keywords: api'ler, düzeltme, düzeltme api'si, alma, düzeltme görevleri, kimlikle düzeltme,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: fa31c0cd5180b286f574e8697678e39af600bb97
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628808"
---
# <a name="get-one-remediation-activity-by-id"></a>Kimlikle bir düzeltme etkinliği al

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink).

> Microsoft Defender Güvenlik Açığı Yönetimi mı yaşamak istiyorsunuz? [Microsoft Defender Güvenlik Açığı Yönetimi genel önizleme denemesine](../defender-vulnerability-management/get-defender-vulnerability-management.md) nasıl kaydolabileceğiniz hakkında daha fazla bilgi edinin.

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Belirtilen düzeltme etkinliğine ilişkin bilgileri döndürür. [Tüm düzeltme etkinliğini al](get-remediation-all-activities.md)" ile aynı sütunları sunar, ancak _yalnızca belirtilen düzeltme etkinliği için_ sonuçları döndürür.

[Düzeltme etkinlikleri hakkında daha fazla bilgi edinin](tvm-remediation.md).

## <a name="list-a-specified-remediation-activity-for-id"></a>(Id) için belirtilen düzeltme etkinliğini listeleme

**URL:** GET: /api/remediationTasks/\{id\}

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|RemediationTasks.Read.All|\'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun\'
Temsilci (iş veya okul hesabı)|RemediationTask.Read.Read|\'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun\'

## <a name="properties"></a>Özellikler

Özellik (Kimlik)|Veri türü|Açıklama|Döndürülen değer örneği
:---|:---|:---|:---
Kategori|Dize|Düzeltme etkinliğinin kategorisi (Yazılım/Güvenlik yapılandırması)|Yazılım
completerEmail|Dize|Düzeltme etkinliği bir kişi tarafından el ile tamamlandıysa, bu sütun kendi e-postasını içerir|Null
completerId|Dize|Düzeltme etkinliği birisi tarafından el ile tamamlandıysa, bu sütun nesne kimliğini içerir|Null
completionMethod|Dize|Bir düzeltme etkinliği "otomatik olarak" (tüm cihazlara düzeltme eki uygulandıysa) veya "tamamlandı olarak işaretle" seçeneğini seçen bir kişi tarafından "el ile" tamamlanabilir|Otomatik
createdOn|Datetime|Bu düzeltme etkinliğinin oluşturulduğu saat|2021-01-12T18:54:11.5499478Z
Açıklama|Dize|Bu düzeltme etkinliğinin açıklaması|Cihazlarınızı etkileyen bilinen güvenlik açıklarını azaltmak için Microsoft Silverlight'ı daha sonraki bir sürüme güncelleştirin.
dueOn|Datetime|Bu düzeltme etkinliği için oluşturanın ayarlandığı son tarih|2021-01-13T00:00:00Z
fixedDevices||Düzeltilmiş cihaz sayısı|2
Kimlik|Dize|Bu düzeltme etkinliğinin kimliği|097d9735-5479-4899-b1b7-77398899df92
nameId|Dize|İlgili ürün adı|Microsoft Silverlight
Öncelik|Dize|Bu düzeltme etkinliği için oluşturucu kümesinin önceliği (Yüksek\Orta\Düşük)|Yüksek
Productıd|Dize|İlgili ürün kimliği|microsoft-_-silverlight
productivityImpactRemediationType|Dize|Yalnızca kullanıcıları etkilemeyen cihazlar için birkaç yapılandırma değişikliği istenebilir. Bu değer, "kullanıma sunulan tüm cihazlar" veya "yalnızca kullanıcı etkisi olmayan cihazlar" arasındaki seçimi gösterir.|AllExposedAssets
rbacGroupNames|Dize|İlgili cihaz grubu adları|[ "Windows Sunucuları", "Windows 11", "Windows 10" ]
önerilenProgram|Dize|Yükseltme için önerilen program|Null
önerilenVendor|Dize|Yükseltmesi önerilen satıcı|Null
recommendedVersion|Dize|Güncelleştirme/yükseltme için önerilen sürüm|Null
relatedComponent|Dize|Bu düzeltme etkinliğinin ilgili bileşeni (güvenlik önerisi için ilgili bileşene benzer)|Microsoft Silverlight
requesterEmail|Dize|Oluşturucu e-posta adresi|globaladmin@UserName.contoso.com
requesterId|Dize|Oluşturucu nesne kimliği|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|Dize|Oluşturucunun bu düzeltme etkinliği için eklediği notlar (serbest metin)|Null
Scid|Dize|İlgili güvenlik önerisinin SCID'sini|Null
Durum|Dize|Düzeltme etkinliği durumu (Etkin/Tamamlandı)|Etkin
statusLastModifiedOn|Datetime|Durum alanının güncelleştirilildiği tarih|2021-01-12T18:54:11.5499487Z
targetDevices|Uzun|Bu düzeltmenin uygulanabilecek kullanıma sunulan cihaz sayısı|43
Başlık|Dize|Bu düzeltme etkinliğinin başlığı|Microsoft Silverlight
Tür|Dize|Düzeltme türü|Güncelleştirme
Vendorıd|Dize|İlgili satıcı adı|Microsoft

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

```http
GET https://api.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.windows.com/api/$metadata#RemediationTasks/$entity",
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c",
    "title": "Update Microsoft Silverlight",
    "createdOn": "2021-02-10T13:20:36.4718166Z",
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4",
    "requesterEmail": "user1@contoso.com",
    "status": "Active",
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
    "relatedComponent": "Microsoft Silverlight",
    "targetDevices": 18511,
    "rbacGroupNames": [
        "UnassignedGroup",
        "hhh"
    ],
    "fixedDevices": 2866,
    "requesterNotes": "test",
    "dueOn": "2021-02-11T00:00:00Z",
    "category": "Software",
    "productivityImpactRemediationType": null,
    "priority": "Medium",
    "completionMethod": null,
    "completerId": null,
    "completerEmail": null,
    "scid": null,
    "type": "Update",
    "productId": "microsoft-_-silverlight",
    "vendorId": "microsoft",
    "nameId": "silverlight",
    "recommendedVersion": null,
    "recommendedVendor": null,
    "recommendedProgram": null
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Düzeltme yöntemleri ve özellikleri](get-remediation-methods-properties.md)
- [Tüm düzeltme etkinliklerini listele](get-remediation-all-activities.md)
- [Bir düzeltme etkinliğine maruz kalmış cihazları listele](get-remediation-exposed-devices-activities.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi](next-gen-threat-and-vuln-mgt.md)
- [Kuruluşunuzdaki güvenlik açıkları](tvm-weaknesses.md)
