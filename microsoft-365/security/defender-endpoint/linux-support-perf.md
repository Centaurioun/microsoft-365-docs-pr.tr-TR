---
title: Linux'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme
description: Linux'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, performans
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
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: b44046600d72955fee57d4be343460c53fe7754f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686392"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Bu belgede, mevcut kaynak yetersizliklerini ve sistemi bu tür durumlara dönüştüren işlemleri anlamak ve azaltmak için kullanılabilir tanılama araçlarını kullanarak Linux'ta Uç Nokta için Defender ile ilgili performans sorunlarının nasıl daraltılacağına ilişkin yönergeler sağlanır. Performans sorunları, sistemdeki kaynak kullanımı profiline bağlı olarak bir veya daha fazla donanım alt sistemindeki performans sorunlarına neden olur. Bazen uygulamalar disk G/Ç kaynaklarına duyarlıdır ve daha fazla CPU kapasitesine ihtiyaç duyar ve bazen bazı yapılandırmalar sürdürülebilir değildir ve çok fazla yeni işlem tetikleyebilir ve çok fazla dosya tanımlayıcısı açabilir.

Çalıştırdığınız uygulamalara ve cihazınızın özelliklerine bağlı olarak, Linux'ta Uç Nokta için Defender'ı çalıştırırken en iyi performansın altında bir performansla karşılaşabilirsiniz. Özellikle CPU, Disk ve Bellek gibi birçok kaynağa kısa bir zaman aralığı boyunca erişen uygulamalar veya sistem işlemleri Linux üzerinde Uç Nokta için Defender'da performans sorunlarına yol açabilir.

> [!WARNING]
> Başlamadan önce **lütfen cihazda şu anda diğer güvenlik ürünlerinin çalışmadığından emin olun**. Birden çok güvenlik ürünü çakışabilir ve konak performansını etkileyebilir.

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>Gerçek Zamanlı Koruma İstatistiklerini kullanarak performans sorunlarını giderme

**Şunlar için geçerlidir:**
- Yalnızca AV ile ilgili performans sorunları

Gerçek zamanlı koruma (RTP), Linux'ta cihazınızı sürekli izleyen ve tehditlere karşı koruyan bir Uç Nokta için Defender özelliğidir. Dosya ve süreç izleme ve diğer buluşsal yöntemlerden oluşur.

Bu sorunları gidermek ve azaltmak için aşağıdaki adımlar kullanılabilir:

