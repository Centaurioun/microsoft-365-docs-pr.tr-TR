---
title: Tam veri eşleşmesine dayalı hassas bilgi türlerini kullanmaya başlama
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Tam veri eşleştirme tabanlı hassas bilgi türleri oluşturmaya genel bir bakış edinin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9fc1af50c329b96ff77108698c8bbf952813f7f
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359502"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>Tam veri eşleşmesine dayalı hassas bilgi türlerini kullanmaya başlama

## <a name="applies-to"></a>Uygulandığı öğe 

- [Yeni deneyim](sit-create-edm-sit-unified-ux-workflow.md)
- [Klasik deneyim](sit-create-edm-sit-classic-ux-workflow.md)

Tam olarak veri eşleşmesi (EDM) tabanlı hassas bilgi türü (SIT) oluşturmak ve kullanıma sunulması çok fazlı bir işlemdir. *Yeni deneyimi* mevcut *klasik deneyimi* veya PowerShell aracılığıyla kullanabilirsiniz. Bu makale, iki deneyim arasındaki farkları anlamanıza ve ihtiyaçlarınıza uygun olanı seçmenize yardımcı olur.

EDM SID'leri şu durumlarda kullanılabilir:

- Microsoft Purview Veri Kaybı Önleme
- Otomatik etiketleme (hizmet ve istemci tarafı)
- Microsoft Purview İçeriden Risk Yönetimi ilkeleri
- Microsoft Purview eKeşif
- Microsoft Purview İçeriden Risk Yönetimi
- Bulut Uygulamaları için Microsoft Defender



## <a name="before-you-begin"></a>Başlamadan önce

Bu makalelerdeki kavramlar ve terimler hakkında bilgi edinin:

- [Hassas bilgi türleri hakkında daha fazla bilgi edinme](sensitive-information-type-learn-about.md)
- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md)

## <a name="supported-regions"></a>Desteklenen bölgeler

Tam veri eşleşmesi şu bölgelerde kullanılabilir:

- Asya Pasifik
- Avustralya
- Brezilya
- Kanada
- Avrupa
- Fransa
- Almanya
- Hindistan
- Japonya
- Kore
- Norveç
- South Africa
- İsviçre
- Birleşik Arap Emirlikleri
- Birleşik Krallık
- Amerika Birleşik Devletleri
- ABD DoD
- ABD GCC
- ABD GCCH

[Microsoft 365 müşteri verilerinizin depolandığı yer](../enterprise/o365-data-locations.md) başlığındaki yordamları izleyerek ve aynı makaledeki veri merkezi şehir konumlarına başvurarak kiracınızın bekleyen verileri barındırdığı bölgeyi öğrenebilirsiniz.

## <a name="required-licenses-and-permissions"></a>Gerekli lisanslar ve izinler

