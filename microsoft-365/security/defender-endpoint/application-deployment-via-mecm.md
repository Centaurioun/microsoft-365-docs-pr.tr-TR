---
title: Sunucuları Microsoft Monitoring Agent'tan birleşik çözüme geçirme
description: Bu makaledeki alt düzey sunucuları Microsoft Monitoring Agent'tan yeni birleşik çözüme adım adım geçirmeyi öğrenin.
keywords: sunucuyu geçirme, sunucu, 2012r2, 2016, sunucu geçişi Uç Nokta için Microsoft Defender sunucuları, MECM, Microsoft Monitoring Agent, MMA, alt düzey sunucu, birleşik çözüm, UA
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: alekyaj
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fef1a5a7b8e47c4f97d36d4002ccf00401948d12
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66696412"
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
- MECM örneğinizde MMA aracısını kullanan Windows Server 2012 R2 veya Windows Server 2016 gibi alt düzey sunucuları içeren bir Cihaz Koleksiyonu ayarlanır.

Listelenen önkoşulları yükleme hakkında daha fazla bilgi için [ilgili konular](#related-topics) bölümüne bakın.

## <a name="gather-required-files"></a>Gerekli dosyaları toplama

MeCM ile diğer uygulamaları dağıttığınız içerik kaynağına birleştirilmiş çözüm paketini, ekleme betiğini ve geçiş betiğini kopyalayın.

1. [Microsoft 365 Defender ayarları sayfasından](https://sip.security.microsoft.com/preferences2/onboarding) Ekleme Betiği'ni ve birleşik çözümü indirin.
      :::image type="content" source="images/onboarding-script.png" alt-text="Ekleme betiği ve birleşik çözüm indirme işleminin ekran görüntüsü." lightbox="images/onboarding-script.png":::
2. Geçiş betiğini belgeden indirin: [Önceki MMA tabanlı Uç Nokta için Microsoft Defender çözümünden sunucu geçişi senaryoları](server-migration.md). Bu betik GitHub'da da bulunabilir: [GitHub - microsoft/mdefordownlevelserver](https://github.com/microsoft/mdefordownlevelserver).
3. Üç dosyayı da MECM tarafından kullanılan paylaşılan bir klasöre Yazılım Kaynağı olarak kaydedin.
     :::image type="content" source="images/ua-migration.png" alt-text="MeCM tarafından paylaşılan klasörü kaydetme işleminin ekran görüntüsü.":::

## <a name="create-the-package-as-an-application"></a>Paketi uygulama olarak oluşturma

1. MECM konsolunda şu adımları izleyin: **Yazılım Kitaplığı>Uygulamalar>Uygulama Oluşturma**.
2. **Uygulama bilgilerini el ile belirtin'i** seçin.
      :::image type="content" source="images/manual-application-information.png" alt-text="Uygulama bilgileri seçimini el ile belirtme işleminin ekran görüntüsü." lightbox="images/manual-application-information.png":::
3. Sihirbazın Yazılım Merkezi ekranında **İleri'ye** tıklayın.
4. Dağıtım Türleri'nin üzerinde **Ekle'ye** tıklayın.
5. **Dağıtım türü bilgilerini belirtmek için El ile'yi** seçin ve **İleri'ye** tıklayın.
6. Betik dağıtımınıza bir ad verin ve **İleri'ye** tıklayın.
     :::image type="content" source="images/manual-deployment-information.png" alt-text="Betik dağıtım bilgilerini belirten ekran görüntüsü.":::
7. Bu adımda, içeriğinizin bulunduğu UNC yolunu kopyalayın. Örnek: `\\Cm1\h$\SOFTWARE_SOURCE\UAmigrate`.
     :::image type="content" source="images/deployment-type-wizard.png" alt-text="UNC yol kopyalamayı gösteren ekran görüntüsü.":::
8. Ayrıca, aşağıdakileri yükleme programı olarak ayarlayın:

     ```powershell
       Powershell.exe -ExecutionPolicy ByPass -File install.ps1 -Log -Etl -RemoveMMA 48594f03-7e66-4e15-8b60-d9da2f92d564 -OnboardingScript .\WindowsDefenderATP.onboarding
     ```

9. **İleri'ye** tıklayın ve yan tümce ekle'ye tıklayın.
10. Yan tümcesi, aşağıdaki anahtarın mevcut olup olmadığını görmek için kayıt defterinde arar:  `HKEY_LOCAL_MACHINESOFTWARE\Classes\Installer\Products\63FAD065BFFD18F1926692665F704C6D`

     Aşağıdaki girişleri sağlayın:
     - Değer: **ProductName**
     - Veri Türü: **Dize**
     - Şu seçeneği işaretleyin: **Bu uygulamanın var olduğunu belirtmek için hedef sistemde bu kayıt defteri ayarının çıkması gerekir.**

     :::image type="content" source="images/detection-rule-wizard.png" alt-text="Kayıt defteri anahtarı algılamayı gösteren ekran görüntüsü.":::

     >[!TIP]
     >Bu kayıt defteri anahtarı değeri, birleşik çözümün yüklü olduğu bir cihazda aşağıdaki PowerShell komutu çalıştırılarak elde edildi. Diğer yaratıcı algılama yöntemleri de kullanılabilir. Amaç, birleşik çözümün belirli bir cihaza zaten yüklenip yüklenmediğini tanımlamaktır.

     ```powershell
     PowerShell Cmd:  get-wmiobject Win32_Product | Sort-Object -Property Name |Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize
     ```

11. **Kullanıcı Deneyimi** bölümünde ortamınıza uygun olanı seçebilir ve **İleri'ye** tıklayabilirsiniz. **Yükleme programı görünürlüğü** için aşama testi sırasında **Normal görünürlük** ile yüklemeniz ve ardından genel dağıtım için **simge durumuna küçültülmüş** olarak değiştirmeniz önerilir.
     >[!TIP]
     > İzin verilen çalışma zamanı üst sınırı (varsayılan) 120 dakikadan 30 dakikaya düşürülebilir.

     :::image type="content" source="images/user-experience-in-deployment-type-wizard.png" alt-text="Dağıtım türü sihirbazındaki kullanıcı deneyimini gösteren ekran görüntüsü.":::

12. Gereksinimler'de **İleri'ye** tıklayın.
13. Bağımlılıklar'da **İleri'ye** tıklayın.
14. Tamamlama ekranı açılana kadar **İleri'ye** ve ardından **Kapat'a** tıklayın.
15. Uygulama Sihirbazı tamamlanıncaya kadar İleri'ye tıklamaya devam edin. Tümünün yeşil işaretli olduğunu doğrulayın.
16. Sihirbazı kapatın, kısa süre önce oluşturulan uygulamaya sağ tıklayın ve alt düzey sunucu koleksiyonunuz için dağıtın.
     :::image type="content" source="images/deploy-application.png" alt-text="Oluşturulan uygulamanın dağıtımını gösteren ekran görüntüsü." lightbox="images/deploy-application.png":::
17. MECM>İzleme>Dağıtımlarında bu geçişin durumunu doğrulayın.

      :::image type="content" source="images/deployment-status.png" alt-text="Dağıtım durumu denetimini gösteren ekran görüntüsü." lightbox="images/deployment-status.png":::

## <a name="related-topics"></a>İlgili konular

- [Microsoft Monitoring Agent Kurulumu](/services-hub/health/mma-setup)
- [Uygulamaları dağıtma - Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Uç Nokta için Microsoft Defender - Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Windows sunucularını Uç Nokta için Microsoft Defender hizmetine ekleme](configure-server-endpoints.md)
- [Uç Nokta için Microsoft Defender: Windows Server 2012 R2 ve 2016'nın Savunması](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292)
