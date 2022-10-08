---
title: Kuruluşunuzun cihazlarını İş için Microsoft Defender ekleme
description: Kuruluşunuzun cihazlarını İş için Microsoft Defender ekleme
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.openlocfilehash: d358c456bea558bae4b5c17f7d0ea52e8a5803a9
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097105"
---
# <a name="onboard-enrolled-devices-to-microsoft-defender-for-business"></a>Kayıtlı cihazları İş için Microsoft Defender ekleme

Microsoft 365 İş Ekstra küçük ve orta ölçekli işletmeler için bir uç nokta güvenlik çözümü olan [İş için Microsoft Defender](../security/defender-business/mdb-overview.md) içerir. İş için Defender, şirketinizin cihazları için yeni nesil koruma (virüsten koruma, kötü amaçlı yazılımdan koruma ve bulut tabanlı koruma), güvenlik duvarı koruması, web içeriği filtreleme ve daha fazlasını sağlar. Cihazları eklediğinizde ve bu cihazlara güvenlik ilkeleri uyguladığınızda koruma uygulanır.

Cihazları İş için Defender'a eklemek için çeşitli seçenekler arasından seçim yapabilirsiniz:

- [zaten Microsoft Intune kayıtlı Windows cihazları için otomatik ekleme](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune)
- [Windows ve Mac cihazlarını İş için Defender'a eklemeye yönelik yerel betik](#use-a-local-script-to-onboard-windows-and-mac-devices-to-defender-for-business) (Intune henüz kaydedilmemiş cihazlar için)
- Mobil cihazlar (Windows, Mac, iOS ve Android) [dahil olmak üzere yeni cihazları kaydetmek için Intune](#use-intune-to-enroll-devices) ve ardından bu cihazlara İş için Defender ilkelerini uygulama

Bu makale şunları da içerir:

- [Sunucular ne olacak?](#what-about-servers) (YENİ!)
- [Windows cihazında algılama testi çalıştırma](#run-a-detection-test-on-a-windows-device)
- [Cihazları aşamalı olarak ekleme](#onboard-devices-gradually)
- Bir [cihaz](#offboard-a-device) değiştirilirse veya biri kuruluştan ayrılırsa cihazı çıkarma

> [!IMPORTANT]
> Bir sorun oluşursa ve ekleme işleminiz başarısız olursa sorun [giderme İş için Microsoft Defender](../security/defender-business/mdb-troubleshooting.yml) bakın.

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-intune"></a>Zaten Intune kayıtlı Windows cihazları için otomatik ekleme kullanma

Bu cihazlar zaten Intune kayıtlıysa Windows istemci cihazlarını İş için Defender'a otomatik olarak ekleyebilirsiniz. İş için Defender, zaten Intune kayıtlı Windows istemci cihazlarını algılar ve bu cihazların otomatik olarak eklenip eklenmeyeceğini seçmenizi ister. Daha sonra İş için Defender'daki güvenlik ilkeleri ve ayarları bu cihazlara uygulanır. Bu işlemi *otomatik ekleme* olarak adlandırıyoruz. 

Otomatik ekleme, cihazlarınızın hemen korunmasına yardımcı olur. Otomatik ekleme seçeneğinin yalnızca aşağıdaki koşulların karşılanması durumunda Windows istemci cihazları için geçerli olduğunu unutmayın:

- Kuruluşunuz, İş için Defender'ı almadan önce Intune'da zaten Intune veya Mobil Cihaz Yönetimi (MDM) kullanıyordu (Microsoft 365 İş Ekstra müşterilerin zaten Microsoft Intune ve MDM'leri var).
- Intune kayıtlı Windows istemci cihazlarınız zaten var.

> [!TIP]
> Otomatik ekleme kullanmanız istenirse "tüm cihazlar kaydedildi" seçeneğini belirlemenizi öneririz. Bu şekilde, Windows cihazları daha sonra Intune kaydedildiğinde otomatik olarak İş için Defender'a eklenir.

Otomatik ekleme hakkında daha fazla bilgi edinmek için bkz. [İş için Microsoft Defender ayarlamak için sihirbazı kullanma](../security/defender-business/mdb-use-wizard.md).

## <a name="use-a-local-script-to-onboard-windows-and-mac-devices-to-defender-for-business"></a>Windows ve Mac cihazlarını İş için Defender'a eklemek için yerel betik kullanma

Windows ve Mac cihazlarını eklemek için yerel bir betik kullanabilirsiniz. Ekleme betiğini bir cihazda çalıştırdığınızda, Azure Active Directory ile bir güven oluşturur (bu güven yoksa), cihazı Intune kaydeder (henüz kaydedilmediyse) ve ardından cihazı İş için Defender'a ekler. Yerel betiği kullanarak aynı anda en fazla 10 cihaz ekleyebilirsiniz.

Ayrıntılı yönergeler için bkz. [İş için Microsoft Defender cihazları ekleme](../security/defender-business/mdb-onboard-devices.md).

## <a name="use-intune-to-enroll-devices"></a>Cihazları kaydetmek için Intune kullanma

Bir cihazı kaydetmek için cihazı kendiniz kaydedebilir veya kullanıcıların şirket portalı uygulamasında oturum açmasını, cihazlarını kaydetmesini ve ardından gerekli uygulamaları yüklemesini sağlayabilirsiniz. 

İş için Defender'ı almadan önce zaten Intune veya Mobil Cihaz Yönetimi kullanıyorsanız kuruluşunuzun cihazlarını eklemek için Intune kullanmaya devam edebilirsiniz. Intune ile, iOS ve Android cihazlar da dahil olmak üzere bilgisayarları, tabletleri ve telefonları ekleyebilirsiniz.

Bkz[. Microsoft Intune'da cihaz kaydı](/mem/intune/enrollment/device-enrollment). 

## <a name="what-about-servers"></a>Sunucular ne olacak?

Varsayılan olarak, sunucular Microsoft 365 İş Ekstra ve İş için Defender'ın tek başına sürümünde desteklenmez. Ancak **, Windows Server veya Linux Server çalıştıran bir uç nokta gibi bir sunucuyu ekleme özelliği artık önizleme aşamasında!** 

Bkz. [İş için Microsoft Defender sunucuları alma (önizleme)](../security/defender-business/get-defender-business-servers.md).

## <a name="run-a-detection-test-on-a-windows-device"></a>Windows cihazında algılama testi çalıştırma

Windows cihazlarını İş için Defender'a ekledikten sonra, her şeyin düzgün çalıştığından emin olmak için bir Windows cihazında algılama testi çalıştırabilirsiniz.

1. Windows cihazında bir klasör oluşturun: `C:\test-MDATP-test`.

2. Yönetici olarak Komut İstemi'ni açın.

3. Komut İstemi penceresinde aşağıdaki PowerShell komutunu çalıştırın:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Komut çalıştırıldıktan sonra Komut İstemi penceresi otomatik olarak kapanır. Başarılı olursa algılama testi tamamlandı olarak işaretlenir ve yeni eklenen cihaz için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) yaklaşık on dakika içinde yeni bir uyarı görünür.

## <a name="onboard-devices-gradually"></a>Cihazları aşamalı olarak ekleme

Cihazları *aşamalı cihaz ekleme* olarak adlandırdığımız aşamalara eklemeyi tercih ediyorsanız şu adımları izleyin: 

1. Eklemek istediğiniz bir cihaz kümesini belirleyin.

2. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

3. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Ekleme'yi** seçin.

4. bir işletim sistemi (**Windows 10 ve 11 gibi)** seçin ve ardından bir ekleme yöntemi (**Yerel betik** gibi) seçin. Seçtiğiniz yöntem için sağlanan yönergeleri izleyin.

5. Eklemek istediğiniz her cihaz kümesi için bu işlemi yineleyin. 

> [!TIP]
> Cihazları her eklediğinizde aynı ekleme paketini kullanmanız gerekmez. Örneğin, bazı cihazları eklemek için yerel bir betik kullanabilir ve daha sonra daha fazla cihaz eklemek için başka bir yöntem seçebilirsiniz.

## <a name="offboard-a-device"></a>Cihazı çıkarma

Bir cihazı boşaltmak istiyorsanız aşağıdaki yordamlardan birini kullanın:

1. Gezinti bölmesinde **Ayarlar'ı** ve ardından **Uç Noktalar'ı** seçin.

2. **Cihaz yönetimi'nin** altında **Çıkarma'yı** seçin.

3. **Windows 10 ve 11** gibi bir işletim sistemi seçin ve ardından **Cihazı kullanıma alma** altında Dağıtım **yöntemi** bölümünde **Yerel betik'i** seçin. 

4. Onay ekranında bilgileri gözden geçirin ve ardından devam etmek için **İndir'i** seçin.

5. **Çıkarma paketini indir'i** seçin. Çıkarma paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz.

6. Betiği, gemiden çıkarmak istediğiniz her cihazda çalıştırın. Bu görevle ilgili yardıma mı ihtiyacınız var? Aşağıdaki kaynaklara bakın:   

   - Windows cihazları: [Yerel betik kullanarak Windows cihazlarını](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script) çıkarma 
   - Mac: [Mac'te kaldırma](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> Cihazı kullanıma almak, cihazların İş için Defender'a veri göndermeyi durdurmasına neden olur. Ancak, çıkarmadan önce alınan veriler altı (6) aya kadar saklanır.

## <a name="next-objective"></a>Sonraki hedef

[Windows cihazlarınız için korumayı ayarlayın](m365bp-protection-settings-for-windows-10-devices.md).
