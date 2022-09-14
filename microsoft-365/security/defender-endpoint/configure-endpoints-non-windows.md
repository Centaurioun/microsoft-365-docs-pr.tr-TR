---
title: Windows olmayan cihazları Uç Nokta için Microsoft Defender hizmetine ekleme
description: Windows olmayan cihazları, algılayıcı verilerini Uç Nokta için Microsoft Defender hizmetine gönderebilecekleri şekilde yapılandırın.
keywords: Windows dışı cihazları ekleme, macos, linux, cihaz yönetimi, Uç Nokta için Microsoft Defender cihazları yapılandırma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 95ed620bf8b5af456174c232d90e05e6fbd547fd
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67680409"
---
# <a name="onboard-non-windows-devices"></a>Windows dışı diğer cihazları ekleyin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platform**
- macOS
- Linux

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-nonwindows-abovefoldlink)

Uç Nokta için Defender, Windows ve Windows dışı platformlar için merkezi bir güvenlik işlemleri deneyimi sağlar. Microsoft 365 Defender'da desteklenen çeşitli işletim sistemlerinden (OS) gelen uyarıları görebilir ve kuruluşunuzun ağını daha iyi koruyabilirsiniz.

Tümleştirmenin çalışması için Uç Nokta için Defender ile uyumlu tam Linux dağıtımlarını ve macOS sürümlerini bilmeniz gerekir. Daha fazla bilgi için bkz.:

- [Linux sistem gereksinimlerini Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md#system-requirements)
- [macOS sistem gereksinimlerini Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Windows olmayan cihazları ekleme

Windows olmayan cihazları eklemek için aşağıdaki adımları uygulamanız gerekir:

1. Tercih ettiğiniz ekleme yöntemini seçin:

   - macOS cihazlarda, Uç Nokta için Microsoft Defender veya üçüncü taraf bir çözüm aracılığıyla eklemeyi seçebilirsiniz. Daha fazla bilgi için bkz. [Mac'te Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).

   - Windows olmayan diğer cihazlar için **Üçüncü taraf tümleştirmesi aracılığıyla Windows dışı cihazları ekleme'yi** seçin.
    1. Gezinti bölmesinde **İş Ortakları ve API'ler** \> **İş Ortağı Uygulamaları'nı** seçin. Üçüncü taraf çözümünün listelendiğinden emin olun.
    2. **İş Ortağı Uygulamaları** sayfasında Windows dışı cihazlarınızı destekleyen iş ortağını seçin.
    3. İş ortağının sayfasını açmak için **Görünüm'e** tıklayın. Sayfada sağlanan yönergeleri izleyin.
    4. Bir hesap oluşturduktan veya iş ortağı çözümüne abone olduktan sonra, kuruluşunuzdaki bir kiracı genel Yönetici iş ortağı uygulamasından gelen izin isteğini kabul etmesinin istendiği bir aşamaya gelmelisiniz. İzin isteğini dikkatle okuyarak ihtiyacınız olan hizmetle uyumlu olduğundan emin olun.

2. Üçüncü taraf çözümün yönergelerini izleyerek bir algılama testi çalıştırın.

## <a name="offboard-non-windows-devices"></a>Windows olmayan cihazları kullanıma açma

macOS ve Linux cihazları için Uç Nokta için Microsoft Defender aracılığıyla kullanıma almayı seçebilirsiniz. Çıkarma İşlemi'ni başlatmak için gezinti bölmesinde **Ayarlar** \> **Çıkarılmış** \> **İşletim Sistemi Seç'i** seçin.

Üçüncü taraf tümleştirmesini devre dışı bırakarak Windows dışı cihazları da kullanıma alabilirsiniz. [Üçüncü taraf çözümleri tümleştirerek](https://security.microsoft.com/interoperability/partners) Windows dışı platformlar çalıştıran cihazlar için kapsamı etkinleştirin.

## <a name="related-topics"></a>İlgili konular
- [Windows cihazlarını ekleme](configure-endpoints.md)
- [Sunucuları ekleme](configure-server-endpoints.md)
- [Ara sunucu ve internet bağlantısı ayarlarını yapılandırın](configure-proxy-internet.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
