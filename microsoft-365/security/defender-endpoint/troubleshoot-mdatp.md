---
title: Uç Nokta için Microsoft Defender sorunlarını giderin
description: Hizmete erişmeye çalışırken karşılaşılan sunucu hataları gibi bilinen sorunların çözümlerini ve geçici çözümlerini bulun.
keywords: sorun giderme Uç Nokta için Microsoft Defender, sunucu hatası, erişim reddedildi, geçersiz kimlik bilgileri, veri yok, pano portalı, izin ver, olay görüntüleyicisi
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
search.appverid: met150
ms.openlocfilehash: eabaf627d882544d377e0cea61d83c5858fe3ac7
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690820"
---
# <a name="troubleshoot-service-issues"></a>Hizmet sorunlarını giderin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Bu bölümde, Uç Nokta için Microsoft Defender hizmetini kullanırken ortaya çıkabilecek sorunlar ele alınıyor.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Sunucu hatası - Geçersiz kimlik bilgileri nedeniyle erişim reddedildi

Hizmete erişmeye çalışırken bir sunucu hatasıyla karşılaşırsanız tarayıcı tanımlama bilgisi ayarlarınızı değiştirmeniz gerekir.
Tarayıcınızı tanımlama bilgilerine izin verecek şekilde yapılandırın.

## <a name="elements-or-data-missing-on-the-portal"></a>Portalda eksik öğeler veya veriler

Microsoft 365 Defender bazı öğeler veya veriler eksikse ara sunucu ayarlarının bunu engellemesi mümkündür.

Proxy izin verilenler listesine eklendiğinden emin `*.security.microsoft.com` olun.

> [!NOTE]
> Aşağıdaki uç noktaları eklerken HTTPS protokollerini kullanmanız gerekir.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Uç Nokta için Microsoft Defender hizmeti Olay Görüntüleyicisi olay veya hata günlüklerini gösterir

Uç Nokta için Microsoft Defender hizmeti tarafından bildirilen olay kimliklerinin listesi için bkz. [Olay Görüntüleyicisi kullanarak olayları ve hataları gözden geçirme](event-error-codes.md). Makale ayrıca olay hatalarıyla ilgili sorun giderme adımlarını da içerir.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Uç Nokta için Microsoft Defender hizmeti yeniden başlatmadan sonra başlatılamıyor ve 577 hatasını gösteriyor

Ekleme cihazları başarıyla tamamlanırsa ancak Uç Nokta için Microsoft Defender yeniden başlatmadan sonra başlamıyorsa ve hata 577 gösteriyorsa, Windows Defender bir ilke tarafından devre dışı bırakılmadığını denetleyin.

Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma'nın ilke tarafından devre dışı bırakılmadığından emin olun](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Bölgesel biçimlerle ilgili bilinen sorunlar

### <a name="date-and-time-formats"></a>Tarih ve saat biçimleri

Saat ve tarih biçimleriyle ilgili bazı bilinen sorunlar vardır.

Aşağıdaki tarih biçimleri desteklenir:

- AA/gg/yyyy
- dd/AA/yyyy

Aşağıdaki tarih ve saat biçimleri şu anda desteklenmiyor:

- Tarih biçimi yyyy/AA/gg
- Tarih biçimi dd/AA/yy
- yy ile tarih biçimi. Sadece yyyy gösterecektir.
- SS:dd:ss saat biçimi desteklenmez (12 saat/PM biçimi desteklenmez). Yalnızca 24 saatlik biçim desteklenir.

### <a name="use-of-comma-to-indicate-thousand"></a>Bini belirtmek için virgül kullanımı

Sayılarda ayırıcı olarak virgül kullanımı desteği desteklenmez. Bir sayının bini belirtmek için virgülle ayrıldığı bölgeler, yalnızca ayırıcı olarak nokta kullanımını görür. Örneğin, 15,5 K 15,5 K olarak görüntülenir.

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Uç Nokta için Microsoft Defender kiracı Avrupa'da otomatik olarak oluşturuldu

Sunucuları izlemek için Bulut için Microsoft Defender'ı kullandığınızda, otomatik olarak bir Uç Nokta için Microsoft Defender kiracısı oluşturulur. Uç Nokta için Microsoft Defender verileri varsayılan olarak Avrupa'da depolanır.

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](troubleshoot-onboarding.md)
- [Olay Görüntüleyicisi kullanarak olayları ve hataları gözden geçirme](event-error-codes.md)
