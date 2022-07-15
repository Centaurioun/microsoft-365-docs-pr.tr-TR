---
title: Tarayıcılarda Teams sanal randevuları için katılım deneyimini yönetme
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
ms.reviewer: hafarmer
description: Tarayıcılardaki Teams sanal randevuları için katılma deneyimi hakkında bilgi edinin.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 869e554ed202f5e2ef24cf75e3dc2338c65de554
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66824751"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Tarayıcılarda Teams sanal randevuları için katılım deneyimini yönetme

Microsoft Teams, kişilerin Teams'i indirmek zorunda kalmadan sanal randevulara katılmasını kolaylaştırır. Daha sorunsuz bir deneyim için, katılımcılar masaüstü veya mobil tarayıcıdan sağlık ziyaretleri ve finansal danışmanlıklar gibi randevulara katılabilir. Katılımcıların cihazlarına Teams uygulamasını yüklemeleri gerekmez.

Tarayıcıya katıldığınızda, bir katılımcı bir randevuya katıldığında Teams'i indirmesi istenmez. Bunun yerine Teams, katılımcının katılmak için **Şimdi katıl'ı** seçebileceği bir tarayıcıda açılır. Bu özellik sayesinde Teams cihazda zaten yüklüyse Teams'in uygulamada değil tarayıcıda açılacağını unutmayın.

Şu anda tarayıcı katılımı, aşağıdakiler aracılığıyla zamanlanan randevular için kullanılabilir:

- [Bookings uygulaması](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams Elektronik Sistem Durumu Kaydı (EHR) bağlayıcısı

  - [Cerner EHR](ehr-admin-cerner.md) ile tümleştirme
  - [Epic EHR](ehr-admin-epic.md) ile tümleştirme

## <a name="set-up-browser-join"></a>Tarayıcı katılımını ayarlama

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings uygulaması aracılığıyla zamanlanan randevular

Kuruluşunuzdaki zamanlayıcılar, bookings uygulamasında belirli randevu türleri ve bireysel randevular için bu özelliği açabilir.

Bu özellik açıldıktan sonra katılımcılara gönderilen onay e-postası veya SMS metni, Teams'i masaüstünde veya mobil tarayıcıda açan bir toplantıya katılma bağlantısı içerir. Desteklenen tarayıcıların listesi için bkz [. Desteklenen tarayıcılar](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Randevu türü için tarayıcı katılımını açma

Rezervasyonlar'da **Ayarlar** > **Randevu türleri'ne** gidin, bir [randevu türü](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) seçin ve katılımcıların **tarayıcıdan katılmasına izin ver'i** açın. Bunu yapmak, bu tür tüm randevular için tarayıcı katılımını sağlar.

:::image type="content" source="media/browser-join-bookings-appointment-type.png" alt-text="Bookings uygulamasında randevu türleri için Katılımcıların tarayıcıdan katılmasına izin ver ayarının ekran görüntüsü":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Tek bir randevu için tarayıcı katılımını açma

Bookings'te **Yeni rezervasyon'u** seçin ve katılımcıların **bir tarayıcıdan katılmasına izin ver'i** açın.

:::image type="content" source="media/browser-join-bookings-form.png" alt-text="Bookings uygulamasındaki yeni rezervasyon formundaki Katılımcıların tarayıcıdan katılmasına izin ver ayarının ekran görüntüsü":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Teams EHR bağlayıcısı aracılığıyla zamanlanan randevular

Sizin veya personelinizin kuruluma ihtiyacı yok!

**Cerner EHR ile tümleştirme**: Teams EHR bağlayıcısı, SMS metin iletisindeki bir bağlantı aracılığıyla sanal randevulara katılan hastaları destekler. Randevu sırasında, hastalar SMS kısa mesajındaki bağlantıya dokunarak katılabilir ve Teams tarayıcıda açılır.

**Epic EHR ile tümleştirme**: Teams EHR bağlayıcısı, MyChart web ve mobil üzerinden sanal randevulara katılan hastaları destekler. Randevu sırasında, hastalar **Sanal ziyaret** başlat düğmesini kullanarak MyChart'tan randevuyu başlatabilir ve Teams tarayıcıda açılır.

## <a name="supported-browsers"></a>Desteklenen tarayıcılar

Şu anda desteklenen tarayıcılar aşağıdadır. Aksi belirtilmedikçe en son sürümü ve iki önceki sürümü destekliyoruz.

|Ortam  |Chrome |Safari |Kenar (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; IOS veya Android'de giden ekran paylaşımı desteklenmez.

&sup2; Safari'de iOS uygulamaları mikrofon ve hoparlör cihazlarını seçemez. Örneğin, Bluetooth cihazları. Bu, varsayılan cihaz seçimini denetleyen işletim sisteminin bir sınırlamasıdır.

## <a name="things-to-consider"></a>Göz önüne alınacak noktalar

Randevuyu yürüten personel, Teams masaüstü, mobil veya web istemcisinden ekranını masaüstü veya mobil tarayıcıdan katılan bir katılımcıyla paylaşabilir. Ancak katılımcılar ekranlarını masaüstü veya mobil tarayıcıdan paylaşamaz.

## <a name="related-articles"></a>İlgili makaleler

- [Teams ve Bookings uygulamasıyla sanal randevular](bookings-virtual-visits.md)
- [Bookings randevu türü oluşturma](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Bookings randevusna katılımcı olarak katılma](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Teams ile sanal randevular - Cerner EHR ile tümleştirme](ehr-admin-cerner.md)
- [Teams ile sanal randevular - Epic EHR ile tümleştirme](ehr-admin-epic.md)
