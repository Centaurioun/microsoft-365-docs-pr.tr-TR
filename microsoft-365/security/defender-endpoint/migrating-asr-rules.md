---
title: Üçüncü taraf HIPS'ten ASR kurallarına geçiş
description: Üçüncü taraf konak yetkisiz erişim önleme sistemi (HIPS) çözümünden ASR kurallarına geçişe nasıl yaklaşıldığı açıklanır.
keywords: Saldırı yüzeyi azaltma kuralları, asr, asr kuralları, kalçalar, konak izinsiz giriş önleme sistemi, koruma kuralları, anti-exploit, antiexploit, exploit, enfeksiyon önleme, Uç Nokta için Microsoft Defender
ms.topic: article
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: edbf7121a23bd5effda50256fdc07a6d58e09493
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231648"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Üçüncü taraf HIPS'ten ASR kurallarına geçiş

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Bu makale, ortak kuralları Uç Nokta için Microsoft Defender eşlemenize yardımcı olur.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Üçüncü taraf HIPS ürününden ASR kurallarına geçiş senaryoları

### <a name="block-creation-of-specific-files"></a>Belirli dosyaların oluşturulmasını engelleme

- **Şunlar için geçerlidir**: Tüm işlemler
- **İşlem**- Dosya Oluşturma
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab örnekleri
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Saldırı tekniklerini engeller ve Risk Altındaki Göstergeler'i (IOC) engellemez. Belirli bir dosya uzantısını engellemek her zaman kullanışlı değildir çünkü cihazın güvenliğinin aşılmasını engellemez. Saldırganlar yük için yeni bir uzantı türü oluşturana kadar yalnızca bir saldırıyı kısmen engeller.
- **Önerilen diğer özellikler**: Bulut Koruması ve Davranış Analizi ile birlikte Microsoft Defender Virüsten Koruma'nın etkinleştirilmesi kesinlikle önerilir. ASR kuralı "Fidye yazılımına karşı gelişmiş koruma kullan" gibi başka bir önleme kullanmanızı öneririz. Bu, fidye yazılımı saldırılarına karşı daha yüksek bir koruma düzeyi sağlar. Ayrıca, bu kayıt defteri anahtarlarının çoğu, belirli uyarıları tetikleyecek ASEP teknikleri gibi Uç Nokta için Microsoft Defender tarafından izlenir. Kullanılan kayıt defteri anahtarları için en az Yerel Yönetici veya Güvenilen Yükleyici ayrıcalıkları değiştirilebilir. En düşük yönetim hesapları veya haklarıyla kilitli bir ortam kullanılması önerilir. Daha geniş güvenlik önerilerimizin bir parçası olan "Gerekli olmayan roller için SeDebug'ü devre dışı bırak" dahil olmak üzere diğer sistem yapılandırmaları etkinleştirilebilir.

### <a name="block-creation-of-specific-registry-keys"></a>Belirli kayıt defteri anahtarlarının oluşturulmasını engelle

- **Şunlar için geçerlidir**: Tüm İşlemler
- **İşlemler**- Yok
- **operation**- Kayıt Defteri Değişiklikleri
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**-  Örnekleri *\* Software,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Saldırı tekniklerini engeller ve Risk Altındaki Göstergeler'i (IOC) engellemez. Belirli bir dosya uzantısını engellemek her zaman yararlı değildir çünkü cihazın güvenliğinin aşılmasını engellemez. Saldırganlar yük için yeni bir uzantı türü oluşturana kadar yalnızca bir saldırıyı kısmen engeller.
- **Önerilen diğer özellikler**: Bulut Koruması ve Davranış Analizi ile birlikte Microsoft Defender Virüsten Koruma'nın etkinleştirilmesi kesinlikle önerilir. ASR kuralı "Fidye yazılımına karşı gelişmiş koruma kullan" gibi ek önleme kullanmanızı öneririz. Bu, fidye yazılımı saldırılarına karşı daha yüksek bir koruma düzeyi sağlar. Ayrıca, bu kayıt defteri anahtarlarının bazıları, belirli uyarıları tetikleyecek ASEP teknikleri gibi Uç Nokta için Microsoft Defender tarafından izlenir. Ayrıca, kullanılan kayıt defteri anahtarları için en az Yerel Yönetici veya Güvenilen Yükleyici ayrıcalıkları değiştirilebilir. En düşük yönetim hesapları veya haklarıyla kilitli bir ortam kullanılması önerilir. Daha geniş güvenlik önerilerimizin bir parçası olan "Gerekli olmayan roller için SeDebug'ü devre dışı bırak" dahil olmak üzere diğer sistem yapılandırmaları etkinleştirilebilir.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Güvenilmeyen programların çıkarılabilir sürücülerden çalıştırılmasını engelleme

