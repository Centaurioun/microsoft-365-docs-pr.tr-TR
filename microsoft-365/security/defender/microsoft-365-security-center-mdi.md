---
title: Microsoft 365 Defender'da Kimlik için Microsoft Defender
description: Kimlik için Microsoft Defender Microsoft 365 Defender değişiklikleri hakkında bilgi edinin
keywords: Microsoft 365 Defender, Kimlik için Microsoft Defender, NDI ile çalışmaya başlama
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 07/06/2022
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 53c43c3196a22a97b2f11105f5145bd62229b137
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66862324"
---
# <a name="microsoft-defender-for-identity-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Kimlik için Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Kimlik için Microsoft Defender](/defender-for-identity/)

Kimlik için Microsoft Defender artık Microsoft 365 Defender bir parçasıdır. Microsoft 365 Defender portalı, güvenlik yöneticilerinin güvenlik görevlerini tek bir konumda gerçekleştirmesine olanak tanır. Bu, iş akışlarını basitleştirir ve diğer Microsoft 365 Defender hizmetlerinin işlevselliğini ekler. Microsoft 365 Defender Microsoft kimlikleriniz, verileriniz, cihazlarınız, uygulamalarınız ve altyapınız genelinde güvenliği izlemeye ve yönetmeye ev sahipliği yapacaktır.

Kimlik için Microsoft Defender, kimlik odaklı bilgileri Microsoft 365 Defender sunan olaylara ve uyarılara katkıda bulunur. Bu bilgiler bağlam sağlamak ve Microsoft 365 Defender içindeki diğer ürünlerden gelen uyarıları ilişkilendirmek için önemlidir.

## <a name="quick-reference"></a>Hızlı başvuru

Aşağıdaki tabloda, Kimlik için Microsoft Defender ile Microsoft 365 Defender arasındaki gezinti değişiklikleri listelenmiştir.

