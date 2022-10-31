---
title: Microsoft 365 Defender'de Microsoft Defender for Cloud Apps (Önizleme)
description: Microsoft Defender for Cloud Apps Microsoft 365 Defender değişiklikleri hakkında bilgi edinin
keywords: Microsoft 365 Defender kullanmaya başlama, Microsoft Defender for Cloud Apps
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 08/04/2022
audience: ITPro
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: a6064137a5a8a7eefc233501707de1de6ae3afe8
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68794052"
---
# <a name="microsoft-defender-for-cloud-apps-in-microsoft-365-defender-preview"></a>Microsoft 365 Defender'de Microsoft Defender for Cloud Apps (Önizleme)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Bulut Uygulamaları için Microsoft Defender](/defender-cloud-apps/)

Microsoft Defender for Cloud Apps artık Microsoft 365 Defender bir parçasıdır. Microsoft 365 Defender portalı, güvenlik yöneticilerinin güvenlik görevlerini tek bir konumda gerçekleştirmesine olanak tanır. Bu, iş akışlarını basitleştirir ve diğer Microsoft 365 Defender hizmetlerinin işlevselliğini ekler. Microsoft 365 Defender Microsoft kimlikleriniz, verileriniz, cihazlarınız, uygulamalarınız ve altyapınız genelinde güvenliği izlemeye ve yönetmeye ev sahipliği yapacaktır.

SOC analistleri bulut uygulamaları da dahil olmak üzere tüm Microsoft 365 Defender iş yüklerini önceliklendirme, araştırma ve avlayabilme olanağına sahiptir.
Cloud Apps için Defender uyarıları Microsoft 365 Defender'ın olay kuyruğunda ve uyarılar kuyruğunda görünmeye devam edecektir, ancak artık Microsoft 365 Defender portalında bulunan uyarı sayfalarının içindeki ilgili içerik, her uyarı türüne uygun uyarlamalarla birleşik bir biçimde görünür.

Microsoft 365 Defender bir <https://security.microsoft.com>göz atın.

Avantajlar hakkında daha fazla bilgi edinin: [Microsoft 365 Defender genel bakış](microsoft-365-defender.md).

## <a name="quick-reference"></a>Hızlı başvuru

Aşağıdaki resimler ve tablolar, Microsoft Defender for Cloud Apps ile Microsoft 365 Defender arasındaki gezinti değişikliklerini listeler.

### <a name="discover"></a>Keşfetmek

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender-discover.png" alt-text="Microsoft 365 Defender portalında Cloud Discovery özellikleri için yeni konumlar" lightbox="../../media/defender-cloud-apps-m365-defender-discover.png":::

| Bulut Uygulamaları için Defender | Microsoft 365 Defender |
|---------|---------|
| Cloud Discover panosu | Bulut uygulamaları -> Bulut bulma |
| Bulunan Uygulamalar | Cloud Discovery sayfasındaki sekme |
| Bulunan kaynaklar | Cloud Discovery sayfasındaki sekme |
| IP adresleri | Cloud Discovery sayfasındaki sekme |
| Kullanıcılar | Cloud Discovery sayfasındaki sekme |
| Aygıtları | Cloud Discovery sayfasındaki sekme |
| Bulut uygulaması kataloğu |  Bulut uygulamaları -> Bulut uygulaması kataloğu |
| Cloud Discovery anlık görüntü raporu oluşturma | Cloud Discovery sayfasındaki Eylemler'in altında |

### <a name="investigate"></a>Araştır

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender-investigate.png" alt-text="Microsoft 365 Defender portalındaki Araştırma özellikleri için yeni konumlar" lightbox="../../media/defender-cloud-apps-m365-defender-investigate.png":::

