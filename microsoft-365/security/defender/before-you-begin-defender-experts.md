---
title: Tehdit Avcılığı için Microsoft Defender Uzmanları hizmetine kaydolmadan önce temel altyapı gereksinimleri
ms.reviewer: ''
description: Bu bölümde karşılamanız gereken temel altyapı gereksinimleri ve veri erişimi ve uyumluluğuyla ilgili önemli bilgiler özetlenmiştir
keywords: yönetilen tehdit avcılığı hizmeti, yönetilen tehdit avcılığı, yönetilen algılama ve yanıt (MDR) hizmeti, MTE, Microsoft Tehdit Uzmanları, MTE-TAN, defender uzmanları bildirimi, Hedefli Saldırı Bildirimi, tehdit avcılığı ve analiz için Microsoft Defender Uzmanları.
search.product: Windows 10
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: 05b88bdb0d77f1844d70d3d1954dff192fe43135
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687471"
---
# <a name="before-you-begin-using-defender-experts-for-hunting"></a>Avcılık için Defender Uzmanlarını kullanmaya başlamadan önce

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Bu belge, karşılamanız gereken temel altyapı gereksinimlerini ve Tehdit Avcılığı için Microsoft Defender Uzmanları hizmetine kaydolmadan önce bilmeniz gereken veri erişimi ve uyumluluğu hakkında önemli bilgileri özetler. Microsoft, yönetilen hizmetlerimizi kullanan müşterilerin bize en değerli varlıklarını ve verilerini emanet ettiğini anlar.

## <a name="check-if-your-environment-meets-licensing-and-access-prerequisites"></a>Ortamınızın lisanslama ve erişim önkoşullarını karşılayıp karşılamadiğini denetleyin

Tehdit Avcılığı için Microsoft Defender Uzmanları, mevcut Defender ürünlerinizden ayrı bir hizmettir. Bu hizmete kaydolmadan önce gerekli lisansa ve erişime sahip olduğunuzdan emin olun. 

### <a name="eligibility-and-licensing"></a>Uygunluk ve lisanslama

Avcılık müşterileri için Defender Uzmanlarına her ayın ilk günü iki İsteğe Bağlı Uzman kredisi atanacak ve bu krediler soru göndermek için kullanılabilecek. Kullanılmayan kredilerin süresi, atama tarihinden itibaren 90 gün veya abonelik döneminin sonunda (hangisi en kısaysa) sona erer.

Microsoft'un ticari lisans koşulları hakkında daha fazla bilgi için [bu sayfayı ziyaret edin](https://www.microsoft.com/licensing/terms/productoffering/Microsoft365/MCA).

### <a name="access-requirements"></a>Erişim gereksinimleri

Kuruluşunuzdaki herkes, Tehdit Avcılığı hizmeti için Microsoft Defender Uzmanları için müşteri ilgi formunu doldurabilir, ancak SKU'yu işleme almak için Ticari Yöneticinizle birlikte çalışmanız gerekir. Hizmet özelliklerine tam olarak erişmek için belirli rollere ve izinlere ihtiyacınız olabilir. Ayrıntılar için [Microsoft 365 Defender için rol tabanlı erişim denetiminde özel roller](custom-roles.md) bölümüne bakın.

## <a name="understand-the-services-availability-and-data-access-requirements"></a>Hizmetin kullanılabilirlik ve veri erişim gereksinimlerini anlama

Avcılık için Defender Uzmanları uç noktalar, e-posta, kimlik ve bulut uygulamaları genelinde tehditleri proaktif olarak avlayan yönetilen bir tehdit avcılığı hizmetidir. Sizin yerinize avcılık yapmak için Microsoft uzmanlarının Microsoft 365 Defender gelişmiş tehdit avcılığı verilerinize erişmesi gerekir. Bu hizmete kaydolmak, Söz konusu verilere erişmek için Microsoft uzmanlarına izin verdiğiniz anlamına gelir.

