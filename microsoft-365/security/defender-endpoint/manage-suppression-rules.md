---
title: Uç Nokta için Microsoft Defender engelleme kurallarını yönetme
description: Gizleme kurallarını kullanarak uyarıların portalda görünmesini engellemeniz gerekebilir. Uç Nokta için Microsoft Defender'de gizleme kurallarınızı yönetmeyi öğrenin.
keywords: gizlemeyi yönetme, kurallar, kural adı, kapsam, eylem, uyarılar, açma, kapatma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 89c7be7c5fcdad33932e9e537d3c05b35656fc44
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67700212"
---
# <a name="manage-suppression-rules"></a>Yinelenen uyarıları engelleme kurallarını yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Uyarıların portalda görünmesini engellemeniz gereken senaryolar olabilir. Kuruluşunuzdaki bilinen araçlar veya işlemler gibi zararsız olduğu bilinen belirli uyarılar için gizleme kuralları oluşturabilirsiniz. Uyarıları gizleme hakkında daha fazla bilgi için bkz [. Uyarıları gizleme](manage-alerts.md).

Tüm gizleme kurallarının listesini görüntüleyebilir ve bunları tek bir yerde yönetebilirsiniz. Uyarı engelleme kuralını da açabilir veya kapatabilirsiniz.


1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Kuralları** \> **Uyarı gizleme'yi** seçin. Kuruluşunuzdaki kullanıcıların oluşturduğu gizleme kurallarının listesi görüntülenir.

2. Kural adının yanındaki onay kutusuna tıklayarak bir kural seçin.

3. **Kuralı aç**, **Kuralı düzenle** veya **Kuralı sil'e** tıklayın. Bir kuralda değişiklik yaparken, bu uyarıların yeni ölçütlerle eşleşip eşleşmediğine bakılmaksızın, zaten gizlediği uyarıları yayınlamayı seçebilirsiniz. 


## <a name="view-details-of-a-suppression-rule"></a>Gizleme kuralının ayrıntılarını görüntüleme

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Kuralları** \> **Uyarı gizleme'yi** seçin. Kuruluşunuzdaki kullanıcıların oluşturduğu gizleme kurallarının listesi görüntülenir.

2. Kural adına tıklayın. Kuralın ayrıntıları görüntülenir. Durum, kapsam, eylem, eşleşen uyarı sayısı, oluşturan ve kuralın oluşturulduğu tarih gibi kural ayrıntılarını görürsünüz. İlişkili uyarıları ve kural koşullarını da görüntüleyebilirsiniz.

## <a name="related-topics"></a>İlgili konular

- [Uyarıları yönetin](manage-alerts.md)