| **Için Defender** Kimlik  | **Microsoft 365 Defender**                                   |
| -------------------------- | ------------------------------------------------------------ |
| Zaman çizelgesi                   | uyarılar/olaylar kuyruğu Microsoft 365 Defender                |
| Raporlar                    | [Klasik Kimlik için Defender portalında](/defender-for-identity/classic-workspace-portal) kalır. <br> Özelleştirilmiş raporlar, [gelişmiş avcılık](#advanced-hunting-new) kullanılarak Microsoft 365 Defender portalında oluşturulabilir.               |
| Kullanıcı sayfası                  | Microsoft 365 Defender Kullanıcı sayfası                             |
| Cihaz sayfası                | Microsoft 365 Defender Cihaz sayfası                           |
| Grup sayfası                 | grupların yan bölmesini Microsoft 365 Defender                      |
| Uyarı sayfası                 | uyarı sayfasını Microsoft 365 Defender                            |
| Arama                     | Microsoft 365 Defender Arama                                |
| Sistem sağlığı merkezi              | Ayarlar -> Kimlikleri -> Algılayıcıları                            |
| Varlık Etkinlikleri          | Gelişmiş avcılık örneği                                             |
| Ayarlar                   | Ayarlar -> Kimlikleri                                       |
| Kullanıcılar ve hesaplar         | Varlıklar -> Kimlikleri                                         |
| Kimlik güvenliği duruşu  | [Kimlik için Microsoft Defender güvenlik duruşu değerlendirmeleri](/defender-for-identity/security-assessment) |
| Yeni çalışma alanı ekleme | Ayarlar -> Kimlikleri (otomatik olarak)                       |

## <a name="whats-changed"></a>Değişenler

### <a name="defender-for-identity-settings"></a>Kimlik için Defender ayarları

Kimlik için Microsoft Defender yapılandırma ayarlarına erişmek için [Microsoft 365 Defender](https://security.microsoft.com) **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

### <a name="defender-for-identity-security-posture"></a>Kimlik için Defender güvenlik duruşu

Daha önce Cloud Apps için Defender'da erişilebilen tüm kimlik güvenliği duruşu yönetim değerlendirmeleri artık [Microsoft 365 Defender portalında](https://security.microsoft.com) bulunan Microsoft Güvenli Puanı'nda <https://security.microsoft.com/securescore> kullanılabilir. Daha fazla bilgi için bkz. [Kimlik için Microsoft Defender güvenlik duruşu değerlendirmeleri](/defender-for-identity/security-assessment).

### <a name="global-search"></a>Genel arama

Microsoft 365 Defender'da genel arama (sayfanın üst kısmındaki arama çubuğunu kullanarak), güvenlik ekiplerinin kimlik, uç nokta, Office 365 verileri ve daha fazlası gibi Microsoft 365 Defender tarafından izlenen herhangi bir varlığı aramasına olanak tanır. Sonuçlar doğrudan arama açılan listesinden etkileşime eklenebilir veya güvenlik ekipleri tüm **kullanıcılar'ı** veya **Tüm cihazlar'ı**  seçerek bu arama terimiyle ilişkili tüm varlıkları görebilir.

### <a name="onboarding-and-administration"></a>Ekleme ve yönetim

Ekleme işlemi artık yeni müşteriler için otomatiktir ve çalışma alanını el ile yapılandırmanıza gerek yoktur. Ayrıca, tüm yönetici özellikleri Microsoft 365 Defender Ayarlar'daki **Kimlikler** menüsünde kullanılabilir.

### <a name="alerting-and-incident-correlation"></a>Uyarı ve olay bağıntısı

Kimlik için Defender uyarıları artık Microsoft 365 Defender uyarı kuyruğuna eklendiğinden otomatik olay bağıntı özelliği tarafından kullanılabilir. Bu, tüm uyarıların tek bir yerde kullanılabilir olmasını ve ihlal kapsamının öncekinden daha hızlı belirlenebilmesini sağlar. Daha fazla bilgi için bkz. [Microsoft 365 Defender'da Kimlik için Defender güvenlik uyarıları](/defender-for-identity/manage-security-alerts).

### <a name="advanced-hunting-new"></a>Gelişmiş avcılık (yeni)

Artık gelişmiş tehdit avcılığı sorgularını kullanarak tehditleri ve kötü amaçlı etkinlikleri proaktif olarak arayabilirsiniz. Bu güçlü sorgular, hem bilinen hem de olası tehditler için tehdit göstergelerini ve varlıkları bulmak ve gözden geçirmek için kullanılabilir.

Özel algılama kuralları, ihlal etkinliğinin ve yanlış yapılandırılmış cihazların göstergesi olabilecek olayları proaktif olarak izlemenize yardımcı olmak için gelişmiş tehdit avcılığı sorgularından oluşturulabilir. Daha fazla bilgi için bkz. [Microsoft 365 Defender'da gelişmiş avcılık ile tehditleri proaktif olarak avlama](advanced-hunting-overview.md).

### <a name="alert-exclusions-updated"></a>Uyarı dışlamaları (güncelleştirildi)

Uyarı arabirimi, kullanışlı bir arama işlevi eklemek de dahil olmak üzere daha kullanıcı dostudur. Buna ek olarak, artık genel dışlamalar da içerir. Bu, herhangi bir varlığın Kimlik için Defender tarafından oluşturulan tüm uyarıların dışında tutulabileceği ve sahip olabileceğiniz test senaryolarına yardımcı olabileceği anlamına gelir. Daha fazla bilgi için bkz[. Microsoft 365 Defender'de Kimlik algılama dışlamaları için Defender'ı yapılandırma](/defender-for-identity/exclusions).

### <a name="entity-profiles"></a>Varlık profilleri

Kimlik için Defender verileri artık Microsoft 365 Kullanıcı ve Cihaz varlık profillerine dahil edilir.

### <a name="remediation-actions-new"></a>Düzeltme eylemleri (yeni)

Hesapları devre dışı bırakma veya parola sıfırlama gerektirme gibi Kimlik için Defender düzeltme eylemleri artık Microsoft 365 Defender Kullanıcı sayfasından gerçekleştirilebilir. Daha fazla bilgi için bkz[. Kimlik için Microsoft Defender düzeltme eylemleri](/defender-for-identity/remediation-actions).

### <a name="lateral-movement-paths"></a>Yanal hareket yolları

Kullanıcı sayfasındaki **Yanal hareket yolları** sekmesine ek olarak, **Gelişmiş avcılık** özelliği ve YanAl Hareket yolları güvenlik değerlendirmesi aracılığıyla yanal hareket yolları da bulunabilir. Daha fazla bilgi için bkz. [Kimlik için Microsoft Defender YanAl Hareket Yolları (LMP)](/defender-for-identity/understand-lateral-movement-paths).

## <a name="related-videos"></a>İlgili videolar

- [Kimlik için Microsoft Defender için yeni](https://www.microsoft.com/videoplayer/embed/RE4HcEU)

## <a name="related-information"></a>İlgili bilgiler

- [Microsoft 365 Defender](microsoft-365-defender.md)
