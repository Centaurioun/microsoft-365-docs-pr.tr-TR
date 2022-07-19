---
title: Kiracı İzin Ver/Engelle Listesindeki izin ver ve blokları yönet
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde izin verme ve blokları yönetmeyi öğrenin.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d8ac90e8e9b7b955457c9bd90cae68e18cb69915
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66862543"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, Exchange Online EOP filtreleme kararına katılamayabilirsiniz. Örneğin, iyi bir ileti kötü (hatalı pozitif) olarak işaretlenebilir veya hatalı bir iletiye (hatalı negatif) izin verilir.

Microsoft 365 Defender portalındaki Kiracı İzin Ver/Engelle Listesi, Microsoft 365 filtreleme kararlarını el ile geçersiz kılmanın bir yolunu sunar. Kiracı İzin Ver/Engelle Listesi, gelen iletiler için posta akışı sırasında (kuruluş içi iletiler için geçerli değildir) ve kullanıcı tıklamaları sırasında kullanılır. Aşağıdaki geçersiz kılma türlerini belirtebilirsiniz:

- Engelleyecek URL'ler.
- Engellenmesi gereken dosyalar.
- Engellenmesi gereken gönderen e-postaları veya etki alanları.
- İzin vermek veya engellemek için sahte gönderenler. Sahte [zeka içgörülerinde](learn-about-spoof-intelligence.md) izin verme veya engelleme kararını geçersiz kılarsanız, sahtekar gönderen yalnızca Kiracı İzin Ver/Engelle Listesi'ndeki **Kimlik Sahtekarı** sekmesinde görünen el ile izin verme veya engelleme girdisine dönüşür. Sahte gönderenler için kimlik sahtekarlık zekası tarafından algılanana kadar el ile izin verme veya engelleme girdileri de oluşturabilirsiniz.
- İzin verecek URL'ler.
- İzin verecek dosyalar.
- İzin vermek için gönderen e-postaları veya etki alanları.

Bu makalede, Microsoft 365 Defender portalında veya Exchange Online'de posta kutuları olan Microsoft 365 kuruluşları için PowerShell'de (Exchange Online Exchange Online olmayan kuruluşlar için tek başına EOP PowerShell) Kiracı İzin Verme/Engelleme Listesi'nde girişlerin nasıl yapılandırıldığı açıklanır  posta kutuları).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. **Doğrudan Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın<https://security.microsoft.com/tenantAllowBlockList>.

- Dosyanın SHA256 karma değerini kullanarak dosyaları belirtirsiniz. Windows'da bir dosyanın SHA256 karma değerini bulmak için komut isteminde aşağıdaki komutu çalıştırın:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Örnek değer: `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. Algısal karma (pHash) değerleri desteklenmez.

- Gönderenler, URL'ler ve dosya karmaları için Kiracı İzin Ver/Engelle Listesi her iki izin ve blok için her biri 500 girişe izin verir ve toplamda 1000 girdi olur. Kimlik sahtekarlığına (sahte gönderenler) izin verilen toplam giriş sayısı 1024'tür.

- Her girdi için en fazla karakter sayısı:
  - Dosya karmaları = 64
  - URL = 250

- Bir girdinin 30 dakika içinde etkin olması gerekir, ancak girdinin etkin olması 24 saat kadar sürebilir.

- Varsayılan olarak, Kiracı İzin Ver/Engelle Listesindeki girdilerin süresi 30 gün sonra dolar. Bir tarih belirtebilir veya bunları hiçbir zaman sona ermeyecek şekilde ayarlayabilirsiniz (giriş blok türü için).

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell). Tek başına EOP PowerShell'e bağlanmak için bkz. [Exchange Online Protection PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bu makaledeki yordamları gerçekleştirmeden önce Exchange Online'de izinlerin atanmış olması gerekir:
  - Kiracı İzin Ver/Engelle Listesinden değer eklemek ve kaldırmak için
    - **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol grubu (**Güvenlik yöneticisi rolü**)
    - **Güvenlik İşleci** rol grubu (**Kiracı AllowBlockList Manager**).
  - Kiracı İzin Ver/Engelle Listesi'ne salt okunur erişim için
    - **Genel Okuyucu**  rol grubu
    - **Güvenlik Okuyucusu** rol grubu
    - **Yalnızca Görüntüle yapılandırma** rol grubu

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri *ve* izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  > - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

