---
title: Microsoft Purview Bilgi Koruması tarayıcısını çalıştırma
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Veri depolarında dosyaları bulmak, sınıflandırmak ve korumak için tarayıcıyı Microsoft Purview Bilgi Koruması çalıştırma yönergeleri.
ms.openlocfilehash: e1e8ab8fcfe2e156d2602a2c5d72511ebf769040
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631361"
---
# <a name="running-the-information-protection-scanner"></a>Bilgi koruma tarayıcısını çalıştırma

[Sistem gereksinimlerinizi](deploy-scanner-prereqs.md) onayladıktan ve [tarayıcınızı yapılandırıp yükledikten](deploy-scanner-configure-install.md) sonra, başlamak için [bir bulma taraması çalıştırın](#run-a-discovery-cycle-and-view-reports-for-the-scanner).

Taramalarınızı ileriye doğru yönetmek için aşağıda ayrıntılı olarak sunulan diğer adımları kullanın.

- [Taramayı durdurma](#stopping-a-scan)
- [Dosyaları yeniden tarama](#rescanning-files)

Daha fazla bilgi için bkz. [Microsoft Purview Bilgi Koruması tarayıcı hakkında bilgi edinin](deploy-scanner.md).

> [!TIP]
> Çoğu müşteri bu yordamları yönetici portalında gerçekleştirse de, yalnızca PowerShell'de çalışmanız gerekebilir.
>
> Örneğin, [Azure China 21Vianet tarayıcı sunucuları](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs) gibi Azure portal erişimi olmayan bir ortamda çalışıyorsanız [AzureInformationProtection](/powershell/module/azureinformationprotection) PowerShell modülünde kimlik doğrulaması yapın ve ardından yalnızca PowerShell için bu makaledeki yönergelerle devam edin.
>
## <a name="run-a-discovery-cycle-and-view-reports-for-the-scanner"></a>Bulma döngüsü çalıştırma ve tarayıcı için raporları görüntüleme

İçeriğinizi ilk kez anlamak için [tarayıcınızı yapılandırıp yükledikten](deploy-scanner-configure-install.md) sonra aşağıdaki yordamı kullanın.

İçeriğiniz değiştiğinde bu adımları gerektiği gibi yeniden gerçekleştirin.

1. İçerik tarama işinizde bir tarama başlatın.

    İçerik tarama işini başlatmak için aşağıdakilerden birini yapın:

    - **Microsoft Purview uyumluluk portalı kullanın.**  **Bilgi koruma tarayıcısı - İçerik tarama işleri** bölmesinde, içerik tarama işlerinizi seçin ve ardından **Şimdi tara** seçeneğini belirleyin. **Şimdi tara** seçeneği yalnızca bir içerik tarama işi belirlendikten sonra görünür. 
        
    - **PowerShell komutu kullanın.** Taramayı başlatmak için komutunu çalıştırın `Start-AIPScan` .

1. Tarayıcının döngüsünü tamamlanmasını bekleyin. Tarayıcı belirtilen veri depolarındaki tüm dosyalarda gezindiğinde tarama tamamlanır.

    Tarayıcının ilerleme durumunu izlemek için aşağıdakilerden birini yapın:

    - **Microsoft Purview uyumluluk portalı kullanın.**  **Bilgi koruma tarayıcısı - İçerik tarama işleri** bölmesinde **Yenile'yi** seçin.

        **SON TARAMA SONUÇLARI** sütunu ve SON **TARAMA (BITIŞ SAATİ)** sütununun değerlerini görene kadar bekleyin.
        
    - **PowerShell komutu kullanın.** Durum değişikliğini izlemek için komutunu çalıştırın `Get-AIPScannerStatus` .

1. Tarama tamamlandığında ***localappdata*%\Microsoft\MSIP\Scanner\Reports dizininde%** depolanan raporları gözden geçirin.

    - .txt özet dosyaları tarama için geçen süreyi, taranan dosya sayısını ve bilgi türleriyle eşleşen dosya sayısını içerir.

    - .csv dosyaları her dosya için daha fazla ayrıntı içerir. Bu klasör her tarama döngüsü için en fazla 60 rapor depolar ve gerekli disk alanını en aza indirmek için en son rapor dışındaki tüm raporlar sıkıştırılır. 

        Tarama tamamlandığında, tarama özetiyle birlikte bir `Summary_<x>.txt` dosya oluşturulur.

> [!NOTE]
> Tarayıcılar toplanan veri bilgilerini beş dakikada bir Microsoft Purview Bilgi Koruması gönderir, böylece sonuçları yönetici portalından neredeyse gerçek zamanlı olarak görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Azure Information Protection için analiz ve merkezi raporlama](/azure/information-protection/reports-aip).
>
> Yönetici portalı yalnızca son taramayla ilgili bilgileri görüntüler. Önceki taramaların sonuçlarını görmeniz gerekiyorsa, %*localappdata*%\Microsoft\MSIP\Scanner\Reports klasöründe tarayıcı bilgisayarında depolanan raporlara dönün.
>

[İlk yapılandırmalar](deploy-scanner-configure-install.md#configure-the-scanner-settings) , **keşfedilecek Bilgi türlerini** **yalnızca İlke** olarak ayarlamanızı gerektirir. Bu yapılandırma, ayrıntılı raporlara yalnızca otomatik sınıflandırma için yapılandırdığınız koşulları karşılayan dosyaların dahil olduğu anlamına gelir.

Herhangi bir etiketin uygulandığını görmüyorsanız, etiket yapılandırmanızın önerilen sınıflandırma yerine otomatik olarak eklenip eklenmediğini denetleyin veya **Önerilen etiketlemeyi otomatik olarak kabul et'i** etkinleştirin (tarayıcının 2.7.x.x ve sonraki sürümlerinde kullanılabilir).

Sonuçlar hala beklediğiniz gibi değilse, etiketleriniz için belirttiğiniz koşulları yeniden yapılandırmanız gerekebilir. Bu durumda, koşulları gerektiği gibi yeniden yapılandırın ve sonuçlardan memnun kalana kadar bu yordamı yineleyin. Ardından yapılandırmanızı otomatik olarak ve isteğe bağlı olarak koruma olarak güncelleştirin.

### <a name="changing-log-levels-or-locations"></a>Günlük düzeylerini veya konumlarını değiştirme

[Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) ile *ReportLevel* parametresini kullanarak günlük düzeyini değiştirin.

Rapor klasörü konumu veya adı değiştirilemez. Raporları farklı bir konumda depolamak istiyorsanız, klasör için bir dizin birleşim noktası kullanmayı göz önünde bulundurun.

Örneğin, [Mklink](/windows-server/administration/windows-commands/mklink) komutunu kullanın: `mklink /j D:\Scanner_reports C:\Users\aipscannersvc\AppData\Local\Microsoft\MSIP\Scanner\Reports`

İlk yapılandırma ve yüklemeden sonra bu adımları gerçekleştirdiyseniz, [Tarayıcıyı sınıflandırma ve koruma uygulamak için yapılandırma](deploy-scanner-configure-install.md#configure-the-scanner-to-apply-classification-and-protection) ile devam edin.

## <a name="stopping-a-scan"></a>Taramayı durdurma

Şu anda çalışmakta olan bir taramayı tamamlanmadan durdurmak için aşağıdaki yöntemlerden birini kullanın:

- **Microsoft Purview uyumluluk portalı.** **Taramayı durdur'u** seçin:

- **Bir PowerShell komutu çalıştırın.** Aşağıdaki komutu çalıştırın:

    ```PowerShell
    Stop-AIPScan
    ```

## <a name="rescanning-files"></a>Dosyaları yeniden tarama

[İlk tarama döngüsü](#run-a-discovery-cycle-and-view-reports-for-the-scanner) için tarayıcı, yapılandırılan veri depolarındaki tüm dosyaları inceler. Sonraki taramalar için yalnızca yeni veya değiştirilmiş dosyalar incelenir.

Raporların tüm dosyaları içermesini istediğinizde, tüm dosyalara uygulamak istediğiniz değişiklikler olduğunda ve tarayıcı bulma modunda çalıştığında tüm dosyaları yeniden incelemek yararlı olur.

**Microsoft Purview uyumluluk portalı tam bir yeniden taramayı el ile çalıştırmak için**:

1. **Microsoft Purview uyumluluk portalı Bilgi koruma tarayıcısı - İçerik tarama işleri** bölmesine gidin.

2. Listeden içerik tarama işinizi seçin ve ardından **Tüm dosyaları yeniden tara** seçeneğini belirleyin:

Tam tarama tamamlandığında, tarama türü otomatik olarak artımlı olarak değişir, böylece sonraki taramalarda yalnızca yeni veya değiştirilmiş dosyalar yeniden taranır.

> [!TIP]
> [İçerik tarama işinizde](deploy-scanner-configure-install.md#create-a-content-scan-job) değişiklik yaptıysanız, uyumluluk portalı tam bir yeniden taramayı atlamanızı ister. Yeniden taramanızın gerçekleştiğinden emin olmak için görüntülenen istemde **Hayır'ı** seçtiğinizden emin olun.
>

### <a name="trigger-a-full-rescan-by-modifying-your-settings"></a>Ayarlarınızı değiştirerek tam bir yeniden tarama tetikleme

Tarayıcının önceki sürümleri, tarayıcı otomatik ve önerilen etiketleme için yeni veya değiştirilmiş ayarlar algılasa tüm dosyaları taramıştı. Tarayıcı ilkeyi dört saatte bir otomatik olarak yeniler.

Tarayıcı 2.8.85.0 veya sonraki sürümlerinde, bilgi koruma tarayıcısı tutarlı performans sağlamak için güncelleştirilmiş ayarlar için tam yeniden taramayı atlar. Tam [yeniden taramayı gerektiği gibi el ile çalıştırdığınızdan](#rescanning-files) emin olun.

Örneğin, **Duyarlılık ilkesi** ayarlarını **Zorla = Kapalı olan Zorlama =** **Açık** olarak değiştirdiyseniz, etiketlerinizi içeriğinize uygulamak için tam bir yeniden tarama çalıştırdığınızdan emin olun.

> [!NOTE]
> Tarayıcı sürüm [2.7.101.0](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history#general-availability-versions-that-are-no-longer-supported) ve altında, ilkeyi test ederken olduğu gibi dört saatten daha erken yenilemek isteyebilirsiniz. Bu gibi durumlarda **, %LocalAppData%\Microsoft\MSIP\mip\mip\<processname>** dizininin içeriğini el ile silin ve Azure Information Protection hizmetini yeniden başlatın.
>
> Duyarlılık etiketlerinizin şifreleme ayarlarını da değiştirdiyseniz, Azure Information Protection hizmetini yeniden başlatmadan önce güncelleştirilmiş şifreleme ayarlarını kaydettiğinizde fazladan 15 dakika bekleyin.
>

## <a name="next-steps"></a>Sonraki adımlar

PowerShell'i kullanarak dosyaları masaüstü bilgisayarınızdan etkileşimli olarak sınıflandırabilir ve koruyabilirsiniz. Bu ve PowerShell kullanan diğer senaryolar hakkında daha fazla bilgi için bkz. [Azure Information Protection birleşik etiketleme istemcisiyle PowerShell kullanma](/azure/information-protection/rms-client/clientv2-admin-guide-powershell).
