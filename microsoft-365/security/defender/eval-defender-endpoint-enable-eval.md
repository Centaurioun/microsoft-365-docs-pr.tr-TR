---
title: Uç Nokta için Microsoft Defender değerlendirmesini etkinleştirme
description: Lisans durumunu denetleme ve uç noktaları ekleme dahil olmak üzere Microsoft 365 Defender deneme laboratuvarınızı veya pilot ortamınızı etkinleştirin
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 09/22/2022
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 2d4de8ce1507635187c140830e92fd50ad8ec3e6
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084825"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Uç Nokta için Microsoft Defender değerlendirme ortamını etkinleştirme


Bu makale, üretim cihazlarını kullanarak Uç Nokta için Microsoft Defender için değerlendirme ortamını ayarlama adımlarında size yol gösterir. 


> [!TIP]
> Uç Nokta için Microsoft Defender ayrıca önceden yapılandırılmış cihazlar ekleyebileceğiniz ve platformun özelliklerini değerlendirmek için simülasyonlar çalıştırabileceğiniz bir ürün içi değerlendirme laboratuvarıyla birlikte gelir. Laboratuvar, gelişmiş tehdit avcılığı ve tehdit analizi gibi birçok özellik için rehberlik de dahil olmak üzere Uç Nokta için Microsoft Defender değerini hızla göstermeye yardımcı olabilecek basitleştirilmiş bir kurulum deneyimiyle birlikte gelir. Daha fazla bilgi için bkz [. Özellikleri değerlendirme](../defender-endpoint/evaluation-lab.md). <br> Bu makalede sağlanan yönergelerle değerlendirme laboratuvarı arasındaki temel fark, değerlendirme ortamında üretim cihazlarının kullanıldığı, değerlendirme laboratuvarının ise üretim dışı cihazlar kullandığıdır. 

Uç Nokta için Microsoft Defender için değerlendirmeyi etkinleştirmek için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-endpoint-eval-enable-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Uç Nokta için Microsoft Defender etkinleştirme adımları" lightbox="../../media/defender/m365-defender-endpoint-eval-enable-steps.png":::

- [1. Adım. Lisans durumunu denetleme](#step-1-check-license-state)
- [2. Adım. Uç noktaları ekleme](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Adım 1. Lisans durumunu denetleme

Doğru şekilde sağlandığını doğrulamak için önce lisans durumunu denetlemeniz gerekir. Bunu yönetim merkezi veya **Microsoft Azure portal** aracılığıyla yapabilirsiniz.


1. Lisanslarınızı görüntülemek için **Microsoft Azure portal** ve [Microsoft Azure portal lisansı bölümüne](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products) gidin.

   :::image type="content" source="../../media/defender/atp-licensing-azure-portal.png" alt-text="Microsoft 365 Defender portalındaki Azure Lisanslama sayfası" lightbox="../../media/defender/atp-licensing-azure-portal.png":::

1. Alternatif olarak, yönetim merkezinde **Faturalama** > **Abonelikleri'ne** gidin.

    Ekranda sağlanan tüm lisansları ve geçerli **Durumlarını** görürsünüz.

    :::image type="content" source="../../media/defender/atp-billing-subscriptions.png" alt-text="Microsoft Azure portal Faturalama lisansları sayfası" lightbox="../../media/defender/atp-billing-subscriptions.png":::
    

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Adım 2. Desteklenen yönetim araçlarından herhangi birini kullanarak uç noktaları ekleme

Lisans durumunun düzgün sağlandığını doğruladıktan sonra, cihazları hizmete eklemeye başlayabilirsiniz. 

Uç Nokta için Microsoft Defender değerlendirme amacıyla değerlendirmeyi gerçekleştirmek üzere birkaç Windows cihazı seçmenizi öneririz.

Desteklenen yönetim araçlarından herhangi birini kullanmayı seçebilirsiniz, ancak Intune en iyi tümleştirmeyi sağlar. Daha fazla bilgi için bkz[. Microsoft Intune'da Uç Nokta için Microsoft Defender yapılandırma](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune).

[Plan dağıtımı](../defender-endpoint/deployment-strategy.md) konusunda, Uç Nokta için Defender'ı dağıtmak için uygulamanız gereken genel adımlar özetlenmiştir.  

Ekleme işlemine hızlı bir genel bakış için bu videoyu izleyin ve kullanılabilir araçlar ve yöntemler hakkında bilgi edinin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Ekleme aracı seçenekleri

Aşağıdaki tabloda, eklemeniz gereken uç noktayı temel alan kullanılabilir araçlar listelenir.

| Uç nokta | Araç seçenekleri |
|:---|:---|
| **Windows** |- [Yerel betik (en fazla 10 cihaz)](../defender-endpoint/configure-endpoints-script.md)<br/>- [grup ilkesi](../defender-endpoint/configure-endpoints-gp.md)<br/>- [Microsoft Endpoint Manager/ Mobile Aygıt Yöneticisi](../defender-endpoint/configure-endpoints-mdm.md)<br/>- [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md)<br/>- [VDI betikleri](../defender-endpoint/configure-endpoints-vdi.md) |
| **macOS** | - [Yerel betikler](../defender-endpoint/mac-install-manually.md)<br/>- [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md)<br/>- [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)<br/>- [Mobil Cihaz Yönetimi](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | - [Yerel betik](../defender-endpoint/linux-install-manually.md)<br/>- [Kukla](../defender-endpoint/linux-install-with-puppet.md)<br/>- [Ansible](../defender-endpoint/linux-install-with-ansible.md) |
| **iOS** | [Uygulama tabanlı](../defender-endpoint/ios-install.md) |
| **Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md) |



## <a name="next-step"></a>Sonraki adım
[pilotu Uç Nokta için Microsoft Defender için ayarlama](eval-defender-endpoint-pilot.md)
 
[Değerlendirme Uç Nokta için Microsoft Defender](eval-defender-endpoint-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
