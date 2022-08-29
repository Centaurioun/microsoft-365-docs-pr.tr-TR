---
title: cihazları Uç Nokta için Microsoft Defender hizmetinden çıkarma
description: Uç Nokta için Microsoft Defender hizmetinden Windows cihazlarını, sunucularını, Windows dışı cihazları ekleme
keywords: çıkarma, Uç Nokta için Microsoft Defender çıkarma, çıkarma
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4cdd61ffaf91f6ddf88825f243abba38ffe78cd9
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67323671"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>cihazları Uç Nokta için Microsoft Defender hizmetinden çıkarma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platform**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Tercih ettiğiniz dağıtım yöntemine bağlı olarak ilgili yönergeleri izleyin.

> [!NOTE]
> Cihazın durumu, çıkarmadan 7 gün sonra [Etkin Değil](fix-unhealthy-sensors.md#inactive-devices) olarak değiştirilir.
>
> Eklenen cihazların verileri (Zaman Çizelgesi, Uyarılar, Güvenlik Açıkları vb.) yapılandırılmış [saklama süresi](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) dolana kadar portalda kalır.
>
> Cihazın profili (veri olmadan) 180 günden uzun süre [Cihazlar Listesi'nde](machines-view-overview.md) kalır.
>
> Ayrıca, son 30 gün içinde etkin olmayan cihazlar, kuruluşunuzun Defender Güvenlik Açığı Yönetimi [açığa çıkarma puanını](tvm-exposure-score.md) ve Cihazlar için Microsoft Güvenli Puanı'nı yansıtan verilere eklenmez.
>
> Yalnızca etkin cihazları görüntülemek için [algılayıcı sistem durumuna](machines-view-overview.md#use-filters-to-customize-the-device-inventory-views), [cihaz etiketlerine](machine-tags.md) veya [makine gruplarına](machine-groups.md) göre filtreleyebilirsiniz.

## <a name="offboard-windows-devices"></a>Windows cihazlarını çıkarma

- [Yerel betik kullanarak cihazları çıkarma](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [grup ilkesi kullanarak cihazları çıkarma](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Mobil Cihaz Yönetimi araçlarını kullanarak cihazları çıkarma](configure-endpoints-mdm.md#offboard-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Offboard Sunucuları

- [Sunucuları çıkarma](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Windows olmayan cihazları kullanıma açma

- [Windows olmayan cihazları kullanıma açma](configure-endpoints-non-windows.md#offboard-non-windows-devices)
