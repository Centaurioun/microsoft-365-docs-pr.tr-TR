---
title: Kimlik için Microsoft Defender'de Dizin Hizmetleri hesabını yapılandırma
description: Microsoft 365 Defender'da Kimlik için Microsoft Defender Dizin Hizmetleri hesabını yapılandırmayı öğrenin
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: ea7195943dcfb24bd021930f4013263fc15e62cc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080469"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Microsoft 365 Defender'de Dizin Hizmetleri hesabını Kimlik için Microsoft Defender

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede[, Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) Dizin Hizmetleri hesabının nasıl yapılandırılır açıklanmaktadır[](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

## <a name="configure-directory-services-account"></a>Dizin Hizmetleri hesabını yapılandırma

[Algılayıcıyı](sensor-health.md#add-a-sensor) Active Directory etki alanlarınıza bağlamak için Dizin Hizmetleri hesaplarını yapılandırmanız gerekir.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ayarlar sayfasındaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::


1. **Dizin Hizmeti hesapları'nı** seçin. Hangi hesapların hangi etki alanlarıyla ilişkili olduğunu görürsünüz.

   :::image type="content" source="../../media/defender-identity/directory-service-accounts.png" alt-text="Dizin Hizmeti hesapları menü öğesi" lightbox="../../media/defender-identity/directory-service-accounts.png":::

1. Bir hesap seçerseniz, bu hesabın ayarlarını içeren bir bölme açılır.

   :::image type="content" source="../../media/defender-identity/account-settings.png" alt-text="Hesap ayarları sayfası" lightbox="../../media/defender-identity/account-settings.png":::

1. Yeni bir Dizin Hizmetleri hesabı eklemek için **Yeni hesap oluştur'u** seçin ve **Hesap adı**, **Etki Alanı** ve **Parola'yı** doldurun. Bunun bir **Grup tarafından yönetilen hizmet hesabı** (gMSA) olup olmadığını ve **Tek etiketli bir etki alanına** ait olup olmadığını da seçebilirsiniz.

   :::image type="content" source="../../media/defender-identity/new-directory-service-account.png" alt-text="Yeni hesap oluştur seçeneği" lightbox="../../media/defender-identity/new-directory-service-account.png":::

1. **Kaydet**'i seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [algılayıcının sistem durumunu ve ayarlarını Kimlik için Microsoft Defender](sensor-health.md)
