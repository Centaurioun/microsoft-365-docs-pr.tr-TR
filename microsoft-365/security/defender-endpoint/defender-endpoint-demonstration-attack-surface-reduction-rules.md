---
title: Uç Nokta için Microsoft Defender saldırı yüzeyi azaltma kuralları tanıtımları
description: Saldırı yüzeyi azaltma kurallarının bilinen çeşitli tehdit türlerini nasıl engellediğini görün.
keywords: Uç Nokta için Microsoft Defender gösterimi, saldırı yüzeyi azaltma kuralları gösterimi, ASR kuralları, tanıtım
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: b0c57f4fc094d8efbcd2fd13f4c4835536dceb21
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729863"
---
# <a name="attack-surface-reduction-rules-demonstrations"></a>Saldırı yüzeyi azaltma kuralları tanıtımları

Saldırı Yüzeyi Azaltma (ASR) kuralları, genellikle kötü amaçlı yazılımlar ve kötü amaçlı uygulamalar tarafından makinelere bulaşmak için kullanılan belirli davranışları hedefler, örneğin:

- Dosyaları indirmeye veya çalıştırmaya çalışan Office uygulamalarında veya web postasında kullanılan yürütülebilir dosyalar ve betikler
- Karartılmış veya başka bir şekilde şüpheli olan betikler
- Uygulamaların gerçekleştirdiği ve normal gündelik iş sırasında başlatılmamış davranışlar

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 1709 derleme 16273
- Windows 10 1803 derlemesi (1803 kuralları)
- Microsoft Defender AV
- Microsoft Office (Office kuralları ve örneği için gereklidir)
- [ASR PowerShell betiklerini indirme](https://demo.wd.microsoft.com/Content/WindowsDefender_ASR_scripts.zip)

## <a name="powershell-commands"></a>PowerShell komutları

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 3B576869-A4EC-4529-8536-B80A7769E899 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D3E037E1-3EB8-44C8-A917-57927947596D -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D1E49AAC-8F56-4280-B9BA-993A6D77406C -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids C1DB55AB-C21A-4637-BB3F-A12568109D35 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 01443614-CD74-433A-B99E-2ECDC07BFC25 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 26190899-1602-49E8-8B27-EB1D0A1CE869 -AttackSurfaceReductionRules_Actions AuditMode
Add-MpPreference -AttackSurfaceReductionRules_Ids 7674BA52-37EB-4A4F-A9A1-F0F9A1619A2C -AttackSurfaceReductionRules_Actions AuditMode
```

### <a name="rule-states"></a>Kural durumları

|Durum | Mod| Sayısal değer |
|:---|:---|:---|
| Devre dışı | = Kapalı | 0 |
| Etkin | = Blok modu | 1 |
| Denetim | = Denetim modu | 2 |

### <a name="verify-configuration"></a>Yapılandırmayı doğrulama

```powershell

Get-MpPreference
```

## <a name="test-files"></a>Dosyaları test et

Not - Bazı test dosyalarında birden çok açık eklenmiş ve birden çok kural tetiklenecektir

| Kural adı | Kural GUID'i | Windows sürümü |
|:---|:---|:---|
| E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550 | 1709 |
| [Office uygulamalarının alt işlemler oluşturmalarını engelleme](https://demo.wd.microsoft.com/Content/TestFile_OfficeChildProcess_D4F940AB-401B-4EFC-AADC-AD5F3C50688A.docm) | D4F940AB-401B-4EFC-AADC-AD5F3C50688A | 1709 |
| [Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme](https://demo.wd.microsoft.com/Content/TestFile_Block_Office_applications_from_creating_executable_content_3B576869-A4EC-4529-8536-B80A7769E899.docm) | 3B576869-A4EC-4529-8536-B80A7769E899 | 1709 |
| Office uygulamalarının diğer işlemlere eklemesini engelleme | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 | 1709 |
| [Yürütülebilir dosyaları başlatmak için JavaScript ve VBScript'i engelleyin](https://demo.wd.microsoft.com/Content/TestFile_Impede_JavaScript_and_VBScript_to_launch_executables_D3E037E1-3EB8-44C8-A917-57927947596D.js) | D3E037E1-3EB8-44C8-A917-57927947596D | 1709 |
| Karartılmış olabilecek betiklerin yürütülmesini engelleme | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC | 1709 |
| [Office'te Makro kodundan Win32 içeri aktarmalarını engelleme](https://demo.wd.microsoft.com/Content/Block_Win32_imports_from_Macro_code_in_Office_92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B.docm) | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B | 1709 |
|[{PSExec & WMI komutlarından kaynaklanan İşlem Oluşturmalarını Engelle](https://demo.wd.microsoft.com/Content/TestFile_PsexecAndWMICreateProcess_D1E49AAC-8F56-4280-B9BA-993A6D77406C.vbs) | D1E49AAC-8F56-4280-B9BA-993A6D77406C | 1803 |
| [Çıkarılabilir USB medyası içinde güvenilmeyen veya imzalanmamış yürütülebilir dosyaları yürütmeyi engelle](https://demo.wd.microsoft.com/Content/UNSIGNED_ransomware_test_exe.exe) | B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 | 1803 |
| Agresif Fidye Yazılımı Önleme | C1DB55AB-C21A-4637-BB3F-A12568109D35 | 1803 |
| Yaygınlık, yaş veya güvenilen liste ölçütlerini karşılamadığı sürece yürütülebilir dosyaların çalışmasını engelleme | 01443614-CD74-433A-B99E-2ECDC07BFC25 | 1803 |
| Adobe Reader'ın alt işlemler oluşturmalarını engelleme | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c | 1803 |

## <a name="scenarios"></a>Senaryo

### <a name="setup"></a>Kurulum

Bu [kurulum betiğini](https://demo.wd.microsoft.com/Content/ASR_SetupScript.zip) indirip çalıştırın. Bu PowerShell komutunu kullanarak betik kümesi yürütme ilkesini Sınırsız olarak çalıştırmadan önce:

```powershell
Set-ExecutionPolicy Unrestricted

```

Bunun yerine şu el ile adımları gerçekleştirebilirsiniz:

1. c: adlı demo, "c:\demo" altında bir klasör oluşturun
2. Bu [temiz dosyayı](https://demo.wd.microsoft.com/Content/testfile_safe.txt) c:\demo dosyasına kaydedin.
3. Yukarıdaki powershell komutlarını kullanarak tüm kuralları etkinleştirin.

### <a name="scenario-1-asr-blocks-a-test-file-with-multiple-vulnerabilities"></a>Senaryo 1: ASR, birden çok güvenlik açığı olan bir test dosyasını engeller

1. Yukarıdaki PowerShell komutlarını kullanarak tüm kuralları blok modunda etkinleştirin (tümünü yapıştır seçeneğini kopyalayabilirsiniz)
2. Yukarıda bağlantılı test dosyalarından/belgelerden herhangi birini indirip açın, istenirse düzenlemeyi ve içeriği etkinleştirin.

#### <a name="scenario-1-expected-results"></a>Senaryo 1 beklenen sonuçlar

Hemen bir "Eylem engellendi" bildirimi görmeniz gerekir.

### <a name="scenario-2-asr-rule-blocks-the-test-file-with-the-corresponding-vulnerability"></a>Senaryo 2: ASR kuralı test dosyasını ilgili güvenlik açığıyla engeller

1. Yukarıdan PowerShell komutunu kullanarak test etmek istediğiniz kuralı yapılandırın.
2. Örnek: `Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Enabled`
3. Yukarıda bağlantılı olarak test etmek istediğiniz kuralın test dosyasını/belgesini indirip açın, istenirse düzenlemeyi ve içeriği etkinleştirin
4. Örnek: Office uygulamalarının D4F940AB-401B-4EFC-AADC-AD5F3C50688A [alt işlemleri oluşturmalarını engelleme](https://demo.wd.microsoft.com/Content/ransomware_testfile_doc.docm)

#### <a name="scenario-2-expected-results"></a>Senaryo 2 beklenen sonuçlar

Hemen bir "Eylem engellendi" bildirimi görmeniz gerekir.

### <a name="scenario-3-1803-asr-rule-blocks-unsigned-usb-content-from-executing"></a>Senaryo 3 (1803): ASR kuralı imzalanmamış USB içeriğinin yürütülmesini engeller

1. USB koruması için kuralı yapılandırın (B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4).

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Enabled
```

3. Dosyayı indirin ve bir USB çubuğuna yerleştirin ve [çıkarılabilir USB medyası içinde güvenilmeyen veya imzalanmamış yürütülebilir dosyaları engelleme yürütmesini](https://demo.wd.microsoft.com/Content/UNSIGNED_ransomware_test_exe.exe) yürütür

#### <a name="scenario-3-expected-results"></a>Senaryo 3 beklenen sonuçlar

Hemen bir "Eylem engellendi" bildirimi görmeniz gerekir.

### <a name="scenario-4-what-would-happen-without-asr"></a>Senaryo 4: ASR olmadan ne olur?

1. Temizleme bölümünde aşağıdaki PowerShell komutlarını kullanarak tüm ASR kurallarını kapatın
2. Yukarıda bağlantılı herhangi bir test dosyasını/belgesini indirin, istenirse düzenlemeyi ve içeriği etkinleştirin

#### <a name="scenario-4-expected-results"></a>Senaryo 4 beklenen sonuçlar

- c:\demo dosyasındaki dosyalar şifrelenir ve bir uyarı iletisi almanız gerekir
- Dosyaların şifresini çözmek için test dosyasını yeniden yürütür

## <a name="clean-up"></a>Temizleme

Bu [temizleme betiğini](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip) indirip çalıştırın

Alternatif olarak, şu el ile adımları gerçekleştirebilirsiniz:

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 3B576869-A4EC-4529-8536-B80A7769E899 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D3E037E1-3EB8-44C8-A917-57927947596D -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D1E49AAC-8F56-4280-B9BA-993A6D77406C -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids C1DB55AB-C21A-4637-BB3F-A12568109D35 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 01443614-CD74-433A-B99E-2ECDC07BFC25 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 26190899-1602-49E8-8B27-EB1D0A1CE869 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 7674BA52-37EB-4A4F-A9A1-F0F9A1619A2C -AttackSurfaceReductionRules_Actions Disabled
```

Temizleme c:\demo [şifrelemesi şifreleme/şifre çözme dosyasını](https://demo.wd.microsoft.com/Content/ransomware_cleanup_encrypt_decrypt.exe) çalıştırın

## <a name="see-also"></a>Ayrıca bkz.

[Saldırı yüzeyi azaltma kuralları dağıtım kılavuzu](attack-surface-reduction-rules-deployment.md)

[Saldırı yüzeyi azaltma kuralları başvurusu](attack-surface-reduction-rules-reference.md)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
