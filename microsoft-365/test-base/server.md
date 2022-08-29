---
title: Windows Server uygulama testi
description: Windows Server uygulama testi ile doğrulama
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
ms.openlocfilehash: 5d111b680105628ab1351a2cc45eeba01c41aa68
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316018"
---
# <a name="windows-server-application-testing"></a>Windows Server Uygulama Testi

Microsoft 365 için Test Temeli ile artık Sunucu Çekirdeği de dahil olmak üzere uygulamalarınızı Windows Server 2016 ve 2019'da doğrulayabilirsiniz!

Microsoft 365 için Test Base'de Windows Server 2016 ve 2019 işletim sistemlerinin yayın öncesi güncelleştirmelerinde karşıya yüklediğiniz uygulamaları doğrulamaya başlamak için aşağıdaki adımlara uyun:

1. Self servis ekleme portalımızda oturum açın. Sol taraftaki gezinti menüsünden altında `Package catalogue` öğesini seçin `Upload new package` ve Test ayrıntılarını doldurun.

2. İşletim sistemi güncelleştirme türü olarak seçin `Security updates` :

   ![Güvenlik güncelleştirmelerini seçin.](Media/selecting-security-updates.png)

3. Test etmek için işletim sistemi sürümleri'nin altında geçerli işletim sistemi sürümlerini seçin. Windows Server işletim sistemi sürümlerini veya sunucu ve istemci işletim sistemi sürümlerinin bir bileşimini seçebilirsiniz.

   ![İşletim sistemi sürümü'ne tıklayın.](Media/selecting-OS-versions.png)

4. Diğer gerekli bilgileri sağlayın, sağlanan ayrıntıları gözden geçirin ve uygulama paketinizi karşıya yükleyin. Karşıya yükledikten sonra Paketleri yönet menü sekmesinde paket durumunu görüntüleyebilirsiniz.

5. Windows Server 2016 ve 2019'da yayın öncesi güvenlik güncelleştirmelerine karşı uygulamanızın doğrulanmasıyla ilgili test sonuçlarını ve içgörülerini görüntülemek için Test özeti sayfasına veya Güvenlik güncelleştirmesi sonuçları sayfasına gidin.

   ![Test sonuçlarını görüntüleyin.](Media/access-test-results.png)

**İşlevsel testi** kullanmaya başlamak için sonraki makaleye geçin
> [!div class="nextstepaction"]
> [Sonraki adım](functional.md)
