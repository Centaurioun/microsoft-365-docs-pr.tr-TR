---
title: Sunucuları Microsoft Monitoring Agent'tan birleşik çözüme geçirme
description: Bu makaledeki alt düzey sunucuları Microsoft Monitoring Agent'tan yeni birleşik çözüme adım adım geçirmeyi öğrenin.
keywords: sunucuyu geçirme, sunucu, 2012r2, 2016, sunucu geçişi Uç Nokta için Microsoft Defender sunucuları, MECM, Microsoft Monitoring Agent, MMA, alt düzey sunucu, birleşik çözüm, UA
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
author: alekyaj
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.openlocfilehash: 82c4a9e5bc61377209a1f05e24f13452f587ff2e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638884"
---
# <a name="migrating-servers-from-microsoft-monitoring-agent-to-the-unified-solution"></a>Sunucuları Microsoft Monitoring Agent'tan birleşik çözüme geçirme

**Şunlar için geçerlidir:**

- Windows Server 2012 R2
- Windows Server 2016

Bu makale, alt düzey sunucuları Microsoft Monitoring Agent'tan (MMA) birleşik çözüme geçirme konusunda size yol gösterir.

## <a name="prerequisites"></a>Önkoşullar

- 2207'den eski Microsoft Endpoint Configuration Manager (MECM).
- Microsoft Monitoring Agent ile birlikte ortamınızdaki alt düzey işletim sistemi cihazları. Onaylamak için Görev Yöneticisi'nde çalıştığını doğrulayın `MsSenseS.exe` .
- MMA aracısının varlığı. Denetim Masası> Microsoft Monitoring Agent'ta doğru Çalışma Alanı Kimliğinin mevcut olup olmadığını denetleyerek bunu doğrulayabilirsiniz.
- Cihazlar ekli etkin Microsoft 365 Defender portalı.
- MECM örneğinizde MMA aracısını kullanan Windows Server 2012 R2 veya Windows Server 2016 gibi alt düzey sunucuları içeren **bir Cihaz Koleksiyonu** ayarlanır.

