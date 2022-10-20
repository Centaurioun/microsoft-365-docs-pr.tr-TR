---
title: Zamanlanmış ve isteğe bağlı taramaları çalıştırın ve özelleştirin
description: Ağınızdaki uç noktalarda virüsten koruma taramalarını özelleştirme ve Microsoft Defender başlatma
keywords: tarama, zamanlama, özelleştirme, dışlamalar, dosyaları dışlama, düzeltme, tarama sonuçları, karantina, tehdit kaldırma, hızlı tarama, tam tarama, Microsoft Defender Virüsten Koruma
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 82cdf185f36bc337aa0c783d6d37a2fbb6e4036c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635718"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>Microsoft Defender Virüsten Koruma taramalarının ve düzeltmelerinin sonuçlarını özelleştirme, başlatma ve gözden geçirme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

grup ilkesi, PowerShell ve Windows Yönetim Araçları'nın (WMI) Microsoft Defender Virüsten Koruma taramalarını yapılandırmak için kullanabilirsiniz. 

## <a name="in-this-section"></a>Bu bölümde

Konu | Açıklama
---|---
[Microsoft Defender Virüsten Koruma taramalarında dosya, klasör ve işlem tarafından açılan dosya dışlamalarını yapılandırma ve doğrulama](configure-exclusions-microsoft-defender-antivirus.md) | Dosyaları (belirtilen işlemler tarafından değiştirilen dosyalar dahil) ve klasörleri isteğe bağlı taramaların, zamanlanmış taramaların ve her zaman açık gerçek zamanlı koruma izleme ve taramanın dışında tutabilirsiniz
[Microsoft Defender Virüsten Koruma tarama seçeneklerini yapılandırın](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Microsoft Defender Virüsten Koruma'yı belirli türlerdeki e-posta depolama dosyalarını, yedekleme veya yeniden ayrıştırma noktalarını ve arşivlenmiş dosyaları (.zip dosyaları gibi) taramalara dahil etmek üzere yapılandırabilirsiniz. Ağ dosyası taramasını da etkinleştirebilirsiniz
[Taramalar için düzeltmeyi yapılandırma](configure-remediation-microsoft-defender-antivirus.md) | Microsoft Defender Virüsten Koruma'nın bir tehdit algıladığında ne yapacağını ve karantinaya alınan dosyaların karantina klasöründe ne kadar süreyle tutulacaklarını yapılandırın
[Zamanlanmış taramaları yapılandırma](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Ne zaman çalıştırılmaları gerektiği ve tam veya hızlı tarama olarak çalıştırılıp çalıştırılmadıkları da dahil olmak üzere yinelenen (zamanlanmış) taramalar ayarlama
[Taramaları yapılandırma ve çalıştırma](run-scan-microsoft-defender-antivirus.md) | PowerShell, Windows Yönetim Araçları'nı kullanarak veya Windows Güvenliği uygulamasıyla uç noktalarda tek tek isteğe bağlı taramaları çalıştırma ve yapılandırma
[Tarama sonuçlarını gözden geçirme](review-scan-results-microsoft-defender-antivirus.md) | Microsoft Endpoint Configuration Manager, Microsoft Intune veya Windows Güvenliği uygulamasını kullanarak taramaların sonuçlarını gözden geçirin