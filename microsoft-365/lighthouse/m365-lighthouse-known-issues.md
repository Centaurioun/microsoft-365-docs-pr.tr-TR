---
title: Microsoft 365 Lighthouse ile ilgili bilinen sorunlar
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthous
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için, Özellik alanına göre Lighthouse ile ilgili bilinen sorunların listesine bakın.
ms.openlocfilehash: 700af168113641bdc0fd4e9ede507148dced58db
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596214"
---
# <a name="known-issues-with-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse ile ilgili bilinen sorunlar

Bu makalede, özellik alanına göre Microsoft 365 Lighthouse ile ilgili bilinen sorunlar listelenir. Lighthouse hakkında daha fazla bilgi için bkz. [Microsoft 365 Lighthouse genel bakış](m365-lighthouse-overview.md).

## <a name="users"></a>Kullanıcılar

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Kullanıcı ayrıntıları bölmesindeki OneDrive sekmesinde veri görüntü yok** | MSP teknisyeni, kullanıcı ayrıntıları bölmesindeki OneDrive sekmesinde OneDrive verilerini görüntülemeye çalıştığında şu iletiyi görür: "OneDrive bu kullanıcı için ayarlanmadı. Kişiden ayarlamak için portal.office.com/onedrive gitmesini isteyin. Biraz zaman alabilir. Bu iletiyi 24 saat sonra hala görüyorsanız desteğe başvurun." | OneDrive sekmesi şu anda temsilci kimlik doğrulamasını desteklemez. Sorunu geçici olarak çözmek için MSP teknisyenlerinin müşterinin kimlik bilgilerini kullanarak oturum açarak Microsoft 365 yönetim merkezi OneDrive verilerini görüntülemesi gerekir. |

## <a name="threat-management"></a>Tehdit yönetimi

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Tehdit adı eksik** | MSP teknisyenleri Tehdit yönetimi sayfasından tehdit listesini görüntülediğinde, bazı tehditlerde tehdidin adı eksik olabilir. Tehdit algılanan cihaz yakın zamanda Intune'dan kaldırıldığında bu durum ortaya çıkar. | Sorun 48 saat içinde çözülecektir. Ek adım gerekmez. |

## <a name="baselines"></a>Temel

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Eski kimlik doğrulamasını engelleme ve MFA dağıtım adımlarını karşılaştırırken çakışan ayarlar** | Müşteri kiracısı eski kimlik doğrulamasını engelle ve MFA dağıtım adımlarından birini dağıttıysa, karşılaştırma testi hatalı bir şekilde bu ayarları çakışıyor olarak tanımlar. | Geçici çözüm gerekmez. Ayarlar aslında çakışmaz ve müşteri kiracısında kullanıcılar etkilenmez. |

## <a name="windows-365"></a>Windows 365

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Sağlamayı yeniden deneme hatası** | MSP teknisyenleri, Bulut bilgisayar sağlamayı yeniden denemeyi denerken "Bunu yapma izniniz yok" hata iletisini alır. | Bu sorunu geçici olarak çözmek için müşteri kiracısında oturum açın ve ardından Microsoft Endpoint Manger yönetim merkezinden Bulut bilgisayarları yeniden sağlayın. Yönergeler için bkz. [Bulut bilgisayarı yeniden sağlama](/windows-365/enterprise/reprovision-cloud-pc). |

## <a name="delegated-admin-privileges-dap"></a>Temsilci Yönetici Ayrıcalıkları (DAP)

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **DAP rollerini değiştirirken izin gecikmesi** | bir MSP teknisyeni Yönetici Aracısı veya Yardım Masası Aracısı grubuna eklenirse veya gruptan kaldırılırsa, Lighthouse içindeki uygun izinlerin yansıtılmasında gecikme olabilir. | Sorun 30 dakika içinde çözülecektir. Ek adım gerekmez. |

## <a name="granular-delegated-admin-privileges-gdap"></a>Ayrıntılı Temsilci Yönetici Ayrıcalıkları (GDAP)

