---
title: Şifreleme hakkında teknik başvuru ayrıntıları
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- tier1
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 ve Microsoft 365'te şifreleme için kullanılan çeşitli sertifikalar, teknolojiler ve Aktarım Katmanı Güvenliği (TLS) şifreleme paketleri hakkında bilgi edinin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a26d54a4532c7c6fe5c07f59368bd143a53b5285
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644757"
---
# <a name="technical-reference-details-about-encryption"></a>Şifreleme hakkında teknik başvuru ayrıntıları

[Office 365'te şifreleme](encryption.md) için kullanılan sertifikalar, teknolojiler ve TLS şifreleme paketleri hakkında bilgi edinmek için bu makaleye bakın. Bu makalede planlı kullanımdan kaldırma işlemleriyle ilgili ayrıntılar da sağlanır.
  
- Genel bakış bilgileri arıyorsanız bkz [. Office 365'te şifreleme](encryption.md).
- Kurulum bilgilerini arıyorsanız bkz. [Office 365 Kurumsal'da şifrelemeyi ayarlama](set-up-encryption.md).
- Windows'un belirli sürümleri tarafından desteklenen şifre paketleri hakkında bilgi için bkz. [TLS/SSL'de Şifreleme Paketleri (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 sertifika sahipliği ve yönetimi

Office 365 için sertifika satın almanız veya bakımını yapmanız gerekmez. Bunun yerine, Office 365 kendi sertifikalarını kullanır.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Geçerli şifreleme standartları ve planlanan kullanımdan kaldırmalar

Office 365, sınıfının en iyisi şifreleme sağlamak için desteklenen şifreleme standartlarını düzenli olarak inceler. Bazen eski standartlar eski ve daha az güvenli hale geldikçe kullanım dışı kalır. Bu makalede, şu anda desteklenen şifreleme paketleri ve diğer standartlar ve planlı kullanımdan kaldırmalarla ilgili ayrıntılar açıklanmaktadır.

## <a name="fips-compliance-for-office-365"></a>Office 365 için FIPS uyumluluğu

Office 365 tarafından desteklenen tüm şifreleme paketleri FIPS 140-2 altında kabul edilebilir algoritmalar kullanır. Office 365, FIPS doğrulamalarını Windows'tan devralır (Schannel aracılığıyla). Schannel hakkında daha fazla bilgi için bkz. [TLS/SSL 'de Şifreleme Paketleri (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 tarafından desteklenen TLS sürümleri

TLS ve TLS'den önce gelen SSL, bilgisayarlar arasındaki bağlantıyı şifrelemek için güvenlik sertifikaları kullanarak ağ üzerinden iletişimin güvenliğini sağlayan şifreleme protokolleridir. Office 365 TLS sürüm 1.2'yi (TLS 1.2) destekler.

TLS sürüm 1.3 (TLS 1.3), bazı hizmetler tarafından desteklenir.

> [!IMPORTANT]
> TLS sürümlerinin kullanım dışı bırakıldığını ve daha yeni sürümlerin kullanılabildiği durumlarda kullanım dışı bırakılan *sürümlerin kullanılmaması gerektiğini* unutmayın. Eski hizmetleriniz TLS 1.0 veya 1.1 gerektirmiyorsa bunları devre dışı bırakmalısınız.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>TLS 1.0 ve 1.1 kullanımdan kaldırma desteği

Office 365, 31 Ekim 2018'de TLS 1.0 ve 1.1'i desteklemeyi durdurdu. GCC High ve DoD ortamlarında TLS 1.0 ve 1.1'i devre dışı bırakmayı tamamladık. 15 Ekim 2020'den itibaren Dünya çapında ve GCC ortamlarında TLS 1.0 ve 1.1'i devre dışı bırakmaya başladık ve önümüzdeki haftalar ve aylar boyunca kullanıma sunulmaya devam edeceğiz.

Office 365 ve Microsoft 365 hizmetlerine güvenli bir bağlantı sağlamak için tüm istemci-sunucu ve tarayıcı-sunucu birleşimleri TLS 1.2 ve modern şifreleme paketlerini kullanır. Belirli istemci-sunucu ve tarayıcı-sunucu kombinasyonlarını güncelleştirmeniz gerekebilir. Bu değişikliğin sizi nasıl etkilediğini öğrenmek için bkz. [Office 365'te TLS 1.2'nin zorunlu kullanımına hazırlanma](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>3DES desteğini kullanımdan kaldırma

31 Ekim 2018'den bu yana, Office 365 artık Office 365 ile iletişim için 3DES şifreleme paketlerinin kullanımını desteklememektedir. Daha açık belirtmek gerekirse, Office 365 artık TLS_RSA_WITH_3DES_EDE_CBC_SHA şifreleme paketini desteklememektedir. Bu şifre paketi 28 Şubat 2019'dan bu yana Office 365'te devre dışı bırakılmıştır. Office 365 ile iletişim kuran istemciler ve sunucular desteklenen şifrelemelerden birini veya daha fazlasını desteklemelidir. Desteklenen şifrelemelerin listesi için bkz. [Office 365 tarafından desteklenen TLS şifreleme paketleri](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365'te SHA-1 sertifika desteğini kullanımdan kaldırma

Haziran 2016'dan bu yana, Office 365 artık giden veya gelen bağlantılar için sha-1 sertifikası kabul etmemektedir. Sertifika zincirinde SHA-2 (Güvenli Karma Algoritması 2) veya daha güçlü bir karma algoritması kullanın.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 tarafından desteklenen TLS şifre paketleri

TLS, güvenli bağlantılar kurmak için *şifreleme paketlerini*, şifreleme algoritmaları koleksiyonlarını kullanır. Office 365, aşağıdaki tabloda listelenen şifre paketlerini destekler. Tabloda şifreleme paketleri güç sırasına göre listelenir ve en güçlü şifreleme paketi ilk sırada listelenir.

Office 365, önce en güvenli şifreleme paketini kullanarak bağlanmayı deneyerek bir bağlantı isteğine yanıt verir. Bağlantı çalışmazsa, Office 365 listedeki en güvenli ikinci şifreleme paketini dener, vb. Hizmet, bağlantı kabul edilene kadar listede devam eder. Benzer şekilde, Office 365 bir bağlantı istediğinde, alıcı hizmet TLS'nin kullanılıp kullanılmayacağını ve hangi şifre paketinin kullanılacağını seçer.

| Şifreleme paketi adı | Anahtar değişimi algoritması/gücü | İletme gizliliği | Şifreleme/güç | Kimlik doğrulama algoritması/gücü |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | Evet  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | Evet  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | Evet  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | Evet  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | Evet  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | Evet  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | Hayır   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | Hayır   <br/> | AES/256  <br/> | RSA/112  <br/> |

Aşağıdaki şifreleme paketleri, kullanımdan kaldırılana kadar TLS 1.0 ve 1.1 protokollerini desteklemektedir. Kullanımdan kaldırma tarihi 15 Ocak 2020 olan GCC High ve DoD ortamları için. Tarih 15 Ekim 2020 olan Dünya çapında ve GCC ortamları için.

| Protokol | Şifreleme paketi adı | Anahtar değişimi algoritması/gücü | İletme gizliliği | Şifreleme/güç | Kimlik doğrulama algoritması/gücü | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | Evet  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | Evet  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | Hayır   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | Hayır   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | Hayır   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | Hayır   <br/> | AES/256  <br/> | RSA/112  <br/> |

Bazı Office 365 ürünleri (Microsoft Teams dahil) TLS bağlantılarını sonlandırmak ve ağ trafiğini verimli bir şekilde yönlendirmek için [Azure Front Door](/azure/frontdoor/front-door-overview) kullanır. [Azure Front Door tarafından TLS 1.2 üzerinden desteklenen şifre paketlerinden](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) en az birinin bu ürünlere başarıyla bağlanabilmesi için etkinleştirilmesi gerekir. Windows 10 ve üzeri için, daha iyi güvenlik için ECDHE şifreleme paketlerinden birini veya her ikisini etkinleştirmenizi öneririz. Windows 7, 8 ve 8.1, Azure Front Door'un ECDHE şifreleme paketleriyle uyumlu değildir ve DHE şifreleme paketleri bu işletim sistemleriyle uyumluluk için sağlanmıştır.

## <a name="related-articles"></a>İlgili makaleler

[Windows 10 v1903'te TLS Şifreleme Paketleri](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365'de şifreleme](encryption.md)
  
[Office 365 Kurumsal'de şifrelemeyi ayarlama](set-up-encryption.md)
  
[Windows güvenlik durumu güncelleştirmesinde TLS 1.0'ın Schannel uygulaması: 24 Kasım 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Şifreleme Geliştirmeleri (Windows BT Merkezi)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Office 365 ve Office 365 GCC'de TLS 1.2'ye hazırlanma](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Azure Front Door tarafından desteklenen geçerli şifreleme paketleri nelerdir?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
