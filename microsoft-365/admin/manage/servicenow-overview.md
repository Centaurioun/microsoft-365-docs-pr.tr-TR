---
title: ServiceNow yapılandırmasına genel bakış ile Microsoft 365 desteği tümleştirmesi
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow için Kapsamlı Sertifikalı uygulama yükleme ve yapılandırma kılavuzu.
ms.openlocfilehash: 898b6a8f15d67fbf3530f6db269f47d5031f3676
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359241"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>ServiceNow yapılandırmasına genel bakış ile Microsoft 365 desteği tümleştirmesi

Aşağıdaki içerik, en az **1.0.7** sürümüne sahip Microsoft 365 destek tümleştirme uygulaması için geçerlidir.

**Microsoft 365 destek tümleştirmesi** , Microsoft 365 yardım, destek ve hizmet durumunu ServiceNow örneklerinizle tümleştirmenize olanak tanır. Microsoft tarafından bilinen ve bildirilen sorunları araştırabilir, olayları çözebilir, Microsoft tarafından önerilen çözümleri kullanarak görevleri tamamlayabilir ve gerekirse Microsoft'un insan destekli desteğine yükseltebilirsiniz.

ServiceNow mağazasından **Microsoft 365 destek tümleştirme** uygulaması için [ServiceNow Mağazası'na](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f) gidin.

## <a name="key-features"></a>Temel özellikler

ServiceNow örneğinizdeki Microsoft 365 destek tümleştirme uygulamasıyla elde ettiğiniz temel özellikler şunlardır:

- Hizmet Durumu Olayları: Kullanıcı etkisi, kapsam, geçerli durum ve bir sonraki beklenen güncelleştirme de dahil olmak üzere bilinen Microsoft hizmet durumu olayları hakkında bilgiler. Makine öğrenmesi kullanılarak ServiceNow olayları, kısa açıklama alanına göre Microsoft hizmet durumu olaylarıyla eşleştirilir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="Hizmet Durumu Olayları açıklama alanı.":::

- Önerilen çözümler: Makine öğrenmesi tarafından desteklenen Microsoft'tan kesin hedeflenmiş çözümler ve ilgili makaleler önermek için görev ve olayların açıklamaları kullanılır. Gerekirse diğer çözümleri bulmak için Arama'yı da kullanabilirsiniz.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="Önerilen çözümler açıklama alanı.":::

- Microsoft hizmet isteği: Sorunları Microsoft destek aracılarına iletin ve durumunuz için durum güncelleştirmelerini alın.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="Hizmet isteği formu.":::

## <a name="prerequisites"></a>Önkoşullar

### <a name="permissions-requirements"></a>İzin gereksinimleri

Bu kılavuza devam etmek için tüm işlem sırasında ortamlarınız için aşağıdaki izinlerin kullanılabilir ve yapılandırıldığından emin olun:

- Azure AD Uygulamaları oluşturabilen Azure Active Directory (AAD) yöneticisi

- ServiceNow yöneticisi

- Microsoft 365 kiracı yöneticisi

### <a name="configuration-highlights"></a>Yapılandırma vurguları

**Microsoft 365 destek tümleştirmesini** ayarlamak için:

- Hem giden hem de gelen API çağrılarının kimlik doğrulaması için uygulamaları Microsoft Azure Active Directory'ye (AAD) kaydedin.

- Hem giden hem de gelen veri akışı için Microsoft Azure AD Uygulaması ile ServiceNow varlıkları oluşturun.

- Microsoft 365 yönetim portalı aracılığıyla ServiceNow örneğini Microsoft desteğiyle tümleştirin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow tümleştirme diyagramı.":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow ortamlarınızdaki uygulama bağımlılıkları

Gerekli izinler:

- oauth\_varlığı

- oauth\_varlık\_profili

Microsoft 365 Destek Tümleştirme uygulaması yüklendikten sonra iki Uygulama Arası Kapsam erişimi oluşturulur. Bunlar başarıyla oluşturulmazsa el ile oluşturun.

## <a name="setup-the-integration"></a>Tümleştirmeyi ayarlama

Uygulamayı indirdikten sonra, kurulum işlemini tamamlamak için SNOW ortamınızdaki Microsoft 365 kurulum sihirbazına gidin.
:::image type="content" source="../../media/154124985-76e13e7d-b32e-4741-830b-bbb110d3ecbf.png" alt-text="Kar kurulum sihirbazı":::

Aşağıdaki sayfaları ziyaret ederek adımlar hakkında daha fazla bilgi edinebilirsiniz:
- ServiceNow ortamınız gelen web hizmeti çağrıları için Temel Kimlik Doğrulamasına (ServiceNow kullanıcı kimlik bilgileriyle erişim) izin veriyorsa, [ServiceNow Temel Kimlik Doğrulaması ile Microsoft 365 destek tümleştirmesini ayarlama](servicenow-basic-authentication.md) başlığı altında yer alan yönergeleri izleyin.
- ServiceNow ortamınız gelen web hizmeti çağrıları için Temel Kimlik Doğrulamasına (ServiceNow kullanıcı kimlik bilgileriyle erişim) izin vermiyorsa, [Azure AD Kimlik Doğrulama Belirteci ile Microsoft 365 destek tümleştirmesini ayarlama](servicenow-aad-oauth-token.md) başlığı altında yer alan yönergeleri izleyin.
  - Bu yapılandırma, AAD Kimlik Doğrulama Belirtecinin düzgün çalışması için bir SSO kiracısı gerektirir.

Her özelliği anlamak için bkz. [Microsoft 365 destek tümleştirmesi](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f).

> [!NOTE]
> Bu uygulama, düzenlenmiş veya kısıtlanmış ortamlarda desteklenmez.

> [!IMPORTANT]
> Microsoft 365 destek tümleştirme uygulaması bazen kullanıcılardan uygulama hakkında geri bildirim ister. Kullanıcılardan geri bildirim istenmesini istemiyorsanız uygulama ayarlarında bu işlevi kapatın. Microsoft geri bildirim ilkeleri hakkında daha fazla bilgi için bkz. [Kuruluşunuz için Microsoft geri bildirimi hakkında bilgi edinin](/microsoft-365/admin/misc/feedback-user-control). Geri bildirim ayarlarını değiştirmek için yükleme işlemindeki adımları izleyin.
