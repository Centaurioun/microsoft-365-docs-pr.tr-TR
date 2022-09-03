---
title: Uç Nokta için Microsoft Defender - Mobil Tehdit Savunması
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender'da Mobile Threat Defense'e genel bakış
keywords: mobile, defender, Uç Nokta için Microsoft Defender, ios, mtd, android, security
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 0f94cab9a414a2d5dc8343ff01cd4dcb10636ef2
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67578090"
---
# <a name="microsoft-defender-for-endpoint---mobile-threat-defense"></a>Uç Nokta için Microsoft Defender - Mobil Tehdit Savunması

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android ve iOS'ta Uç Nokta için Microsoft Defender **mobil tehdit savunması çözümümüzdür (MTD).** Genellikle şirketler bilgisayarları güvenlik açıklarına ve saldırılara karşı korurken mobil cihazlar genellikle izlenmeyen ve korumasız hale getirilir. Mobil platformların uygulama yalıtımı ve incelenmiş tüketici uygulama mağazaları gibi yerleşik korumaları olduğu durumlarda, bu platformlar web tabanlı veya diğer gelişmiş saldırılara karşı savunmasız kalır. Daha fazla çalışan, cihazları iş ve hassas bilgilere erişmek için kullandığından, şirketlerin cihazları ve kaynaklarınızı cep telefonlarına yönelik giderek daha karmaşık saldırılara karşı korumak için bir MTD çözümü dağıtması zorunludur.

## <a name="key-capabilities"></a>Önemli özellikler

Android ve iOS'ta Uç Nokta için Microsoft Defender aşağıdaki temel özellikleri sağlar. En son özellikler ve avantajlar hakkında bilgi için [duyurularımızı](https://aka.ms/mdeblog) okuyun.

<br>

|Yeteneği|Açıklama|
|---|---|
|Web Koruması|Kimlik avı önleme, güvenli olmayan ağ bağlantılarını engelleme ve özel göstergeler için destek.|
|Kötü Amaçlı YazılımDan Koruma (yalnızca Android)|Kötü amaçlı uygulamaları tarama.|
|Jailbreak Algılama (yalnızca iOS)|Jailbreak uygulanmış cihazların algılanması.|
|Microsoft Defender Güvenlik Açığı Yönetimi (MDVM) |Eklenen mobil cihazların güvenlik açığı değerlendirmesi. Uç Nokta için Microsoft Defender'da Microsoft Defender Güvenlik Açığı Yönetimi hakkında daha fazla bilgi edinmek için bu [sayfayı](next-gen-threat-and-vuln-mgt.md) ziyaret edin. *Bu önizlemede yalnızca iOS işletim sistemi güvenlik açıklarının desteklendiğini unutmayın.*|
|Ağ Koruması *(Genel Önizleme)*| Wi-Fi ilgili tehditlere ve sahte sertifikalara karşı koruma; Intune'de kök CA ve özel kök CA sertifikalarını listeleme olanağı; uç noktalarla güven oluşturma.|
|Birleşik uyarı|Birleşik M365 güvenlik konsolundaki tüm platformlardan uyarılar|
|Koşullu Erişim, Koşullu başlatma|Riskli cihazların şirket kaynaklarına erişmesini engelleme. Uç Nokta için Defender risk sinyalleri, uygulama koruma ilkelerine (MAM) de eklenebilir|
|Gizlilik Denetimleri. Önizlemede (aşağıdaki nota bakın)|Uç Nokta için Microsoft Defender tarafından gönderilen verileri denetleyerek tehdit raporlarında gizliliği yapılandırın. *Gizlilik denetimlerinin şu anda yalnızca kayıtlı cihazlarda kullanılabildiğini unutmayın. Kaydı kaldırılan cihazlar için denetimler daha sonra eklenecek*|
|Microsoft Tunnel ile tümleştirme|Tek bir uygulamada güvenliği ve bağlantıyı etkinleştirmek için bir VPN ağ geçidi çözümü olan Microsoft Tunnel ile tümleştirebilir. Android'de kullanılabilir ve artık iOS'ta da genel kullanıma sunulmuştur.|

Tüm bu özellikler Uç Nokta için Microsoft Defender lisans sahipleri için kullanılabilir. Daha fazla bilgi için bkz [. Lisanslama gereksinimleri](minimum-requirements.md#licensing-requirements).


## <a name="overview-and-deploy"></a>Genel Bakış ve Dağıtma

Mobil cihazlarda Uç Nokta için Microsoft Defender dağıtımı Microsoft Endpoint Manager (MEM) aracılığıyla yapılabilir. MTD özelliklerine ve dağıtımına hızlı bir genel bakış için bu videoyu izleyin:

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMpiC]

### <a name="deploy"></a>Dağıtım

