---
title: Linux'ta Uç Nokta için Microsoft Defender güncelleştirmelerini dağıtma
ms.reviewer: ''
description: Kurumsal ortamlarda Linux'ta Uç Nokta için Microsoft Defender güncelleştirmelerinin nasıl dağıtılacağı açıklanır.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, güncelleştirmeler, dağıtma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 9987c5b6921d39bc5f3c0550388bddbfc5c91a92
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521671"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender güncelleştirmelerini dağıtma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft, performansı, güvenliği geliştirmek ve yeni özellikler sunmak için düzenli olarak yazılım güncelleştirmeleri yayımlar.

> [!WARNING]
> Linux'ta Uç Nokta için Defender'ın her sürümünün bir sona erme tarihi vardır ve bundan sonra cihazınızı korumaya devam etmeyecektir. Ürünü bu tarihten önce güncelleştirmeniz gerekir. Son kullanma tarihini denetlemek için aşağıdaki komutu çalıştırın:
> ```bash
> mdatp health --field product_expiration
> ```


Genel olarak kullanılabilen Uç Nokta için Microsoft Defender özellikleri, dağıtım için kullanılan güncelleştirme kanalı (Beta (Insider), Önizleme (Dış), Geçerli (Üretim)) ne olursa olsun eşdeğerdir.


Linux'ta Uç Nokta için Defender'ı el ile güncelleştirmek için aşağıdaki komutlardan birini yürütebilirsiniz:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL ve varyantlar (CentOS ve Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES ve çeşitlemeler

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu ve Debian sistemleri

```bash
sudo apt-get install --only-upgrade mdatp
```

> [!IMPORTANT]
> Uç Nokta için Microsoft Defender ve Bulut için Defender'ı tümleştirdiğinizde, mdatp aracısı güncelleştirmeleri varsayılan olarak otomatik olarak alır.
