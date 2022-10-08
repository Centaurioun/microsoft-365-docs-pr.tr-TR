---
title: Uç Nokta için Microsoft Defender Denetimli klasör erişimi (CFA) tanıtım test aracı
description: Microsoft Defender Virüsten Koruma tarafından kötü amaçlı uygulamaların ve tehditlerin nasıl değerlendirilip karşılandığına bakın.
keywords: Uç Nokta için Microsoft Defender, korumalı klasör erişimi engellendi, şüpheli dosyaları algılayın, şüpheli uygulamaları algılayın,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: a1b5548b47c9bd60764d988235999f76349e7db6
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319597"
---
# <a name="controlled-folder-access-cfa-demonstration-test-tool-block-script"></a>Denetimli klasör erişimi (CFA) tanıtım test aracı (blok betiği)

Denetimli Klasör Erişimi değerli verileri fidye yazılımı gibi kötü amaçlı uygulamalardan ve tehditlerden korumanıza yardımcı olur. Tüm uygulamalar (.exe, .scr, .dll dosyaları ve diğerleri dahil olmak üzere tüm yürütülebilir dosyalar) Microsoft Defender Virüsten Koruma tarafından değerlendirilir ve bu da uygulamanın kötü amaçlı veya güvenli olup olmadığını belirler. Uygulamanın kötü amaçlı veya şüpheli olduğu belirlenirse, korunan herhangi bir klasördeki dosyalarda değişiklik yapmasına izin verilmez.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 1709 derleme 16273
- Microsoft Defender Virüsten Koruma (etkin mod)

## <a name="powershell-commands"></a>PowerShell komutları

```powershell
Set-MpPreference -EnableControlledFolderAccess <State>
```

Devletleri:
- Etkin = Blok modu (1)
- AuditMode = Denetim Modu (2)
- Devre Dışı = Kapalı (0)

### <a name="verify-configuration"></a>Yapılandırmayı doğrulama

```powershell
Get-MpPreference
```
## <a name="scenario"></a>Senaryo

### <a name="setup"></a>Kurulum

Bu [kurulum betiğini](https://demo.wd.microsoft.com/Content/CFA_SetupScript.zip) indirip çalıştırın. Bu PowerShell komutunu kullanarak betik kümesi yürütme ilkesini Sınırsız olarak çalıştırmadan önce: Set-ExecutionPolicy Sınırsız

Bunun yerine şu el ile adımları gerçekleştirebilirsiniz:
1. PowerShell komutunu kullanarak CFA'yı açın: Set-MpPreference -EnableControlledFolderAccess Etkin
2. CFA [test aracını](https://demo.wd.microsoft.com/Content/CFAtool.exe) indirme
3. Yukarıdaki PowerShell komutlarını yürütme


## <a name="scenario-use-the-cfa-test-tool-to-simulate-an-untrusted-process-writing-to-a-protected-folder"></a>Senaryo: CfA test aracını kullanarak korumalı bir klasöre yazma işlemine güvenilmeyen bir işlemin benzetimini gerçekleştirme
1. CFA test aracını başlatma
2. İstenen klasörü seçin ve dosya oluşturun
- Daha fazla bilgiyi [burada](/windows/threat-protection/windows-defender-exploit-guard/evaluate-controlled-folder-access.md) bulabilirsiniz

## <a name="clean-up"></a>Temizleme

Bu [temizleme betiğini](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip) indirin ve çalıştırın. Bunun yerine şu el ile adımları gerçekleştirebilirsiniz:

- Set-MpPreference -EnableControlledFolderAccess Devre Dışı

## <a name="see-also"></a>Ayrıca bkz.
[Denetimli klasör erişimi](/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)