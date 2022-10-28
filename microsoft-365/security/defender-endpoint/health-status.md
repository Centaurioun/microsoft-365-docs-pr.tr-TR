---
title: Sistem durumu sorunlarını araştırın
description: mdatp health komutunu çalıştırırken döndürülen değerler hakkında bilgi edinin
keywords: mdatp health, command, health, status, command, onboarding status
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
ms.openlocfilehash: 0d8fe040f8fb8bc28343ee758d0fd58ae307ecd9
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768115"
---
# <a name="investigate-agent-health-issues"></a>Sistem durumu sorunlarını araştırın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Aşağıdaki tabloda, komutu çalıştırdığınızda `mdatp health` döndürülen değerler ve karşılık gelen açıklamaları hakkında bilgi sağlanır.

<br>

****

|Değer|Açıklama|
|---|---|
|automatic_definition_update_enabled|Otomatik virüsten koruma tanımı güncelleştirmeleri etkinse true, aksi takdirde false.|
|cloud_automatic_sample_submission_consent|Geçerli örnek gönderim düzeyi. Aşağıdaki değerlerden biri olabilir: <ul><li>**Hiçbiri**: Microsoft'a şüpheli örnek gönderilmez.</li><li>**Güvenli**: Yalnızca kişisel bilgiler (PII) içermeyen şüpheli örnekler otomatik olarak gönderilir. Bu ayar için varsayılan değer budur.</li><li>**Tümü**: Tüm şüpheli örnekler Microsoft'a gönderilir.</li></ul>|
|cloud_diagnostic_enabled|İsteğe bağlı tanılama veri toplama etkinse true, aksi takdirde false. Uç Nokta için Defender ile Microsoft Defender Virüsten Koruma ve Windows gibi diğer ürün ve hizmetlerle ilgili daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=827576).|
|cloud_enabled|Bulut tabanlı koruma etkinleştirildiyse true, aksi takdirde false.|
|conflicting_applications|Uç Nokta için Microsoft Defender ile çakışan uygulamaların listesi. Bu liste, uyumluluk sorunlarına neden olduğu bilinen diğer güvenlik ürünlerini ve diğer uygulamaları içerir ancak bunlarla sınırlı değildir.|
|definitions_status|Virüsten koruma tanımlarının durumu.|
|definitions_updated|Son virüsten koruma tanımı güncelleştirmesinin tarihi ve saati.|
|definitions_updated_minutes_ago|Son virüsten koruma tanımı güncelleştirmesinin üzerinden geçen dakika sayısı.|
|definitions_version|Virüsten koruma tanımı sürümü.|
|edr_client_version|Cihazda çalışan EDR istemcisinin sürümü.|
|edr_configuration_version|EDR yapılandırma sürümü.|
|edr_device_tags|Cihazla ilişkili etiketlerin listesi.|
|edr_group_ids|Cihazın ilişkili olduğu grup kimliği.|
|edr_machine_id|Microsoft 365 Defender'de kullanılan cihaz tanımlayıcısı.|
|engine_version|Virüsten koruma altyapısının sürümü.|
|Sağlıklı|Ürün iyi durumdaysa true, aksi takdirde false.|
|Lisanslı|Cihaz bir kiracıya ekliyse true, aksi takdirde false.|
|log_level|Ürün için geçerli günlük düzeyi.|
|machine_guid|Virüsten koruma bileşeni tarafından kullanılan benzersiz makine tanımlayıcısı.|
|network_protection_status|Ağ koruma bileşeninin durumu (yalnızca macOS). Aşağıdaki değerlerden biri olabilir: <ul><li>**başlatma** - Ağ koruması başlatılıyor</li><li>**failed_to_start** - Ağ koruması bir hata nedeniyle başlatılamıyor</li><li>**başlatıldı** - Ağ koruması şu anda cihazda çalışıyor</li><li>**yeniden başlatma** - Ağ koruması şu anda yeniden başlatılıyor</li><li>**durdurma** - Ağ koruması durduruluyor</li><li>**durduruldu** - Ağ koruması çalışmıyor</li></ul>|
|org_id|Cihazın eklendiği kuruluş. Cihaz henüz herhangi bir kuruluşa eklenmemişse, bu yazdırma kullanılamaz. Ekleme hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender ekleme](onboarding.md).|
|passive_mode_enabled|Virüsten koruma bileşeni pasif modda çalışacak şekilde ayarlandıysa true, aksi takdirde false.|
|product_expiration|Geçerli ürün sürümünün destek sonuna ulaştığı tarih ve saat.|
|real_time_protection_available|Gerçek zamanlı koruma bileşeni iyi durumdaysa true, aksi takdirde false.|
|real_time_protection_enabled|Gerçek zamanlı virüsten koruma etkinse true, aksi takdirde false.|
|real_time_protection_subsystem|Gerçek zamanlı koruma sağlamak için kullanılan alt sistem. Gerçek zamanlı koruma beklendiği gibi çalışmıyorsa, bu yazdırma kullanılamaz.|
|release_ring|Yayın halkası. Daha fazla bilgi için bkz [. Dağıtım halkaları](deployment-rings.md).|
|

## <a name="component-specific-health"></a>Bileşene özgü sistem durumu

ile `mdatp health --details <feature>`farklı Defender özellikleri için daha ayrıntılı sistem durumu bilgileri alabilirsiniz. Örneğin:

    ```bash
    mdatp health --details edr
    ```

    ```
    edr_early_preview_enabled                   : "disabled"
    edr_device_tags                             : []
    edr_group_ids                               : ""
    edr_configuration_version                   : "20.199999.main.2022.10.25.03-514032a834557bdd31ac415be6df278d9c2a4c25"
    edr_machine_id                              : "a47ba049f43319ac669b6291ce73275cd445c9cd"
    edr_sense_guid                              : "298a1a8c-04dd-4929-8efd-3bb14cb54b94"
    edr_preferred_geo                           : "unitedstates"
    ```

Desteklenen `feature`tüm sürümleri listelemek için son sürümlerde çalıştırabilirsiniz`mdatp health --help`.
