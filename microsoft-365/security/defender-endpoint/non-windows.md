---
title: Windows dışı platformlar için Uç Nokta için Microsoft Defender
description: Windows olmayan platformlar için Uç Nokta için Microsoft Defender özellikleri hakkında bilgi edinin
keywords: windows, mac, macos, linux, android olmayan
search.product: eADQiWindows 10XVcnh
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
- m365-security
- m365solution-evalutatemtp
- highpri
- tier1
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 78ee819c1019ee65f11c926c8190fd835854290d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233562"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Windows dışı platformlar için Uç Nokta için Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Plan 1 ve Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft, sektör lideri uç nokta güvenlik özelliklerini Windows ve Windows Server'ın ötesine macOS, Linux, Android ve iOS'a genişletme yolculuğundadır.

Kuruluşlar çeşitli platformlarda ve cihazlarda tehditlerle karşı karşıya kalır. Ekiplerimiz, müşterilerimizin heterojen ortamlarını korumalarını ve güvenliğini sağlamalarını sağlamak için yalnızca Microsoft *için* değil, *Microsoft'tan* da güvenlik çözümleri oluşturmayı taahhüt etmiştir. Müşteri geri bildirimlerini dinliyor ve müşterilerimizin ihtiyaçlarını karşılayan çözümler oluşturmak için müşterilerimizle yakın iş ortaklığı kuruyoruz.

müşteriler Uç Nokta için Microsoft Defender ile Microsoft 365 Defender portalında, Windows ve Windows dışı platformlarda tüm tehditlerin ve uyarıların birleşik bir görünümünden yararlanarak ortamlarında olup bitenleri tam olarak görmelerini sağlar ve bu sayede tehditleri daha hızlı değerlendirip yanıtlamalarını sağlar.

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS üzerinde Uç Nokta için Microsoft Defender

macOS'ta Uç Nokta için Microsoft Defender, macOS'un en son yayınlanan üç sürümü için virüsten koruma, uç nokta algılama ve yanıt (EDR) ve güvenlik açığı yönetimi özellikleri sunar. Müşteriler çözümü Microsoft Endpoint Manager ve Jamf aracılığıyla dağıtabilir ve yönetebilir. MacOS'ta Microsoft Office uygulamalarında olduğu gibi, Mac'te Uç Nokta için Microsoft Defender güncelleştirmelerini yönetmek için De Microsoft Auto Update kullanılır. Önemli özellikler ve avantajlar hakkında bilgi için [duyurularımızı](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS) okuyun.

Kullanmaya başlama hakkında daha fazla bilgi için macOS üzerinde Uç Nokta için Defender [belgelerini ziyaret edin](microsoft-defender-endpoint-mac.md).

> [!NOTE]
> Aşağıdaki özellikler şu anda macOS uç noktalarında desteklenmemektedir:
>
> - Uç Nokta için Microsoft Defender için Güvenlik Yönetimi

## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender

Linux'ta Uç Nokta için Microsoft Defender, Linux sunucuları için önleyici virüsten koruma (AV), uç nokta algılama ve yanıt (EDR) ve güvenlik açığı yönetimi özellikleri sunar. Bu, aracıyı yapılandırmak ve yönetmek, taramaları başlatmak ve tehditleri yönetmek için tam bir komut satırı deneyimi içerir. En yaygın altı Linux Server dağıtımının son sürümlerini destekliyoruz: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS veya üzeri LTS, SLES 12+, Debian 9+ve Oracle Linux 7.2. Linux'ta Uç Nokta için Microsoft Defender Puppet, Ansible veya mevcut Linux yapılandırma yönetim aracınız kullanılarak dağıtılabilir ve yapılandırılabilir. Önemli özellikler ve avantajlar hakkında bilgi için [duyurularımızı](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux) okuyun.

Kullanmaya başlama hakkında daha fazla bilgi için Linux'ta Uç Nokta için Microsoft Defender [belgelerini ziyaret edin](microsoft-defender-endpoint-linux.md).


> [!NOTE]
> Aşağıdaki özellikler şu anda Linux uç noktalarında desteklenmemektedir:
>
> - Veri kaybı önleme
> - Uç Nokta için Microsoft Defender için Güvenlik Yönetimi

## <a name="microsoft-defender-for-endpoint-on-android"></a>Android'de Uç Nokta için Microsoft Defender

Android'de Uç Nokta için Microsoft Defender, Android 6.0 ve üzerini çalıştıran cihazlar için mobil tehdit savunması çözümümüzdür. Hem Android Kurumsal (İş Profili) hem de Cihaz Yöneticisi modları desteklenir. Android'de kimlik avı önleme, güvenli olmayan bağlantıları engelleme ve özel göstergelerin ayarlanması gibi web koruması sunuyoruz. Çözüm, kötü amaçlı yazılımları ve istenmeyebilecek uygulamaları (PUA) tarar ve Microsoft Endpoint Manager ve Koşullu Erişim ile tümleştirme yoluyla ek ihlal önleme özellikleri sunar. Önemli özellikler ve avantajlar hakkında bilgi için [duyurularımızı](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android) okuyun.

Kullanmaya başlama hakkında daha fazla bilgi için Android'de Uç Nokta için Microsoft Defender [belgelerini ziyaret edin](microsoft-defender-endpoint-android.md).

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS'ta Uç Nokta için Microsoft Defender

iOS'ta Uç Nokta için Microsoft Defender, iOS 11.0 ve üzerini çalıştıran cihazlar için mobil tehdit savunma çözümümüzdür. Müşterinin kiracısı içinde kayıtlı cihazlar (kayıtlı veya kaydı kaldırılmış) desteklenir. Hem denetimli hem de denetimsiz kayıtlı cihazlar desteklenir. iOS'ta kimlik avı önleme, güvenli olmayan bağlantıları engelleme ve özel göstergeler ayarlama ve jailbreak algılamayı içeren web koruması sunuyoruz. Önemli özellikler ve avantajlar hakkında daha fazla bilgi için [duyurularımızı](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS) okuyun.

Kullanmaya başlama hakkında daha fazla bilgi için iOS'ta Uç Nokta için Microsoft Defender [belgelerini ziyaret edin](microsoft-defender-endpoint-ios.md).

## <a name="licensing-requirements"></a>Lisans gereksinimleri

Uygun Lisanslı Kullanıcılar en fazla beş eşzamanlı cihazda Uç Nokta için Microsoft Defender kullanabilir. Uç Nokta için Microsoft Defender, bulut çözümü sağlayıcısından (CSP) satın alınabilir.

Müşteriler, Microsoft 365 A5/E5 veya Microsoft 365 Güvenliği kapsamında tek başına Uç Nokta için Microsoft Defender lisansı aracılığıyla macOS'ta Uç Nokta için Microsoft Defender edinebilir.

Android ve iOS'taki Uç Nokta için Microsoft Defender yakın zamanda duyurulan özellikleri, uygun lisanslı kullanıcılar için beş nitelikli cihazın parçası olarak yukarıda bahsedilen tekliflere dahildir.

Linux'ta Uç Nokta için Defender, hem ticari hem de eğitim müşterileri için kullanılabilen Uç Nokta için Defender Server SKU'su aracılığıyla kullanılabilir.

Fiyatlandırma ve ek uygunluk gereksinimleri için lütfen hesap ekibinize veya CSP'nize başvurun.
