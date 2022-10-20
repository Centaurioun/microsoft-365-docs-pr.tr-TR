---
title: Bir düzeltme etkinliğine maruz kalmış cihazları listele
description: Belirtilen düzeltme görevi için kullanıma sunulan cihazlar hakkındaki bilgileri döndürür.
keywords: api'ler, düzeltme, düzeltme api'leri, alma, düzeltme görevleri, kullanıma sunulan cihazları düzeltme
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
ms.openlocfilehash: 148946ee5b786b9557b1c1ca820266229386b318
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628818"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>Bir düzeltme etkinliğine maruz kalmış cihazları listele

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API Açıklaması

Belirtilen düzeltme görevi için kullanıma sunulan cihazlar hakkındaki bilgileri döndürür.

[Düzeltme etkinlikleri hakkında daha fazla bilgi edinin](tvm-remediation.md).

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>Bir düzeltme görevi (id) ile ilişkili kullanıma sunulan cihazları listeleme

**URL:** GET: /api/remediationTasks/\{id\}/machineReferences

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek [için ayrıntılar için bkz. Uç Nokta için Microsoft Defender API'lerini kullanma.](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|RemediationTasks.Read.All|\'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun\'
Temsilci (iş veya okul hesabı)|RemediationTask.Read.Read|\'Tehdit ve Güvenlik Açığı Yönetimi güvenlik açığı bilgilerini okuyun\'

## <a name="properties-details"></a>Özellikler ayrıntıları

Özellik (id)|Veri türü|Açıklama|Örnek
:---|:---|:---|:---
Kimliği|Dize|Cihaz Kimliği|w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName|Dize|Cihaz adı|PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform|Dize|Cihaz işletim sistemi|WindowsServer2012R2
rbacGroupName|Dize|Bu cihazın ilişkili olduğu cihaz grubunun adı|Sunucular

## <a name="example"></a>Örnek

### <a name="request-example"></a>İstek örneği

```http
GET https://api.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>Yanıt örneği

```json
{
    "@odata.context": "https://api.securitycenter.windows.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        }
]
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Düzeltme yöntemleri ve özellikleri](get-remediation-methods-properties.md)
- [Kimliğine göre bir düzeltme etkinliği alma](get-remediation-one-activity.md)
- [Tüm düzeltme etkinliklerini listele](get-remediation-all-activities.md)
- [Microsoft Defender Güvenlik Açığı Yönetimi](next-gen-threat-and-vuln-mgt.md)
- [Kuruluşunuzdaki güvenlik açıkları](tvm-weaknesses.md)