Listelenen önkoşulları yükleme hakkında daha fazla bilgi için [ilgili konular](#related-topics) bölümüne bakın.

## <a name="gather-required-files"></a>Gerekli dosyaları toplama

MeCM ile diğer uygulamaları dağıttığınız içerik kaynağına birleştirilmiş çözüm paketini, ekleme betiğini ve geçiş betiğini kopyalayın.

1. [Microsoft 365 Defender ayarları sayfasından](https://sip.security.microsoft.com/preferences2/onboarding) Ekleme Betiği'ni ve birleşik çözümü indirin.
   :::image type="content" source="images/onboarding-script.png" alt-text="Ekleme betiği ve birleşik çözüm indirme işleminin ekran görüntüsü" lightbox="images/onboarding-script.png":::
   > [!Note]
   > .cmd dosyasını almak için Dağıtım yöntemi açılan listesinden grup ilkesi seçmeniz gerekir.
2. Geçiş betiğini belgeden indirin: [Önceki MMA tabanlı Uç Nokta için Microsoft Defender çözümünden sunucu geçişi senaryoları](server-migration.md). Bu betik GitHub'da da bulunabilir: [GitHub - microsoft/mdefordownlevelserver](https://github.com/microsoft/mdefordownlevelserver).
3. Üç dosyayı da MECM tarafından kullanılan paylaşılan bir klasöre Yazılım Kaynağı olarak kaydedin.

   :::image type="content" source="images/ua-migration.png" alt-text="MeCM tarafından paylaşılan klasörü kaydetme işleminin ekran görüntüsü.":::

## <a name="create-the-package-as-an-application"></a>Paketi uygulama olarak oluşturma

1. MECM konsolunda şu adımları izleyin: **Yazılım Kitaplığı>Uygulamalar>Uygulama Oluşturma**.
2. **Uygulama bilgilerini el ile belirtin'i** seçin.
   :::image type="content" source="images/manual-application-information.png" alt-text="Uygulama bilgileri seçimini el ile belirtme işleminin ekran görüntüsü." lightbox="images/manual-application-information.png":::
3. Sihirbazın Yazılım Merkezi ekranında **İleri'yi** seçin.
4. Dağıtım Türleri'nin üzerinde **Ekle'ye** tıklayın.
5. **Dağıtım türü bilgilerini belirtmek için El ile'yi** ve **ardından İleri'yi** seçin.
6. Betik dağıtımınıza bir ad verin ve **İleri'yi** seçin.

   :::image type="content" source="images/manual-deployment-information.png" alt-text="Betik dağıtım bilgilerini belirten ekran görüntüsü.":::
7. Bu adımda, içeriğinizin bulunduğu UNC yolunu kopyalayın. Örnek: `\\ServerName\h$\SOFTWARE_SOURCE\path`.

   :::image type="content" source="images/deployment-type-wizard.png" alt-text="UNC yol kopyalamayı gösteren ekran görüntüsü.":::
  
8. Ayrıca, aşağıdakileri yükleme programı olarak ayarlayın:

     ```powershell
      Powershell.exe -ExecutionPolicy ByPass -File install.ps1 -RemoveMMA <workspace ID> -OnboardingScript .\WindowsDefenderATPOnboardingScript.cmd 
     ```

      **İleri'ye** tıklayın ve bu bölümde kendi Çalışma Alanı Kimliğinizi eklediğinizden emin olun.
9. **İleri'ye** tıklayın ve yan tümce ekle'ye tıklayın.
10. Algılama yöntemi aşağıda gösterilen kayıt defteri anahtarını temel alır.
      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Sense`

      Şu seçeneği işaretleyin: **Bu uygulamanın var olduğunu belirtmek için hedef sistemde bu kayıt defteri ayarının çıkması gerekir.**

      :::image type="content" source="images/detection-wizard.png" alt-text="Algılama türü sihirbazını gösteren ekran görüntüsü":::

      >[!TIP]
      >Kayıt defteri anahtarı değeri, birleşik çözümün yüklü olduğu bir cihazda aşağıda gösterilen Powershell komutu çalıştırılarak elde edildi. Diğer yaratıcı algılama yöntemleri de kullanılabilir. Amaç, birleşik çözümün belirli bir cihaza önceden yüklenmiş olup olmadığını belirlemektir. Değer ve Veri Türü alanlarını boş bırakabilirsiniz.

     ```powershell
      get-wmiobject Win32_Product | Sort-Object -Property Name |Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize 
     ```

11. **Kullanıcı Deneyimi** bölümünde, ekran görüntüsünde gösterilen önerilen ayarları denetleyin. Ortamınıza uygun olanı seçip **İleri'ye** tıklayabilirsiniz. **Yükleme programı görünürlüğü** için aşama testi sırasında **Normal** ile yüklemeniz ve ardından genel dağıtım için **simge durumuna küçültülmüş** olarak değiştirmeniz önerilir.

     >[!TIP]
     >İzin verilen çalışma zamanı üst sınırı (varsayılan) 120 dakikadan 60 dakikaya düşürülebilir.

     :::image type="content" source="images/user-experience-in-deployment-type-wizard.png" alt-text="Dağıtım türü sihirbazındaki kullanıcı deneyimini gösteren ekran görüntüsü.":::

12. Ek gereksinimler ekledikten sonra **İleri'yi** seçin. 
13. Bağımlılıklar bölümünde **İleri'yi** seçin. 
14. Tamamlama ekranı **açılana kadar İleri'yi** ve ardından **Kapat'ı** seçin.
15. Uygulama Sihirbazı tamamlanıncaya kadar **İleri'yi** seçin. Tümünün yeşil işaretli olduğunu doğrulayın.
16. Sihirbazı kapatın, kısa süre önce oluşturulan uygulamaya sağ tıklayın ve alt düzey sunucu koleksiyonunuz için dağıtın. Yerel olarak, yükleme Yazılım Merkezi'nde onaylanabilir. Ayrıntılar için konumundaki `C:\Windows\CCM\Logs\AppEnforce.log`CM günlüklerine bakın.

    :::image type="content" source="images/deploy-application.png" alt-text="Oluşturulan uygulamanın dağıtımını gösteren ekran görüntüsü." lightbox="images/deploy-application.png":::
     
17. MECM > İzleme > Dağıtımları'nda geçişin durumunu doğrulayın.

    :::image type="content" source="images/deployment-status.png" alt-text="Dağıtım durumu denetimini gösteren ekran görüntüsü." lightbox="images/deployment-status.png":::
      
18. Sorun giderme. ETL dosyaları oluşturulur ve bu konumdaki `C:\Windows\ccmcache\#\`her sunucuya otomatik olarak kaydedilir. Bu dosyalar, ekleme sorunlarını gidermek için destek tarafından kullanılabilir.

## <a name="related-topics"></a>İlgili konular

- [Microsoft Monitoring Agent Kurulumu](/services-hub/health/mma-setup)
- [Uygulamaları dağıtma - Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Uç Nokta için Microsoft Defender - Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Windows sunucularını Uç Nokta için Microsoft Defender hizmetine ekleme](configure-server-endpoints.md)
- [Uç Nokta için Microsoft Defender: Windows Server 2012 R2 ve 2016'nın Savunması](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292)