Aşağıdaki tabloda, Android ve iOS'ta Uç Nokta için Microsoft Defender nasıl dağıtılacağı özetlemektedir. Ayrıntılı belgeler için bkz. 
- [Android'de Uç Nokta için Microsoft Defender genel bakış](microsoft-defender-endpoint-android.md) ve
- [iOS'ta Uç Nokta için Microsoft Defender’a genel bakış](microsoft-defender-endpoint-ios.md)

**Android**

|Kayıt türü     |Ayrıntılar      |
|--------------------|-------------|
|Intune Unified Endpoint Manager (Microsoft Endpoint Manager) ile Android Kurumsal|[Android Kurumsal kayıtlı cihazlarda dağıtma](android-intune.md#deploy-on-android-enterprise-enrolled-devices)|
|Intune Birleşik Endpoint Manager (Microsoft Endpoint Manager) ile Cihaz Yöneticisi|[Cihaz Yöneticisi tarafından kaydedilen cihazlarda dağıtma](android-intune.md#deploy-on-device-administrator-enrolled-devices)|
|Diğer Birleşik Uç Nokta Yöneticileri tarafından yönetilen yönetilmeyen KCG VEYA cihazlar / Uygulama koruma ilkesini ayarlama (MAM)|[Uygulama koruma ilkesinde (MAM) Defender risk sinyallerini yapılandırma](android-configure-mam.md)|

**iOS**

|Kayıt türü     |Ayrıntılar      |
|--------------------|-------------|
|Intune Birleşik Endpoint Manager sahip denetimli cihazlar (Microsoft Endpoint Manager)|1. [iOS mağazası uygulaması olarak dağıtma](ios-install.md)<br/>2. [Denetimli iOS cihazları için VPN olmadan Web Koruması kurma](ios-install.md#complete-deployment-for-supervised-devices)|
|Intune UEM(Microsoft Endpoint Manager) ile kaydedilen denetimsiz (KCG) cihazlar|[iOS mağazası uygulaması olarak dağıtma](ios-install.md)|
|Yönetilmeyen KCG VEYA diğer UEM'ler tarafından yönetilen cihazlar / Uygulama koruma ilkesi (MAM) kurulumu|[Uygulama koruma ilkesinde (MAM) Defender risk sinyallerini yapılandırma](ios-install-unmanaged.md)|

### <a name="end-user-onboarding"></a>Son kullanıcı ekleme

- [iOS kayıtlı cihazlar için Sıfır dokunma eklemeyi yapılandırma](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint): Yöneticiler, kullanıcının uygulamayı açmasına gerek kalmadan kayıtlı iOS cihazlarına sessizce Uç Nokta için Microsoft Defender eklemek için sıfır dokunmayla yüklemeyi yapılandırabilir. 

- [Kullanıcı ekleme işlemini zorunlu kılmak için Koşullu Erişimi yapılandırın](android-configure.md#conditional-access-with-defender-for-endpoint-on-android): Bu, son kullanıcıların dağıtıldıktan sonra Uç Nokta için Microsoft Defender uygulamasına eklendiğinden emin olmak için uygulanabilir. Uç Nokta için Defender risk sinyalleriyle koşullu erişimi yapılandırma hakkında hızlı bir tanıtım için bu videoyu izleyin. 

  <br/>

  > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMwR1]

### <a name="simplify-onboarding"></a>Ekleme işlemini basitleştirme

- [iOS - Zero-Touch Ekleme](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint)
- [Android Kurumsal - Her zaman açık VPN kurulumu](android-intune.md#auto-setup-of-always-on-vpn).
- [iOS - VPN profilinin otomatik kurulumu](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)

## <a name="pilot-evaluation"></a>Pilot değerlendirme

Uç Nokta için Microsoft Defender ile mobil tehdit savunmasını değerlendirirken, hizmeti daha büyük bir cihaz kümesine dağıtmaya devam etmeden önce belirli ölçütlerin karşılandığını doğrulayabilirsiniz. Çıkış ölçütlerini tanımlayabilir ve yaygın olarak dağıtmadan önce bunların karşılandığından emin olabilirsiniz.

Bu, hizmet dağıtılırken ortaya çıkabilecek olası sorunları azaltmaya yardımcı olur. Yardımcı olabilecek bazı testler ve çıkış ölçütleri şunlardır:

- Cihazlar cihaz envanter listesinde gösterilir: Mobil cihazda Uç Nokta için Defender'ın başarıyla eklendikten sonra, cihazın [güvenlik konsolundaki](https://security.microsoft.com) Cihaz Envanteri'nde listelendiğini doğrulayın.

- Android cihazda kötü amaçlı yazılım algılama testi çalıştırma: Google play store'dan herhangi bir test virüs uygulamasını yükleyin ve Uç Nokta için Microsoft Defender tarafından algılandığını doğrulayın. Bu test için kullanılabilecek örnek bir uygulama aşağıda verilmiştir: [Test virüsü](https://play.google.com/store/apps/details?id=com.antivirus&hl=en_US&gl=US). İş profiline sahip Android Kurumsal'da yalnızca iş profilinin desteklendiğini unutmayın.

- Kimlik avı testi çalıştırma: adresine gidin https://smartscreentestratings2.net ve Uç Nokta için Microsoft Defender tarafından engellendiğini doğrulayın. İş profiline sahip Android Kurumsal'da yalnızca iş profilinin desteklendiğini unutmayın.

- Uyarılar panoda görünür: Yukarıdaki algılama testlerine yönelik uyarıların [güvenlik konsolunda](https://security.microsoft.com) göründüğünü doğrulayın.

## <a name="configure"></a>Yapılandırın

- [Android özelliklerini yapılandırma](android-configure.md)
- [iOS özelliklerini yapılandırın](ios-configure-features.md)
- [Denetimli iOS cihazları için VPN olmadan Web Koruması yapılandırma](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="resources"></a>Kaynaklar

- [Android'de Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-android.md)
- [iOS'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-ios.md)
- [Duyurularımızı](https://aka.ms/mdeblog) okuyarak yaklaşan sürümler hakkında bilgi sahibi olun.

