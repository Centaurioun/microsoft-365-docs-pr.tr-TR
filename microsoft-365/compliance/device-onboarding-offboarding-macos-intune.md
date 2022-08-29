---
title: Microsoft Intune kullanarak macOS cihazlarını Microsoft Purview çözümlerine ekleme ve çıkarma
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Intune kullanarak macOS cihazlarını Microsoft Purview çözümlerine ekleme ve çıkarma hakkında bilgi edinin
ms.openlocfilehash: f71cc8f5ef0a0d9a251dca0b8da5e7797f553e0f
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2022
ms.locfileid: "67444973"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-purview-solutions-using-intune"></a>Intune kullanarak macOS cihazlarını Microsoft Purview çözümlerine ekleme ve çıkarma

macOS cihazlarını Microsoft Purview çözümlerine eklemek için Intune kullanabilirsiniz.

> [!IMPORTANT]
> macOS ***cihazlarınıza dağıtılmış*** Uç Nokta için Microsoft Defender (MDE) yoksa bu yordamı kullanın

**Şunlar için geçerlidir:**

- [Uç nokta veri kaybı önleme (DLP)](./endpoint-dlp-learn-about.md)
- [İçeriden risk yönetimi](insider-risk-management.md)

## <a name="before-you-begin"></a>Başlamadan önce

