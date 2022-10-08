---
title: Uç Nokta için Microsoft Defender Denetimli klasör erişimi (CFA) tanıtımları
description: Denetimli Klasör Erişimi'nin değerli verileri fidye yazılımı gibi kötü amaçlı uygulamalardan ve tehditlerden nasıl koruduğunu gösterir.
keywords: Uç Nokta için Microsoft Defender, Denetimli klasör erişim koruması, Denetimli klasör erişimi tanıtımı
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
ms.openlocfilehash: e5a83446613b28b633472f5c6368d92d5e850049
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319672"
---
# <a name="controlled-folder-access-cfa-demonstrations-block-ransomware"></a>Denetimli klasör erişimi (CFA) tanıtımları (fidye yazılımını engelle)

Denetimli Klasör Erişimi değerli verileri fidye yazılımı gibi kötü amaçlı uygulamalardan ve tehditlerden korumanıza yardımcı olur. Tüm uygulamalar (.exe, .scr, .dll dosyaları ve diğerleri dahil olmak üzere tüm yürütülebilir dosyalar) Microsoft Defender Virüsten Koruma tarafından değerlendirilir ve bu da uygulamanın kötü amaçlı veya güvenli olup olmadığını belirler. Uygulamanın kötü amaçlı veya şüpheli olduğu belirlenirse, korunan herhangi bir klasördeki dosyalarda değişiklik yapmasına izin verilmez.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 1709 derleme 16273
- Microsoft Defender Virüsten Koruma (etkin mod)

## <a name="powershell-commands"></a>PowerShell komutları

- Set-MpPreference -EnableControlledFolderAccess (Durum)
- Set-MpPreference -ControlledFolderAccessProtectedFolders C:\demo\

Devletleri
- Etkin = Blok modu (1)
- AuditMode = Denetim Modu (2)
- Devre Dışı = Kapalı (0)

## <a name="verify-configuration"></a>Yapılandırmayı doğrulama

Get-MpPreference

## <a name="test-file"></a>Test dosyası
[CFA fidye yazılımı test dosyası](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe)

## <a name="scenarios"></a>Senaryo

### <a name="setup"></a>Kurulum

Bu [kurulum betiğini](https://demo.wd.microsoft.com/Content/CFA_SetupScript.zip) indirip çalıştırın. Bu PowerShell komutunu kullanarak betik kümesi yürütme ilkesini Sınırsız olarak çalıştırmadan önce: Set-ExecutionPolicy Sınırsız

Bunun yerine şu el ile adımları gerçekleştirebilirsiniz:

1. c: adlı demo, "c:\demo" altında bir klasör oluşturun
2. Bu [temiz dosyayı](https://demo.wd.microsoft.com/Content/testfile_safe.txt) c:\demo dosyasına kaydedin (şifrelemek için bir şey gerekiyor)
3. Yukarıdaki PowerShell komutlarını yürüt

### <a name="scenario-1-cfa-blocks-ransomware-test-file"></a>Senaryo 1: CFA fidye yazılımı test dosyasını engelliyor

1. PowerShell komutunu kullanarak CFA'yı açın: Set-MpPreference -EnableControlledFolderAccess Etkin
2. PowerShell komutunu kullanarak tanıtım klasörünü korumalı klasörler listesine ekleyin: Set-MpPreference -ControlledFolderAccessProtectedFolders C:\demo\
3. Fidye yazılımı [test dosyasını](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe) indirin
4. Fidye yazılımı test dosyasını yürüt *bu fidye yazılımı değildir, basit c:\demo şifrelemeye çalışır

#### <a name="scenario-1-expected-results"></a>Senaryo 1 beklenen sonuçlar

Fidye yazılımı test dosyasını yürütürken 5 saniye sonra CFA tarafından engellenen bir bildirim görmeniz gerekir

### <a name="scenario-2-what-would-happen-without-cfa"></a>Senaryo 2: CFA olmadan ne olur?

1. Bu PowerShell komutunu kullanarak CFA'yı kapatın: Set-MpPreference -EnableControlledFolderAccess Devre Dışı
2. Fidye yazılımı [test dosyasını](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe) yürütme

#### <a name="scenario-2-expected-results"></a>Senaryo 2 beklenen sonuçlar

- c:\demo dosyasındaki dosyalar şifrelenir ve bir uyarı iletisi almanız gerekir
- Dosyaların şifresini çözmek için fidye yazılımı test dosyasını yeniden yürütür

## <a name="clean-up"></a>Temizleme

Bu [temizleme betiğini](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip) indirin ve çalıştırın. Bunun yerine şu el ile adımları gerçekleştirebilirsiniz:

- Set-MpPreference -EnableControlledFolderAccess Devre Dışı
- Temizleme c:\demo [şifrelemesi şifreleme/şifre çözme dosyasını](https://demo.wd.microsoft.com/Content/ransomware_cleanup_encrypt_decrypt.exe) çalıştırın

## <a name="see-also"></a>Ayrıca bkz.
[Denetimli klasör erişimi](/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard?ocid=wd-av-demo-cfa-bottom)