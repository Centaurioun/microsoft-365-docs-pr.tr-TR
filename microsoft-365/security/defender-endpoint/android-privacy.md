---
title: Android’de Uç Nokta için Microsoft Defender - Gizlilik bilgileri
description: Gizlilik denetimleri, Android'de Uç Nokta için Microsoft Defender toplanan tanılama verileri hakkındaki bilgileri ve gizliliği etkileyen ilke ayarlarını yapılandırma.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, android, gizlilik, tanılama
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
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4084db5633a02b1d6f1eeba743549d45c6464689
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693267"
---
# <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Android’de Uç Nokta için Microsoft Defender - Gizlilik bilgileri

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android'de Uç Nokta için Defender, yapılandırılmış Android cihazlarınızdan bilgi toplar ve bu bilgileri Uç Nokta için Defender'ın bulunduğu kiracıda depolar. Bilgiler, Android için Uç Nokta için Defender'ın güvenli, güncel, beklendiği gibi performans göstermesini ve hizmeti desteklemesini sağlamaya yardımcı olmak için toplanır.

Veri depolama hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender veri depolama ve gizlilik](data-storage-privacy.md).

Android için Uç Nokta için Defender'ın güvenli, güncel, beklendiği gibi performans göstermesini ve hizmeti desteklemesini sağlamaya yardımcı olmak için bilgiler toplanır.

Android ve iOS mobil cihazlarda Uç Nokta için Microsoft Defender hakkında en yaygın gizlilik soruları hakkında daha fazla bilgi için bkz. [android ve iOS mobil cihazlarda Uç Nokta için Microsoft Defender ve gizliliğiniz](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).

## <a name="required-data"></a>Gerekli Veriler

Gerekli veriler, Android için Uç Nokta için Defender'ın beklendiği gibi çalışmasını sağlamak için gereken verilerden oluşur. Bu veriler hizmetin çalışması için önemlidir ve son kullanıcı, kuruluş, cihaz ve uygulamalarla ilgili verileri içerebilir. Toplanan veri türlerinin listesi aşağıdadır:

### <a name="app-information"></a>Uygulama bilgileri

Cihazdaki **kötü amaçlı** Android uygulama paketleri (APK' ler) hakkında bilgiler

- Kaynağı yükleme
- APK'nın depolama konumu (dosya yolu)
- Yükleme zamanı, APK boyutu ve izinler

Android Kurumsal Tam olarak yönetilen cihazlar için - Cihazda yüklü Olan Android uygulama paketleri (APK' ler) hakkında bilgiler

- Uygulamanın adı ve paket adı
- Uygulamanın sürüm numarası
- Satıcı adı

İş profili olan Android Kurumsal için - Cihazın İş profiline yüklenen Android uygulama paketleri (APK' ler) hakkında bilgiler

- Uygulamanın adı ve paket adı
- Uygulamanın sürüm numarası
- Satıcı adı

*Kuruluşunuz ayrıca uç nokta için Defender'ı cihazda yüklü olan tüm uygulamalar hakkında bilgi gönderecek şekilde yapılandırmayı da seçebilir. Varsayılan olarak, bu bilgiler kuruluşunuza gönderilmez.*


### <a name="web-page--network-information"></a>Web sayfası / Ağ bilgileri

- Web sitesinin tam URL'si yalnızca kötü amaçlı bir bağlantı veya web sayfası algılandığında ve engellendiğinde.
- Bağlantı bilgileri
- Protokol türü (HTTP, HTTPS vb.)

### <a name="device-and-account-information"></a>Cihaz ve hesap bilgileri

- Tarih & saat, Android sürümü, OEM modeli, CPU bilgileri ve Cihaz tanımlayıcısı gibi cihaz bilgileri.
- Cihaz tanımlayıcısı aşağıdakilerden biridir:
  - Wi-Fi bağdaştırıcısı MAC adresi
  - [Android Kimliği](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (cihazın ilk önyüklemesi sırasında Android tarafından oluşturulduğu gibi).
  - Rastgele oluşturulan genel benzersiz tanımlayıcı (GUID).

- Kiracı, Cihaz ve Kullanıcı bilgileri
  - Azure Active Directory (AD) Cihaz Kimliği ve Azure Kullanıcı Kimliği: Azure Active Directory'de sırasıyla Kullanıcı olan cihazı benzersiz olarak tanımlar.
  - Azure kiracı kimliği: Azure Active Directory'de kuruluşunuzu tanımlayan GUID.
  - Uç Nokta için Microsoft Defender kuruluş kimliği: Cihazın ait olduğu kuruluşla ilişkilendirilmiş benzersiz tanımlayıcı. Microsoft'un sorunların belirli bir kuruluş kümesini etkileyip etkilemediğini ve kaç kuruluşun etkilendiğini belirlemesine olanak tanır.
  - Kullanıcı Asıl Adı: kullanıcının Email kimliği

### <a name="product-and-service-usage-data"></a>Ürün ve hizmet kullanım verileri

Aşağıdaki bilgiler yalnızca cihazda yüklü Uç Nokta için Microsoft Defender uygulama için toplanır. 

- Ad, sürüm ve uygulama yükseltme durumu da dahil olmak üzere uygulama paketi bilgileri.
- Uygulamada gerçekleştirilen eylemler.
- Tehdit adı, kategori vb. gibi tehdit algılama bilgileri.
- Android tarafından oluşturulan kilitlenme raporu günlükleri.

## <a name="optional-data"></a>İsteğe Bağlı Veriler

İsteğe bağlı veriler tanılama verilerini ve geri bildirim verilerini içerir. İsteğe bağlı tanılama verileri ürün geliştirmeleri yapmamıza yardımcı olan ve sorunları algılamamıza, tanılamamıza ve çözmemize yardımcı olacak ileri düzey bilgi sağlayan ek verilerdir. İsteğe bağlı tanılama verileri şunları içerir:

- Uygulama, CPU ve ağ kullanımı.
- Tarama durumu, tarama zamanlamaları, verilen uygulama izinleri ve yükseltme durumu gibi uygulamanın durumu.
- Yönetici tarafından yapılandırılan özellikler.
- Cihazdaki tarayıcılar hakkında temel bilgiler.

**Geri Bildirim Verileri** , kullanıcı tarafından sağlanan uygulama içi geri bildirim aracılığıyla toplanır

- Sağlamayı tercih ederse kullanıcının e-posta adresi.
- Geri bildirim türü (gülümseme, kaş çatma, fikir) ve kullanıcı tarafından gönderilen geri bildirim yorumları.
