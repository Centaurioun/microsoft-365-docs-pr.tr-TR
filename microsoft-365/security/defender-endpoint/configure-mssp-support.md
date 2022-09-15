---
title: Yönetilen güvenlik hizmeti sağlayıcısı desteğini yapılandırma
description: MSSP tümleştirmesini Uç Nokta için Microsoft Defender yapılandırmak için gerekli adımları uygulayın
keywords: yönetilen güvenlik hizmeti sağlayıcısı, mssp, yapılandırma, tümleştirme
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
ms.openlocfilehash: 0127dc1c2c3a16c21694fd693389a203458ae734
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705150"
---
# <a name="configure-managed-security-service-provider-integration"></a>Güvenlik hizmeti sağlayıcısı tümleştirmesini yapılandırın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Yönetilen güvenlik hizmeti sağlayıcısı (MSSP) tümleştirmesini etkinleştirmek için aşağıdaki yapılandırma adımlarını uygulamanız gerekir.

> [!NOTE]
> Hizmet sağlayıcısı ile hizmet tüketicisi arasında ayrım yapmak için bu makalede aşağıdaki terimler kullanılır:
>
> - MSSP'ler: Bir kuruluşun güvenlik cihazlarını izlemeyi ve yönetmeyi teklif eden güvenlik kuruluşları.
> - MSSP müşterileri: MSSP hizmetlerini devreye alan kuruluşlar.

Tümleştirme, MSSP'lerin aşağıdaki eylemleri gerçekleştirmesine olanak sağlar:

- MSSP müşteri Microsoft 365 Defender portalına erişme
- E-posta bildirimlerini alma ve
- Güvenlik bilgileri ve olay yönetimi (SIEM) araçları aracılığıyla uyarıları getirme

MSSP'lerin bu eylemleri gerçekleştirebilmesi için ÖNCE MSSP müşterisinin Uç Nokta için Defender kiracısına erişim vermesi gerekir, böylece MSSP portala erişebilir.

MSSP müşterileri genellikle Windows Defender Security Central kiracılarına MSSP erişimi vermek için ilk yapılandırma adımlarını uygular. Erişim verildikten sonra, diğer yapılandırma adımları MSSP müşterisi veya MSSP tarafından yapılabilir.

Genel olarak, aşağıdaki yapılandırma adımlarının izlenmesi gerekir:

- **MSSP'ye Microsoft 365 Defender erişimi verme**

  Bu eylemin MSSP müşterisi tarafından yapılması gerekir. MSSP müşterisinin Uç Nokta için Defender kiracısına MSSP erişimi verir.

- **MSSP'lere gönderilen uyarı bildirimlerini yapılandırma**

  Bu eylem, MSSP müşterisi veya MSSP tarafından yapılabilir. Bu, MSSP'lerin MSSP müşterisi için hangi uyarıları ele almak zorunda olduklarını bilmesini sağlar.

- **MSSP müşteri kiracısından SIEM sistemine uyarı getirme**

  Bu eylem MSSP tarafından gerçekleştirilen. MSSP'lerin SIEM araçlarında uyarıları getirmesine olanak tanır.

- **API'leri kullanarak MSSP müşteri kiracısından uyarıları getirme**

  Bu eylem MSSP tarafından gerçekleştirilen. MSSP'lerin API'leri kullanarak uyarıları getirmesine olanak tanır.

## <a name="multi-tenant-access-for-mssps"></a>MSSP'ler için çok kiracılı erişim

Çok kiracılı temsilci erişimi uygulama hakkında bilgi için bkz. [Yönetilen Güvenlik Hizmeti Sağlayıcıları için çok kiracılı erişim](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).

## <a name="related-topics"></a>İlgili konular

- [Portala MSSP erişimi ver](grant-mssp-access.md)
- [MSSP müşteri portalına erişin](access-mssp-portal.md)
- [Uyarı bildirimlerini yapılandırın](configure-mssp-notifications.md)
- [Müşteri kiracı uyarılarını getir](fetch-alerts-mssp.md)
