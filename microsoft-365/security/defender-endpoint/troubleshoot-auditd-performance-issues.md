---
title: Linux'ta Uç Nokta için Microsoft Defender ile ilgili Denetimli performans sorunlarını giderme
ms.reviewer: ''
description: Linux için Microsoft Defender karşılaşabileceğiniz AuditD ile ilgili performans sorunlarının nasıl giderildiğini açıklar.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, sorun giderme, AuditD, XMDEClientAnalyzer, yükleme, dağıtma, kaldırma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7d5056470331bc52318ca4a5e433edbe37cabf03
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68337320"
---
# <a name="troubleshoot-auditd-performance-issues-with-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender ile ilgili Denetimli performans sorunlarını giderme 

Bu makale, Linux'ta Uç Nokta için Microsoft Defender karşılaşabileceğiniz AuditD ile ilgili performans sorunlarını giderme konusunda rehberlik sağlar. 

**Arka plan:** 

- Linux işletim sistemi dağıtımlarında Uç Nokta için Microsoft Defender, belirli türlerdeki telemetri olaylarını toplamak için AuditD çerçevesini kullanır. 

- 'a `/etc/audit/rules.d/` eklenen kurallar tarafından yakalanan sistem olayları audit.log'lara eklenir ve konak denetimini ve yukarı akış koleksiyonunu etkileyebilir.  

- Linux'ta Uç Nokta için Microsoft Defender tarafından eklenen olaylar anahtarla `mdatp` etiketlenir. 