| Bulut Uygulamaları için Defender | Microsoft 365 Defender |
|---------|---------|
| Etkinlik günlüğü | Bulut uygulamaları -> Etkinlik günlüğü |
| Dosyalar | Bulut uygulamaları -> Dosyaları |
| Kullanıcılar ve hesaplar | Varlıklar -> Kimlikleri |
| Güvenlik yapılandırması | [Bulut için Microsoft Defender'da](/azure/defender-for-cloud/defender-for-cloud-introduction) kullanılabilir |
| Kimlik güvenliği duruşu | [Kimlik için Microsoft Defender kimlik güvenliği duruş değerlendirmeleri](/defender-for-identity/isp-overview) |
| OAuth uygulamaları | Bulut uygulamaları -> OAuth uygulamaları |
| Bağlı uygulamalar | Ayarlar -> Bulut uygulamaları -> Bağlı uygulamalar |

### <a name="control"></a>Denetim

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender-control.png" alt-text="Microsoft 365 Defender portalındaki Denetim özellikleri için yeni konumlar" lightbox="../../media/defender-cloud-apps-m365-defender-control.png":::

| Bulut Uygulamaları için Defender | Microsoft 365 Defender |
|---------|---------|
| İlkeler | Bulut uygulamaları -> İlke yönetimi |
| Şablonlar | Bulut uygulamaları -> İlke şablonları |

### <a name="settings"></a>Ayarlar

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/defender-cloud-apps-m365-defender-settings.png" alt-text="Microsoft 365 Defender portalında Ayarlar için yeni konumlar" lightbox="../../media/defender-cloud-apps-m365-defender-settings.png":::

| Bulut Uygulamaları için Defender | Microsoft 365 Defender |
|---------|---------|
| Ayarlar | Ayarlar -> Bulut uygulamaları |
| Ayarlar/İdare günlüğü | Bulut uygulamaları -> İdare günlüğü |
| Güvenlik uzantıları -> Playbook'lar | Ayarlar -> Bulut uygulamaları |
| Güvenlik uzantıları -> SIEM aracıları | Ayarlar -> Bulut uygulamaları |
| Dış DLP > güvenlik uzantıları | Ayarlar -> Bulut uygulamaları |
| Güvenlik uzantıları -> API belirteçleri | Ayarlar -> Bulut uygulamaları |
| Yönetici erişimini yönetme -> Yönetici rolleri | İzinler-> Bulut uygulamaları-> Rolleri |
| Yönetici erişimini yönetme -> Etkinlik gizlilik izinleri | İzinler-> Bulut uygulamaları-> Etkinlik gizlilik izinleri |
| Dışarı aktarılan raporlar | Raporlar -> Bulut uygulamaları -> Dışarı aktarılan raporlar |
| Kapsamlı dağıtım ve gizlilik | Ayarlar -> Cloud Apps -> Kapsamlı dağıtım ve gizlilik |
| Bağlı Uygulamalar / Uygulama bağlayıcıları | Ayarlar -> Cloud Apps -> Bağlı uygulamalar -> Uygulama Bağlayıcıları |
| Koşullu Erişim Uygulama Denetimi | Ayarlar -> Bulut uygulamaları -> Bağlı uygulamalar -> Koşullu Erişim Uygulama Denetimi uygulamaları |
| IP adresi aralıkları              | Ayarlar -> Bulut uygulamaları                                      |
| Kullanıcı grupları                    | Ayarlar -> Bulut uygulamaları                                      |

## <a name="limitations"></a>Sınırlamalar

- Microsoft 365 Defender portalındaki yeni Cloud Apps için Defender deneyimi, şu anda [Yönetici erişimini yönetme](/defender-cloud-apps/manage-admins) bölümünde ayrıntılı olarak belirtilen tüm kullanıcılar tarafından kullanılabilir:
  - Cloud [Apps için Defender'daki Yerleşik yönetici rollerinde](/defender-cloud-apps/manage-admins#built-in-admin-roles-in-defender-for-cloud-apps) tanımlandığı gibi **Uygulama/Örnek yöneticisi**, **Kullanıcı grubu yöneticisi**, Cloud **Discovery genel** yöneticisi ve Cloud **Discovery rapor yöneticisi**.
  - Etkinlik gizliliği bölümünde tanımlanan kullanıcı [gizlilik](/defender-cloud-apps/activity-privacy) grupları

- Yeni deneyim şu anda yalnızca tam Microsoft Defender for Cloud Apps lisanslarında kullanılabilir.
- Yeni müşterilerin önce Microsoft Defender for Cloud Apps portalında oturum açması gerekir.
- Bazı bağlantılar sizi Cloud Apps için Defender portalına yönlendirebilir.

## <a name="whats-changed"></a>Değişenler

Cloud Apps için Defender ve Microsoft 365 Defender tümleştirmesiyle birlikte gelen değişiklikler hakkında bilgi edinin.

### <a name="global-search"></a>Genel arama

Microsoft 365 Defender'da genel arama (sayfanın üst kısmındaki arama çubuğunu kullanarak) artık ek bir aranabilir varlık içerir: Cloud Apps için Defender'da bağlı uygulamaları aramanıza olanak tanır.

:::image type="content" source="../../media/global-search-apps.png" alt-text="Bağlı uygulamaları arayın.":::

### <a name="assets-and-identities"></a>Varlıklar ve kimlikler

Microsoft 365 Defender deneyiminin tamamına yayılan ayrılmış **varlıklar** bölümünün oluşturulması kapsamında, Bulut Uygulamaları için Defender'ın **Kullanıcılar ve Hesaplar** bölümü **Kimlikler** bölümü olarak yeniden adlandırılır. İşlevlerde değişiklik beklenmiyor.

## <a name="related-videos"></a>İlgili videolar

- [Microsoft 365 Defender'de bulut uygulamalarını koruma](https://www.microsoft.com/videoplayer/embed/RE59yVU)

## <a name="related-information"></a>İlgili bilgiler

- [Microsoft 365 Defender](microsoft-365-defender.md)