- USB'den Güvenilmeyen Programlar **için geçerlidir**
- **İşlemler**- *
- **İşlem**- İşlem Yürütme
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler Örnekleri:-*
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, çıkarılabilir sürücülerden güvenilmeyen ve imzalanmamış programların başlatılmasını önlemek için yerleşik bir kurala sahiptir: "USB'den çalıştırılan güvenilmeyen ve imzasız işlemleri engelle", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Önerilen diğer özellikler**- Lütfen Uç Nokta için Microsoft Defender kullanarak USB cihazları ve diğer çıkarılabilir medyalar için ek denetimleri keşfedin:[Uç Nokta için Microsoft Defender kullanarak USB cihazlarını ve diğer çıkarılabilir medyaları denetleme](/windows/security/threat-protection/device-control/control-usb-devices-using-intune).

### <a name="block-mshta-from-launching-certain-child-processes"></a>Mshta'nın belirli alt işlemleri başlatmasını engelleme

- **Şunun için geçerlidir**: Mshta
- **İşlemler**- mshta.exe
- **İşlem**- İşlem Yürütme
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- powershell.exe, cmd.exe regsvr32.exe örnekleri
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, alt işlemlerin "mshta.exe" olmasını önlemek için belirli bir kural içermez. Bu denetim, Exploit Protection veya Windows Defender Uygulama Denetimi kapsamındadır.
- **Önerilen diğer özellikler**: mshta.exe tamamen yürütülmesini önlemek için Windows Defender Uygulama Denetimi'ne olanak tanıyabilirsiniz. Kuruluşunuz iş kolu uygulamaları için "mshta.exe" gerektiriyorsa, mshta.exe alt işlemleri başlatmasını önlemek için belirli bir Windows Defender Exploit Protection kuralı yapılandırın.

### <a name="block-outlook-from-launching-child-processes"></a>Outlook'un alt işlemleri başlatmasını engelleme

- **Şunlar için geçerlidir**: Outlook
- **İşlemler**- outlook.exe
- **İşlem**- İşlem Yürütme
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler** örnekleri- powershell.exe
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kurallarının, Office iletişim uygulamalarının (Outlook, Skype ve Teams) alt işlemleri başlatmasını engelleyen yerleşik bir kuralı vardır: "Office iletişim uygulamasının alt işlemler oluşturmasını engelle", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Önerilen diğer özellikler**- PowerShell'den gelen saldırı yüzeyini en aza indirmek için PowerShell kısıtlanmış dil modunu etkinleştirmenizi öneririz.

### <a name="block-office-apps-from-launching-child-processes"></a>Office Uygulamalarının alt işlemleri başlatmasını engelleme

- **Şunlar için geçerlidir**: Office
- **İşlemler**- winword.exe, powerpnt.exe, excel.exe
- **İşlem**- İşlem Yürütme
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe örnekleri
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Office uygulamalarının alt işlemleri başlatmasını önlemek için yerleşik bir kurala sahiptir: "Tüm Office uygulamalarının alt işlemler oluşturmasını engelle", GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a".
- **Önerilen diğer özellikler**- Yok

### <a name="block-office-apps-from-creating-executable-content"></a>Office Uygulamalarının yürütülebilir içerik oluşturmalarını engelleme

- **Şunlar için geçerlidir**: Office
- **İşlemler**- winword.exe, powerpnt.exe, excel.exe
- **İşlem**- Dosya Oluşturma
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri örnekleri, İşlemler, Hizmetler**- C:\Users *\AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\**Temp.com, C:\Users*\Downloads**.exe, C:\Users *\AppData.scf **, C:\ProgramData.scf**, C:\Users\Public*.exe, C:\Users*\Desktop.exe
- **Saldırı Yüzeyi Azaltma kuralları**- Yok.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Wscript'in belirli dosya türlerini okumalarını engelleme

