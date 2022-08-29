---
title: Uygulama/Test kuralları
description: Uygulama/test karşıya yüklenirken uyulması gereken kurallar
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 6a3878e0326fdcfe1ea9d35997e6a605457fcbf7
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316500"
---
# <a name="applicationtest-rules"></a>Uygulama/Test kuralları

Test Tabanındaki tüm uygulamaların veya testlerin aşağıdaki kurallara uyması gerekir:

## <a name="test-base-folders"></a>Temel klasörleri test edin 

Aşağıdaki klasörler Test Temeli altyapısı tarafından kullanılır:
* %SYSTEMDRIVE%\USL
* %SYSTEMDRIVE%\EtlExport
* %SYSTEMDRIVE%\Ffmpeg
* %SYSTEMDRIVE%\İzleme
* %SYSTEMDRIVE%\powershell-yaml
* %SYSTEMDRIVE%\ProcMon
* %SYSTEMDRIVE%\PSTools
* %SYSTEMDRIVE%\TokenProviderTool
* %SYSTEMDRIVE%\USLPowershellModules
* %SYSTEMDRIVE%\UtcUtil
* %SYSTEMDRIVE%\WPT
* %SYSTEMDRIVE%\WULogs

> [!IMPORTANT]
> **Aşağıdakilerden kaçının**:
> * Bu klasörlerden herhangi bir işlemin yürütülmesini engelleme. Uygulamanız kötü amaçlı yazılımdan koruma yazılımıysa, uygulama yüklemenizi bu klasörlerdeki tüm işlemlerin engelsiz yürütülmesine izin verecek şekilde yapılandırın.
> * Bu klasörlerin herhangi biriyle oynanıyor.

## <a name="test-base-registry-keys"></a>Test Temeli kayıt defteri anahtarları

Uygulamalar/testler şunlarla ilgili kayıt defteri anahtarlarını silmemeli veya değiştirmemelidir:
* Windows telemetri düzeyi
* TLS 1.2 kaldırılıyor
