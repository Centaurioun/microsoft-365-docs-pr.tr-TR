---
title: Python için Test Temel SDK'sı
description: Test Temeli'nin Python için SDK'sını anlamayla ilgili ayrıntılar
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 90a8348e2bde22fa2d0358b9d1696798e089d328
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316522"
---
# <a name="test-base-sdk-for-python"></a>Python için Test Temel SDK'sı

## <a name="overview"></a>Genel bakış
Test Temeli SDK'sı, Azure test temeli kaynağıyla etkileşime geçmek için kullanılabilir. (Başka bir ifadeyle uygulama paketinizi yönetin, paket oluşturma, paketi düzenleme ve paketi silme dahil edin).

SDK ile elde edilebilecek test özeti ve Çözümleme Sonucu şunlardır: scriptExecution, güvenilirlik, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.

Test Temeli SDK'sı ile test tabanını CI/CD işlem hattınızla tümleştirebilirsiniz.

## <a name="client-library"></a>İstemci Kitaplığı

Test temel paketini pip ile yükleyin.

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>Örnek
