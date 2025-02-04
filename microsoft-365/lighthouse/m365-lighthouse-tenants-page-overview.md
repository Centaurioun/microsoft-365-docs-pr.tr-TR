---
title: Microsoft 365 Lighthouse'da Kiracılar sayfasına genel bakış
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: kywirpel
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için Kiracılar sayfası hakkında bilgi edinin.
ms.openlocfilehash: 59b1071aa698e6e44086223c2388bc4746a11347
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734505"
---
# <a name="overview-of-the-tenants-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'da Kiracılar sayfasına genel bakış

Microsoft 365 Lighthouse, kiracılar sayfasını açmak için sol gezinti bölmesinde **Kiracılar'ı** seçerek kiracı hesaplarını yönetmenize olanak tanır. Kiracılar sayfası tüm kiracılarınızın listesini içerir. Kişi ayrıntıları ve dağıtım durumu gibi ayrıntılı bilgileri görüntülemek için bir kiracı seçebilirsiniz.

Kiracılar sayfası aşağıdaki seçenekleri de içerir:

- **Ihracat:** Kiracı verilerini Excel virgülle ayrılmış değerler (.csv) dosyasına dışarı aktarmak için seçin.
- **Etiketleri Yönet:** Etiket eklemek, düzenlemek veya silmek için seçin.
- **Etiketleri Ata:** Kiracıya etiket atamak için öğesini seçin.
- **Arama:** Listede belirli bir kiracıyı hızla bulmak için anahtar sözcükler girin.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-page-overview.png" alt-text="Kiracı sayfasının ekran görüntüsü.":::

## <a name="tenant-list"></a>Kiracı listesi

Kiracı listesi, sözleşmeniz olan farklı kiracılara ilişkin içgörüler sağlar ve bunların kiracı Lighthouse ekleme durumu da buna dahildir. Kiracı listesi ayrıca Lighthouse genelinde farklı filtreler sağlamak için kiracıları etiketlemenize ve belirli bir kiracı ve dağıtım planının durumu hakkında daha fazla bilgi edinmek için detaya gitmenizi sağlar.

Kiracılarınız [Lighthouse ekleme gereksinimlerini karşıladıktan](m365-lighthouse-requirements.md) sonra kiracı listesinde durumu **Etkin** olarak gösterilir.

Kiracı listesi şunları yapmanızı sağlar:

- Kiracıları etkin, etkin olmayan ve uygun olmayanlara göre otomatik olarak sıralayın.
- Kiracı listesini dışarı aktarın.
- Etiketleri atama ve yönetme.
- Kiracıları ada göre arayın.
- Kiracıları duruma, temsilci yönetim ayrıcalığına (DAP) ve etiketlere göre filtreleyin.

Kiracıyı devre dışı bırakmak veya etiketleri görüntülemek ve yönetmek için kiracı adının yanındaki üç noktayı (diğer eylemler) seçin. Kiracı adını seçerek veya kiracıya atanan etiketlerden birini seçerek tek tek kiracıları görüntüleyebilirsiniz.

Kiracı ekleme hakkında bilgi için bkz. [İş Ortağı Merkezi hesabınızda birden çok kiracı ekleme ve yönetme](/partner-center/multi-tenant-account).

## <a name="tenant-status"></a>Kiracı durumu

