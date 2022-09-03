---
title: Uç Nokta için Defender Windows Server'a ekleme
description: Windows Server'ı Uç Nokta için Microsoft Defender'a ekleme.
keywords: ekleme, Uç Nokta için Microsoft Defender ekleme, sccm, grup ilkesi, mdm, yerel betik, algılama testi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 6bc6bfa6848d613b23fab0bf00d137d3c62b80e3
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585630"
---
# <a name="defender-for-endpoint-onboarding-windows-server"></a>Uç Nokta için Defender Windows Server'a ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server Semi-Annual Enterprise Channel
- Windows Server 2019 ve üzeri
- Windows Server 2019 core edition
- Windows Server 2022
- [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https:%2F%2Faka.ms%2FMDEp2OpenTrial)

Desteklenen cihazlardan herhangi birini eklemek için Uç Nokta için Defender portalının ekleme bölümünden geçmeniz gerekir. Cihaza bağlı olarak, uygun adımlarla yönlendirilirsiniz ve cihaza uygun yönetim ve dağıtım aracı seçenekleri sağlanır.

Uç Nokta için Defender, Windows Server işletim sistemini de içerecek şekilde desteği genişletir. Bu destek, Microsoft 365 Defender konsolu aracılığıyla sorunsuz bir şekilde gelişmiş saldırı algılama ve araştırma özellikleri sağlar. Windows Server desteği sunucu etkinlikleri, çekirdek ve bellek saldırısı algılama kapsamı hakkında daha ayrıntılı içgörüler sağlar ve yanıt eylemlerini etkinleştirir.

Bu konu başlığında, belirli Windows sunucularının Uç Nokta için Microsoft Defender ekleme işlemi açıklanmaktadır.

Windows sunucuları için Windows Güvenliği Taban Çizgilerini indirme ve kullanma hakkında yönergeler için bkz[. Windows Güvenliği Temeller.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-baselines)

## <a name="license-requirement"></a>Lisans gereksinimi

Uç Nokta için Microsoft Defender Server SKU'su satın almaya uygun olmak için, aşağıdakilerden en az birini zaten satın almış olmanız gerekir: Windows E5/A5, Microsoft 365 E5/A5 veya Microsoft 365 E5 Güvenlik abonelik lisansları. Lisanslama hakkında daha fazla bilgi için bkz. [Ürün Koşulları](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all).

## <a name="windows-server-onboarding-overview"></a>Windows Server eklemeye genel bakış

Sunucuları başarıyla eklemek için aşağıdaki genel adımları tamamlamanız gerekir: 2008 R2, 2012 R2, 2016, 2019, 2022.

:::image type="content" source="images/server-onboarding.png" alt-text="Sunucu Ekleme" lightbox="images/server-onboarding.png":::

### <a name="windows-server-2012-r2-and-windows-server-2016"></a>R2 ve Windows Server 2016 Windows Server 2012
- Yükleme ve ekleme paketlerini indirin.
- Yükleme paketini uygulayın.
- İlgili araç için ekleme adımlarını izleyin.

### <a name="windows-server-semi-annual-enterprise-channel-and-windows-server-2019"></a>Windows Server Semi-Annual Enterprise Channel ve Windows Server 2019
- Ekleme paketini indirin.
- İlgili araç için ekleme adımlarını izleyin.

## <a name="offboard-windows-servers"></a>Windows sunucularını çıkarma

Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC), Windows Server 2019 ve Windows Server 2019 Core sürümünü Windows 10 istemci cihazları için kullanılabilen yöntemle çıkarabilirsiniz.

- [Configuration Manager kullanarak cihazları çıkarma](/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#offboard-devices-using-configuration-manager)
- [Mobil Cihaz Yönetimi araçlarını kullanarak cihazları çıkarma ve izleme](/microsoft-365/security/defender-endpoint/configure-endpoints-mdm#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [grup ilkesi kullanarak cihazları çıkarma](/microsoft-365/security/defender-endpoint/configure-endpoints-gp#offboard-devices-using-group-policy)
- [Yerel betik kullanarak cihazları çıkarma](/microsoft-365/security/defender-endpoint/configure-endpoints-script#offboard-devices-using-a-local-script)

Çıkarma sonrasında, Windows Server 2012 R2 ve Windows Server 2016'da birleşik çözüm paketini kaldırmaya devam edebilirsiniz.

Diğer Windows sunucu sürümleri için, Hizmetten Windows sunucularını çıkarmak için iki seçeneğiniz vardır:
- MMA aracısını kaldırma
- Uç Nokta için Defender çalışma alanı yapılandırmasını kaldırma

> [!NOTE]
> Diğer Windows server sürümleri için bu çıkarma yönergeleri, MMA gerektiren Windows Server 2016 ve Windows Server 2012 R2 için önceki Uç Nokta için Microsoft Defender çalıştırıyorsanız da geçerlidir. Yeni birleştirilmiş çözüme geçiş yönergeleri[, Uç Nokta için Microsoft Defender'daki Sunucu geçiş senaryolarında yer alır](/microsoft-365/security/defender-endpoint/server-migration).

## <a name="related-topics"></a>İlgili konular

- [Microsoft Endpoint Configuration Manager kullanarak Windows cihazlarını ekleyin](configure-endpoints-sccm.md)
- [Windows araçlarını Grup İlkesi kullanarak ekleyin](configure-endpoints-gp.md)
- [Kalıcı olmayan sanal masaüstü altyapısı (VDI) cihazlarının katılımı](configure-endpoints-vdi.md)
