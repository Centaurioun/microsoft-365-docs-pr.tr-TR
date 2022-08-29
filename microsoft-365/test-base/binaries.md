---
title: Uygulama İkili Dosyalarını Karşıya Yükleme
description: Microsoft 365 için Test Tabanını kullanmaya başlama
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
ms.openlocfilehash: fdb5bfed0eb103be68e1a8967dc97f9fbe64683e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316413"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>3. Adım: İkili dosyalarınızı, bağımlılıklarınızı ve betiklerinizi karşıya yükleme

Bu sekmede, test paketinizi çalıştırmak için kullanılan ikili dosyaları, bağımlılıkları ve betikleri içeren tek bir zip paketini karşıya yükleyeceksiniz.

> [!NOTE]
> Zip paketinin boyutu en az 10 MB ile en fazla 2 GB arasında olmalıdır.

## <a name="upload-package-zip-file"></a>Paket zip dosyasını karşıya yükleme

:::image type="content" alt-text="İkili dosyalarınızı karşıya yükleyin." source="Media/AddBinaries.png":::

  - Karşıya yüklenen bağımlılıklar test çerçevelerini, betik altyapılarını veya uygulamanızı veya test çalışmalarınızı çalıştırmak için erişilecek verileri içerebilir. Örneğin, tarayıcı tabanlı testler çalıştırmaya yardımcı olmak için Selenium'u ve bir web sürücüsü yükleyicisini karşıya yükleyebilirsiniz.
  - Betik etkinliklerinizin modüler olduğundan emin olmak en iyi yöntemdir.
    - Betik `Install` yalnızca yükleme işlemlerini gerçekleştirir.
    - Betik `Launch` yalnızca uygulamayı başlatır.
    - Betik `Close` yalnızca uygulamayı kapatır.
    - İsteğe bağlı `Uninstall` betik yalnızca uygulamayı kaldırır.

**Şu anda portal yalnızca PowerShell betiklerini desteklemektedir.**


## <a name="next-steps"></a>Sonraki adımlar 

4. Adım: **Test Görevlerinizi Ayarlama** bölümüne gitmek için sonraki makaleye geçin.
> [!div class="nextstepaction"]
> [Geri dön](uploadApplication.md)
> [!div class="nextstepaction"]
> [Sonraki adım](testtask.md)

