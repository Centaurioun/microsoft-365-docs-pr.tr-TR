---
title: İstenmeyen yazılım
ms.reviewer: ''
description: İstenmeyen yazılımların izniniz olmadan varsayılan ayarlarınızı nasıl değiştirebileceği ve kendinizi korumak için yapabilecekleriniz hakkında bilgi edinin.
keywords: güvenlik, kötü amaçlı yazılım, koruma, istenmeyen, yazılım, alter, enfekte, istenmeyen yazılım, yazılım paketleyiciler, tarayıcı değiştiriciler, gizlilik, güvenlik, bilgi işlem deneyimi, bulaşmayı önleme, çözüm, WDSI, MMPC, Microsoft Kötü Amaçlı Yazılımdan Koruma Merkezi, virüs araştırma tehditleri, araştırma kötü amaçlı yazılımları, Pc koruması, bilgisayar bulaşması, virüs bulaşması, açıklamalar, düzeltme, en son tehditler
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: ab64cf13c2f219296ab6ee0831714098fd08e73f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640378"
---
# <a name="unwanted-software"></a>İstenmeyen yazılım

İstenmeyen yazılımlar, onayınız veya denetiminiz olmadan Windows deneyimini değiştiren programlardır. Bu, değiştirilmiş gözatma deneyimi, indirmeler ve yükleme üzerinde denetim eksikliği, yanıltıcı iletiler veya Windows ayarlarında yetkisiz değişiklikler olabilir.

## <a name="how-unwanted-software-works"></a>İstenmeyen yazılımlar nasıl çalışır?

İstenmeyen yazılımlar, kullanıcı İnternet'ten uygulama arayıp indirdiğinde ortaya çıkar. Bazı uygulamalar yazılım paketleyicileridir ve bu da diğer uygulamalarla birlikte paketlendiği anlamına gelir. Sonuç olarak, özgün uygulama indirildiğinde diğer programlar yanlışlıkla yüklenebilir.

İstenmeyen yazılımların bazı göstergeleri şunlardır:

- Yüklemediğiniz ve kaldırılması zor olabilecek programlar var

- Tarayıcı özellikleri veya ayarları değişti ve bunları görüntüleyemez veya değiştiremezsiniz

- Cihazınızın durumu veya dosyalar ve programlar hakkında çok fazla ileti var

- Kolayca kapatılamayan reklamlar var

Bazı göstergelerin tanınması daha zordur çünkü bunlar daha az kesintiye neden olur, ancak yine de istenmeyendir. Örneğin, istenmeyen yazılımlar belirli reklamları görüntülemek, gözatma etkinliklerini izlemek veya tarayıcının denetimini kaldırmak için web sayfalarını değiştirebilir.

Microsoft, istenmeyen yazılımları tanımlamak için kapsamlı bir [değerlendirme ölçütü](criteria.md) kullanır.

## <a name="how-to-protect-against-unwanted-software"></a>İstenmeyen yazılımlara karşı koruma

İstenmeyen yazılım bulaşmasını önlemek için yalnızca resmi web sitelerinden veya Microsoft Store'dan yazılım indirin. Üçüncü taraf sitelerden yazılım indirmeye karşı dikkatli olun.

İnternet'e göz atarken [Microsoft Edge'i](/microsoft-edge/deploy/index) kullanın. Microsoft Edge, tarayıcı ayarlarınızı değiştirebilen tarayıcı değiştiricilerini etkili bir şekilde engelleyen ek korumalar içerir. Microsoft Edge, [Windows Defender SmartScreen](/microsoft-edge/deploy/index) (Internet Explorer tarafından da kullanılır) kullanarak istenmeyen yazılımları barındıran bilinen web sitelerini de engeller.

[Windows 10'da Microsoft Defender Virüsten Koruma'yı](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10) etkinleştirin. Tehditlere karşı gerçek zamanlı koruma sağlar ve bilinen istenmeyen yazılımları algılar ve kaldırır.

Windows 7 veya Windows Vista'da gerçek zamanlı koruma için [Microsoft Security Essentials'ı](https://www.microsoft.com/download/details.aspx?id=5201) indirin.

Daha genel ipuçları için bkz. [Kötü amaçlı yazılım bulaşmasını önleme](prevent-malware-infection.md).

### <a name="what-should-i-do-if-my-device-is-infected"></a>Cihazıma virüs bulaşmışsa ne yapmalıyım? 

İstenmeyen yazılıma sahip olduğunuzdan şüpheleniyorsanız dosyaları [analiz için gönderebilirsiniz](https://www.microsoft.com/wdsi/filesubmission).

İstenmeyen bazı yazılımlar kaldırma girdileri ekler. Bu, **bunları Ayarlar'ı kullanarak kaldırabileceğiniz** anlamına gelir.
1. Başlangıç düğmesini seçin
2. **Ayarlar > Uygulamalar > Uygulamalar & özellikleri'ne** gidin.
3. Kaldırmak istediğiniz uygulamayı seçin ve **kaldır'a** tıklayın.

İstenmeyen yazılım bulaşma belirtilerini yalnızca yakın zamanda fark ettiyseniz, uygulamaları yükleme tarihine göre sıralamayı ve ardından yüklemediğiniz en son uygulamaları kaldırmayı düşünün.

Tarayıcılarınızda Internet Explorer, Firefox veya Chrome gibi **tarayıcı eklentilerini de kaldırmanız** gerekebilir.

Tehdit kaldırma işleminin başarısız olması durumunda [kötü amaçlı yazılım algılama ve kaldırma sorunlarını giderme](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware) hakkında bilgi edinin.