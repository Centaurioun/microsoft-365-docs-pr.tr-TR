---
title: Microsoft Defender Virüsten Koruma için tanımı kullanımdan kaldırmayı açma
description: Microsoft Defender Virüsten Koruma için tanımı kullanımdan kaldırmayı açın.
keywords: Microsoft Defender Virüsten Koruma, kötü amaçlı yazılımdan koruma, güvenlik, defender, tanımı kullanımdan kaldırma
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 0dbe84760518480883daecd1739eb4f12b5805cf
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577089"
---
# <a name="turn-on-definition-retirement"></a>Tanım kullanımdan kaldırılmasını aç

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

grup ilkesi kullanarak tanımın kullanımdan kaldırılmasını yapılandırabilirsiniz. Tanım kullanımdan kaldırma, bilgisayarın belirli bir güvenlik açığına karşı korumak için gerekli güvenlik güncelleştirmelerine sahip olup olmadığını denetler. Sistem bir tanım tarafından algılanan açıklara karşı savunmasız değilse, bu tanım "kullanımdan kaldırılmıştır". Belirli bir protokolün tüm güvenlik bilgileri kullanımdan kaldırılırsa bu protokol artık ayrıştırılır. Bu özelliğin etkinleştirilmesi performansı artırmaya yardımcı olur. En son güvenlik güncelleştirmelerinin tümünün güncel olduğu bir bilgisayarda ağ korumasının ağ performansı üzerinde hiçbir etkisi olmaz.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Tanımın kullanımdan kaldırılmasını yapılandırmak için grup ilkesi kullanma

1. grup ilkesi yönetim uç noktanızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın.

2. **Bilgisayar Yapılandırması** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **Ağ İnceleme Sistemi'ne** gidin.

3. **Tanımın kullanımdan kaldırılmasını aç'ı** seçin. Bu ilke varsayılan olarak etkindir. **Yapılandırılmadı** olarak ayarlanırsa, tanımın kullanımdan kaldırılması etkinleştirilir.

4. İlkeyi düzenlemek için **ilke ayarını düzenle** bağlantısını seçin.

5. **Etkin'i** ve ardından **Tamam'ı** seçin.

6. Güncelleştirilmiş grup ilkesi Nesnenizi dağıtın. Bkz. [yönetim konsolu grup ilkesi](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Şirket içinde grup ilkesi Nesneleri mi kullanıyorsunuz? Bulutta nasıl çeviri yaptıklarını görün. [Microsoft Endpoint Manager - Önizleme'de grup ilkesi analizini kullanarak şirket içi grup ilkesi nesnelerinizi analiz](/mem/intune/configuration/group-policy-analytics) edin.