Müşterileri Lighthouse'a eklemek için Ayrıntılı Temsilcili Yönetici Ayrıcalıkları (GDAP) ve dolaylı bayi ilişkisi ya da Temsilci Yönetici Ayrıcalıkları (DAP) ilişkisi gerekir. MÜŞTERI kiracısında DAP ve GDAP birlikte varsa, GDAP özellikli güvenlik gruplarındaki MSP teknisyenleri için GDAP izinleri önceliklidir. Yalnızca GDAP ilişkileri olan müşteriler (dolaylı kurumsal bayi ilişkileri olmadan) şu anda Lighthouse'a eklenemez, ancak gelecekteki bir sürümde ekleme yapabilir.<br><br>

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Lighthouse genelinde çeşitli GDAP izin sorunları** | Bazı GDAP rolleri, Lighthouse'daki müşteri verilerine tek kiracılı bir deneyimde olduğu gibi aynı düzeyde erişim vermez. Aşağıdaki rollerden herhangi biri MSP teknisyenlerine ayrı ayrı atanırsa (bu, diğer GDAP rolleriyle birlikte değil) aşağıdakiler de dahil olmak üzere hatalarla karşılaşabilir:<ul><li>GDAP Güvenlik Yöneticileri, Lighthouse'da riskli kullanıcıları görüntüleyemiyor, riskleri kapatamıyor veya güvenliği aşılmış kullanıcıları onaylayamıyor.</li><li>GDAP Güvenlik Okuyucuları Lighthouse'da riskli kullanıcıları görüntüleyemez.</li><li>GDAP Genel Yöneticileri Lighthouse'da hizmet durumunu görüntülemeye çalışırken bir hata iletisi görür.</li><li>GDAP Genel Yöneticileri Lighthouse'da dağıtım planı adımlarını dağıtırken sorunlarla karşılaşır.</li></ul> | Geçici çözüm, MSP teknisyenlerine ihtiyaç duydukları müşteri verilerine erişim düzeyine göre GDAP rollerinin bir birleşimini atamaktır. Lighthouse'un kullanılması önerilen GDAP rollerinin listesi için bkz. [Microsoft 365 Lighthouse'de izinlere genel bakış](m365-lighthouse-overview-of-permissions.md).<br><br>GDAP Genel Yönetici izinlerinin bile Lighthouse'da bir özelliğin kullanımına izin vermediği sorunlar için geçici çözüm, müşteriyi yönetmek için müşteri kiracısından uygun yönetim merkezine erişmektir (örneğin, hizmet durumunu denetlemek için müşteri kiracısından Microsoft 365 yönetim merkezi erişin). GDAP ilişkisini değiştirme yönergeleri için bkz. [Müşterinin hizmetini yönetmek için ayrıntılı yönetici izinleri alma - İş Ortağı Merkezi](/partner-center/gdap-obtain-admin-permissions-to-manage-customer). |

## <a name="localization"></a>Yerel -leştirme

| Sorun | Açıklama | Çözüm |
| ---------------- | ---------------- | ---------------- |
| **Çeviri sorunları** | Kullanıcılar, tarayıcılarının dili veya Lighthouse'daki dil seçimleri İngilizce dışında bir şey olduğunda dil çevirisi sorunlarıyla karşılaşabilir. | Lighthouse'da çeviri sorunlarını en aza indirmek için tarayıcının dil seçiminin Lighthouse portalındaki dil ayarıyla eşleştiğinden emin olun. Lighthouse'da dil seçimini değiştirmek için Lighthouse'da oturum açın ve sayfanın üst kısmındaki dişli simgesini seçerek Portal ayarları sayfasını açın, **Dil + bölge'yi** seçin ve ardından uygun dil ve bölgesel biçimleri seçin. |

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)\
[Microsoft 365 Lighthouse hata iletilerini ve sorunlarını giderme](m365-lighthouse-troubleshoot.md) (makale)\
[Microsoft 365 Lighthouse için yardım ve destek alma](m365-lighthouse-get-help-and-support.md) (makale)