- **Şunun için geçerlidir**: Wscript
- **İşlemler**- wscript.exe
- **İşlem**- Dosya Okuma
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- C:\Users *\AppData**.js, C:\Users*\Downloads**.js örnekleri
- **Saldırı Yüzeyi Azaltma kuralları**- Güvenilirlik ve performans sorunları nedeniyle ASR kurallarının belirli bir işlemin belirli bir betik dosya türünü okumasını engelleme özelliği yoktur. Bu senaryolardan kaynaklanabilir saldırı vektörlerini önlemeye yönelik bir kuralımız var. Kural adı "JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelle" (GUID "d3e037e1-3eb8-44c8-a917-57927947596 ") ve "Belirsiz olabilecek betiklerin yürütülmesini engelle" (GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc").
- **Önerilen diğer özellikler**- Bu senaryolarda belirli saldırı vektörlerini azaltan belirli ASR kuralları olsa da, AV'nin varsayılan olarak kötü amaçlı yazılımdan koruma tarama arabirimi (AMSI) aracılığıyla betikleri (PowerShell, Windows Betik Konağı, JavaScript, VBScript ve daha fazlası) gerçek zamanlı olarak inceleyebildiğinden bahsetmek önemlidir. Burada daha fazla bilgi bulabilirsiniz: [Kötü Amaçlı Yazılımdan Koruma Tarama Arabirimi (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Alt işlemlerin başlatılmasını engelle

- **Adobe Acrobat için geçerlidir**
- **İşlemler**- AcroRd32.exe, Acrobat.exe
- **İşlem**- İşlem Yürütme
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- cmd.exe, powershell.exe wscript.exe örnekleri
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Adobe Reader'ın alt işlemleri başlatmasını engellemeye olanak sağlar. Kural adı "Adobe Reader'ın alt işlemler oluşturmasını engelle", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c" şeklindedir.
- **Önerilen diğer özellikler**- Yok

### <a name="block-download-or-creation-of-executable-content"></a>Yürütülebilir içeriğin indirilmesini veya oluşturulmasını engelleme

- **Şunlar için geçerlidir**: CertUtil: İndirilmesini veya yürütülebilir dosya oluşturulmasını engelleme
- **İşlemler**- certutil.exe
- **İşlem**- Dosya Oluşturma
- **Dosya/Klasör, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler-** *.exe
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Microsoft Defender Virüsten Koruma korumasının bir parçası olduğundan bu senaryoları desteklemez.
- **Önerilen diğer özellikler**: Microsoft Defender Virüsten Koruma, CertUtil'in yürütülebilir içerik oluşturmasını veya indirmesini engeller.

### <a name="block-processes-from-stopping-critical-system-components"></a>İşlemlerin kritik Sistem bileşenlerini durdurmalarını engelleme

- **Şunlar için geçerlidir**: Tüm İşlemler
- **İşlemler**- *
- **İşlem**- İşlem Sonlandırma
- **Dosyalar/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe ve daha fazlası örnekleri.
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Windows'un yerleşik güvenlik korumalarıyla korunduğundan bu senaryoları desteklemez.
- **Önerilen diğer özellikler**: ELAM (Erken Başlatma AntiMalware), PPL (Koruma Süreci Işığı), PPL Kötü Amaçlı Yazılımdan Koruma Işığı ve System Guard.

### <a name="block-specific-launch-process-attempt"></a>Belirli başlatma İşlemi Girişimini engelle

- **Belirli İşlemler için geçerlidir**
- **İşlemler**- "İşleminizi Adlandır"
- **İşlem**- İşlem Yürütme
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- tor.exe, bittorrent.exe, cmd.exe, powershell.exe ve daha fazlası
- **Saldırı Yüzeyi Azaltma kuralları**- Genel olarak ASR kuralları, Uygulama yöneticisi olarak işlev görecek şekilde tasarlanmamıştır.
- **Önerilen diğer özellikler**: Kullanıcıların belirli işlemleri veya programları başlatmasını önlemek için uygulama denetimi Windows Defender kullanılması önerilir. Uç Nokta için Microsoft Defender Dosya ve Sertifika göstergeleri bir Olay Yanıtı senaryosunda kullanılabilir (uygulama denetim mekanizması olarak görülmemelidir).

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Microsoft Defender Virüsten Koruma yapılandırmalarında yetkisiz değişiklikleri engelleme

- **Şunlar için geçerlidir**: Tüm İşlemler
- **İşlemler**- *
- **operation**- Kayıt Defteri Değişiklikleri
- **Dosya/Klasörler, Kayıt Defteri Anahtarları/Değerleri, İşlemler, Hizmetler**- HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring gibi örnekler.
- **Saldırı Yüzeyi Azaltma kuralları**- ASR kuralları, Uç Nokta için Microsoft Defender yerleşik korumasının bir parçası olduğundan bu senaryoları kapsamaz.
- **Diğer önerilen özellikler**- Kurcalama Koruması (Intune tarafından yönetilen) DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring ve DisableIOAVProtection kayıt defteri anahtarlarında (ve daha fazlası) yetkisiz değişiklikleri önler.

Ayrıca bkz.

- [Saldırı yüzeyini azaltma ile ilgili SSS](attack-surface-reduction-faq.yml)
- [Saldırı yüzeyi azaltma kurallarını etkinleştirme](enable-attack-surface-reduction.md)
- [Saldırı yüzeyi azaltma kurallarını değerlendirme](evaluate-attack-surface-reduction.md)