- [macOS cihazlarınızın Intune eklenip Şirket Portalı](/mem/intune/fundamentals/deployment-guide-platform-macos) [uygulamasına](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) kaydedildiğinden emin olun. 
- [Microsoft Endpoint Manager merkezine](https://endpoint.microsoft.com/#home) erişiminiz olduğundan emin olun.
- Bu, macOS'un en son üç ana sürümünü destekler.
- Yapılandırma güncelleştirmelerini atayacağınız kullanıcı gruplarını oluşturun.
- macOS cihazlarınıza v95+ Edge tarayıcısını yükleme 


## <a name="onboard-macos-devices-into-microsoft-purview-solutions-using-microsoft-intune"></a>Microsoft Intune kullanarak macOS cihazlarını Microsoft Purview çözümlerine ekleme

MacOS cihazını Uyumluluk çözümlerine ekleme çok aşamalı bir işlemdir.

1. [Sistem yapılandırma profilleri oluşturma](#create-system-configuration-profiles)
1. [Cihaz ekleme paketini alma](#get-the-device-onboarding-package)
1. [Mobileconfig ve ekleme paketlerini dağıtma](#deploy-the-mobileconfig-and-onboarding-packages)
1. [Uygulamayı yayımlama](#publish-application)
<!--1. [Enable system extension](#enable-system-extension)-->


### <a name="create-system-configuration-profiles"></a>Sistem yapılandırma profilleri oluşturma

1. Bu yordam için bu dosyalara ihtiyacınız olacaktır. 

|için gereken dosya |Kaynak |
|---------|---------|
Sistem mobil yapılandırma dosyası | [mdatp-nokext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) İçeriği kopyalayıp bir metin dosyasına yapıştırın. Dosyayı yalnızca **mobileconfig** uzantısıyla kaydedin; .txt uzantısına sahipse tanınmaz.|
MDE tercihleri| [com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig). İçeriği kopyalayıp bir metin dosyasına yapıştırın. Dosyayı yalnızca **mobileconfig** uzantısıyla kaydedin; .txt uzantısına sahipse tanınmaz.

### <a name="get-the-device-onboarding-package"></a>Cihaz ekleme paketini alma

1. **Microsoft Purview Uyumluluk merkezinde** **Ayarlar** > **Cihaz Ekleme'yi** açın ve **Ekleme'yi** seçin.
 
1. **Ekleme işlemini başlatmak için İşletim sistemini seçin** için **macOS'u** seçin.
 
1. **Dağıtım yöntemi** için **Mobil Cihaz Yönetimi/Microsoft Intune'ı** seçin.
 
1. **Ekleme paketini indir'i** seçin. 

1. Zip dosyasını ayıklayın ve *Intune* klasörünü açın. Bu, *DeviceComplianceOnboarding.xml* dosyasındaki ekleme kodunu içerir.

<!--|accessibility |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
full disk access     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|Network filer| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|System extensions |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE preference     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU preference|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|Installation package     |downloaded from the compliance portal **Installation package**, file name *\*wdav.pkg*\* |

> [!TIP]
> You can download the *.mobileconfig* files individually or in [single combined file](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) that contains:
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - system extensions
>
>If any of these individual files is updated, you'd need to download the either the combined file again or the single updated file individually.-->

### <a name="deploy-the-mobileconfig-and-onboarding-packages"></a>Mobileconfig ve ekleme paketlerini dağıtma

1. **Microsoft Endpoint Manager merkezi** > **Cihazlar** > **Yapılandırma profillerini** açın.

1. Seç: **Profil oluştur** 

1. Seçin:
    1. **Platform = macOS**
    1. **Profil türü = Şablonlar**
    1. **Şablon adı = Özel**

1. **Oluştur'u** seçin

1. Bu örnekteki *SystemMobileConfig* gibi bir profil adı seçin. **İleri**'yi seçin.

1. 1. adımda kopyalayıp kaydettiğiniz **mdatp-nokext.mobileconfig** dosyasını yapılandırma profili dosyası olarak seçin.

1. **İleri'yi** seçin

1. **Atamalar** sekmesinde, bu yapılandırmaları dağıtmak istediğiniz grubu ekleyin ve **İleri'yi** seçin.

1. Ayarlarınızı gözden geçirin ve **oluştur'u** seçerek yapılandırmayı dağıtın.

1. Aşağıdakiler için profil oluşturmak için 2-9 arası adımları yineleyin:
    1. **DeviceComplianceOnboarding.xml** dosyası. *Purview Cihaz Ekleme Paketi olarak adlandır*
    1. **com.microsoft.wdav.mobileconfig** dosyası. *Uç Nokta Cihaz Tercihleri* olarak adlandır
 
1. **Cihaz** > **Yapılandırma profillerini** açın, oluşturduğunuz profilleri orada görmeniz gerekir.

1. **Yapılandırma profilleri** sayfasında, yeni oluşturduğunuz profili (örneğin *SystemMobileConfig*) seçin ve cihaz listesini ve yapılandırma profilinin dağıtım durumunu görmek için **Cihaz durumu'nu** seçin.

### <a name="publish-application"></a>Uygulamayı yayımlama

Microsoft Endpoint DLP, macOS'ta Uç Nokta için Microsoft Defender (MDE) bileşeni olarak yüklenir. Bu yordam, cihazları Microsoft Purview çözümlerine ekleme için geçerlidir

1. [Microsoft Endpoint Manager yönetim merkezinde](https://endpoint.microsoft.com/) **Uygulamalar'ı** açın.

1. Platforma göre > macOS > Ekle'yi seçin.

1. **Uygulama türü****macOS'u**= seçin, **Seç'e** tıklayın.

1. Varsayılan değerleri koru'ya tıklayın, **İleri'ye** tıklayın.

1. Ödev ekleyin, **İleri'ye** tıklayın.

1. Gözden Geçir ve **Oluştur'u seçin**.

1. Tüm uygulamalar listesinde görmek için **MacOS** **platformuna** \> göre **Uygulamalar** \> sayfasını ziyaret edebilirsiniz.

<!--## Offboard macOS devices using Intune PINGING PG FOR THIS PROCEDURE

> [!NOTE]
> Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to six months.

1. In **Microsoft Endpoint Manager center**, open **Devices** > **Configuration profiles**, you should see your created profiles there.

1. In the **Configuration profiles** page, choose the *wdav.pkg.intunemac* profile.

1. Choose **Device status** to see a list of devices and the deployment status of the configuration profile

1. Open **Properties** and **Assignments**

1. Remove the group from the assignment. This will uninstall the *wdav.pkg.intunemac* package and offboard the macOS device from Compliance solutions.-->
