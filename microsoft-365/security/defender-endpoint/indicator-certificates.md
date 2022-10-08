---
title: Sertifikaları temel alan göstergeler oluşturma
ms.reviewer: ''
description: Varlıkların algılanmasını, önlenmesini ve dışlanmasını tanımlayan sertifikalara dayalı göstergeler oluşturun.
keywords: ioc, sertifika, sertifikalar, yönetme, izin verildi, engellendi, engelleme, temiz, kötü amaçlı, dosya karması, IP adresi, URL'ler, etki alanı
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
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ca15e36c0de968a2afddb14a5c8c74cffe969953
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232506"
---
# <a name="create-indicators-based-on-certificates"></a>Sertifikaları temel alan göstergeler oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Sertifikalar için göstergeler oluşturabilirsiniz. Bazı yaygın kullanım örnekleri şunlardır:

- [Saldırı yüzeyi azaltma kuralları](attack-surface-reduction.md) ve [denetimli klasör erişimi](controlled-folders.md) gibi engelleme teknolojilerini dağıtmanız gereken ancak sertifikayı izin listesine ekleyerek imzalı uygulamalardan gelen davranışlara izin vermeniz gereken senaryolar.
- Kuruluşunuz genelinde belirli bir imzalı uygulamanın kullanımını engelleme. Windows Defender AV, uygulamanın sertifikasını engellemek için bir gösterge oluşturarak dosya yürütmelerini engeller (engelleme ve düzeltme) ve Otomatik Araştırma ve Düzeltme aynı şekilde davranır.

## <a name="before-you-begin"></a>Başlamadan önce

Sertifikalar için göstergeler oluşturmadan önce aşağıdaki gereksinimleri anlamak önemlidir:

- Kuruluşunuz virüsten koruma Microsoft Defender kullanıyorsa ve Bulut tabanlı koruma etkinleştirildiğinde bu özellik kullanılabilir. Daha fazla bilgi için bkz. [Bulut tabanlı korumayı yönetme](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- Kötü amaçlı yazılımdan koruma istemcisi sürümü 4.18.1901.x veya üzeri olmalıdır.
- Windows 10, sürüm 1703 veya üzeri, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2 ve Windows Server 2022 üzerindeki makinelerde desteklenir.
    
    >[!NOTE]
    >Windows Server 2016 ve Windows Server 2012 R2'nin bu özelliğin çalışması için [Windows sunucularını ekleme](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) yönergeleri kullanılarak eklenmesi gerekir. 

- Virüs ve tehdit koruması tanımları güncel olmalıdır.
- Bu özellik şu anda girişini destekler. CER veya . PEM dosya uzantıları.

> [!IMPORTANT]
>
> - Geçerli yaprak sertifika, geçerli bir sertifika yoluna sahip olan ve Microsoft tarafından güvenilen Kök Sertifika Yetkilisi'ne (CA) zincirlenmiş bir imzalama sertifikasıdır. Alternatif olarak, istemci tarafından güvenilen özel (otomatik olarak imzalanan) bir sertifika kullanılabilir (Kök CA sertifikası Yerel Makine 'Güvenilen Kök Sertifika Yetkilileri' altına yüklenir).
> - İzin verilen/engelleyici sertifika GÇ'lerinin alt öğeleri veya üst öğesi IoC'ye izin ver/engelle işlevine dahil değildir, yalnızca yaprak sertifikalar desteklenir.
> - Microsoft imzalı sertifikalar engellenemez.

## <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Ayarlar sayfasından sertifikalar için bir gösterge oluşturun:

> [!IMPORTANT]
> Sertifika IoC'sini oluşturmak ve kaldırmak 3 saat kadar sürebilir.

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Göstergeleri'ni** seçin ( **Kurallar'ın** altında).

2. **Gösterge ekle'yi** seçin.

3. Aşağıdaki ayrıntıları belirtin:
   - Gösterge - Varlık ayrıntılarını belirtin ve göstergenin süre sonunu tanımlayın.
   - Eylem - Gerçekleştirilecek eylemi belirtin ve bir açıklama sağlayın.
   - Kapsam - Makine grubunun kapsamını tanımlayın.

4. Özet sekmesinde ayrıntıları gözden geçirin ve **Kaydet'e** tıklayın.

## <a name="related-topics"></a>İlgili konular

- [Göstergeleri oluşturun](manage-indicators.md)
- [Dosyalar için göstergeler oluşturun](indicator-file.md)
- [URL/etki alanı ve IP’ler için göstergeler oluşturun](indicator-ip-domain.md)
- [Göstergeleri yönetin](indicator-manage.md)
