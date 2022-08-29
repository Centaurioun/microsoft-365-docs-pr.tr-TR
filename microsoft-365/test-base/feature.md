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
ms.openlocfilehash: 02693d1dc9637b97d6d567a6bc362eaef24adc5d
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315514"
---
# <a name="windows-feature-update-validation"></a>Windows Özellik güncelleştirme doğrulaması

Yeni Windows özelliklerini doğrulamak için bir ortamı korumadan uygulamalarınızın bir sonraki Windows 10 veya Windows 11 sürümüyle nasıl performans göstereceği hakkında içgörülere mi ihtiyacınız var? 

Doğrulama testlerinizi Azure ortamımızda Windows Insider Programı derlemelerinde çalıştırmak istiyor musunuz?

M365 için Test Tabanı'nda **özellik güncelleştirme** doğrulaması, tüm bunları ve daha fazlasını başarmanıza yardımcı olabilir!

M365 hizmeti için Test Temeli'nde bu yeni özelliğe nasıl erişeceklerini öğrenmek için aşağıdaki adım adım ana hattı gözden geçirin.

M365 için Test Temeli'ni kullanmaya başlamak ```Feature update validation``` için self servis ekleme portalı aracılığıyla uygulamalarınızı (ve ilgili dosyaları) karşıya yükleyin. 

**Aşağıda, Test ayrıntılarını** doldururken izlenmeniz gereken adımlar vurgulanır:

1. İşletim sistemi güncelleştirme türünüz olarak **Özellik Güncelleştirmesi'ni** seçin:

![Özellik güncelleştirmesi doğrulama işletim sistemi türü.](Media/Feature-update-validation-01.png)

2. Uygulamanızın doğrulanmasını istediğiniz Windows Insider Kanalı'nı seçin.  

![Özellik güncelleştirme doğrulaması. Insider beta kanalını seçme.](Media/Feature-update-validation-02.png)

3. Testinizin temeli olarak pazar içi bir Windows 10 veya Windows 11 sürümü seçin (ve elde edilen içgörüler!) ve paketinizi başarıyla eklemek için gereken diğer ayrıntıları sağlayın.

![Windows 10 ve Windows 11 sürümleriyle özellik güncelleştirme doğrulaması.](Media/Feature-update-validation-03.png)

4. Uygulamanızın önceden yayımlanan Windows 10 özellik güncelleştirmelerine karşı doğrulamasının sonuçlarını görüntülemek için adresini ziyaret edin```Feature Updates Test Results```.

![Özellik güncelleştirme doğrulaması, sonuçları hızlı bir şekilde gözden geçirmenizi sağlar.](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>Sonraki adımlar

Bellek regresyon analizini anlamaya başlamak için sonraki makaleye geçin.
> [!div class="nextstepaction"]
> [Sonraki adım](memory.md)

<!---
Add button for next page
-->
