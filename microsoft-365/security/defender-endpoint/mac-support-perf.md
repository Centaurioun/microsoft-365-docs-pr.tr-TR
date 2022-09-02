---
title: macOS'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme
description: macOS'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, performans
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 23da340c276256cc624dfc9a84da38ec326ae00e
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521597"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS'ta Uç Nokta için Microsoft Defender performans sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [macOS üzerinde Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu konu, macOS'ta Uç Nokta için Microsoft Defender ile ilgili performans sorunlarını daraltmak için kullanılabilecek bazı genel adımlar sağlar.


Çalıştırdığınız uygulamalara ve cihazınızın özelliklerine bağlı olarak, macOS üzerinde Uç Nokta için Microsoft Defender çalıştırırken en iyi performansla karşılaşabilirsiniz. Özellikle, kısa bir zaman aralığı boyunca birçok kaynağa erişen uygulamalar veya sistem işlemleri macOS'ta Uç Nokta için Microsoft Defender performans sorunlarına yol açabilir.

>[!WARNING]
>Başlamadan önce lütfen cihazda şu anda diğer güvenlik ürünlerinin çalışmadığından emin olun. Birden çok güvenlik ürünü çakışabilir ve konak performansını etkileyebilir. 

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>Gerçek Zamanlı Koruma İstatistiklerini kullanarak performans sorunlarını giderme
**Şunlar için geçerlidir:**
- Yalnızca AV ile ilgili performans sorunları

Gerçek zamanlı koruma (RTP), macOS'ta cihazınızı sürekli izleyen ve tehditlere karşı koruyan uç nokta için Defender özelliğidir. Dosya ve süreç izleme ve diğer buluşsal yöntemlerden oluşur.

Bu sorunları gidermek ve azaltmak için aşağıdaki adımlar kullanılabilir:

