---
title: Uç Nokta için Microsoft Defender'da SIEM aracı tümleştirme sorunlarını giderme
description: Uç Nokta için Microsoft Defender ile SIEM araçlarını kullanırken ortaya çıkabilecek sorunları giderin.
keywords: sorun giderme, siem, istemci gizli anahtarı, gizli dizi
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
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: 879f6e2f5572e5cbbbe61a542f294d97e6844ab5
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585432"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>SIEM aracı tümleştirme sorunlarını giderin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

SIEM araçlarınızda algılamaları çekerken karşılaşılan sorunları gidermeniz gerekebilir.

Bu sayfada karşılaşabileceğiniz sorunları gidermek için ayrıntılı adımlar sağlanır.

## <a name="learn-how-to-get-a-new-client-secret"></a>Yeni bir gizli dizi almayı öğrenin

İstemci gizli dizinizin süresi dolarsa veya SIEM araç uygulamasını etkinleştirirken sağlanan kopyayı yanlış yerleştirdiyseniz, yeni bir gizli dizi almanız gerekir.

1. [Azure yönetim portalında](https://portal.azure.com) oturum açın.

2. **Azure Active Directory**’yi seçin.

3. Kiracınızı seçin.

4. **Uygulama kayıtları'a** tıklayın. Ardından uygulamalar listesinde uygulamayı seçin.

5. **Sertifikalar & Gizli Diziler** bölümünü seçin, Yeni İstemci Gizli Anahtarı'na tıklayın, ardından bir açıklama sağlayın ve geçerlilik süresini belirtin.

6. **Kaydet**'e tıklayın. Anahtar değeri görüntülenir.

7. Değeri kopyalayın ve güvenli bir yere kaydedin.

## <a name="error-when-getting-a-refresh-access-token"></a>Yenileme erişim belirteci alırken hata oluştu

Tehdit bilgileri API'sini veya SIEM araçlarını kullanırken yenileme belirteci almaya çalışırken hatayla karşılaşırsanız Azure Active Directory'de ilgili uygulama için yanıt URL'si eklemeniz gerekir.

1. [Azure yönetim portalında](https://ms.portal.azure.com) oturum açın.

2. **Azure Active Directory**’yi seçin.

3. Kiracınızı seçin.

4. **Uygulama Kayıtları'ne** tıklayın. Ardından uygulamalar listesinde uygulamayı seçin.

5. Aşağıdaki URL'yi ekleyin:
   - Avrupa Birliği için: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Birleşik Krallık için: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Birleşik Devletler için: `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.

6. **Kaydet**'e tıklayın.

## <a name="error-while-enabling-the-siem-connector-application"></a>SIEM bağlayıcı uygulaması etkinleştirilirken hata oluştu

SIEM bağlayıcı uygulamasını etkinleştirmeye çalışırken bir hatayla karşılaşırsanız tarayıcınızın açılır pencere engelleyici ayarlarını denetleyin. Özelliği etkinleştirdiğinizde yeni pencerenin açılmasını engelliyor olabilir.

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)

## <a name="related-topics"></a>İlgili konular

- [SIEM araçlarınıza çekme algılamaları](configure-siem.md)

