---
title: Gizlilik bilgileri - iOS'ta Uç Nokta için Microsoft Defender
ms.reviewer: ''
description: iOS'ta Uç Nokta için Microsoft Defender gizlilik bilgilerini açıklar
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, ios, ilke, genel bakış
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
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 17d1311ce08435de134e4a04643d58f780f04f1d
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68225844"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>Gizlilik bilgileri - iOS'ta Uç Nokta için Microsoft Defender

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> iOS'ta Uç Nokta için Defender, Web Koruması özelliğini sağlamak için bir VPN kullanır. Bu normal bir VPN değildir ve cihazın dışına trafik almayan yerel veya kendi kendine döngüye alınmış bir VPN'dir. **Microsoft veya kuruluşunuz gözatma etkinliğinizi görmüyor.**

iOS'ta Uç Nokta için Defender, yapılandırılmış iOS cihazlarınızdan bilgi toplar ve bunu Uç Nokta için Defender'ın bulunduğu kiracıda depolar. Bilgiler, iOS'ta Uç Nokta için Defender'ın güvenli, güncel, beklendiği gibi performans göstermesini ve hizmeti desteklemesini sağlamaya yardımcı olmak için toplanır.

Veri depolama hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender veri depolama ve gizlilik](data-storage-privacy.md).

Android ve iOS mobil cihazlarda Uç Nokta için Microsoft Defender hakkında en yaygın gizlilik soruları hakkında daha fazla bilgi için bkz. [android ve iOS mobil cihazlarda Uç Nokta için Microsoft Defender ve gizliliğiniz](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).

## <a name="required-data"></a>Gerekli veriler

Gerekli veriler, iOS'ta Uç Nokta için Defender'ın beklendiği gibi çalışmasını sağlamak için gereken verilerden oluşur. Bu veriler hizmetin çalışması için önemlidir ve son kullanıcı, kuruluş, cihaz ve uygulamalarla ilgili verileri içerebilir.

Toplanan veri türlerinin listesi aşağıdadır:

### <a name="web-page-or-network-information"></a>Web sayfası veya Ağ bilgileri

- Web sitesinin etki alanı adı ve IP adresi yalnızca kötü amaçlı bir bağlantı veya web sayfası algılandığında.

### <a name="device-and-account-information"></a>Cihaz ve hesap bilgileri

- Tarih & saat, iOS sürümü, CPU bilgileri ve Cihaz tanımlayıcısı gibi cihaz bilgileri, burada Cihaz tanımlayıcısı aşağıdakilerden biridir:
  - Wi-Fi bağdaştırıcısı MAC adresi
  - Rastgele oluşturulan genel benzersiz tanımlayıcı (GUID)
- Kiracı, Cihaz ve Kullanıcı bilgileri
  - Azure Active Directory (AD) Cihaz Kimliği ve Azure Kullanıcı Kimliği - Azure Active Directory'de sırasıyla Kullanıcı olan cihazı benzersiz olarak tanımlar.
  - Azure kiracı kimliği - Azure Active Directory'de kuruluşunuzu tanımlayan GUID.
  - kuruluş kimliği Uç Nokta için Microsoft Defender - Cihazın ait olduğu kuruluşla ilişkilendirilmiş benzersiz tanımlayıcı. Microsoft'un belirli bir kuruluş kümesini ve etkilenen kuruluş sayısını etkileyen sorunlar olup olmadığını belirlemesine olanak tanır.
  - Kullanıcı Asıl Adı - kullanıcının Email kimliği.

### <a name="product-and-service-usage-data"></a>Ürün ve hizmet kullanım verileri

Aşağıdaki bilgiler yalnızca cihazda yüklü Uç Nokta için Microsoft Defender uygulama için toplanır.

- Ad, sürüm ve uygulama yükseltme durumu da dahil olmak üzere uygulama paketi bilgileri.
- Uygulamada gerçekleştirilir.
- iOS tarafından oluşturulan kilitlenme raporu günlükleri.
- Bellek kullanım verileri.

## <a name="optional-data"></a>İsteğe Bağlı Veriler

İsteğe bağlı veriler, istemciden gelen tanılama verilerini ve geri bildirim verilerini içerir. İsteğe bağlı tanılama verileri ürün geliştirmeleri yapmamıza yardımcı olan ve sorunları algılamamıza, tanılamamıza ve çözmemize yardımcı olacak ileri düzey bilgi sağlayan ek verilerdir. Bu veriler yalnızca tanılama amaçlıdır ve hizmetin kendisi için gerekli değildir.

İsteğe bağlı tanılama verileri şunları içerir:

- Uç Nokta için Defender için uygulama, CPU ve ağ kullanımı.
- Uç Nokta için Defender yöneticisi tarafından yapılandırılan özellikler.

Geri Bildirim Verileri, kullanıcı tarafından sağlanan uygulama içi geri bildirim aracılığıyla toplanır.

- Sağlamayı tercih ederse kullanıcının e-posta adresi.
- Geri bildirim türü (gülümseme, kaş çatma, fikir) ve kullanıcı tarafından gönderilen geri bildirim yorumları.

Daha fazla bilgi için bkz [. Gizlilik hakkında daha fazla bilgi](https://aka.ms/mdatpiosprivacystatement).