Aşağıdaki bölümlerde hizmetin veri kullanımı, uyumluluğu ve kullanılabilirliği hakkında ek bilgiler listelenir. Microsoft'un verilerinizi değerlendirme ve koruma taahhüdü hakkında daha fazla bilgi için [Güven Merkezi'ni](https://aka.ms/trustcenter-dex4hunting) ziyaret edin > **Ek ürün ve hizmetler** > **Yönetilen Güvenlik Hizmetleri** > [**Tehdit Avcılığı için Microsoft Defender Uzmanı'na**](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE51fRH) gidin.

### <a name="data-collection-usage-and-retention"></a>Veri toplama, kullanım ve saklama

Mevcut Defender hizmetlerinden avlanmak için kullanılan tüm veriler müşterinin özgün Microsoft 365 Defender hizmet depolama konumunda bulunmaya devam eder. [Daha fazla bilgi edinin](../../enterprise/o365-data-locations.md)

Servis talebi biletleri ve analist notları gibi Tehdit Avcılığı için Defender Uzmanları, Microsoft 365 Defender hizmet depolama konumuna bakılmadan hizmetin uzunluğu için ABD bölgesindeki bir Microsoft veri merkezinde oluşturulur ve depolanır. Raporlama panosu için oluşturulan veriler müşterinin Microsoft 365 Defender hizmet depolama konumunda depolanır. Raporlama verileri ve işletimsel veriler, müşteri hizmetten ayrıldıktan sonra 90 günden az bir süre boyunca saklanır.

Microsoft uzmanları [Microsoft 365 Defender gelişmiş avcılık](../../security/defender/advanced-hunting-schema-tables.md) tablolarında gelişmiş avcılık günlüklerini avlar. Bu tablolardaki veriler müşterinin etkinleştirildiği Defender hizmetleri kümesine bağlıdır (örneğin, Uç Nokta için Microsoft Defender, Office 365 için Microsoft Defender, Kimlik için Microsoft Defender, Microsoft Defender for Cloud Apps ve Azure Active Directory). Uzmanlar ayrıca tehdit avcılığı ve otomasyonlarını bilgilendirmek için büyük bir iç tehdit zekası verileri kümesi kullanır.

### <a name="security-and-compliance"></a>Güvenlik ve uyumluluk

Avcılık için Defender Uzmanlar'ı satın alıp eklediğinizde, Microsoft uzmanlarına gelişmiş tehdit avcılığı verilerinize erişme izni verirsiniz.

Bu hizmet mevcut güvenlik ve gizlilik standartlarına uygun olarak geliştirilmiştir ve ISO 27001 ve ISO 27018 dahil olmak üzere çeşitli sertifikalar için çalışmaktadır.

### <a name="availability"></a>Kullanılabilirlik

Bu hizmet, ticari genel bulutlarımızdaki müşteriler için dünya çapında kullanılabilir. Şu anda kamu ve bağımsız bulutlardaki müşterilerin kullanımına sunulmamaktadır.

### <a name="languages"></a>Diller

Bu hizmet şu anda yalnızca İngilizce dilinde teslim edilir.

## <a name="apply-for-microsoft-defender-experts-for-hunting-service"></a>Avlanma hizmeti için Microsoft Defender Uzmanlarına başvurun

Henüz yapmadıysanız, Avcılık için Defender Uzmanları için müşteri ilgi formunu doldurabilirsiniz:

1. [Müşteri faiz formunu](https://aka.ms/DEX4HuntingCustomerInterestForm) doldurun. Şirketinizden herkes başvurabilir, ancak kabul edilirseniz, SKU'yu işleme almak için Ticari Yöneticinizle birlikte çalışmanız gerekir.
2. Adınızı, şirket adınızı ve şirket e-posta kimliğinizi girin.
3. **Gönder'i** seçin. Satış ekibimizden biri beş iş günü içinde bize ulaşacak.


### <a name="next-step"></a>Sonraki adım

- [Tehdit Avcılığı için Defender Uzmanları’nı kullanmaya başlama](onboarding-defender-experts-for-hunting.md)
