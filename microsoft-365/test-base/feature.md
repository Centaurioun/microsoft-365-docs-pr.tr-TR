---
title: Özellik güncelleştirme doğrulaması
description: Özellik güncelleştirme doğrulaması için uygulamanızı karşıya yüklemeyle ilgili ayrıntılar
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: bd681f6dceec9182d3fbe80e6bb3beeae510c65a
ms.sourcegitcommit: 893add1e40c3e26e5624663eaf272d12a72d0141
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68540015"
---
# <a name="windows-feature-update-validation"></a>Windows Özellik güncelleştirme doğrulaması

Uygulamalarınızın en son Windows özellikleriyle nasıl performans göstereceğiyle ilgili içgörülere mi ihtiyacınız var? 

Doğrulama testlerinizi Azure ortamımızda Windows Insider Programı derlemelerinde çalıştırmak istiyor musunuz? 

Microsoft 365 için Test Tabanı'nda **özellik güncelleştirme** doğrulaması, tüm bunları ve daha fazlasını başarmanıza yardımcı olabilir! 

Microsoft 365 hizmeti için Test Temeli'nde bu yeni özelliğe nasıl erişeceklerini öğrenmek için aşağıdaki adım adım ana hattı gözden geçirin. 

Microsoft 365 için Test Temeli'nde Özellik güncelleştirme doğrulamasını kullanmaya başlamak için self servis ekleme portalı aracılığıyla uygulamalarınızı (ve ilgili dosyaları) karşıya yükleyin. 

**Aşağıda, Test Matrisi'ni** doldururken atılması gereken adımlar vurgulanır: 

Özellik güncelleştirmelerini ayarlamak için hedef ürünü ve önizleme kanalını "Insider Kanalı" açılan listesinden belirtmeniz gerekir. 

![Özellik güncelleştirmesi doğrulama işletim sistemi türü.](Media/windowsfeatureupdatevalidation01-featureupdate.png)

Seçiminiz, uygulamanızı seçtiğiniz ürün kanalının en son özellik güncelleştirmelerine ve seçiminizin en son Windows Insider Preview Derlemelerinde gelecekteki tüm yeni güncelleştirmelere karşı otomatik test çalıştırmaları için kaydeder. 

Geçerli işletim sisteminizi "İçgörüler için işletim sistemi temeli" bölümünde de ayarlayabilirsiniz. Olduğu gibi işletim sistemi ortamınızın ve en son hedef işletim sisteminizin regresyon analizini yaparak size daha fazla test içgörüleri sağlarız. 

![Özellik güncelleştirme doğrulaması. Insider beta kanalını seçme.](Media/windowsfeatureupdatevalidation02-osbaseline.png) 

Windows Insider Preview derlemeleriyle ilgili diğer ayrıntıları denetlemek için [bkz. Flight Hub - Windows Insider Programı | Microsoft Docs](/../../../../MicrosoftDocs/windows-insider/tree/public/wip/flight-hub/index.md).


## <a name="next-steps"></a>Sonraki adımlar

Bellek regresyon analizini anlamaya başlamak için sonraki makaleye geçin.
> [!div class="nextstepaction"]
> [Sonraki adım](memory.md)

<!---
Add button for next page
-->
