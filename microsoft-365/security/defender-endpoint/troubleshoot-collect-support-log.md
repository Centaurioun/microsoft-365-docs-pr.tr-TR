---
title: Canlı yanıt kullanarak Uç Nokta için Microsoft Defender'de destek günlüklerini toplama
description: Uç Nokta için Microsoft Defender sorunlarını gidermek için canlı yanıt kullanarak günlükleri toplamayı öğrenin
keywords: destek, günlük, toplama, sorun giderme, canlı yanıt, liveanalyzer, çözümleyici, canlı, yanıt
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: 4c9afb98ff4e9cc5b78a15c798da1451487ff744
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584187"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Canlı yanıt kullanarak Uç Nokta için Microsoft Defender'de destek günlüklerini toplama


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


Desteğe başvurduğunuzda, Uç Nokta için Microsoft Defender İstemci Çözümleyicisi aracının çıkış paketini sağlamanız istenebilir.

Bu konuda, aracın Canlı Yanıt aracılığıyla nasıl çalıştırılacaklarına ilişkin yönergeler sağlanır.

1. [Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'nin](https://aka.ms/BetaMDEAnalyzer) 'Araçlar' alt dizininden sağlanan gerekli betikleri indirin ve getirin. <br>
Örneğin, temel algılayıcı ve cihaz sistem durumu günlüklerini almak için ".. \Tools\MDELiveAnalyzer.ps1".<br>
Defender Virüsten Koruma destek günlüklerine de ihtiyacınız varsa (MpSupportFiles.cab), ".. \Tools\MDELiveAnalyzerAV.ps1" 

2. Araştırmanız gereken makinede [bir Canlı Yanıt oturumu](live-response.md#initiate-a-live-response-session-on-a-device) başlatın.

3. **Dosyayı kitaplığa yükle'yi** seçin.

   :::image type="content" source="images/upload-file.png" alt-text="Karşıya yükleme dosyası" lightbox="images/upload-file.png":::

4. **Dosya seç'i** seçin.

   :::image type="content" source="images/choose-file.png" alt-text="Dosya seç düğmesi-1" lightbox="images/choose-file.png":::

5. MDELiveAnalyzer.ps1 adlı indirilen dosyayı seçin ve **onayla'ya** tıklayın

   :::image type="content" source="images/analyzer-file.png" alt-text="Dosya seç düğmesi-2" lightbox="images/analyzer-file.png":::

6. LiveResponse oturumundayken çözümleyiciyi çalıştırmak ve sonuç dosyasını toplamak için aşağıdaki komutları kullanın:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![Komutların görüntüsü.](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)

> [!NOTE]
>
> - MDEClientAnalyzer'ın en son önizleme sürümü buradan indirilebilir: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).
>
> - LiveAnalyzer betiği, hedef makinedeki sorun giderme paketini şu kaynaktan indirir: https://mdatpclientanalyzer.blob.core.windows.net.
>
>   Makinenin yukarıdaki URL'ye ulaşmasına izin veremiyorsanız LiveAnalyzer betiğini çalıştırmadan önce MDEClientAnalyzerPreview.zip dosyasını kitaplığa yükleyin:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
>   ```
>
> - Makinenin Uç Nokta için Microsoft Defender bulut hizmetleriyle iletişim kurmaması veya Uç Nokta için Microsoft Defender portalda beklendiği gibi görünmemesi durumunda makinede verileri yerel olarak toplama hakkında daha fazla bilgi için bkz. [İstemci bağlantısını doğrulama hizmet URL'lerini Uç Nokta için Microsoft Defender](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).
> 
> - [Canlı yanıt komut örneklerinde](live-response-command-examples.md) açıklandığı gibi, günlükleri arka plan eylemi olarak toplamak için komutun sonundaki '&' simgesini kullanmak isteyebilirsiniz:
>   ```console
>   Run MDELiveAnalyzer.ps1&
>   ```


## <a name="see-also"></a>Ayrıca bkz.
- [İstemci çözümleyicisine genel bakış](overview-client-analyzer.md)
- [İstemci çözümleyicisini indirin ve çalıştırın](download-client-analyzer.md)
- [İstemci çözümleyicisini Windows’da çalıştırın](run-analyzer-windows.md)
- [İstemci çözümleyicisini macOS veya Linux'ta çalıştırın](run-analyzer-macos-linux.md)
- [Windows'da gelişmiş sorun giderme için veri toplama](data-collection-analyzer.md)
- [Çözümleyici HTML raporunu inceleyin](analyzer-report.md)
