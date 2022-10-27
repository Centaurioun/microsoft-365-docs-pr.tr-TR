---
title: Saldırı yüzeyi azaltma kuralları başvurusu
description: kural başına Uç Nokta için Microsoft Defender (MDE) saldırı yüzeyi azaltma (ASR) kurallarıyla ilgili ayrıntıları listeler.
keywords: Microsoft Saldırı yüzeyi azaltma kuralları, Uç Nokta için Microsoft Defender ASR kuralları, ASR kuralları listesi, ASR, asr kuralları, kalçalar, konak yetkisiz erişim önleme sistemi, koruma kuralları, kötüye kullanıma karşı koruma kuralları, antiexploit, exploit kuralları, bulaşma önleme kuralları, Uç Nokta için Microsoft Defender, ASR kurallarını yapılandırma, ASR kuralı Açıklama
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.topic: reference
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 2072af8e0591ae0657457b00dbcfec6c7b21ff82
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718248"
---
# <a name="attack-surface-reduction-asr-rules-reference"></a>Saldırı yüzeyini azaltma (ASR) kuralları başvurusu

**Şunlar için geçerlidir:**

- [Uç Nokta Planı 1 için Microsoft Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender Virüsten Koruma

**Platform:**

- Windows

Bu makalede Uç Nokta için Microsoft Defender saldırı yüzeyini azaltma (ASR) kuralları hakkında bilgi sağlanır:

- [ASR kuralları desteklenen işletim sistemi sürümleri](#asr-rules-supported-operating-systems)
- [ASR kuralları tarafından desteklenen yapılandırma yönetim sistemleri](#asr-rules-supported-configuration-management-systems)
- [ASR kuralı uyarı ve bildirim ayrıntıları başına](#per-asr-rule-alert-and-notification-details)
- [ASR kuralı-GUID matrisi](#asr-rule-to-guid-matrix)
- [ASR kural modları](#asr-rule-modes)
- [Kural başına açıklama sayısı](#per-rule-descriptions)

## <a name="attack-surface-reduction-rules-by-type"></a>Türe göre saldırı yüzeyi azaltma kuralları

ASR kuralları iki türden biri olarak kategorize edilir:

1. **Standart koruma kuralları**: Diğer ASR kurallarının etkisini ve yapılandırma gereksinimlerini değerlendirirken Microsoft'un her zaman etkinleştirmenizi önerdiği en düşük kural kümesidir. Bu kurallar genellikle son kullanıcı üzerinde en az farkedilebilir etkiye sahiptir.
1. **Diğer kurallar**: [Saldırı yüzeyi azaltma (ASR) kuralları dağıtım kılavuzunda](attack-surface-reduction-rules-deployment.md) belgelendiği gibi belgelenmiş dağıtım adımlarını izlemenin bir ölçüsünü gerektiren kurallar [Plan > Test (denetim) > Etkinleştir (blok/uyarı modları)]]

Standart koruma kurallarını etkinleştirmenin en kolay yöntemi için bkz. [Basitleştirilmiş standart koruma seçeneği](attack-surface-reduction-rules-report.md#simplified-standard-protection-option).

| ASR kural adı: | Standart koruma kuralı mı? | Başka bir kural mı? |
|:---|:---|:---|
| Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi| Evet | |
| Adobe Reader'ın alt işlemler oluşturmalarını engelleme | | Evet |
| Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme | | Evet |
| Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme | Evet | |
| E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme | | Evet |
| Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin | | Evet |
| Karartılmış olabilecek betiklerin yürütülmesini engelleme | | Evet |
| JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme | | Evet |
| Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme | | Evet |
| Office uygulamalarının diğer işlemlere kod eklemesini engelleme | | Evet |
| Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme | | Evet |
| WMI olay aboneliği aracılığıyla kalıcılığı engelleme | Evet | |
| PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme | | Evet |
| USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme | | Evet |
| Office makrolarından Win32 API çağrılarını engelleme | | Evet |
| Fidye yazılımına karşı gelişmiş koruma kullanma | | Evet |

## <a name="asr-rules-supported-operating-systems"></a>ASR kuralları tarafından desteklenen işletim sistemleri

Aşağıdaki tabloda, şu anda genel kullanıma sunulan kurallar için desteklenen işletim sistemleri listelenmektedir. Kurallar bu tabloda alfabetik sırada listelenmiştir.

> [!NOTE]
>
> Aksi belirtilmedikçe, en düşük Windows&nbsp;10 derlemesi sürüm 1709 (RS3, derleme 16299) veya üstüdür; en düşük Windows&nbsp;Server derlemesi 1809 veya üzeridir.
>
> Windows Server 2012&nbsp;R2 ve Windows&nbsp;&nbsp;Server&nbsp;&nbsp;2016'daki saldırı yüzeyi azaltma kuralları, modern birleşik çözüm paketi kullanılarak eklenen cihazlar için kullanılabilir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 Önizlemesi için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview).

| Kural adı| Windows&nbsp;11 <br>ve<br> Windows&nbsp;10 | Windows&nbsp;Server <br> 2022 <br>ve<br>  Windows&nbsp;Server <br> 2019 | Windows Server | Windows&nbsp;Server <br> 2016 <sup>[[1, 2](#fn1)]<sup></sup> | Windows&nbsp;Server <br> 2012&nbsp;R2 <sup>[[1, 2](#fn1)]<sup></sup> |
|:---|:---:|:---:|:---:|:---:|:---:|
| [Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi](#block-abuse-of-exploited-vulnerable-signed-drivers) | E | E | E <br> sürüm 1803 (Altı Aylık Kurumsal Kanal) veya üzeri | E | E |
| [Adobe Reader'ın alt işlemler oluşturmalarını engelleme](#block-adobe-reader-from-creating-child-processes) | E <br> sürüm 1809 veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E | E | E |
| [Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme](#block-all-office-applications-from-creating-child-processes) | E | E | E | E | E |
| [Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | E <br> sürüm 1803 veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E | E | E |
| [E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme](#block-executable-content-from-email-client-and-webmail) | E | E | E | E | E |
| [Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | E <br> sürüm 1803 veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E | E | E |
| [Karartılmış olabilecek betiklerin yürütülmesini engelleme](#block-execution-of-potentially-obfuscated-scripts) | E | E | E | E | E |
| [JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | E | E | E | N | N |
| [Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme](#block-office-applications-from-creating-executable-content) | E | E | E | E | E |
| [Office uygulamalarının diğer işlemlere kod eklemesini engelleme](#block-office-applications-from-injecting-code-into-other-processes)  | E | E | E | E | E |
| [Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme](#block-office-communication-application-from-creating-child-processes) | E | E | E | E | E |
| [Windows Yönetim Araçları (WMI) olay aboneliği aracılığıyla kalıcılığı engelleme](#block-persistence-through-wmi-event-subscription) <br> \*_Dosya ve klasör dışlamaları desteklenmiyor._ | E <br> sürüm 1903 (derleme 18362) veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E <br> sürüm 1903 (derleme 18362) veya üzeri | N | N |
| [PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme](#block-process-creations-originating-from-psexec-and-wmi-commands) | E <br> sürüm 1803 veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E | E | E |
| [USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme](#block-untrusted-and-unsigned-processes-that-run-from-usb) | E | E | E | E | E |
| [Office makrolarından Win32 API çağrılarını engelleme](#block-win32-api-calls-from-office-macros) | E | E | E | N | N |
| [Fidye yazılımına karşı gelişmiş koruma kullanma](#use-advanced-protection-against-ransomware) | E <br> sürüm 1803 veya üzeri <sup>[[3](#fn1)]<sup></sup> | E | E | E | E |

(<a id="fn1">1</a>) Windows Server 2012 ve 2016 için modern birleşik çözümü ifade eder. Daha fazla bilgi için bkz. [Uç Nokta için Defender hizmetine Windows Sunucuları ekleme](configure-server-endpoints.md).

(<a id="fn1">2</a>) Windows&nbsp;Server 2016 ve Windows&nbsp;Server 2012&nbsp;R2 için, Microsoft Endpoint Configuration Manager için gereken en düşük sürüm 2111'dir.

(<a id="fn1">3</a>) Sürüm ve derleme numarası yalnızca Windows&nbsp;10 için geçerlidir.

## <a name="asr-rules-supported-configuration-management-systems"></a>ASR kuralları tarafından desteklenen yapılandırma yönetim sistemleri

Bu tabloda başvurulan yapılandırma yönetim sistemi sürümleri hakkındaki bilgilerin bağlantıları bu tablonun altında listelenmiştir.

|Kural adı | Microsoft Intune | Microsoft Uç Noktası Yapılandırma Yöneticisi |<sup>grup ilkesi[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|
|[Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi](#block-abuse-of-exploited-vulnerable-signed-drivers) | E |   | E  |  E  |
|[Adobe Reader'ın alt işlemler oluşturmalarını engelleme](#block-adobe-reader-from-creating-child-processes) | E |  | E  | E  |
|[Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme](#block-all-office-applications-from-creating-child-processes) | E |E <br><br> CB 1710 | E  | E  |
|[Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | E  | E <br><br>CB 1802 | E  | E  |
|[E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme](#block-executable-content-from-email-client-and-webmail) | E |E <br><br> CB 1710 | E | E  |
|[Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | E | E <br><br> CB 1802 |  E |  E |
|[Karartılmış olabilecek betiklerin yürütülmesini engelleme](#block-execution-of-potentially-obfuscated-scripts) | E |E  <br><br> CB 1710 | E  | E  |
|[JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | E |E <br><br> CB 1710 | E  | E  |
|[Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme](#block-office-applications-from-creating-executable-content) | E |E <br><br> CB 1710 | E  | E  |
|[Office uygulamalarının diğer işlemlere kod eklemesini engelleme](#block-office-applications-from-injecting-code-into-other-processes) | E |E <br><br> CB 1710 | E  | E  |
|[Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme](#block-office-communication-application-from-creating-child-processes) | E |E <br><br> CB 1710 | E  | E  |
|[WMI olay aboneliği aracılığıyla kalıcılığı engelleme](#block-persistence-through-wmi-event-subscription) |E  |  |E   | E  |
|[PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme](#block-process-creations-originating-from-psexec-and-wmi-commands) | E |   |  E | E  |
|[USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme](#block-untrusted-and-unsigned-processes-that-run-from-usb) | E |E <br><br> CB 1802  | E  | E  |
|[Office makrolarından Win32 API çağrılarını engelleme](#block-win32-api-calls-from-office-macros) | E |E <br><br> CB 1710  | E  |  E |
|[Fidye yazılımına karşı gelişmiş koruma kullanma](#use-advanced-protection-against-ransomware) | E |E <br><br> CB 1802 | E  | E  |

  (<a id="fn1">1</a>) Herhangi bir kuralın GUID'sini kullanarak saldırı yüzeyi azaltma kurallarını kural temelinde yapılandırabilirsiniz.

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM artık Microsoft Endpoint Configuration Manager._

## <a name="per-asr-rule-alert-and-notification-details"></a>ASR kuralı uyarı ve bildirim ayrıntıları başına

Blok modundaki tüm kurallar için bildirim bildirimleri oluşturulur. Diğer modlardaki kurallar bildirim oluşturmaz

"Kural Durumu" belirtilen kurallar için:

- Birleşimleri olan \<ASR Rule, Rule State\> ASR kuralları, uyarıları (bildirim bildirimleri) yalnızca yüksek bulut bloğu düzeyindeki cihazlar için Uç Nokta için Microsoft Defender ortaya koyabilmek için kullanılır. Yüksek bulut bloğu düzeyinde olmayan cihazlar herhangi bir <ASR Kuralı, Kural Durumu> birleşimleri için uyarı oluşturmaz
- EDR uyarıları belirtilen durumlarda ASR kuralları için oluşturulur, ancak yalnızca yüksek bulut bloğu düzeyindeki cihazlar için oluşturulur.

| Kural adı: | Kural durumu: | EDR'de uyarılar oluşturulsun mu? <br> (Evet&nbsp;\|&nbsp;Hayır) | Bildirim oluştursun mu? <br> (Evet&nbsp;\|&nbsp;Hayır) |
|---|:---:|:---:|:---:|
|   |   |  _Yalnızca yüksek bulut blok düzeyindeki cihazlar için_ | _Yalnızca Blok modunda_ |
|[Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | E |
|[Adobe Reader'ın alt işlemler oluşturmalarını engelleme](#block-adobe-reader-from-creating-child-processes) | Engelle  | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme](#block-all-office-applications-from-creating-child-processes) |   | N | E |
|[Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | E |
|[E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme](#block-executable-content-from-email-client-and-webmail) |   | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | E |
|[Karartılmış olabilecek betiklerin yürütülmesini engelleme](#block-execution-of-potentially-obfuscated-scripts) |  Denetim&nbsp;\|&nbsp;Bloğu | Y \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | N \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Engelle | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | E <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme](#block-office-applications-from-creating-executable-content) |   | N | E |
|[Office uygulamalarının diğer işlemlere kod eklemesini engelleme](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | E |
|[Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme](#block-office-communication-application-from-creating-child-processes) |  |  N | E |
|[WMI olay aboneliği aracılığıyla kalıcılığı engelleme](#block-persistence-through-wmi-event-subscription) |  Denetim&nbsp;\|&nbsp;Bloğu | Y \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | N \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | E |
|[USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Denetim&nbsp;\|&nbsp;Bloğu | Y \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | N \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
|[Office makrolarından Win32 API çağrılarını engelleme](#block-win32-api-calls-from-office-macros) |   | N | E |
|[Fidye yazılımına karşı gelişmiş koruma kullanma](#use-advanced-protection-against-ransomware) | Denetim&nbsp;\|&nbsp;Bloğu | Y \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir  | N \| Y <br> Yüksek bulut blok düzeyinde cihaz gerektirir |
  
## <a name="asr-rule-to-guid-matrix"></a>ASR kuralı-GUID matrisi

| Kural Adı | Kural GUID'i |
|:-----|:-----|
| Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| Adobe Reader'ın alt işlemler oluşturmalarını engelleme | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| Karartılmış olabilecek betiklerin yürütülmesini engelleme | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme | d3e037e1-3eb8-44c8-a917-57927947596d |
| Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme | 3b576869-a4ec-4529-8536-b80a7769e899 |
| Office uygulamalarının diğer işlemlere kod eklemesini engelleme | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| WMI olay aboneliği aracılığıyla kalıcılığı engelleme <br>* Dosya ve klasör dışlamaları desteklenmiyor. | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| Office makrolarından Win32 API çağrılarını engelleme | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| Fidye yazılımına karşı gelişmiş koruma kullanma | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>ASR kural modları

- **Yapılandırılmadı** veya **Devre Dışı Bırak**: ASR kuralının etkinleştirilmediği veya devre dışı bırakıldığı durum. Bu durum için kod = 0.
- **Engelle**: ASR kuralının etkinleştirildiği durum. Bu durum için kod 1'dir.
- **Denetim**: ASR kuralının etkinse kuruluş veya ortam üzerindeki etkisine göre değerlendirildiği durumdur (engelleyecek veya uyaracak şekilde ayarlanır). Bu durum için kod 2'dir.
- **Uyarmak** ASR kuralının etkinleştirildiği ve son kullanıcıya bir bildirim sunduğu ancak son kullanıcının bloğu atlamasına izin veren durum. Bu durum için kod 6'dır.

_Uyarı modu_ , kullanıcıları riskli olabilecek eylemler hakkında uyaran bir blok modu türüdür. Kullanıcılar blok uyarısı iletisini atlamayı ve temel eyleme izin vermeyi seçebilir. Kullanıcılar bloğu zorlamak için **Tamam'ı** seçebilir veya blok sırasında oluşturulan son kullanıcı açılır bildirimi aracılığıyla atlama seçeneğini ( **Engellemeyi Kaldır** ) seçebilir. Uyarının engeli kaldırıldıktan sonra, son kullanıcının eylemi yeniden oluşturması gerekeceği uyarı iletisinin bir sonraki oluş zamanına kadar işleme izin verilir.

İzin ver düğmesine tıklandığında, blok 24 saat boyunca gizlenecektir. 24 saat sonra, son kullanıcının engellemeye yeniden izin vermesi gerekir. ASR kuralları için uyarı modu yalnızca RS5+ (1809+) cihazlarda desteklenir. Eski sürümleri olan cihazlarda ASR kurallarına atlama atanırsa, kural engellenmiş modda olur.

Ayrıca, AttackSurfaceReductionRules_Actions "Uyar" olarak belirterek PowerShell aracılığıyla uyarı modunda bir kural ayarlayabilirsiniz. Örneğin:

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>Kural açıklamaları başına

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi

Bu kural, bir uygulamanın diske güvenlik açığı bulunan imzalı bir sürücü yazmasını engeller. Çekirdek erişimi elde etmek için _yeterli ayrıcalığı olan_ yerel uygulamalar\-, vahşi kullanıma açık, güvenlik açığı bulunan imzalı sürücülerden \- yararlanabilir. Güvenlik açığı bulunan imzalı sürücüler, saldırganların güvenlik çözümlerini devre dışı bırakmasına veya aşmasına olanak tanır ve sonunda sistem güvenliğinin aşılmasına neden olur.

**Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılmasına** engel olun kuralı, sistemde zaten var olan bir sürücünün yüklenmesini engellemez.

> [!NOTE]
>
> Bu kuralı MEM OMA-URI kullanarak yapılandırabilirsiniz. Özel kuralları yapılandırmak için bkz. [MEM OMA-URI](enable-attack-surface-reduction.md#mem) .
>
> Bu kuralı [PowerShell](enable-attack-surface-reduction.md#powershell) kullanarak da yapılandırabilirsiniz.
>
> Bir sürücünün incelenmesini sağlamak için bu Web sitesini kullanarak [Analiz için bir sürücü gönderin](https://www.microsoft.com/en-us/wdsi/driversubmission).

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

Intune Adı:`Block abuse of exploited vulnerable signed drivers`

Configuration Manager adı: Henüz kullanılamıyor
  
GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

Gelişmiş tehdit avcılığı eylem türü:

- AsrVulnerableSignedDriverAudited
- AsrVulnerableSignedDriverBlocked

<!-- 
Dependencies: none provided by engineering
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader'ın alt işlemler oluşturmalarını engelleme

Bu kural, Adobe Reader'ın işlem oluşturmasını engelleyerek saldırıları engeller.

Kötü amaçlı yazılımlar, sosyal mühendislik veya açıklardan yararlanarak adobe reader'ın yüklerini indirip başlatabilir ve bu yükten kurtulabilir. Alt işlemlerin Adobe Reader tarafından oluşturulması engellenerek, Adobe Reader'ı saldırı vektöru olarak kullanmaya çalışan kötü amaçlı yazılımların yayılması engellenir.

Intune adı:`Process creation from Adobe Reader (beta)`

Configuration Manager adı: Henüz kullanılamıyor

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

Gelişmiş tehdit avcılığı eylem türü:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-all-office-applications-from-creating-child-processes"></a>Tüm Office uygulamalarının alt işlemler oluşturmalarını engelleme

Bu kural, Office uygulamalarının alt işlemler oluşturmalarını engeller. Office uygulamaları Word, Excel, PowerPoint, OneNote ve Access'i içerir.

Kötü amaçlı alt işlemler oluşturmak yaygın bir kötü amaçlı yazılım stratejisidir. Vektör olarak Office'i kötüye kullanan kötü amaçlı yazılımlar genellikle VBA makroları çalıştırır ve daha fazla yük indirip çalıştırmaya çalışmak için koddan yararlanılır. Ancak bazı meşru iş kolu uygulamaları da zararsız amaçlarla alt süreçler oluşturabilir; örneğin, bir komut istemi oluşturma veya powershell kullanarak kayıt defteri ayarlarını yapılandırma.

Intune adı:`Office apps launching child processes`

Configuration Manager adı:`Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

Gelişmiş tehdit avcılığı eylem türü:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgilerinin çalınmalarını engelleme

Bu kural, Yerel Güvenlik Yetkilisi Alt Sistem Hizmeti'ni (LSASS) kilitleyerek kimlik bilgilerinin çalınmasını önlemeye yardımcı olur.

LSASS, Windows bilgisayarında oturum açan kullanıcıların kimliğini doğrular. Windows'da Credential Guard Microsoft Defender normalde LSASS'den kimlik bilgilerini ayıklama girişimlerini engeller. Bazı kuruluşlar, özel akıllı kart sürücüleri veya Yerel Güvenlik Yetkilisi'ne (LSA) yüklenen diğer programlarla ilgili uyumluluk sorunları nedeniyle Credential Guard'ı tüm bilgisayarlarında etkinleştiremiyor. Bu gibi durumlarda saldırganlar, Cleartext parolalarını ve LSASS'den NTLM karmalarını kazımak için Mimikatz gibi araçları kullanabilir.

> [!NOTE]
> Bazı uygulamalarda kod, çalışan tüm işlemleri numaralandırır ve bunları kapsamlı izinlerle açmaya çalışır. Bu kural, uygulamanın işlem açma eylemini reddeder ve ayrıntıları güvenlik olay günlüğüne kaydeder. Bu kural çok fazla gürültü oluşturabilir. LSASS'yi numaralandıran ancak işlevsellikte gerçek bir etkisi olmayan bir uygulamanız varsa, bunu dışlama listesine eklemeniz gerekmez. Bu olay günlüğü girdisi tek başına kötü amaçlı bir tehdit anlamına gelmez.
  
> [!IMPORTANT]
> Saldırı Yüzeyi Azaltma (ASR) kuralının "Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınması engellenir" varsayılan durumu **Yapılandırılmadı** **olarak, varsayılan** mod ise **Engelle** olarak ayarlanır. Diğer tüm ASR kuralları varsayılan durumunda kalır: **Yapılandırılmadı**. Son kullanıcı bildirimlerini azaltmak için kurala ek filtreleme mantığı zaten eklenmiştir. Müşteriler kuralı **Denetim**, **Uyarı** veya **Devre Dışı** modları olarak yapılandırabilir ve bu da varsayılan modu geçersiz kılar. Kuralın varsayılan modda yapılandırılması veya Engelleme modunu el ile etkinleştirmeniz fark etmeksizin, bu kuralın işlevselliği aynıdır.

Intune adı:`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager adı:`Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

Gelişmiş tehdit avcılığı eylem türü:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-executable-content-from-email-client-and-webmail"></a>E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleme

Bu kural, aşağıdaki dosya türlerinin Microsoft Outlook uygulamasında açılan e-postadan veya Outlook.com ve diğer popüler web postası sağlayıcılarından başlatılmasını engeller:

- Yürütülebilir dosyalar (.exe, .dll veya .scr gibi)
- Betik dosyaları (PowerShell .ps1, Visual Basic .vbs veya JavaScript .js dosyası gibi)

Intune adı:`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager adı: `Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

Gelişmiş tehdit avcılığı eylem türü:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

> [!NOTE]
> **E-posta istemcisinden ve web postasından yürütülebilir içeriği engelle** kuralı, hangi uygulamayı kullandığınıza bağlı olarak aşağıdaki alternatif açıklamalara sahiptir:
>
> - Intune (Yapılandırma Profilleri): E-postadan bırakılan yürütülebilir içeriğin (exe, dll, ps, js, vbs vb.) yürütülmesi (özel durum yok).
> - Endpoint Manager: E-posta ve web postası istemcilerinden yürütülebilir içerik indirmeyi engelleyin.
> - grup ilkesi: E-posta istemcisinden ve web postasından yürütülebilir içeriği engelleyin.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Bir yaygınlık, yaş veya güvenilir liste ölçütüne uymadığı sürece yürütülebilir dosyaların çalışmasını engelleyin

Bu kural, .exe, .dll veya .scr gibi yürütülebilir dosyaların başlatılmasını engeller. Bu nedenle, güvenilmeyen veya bilinmeyen yürütülebilir dosyaların başlatılması riskli olabilir, bu nedenle dosyaların kötü amaçlı olup olmadığı başlangıçta net olmayabilir.

> [!IMPORTANT]
> Bu kuralı kullanmak için [bulut tabanlı korumayı etkinleştirmeniz](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) gerekir.
>
> GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` ile bir **yaygınlık, yaş veya güvenilir liste ölçütüne uymadıkları sürece yürütülebilir dosyaların çalışmasını engelle** kuralı Microsoft'a aittir ve yöneticiler tarafından belirtilmez. Bu kural, güvenilir listesini düzenli olarak güncelleştirmek için bulut tabanlı koruma kullanır.
>
> Tek tek dosyaları veya klasörleri (klasör yollarını veya tam kaynak adlarını kullanarak) belirtebilirsiniz, ancak hangi kuralların veya dışlamaların uygulanacağını belirtemezsiniz.

Intune adı:`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager adı:`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

Gelişmiş tehdit avcılığı eylem türü:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, Bulut Koruması

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Karartılmış olabilecek betiklerin yürütülmesini engelleme

Bu kural, belirsiz bir betik içindeki şüpheli özellikleri algılar.
  
> [!IMPORTANT]
> PowerShell betikleri, geçmişte karşılaşılan büyük ölçekli FP sorunları nedeniyle geçici olarak "Belirsiz olabilecek betiklerin yürütülmesini engelle" kuralının dışında bırakılmıştır.

Betik karartma, hem kötü amaçlı yazılım yazarlarının hem de yasal uygulamaların fikri mülkiyeti gizlemek veya betik yükleme sürelerini azaltmak için kullandığı yaygın bir tekniktir. Kötü amaçlı yazılım yazarları, kötü amaçlı kodları okumayı zorlaştırmak için de karartma kullanır ve bu da insanlar ve güvenlik yazılımları tarafından yakından incelemeyi engeller.

> [!IMPORTANT]
> Çok sayıda hatalı pozitif sonuç nedeniyle bu kural şu anda PowerShell betiklerini algılamaz; bu geçici bir çözümdür. Kural güncelleştirilecek ve yakında PowerShell betiklerini yeniden algılamaya başlayacaktır.

Intune adı:`Obfuscated js/vbs/ps/macro code`

Configuration Manager adı:`Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

Gelişmiş tehdit avcılığı eylem türü:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, Kötü Amaçlı Yazılımdan Koruma Tarama Arabirimi (AMSI)

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript veya VBScript'in indirilen yürütülebilir içeriği başlatmasını engelleme

Bu kural betiklerin kötü amaçlı olabilecek indirilen içeriği başlatmasını engeller. JavaScript veya VBScript ile yazılan kötü amaçlı yazılımlar genellikle İnternet'ten başka kötü amaçlı yazılımları getirmek ve başlatmak için bir indirici görevi görür.

Yaygın olmasa da, iş kolu uygulamaları bazen yükleyicileri indirmek ve başlatmak için betikler kullanır.

Intune adı:`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager adı:`Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

Gelişmiş tehdit avcılığı eylem türü:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>Office uygulamalarının yürütülebilir içerik oluşturmalarını engelleme

Bu kural, Word, Excel ve PowerPoint gibi Office uygulamalarının, kötü amaçlı kodun diske yazılmasını engelleyerek kötü amaçlı olabilecek yürütülebilir içerik oluşturmasını engeller.

Vektör olarak Office'i kötüye kullanan kötü amaçlı yazılımlar, Office'in dışına çıkıp kötü amaçlı bileşenleri diske kaydetmeye çalışabilir. Bu kötü amaçlı bileşenler bilgisayarın yeniden başlatılmasından ve sistemde kalıcı hale getirir. Bu nedenle, bu kural ortak bir kalıcılık tekniğine karşı savunur.

Intune adı:`Office apps/macros creating executable content`

SCCM adı: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

Gelişmiş tehdit avcılığı eylem türü:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Office uygulamalarının diğer işlemlere kod eklemesini engelleme

Bu kural, Office uygulamalarından diğer işlemlere kod ekleme girişimlerini engeller.

Saldırganlar, kötü amaçlı kodu kod ekleme yoluyla diğer işlemlere geçirmek için Office uygulamalarını kullanmayı deneyerek kodun temiz bir işlem olarak gizlenmesini sağlayabilir.

Kod ekleme kullanmanın bilinen meşru iş amaçları yoktur.

Bu kural Word, Excel ve PowerPoint için geçerlidir.

Intune adı:`Office apps injecting code into other processes (no exceptions)`

Configuration Manager adı:`Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

Gelişmiş tehdit avcılığı eylem türü:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-office-communication-application-from-creating-child-processes"></a>Office iletişim uygulamasının alt işlemler oluşturmalarını engelleme

Bu kural, Outlook'un alt işlemler oluşturmasını engellerken, geçerli Outlook işlevlerine de izin verir.

Bu kural sosyal mühendislik saldırılarına karşı koruma sağlar ve Kodun Outlook'taki güvenlik açıklarını kötüye kullanmasını önler. Ayrıca, bir kullanıcının kimlik bilgileri tehlikeye atıldığında saldırganların kullanabileceği [Outlook kurallarına ve biçim açıklarına](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) karşı koruma sağlar.

> [!NOTE]
> Bu kural, Outlook'ta DLP ilkesi ipuçlarını ve Araç İpuçlarını engeller. Bu kural yalnızca Outlook ve Outlook.com için geçerlidir.

Intune adı:`Process creation from Office communication products (beta)`

Configuration Manager adı: Kullanılamıyor

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

Gelişmiş tehdit avcılığı eylem türü:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI olay aboneliği aracılığıyla kalıcılığı engelleme

Bu kural, kötü amaçlı yazılımların cihazda kalıcılık elde etmek için WMI'yi kötüye çalışmasını önler.

> [!IMPORTANT]
> Dosya ve klasör dışlamaları bu saldırı yüzeyi azaltma kuralı için geçerli değildir.

Dosyasız tehditler, gizli kalmak, dosya sisteminde görülmemek ve düzenli yürütme denetimi elde etmek için çeşitli taktikler uygular. Bazı tehditler, gizli kalmak için WMI deposunu ve olay modelini kötüye kullanabilir.

Intune adı: Kullanılamıyor

Configuration Manager adı: Kullanılamıyor

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

Gelişmiş tehdit avcılığı eylem türü:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec ve WMI komutlarından kaynaklanan işlem oluşturma işlemlerini engelleme

Bu kural [, PsExec](/sysinternals/downloads/psexec) ve [WMI](/windows/win32/wmisdk/about-wmi) aracılığıyla oluşturulan işlemlerin çalışmasını engeller. Hem PsExec hem de WMI uzaktan kod yürütebilir. PsExec ve WMI'nin komut ve denetim amacıyla işlevselliğini kötüye kullanma veya kuruluşun ağına bulaşma riski vardır.

> [!WARNING]
> Bu kuralı yalnızca cihazlarınızı [Intune](/intune) veya başka bir MDM çözümüyle yönetiyorsanız kullanın. Bu kural, Configuration Manager istemcisinin düzgün çalışması için kullandığı WMI komutlarını engellediğinden, bu kural [Microsoft Endpoint](/configmgr) Configuration Manager aracılığıyla yönetimle uyumsuzdur.

Intune adı:`Process creation from PSExec and WMI commands`

Configuration Manager adı: Geçerli değil

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

Gelişmiş tehdit avcılığı eylem türü:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB'den çalıştırılan güvenilmeyen ve imzalanmamış işlemleri engelleme

Bu kuralla, yöneticiler imzalanmamış veya güvenilmeyen yürütülebilir dosyaların SD kartlar da dahil olmak üzere USB çıkarılabilir sürücülerden çalıştırılmasını engelleyebilir. Engellenen dosya türleri yürütülebilir dosyaları (.exe, .dll veya .scr gibi) içerir

> [!IMPORTANT]
> USB'den disk sürücüsüne kopyalanan dosyalar, disk sürücüsünde yürütülmek üzereyse ve yürütülmek üzere olduğunda bu kural tarafından engellenir.

Intune adı:`Untrusted and unsigned processes that run from USB`

Configuration Manager adı:`Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

Gelişmiş tehdit avcılığı eylem türü:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma

### <a name="block-win32-api-calls-from-office-macros"></a>Office makrolarından Win32 API çağrılarını engelleme

Bu kural VBA makrolarının Win32 API'lerini çağırmasını engeller.

Office VBA, Win32 API çağrılarını etkinleştirir. Kötü amaçlı yazılımlar, doğrudan diske hiçbir şey yazmadan [kötü amaçlı kabuk kodu başlatmak için Win32 API'lerini çağırmak](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) gibi bu özelliği kötüye kullanabilir. Çoğu kuruluş, makroları başka şekillerde kullansalar bile günlük çalışmalarında Win32 API'lerini çağırma özelliğine güvenmez.

Desteklenen işletim sistemleri:

- [Windows 10, sürüm 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, sürüm 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune adı:`Win32 imports from Office macro code`

Configuration Manager adı:`Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

Gelişmiş tehdit avcılığı eylem türü:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, AMSI

### <a name="use-advanced-protection-against-ransomware"></a>Fidye yazılımına karşı gelişmiş koruma kullanma

Bu kural fidye yazılımlarına karşı ek bir koruma katmanı sağlar. Bir dosyanın fidye yazılımına benzeip benzemediğini belirlemek için hem istemci hem de bulut buluşsal yöntemleri kullanır. Bu kural, aşağıdaki özelliklerden birine veya daha fazlasına sahip dosyaları engellemez:

- Dosya, Microsoft bulutunda zaten zarar görmemiş olarak bulundu.
- Dosya geçerli bir imzalı dosyadır.
- Dosya fidye yazılımı olarak kabul edilmeyecek kadar yaygındır.

Kural, fidye yazılımlarını önlemek için dikkatli olma eğilimindedir.

> [!NOTE]
> Bu kuralı kullanmak için [bulut tabanlı korumayı etkinleştirmeniz](enable-cloud-protection-microsoft-defender-antivirus.md) gerekir.

Intune adı:`Advanced ransomware protection`

Configuration Manager adı:`Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

Gelişmiş tehdit avcılığı eylem türü:

- AsrRansomwareAudited
- AsrRansomwareBlocked

Bağımlılıklar: Microsoft Defender Virüsten Koruma, Bulut Koruması

## <a name="see-also"></a>Ayrıca bkz.

- [Saldırı yüzeyini azaltma (ASR) kuralları dağıtımına genel bakış](attack-surface-reduction-rules-deployment.md)
- [Saldırı yüzeyini azaltma (ASR) kuralları dağıtım planı](attack-surface-reduction-rules-deployment-plan.md)
- [Saldırı yüzeyini azaltma (ASR) kuralları testi](attack-surface-reduction-rules-deployment-test.md)
- [Saldırı yüzeyini azaltma (ASR) kurallarını etkinleştirme](attack-surface-reduction-rules-deployment-implement.md)
- [Saldırı yüzeyini azaltma (ASR) kurallarını kullanıma hazır hale getirme](attack-surface-reduction-rules-deployment-operationalize.md)
- [Saldırı yüzeyi azaltma \(ASR\) kuralları raporu](attack-surface-reduction-rules-report.md)
- [Saldırı yüzeyi azaltma kuralları başvurusu](attack-surface-reduction-rules-reference.md)
