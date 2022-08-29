---
title: Test görevlerinizi ayarlama
description: Test görevlerinizi ayarlama
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
ms.openlocfilehash: 3356fc09609601d1974cb3daea7ea7aeb6ac979e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316347"
---
# <a name="step-4-the-tasks-tab"></a>4. Adım: Görevler sekmesi

Görevler sekmesinde, ikili dosyalar sekmesi altında karşıya yüklediğiniz zip klasöründeki test betiklerinizin yollarını sağlamanız beklenir.

  - **Kullanıma Ait Test Betikleri:** Yükleme, başlatma, kapatma ve kaldırma betiklerinizin göreli yollarını yazın. Yükleme betiği için ek ayarlar da seçebilirsiniz.
  - **İşlevsel Test Betikleri:** Karşıya yüklenen her işlevsel test betiğinin göreli yolunu yazın. Düğme kullanılarak fazladan işlevsel test betikleri ```Add Script``` eklenebilir. En az bir (1) betik gerekir ve en fazla sekiz (8) işlevsel test betiği ekleyebilirsiniz. 
  
    Betikler listelendikleri sırayla çalışır. Belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.
    Sağlanan her betik için ek ayarlar seçme seçeneğiniz de vardır.

## <a name="set-script-path"></a>Betik yolunu ayarlama

![Test görevinin resmi.](Media/testtask.png)

Klasör yapısında göreli yol sağlama örneği aşağıda verilmiştir:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** olurdu. _göreli_ yol olarakScriptX.ps1.
  - **Script.ps1** göreli yol olarak _klasör1/script.ps1_ olacaktır.


## <a name="next-steps"></a>Sonraki adımlar

Sonraki makalede test seçenekleri sekmesinin ayrıntılarını görüntüleme 
> [!div class="nextstepaction"]
> [Sonraki adım](testoptions.md)
