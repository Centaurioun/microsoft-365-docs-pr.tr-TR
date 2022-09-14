---
title: Uç Nokta için Microsoft Defender'de bağlı uygulamalar
ms.reviewer: ''
description: Kimlik doğrulaması yapmak ve Uç Nokta için Microsoft Defender API'lerle kullanılmak üzere belirteçler sağlamak için standart OAuth 2.0 protokollerini kullanan bağlı iş ortağı uygulamalarını görüntüleyin.
keywords: partners, applications, third-party, connections, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: adf538a26b6d5514a740c696e524567ec55832f3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67680317"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de bağlı uygulamalar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Bağlı uygulamalar, API'leri kullanarak Uç Nokta için Defender platformuyla tümleştirilir.

Uygulamalar, kimlik doğrulaması yapmak ve Uç Nokta için Microsoft Defender API'lerle kullanılmak üzere belirteçler sağlamak için standart OAuth 2.0 protokollerini kullanır. Ayrıca, Azure Active Directory (Azure AD) uygulamaları kiracı yöneticilerinin ilgili uygulama kullanılarak erişilebilen API'ler üzerinde açık denetim ayarlamasına olanak tanır.

API'leri bağlı uygulamayla kullanmak için [bu adımları](/microsoft-365/security/defender-endpoint/apis-intro) izlemeniz gerekir.

Sol gezinti menüsünden **İş Ortakları & API'leri** ( **Uç Noktalar'ın** altında) > **Bağlı uygulamalar'ı** seçin.

## <a name="view-connected-application-details"></a>Bağlı uygulama ayrıntılarını görüntüleme

Bağlı uygulamalar sayfası, kuruluşunuzdaki Uç Nokta için Microsoft Defender bağlı Azure AD uygulamaları hakkında bilgi sağlar. Bağlı uygulamaların kullanımını gözden geçirebilirsiniz: son görülen, son 24 saat içindeki istek sayısı ve son 30 gün içindeki istek eğilimleri.

:::image type="content" source="images/connected-apps.png" alt-text="Bağlı uygulamalar" lightbox="images/connected-apps.png":::
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Bağlı bir uygulamayı düzenleme, yeniden yapılandırma veya silme

**Uygulama ayarlarını aç** bağlantısı, Azure portal ilgili Azure AD uygulama yönetimi sayfasını açar. Azure portal izinleri yönetebilir, yeniden yapılandırabilir veya bağlı uygulamaları silebilirsiniz.