Aşağıdaki tabloda farklı durumlar ve anlamları gösterilmektedir. Müşteri kiracısı durumlarını giderme hakkında bilgi için bkz. [Microsoft 365 Lighthouse: Müşteri kiracı eklemesinde hata iletilerini ve sorunları giderme](m365-lighthouse-troubleshoot.md#customer-tenant-onboarding).<br><br>

| Durum                                   | Açıklama                                                                                             |
|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Etkin                                   | Kiracı ekleme ve veri akışı başlatıldı.                                                           |
| Etkin olmayan                                 | Kiracı, MSP'nin isteği üzerine eklendi ve artık Lighthouse'da yönetilmedi.           |
| İşlemde                               | Kiracı bulundu ancak tam olarak eklenmedi.                                                              |
| Uygun değil - DAP veya GDAP ayarlanmadı    | İş ortağının kiracıyla ayarlanmış temsilci (DAP) veya ayrıntılı temsilci (GDAP) yönetici ayrıcalıkları olmalıdır. |
| Uygun değil - Gerekli lisans eksik | Kiracı gerekli lisansa sahip değil.                                                               |
| Uygun değil - Kullanıcı sayısı aşıldı         | Kiracının izin verilenden daha fazla kullanıcısı var.                                                                     |
| Uygun değil - Coğrafi denetim başarısız oldu            | İş ortağı ve müşteri aynı coğrafi konumda bulunmalıdır.                                       |

Bir kiracıyı devre dışı bırakdıktan sonra, devre dışı bırakma işlemi tamamlanana kadar kiracı üzerinde işlem yapamazsınız. Devre dışı bırakmanın tamamlanması 48 saat kadar sürebilir. Bir kiracıyı yeniden etkinleştirmeye karar verirseniz verilerin yeniden görüntülenmesi 48 saat kadar sürebilir.

## <a name="tenant-tags"></a>Kiracı etiketleri

Kiracılarınızı düzenlemeye ve mevcut görünümleri kolayca filtrelemeye yardımcı olmak için, kiracılarınıza etiketler oluşturabilir ve atayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft 365 Lighthouse'da kiracı listenizi yönetme](m365-lighthouse-manage-tenant-list.md).

> [!NOTE]
> Tüm kiracılarda en fazla 30 etiket oluşturabilirsiniz.

## <a name="tenant-details-page"></a>Kiracı ayrıntıları sayfası

Ayrıntılı kiracı bilgilerini görüntülemek için kiracı listesinden bir kiracı seçin. Kiracı ayrıntıları sayfası kişi bilgilerini ve dağıtım planı durumunu içerir.

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-details-page.png" alt-text="Kiracı ayrıntıları sayfasının ekran görüntüsü.":::

### <a name="overview-tab"></a>Genel Bakış sekmesi

Genel Bakış sekmesinde kiracıya genel bakış, kişi bilgileri ve Microsoft 365 hizmet kullanımını görüntüleyebilirsiniz.

#### <a name="tenant-overview-section"></a>Kiracıya genel bakış bölümü

Kiracıya genel bakış bölümü, Microsoft 365 hesabından kiracı hakkında bilgi sağlar.<br><br>

| Kiracı bilgileri    | Açıklama|
|-----------------------|------------------|
| Genel Müdürlük    | Kiracının bulunduğu yer.|
| Sanayi    |Kuruluşun sektörü.|
| Web sitesi    |Kuruluşun web sitesi. Veri sağlanmazsa bu alanı düzenleyebilirsiniz.|
| Müşteri etki alanı    |Kuruluşun etki alanı.|
| Toplam kullanıcı sayısı    |Kiracıda atanan kullanıcı sayısı. Bu kiracının Kullanıcılar sayfasını açmak için bu numarayı seçebilirsiniz.|
| Toplam cihaz sayısı|Kiracıya kaydedilen cihaz sayısı. Bu kiracının Cihazlar sayfasını açmak için bu numarayı seçebilirsiniz.|

#### <a name="contacts-section"></a>Kişiler bölümü

Kişiler bölümü, yönettiğiniz kiracıların içindeki önemli kişiler için aşağıdakiler gibi bilgiler sağlar:

- Name
- Başlık
- Phone
- E-posta
- Notlar

**Notlar** sütunu kiracıya ilişkin katılım tercihleri, konum, saat dilimi ve kuruluştaki rolüyle ilgili ayrıntılar gibi bilgileri gösterir.

Ayrıntıları düzenlemek, not eklemek veya var olan bir kişiyi silmek için listeden kişi adını seçin. **Kişiyi düzenle** bölmesinde, kişiyi düzenleyin veya silin. Başka bir kişi eklemek için **+Kişi ekle'yi** seçin.

#### <a name="microsoft-365-services-usage-section"></a>Microsoft 365 hizmetleri kullanımı bölümü

Lighthouse, bir kiracıdaki kaç kullanıcının lisanslı olduğu ve her hizmeti etkin bir şekilde kullandığı dahil olmak üzere Microsoft 365 hizmet kullanımıyla ilgili içgörüler sağlar. **Etkin kullanıcılar & cihazlar** sütunu, son 28 gün içinde hizmette en az bir kez oturum açmış olan kullanıcı veya cihaz sayısını gösterir. **Etkinlikte değişiklik** sütunu, geçen aydan bu yana etkin kullanıcılar ve cihazlardaki değişikliği gösterir.

**Microsoft 365 hizmetleri kullanımı** bölümünde iki alt bölüm bulunur:

- **Microsoft 365 Lighthouse etkin hizmetler:** Lighthouse portalında yönetilebilen hizmetler.
- **Ek Microsoft 365 hizmetleri:** Microsoft 365 paketine dahil edilen ancak şu anda Microsoft 365 Lighthouse portalında yönetilebilen hizmetler.

### <a name="deployment-plan-tab"></a>Dağıtım Planı sekmesi

Dağıtım Planları sekmesi, kiracının dağıtım planında durum sağlar. Listedeki dağıtım adımları, kiracıya uygulanan temeli temel alır. Dağıtım adımı ayrıntılarını görmek için listeden bir dağıtım adımı seçin.

Dağıtım Planı sekmesi aşağıdaki seçenekleri de içerir:

- **Ihracat:** Dağıtım adımı verilerini Excel virgülle ayrılmış değerler (.csv) dosyasına aktarmak için seçin.
- **Yenileme:** En güncel dağıtım adımı verilerini almak için öğesini seçin.
- **Arama:** Listede belirli bir dağıtım adımını hızla bulmak için anahtar sözcükler girin.

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md) (makale)\
[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)\
[kiracı listenizi Microsoft 365 Lighthouse 'de yönetme](m365-lighthouse-manage-tenant-list.md) (makale)\
[Standart kiracı yapılandırmalarını dağıtmak için Microsoft 365 Lighthouse temellerini kullanmaya genel bakış](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (makale)\
[Microsoft 365 Lighthouse temellerini dağıtma](m365-lighthouse-deploy-baselines.md) (makale)
