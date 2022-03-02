---
title: Cihazları kaldır
description: Cihazları Microsoft Yönetilen Masaüstü yönetiminden kaldırma
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c4be03b7ba86449a875e268adbbdfbf1d4625aab
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2022
ms.locfileid: "63010088"
---
# <a name="remove-devices"></a>Cihazları kaldır

Yönetim portalını kullanarak cihazları Microsoft Yönetilen Masaüstü yönetiminden kaldırabilirsiniz. Bu eylem kalıcıdır, ancak kayıt adımlarını takiperek bunları Microsoft Yönetilen Masaüstü'ne [tekrar kaydettirebilirsiniz](../get-started/register-devices-self.md).

Bir cihazı kaldırsanız, aşağıdakilerin hepsi gerçekleşir:

- Cihazı AutoPilot'tan kaldıracağız.
- Cihazı tüm "Modern Çalışma Alanı" cihaz gruplarından kaldırıruz.
- Cihazı Yönetici portalında **Cihazlar** blade'dan kaldırmış oluruz.

Bir cihazı kaldırsanız da cihaz Azure Active Directory (Azure AD) ve diğer Microsoft Intune.
  
> [!CAUTION]
> Bir cihazla ilgili nesneleri Azure AD ve Microsoft Intune kaldırma kalıcıdır. Nesneleri kaldırırsanız, Intune ve Azure portallarından cihazları görüntü veya yönetesiniz. Cihazlar, kendi şirketinin şirket kaynaklarına erişe olmayacaktır. Cihazlar silindikten sonra oturum açmayı denerse, şirket verileri bu cihazlardan silinebilir.

**Cihazı kaldırmak için:**

1. Gezinti [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) gezinti bölmesinde **Cihazlar'ı** seçin.
2. Microsoft Yönetilen **Masaüstü bölümünde Cihazlar'ı** **seçin**.
3. **Microsoft Yönetilen Masaüstü Cihazları çalışma** alanında, silmek istediğiniz cihazları seçin.
4. Cihaz **eylemleri'ne** ve ardından **cihazları kaldırmak** için bir açılır pencere açan Cihazı Sil'e tıklayın.
5. Uçarak uçan cihazlarda, seçili cihazları gözden geçirin ve cihazları **kaldır'ı seçin**. Aynı anda Azure AD ve Intune nesnelerini de kaldırmak için onay kutusunu seçin. Cihaz kaldırma işleminin tamamlanması birkaç dakika sürebilir.

> [!NOTE]
> Kayıt durumu beklemede olan cihazları **kaldırabilirsiniz** .