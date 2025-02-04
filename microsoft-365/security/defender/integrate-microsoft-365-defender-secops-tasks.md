---
title: 6. Adım. SOC bakım görevlerini tanımlama
description: Microsoft 365 Defender güvenlik işlemlerinizle tümleştirirken SOC bakım görevlerini belirleyin.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı, secops, güvenlik işlemleri, soc
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-m365dsecops
- tier2
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b3d3df2fe96b0af79cafcaf5a7979d0c491bc816
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68092580"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>6. Adım. SOC bakım görevlerini tanımlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender için SOC'nizin bakımını yapmak için düzenli veya gerektiği gibi görevler aşağıdadır.

|Etkinlik|Açıklama|Cadence|Ekip atandı|
|---|---|---|---|
|SOC Teams ile hizmet yönetimi işbirliği|Varlık izleme (CMDB), uygulama lisanslama (yeni SaaS lisansları), cihaz satın almaları (yükseltmeler veya cihaz dağıtımlarını yenileme) ve Microsoft 365 Defender ürünlerinin dağıtımını etkileyebilecek diğer Microsoft 365 kiracı genelindeki değişikliklerin (Intune, Microsoft 365 ve diğerleri) yönetimi.|Haftalık ve gerektiğinde|Mühendislik & SecOps|
|Kimlik avı önleme ve veri kaybı önleme kampanyalarını güncelleştirme|Genişletilmiş kuruluşla (İk, hukuk, eğitim ve diğerleri) öğrenilen SOC kullanım örneğini ve derslerini birleştirir.|Aylık ve gerektiğinde|SOC Gözetim|
|Otomasyon betiklerini ve hizmetlerini uygun yerlerde dağıtma|Microsoft 365 Defender işlemlerini geliştirmek için onaylı Microsoft sitelerinden otomasyon betiklerini ve yapılandırma dosyalarını indirin ve test edin.|Haftalık ve gerektiğinde|Mühendislik ve SecOps|
|Portal veya lisans yönetimi|Microsoft güncelleştirmelerine ve yeni özelliklere bağlı olarak duyuruları ve Microsoft 365 Defender portalı veya lisanslama gereksinimlerini görmek için Microsoft Mesajlaşma Merkezi'ni denetleyin.|Hafta -lık|SOC Gözetim|
|SOC yükseltme biletlerini güncelleştirme|Tüm SOC ekipleri kendilerine atanan yükseltme biletlerini (Sentinel, ServiceNow biletleri gibi) güncelleştirir.|Günlük|Tüm SOC ekipleri|
|Microsoft Defender Güvenlik Açığı Yönetimi (MDVM) düzeltme etkinliğini izleme|MDVM Güvenli Puan düzeltme etkinliği oluşturun ve bir intranet portalı aracılığıyla varlık sahiplerine bildirin.|Günlük|Izleme|
|Güvenli Puan raporu oluşturma|İzleme ekibi Güvenli Puan geliştirmelerini izler ve raporlar.|Haftalık SOC|Izleme|
|IR tabletop alıştırması çalıştırma|Masa üstü alıştırmasında SOC ekibi playbook'larını test edin.|Gerektiği gibi|Tüm SOC ekipleri|

Bu görevleri geçerli SOC süreçlerinizle tümleştirin.

## <a name="next-steps"></a>Sonraki adımlar

Kendi Microsoft 365 Defender uygulamanızın nasıl yapılandırılıp tümleştirilmesi gerektiğini belirlemek için bu içerikte ve [Microsoft 365 Defender kitaplığında](/microsoft-365/security/defender) başvuruda bulunılan kılavuzları gözden geçirmelisiniz.
