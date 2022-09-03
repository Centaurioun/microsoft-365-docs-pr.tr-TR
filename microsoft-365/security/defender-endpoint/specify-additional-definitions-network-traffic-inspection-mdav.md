---
title: Microsoft Defender Virüsten Koruma için ağ trafiği denetimi için ek tanım kümeleri belirtme
description: Microsoft Defender Virüsten Koruma için ağ trafiği denetimi için ek tanım kümeleri belirtin.
keywords: Microsoft Defender Virüsten Koruma, kötü amaçlı yazılımdan koruma, güvenlik, defender, ağ trafiği denetimi
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: a679db9fc1ce416a4385caaa6bc21e8d34596838
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67578542"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Ağ trafiği denetimi için ek tanım kümeleri belirtin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

grup ilkesi kullanarak ağ trafiği denetimi için ek tanım kümeleri belirtebilirsiniz.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Ağ trafiği denetimi için ek tanım kümeleri belirtmek üzere grup ilkesi kullanma

1. grup ilkesi yönetim uç noktanızda [grup ilkesi Yönetim Konsolu'nu](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) açın.

2. **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **Ağ İnceleme Sistemi'ne** gidin.

3. **Ağ trafiği denetimi için ek tanım kümeleri belirtin'i** seçin. Varsayılan olarak, bu ilke **Yapılandırılmadı** olarak ayarlanır.

4. İlkeyi düzenlemek için **ilke ayarını düzenle** bağlantısını seçin.

5. **Etkin'i** seçin ve **seçenekler bölümünde** **Göster...** öğesini seçin.

6. Listeye girdiler ekleyin ve **ardından Tamam'ı** seçin.

   Her girdi bir ad-değer çifti olarak listelenmelidir; burada ad, bir tanım kümesi GUID'sinin dize gösterimidir. Örnek olarak, test güvenlik zekasını etkinleştirmek için tanım kümesi GUID'i şöyle tanımlanır: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`. Değer kullanılmaz, bu nedenle değerini olarak `0`ayarlamanızı öneririz.

7. **Tamam'ı** seçin ve güncelleştirilmiş grup ilkesi Nesnenizi dağıtın. Bkz. [yönetim konsolu grup ilkesi](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Şirket içinde grup ilkesi Nesneleri mi kullanıyorsunuz? Bulutta nasıl çeviri yaptıklarını görün. [Microsoft Endpoint Manager - Önizleme'de grup ilkesi analizini kullanarak şirket içi grup ilkesi nesnelerinizi analiz](/mem/intune/configuration/group-policy-analytics) edin.

## <a name="related-articles"></a>İlgili makaleler

- [Windows 10'da Microsoft Defender Virüsten Koruma](microsoft-defender-antivirus-in-windows-10.md)
- [Bulut tabanlı korumayı etkinleştirme](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Kötü amaçlı yazılımdan koruma ilkeleri oluşturma ve dağıtma: Bulut koruma hizmeti](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)