Bu makalede açıklanan görevleri gerçekleştirmek için genel yönetici, uyumluluk yöneticisi veya Exchange Online yöneticisi olmanız gerekir. DLP izinleri hakkında daha fazla bilgi edinmek için bkz. [İzinler](data-loss-prevention-policies.md#permissions).

Tam lisans bilgileri için [veri kaybı önleme hizmeti açıklamasına](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) bakın

## <a name="portal-links-for-your-subscription"></a>Aboneliğiniz için portal bağlantıları

|Portal|World Wide/GCC|GCC-High|Dod|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 Defender portalı|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft Purview uyumluluk portalı|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="new-edm-experience"></a>Yeni EDM deneyimi

Yeni EDM deneyimi, EDM şeması ve EDM hassas bilgi türleri sihirbazlarının işlevselliğini tek bir kullanıcı deneyiminde birleştirir. Yeni deneyim aşağıdakileri ekler:

### <a name="simplified-workflow"></a>Basitleştirilmiş iş akışı

Yeni deneyimle, şema ve SIT daha az tıklama anlamına gelen bir kullanıcı deneyimi, birincil öğeleri varsayılan SID'lere eşlemeye yönelik daha iyi rehberlik ve kurallar için varsayılan güvenilirlik düzeyleri aracılığıyla oluşturulur.

Oluşturma işleminde bir EDM SIT'in durumunu görmeniz gerektiğinde, yeni deneyim kullanıcı arabiriminde bunu bildirir.

- Veriler henüz karşıya yüklenmedi
- Veri yükleme yüzdesi
- Verileri karşıya yükleme tamamlandı
- Dizin oluşturma tamamlandı
- Veri karşıya yüklenemedi
- Veri dizin oluşturma başarısız oldu


### <a name="automated-schema-and-sit-creation"></a>Otomatik şema ve SIT oluşturma

Yeni deneyimde, aynı üst bilgi değerlerine ve sisteme yeterli sayıda temsili veri (10-20) satırına sahip bir örnek veri dosyası sağlayabilirsiniz. Sistem biçimi doğrular ve üst bilgileri temel alarak şemayı oluşturur. Ardından şemadaki birincil alanları tanımlarsınız ve sistem, birincil alanla ilişkilendirmek için en uygun SID'leri önerir. Dosyayı karşıya yüklemek istemiyorsanız, aynı değerleri kullanıcı arabirimine el ile girebilirsiniz.

> [!IMPORTANT]
> Hassas olmayan ancak gerçek hassas verilerinizle aynı biçimde olan örnek veri değerlerini kullandığınızdan emin olun. Hassas olmayan verilerin kullanılması çok önemlidir çünkü örnek veri dosyası, gerçek hassas bilgi tablosunda olduğu gibi karşıya yüklediğinizde şifrelenmez ve karmalanmaz. EDM SIT oluşturulduktan sonra örnek veri dosyasındaki veriler korunmaz veya erişilebilir olmaz.

Sistem, her birincil alan için bir tane olan EDM SIT algılama kurallarını oluşturur. Birincil alanların algılanması temelinde sistem, diğer tüm alanları doğrulayıcı kanıt olarak kullanarak yüksek ve orta düzeyde güvenilirlik kuralları oluşturur. İsterseniz düşük güvenilirlik kuralları ekleyebilirsiniz. 

### <a name="additional-guardrails-to-ensure-better-performance"></a>Daha iyi performans sağlamak için ek korumalar

<!--As the Azure-based EDM cloud service leverages a shared infrastructure, a misconfigured EDM SIT that triggers excessive EDM lookups could impact EDM performance for other customers if it wasn't controlled. This is prevented by throttling instances where EDM is misconfigured in a way that would cause excessive lookups.--> 

Sistem, *gevşek tanımlı* SIT olarak adlandırılan çok çeşitli değerleri algılayan bir SIT ile eşlenmiş birincil alan bulursa sizi uyarır.  Bu, sistemin aradığınız içerik türüyle ilgili olmayan çok sayıda dize üzerinde aramalar gerçekleştirmesine neden olabilir. Bu tür SID'ler ve birincil alanlar arasında eşleme, hatalı negatiflere neden olabilir ve performansı düşürebilir.

> [!NOTE]
> Tüm kişisel kimlik numaralarının arandığı özel bir *sit gibi gevşek tanımlanmış sit*, algılanan öğelerde daha fazla değişkenlik sağlayan algılama kurallarına sahiptir. ABD Sosyal Güvenlik Numarası gibi *güçlü tanımlanmış bir SIT,yalnızca* dar, iyi tanımlanmış bir öğe kümesinin algılanmasına izin veren algılama kurallarına sahiptir. 

Seçtiğiniz birincil alandaki değerler çok sayıda satırda birden çok kez gerçekleşirse sistem sizi uyarır. Bu, çok sayıda sonuç kümesinin döndürülerek işlenmesine neden olabilir ve bu da zaman aşımına neden olabilir. Zaman aşımları, eksik algılamalara ve düşük performansa neden olabilir.


## <a name="choosing-the-right-edm-sit-creation-experience-for-you"></a>Sizin için doğru EDM SIT oluşturma deneyimini seçme

Yeni ve klasik deneyimler arasında geçiş yapabilirsiniz, ancak gereksinimleriniz bu dört kullanım örneğinden birine veya daha fazlasına dahil edilmediği sürece yeni deneyimi kullanmanızı öneririz. 

1. Bu bölümü okuyun
1. Kullanmak istediğiniz deneyimi seçin
1. İstediğiniz deneyim için [Sonraki adım](#next-steps) bağlantısını seçin.

### <a name="you-want-to-map-multiple-edm-sits-to-the-same-schema"></a>Birden çok EDM SITS'i aynı şemaya eşlemek istiyorsunuz

EDM'de en fazla 10 şema oluşturabilirsiniz. Yeni deneyimi kullanarak her EDM SIT oluşturduğunuzda yeni bir şema oluşturulur. Bu, EDM şeması ile EDM SIT arasında 1:1 eşlemesi ile sonuçlanır. Yeni deneyim, aynı şemaya birden çok SıT eşlemeyi desteklemez.

### <a name="you-need-to-create-or-manage-more-than-10-edm-sits"></a>10'dan fazla EDM SID oluşturmanız veya yönetmeniz gerekir

 Yeni deneyim aynı şemaya birden çok SID eşlemeyi desteklemediğinden, 10 EDM SITS oluşturma ve yönetme ile sınırlısınız. Klasik deneyimde, birden çok EDM SID'sini aynı şemaya eşleyebilirsiniz ve bu nedenle 10'dan fazla EDM SID'si vardır. Yeni akışı kullanarak, on birinci EDM şeması oluşturmaya çalışırsanız bir hata alırsınız ve 10'dan fazla EDM SID'sini görüntüleyemezsiniz.

### <a name="you-need-to-specify-the-name-of-your-edm-schema"></a>EDM şemanızın adını belirtmeniz gerekir

EDM SIT şemalarınız için bir ad belirtmeniz gerekiyorsa, bunları oluşturmak ve yönetmek için klasik deneyimi kullanmanız gerekir. Yeni deneyim şemayı otomatik olarak oluşturduğundan, şemanıza özel bir ad verme fırsatı elde etmezsiniz. Otomatik oluşturulan ad, EDM SIT adı ve *şema* sözcüğünün birleştirilmiş bir sonucudur. Örneğin, EDM SIT adı *PatientNumber* ise şema adı *PatientNumberschema* olur.

### <a name="you-need-to-edit-edm-schemas-that-were-created-in-the-classic-experience"></a>Klasik deneyimde oluşturulan EDM şemalarını düzenlemeniz gerekir

Klasik deneyim kullanılarak oluşturulan veya PowerShell kullanılarak XML dosyası olarak yüklenen tüm şemalar yeni deneyimde görüntülenemez veya yönetilemez.

## <a name="next-steps"></a>Sonraki adımlar

- [Hassas bilgi türü yeni deneyimiyle tam veri eşleştirmesi oluşturma](sit-create-edm-sit-unified-ux-workflow.md)

veya

- [Hassas bilgi türü klasik deneyimiyle tam veri eşleştirmesi oluşturma](sit-create-edm-sit-classic-ux-workflow.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md)
- [Tam veri eşleşmesine dayalı hassas bilgi türleri için kaynak verilerini dışa aktarma](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
- [Hassas bilgi türü iş akışı yeni deneyimiyle tam veri eşleştirmesi oluşturma](sit-create-edm-sit-unified-ux-workflow.md)
- [Hassas bilgi türü iş akışı klasik deneyimiyle tam veri eşleştirmesi oluşturma](sit-create-edm-sit-classic-ux-workflow.md)