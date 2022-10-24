---
title: Microsoft 365'i ServiceNow Sanal Aracısı ile tümleştirme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: Microsoft 365 destek tümleştirme ekibine geri bildirim sağlamak ve test etmek için destek tümleştirmesini yapılandırın.
ms.openlocfilehash: 858c90ac2ac101371f4b03017073ca2f4c331aee
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68685490"
---
# <a name="integrate-microsoft-365-with-servicenow-virtual-agent"></a>Microsoft 365'i ServiceNow Sanal Aracısı ile tümleştirme

Microsoft 365 destek tümleştirme uygulamasını ServiceNow Sanal Aracısı ile çalışacak şekilde yapılandırdığınızda, Microsoft 365 ürün ekipleri tarafından oluşturulan kendi kendine yardıma iki farklı kullanıcı deneyimi aracılığıyla erişebilirsiniz:

- Microsoft 365 adım adım çözümler ve adım adım kılavuz çözümleri.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Hızlı İçgörüler.":::
    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2b.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-2b.png" alt-text="Hızlı İçgörüler.":::

- Microsoft 365 bilgi bankası makalelerinin en iyi web arama sonuçları.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-1.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Bilgi bankası makalesi arama sonuçları.":::

## <a name="before-you-begin"></a>Başlamadan önce

- ServiceNow'da Sanal Aracı'yı etkinleştirin. Ayrıntılar için bkz. [Sanal Aracıyı Etkinleştirme](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/activate-virtual-agent.html).

- ServiceNow Store'dan Microsoft 365 destek tümleştirme uygulamasının kurulumunu yükleyin ve tamamlayın.

- ServiceNow'un en düşük sürümü: Roma.

- Rol gerekli: ServiceNow yöneticisi veya virtual_agent_admin.

## <a name="configure-microsoft-365-support-integration-to-work-with-servicenow-virtual-agent"></a>ServiceNow Sanal Aracısı ile çalışmak için Microsoft 365 destek tümleştirmesini yapılandırma

### <a name="standalone-fallback-topic"></a>Tek başına geri dönüş konusu

Geri dönüş konunuz olarak Microsoft 365 Desteği'ne ayarlayın. Ayrıntılar için bkz. [Sanal Temsilci sohbet deneyimini yapılandırma](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/configure-default-chat-experience.html).

:::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-3.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-3.png" alt-text="Varsayılan sohbet deneyimi geri dönüş konusunu ayarlayın.":::

### <a name="topic-blocks"></a>Konu blokları

Oluşturulmuş bir konunuz yoksa, yukarıda olduğu gibi tek başına geri dönüş konusunu kullanabilir veya [kendi sanal aracı konunuzu oluşturabilirsiniz](https://docs.servicenow.com/bundle/rome-now-intelligence/page/administer/virtual-agent/task/create-virtual-agent-topic.html).

Microsoft 365 Desteği konu bloğunu eklemek için şu adımları izleyin:

1. **Yardımcı Programlar'ın** altında **Konu Bloğu'na** tıklayın ve akışınıza ekleyin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-1.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-1.png" alt-text="Akışınıza bir konu bloğu ekleyin.":::

1. **Konu Bloğu Özellikleri'nin** altında **Microsoft 365 Destek Konusu Bloğu'nı** seçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-2.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-2.png" alt-text="Destek Konusu Bloğu özelliğini seçin.":::

1. Microsoft 365 Destek Konusu Bloğu, giriş metnine şu sırayla erişir:

    a. Giriş değişkenlerini denetler. Giriş değişkeni boş değilse, giriş değişkeninin sonuçlarını getirir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-3.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-3.png" alt-text="Giriş değişkeninin sonuçlarını getirir.":::

    b. Giriş değişkeni boşsa, sohbet penceresinde kullanıcı tarafından girilen metni denetler ve metin sonuçlarını getirir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-4.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-4.png" alt-text="Sohbet penceresine girilen metni denetler.":::

    c. Kullanıcı metin girmediyse, kullanıcıdan sonuçları getirmek için metin girmesini ister.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-5.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-5.png" alt-text="Sohbet penceresine girilen metni denetler.":::

1. Microsoft 365 Destek Konusu Bloğu, kullanıcının sonuçlar için geri bildirimi olan bir çıkış değişkeni sağlar.

    a. Çıkış değişkeni adı: m365_success b. Olası çıkış değişkeni değerleri: EVET/HAYIR

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-topic-block-6.png" lightbox="../../media/ServiceNow-guide/servicenow-topic-block-6.png" alt-text="Çıkış değişkeni adı ve değerleri.":::