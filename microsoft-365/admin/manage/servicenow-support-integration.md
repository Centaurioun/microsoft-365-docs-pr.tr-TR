---
title: ServiceNow Sanal Aracısı için Microsoft 365 destek tümleştirmesini etkinleştirme
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
description: Microsoft 365 destek tümleştirme ekibine geri bildirim sağlamak ve test etmek için destek tümleştirmesi deneysel özelliğini yapılandırın.
ms.openlocfilehash: 48a49b1e4a19039c40db278adf398f9a0ccd3831
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68172961"
---
# <a name="enable-microsoft-365-support-integration-for-servicenow-virtual-agent"></a>ServiceNow Sanal Aracısı için Microsoft 365 destek tümleştirmesini etkinleştirme

> [!IMPORTANT]
> ServiceNow Sanal Aracısı için destek tümleştirmesi, kullanıcıların Microsoft 365 destek tümleştirme ekibine geri bildirim sağlamalarını ve test etmelerini sağlayan deneysel bir özelliktir.

Microsoft 365 destek tümleştirme uygulamasını ServiceNow Sanal Aracısı ile çalışacak şekilde yapılandırdığınızda, **önerilen çözümlere** iki farklı kullanıcı deneyimi aracılığıyla erişebilirsiniz:

- **Hızlı İçgörüler** Olaylar sayfasında görünene benzer şekilde, ServiceNow Sanal Aracısı girilen metne göre **Önerilen makaleler** ve **Önerilen çözümler** görüntüler.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-1.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-1.png" alt-text="Hızlı İçgörüler.":::

- **Dallanma Deneyimi** Dallanma, kullanıcılara girilen metne göre yanıt döndüren bir sorun giderme akışında yol göstermek için arama ve yardımcı özelliğiyle tümleştirilir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-2.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-2.png" alt-text="Dallanma Deneyimi.":::

## <a name="before-you-begin"></a>Başlamadan önce

- ServiceNow'da Sanal Aracı'yı etkinleştirin. Ayrıntılar için bkz. [Sanal Aracıyı Etkinleştirme](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/activate-virtual-agent.html).

- ServiceNow Store'dan Microsoft 365 destek tümleştirme uygulamasının kurulumunu indirin ve tamamlayın.

- Microsoft 365'in en düşük sürümü tümleştirme desteği: v1.0.10.

- ServiceNow'un en düşük sürümü: Quebec.

- Rol gerekli: Yönetici.

## <a name="configure-microsoft-365-support-integration-to-work-with-servicenow-virtual-agent"></a>ServiceNow Sanal Aracısı ile çalışmak için Microsoft 365 destek tümleştirmesini yapılandırma

- Geri dönüş konunuz olarak Microsoft 365 Desteği'ne ayarlayın. Ayrıntılar için bkz. [Sanal Temsilci sohbet deneyimini yapılandırma](https://docs.servicenow.com/bundle/quebec-now-intelligence/page/administer/virtual-agent/task/configure-default-chat-experience.html).

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-support-integration-3.png" lightbox="../../media/ServiceNow-guide/servicenow-support-integration-3.png" alt-text="Varsayılan sohbet deneyimi geri dönüş konusunu ayarlayın.":::