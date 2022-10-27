---
title: Bookings iş akışları oluşturmak için Power Automate bağlayıcılarını kullanma
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
description: Randevu tetikleyicileriyle özel iş akışları oluşturmak için Power Automate Bookings Bağlayıcıları'nı kullanın.
ms.openlocfilehash: 1c6f0bbcf2aa5ef8fecf410effe7ec4baebaa099
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68736485"
---
# <a name="use-power-automate-connectors-to-build-bookings-workflows"></a>Bookings iş akışları oluşturmak için Power Automate bağlayıcılarını kullanma

Microsoft Bookings Bağlayıcısı, Booking randevularını güç platformlarının sunması gereken diğer işlevlerle genişletmek için oluşturulmuş. İş müşteri randevularınız için özel iş akışları oluşturmak, örneğin müşterilerin randevuyla birlikte Zoom toplantısı rezervasyonu yapmalarına, Stripe kullanarak bir ödeme yöntemini tümleştirmelerine, müşteri verilerini CRM sistemine yüklemelerine veya karşılama e-postaları göndermelerine izin vermek istiyorsanız Bookings Bağlayıcısı Bookings çözümünüzdür.

## <a name="before-you-begin"></a>Başlamadan önce

Bookings Bağlayıcısı'nı kullanmak isteyen müşterilerin Bookings lisansına sahip olması gerekir. Microsoft Bookings lisansları ve abonelikleri hakkında daha fazla bilgi için bkz. [Microsoft Bookings Sık Sorulan Sorular](bookings-faq.yml#is-bookings-available-for-my-subscription-).

Microsoft Bookings, Azure Active Directory (AAD) kimlik doğrulamasını kullanır. Geçerli bir Microsoft 365 hesabı, Bookings Bağlayıcısı'nı kullanmak için kimliğinizin doğrulanmasını sağlar. Randevu tabanlı akışlar oluşturmak için oturum açmanız gerekir.

Bookings randevularını tetikleyici olarak kullanan özel bir akış oluşturmak için Bookings iş SMTP adresini sağlamanız gerekir.

![SMTP adresinin resmi.](media/bookings-teams-smtp.png)

## <a name="get-started-with-connectors"></a>Bağlayıcıları kullanmaya başlama

Microsoft Bookings Bağlayıcıları ile oluşturabileceğiniz yaygın akışlardan bazıları şunlardır:

### <a name="integration-with-stripe"></a>Stripe ile tümleştirme

Stripe, özel kişilerin ve işletmelerin internet üzerinden ödemeleri kabul etmesine olanak tanır. Müşterileri, siparişleri, faturaları ve daha fazlasını izleyebilirsiniz. Daha fazla bilgi için bkz [. Stripe | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_stripe/stripe/).

### <a name="integration-with-zoom"></a>Zoom ile tümleştirme

Yakınlaştırma Toplantıları bağlayıcısı, Yakınlaştırma toplantı işlemlerini otomatikleştirmeye yardımcı olur. Daha fazla bilgi için bkz [. Yakınlaştırma Toplantıları (Bağımsız Yayımcı) | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_zoommeetingsip/zoom-meetings-independent-publisher/).

### <a name="integration-with-dynamic-365"></a>Dinamik 365 ile tümleştirme

Dynamics 365 Sales İçgörüler, ilişkilerin oluşturulmasına yardımcı olmak için kişiselleştirilmiş etkileşimi ve proaktif karar alma sürecini teşvik eden Yapay Zeka (AI) odaklı içgörülerin yardımıyla satışların artırılmasına yardımcı olur. Daha fazla bilgi için bkz[. Dynamics 365 Sales Insights | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_assistantstudio/dynamics-365-sales-insights/).

Tüm kullanılabilir Bookings bağlayıcıları için bkz [. Desteklenen bağlayıcılar | Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/).

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- **Yalnızca yöneticiler randevu tetikleyicilerini kullanarak akış oluşturabilir.** Yalnızca Bookings yöneticileri randevu tetikleyicileri oluşturabilir. Yönetici değil de kullanıcıysanız (Ekip Üyesi, Zamanlayıcı, Görüntüleyici, Konuk) yöneticinizden akış oluşturmasını istemeniz gerekir. Alternatif olarak, yönetici erişimi de isteyebilirsiniz.

- **Bookings posta kutusu başına yalnızca beş akış oluşturulabilir.** Bu, yönetici başına değil Bookings posta kutusu düzeyinde bir sınırdır. Randevu tetikleyicisi için birden fazla eylem istiyorsanız, Eylemi Ekle düğmesiyle eylemi mevcut akışlardan birine **ekleyebilirsiniz** . Destek için diğer Booking yöneticilerine başvurun.

- **Bazı Bookings parametreleri doldurulmuyor.** 1:1 Rezervasyonları için İptal Nedeni ve Özel Notlar doldurulmuyor. Bunun düzeltmesi yakında kullanıma sunulacaktır.

- **Akış oluşturma sırasındaki hata kodları tam olarak görünür değildir.** Akış oluşturulurken oluşabilecek hatalar akış portalında görünmez. Bunun düzeltmesi devam etmektedir ve sonraki sürümde kullanıma sunulacaktır.

## <a name="common-errors-and-remedies"></a>Yaygın hatalar ve çözümler

Akış oluştururken HTTP Hata Kodları:

- '401': Bağlantınızdaki kimlik doğrulamasıyla ilgili sorunları denetleyin.
- '403': Yalnızca Bookings yöneticileri randevu akışları oluşturabilir. Yukarıdaki "Bilinen sorunlar ve sınırlamalar" içindeki ilk soruna bakın.
- '403': Bildirim URL'si etki alanı izin verilenler listesinin bir parçası değil.
- '429': bir işletme için beklenen randevu akışı sayısından daha fazla oluşturuldu. Yukarıdaki "Bilinen sorunlar ve sınırlamalar" bölümünde Bookings posta kutusu başına beş akış sınırına bakın.
- '500': Bu bir iç sunucu hatasıdır. Bu hatayı destek mühendisinize bildirin ve hata ayrıntılarını akış oluşturma yanıtına ekleyin.

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular

**Randevu tetikleyicisi tabanlı akış oluşturmak için SMTP adresini Nasıl yaparım? alır?**

Randevu tetikleyici tabanlı akışlar oluşturmak için oluşturucunun Bookings işinin SMTP adresini alması gerekir. Bu, grafik çağrıları yapmak için kullanılan SMTP adresiyle aynıdır. Bu aynı zamanda Bookings sayfası URL'sinin bir parçasıdır.

**Randevu tetikleyici yanıtlarından müşteri verilerini nasıl alabilirim?**

1:1 rezervasyon için CustomerName, CustomerEmail gibi üst düzey alanlar mevcuttur. Grup rezervasyonu için, müşteriler dizisi displayName, müşteri e-postası, müşteriler displayName gibi alanları bir power automate döngü bileşeniyle kullanabilir.

**StaffMembers neden bir dizidir?**

Konak olarak birden fazla personel üyesi atayabilirsiniz. Hizmetinizde konak olarak atanan yalnızca bir personel üyesi varsa personel ayrıntıları personel üyesi dizisinde görülür.

## <a name="related-content"></a>İlgili içerik

[Microsoft Power Automate Bağlayıcıları](https://make.preview.powerautomate.com/connectors/shared_microsoftbookings/microsoft-bookings/)\
[Microsoft Bookings (Önizleme) Başvurusu](/connectors/microsoftbookings/) (makale)