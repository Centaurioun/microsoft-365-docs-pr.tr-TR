---
title: Bir öğenin ne zaman saklandığını veya silindiğini saptamak için akış çizelgesi
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365'teki bir öğenin birden çok bekletme ilkesine veya bekletme etiketine ve bekletme ilkesine sahip olduğu sonucu belirlemek için akış çizelgesi kullanma
ms.openlocfilehash: a864b11c355c8e9b1fc50aed262f771a6a580c12
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68129419"
---
# <a name="flowchart-to-determine-when-an-item-will-be-retained-or-permanently-deleted"></a>Bir öğenin ne zaman tutulacağını veya kalıcı olarak silineceğini saptamak için akış çizelgesi

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Bir öğeye [bekletme ilkelerini](retention.md#the-principles-of-retention-or-what-takes-precedence) uygulamak için aşağıdaki akış çizelgesini kullanarak sistemin saklama etiketinin veya bekletme ilkesinin bir sonucu olarak saklamayı mı yoksa kalıcı olarak mı sileceğini belirleyin.

Bu mantıksal akış, aşağıdaki koşullardan biri uygulandığında bir öğe için kullanılır:

- Birden fazla bekletme ilkesi uygulandı
- Bekletme etiketi ve bir veya daha fazla bekletme ilkesi vardır

Bir öğe bir eBulma ayrı tutmasına (veya Dava tutma veya In-Place tutma eski teknolojilerine) tabi olduğunda, saklama ilkeleri ve bekletme etiketi için karar akışlarından önce her zaman korunur.

Bu akış çizelgesinde kullanılan terimlerden herhangi biri size yabancıysa bkz. [Bekletme ilkeleri ve bekletme etiketleri hakkında bilgi edinin](retention.md).


   ![Bir öğenin ne zaman tutulacağını veya kalıcı olarak silineceğini belirlemek için akış çizelgesi.](../media/retention-flowchart.svg)

> [!NOTE]
> Öğe için en uzun saklama süresi ile bir bekletme ilkesi veya etiketinde belirtilen en uzun süre arasında ayrım yapmak önemlidir. Benzer şekilde, öğe için en kısa süre sonu tarihi ile bekletme ilkesinde belirtilen en kısa süre arasında.
> 
> Daha fazla bilgi için [bekletme ilkeleri](retention.md#the-principles-of-retention-or-what-takes-precedence) bölümündeki grafik sonrasındaki açıklamaya bakın.
