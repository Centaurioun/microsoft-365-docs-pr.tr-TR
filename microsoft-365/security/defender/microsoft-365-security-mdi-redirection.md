---
title: Hesapları Kimlik için Microsoft Defender'den Microsoft 365 Defender'a yeniden yönlendirme
description: Kimlik için Defender'dan Microsoft 365 Defender hesapları ve oturumları yeniden yönlendirme.
keywords: Microsoft 365 Defender, Microsoft 365 Defender kullanmaya başlama, güvenlik merkezi yeniden yönlendirmesi
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b5c122f01d37d066e0f20bf817ca45ad5c57480b
ms.sourcegitcommit: 5fe7f2954a89406245416fc1a218cf4bf19abb85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2022
ms.locfileid: "66861781"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-identity-to-microsoft-365-defender"></a>Hesapları Kimlik için Microsoft Defender'den Microsoft 365 Defender'a yeniden yönlendirme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu kılavuzda, eski Kimlik için Microsoft Defender portalından (portal.atp.azure.com) Microsoft 365 Defender otomatik yeniden yönlendirmeyi etkinleştirerek <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">hesapların Microsoft 365 Defender</a> nasıl yönlendirildiği açıklanır.

## <a name="what-to-expect"></a>Bekleyebileceğiniz şeyler

Otomatik yeniden yönlendirme etkinleştirildikten sonra, portal.atp.azure.com'da eski Kimlik için Microsoft Defender portalına erişen hesaplar otomatik olarak <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">security.microsoft.com</a> Microsoft 365 Defender portalına yönlendirilir.

## <a name="when-does-this-take-effect"></a>Bu ne zaman geçerli olur?

Etkinleştirildikten sonra, bu güncelleştirme bazı hesaplar için hemen geçerli olabilir. Ancak yeniden yönlendirmenin kuruluşunuzdaki her hesaba yayılması daha uzun sürebilir. Bu ayar uygulandığında etkin oturumlardaki hesaplar oturumlarından çıkarılamaz ve yalnızca geçerli oturumlarını bitirip yeniden oturum açtıktan sonra Microsoft 365 Defender yönlendirilir.  

### <a name="set-up-portal-redirection"></a>Portal yeniden yönlendirmesini ayarlama

Hesapları Microsoft 365 Defender yönlendirmeye başlamak için:

1. Azure Active Directory'de genel yönetici olduğunuzdan veya güvenlik yöneticisi izinlerine sahip olduğunuzdan emin olun.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> oturum açın.

1. **Ayarlar** > **Kimlikleri** > **Genel** > **Portal yeniden yönlendirmesine** gidin veya [buraya tıklayın](https://security.microsoft.com/preferences2/portal_redirection).

    :::image type="content" source="../../media/portal-redirection.png" alt-text="Portal yeniden yönlendirme."lightbox="../../media/portal-redirection.png":::

1. Otomatik yeniden yönlendirme ayarını **Açık** olarak değiştirin.

>[!IMPORTANT]
>Bu ayarın etkinleştirilmesi etkin kullanıcı oturumlarını sonlandırmaz. Bu ayar uygulandığı sırada etkin oturumda olan hesaplar yalnızca geçerli oturumlarını sonlandırıp yeniden oturum açtıktan sonra Microsoft 365 Defender yönlendirilir.

>[!NOTE]
>Bu ayarı etkinleştirmek veya devre dışı bırakmak için Azure Active Directory'de genel yönetici olmanız veya güvenlik yöneticisi izinlerine sahip olmanız gerekir.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Eski portalı kullanmaya geri dönebilir miyim?

Sizin için bir şey çalışmıyorsa veya Microsoft 365 Defender tamamlayamadığınız bir şey varsa, bunu duymak isteriz. Yeniden yönlendirmeyle ilgili herhangi bir sorunla karşılaştıysanız, Geri bildirim gönder formunu kullanarak bize bildirmenizi öneririz.

Eski Kimlik için Microsoft Defender portalına geri dönmek için:

1. Azure Active Directory'de genel yönetici olarak veya güvenlik yöneticisi izinleriyle ve hesabı kullanarak <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> oturum açın.

2. **Ayarlar** > **Kimlikleri** > **Genel** > **Portal yeniden yönlendirmesine** gidin veya [sayfayı burada açın](https://security.microsoft.com/preferences2/portal_redirection).  

3. Otomatik yeniden yönlendirme ayarını **Kapalı olarak değiştirin**.

Bu ayar istediğiniz zaman yeniden etkinleştirilebilir.

Devre dışı bırakıldıktan sonra hesaplar artık security.microsoft.com yönlendirilmeyecektir.

## <a name="related-information"></a>İlgili bilgiler

- [Microsoft 365 Defender genel bakış](microsoft-365-defender.md)
- [Microsoft 365 Defender hakkında](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender)
- [Microsoft güvenlik portalları ve yönetim merkezleri](portals.md)
