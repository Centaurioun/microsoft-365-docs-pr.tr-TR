---
title: Microsoft Defender Virüsten Koruma bulut bloğu zaman aşımı süresini yapılandırma
description: Microsoft Defender Virüsten Koruma'nın bulut belirlemeyi beklerken bir dosyanın çalışmasını ne kadar süreyle engelleyeceklerini yapılandırabilirsiniz.
keywords: Microsoft Defender Virüsten Koruma, kötü amaçlı yazılımdan koruma, güvenlik, defender, bulut, zaman aşımı, blok, nokta, saniye
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: db2bddee6bae8c314dfcb1d721f5742a00b04584
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193135"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Bulut engelleme zaman aşımı dönemini yapılandırın

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

Microsoft Defender Virüsten Koruma şüpheli bir dosya bulduğunda, [Microsoft Defender Virüsten Koruma bulut hizmetini](cloud-protection-microsoft-defender-antivirus.md) sorgularken dosyanın çalışmasını engelleyebilir.

Dosyanın [engellendiği](configure-block-at-first-sight-microsoft-defender-antivirus.md) varsayılan süre 10 saniyedir. Güvenlik yöneticisiyseniz, dosyanın çalışmasına izin verilmeden önce bekleyebileceğiniz daha fazla zaman belirtebilirsiniz. Bulut bloğu zaman aşımı süresini uzatmak, Microsoft Defender Virüsten Koruma bulut hizmetinden düzgün bir belirleme almak için yeterli zaman olduğundan emin olmak için yardımcı olabilir.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Genişletilmiş bulut bloğu zaman aşımını kullanma önkoşulları

[İlk bakışta engelle](configure-block-at-first-sight-microsoft-defender-antivirus.md) ve uzun bir zaman aşımı süresi belirtebilmeniz için önce önkoşulları etkinleştirilmelidir.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager kullanarak genişletilmiş zaman aşımı süresini belirtme

[Microsoft Endpoint Manager'de bir uç nokta güvenlik ilkesiyle](/mem/intune/protect/endpoint-security-policy) bulut bloğu zaman aşımı süresini belirtebilirsiniz.

1. Endpoint Manager yönetim merkezine ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) gidin ve oturum açın.

2. **Uç nokta güvenliği'ni** seçin ve **yönet'in** altında **Virüsten Koruma'yı** seçin.

3. Virüsten koruma ilkesi seçin (veya oluşturun).

4. **Yapılandırma ayarları** bölümünde **Bulut koruması'nı** genişletin. Ardından **Microsoft Defender Virüsten Koruma Genişletilmiş Zaman Aşımı Saniye cinsinden** kutusunda, saniye cinsinden 1 saniye ile 50 saniye arasındadır. Belirttiğiniz her şey varsayılan 10 saniyeye eklenir.

5. (Bu adım isteğe bağlıdır) Virüsten koruma ilkenizde başka değişiklikler yapın. (Yardıma mı ihtiyacınız var? Bkz[. Microsoft Intune Microsoft Defender Virüsten Koruma ilkesi ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. **İleri'yi** seçin ve ilkenizi yapılandırmayı tamamlayın.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>grup ilkesi kullanarak genişletilmiş zaman aşımı süresini belirtme

Bulut denetimleri için genişletilmiş bir zaman aşımı belirtmek üzere grup ilkesi kullanabilirsiniz.

1. grup ilkesi yönetim bilgisayarınızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın

2. Yapılandırmak istediğiniz grup ilkesi Nesnesine sağ tıklayın ve **düzenle'yi** seçin.

3. **grup ilkesi Yönetim Düzenleyicisi'nde** **Bilgisayar yapılandırması'na** gidin ve **yönetim şablonları'nı** seçin.

3. Ağacı **Windows bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **MpEngine** olarak genişletin.

4. **Genişletilmiş bulut denetimini yapılandır'a** çift tıklayın ve seçeneğin etkinleştirildiğinden emin olun. 

   Bulut belirlemeyi beklerken dosyanın çalışmasını önlemek için ek süreyi belirtin. 1 saniyeden 50 saniyeye kadar olan ek süreyi saniye cinsinden belirtin. Belirttiğiniz her şey varsayılan 10 saniyeye eklenir.

5. **Tamam**'ı seçin.

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md) 
