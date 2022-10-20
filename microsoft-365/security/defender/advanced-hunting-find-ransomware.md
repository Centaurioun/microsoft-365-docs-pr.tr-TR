---
title: Gelişmiş avcılık ile fidye yazılımı bulma
description: Fidye yazılımından etkilenecek cihazları bulmak için gelişmiş avcılığı kullanın.
keywords: gelişmiş avcılık, fidye yazılımı, tehdit avcılığı, siber tehdit avcılığı, arama, sorgulama, telemetri, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-ransomware
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 0decdcf0302b9cd3ea7db3aeda53a1d15d49c61d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640752"
---
# <a name="hunt-for-ransomware"></a>Fidye yazılımı avlayın

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Fidye yazılımı, tek tek bilgisayar kullanıcılarını etkileyen basit ticari kötü amaçlı yazılımlardan sektörleri ve kamu kurumlarını ciddi şekilde etkileyen kurumsal bir tehdide dönüşmüştür. [Microsoft 365 Defender](microsoft-365-defender.md) fidye yazılımlarını ve ilişkili yetkisiz erişim etkinliklerini algılayıp engelleyen birçok özellik sağlasa da, güvenlik açığı belirtileri için proaktif denetimler yapmak ağınızın korunmasına yardımcı olabilir.

> [İnsan tarafından çalıştırılan fidye yazılımı hakkında bilgi edinin](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

Microsoft 365 Defender'da [gelişmiş avcılık](advanced-hunting-overview.md) sayesinde fidye yazılımı etkinliğiyle ilişkili tek tek yapıtları bulayan sorgular oluşturabilirsiniz. Ayrıca, hemen ilgilenilmesi gereken cihazları bulmak için etkinlik işaretlerini arayabilen ve bu işaretleri tartabilen daha gelişmiş sorgular da çalıştırabilirsiniz.

## <a name="signs-of-ransomware-activity"></a>Fidye yazılımı etkinliğinin işaretleri
Microsoft güvenlik araştırmacıları, karmaşık davetsiz misafirler tarafından başlatılan birçok fidye yazılımı kampanyasında çeşitli yaygın ancak ince yapıtları gözlemlemektedir. Bu işaretler çoğunlukla şifrelemeye hazırlanmak, algılamayı önlemek ve adli kanıtları temizlemek için sistem araçlarının kullanılmasını içerir.

| Fidye yazılımı etkinliği | Ortak araçlar | Niyet |
|--|--|--|
| İşlemleri durdurma | _taskkill.exe_, _net stop_ | Şifreleme için hedeflenen dosyaların çeşitli uygulamalar tarafından kilitlenmediğinden emin olun. |
| Hizmetleri kapatma | _sc.exe_ | - Şifreleme için hedeflenen dosyaların çeşitli uygulamalar tarafından kilitlenmediğinden emin olun.<br>- Güvenlik yazılımının şifrelemeyi ve diğer fidye yazılımı etkinliklerini kesintiye uğratmasını engelleyin.<br>- Yedekleme yazılımının kurtarılabilir kopyalar oluşturmasını durdurun.  |
| Günlükleri ve dosyaları silme | _cipher.exe_, _wevtutil_, _fsutil.exe_ | Adli delilleri kaldırın. |
| Gölge kopyaları silme  | _vsadmin.exe_, _wmic.exe_ | Şifrelenmiş dosyaları kurtarmak için kullanılabilecek sürücü gölge kopyalarını kaldırın. |
| Yedeklemeleri silme ve durdurma | _wbadmin.exe_ | Mevcut yedeklemeleri silin ve zamanlanmış yedekleme görevlerini durdurun ve şifrelemeden sonra kurtarmayı engelleyin. |
| Önyükleme ayarlarını değiştirme | _bcdedit.exe_ | Şifreleme işleminden kaynaklanabilir önyükleme hatalarından sonra uyarıları ve otomatik onarımları kapatın. |
| Kurtarma araçlarını kapatma | _schtasks.exe_, _regedit.exe_, | Sistem Geri Yükleme'yi ve diğer sistem kurtarma seçeneklerini kapatın. |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>Fidye yazılımı etkinliğinin bireysel işaretlerini denetleyin
Önceki bölümde açıklanan etkinlikler de dahil olmak üzere fidye yazılımı davranışını oluşturan birçok etkinlik zararsız olabilir. Fidye yazılımını bulmak için aşağıdaki sorguları kullanırken, aynı cihazların olası fidye yazılımı etkinliğine ilişkin çeşitli işaretler sergileyip sergilemediğini denetlemek için birden fazla sorgu çalıştırın.

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>_taskkill.exe_ kullanarak birden çok işlemi durdurma
Bu sorgu, _taskkill.exe_ yardımcı programını kullanarak en az 10 ayrı işlemi durdurma girişimlerini denetler. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>_Net stop_ kullanarak işlemleri durdurma
Bu sorgu _, net stop_ komutunu kullanarak en az 10 ayrı işlemi durdurma girişimlerini denetler. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>_cipher.exe_ kullanarak birden çok sürücüdeki verilerin silinmesi
Bu sorgu _,cipher.exe_ kullanarak birden çok sürücüdeki verileri silme girişimlerini denetler. Bu etkinlik genellikle şifrelemeden sonra verilerin kurtarılmasını önlemek için fidye yazılımı tarafından gerçekleştirilir. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>_Wevtutil_ kullanılarak olay günlüklerinden adli kanıtların temizlenmesi
Bu sorgu _, wevtutil_ kullanarak olay günlüklerinden en az 10 günlük girdisini temizleme girişimlerini denetler. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>_sc.exe_ kullanarak hizmetleri kapatma
Bu sorgu, _sc.exe_ kullanarak en az 10 mevcut hizmeti kapatma girişimlerini denetler. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>Sistem Geri Yükleme'yi kapatma
Bu sorgu, Sistem Geri Yükleme'yi durdurma ve sistemin geri yükleme noktaları oluşturmasını engelleme girişimlerini tanımlar. Bu, fidye yazılımı tarafından şifrelenmiş verileri kurtarmak için kullanılabilir. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a>Yedekleme silme
Bu sorgu, şifrelemeden önce gölge kopya anlık görüntülerini silmek için _wmic.exe_ kullanımını tanımlar. [Sorguyu çalıştırma](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>Fidye yazılımı etkinliğinin birden çok işaretini denetleyin
Birkaç sorguyu ayrı ayrı çalıştırmak yerine, etkilenen cihazları tanımlamak için birden çok fidye yazılımı etkinliği işaretini denetleyecek kapsamlı bir sorgu da kullanabilirsiniz. Aşağıdaki birleştirilmiş sorgu:
- Fidye yazılımı etkinliğinin hem nispeten somut hem de ince işaretlerini arar
- Bu işaretlerin varlığını tartıyor
- Fidye yazılımı hedefi olma olasılığı daha yüksek olan cihazları tanımlar 

Çalıştırıldığında, bu birleştirilmiş sorgu birden çok saldırı işareti sergileyen cihazların listesini döndürür. Her fidye yazılımı etkinliğinin sayısı da gösterilir. Bu birleştirilmiş sorguyu çalıştırmak için doğrudan [gelişmiş tehdit avcılığı sorgu düzenleyicisine](https://security.microsoft.com/advanced-hunting) kopyalayın. 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a>Sorgu sonuçlarını anlama ve ayarlama
Birleştirilmiş sorgu aşağıdaki sonuçları döndürür:

- **DeviceId**— etkilenen cihazı tanımlar 
- **TimeStamp**— cihazda ilk kez fidye yazılımı etkinliğine ilişkin herhangi bir işaret gözlemlendi
- **Belirli etkinlik işaretleri**— _BcdEdit_ veya _FsUtil_ gibi birden çok sütunda gösterilen her işaretin sayısı
- **TotalEvidenceCount**— gözlemlenen işaret sayısı
- **UniqueEvidenceCount**— gözlemlenen işaret türlerinin sayısı

:::image type="content" source="../../media/advanced-hunting-ransomware-query.png" alt-text="Microsoft 365 Defender portalında fidye yazılımı etkinliği için birleştirilmiş sorgu örneği" lightbox="../../media/advanced-hunting-ransomware-query.png":::

*Etkilenen cihazları ve fidye yazılımı etkinliğinin çeşitli işaretlerini gösteren sorgu sonuçları*

Varsayılan olarak, sorgu sonucu yalnızca ikiden fazla fidye yazılımı etkinliği türüne sahip cihazları listeler. Fidye yazılımı etkinliği işareti olan tüm cihazları görmek için aşağıdaki `where` işleci değiştirin ve sayıyı sıfır (0) olarak ayarlayın. Daha az cihaz görmek için daha yüksek bir sayı ayarlayın. 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>İlgili konular
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Sorgu dilini öğrenin](advanced-hunting-query-language.md)
- [Sorgu sonuçlarıyla çalışın](advanced-hunting-query-results.md)
- [Paylaşılan sorguları kullanın](advanced-hunting-shared-queries.md)
- [Şemayı anlayın](advanced-hunting-schema-tables.md)
- [Sorgu en iyi yöntemlerini uygulayın](advanced-hunting-best-practices.md)

## <a name="more-ransomware-resources"></a>Diğer fidye yazılımı kaynakları

Microsoft'tan önemli bilgiler:

- [Artan fidye yazılımı tehdidi](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), Microsoft On the Issues blog gönderisi 20 Temmuz 2021'de
- [İnsan tarafından çalıştırılan fidye yazılımı](/security/compass/human-operated-ransomware)
- [Fidye yazılımı ve gaspa karşı hızla koruma](/security/compass/protect-against-ransomware)
- [2021 Microsoft Dijital Savunma Raporu](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (bkz. sayfa 10-19)
- [Fidye yazılımı: Microsoft 365 Defender portalında sürekli ve sürekli tehdit tehdit](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) analizi raporu

Microsoft 365:

- [Microsoft 365 kiracınız için fidye yazılımı koruması dağıtın](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Azure ve Microsoft 365 ile Fidye Yazılımı Dayanıklılığını En Üst Düzeye Çıkarma](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Fidye yazılımı saldırısından kurtarma](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [Kötü amaçlı yazılım ve fidye yazılımı koruması](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Windows bilgisayarınızı fidye yazılımlarından koruma](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online'da fidye yazılımlarını işleme](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- Microsoft 365 Defender portalında [fidye yazılımı için tehdit analizi raporları](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)

Microsoft Azure:

- [Fidye Yazılımı Saldırısı için Azure Defenses](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Azure ve Microsoft 365 ile Fidye Yazılımı Dayanıklılığını En Üst Düzeye Çıkarma](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Fidye yazılımlarına karşı koruma sağlamak için yedekleme ve geri yükleme planı](/security/compass/backup-plan-to-protect-against-ransomware)
- [Microsoft Azure Backup ile fidye yazılımlarından korunmaya yardımcı olun](https://www.youtube.com/watch?v=VhLOr2_1MCg) (26 dakikalık video)
- [Sistemik kimlik güvenliğinin aşılmasından kurtarma](/azure/security/fundamentals/recover-from-identity-compromise)
- [Microsoft Sentinel'de gelişmiş çok aşamalı saldırı algılama](/azure/sentinel/fusion#ransomware)
- [Microsoft Sentinel'de Fidye Yazılımı için Fusion Algılama](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps:

-  [Cloud Apps için Defender'da anomali algılama ilkeleri oluşturma](/cloud-app-security/anomaly-detection-policy)

Microsoft Güvenlik ekibi blog gönderileri:

- [Fidye yazılımlarını önlemeye ve fidye yazılımlarından kurtulmaya yönelik üç adım (Eylül 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [İnsan tarafından çalıştırılan fidye yazılımıyla mücadele kılavuzu: Bölüm 1 (Eylül 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Microsoft'un Algılama ve Yanıt Ekibi'nin (DART) fidye yazılımı olay araştırmalarını nasıl yürüttüğüne ilişkin temel adımlar.

- [İnsan tarafından çalıştırılan fidye yazılımıyla mücadele kılavuzu: Bölüm 2 (Eylül 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  Öneriler ve en iyi yöntemler.

- [Siber güvenlik risklerini anlayarak dayanıklı hale gelme: Bölüm 4— Mevcut tehditlerde gezinme (Mayıs 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  **Fidye yazılımı** bölümüne bakın.

- [İnsan tarafından işletilen fidye yazılımı saldırıları: Önlenebilir bir olağanüstü durum (Mart 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  Gerçek saldırıların saldırı zinciri analizlerini içerir.

- [Fidye yazılımı yanıtı— ödeme yapmak için mi yoksa ödememek için mi? (Aralık 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro fidye yazılımı saldırısına şeffaflıkla yanıt veriyor (Aralık 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
