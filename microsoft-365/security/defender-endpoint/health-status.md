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
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 8ae4ff58ae71ef51d09716761d2660d239f51083
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523830"
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
|cloud_diagnostic_enabled|İsteğe bağlı tanılama veri toplama etkinse true, aksi takdirde false. Uç Nokta için Defender ve Microsoft Defender Virüsten Koruma ve Windows gibi diğer ürün ve hizmetlerle ilgili daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?linkid=827576).|
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