- AuditD hizmeti yanlış yapılandırılmış veya çevrimdışıysa, bazı olaylar eksik olabilir. Böyle bir sorunu gidermek için bkz. [Linux'ta Uç Nokta için Microsoft Defender için eksik olayları veya uyarı sorunlarını giderme.](linux-support-events.md)

Bazı sunucu iş yüklerinde iki sorun gözlemlenebilir: 

- **_mdatp_audisp_plugin_** işlemden **yüksek CPU** kaynak tüketimi. 

- ***/var/log/audit/audit.log*** büyük veya sık sık dönüyor. 

Bu sorunlar, AuditD'yi basan birçok olayı olan sunucularda oluşabilir.  

AuditD için birden çok tüketici veya Uç Nokta için Microsoft Defender ve üçüncü taraf tüketicilerin birleşimiyle çok fazla kural veya çok fazla olay oluşturan yüksek iş yükü varsa bu durum oluşabilir. 

Bu tür sorunları gidermek için, etkilenen örnek sunucuda [MDEClientAnalyzer günlüklerini toplayarak](run-analyzer-macos-linux.md) başlayın. 

> [!NOTE]
> Genel bir en iyi uygulama olarak, [Uç Nokta için Microsoft Defender aracısını en son kullanılabilir sürüme](linux-whatsnew.md) güncelleştirmeniz ve daha fazla araştırma yapmadan önce sorunun devam edip etmediğini onaylamanız önerilir.

> [!NOTE]
> AuditD alt sistem CPU zorluğunu etkileyebilecek ek yapılandırmalar olduğunu. <BR>
> Özellikle [auditd.conf](https://linux.die.net/man/8/auditd.conf) dosyasında yüksek CPU tüketimini azaltmak için **disp_qos** değeri "kayıplı" olarak ayarlanabilir. <BR>
> Ancak bu, yoğun CPU tüketimi sırasında bazı olayların bırakılabileceği anlamına gelir. <BR>

## <a name="xmdeclientanalyzer"></a>XMDEClientAnalyzer 

[XMDEClientAnalyzer](run-analyzer-macos-linux.md) kullandığınızda, aşağıdaki dosyalar sorunları gidermenize yardımcı olacak içgörüler sağlayan bir çıktı görüntüler.
- auditd_info.txt
- auditd_log_analysis.txt


### <a name="auditd_infotxt"></a>auditd_info.txt

Genel AuditD yapılandırmasını içerir ve şunları görüntüler:

- Hangi işlemlerin AuditD tüketicileri olarak kaydedildiği. 

- **Enabled=2** ile **Auditctl -s** çıkışı  

    - Denetlenenlerin sabit modda olduğunu önerir (yapılandırma değişikliklerinin etkili olması için yeniden başlatma gerektirir). 

- **Auditctl -l** çıkışı  

    - Şu anda çekirdeğe hangi kuralların yüklendiğini gösterir (diskteki "/etc/auditd/rules.d/mdatp.rules" içinde bulunan kurallar farklı olabilir). 
    
    - hangi kuralların Uç Nokta için Microsoft Defender ile ilişkili olduğunu gösterir. 
    
### <a name="auditd_log_analysistxt"></a>auditd_log_analysis.txt

Denetimli performans sorunlarını araştırırken yararlı olan önemli toplu bilgiler içerir.  

- En çok bildirilen olayların sahibi hangi bileşendir (Uç Nokta için Microsoft Defender olaylar ile `key=mdatp`etiketlenir). 

- En iyi raporlama başlatıcıları. 

- En yaygın sistem çağrıları (ağ veya dosya sistemi olayları ve diğerleri). 

- En gürültülü dosya sistemi yollarıdır. 

**Çoğu Denetimli performans sorununu azaltmak için Denetimli dışlama uygulayabilirsiniz. **

> [!NOTE]
> Dışlamalar yalnızca düşük tehdit ve yüksek kirlilik başlatıcıları veya yolları için yapılmalıdır. Örneğin, büyük bir kör nokta oluşturma riski taşıyan /bin/bash'i hariç tutmayın.
> [Dışlamaları tanımlarken kaçınılması gereken yaygın hatalar](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus).



## <a name="exclusion-types"></a>Dışlama Türleri 

XMDEClientAnalyzer destek aracı, AuditD dışlama yapılandırma kurallarını eklemek için kullanılabilecek söz dizimi içerir: 

AuditD dışlama – destek aracı söz dizimi yardımı:

:::image type="content" source="images/auditd-exclusion-support-tool-syntax-help.png" alt-text="AuditD dışlama yapılandırma kuralları eklemek için kullanılabilecek söz dizimi" lightbox="images/auditd-exclusion-support-tool-syntax-help.png":::

**Başlatıcı tarafından** 

- **-e/ -exe** tam ikili yolu > Bu başlatıcı tarafından tüm olayları kaldırır 

**Yola göre** 

- **-d / -dir** dizinin tam yolu > Bu dizini hedefleyen dosya sistemi olaylarını kaldırır 

Örnekler: 

"`/opt/app/bin/app`" ifadesi "`/opt/app/cfg/logs/1234.log`" olarak yazılırsa, çeşitli seçeneklerle dışlamak için destek aracını kullanabilirsiniz: 

`-e /opt/app/bin/app`

`-d /opt/app/cfg`

`-x /usr/bin/python /etc/usercfg` 

`-d /usr/app/bin/`

Diğer örnekler: 

`./mde_support_tool.sh exclude -p <process id>`

`./mde_support_tool.sh exclude -e <process name>`

Birden fazla öğeyi dışlamak için dışlamaları tek bir satırda birleştirin: 

`./mde_support_tool.sh exclude -e <process name> -e <process name 2> -e <process name3>`
 
-x bayrağı, belirli başlatıcılar tarafından alt dizinlere erişimi dışlamak için kullanılır, örneğin: 

`./mde_support_tool.sh exclude -x /usr/sbin/mv /tmp`

Yukarıdakiler, mv işlemi tarafından erişildiğinde /tmp alt klasörünün izlenmesini dışlar. 

 
> [!NOTE]
> AuditD ile ilgili performans sorunlarını analiz etme ve azaltma veya Denetimli dışlamaları büyük ölçekte dağıtma konusunda yardıma ihtiyacınız varsa lütfen Microsoft desteğine başvurun. 


