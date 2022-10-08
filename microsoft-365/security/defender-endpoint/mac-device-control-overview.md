---
title: macOS için cihaz denetimi
description: USB cihazları gibi çıkarılabilir depolama birimi tehditlerini azaltmak için Mac'te Uç Nokta için Microsoft Defender yapılandırmayı öğrenin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, device, control, usb, çıkarılabilir, medya
ms.service: microsoft-365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 947fd5b5a490bcd8041c05632ad11ae98fb47ec8
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226679"
---
# <a name="device-control-for-macos"></a>macOS için cihaz denetimi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>Gereksinimler

macOS için cihaz denetimi aşağıdaki önkoşullara sahiptir:

> [!div class="checklist"]
>
> - Uç Nokta için Microsoft Defender yetkilendirme (deneme olabilir)
> - En düşük işletim sistemi sürümü: macOS 11 veya üzeri
> - En düşük ürün sürümü: 101.34.20

## <a name="device-control-policy"></a>Cihaz denetimi ilkesi

macOS için cihaz denetimini yapılandırmak için, kuruluşunuzda uygulamak istediğiniz kısıtlamaları açıklayan bir ilke oluşturmanız gerekir.

Cihaz denetimi ilkesi, diğer tüm ürün ayarlarını yapılandırmak için kullanılan yapılandırma profiline dahildir. Daha fazla bilgi için bkz [. Yapılandırma profili yapısı](mac-preferences.md#configuration-profile-structure).

Yapılandırma profilinde, cihaz denetim ilkesi aşağıdaki bölümde tanımlanır:

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|deviceControl|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|

Cihaz denetimi ilkesi aşağıdakileri yapmak için kullanılabilir:

- [Cihaz denetimi tarafından tetiklenen bildirimler için URL hedefini özelleştirme](#customize-url-target-for-notifications-raised-by-device-control)
- [Çıkarılabilir cihazlara izin verme veya bunları engelleme](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Cihaz denetimi tarafından tetiklenen bildirimler için URL hedeflerini özelleştirme

Uygulamaya koyduğunuz cihaz denetim ilkesi bir cihazda zorunlu kılındığında (örneğin, çıkarılabilir bir medya cihazına erişim kısıtlandığında), kullanıcıya bir bildirim görüntülenir.

:::image type="content" source="images/mac-device-control-notification.png" alt-text="Cihaz denetimi bildirimi" lightbox="images/mac-device-control-notification.png":::

Son kullanıcılar bu bildirime tıkladığında, varsayılan tarayıcıda bir web sayfası açılır. Son kullanıcılar bildirime tıkladığında açılan URL'yi yapılandırabilirsiniz.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|navigationTarget|
|**Veri türü**|Dize|
|**Açıklamalar**|Tanımlanmamışsa, ürün tarafından gerçekleştirilen eylemi açıklayan genel bir sayfaya işaret eden varsayılan bir URL kullanır.|
|

### <a name="allow-or-block-removable-devices"></a>Çıkarılabilir cihazlara izin verme veya bunları engelleme

Cihaz denetim ilkesinin çıkarılabilir medya bölümü, çıkarılabilir medyaya erişimi kısıtlamak için kullanılır.

> [!NOTE]
> Şu anda aşağıdaki çıkarılabilir medya türleri desteklenmektedir ve ilkeye dahil edilebilir: USB depolama cihazları.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|removableMediaPolicy|
|**Veri türü**|Sözlük (iç içe tercih)|
|**Açıklamalar**|Sözlük içeriğinin açıklaması için aşağıdaki bölümlere bakın.|
|

İlkenin bu bölümü hiyerarşiktir ve maksimum esneklik sağlar ve çok çeşitli kullanım örneklerini kapsar. En üst düzeyde, satıcı kimliğiyle tanımlanan satıcılar bulunur. Her satıcı için, bir ürün kimliğiyle tanımlanan ürünler vardır. Son olarak, her ürün için belirli cihazları belirten seri numaraları vardır.

```text
|-- policy top level
    |-- vendor 1
        |-- product 1
            |-- serial number 1
            ...
            |-- serial number N
        ...
        |-- product N
    ...
    |-- vendor N
```

Cihaz tanımlayıcılarını bulma hakkında bilgi için bkz [. Cihaz tanımlayıcılarını arama](#look-up-device-identifiers).

İlke, en özel girdiden en genel girişe değerlendirilir. Başka bir deyişle, bir cihaz takılıyken, ürün her çıkarılabilir medya cihazı için ilkedeki en özel eşleşmeyi bulmaya çalışır ve izinleri bu düzeyde uygular. Eşleşme yoksa, bir sonraki en iyi eşleşme uygulanır ve en üst düzeyde belirtilen izne kadar (cihaz ilkedeki başka bir girişle eşleşmediğinde varsayılan değerdir).

#### <a name="policy-enforcement-level"></a>İlke zorlama düzeyi

Çıkarılabilir medya bölümünün altında, aşağıdaki değerlerden birini alabilen zorlama düzeyini ayarlama seçeneği vardır:

- `audit` - Bu zorlama düzeyi altında, bir cihaza erişim kısıtlanırsa kullanıcıya bir bildirim görüntülenir, ancak cihaz yine de kullanılabilir. Bu zorlama düzeyi, bir ilkenin etkinliğini değerlendirmek için yararlı olabilir.
- `block` - Bu zorlama düzeyi altında, kullanıcının cihazda gerçekleştirebileceği işlemler ilkede tanımlanan işlemle sınırlıdır. Ayrıca kullanıcıya bir bildirim gönderilir.

> [!NOTE]
> Varsayılan olarak, zorlama düzeyi olarak `audit`ayarlanır.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|enforcementLevel|
|**Veri türü**|Dize|
|**Olası değerler**|denetim (varsayılan) <p> Blok|
|

#### <a name="default-permission-level"></a>Varsayılan izin düzeyi

Çıkarılabilir medya bölümünün en üst düzeyinde, ilkedeki başka hiçbir şeyle eşleşmeyen cihazlar için varsayılan izin düzeyini yapılandırabilirsiniz.

Bu ayar şu şekilde ayarlanabilir:

- `none` - Cihazda işlem yapılamaz
- Aşağıdaki değerlerin birleşimi:
  - `read` - Cihazda okuma işlemlerine izin verilir
  - `write` - Cihazda yazma işlemlerine izin verilir
  - `execute` - Cihazda yürütme işlemlerine izin verilir

> [!NOTE]
> `none` İzin düzeyinde varsa, diğer tüm izinler (`read`, `write`veya `execute`) yoksayılır.
>
> İzin `execute` yalnızca Mach-O ikili dosyalarının yürütülmesini ifade eder. Betiklerin veya diğer yük türlerinin yürütülmesini içermez.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Izni|
|**Veri türü**|Dize dizisi|
|**Olası değerler**|yok <p> Okuma <p> Yazmak <p> Yürütmek|
|

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Çıkarılabilir medyayı satıcıya, ürüne ve seri numarasına göre kısıtlama

[Çıkarılabilir cihazlara izin verme veya bunları engelleme](#allow-or-block-removable-devices) bölümünde açıklandığı gibi, USB cihazları gibi çıkarılabilir medya satıcı kimliği, ürün kimliği ve seri numarası ile tanımlanabilir.

Çıkarılabilir medya ilkesinin en üst düzeyinde, isteğe bağlı olarak satıcı düzeyinde daha ayrıntılı kısıtlamalar tanımlayabilirsiniz.

`vendors` Sözlük, her girişin satıcı kimliğiyle tanımlandığı bir veya daha fazla giriş içerir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Satıcı|
|**Veri türü**|Sözlük (iç içe tercih)|
|

Her satıcı için, ilgili satıcıdan gelen cihazlar için istenen izin düzeyini belirtebilirsiniz.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Izni|
|**Veri türü**|Dize dizisi|
|**Olası değerler**|[Varsayılan izin düzeyiyle](#default-permission-level) aynı|
|

Ayrıca, daha ayrıntılı izinlerin tanımlandığı satıcıya ait ürün kümesini isteğe bağlı olarak belirtebilirsiniz. Sözlük, `products` her girişin ürün kimliğiyle tanımlandığı bir veya daha fazla girdi içerir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Ürünler|
|**Veri türü**|Sözlük (iç içe tercih)|
|

Her ürün için, bu ürün için istenen izin düzeyini belirtebilirsiniz.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Izni|
|**Veri türü**|Dize dizisi|
|**Olası değerler**|[Varsayılan izin düzeyiyle](#default-permission-level) aynı|
|

Ayrıca, daha ayrıntılı izinlerin tanımlandığı isteğe bağlı bir seri numaraları kümesi belirtebilirsiniz.

`serialNumbers` Sözlük, her girişin seri numarasıyla tanımlandığı bir veya daha fazla girdi içerir.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|serialNumbers|
|**Veri türü**|Sözlük (iç içe tercih)|
|

Her seri numarası için istenen izin düzeyini belirtebilirsiniz.

<br>

****

|Bölüm|Değer|
|---|---|
|**Etki alanı**|`com.microsoft.wdav`|
|**Anahtar**|Izni|
|**Veri türü**|Dize dizisi|
|**Olası değerler**|[Varsayılan izin düzeyiyle](#default-permission-level) aynı|
|

#### <a name="example-device-control-policy"></a>Örnek cihaz denetimi ilkesi

Aşağıdaki örnekte yukarıdaki kavramların tümünün bir cihaz denetim ilkesinde nasıl birleştirilebileceği gösterilmektedir. Aşağıdaki örnekte, çıkarılabilir medya ilkesinin hiyerarşik yapısına dikkat edin.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>navigationTarget</key>
        <string>[custom URL for notifications]</string>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>[enforcement level]</string> <!-- audit / block -->
            <key>permission</key>
            <array>
                <string>[permission]</string> <!-- none / read / write / execute -->
                <!-- other permissions -->
            </array>
            <key>vendors</key>
            <dict>
                <key>[vendor id]</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>[permission]</string> <!-- none / read / write / execute -->
                        <!-- other permissions -->
                    </array>
                    <key>products</key>
                    <dict>
                        <key>[product id]</key>
                        <dict>
                            <key>permission</key>
                            <array>
                                <string>[permission]</string> <!-- none / read / write / execute -->
                                <!-- other permissions -->
                            </array>
                            <key>serialNumbers</key>
                            <dict>
                                <key>[serial-number]</key>
                                <array>
                                    <string>[permission]</string> <!-- none / read / write / execute -->
                                    <!-- other permissions -->
                                </array>
                                <!-- other serial numbers -->
                            </dict>
                        </dict>
                        <!-- other products -->
                    </dict>
                </dict>
                <!-- other vendors -->
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

Aşağıdaki belgelere daha fazla cihaz denetimi ilkesi örneği ekledik:

- [Intune için cihaz denetimi ilkeleri örnekleri](mac-device-control-intune.md)
- [JAMF için cihaz denetimi ilkeleri örnekleri](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>Cihaz tanımlayıcılarını arama

Bir USB cihazının satıcı kimliğini, ürün kimliğini ve seri numarasını bulmak için:

1. Bir Mac cihazında oturum açın.
1. Tanımlayıcıları aramak istediğiniz USB cihazını takın.
1. macOS'un en üst düzey menüsünde **Bu Mac Hakkında'yı** seçin.

   :::image type="content" source="images/mac-device-control-lookup-1.png" alt-text="Bu Mac Hakkında sayfası" lightbox="images/mac-device-control-lookup-1.png":::

1. **Sistem Raporu'mu** seçin.

   :::image type="content" source="images/mac-device-control-lookup-2.png" alt-text="Sistem raporu" lightbox="images/mac-device-control-lookup-2.png":::

1. Sol sütundan **USB'yi** seçin.

   :::image type="content" source="images/mac-device-control-lookup-3.png" alt-text="Tüm USB cihazlarının görünümü" lightbox="images/mac-device-control-lookup-3.png":::
    

1. **USB Cihaz Ağacı'nın** altında, prize taktığınız USB cihazına gidin.

   :::image type="content" source="images/mac-device-control-lookup-4.png" alt-text="USB cihazının ayrıntıları" lightbox="images/mac-device-control-lookup-4.png":::

1. Satıcı kimliği, ürün kimliği ve seri numarası görüntülenir. Çıkarılabilir medya ilkesine satıcı kimliğini ve ürün kimliğini eklerken, yalnızca öğesinin arkasına `0x`bölümünü eklemeniz gerekir. Örneğin, aşağıdaki görüntüde satıcı kimliği ve `1000` ürün kimliği şeklindedir `090c`.

#### <a name="discover-usb-devices-in-your-organization"></a>Kuruluşunuzdaki USB cihazlarını keşfetme

GELIŞMIŞ Uç Nokta için Microsoft Defender tehdit avcılığında USB cihazlarından kaynaklanan bağlama, çıkarma ve birim değişikliği olaylarını görüntüleyebilirsiniz. Bu olaylar, şüpheli kullanım etkinliğini belirlemek veya iç araştırmalar gerçekleştirmek için yararlı olabilir.

```bash
DeviceEvents
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Cihaz denetimi ilkesi dağıtımı

Cihaz denetimi ilkesi, [macOS'ta Uç Nokta için Microsoft Defender için tercihleri ayarlama](mac-preferences.md) bölümünde açıklandığı gibi diğer ürün ayarlarının yanına eklenmelidir.

Bu profil [, Yapılandırma profili dağıtımında](mac-preferences.md#configuration-profile-deployment) listelenen yönergeler kullanılarak dağıtılabilir.

## <a name="troubleshooting-tips"></a>Sorun giderme ipuçları

Yapılandırma profilini Intune veya JAMF aracılığıyla gönderdikten sonra, Terminal'den aşağıdaki komutu çalıştırarak ürün tarafından başarıyla alınıp alınmadığını kontrol edebilirsiniz:

```bash
mdatp device-control removable-media policy list
```

Bu komut, ürünün kullandığı cihaz denetim ilkesini standart çıktıya yazdırır. Bu yazdırma `Policy is empty`durumunda, (a) yapılandırma profilinin gerçekten de yönetim konsolundan cihazınıza gönderildiğinden ve (b) bu belgede açıklandığı gibi geçerli bir cihaz denetim ilkesi olduğundan emin olun.

İlkenin başarıyla teslim edildiği ve bir veya daha fazla cihazın takılı olduğu bir cihazda, tüm cihazları ve bunlara uygulanan etkin izinleri listelemek için aşağıdaki komutu çalıştırabilirsiniz.

```bash
mdatp device-control removable-media devices list
```

Çıktı örneği:

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

Yukarıdaki örnekte, cihaza teslim edilen cihaz denetim ilkesine göre yalnızca bir çıkarılabilir medya cihazı takılıdır ve `execute` ve izinleri vardır`read`.

## <a name="related-topics"></a>İlgili konular

- [Intune için cihaz denetimi ilkeleri örnekleri](mac-device-control-intune.md)
- [JAMF için cihaz denetimi ilkeleri örnekleri](mac-device-control-jamf.md)
