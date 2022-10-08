---
title: Tarayıcınızda LMS URL'leri için tanımlama bilgilerine izin ver
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Edge, Chrome, Firefox ve Safari tarayıcılarında LMS URL'leri için tanımlama bilgilerine nasıl izin vereceğinizi öğrenin.
ms.openlocfilehash: fcaae51c9cdbab3a052a3c29d24e5386f4f852ee
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167373"
---
# <a name="allow-cookies-for-lms-urls-in-your-browser"></a>Tarayıcınızda LMS URL'leri için tanımlama bilgilerine izin ver

LTI 1.3 el sıkışmasını IMS Global standartlarına göre tamamlamak için üçüncü taraf tarayıcı tanımlama bilgileri gereklidir. Bu nedenle, LTI aracını bir Öğrenme Yönetim Sistemi'nden (LMS) başlatırken, tarayıcı ayarı LMS URL'si için üçüncü taraf tanımlama bilgilerine izin vermelidir.

Tarayıcınızda tanımlama bilgilerine izin verme adımları aşağıdadır.

# <a name="microsoft-edge"></a>[Microsoft Edge](#tab/edge)

## <a name="allow-cookies-for-lms-urls-in-microsoft-edge"></a>Microsoft Edge'de LMS URL'leri için tanımlama bilgilerine izin ver

1. Edge **Ayarlar** penceresinde, **Çerezler ve site izinleri** > **Çerezler ve depolanan veriler** > **Çerezleri ve site verilerini yönetin ve silin**'i seçin.
2. **Çerez verilerini kaydetmek ve okumak için sitelere izin ver (önerilen)**'i açın ve **Üçüncü taraf çerezlerini engelle**'nin kapalı olduğundan emin olun.

Üçüncü taraf tanımlama bilgilerini engellenmiş olarak tutmanız gerekiyorsa:

1. Edge **Ayarlar** penceresinde, **Çerezler ve site izinleri** > **Çerezler ve depolanan veriler** > **Çerezleri ve site verilerini yönetin ve silin**'i seçin.
2. LMS platformunun etki alanı URL'sini eklemek için **İzin Ver'in** altında **Ekle'yi** seçin.
   1. Örneğin, LMS platformu konumunda `https://contoso.com`barındırılıyorsa, bu URL **İzin Ver** altına eklenmelidir.

![Microsoft Edge tanımlama bilgisi ayarları sayfasının ekran görüntüsü](media/edge-cookies.png)

# <a name="google-chrome"></a>[Google Chrome](#tab/chrome)

## <a name="allow-cookies-for-lms-urls-in-google-chrome"></a>Google Chrome'da LMS URL'leri için tanımlama bilgilerine izin ver

1. Chrome'da **Ayarlar** penceresinde, **Gizlilik ve güvenlik** sekmesinde, **Çerezler'i ve diğer site verileri**'ni seçin.

2. **Çerezleri her zaman kullanabilen siteler** altında, **Ekle**'yi seçin ve ardından **Bu sitede üçüncü taraf çerezlerini içer** onay kutusunu seçin.

3. LMS platformunun etki alanı URL'sini ekleyin.
   1. Örneğin, LMS platformu konumunda `https://contoso.com`barındırılıyorsa bu URL kullanılmalıdır.

![Google Chrome tanımlama bilgisi ayarları sayfasının ekran görüntüsü](media/chrome-cookies.png)

# <a name="mozilla-firefox"></a>[Mozilla Firefox](#tab/firefox)

## <a name="allow-cookies-for-lms-urls-in-mozilla-firefox"></a>Mozilla Firefox'ta LMS URL'leri için tanımlama bilgilerine izin ver

1. Firefox **Ayarlar** penceresinde, **Gizlilik ve Güvenlik** sekmesini seçin.

2. **Çerezler ve Site Verileri** altında, **İstisnaları Yönet**'i seçin.

3. **Web sitesinin adresi** metin kutusuna LMS platformunun URL'sini girin.
   1. Örneğin, LMS platformu konumunda `https://contoso.com`barındırılıyorsa bu URL kullanılmalıdır.

4. Girilen web sitesi için tanımlama bilgilerine izin vermek için **İzin Ver'i** seçin.

5. **Değişiklikleri Kaydet**'i seçin.

![Mozilla Firefox tanımlama bilgisi ayarları sayfasının ekran görüntüsü](media/firefox-cookies.png)

# <a name="safari"></a>[Safari](#tab/safari)

## <a name="allow-cookies-for-lms-urls-in-safari"></a>Safari'de LMS URL'leri için tanımlama bilgilerine izin ver

1. **Tercihler** > **Gizlilik**'i seçin.

2. **Siteler arası izlemeyi engelle** onay kutusunu temizleyin.

---

> [!NOTE]
> Ayarları kendiniz değiştiremezsiniz (tarayıcınız kuruluşunuz tarafından yönetilir), BT departmanınıza ulaşın.