1. Aşağıdaki yöntemlerden birini kullanarak gerçek zamanlı korumayı devre dışı bırakın ve performansın iyileşip iyileşmediğini gözlemleyin. Bu yaklaşım, Linux'ta Uç Nokta için Defender'ın performans sorunlarına katkıda bulunup bulunmadığını daraltmaya yardımcı olur.

    Cihazınız kuruluşunuz tarafından yönetilmiyorsa, gerçek zamanlı koruma komut satırından devre dışı bırakılabilir:

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    Cihazınız kuruluşunuz tarafından yönetiliyorsa, [Linux'ta Uç Nokta için Defender tercihlerini ayarlama](linux-preferences.md) başlığı altındaki yönergeler kullanılarak gerçek zamanlı koruma yöneticiniz tarafından devre dışı bırakılabilir.

    > [!NOTE]
    > Gerçek zamanlı koruma kapalıyken performans sorunu devam ederse, sorunun kaynağı uç nokta algılama ve yanıt (EDR) bileşeni olabilir. Bu durumda lütfen bu makalenin **Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'ni kullanarak performans sorunlarını giderme** bölümündeki adımları izleyin.

2. En çok taramayı tetikleyen uygulamaları bulmak için, Linux'ta Uç Nokta için Defender tarafından toplanan gerçek zamanlı istatistikleri kullanabilirsiniz.

    > [!NOTE]
    > Bu özellik 100.90.70 veya daha yeni sürümlerde kullanılabilir.

    Bu özellik ve `InsiderFast` kanallarında `Dogfood` varsayılan olarak etkindir. Farklı bir güncelleştirme kanalı kullanıyorsanız, bu özellik komut satırından etkinleştirilebilir:

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Bu özelliğin etkinleştirilmesi için gerçek zamanlı koruma gerekir. Gerçek zamanlı korumanın durumunu denetlemek için aşağıdaki komutu çalıştırın:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Girdinin `real_time_protection_enabled` olduğunu `true`doğrulayın. Aksi takdirde, etkinleştirmek için aşağıdaki komutu çalıştırın:

    ```bash
    mdatp config real-time-protection --value enabled
    ```

    ```Output
    Configuration property updated
    ```

    Geçerli istatistikleri toplamak için şunu çalıştırın:

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > Kullanmak ```--output json``` (çift çizgiye dikkat edin), çıkış biçiminin ayrıştırma için hazır olmasını sağlar.

    Bu komutun çıkışı tüm işlemleri ve bunların ilişkili tarama etkinliğini gösterir.

3. Linux sisteminizde şu komutu kullanarak örnek Python ayrıştırıcısını **high_cpu_parser.py** indirin:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    Bu komutun çıkışı aşağıdakine benzer olmalıdır:


    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. Ardından, aşağıdaki komutları yazın:

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      Yukarıdaki çıkışı, performans sorunlarına en çok katkıda bulunanların listesidir. İlk sütun işlem tanımlayıcısı (PID), ikinci sütun işlem adı ve son sütun ise etkilenen öğeye göre sıralanmış taranan dosyaların sayısıdır.
    Örneğin, komutun çıkışı aşağıdakine benzer olacaktır: 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool    1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd     407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    Linux'ta Uç Nokta için Defender'ın performansını geliştirmek için satırın altında `Total files scanned` en yüksek sayıya sahip olanı bulun ve bunun için bir dışlama ekleyin. Daha fazla bilgi için bkz. [Linux'ta Uç Nokta için Defender dışlamalarını yapılandırma ve doğrulama](linux-exclusions.md).

    > [!NOTE]
    > Uygulama istatistiği bellekte depolar ve yalnızca başlatıldığından ve gerçek zamanlı koruma etkinleştirildiğinden beri dosya etkinliğini izler. Gerçek zamanlı korumanın kapalı olduğu dönemlerde veya öncesinde başlatılan işlemler sayılmaz. Ayrıca, yalnızca taramaları tetikleyen olaylar sayılır.

5. Performans sorunlarına katkıda bulunan işlemler veya disk konumları için dışlamalarla Linux'ta Uç Nokta için Microsoft Defender yapılandırın ve gerçek zamanlı korumayı yeniden etkinleştirin.

    Daha fazla bilgi için bkz. [Linux'ta Uç Nokta için Microsoft Defender dışlamaları yapılandırma ve doğrulama](linux-exclusions.md).

## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'ni kullanarak performans sorunlarını giderme


**Şunlar için geçerlidir:**
- AV ve EDR gibi kullanılabilir tüm Uç Nokta için Defender bileşenlerinin performans sorunları  

Uç Nokta için Microsoft Defender İstemci Çözümleyicisi (MDECA), macOS'ta [eklenen cihazlardaki](/microsoft-365/security/defender-endpoint/onboard-configure) performans sorunlarını gidermek için izlemeleri, günlükleri ve tanılama bilgilerini toplayabilir.

> [!NOTE]
>- Uç Nokta için Microsoft Defender İstemci Çözümleyicisi aracı, Microsoft Müşteri Destek Hizmetleri (CSS) tarafından ip adresleri, Uç Nokta için Microsoft Defender karşılaşabileceğiniz sorunları gidermeye yardımcı olacak bilgisayar adları gibi bilgileri toplamak için düzenli olarak kullanılır. Gizlilik bildirimimiz hakkında daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://privacy.microsoft.com/privacystatement).
>- Genel bir en iyi uygulama olarak, [Uç Nokta için Microsoft Defender aracısını  en son kullanılabilir sürüme](mac-whatsnew.md)  güncelleştirmeniz ve daha fazla araştırma yapmadan önce sorunun hala devam ettiğini onaylamanız önerilir. 

Performans sorunlarını gidermek üzere istemci çözümleyicisini çalıştırmak için bkz. [macOS ve Linux üzerinde istemci çözümleyicisini çalıştırma](run-analyzer-macos-linux.md).

>[!NOTE]
>Yukarıdaki adımların ardından performans sorununun devam etmesi durumunda, daha fazla yönerge ve risk azaltma için lütfen müşteri desteğine başvurun. 

## <a name="see-also"></a>Ayrıca bkz.

- [Sistem durumu sorunlarını araştırın](health-status.md)
