---
title: Windows'da Uç Nokta için Microsoft Defender'deki yenilikler
description: Windows İstemcisi ve Sunucusu'nda Uç Nokta için Microsoft Defender en son özellik sürümleri hakkında bilgi edinin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, windows, windows istemcisi, windows server, yenilikler
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: v-mathavale
author: v-mathavale
ms.localizationpriority: medium
ms.date: 09/20/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: reference
ms.subservice: mde
ms.openlocfilehash: 90e5ab9fec1c6c8663f493ee9c9135ffbe33daa2
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68334856"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-windows"></a>Windows'da Uç Nokta için Microsoft Defender'deki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Tüm güncelleştirmeler şu içeriği içerir:
- Performans geliştirmeleri
- Hizmet verilebilirlik iyileştirmeleri
- Tümleştirme geliştirmeleri (Bulut, [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804))

<details>
  <summary>Ağustos 2022 (Sürüm: 10.8210.*)</summary>

|Os  |Kb  |Sürüm sürümü  |
|---------|---------|---------|
|Windows Server 2012 R2, 2016 |[KB 5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)|10.8210.22621.1011|
|Windows 11 21H2 (Kobalt)<br> (Windows 11 SV 21H2)     | [KB 5016691](https://support.microsoft.com/en-us/topic/august-25-2022-kb5016691-os-build-22000-918-preview-59097044-915a-49a0-8870-49823236adbd)        | 10.8210.22000.918        |
|Server 2022 (Demir)     | [KB 5016693](https://support.microsoft.com/en-us/topic/august-16-2022-kb5016693-os-build-20348-946-preview-ee90d0bc-c162-4124-b7c6-f963ee7b17ed)        |10.8210.20348.946         |
|Windows 10 20H2/21H1/21H2<br> Windows Server 20H2 (Vibranium)     | [KB 5016688](https://support.microsoft.com/en-us/topic/august-26-2022-kb5016688-os-builds-19042-1949-19043-1949-and-19044-1949-preview-ec31ebdc-067d-44dd-beb0-eabcc984d843)       | 10.8210.19041.1949        |
|Windows Server 2019 (RS5)   |[KB 5016690](https://support.microsoft.com/en-us/topic/august-23-2022-kb5016690-os-build-17763-3346-preview-b81d1ac5-75c7-42c1-b638-f13aa4242f42)       |10.8210.17763.3346         |

**Yenilikler**

- Birleşik aracıyı çalıştıran Windows Server 2012 R2 üzerinde "TelemetryProxyServer" kullanımıyla ilgili eksik bir ara sertifika sorununu çözmek için bir düzeltme eklendi.
- Etiket dosyalarını değil parola korumalı ve şifrelenmiş dosyaları koruma özelliğine sahip gelişmiş Uç Nokta DLP...
- Denetim telemetrisindeki bağlam verileri desteğiyle gelişmiş Uç Nokta DLP'leri (kısa kanıt).
- VDI cihazları için geliştirilmiş Uç Nokta için Microsoft Defender istemci kimlik doğrulaması desteği.
- Gelişmiş Uç Nokta için Microsoft Defender fidye yazılımlarını ve gelişmiş saldırıları tanımlama ve engelleme yeteneği.
- İçerir özelliği artık daha fazla masaüstü ve sunucu sürümünü destekleyip İçeri aktarma eylemini gerçekleştiriyor ve bunlar içerildiğinde bulunan cihazları engelliyor.
- Sorun giderme modu özelliği ek masaüstü ve sunucu sürümlerine genişletildi. Desteklenen işletim sistemi sürümlerinin tam listesi ve önkoşullar hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender sorun giderme modunu kullanmaya başlama](enable-troubleshooting-mode.md).
- Canlı Yanıt iyileştirmeleri ara sunucuları kullanırken oturum oluşturma gecikme süresini azaltmayı, düzeltmeyi geri alma el ile komutunu, FindFile eyleminde OneDrive paylaşımı desteğini ve iyileştirilmiş yalıtım ve kararlılığı içerir.
- [Uç Nokta için Microsoft Defender için Güvenlik Yönetimi](security-config-management.md#configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management) artık belirli bir tempoyu beklemek yerine cihaz yapılandırmasını isteğe bağlı olarak eşitleme olanağı sağlar.

 > [!NOTE] 
 > KB5005292 güncelleştirme paketi, Windows Update boyunca aşamalı bir dağıtım zamanlaması üzerindedir. Bu zamanlamanın sonuna doğru paket, el ile indirme için güncelleştirme kataloğu da dahil olmak üzere tamamen yayımlanacaktır. Geçerli sürüm için bu, Ekim ayının ikinci yarısında olacaktır. Paketi daha erken test etmek istiyorsanız, Önizleme kanalını seçmek [için platform güncelleştirmeleri için aşamalı dağıtım denetimlerini](configure-updates.md) kullanabilirsiniz.
  
<br/>
</details>

Ayrıca bkz: 
- [Uç Nokta için Microsoft Defender'deki yenilikler](whats-new-in-microsoft-defender-endpoint.md)
- [macOS'ta Uç Nokta için Defender'daki yenilikler](mac-whatsnew.md)
- [iOS'ta Uç Nokta için Defender'daki yenilikler](ios-whatsnew.md)
- [Linux'ta Uç Nokta için Defender'daki yenilikler](linux-whatsnew.md)