## <a name="configure-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini Yapılandırma

E-postalara izin vermek veya e-postaları engellemek için bkz. [Kiracı İzin Verme/Engelleme Listesi'ni kullanarak e-postalara izin verme veya engelleme](allow-block-email-spoof.md).

Dosyalara izin vermek veya dosyaları engellemek için bkz. [Kiracı İzin Verme/Engelleme Listesi'ni kullanarak dosyalara izin verme veya bunları engelleme](allow-block-files.md).

URL'lere izin vermek veya url'leri engellemek için bkz. [Kiracı İzin Verme/Engelleme Listesi'ni kullanarak URL'lere izin verme veya engelleme](allow-block-urls.md).

Bu makaleler, hem Microsoft 365 Defender Portal'ı hem de PowerShell veya tek başına EOP PowerShell'i Exchange Online kullanarak Kiracı İzin Ver/Engelle Listesi'nde girdi ekleme veya kaldırma veya değiştirme yönergelerini içerir.

### <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>İzin ver veya engelle girdisi ekledikten sonra beklenmesi gerekenler

Gönderimler portalı aracılığıyla bir izin girişi veya Kiracı İzin Ver/Engelle Listesi'ne bir blok girişi ekledikten sonra, girdi hemen çalışmaya başlamalıdır.

Sistemin izin verme veya engelleme hakkında bilgi edinip öğrenmediğini görmek için girişlerin 30 gün sonra otomatik olarak süresinin dolmasına izin vermenizi öneririz. Aksi takdirde, sisteme öğrenmesi için 30 gün daha vermek için başka bir giriş yapmanız gerekir.

## <a name="view-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki girdileri görüntüleme

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. İstediğiniz sekmeyi seçin. Kullanılabilir sütunlar seçtiğiniz sekmeye bağlıdır:

   - **Gönderenler**:
     - **Değer**: Gönderen etki alanı veya e-posta adresi.
     - **Eylem**: **İzin Ver** veya **Engelle** değeri.
     - **Değiştiren**
     - **Son güncelleştirme**
     - **Kaldırılacak yer**
     - **Notlar**
   - **Sızdırma**
     - **Sahte kullanıcı**
     - **Altyapı gönderme**
     - **Kimlik sahtekarı türü**: **İç** veya **Dış** değeri.
     - **Eylem**: **Engelle** veya **İzin Ver** değeri.
   - **URL'ler**:
     - **Değer**: URL.
     - **Eylem**: **İzin Ver** veya **Engelle** değeri.
     - **Değiştiren**
     - **Son güncelleştirme**
     - **Kaldırılacak yer**
     - **Notlar**
   - **Dosyalar**
     - **Değer**: Dosya karması.
     - **Eylem**: **İzin Ver** veya **Engelle** değeri.
     - **Değiştiren**
     - **Son güncelleştirme**
     - **Kaldırılacak yer**
     - **Notlar**

   Artan veya azalan düzende sıralamak için sütun başlığına tıklayabilirsiniz.

   Sonuçları gruplandırmak için **Gruplandır'a** tıklayabilirsiniz. Kullanılabilir değerler seçtiğiniz sekmeye bağlıdır:

   - **Gönderenler**: Sonuçları **Eyleme** göre gruplandırabilirsiniz.
   - **Kimlik sahtekarlığına:** Sonuçları **Eylem** veya **Kimlik Sahtekarı türüne** göre gruplandırabilirsiniz.
   - **URL'ler**: Sonuçları **Eyleme** göre gruplandırabilirsiniz.
   - **Dosyalar**: Sonuçları **Eyleme** göre gruplandırabilirsiniz.

   **Ara'ya** tıklayın, bir değerin tamamını veya bir bölümünü girin ve belirli bir değeri bulmak için ENTER tuşuna basın. İşiniz bittiğinde Aramayı temizle simgesine tıklayın ![.](../../media/m365-cc-sc-close-icon.png) **Aramayı temizle'yi seçin**.

   Sonuçları filtrelemek için **Filtre'ye** tıklayın. **Görüntülenen Filtre** açılır öğesinde bulunan değerler, seçtiğiniz sekmeye bağlıdır:

   - **Gönderenler**
     - **Eylem**
     - **Hiçbir zaman süresi dolmaz**
     - **Son güncelleştirme tarihi**
     - **Kaldırılacak yer**
   - **Sızdırma**
     - **Eylem**
     - **Kimlik sahtekarı türü**
   - **Url 'leri**
     - **Eylem**
     - **Hiçbir zaman süresi dolmaz**
     - **Son güncelleştirme tarihi**
     - **Kaldırılacak yer**
   - **Dosyalar**
     - **Eylem**
     - **Hiçbir zaman süresi dolmaz**
     - **Son güncelleştirme**
     - **Kaldırılacak yer**

   İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtre'ye** tıklayın ve görüntülenen **Filtre** açılır öğesinde **Filtreleri temizle'ye** tıklayın.

## <a name="modify-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki girdileri değiştirme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. Değiştirmek istediğiniz girdi türünü içeren sekmeyi seçin:
   - **Gönderenler**
   - **Sızdırma**
   - **Url 'leri**
   - **Dosyalar**

3. Değiştirmek istediğiniz girdiyi seçin ve düzenle simgesine tıklayın ![.](../../media/m365-cc-sc-edit-icon.png) **Düzenle'yi seçin**. Görüntülenen açılır öğede değiştirebileceğiniz değerler, önceki adımda seçtiğiniz sekmeye bağlıdır:
   - **Gönderenler**
     - **Hiçbir zaman süresi dolmaz** ve/veya son kullanma tarihi.
     - **İsteğe bağlı not**
   - **Sızdırma**
     - **Eylem**: Değeri **İzin Ver** veya **Engelle** olarak değiştirebilirsiniz.
   - **Url 'leri**
     - **Hiçbir zaman süresi dolmaz** ve/veya son kullanma tarihi.
     - **İsteğe bağlı not**
   - **Dosyalar**
     - **Hiçbir zaman süresi dolmaz** ve/veya son kullanma tarihi.
     - **İsteğe bağlı not**

    Gönderenler, URL'ler ve dosyalar için değerlerin yalnızca engellenen girdiler için hiçbir zaman sona ermeyeceğini unutmayın. 

4. Bitirdiğinizde, **Kaydet**'i tıklatın.

> [!NOTE]
> İzin verilen süreyi yalnızca oluşturma tarihinden sonra en fazla 30 gün uzatabilirsiniz. Bloklar 90 güne kadar uzatılabilir, ancak izin vermedikleri gibi Süresi hiç dolmaz olarak da ayarlanabilir.

## <a name="remove-entries-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden girdileri kaldırma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. Kaldırmak istediğiniz girdi türünü içeren sekmeyi seçin:
   - **Gönderenler**
   - **Sızdırma**
   - **Url 'leri**
   - **Dosyalar**

3. Kaldırmak istediğiniz girdiyi seçin ve sil simgesine tıklayın ![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

4. Görüntülenen uyarı iletişim kutusunda **Sil'e** tıklayın.

## <a name="related-articles"></a>İlgili makaleler

- [Kiracı İzin Ver/Engelle Listesindeki dosyalara izin ver veya bunları engelle](allow-block-files.md)
- [Kiracı İzin Ver/Engelle Listesinde e-postalara izin ver veya e-postaları engelle](allow-block-email-spoof.md)
- [Kiracı İzin Ver/Engelle Listesinde URL'lere izin ver veya url'leri engelle](allow-block-urls.md)
