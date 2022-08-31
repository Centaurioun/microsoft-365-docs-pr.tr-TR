---
title: olay API'lerini ve olay kaynak türünü Microsoft 365 Defender
description: Microsoft 365 Defender'da Olaylar kaynak türünün yöntemleri ve özellikleri hakkında bilgi edinin
keywords: olay, olaylar, api
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
ms.openlocfilehash: 8531a2f647f9f8adaeb952c08cae596142fc884f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67471378"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defender olayları API'si ve olaylar kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

[Olay](incidents-overview.md), bir saldırıyı açıklamaya yardımcı olan ilgili uyarıların bir koleksiyonudur. Kuruluşunuzdaki farklı varlıklardaki olaylar Microsoft 365 Defender tarafından otomatik olarak toplanır. Kuruluşunuzun olaylarına ve ilgili uyarılarına programlı olarak erişmek için olaylar API'sini kullanabilirsiniz.

## <a name="quotas-and-resource-allocation"></a>Kotalar ve kaynak ayırma

Dakikada en fazla 50 veya saatte 1500 çağrı isteyebilirsiniz. Her yöntemin kendi kotaları da vardır. Yönteme özgü kotalar hakkında daha fazla bilgi için kullanmak istediğiniz yöntemin ilgili makalesine bakın.

`429` HTTP yanıt kodu, gönderilen istek sayısına veya ayrılan çalışma süresine göre bir kotaya ulaştığınızı gösterir. Yanıt gövdesi, ulaştığınız kota sıfırlanana kadar olan süreyi içerir.

## <a name="permissions"></a>İzinler

Olay API'sinin yöntemlerinin her biri için farklı türde izinler gerekir. Gerekli izinler hakkında daha fazla bilgi için ilgili yöntemin makalesine bakın.

## <a name="methods"></a>Yöntemler

Yöntem | Dönüş Türü | Açıklama
-|-|-
[Olayları listeleyin](api-list-incidents.md) | [Olay](api-incident.md) listesi | Olayların listesini alın.
[Olayı güncelleştirme](api-update-incidents.md) | [Olay](api-incident.md) | Belirli bir olayı güncelleştirin.
[Olay alma](api-get-incident.md) | [Olay](api-incident.md) | Tek bir olay alın.

## <a name="request-body-response-and-examples"></a>İstek gövdesi, yanıt ve örnekler

İstek oluşturma veya yanıt ayrıştırma hakkında daha fazla ayrıntı ve pratik örnekler için ilgili yöntem makalelerine bakın.

## <a name="common-properties"></a>Ortak özellikler

Özellik | Tür | Açıklama
-|-|-
incidentId | Uzun | Olay benzersiz kimliği.
redirectIncidentId | null atanabilir uzun | Geçerli Olayın birleştirildiği Olay Kimliği.
incidentName | Dize | Olayın adı.
createdTime | Datetimeoffset | Olayın oluşturulduğu tarih ve saat (UTC olarak).
lastUpdateTime | Datetimeoffset | Olayın son güncelleştirildiği tarih ve saat (UTC olarak).
Atanan | Dize | Olayın Sahibi.
Önem | Enum | Olayın önem derecesi. Olası değerler şunlardır: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```ve ```High```.
Durum | Enum | Olayın geçerli durumunu belirtir. Olası değerler şunlardır: ```Active```, ```InProgress```, ```Resolved```ve ```Redirected```.
Sınıflandırma | Enum | Olayın belirtimi. Olası değerler şunlardır: ```Unknown```, ```FalsePositive```, ```TruePositive```.
Belirlenmesi | Enum | Olayın belirlenmesini belirtir. Olası değerler şunlardır: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, , ```UnwantedSoftware```. ```Other```
Etiketler | dize Listesi | Olay etiketlerinin listesi.
Yorum | Olay açıklamalarının listesi | Olay Açıklaması nesnesi şunları içerir: açıklama dizesi, createdBy dizesi ve createTime tarih saati.
Uyarı | Uyarı Listesi | İlgili uyarıların listesi. [Olayları listeleme API'leri belgelerindeki](api-list-incidents.md) örneklere bakın.

>[!NOTE]
>29 Ağustos 2022'de daha önce desteklenen uyarı belirleme değerleri ('Apt' ve 'SecurityPersonnel') kullanım dışı bırakılacak ve artık API aracılığıyla kullanılamayacak.

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Olaylara genel bakış](incidents-overview.md)
- [Olayları listeleme API'si](api-list-incidents.md)
- [Olay API'sini güncelleştirme](api-update-incidents.md)