1. Aşağıdaki yöntemlerden birini kullanarak gerçek zamanlı korumayı devre dışı bırakın ve performansın iyileşip iyileşmediğini gözlemleyin. Bu yaklaşım, macOS'ta Uç Nokta için Microsoft Defender performans sorunlarına katkıda bulunup bulunmadığını daraltmaya yardımcı olur.

      Cihazınız kuruluşunuz tarafından yönetilmiyorsa, gerçek zamanlı koruma aşağıdaki seçeneklerden biri kullanılarak devre dışı bırakılabilir:

    - Kullanıcı arabiriminden. macOS'ta Uç Nokta için Microsoft Defender açın ve **Ayarları yönet'e** gidin.

      :::image type="content" source="images/mdatp-36-rtp.png" alt-text=" Gerçek zamanlı korumayı yönet sayfası" lightbox="images/mdatp-36-rtp.png":::
      

    - Terminalden. Güvenlik amacıyla, bu işlem yükseltme gerektirir.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Cihazınız kuruluşunuz tarafından yönetiliyorsa, [macOS'ta Uç Nokta için Microsoft Defender için tercihleri ayarlama](mac-preferences.md) başlığı altında yer alan yönergeler kullanılarak gerçek zamanlı koruma yöneticiniz tarafından devre dışı bırakılabilir.

      Gerçek zamanlı koruma kapalıyken performans sorunu devam ederse, sorunun kaynağı uç nokta algılama ve yanıt bileşeni olabilir. Bu durumda, daha fazla yönerge ve risk azaltma için lütfen müşteri desteğine başvurun.

2. Bulucu'yı açın ve **Uygulamalar** \> **Yardımcı Programları'na** gidin. **Etkinlik İzleyicisi'ni** açın ve sisteminizdeki kaynakları hangi uygulamaların kullandığını analiz edin. Tipik örnekler arasında yazılım güncelleştirenler ve derleyiciler yer alır.

3. En çok taramayı tetikleyen uygulamaları bulmak için Mac'te Uç Nokta için Defender tarafından toplanan gerçek zamanlı istatistikleri kullanabilirsiniz.

      > [!NOTE]
      > Bu özellik 100.90.70 veya daha yeni sürümlerde kullanılabilir.
      Bu özellik **Dogfood** ve **InsiderFast** kanallarında varsayılan olarak etkindir. Farklı bir güncelleştirme kanalı kullanıyorsanız, bu özellik komut satırından etkinleştirilebilir:

      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Bu özelliğin etkinleştirilmesi için gerçek zamanlı koruma gerekir. Gerçek zamanlı korumanın durumunu denetlemek için aşağıdaki komutu çalıştırın:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    **real_time_protection_enabled** girdisinin doğru olduğunu doğrulayın. Aksi takdirde, etkinleştirmek için aşağıdaki komutu çalıştırın:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Geçerli istatistikleri toplamak için şunu çalıştırın:

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > **--output json** (çift çizgiye dikkat edin) kullanıldığında çıkış biçimi ayrıştırma için hazır olur.
      Bu komutun çıkışı tüm işlemleri ve bunların ilişkili tarama etkinliğini gösterir.

4. Mac sisteminizde komutunu kullanarak örnek Python ayrıştırıcısını high_cpu_parser.py indirin:

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    Bu komutun çıkışı aşağıdakine benzer olmalıdır:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in
    0s
    ```

5. Ardından, aşağıdaki komutları yazın:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      Yukarıdaki çıkışı, performans sorunlarına en çok katkıda bulunanların listesidir. İlk sütun işlem tanımlayıcısı (PID), ikinci sütun te işlem adı ve son sütun ise etkilenen öğeye göre sıralanmış taranan dosyaların sayısıdır.

      Örneğin, komutun çıkışı aşağıdakine benzer olacaktır:

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      Mac'te Uç Nokta için Defender'ın performansını geliştirmek için Taranan toplam dosya satırı altında en yüksek sayıya sahip olanı bulun ve bunun için bir dışlama ekleyin. Daha fazla bilgi için bkz. [macOS'ta Uç Nokta için Defender dışlamalarını yapılandırma ve doğrulama](mac-exclusions.md).

      > [!NOTE]
      > Uygulama istatistiği bellekte depolar ve yalnızca başlatıldığından ve gerçek zamanlı koruma etkinleştirildiğinden beri dosya etkinliğini izler. Gerçek zamanlı korumanın kapalı olduğu dönemlerde veya öncesinde başlatılan işlemler sayılmaz. Ayrıca, yalnızca taramaları tetikleyen olaylar sayılır.
      >
6. performans sorunlarına katkıda bulunan işlemler veya disk konumları için dışlamalarla macOS'ta Uç Nokta için Microsoft Defender yapılandırın ve gerçek zamanlı korumayı yeniden etkinleştirin.

     Ayrıntılar için bkz[. macOS'ta Uç Nokta için Microsoft Defender için dışlamaları yapılandırma ve doğrulama](mac-exclusions.md).


## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'ni kullanarak performans sorunlarını giderme

**Şunlar için geçerlidir:**
- AV ve EDR gibi kullanılabilir tüm Uç Nokta için Defender bileşenlerinin performans sorunları  

Uç Nokta için Microsoft Defender İstemci Çözümleyicisi (MDECA), macOS'ta [eklenen cihazlardaki](/microsoft-365/security/defender-endpoint/onboard-configure) performans sorunlarını gidermek için izlemeleri, günlükleri ve tanılama bilgilerini toplayabilir.

> [!NOTE]
>- Uç Nokta için Microsoft Defender İstemci Çözümleyicisi aracı, Microsoft Müşteri Destek Hizmetleri (CSS) tarafından ip adresleri, Uç Nokta için Microsoft Defender karşılaşabileceğiniz sorunları gidermeye yardımcı olacak bilgisayar adları gibi bilgileri toplamak için düzenli olarak kullanılır. Gizlilik bildirimimiz hakkında daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://privacy.microsoft.com/privacystatement).
>- Genel bir en iyi uygulama olarak, [Uç Nokta için Microsoft Defender aracısını  en son kullanılabilir sürüme](linux-whatsnew.md)  güncelleştirmeniz ve daha fazla araştırma yapmadan önce sorunun hala devam ettiğini onaylamanız önerilir. 

Performans sorunlarını gidermek üzere istemci çözümleyicisini çalıştırmak için bkz. [macOS ve Linux üzerinde istemci çözümleyicisini çalıştırma](run-analyzer-macos-linux.md).

>[!NOTE]
>Yukarıdaki adımların ardından performans sorununun devam etmesi durumunda, daha fazla yönerge ve risk azaltma için lütfen müşteri desteğine başvurun. 


## <a name="see-also"></a>Ayrıca bkz.

- [Sistem durumu sorunlarını araştırın](health-status.md)
