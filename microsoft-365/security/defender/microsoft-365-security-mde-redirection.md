---
title: Hesapları Uç Nokta için Microsoft Defender'dan Microsoft 365 Defender'a yönlendirme
description: Uç Nokta için Defender'dan Microsoft 365 Defender hesapları ve oturumları yeniden yönlendirme.
keywords: Microsoft 365 Defender, Microsoft 365 Defender kullanmaya başlama, güvenlik merkezi yeniden yönlendirmesi
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: 3f7d7bab51a8dfb29b25701ccc87e49b437529ab
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072623"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Hesapları Uç Nokta için Microsoft Defender'dan Microsoft 365 Defender'a yönlendirme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Defender

Microsoft'un SIEM ve Genişletilmiş algılama ve yanıt (XDR) ile tehdit korumasına olan etki alanları arası yaklaşımına uygun olarak Gelişmiş Tehdit Koruması'Microsoft Defender Uç Nokta için Microsoft Defender olarak yeniden Uç Nokta için Microsoft Defender ve tek bir tümleşik portalda birleştirdik: Microsoft 365 Defender.

Bu kılavuzda, eski Uç Nokta için Microsoft Defender portalından (securitycenter.windows.com veya securitycenter.microsoft.com) Microsoft 365 Defender otomatik yeniden yönlendirmeyi etkinleştirerek <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">hesapların Microsoft 365 Defender</a> nasıl yönlendirildiği açıklanır.

> [!NOTE]
> Microsoft 365 Defender'daki Uç Nokta için Microsoft Defender, [yönetilen güvenlik hizmeti sağlayıcılarına (MSSP) Microsoft Defender Güvenlik Merkezi](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) erişim verildiği şekilde erişim [verilmesini](./mssp-access.md) destekler.

## <a name="what-to-expect"></a>Bekleyebileceğiniz şeyler

Otomatik yeniden yönlendirme etkinleştirildikten sonra, securitycenter.windows.com veya securitycenter.microsoft.com'da eski Uç Nokta için Microsoft Defender portalına erişen hesaplar otomatik olarak <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><security.microsoft.com></a>Microsoft 365 Defender portalına yönlendirilir.

Değişenler hakkında daha fazla bilgi edinin: [Microsoft 365 Defender'da Uç Nokta için Microsoft Defender](microsoft-365-security-center-mde.md).

Bu, e-posta bildirimlerindeki bağlantılar ve SIEM API çağrıları tarafından döndürülen bağlantılar gibi eski securitycenter.windows.com portalına yönlendiren bağlantılar da dahil olmak üzere tarayıcı aracılığıyla eski portala doğrudan erişim için yeniden yönlendirmeyi içerir.  

 E-posta bildirimlerinden veya SIEM API'lerinden dış bağlantılar şu anda her iki portalın bağlantılarını içerir. Yeniden yönlendirme etkinleştirildikten sonra, eski bağlantı sonunda kaldırılana kadar her iki bağlantı da Microsoft 365 Defender işaret eder. Microsoft 365 Defender işaret eden yeni bağlantıyı benimsemenizi öneririz.

Bağlantılar ve yönlendirme hakkında daha fazla bilgi için aşağıdaki tabloya bakın.
## <a name="siem-api-routing"></a>SIEM API yönlendirmesi

| Özellik | Yeniden yönlendirme KAPALI olduğunda hedef | Yeniden yönlendirme ON olduğunda hedef |
|---------|---------|---------|
| LinkToWDATP | securitycenter.windows.com uyarı sayfası | security.microsoft.com uyarı sayfası |
| IncidentLinkToWDATP | securitycenter.windows.com'deki olay sayfası | security.microsoft.com'daki olay sayfası |
| LinkToMTP | security.microsoft.com uyarı sayfası | security.microsoft.com uyarı sayfası |
| IncidentLinkToMTP | security.microsoft.com'daki olay sayfası | security.microsoft.com'daki olay sayfası |

## <a name="email-alert-notifications"></a>Uyarı bildirimlerini Email

| Özellik | Yeniden yönlendirme KAPALI olduğunda hedef** | Yeniden yönlendirme ON olduğunda hedef |
|---------|---------|---------|
| Uyarı sayfası | securitycenter.windows.com uyarı sayfası | security.microsoft.com uyarı sayfası |
| Olay sayfası |securitycenter.windows.com'deki olay sayfası | security.microsoft.com'daki olay sayfası |
| Bulut için Defender portalındaki uyarı sayfası | security.microsoft.com uyarı sayfası | security.microsoft.com uyarı sayfası |
| Bulut için Defender portalındaki olay sayfası | security.microsoft.com'daki olay sayfası | security.microsoft.com'daki olay sayfası |

## <a name="when-does-this-take-effect"></a>Bu ne zaman geçerli olur?

Etkinleştirildikten sonra, bu güncelleştirme bazı hesaplar için hemen geçerli olabilir. Ancak yeniden yönlendirmenin kuruluşunuzdaki her hesaba yayılması daha uzun sürebilir. Bu ayar uygulanırken etkin oturumlardaki hesaplar oturumlarından çıkarılmaz ve yalnızca geçerli oturumlarını sonlandırıp yeniden oturum açtıktan sonra Microsoft 365 Defender yönlendirilir.  

### <a name="set-up-portal-redirection"></a>Portal yeniden yönlendirmesini ayarlama

Hesapları Microsoft 365 Defender yönlendirmeye başlamak için:

1. Azure Active Directory'de genel yönetici olduğunuzdan veya güvenlik yöneticisi izinlerine sahip olduğunuzdan emin olun.

2. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> oturum açın.

3. **Ayarlar** > **Uç Noktaları** > **Genel** > **Portal yeniden yönlendirmesine** gidin veya [buraya tıklayın](https://security.microsoft.com/preferences2/portal_redirection).  

4. Otomatik yeniden yönlendirme ayarını **Açık** olarak değiştirin.

5. Microsoft 365 Defender otomatik yeniden yönlendirme uygulamak için **Etkinleştir'e** tıklayın.

>[!IMPORTANT]
>Bu ayarın etkinleştirilmesi etkin kullanıcı oturumlarını sonlandırmaz. Bu ayar uygulandığı sırada etkin oturumda olan hesaplar yalnızca geçerli oturumlarını sonlandırıp yeniden oturum açtıktan sonra Microsoft 365 Defender yönlendirilir.

>[!NOTE]
>Bu ayarı etkinleştirmek veya devre dışı bırakmak için Azure Active Directory'de genel yönetici olmanız veya güvenlik yöneticisi izinlerine sahip olmanız gerekir.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Eski portalı kullanmaya geri dönebilir miyim?

Sizin için bir şey çalışmıyorsa veya Microsoft 365 Defender tamamlayamadığınız bir şey varsa, bunu duymak isteriz. Yeniden yönlendirmeyle ilgili herhangi bir sorunla karşılaştıysanız, Geri bildirim gönder formunu kullanarak bize bildirmenizi öneririz.

Eski Uç Nokta için Microsoft Defender portalına dönmek için:

1. Azure Active Directory'de genel yönetici olarak veya güvenlik yöneticisi izinleriyle ve hesabı kullanarak <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> oturum açın.

2. **Ayarlar** > **Uç Noktaları** > **Genel** > **Portal yeniden yönlendirmesine** gidin veya [sayfayı burada açın](https://security.microsoft.com/preferences2/portal_redirection).  

3. Otomatik yeniden yönlendirme ayarını **Kapalı olarak değiştirin**.

4. İstendiğinde geri bildirim paylaşmak & **Devre Dışı Bırak'a** tıklayın.

Bu ayar istediğiniz zaman yeniden etkinleştirilebilir. 

Devre dışı bırakıldıktan sonra hesaplar artık security.microsoft.com yönlendirilmeyecek ve bir kez daha eski portala (securitycenter.windows.com veya securitycenter.microsoft.com) erişebilirsiniz. 

## <a name="related-information"></a>İlgili bilgiler
- [Microsoft 365 Defender genel bakış](microsoft-365-defender.md)
- [Microsoft 365 Defender'da Uç Nokta için Microsoft Defender](microsoft-365-security-center-mde.md)
- [Microsoft, güvenlik işlemlerini modernleştirmek için birleşik SIEM ve XDR sunar](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR ile SIEM bilgi grafiği karşılaştırması](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [Microsoft 365 Defender hakkında](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft güvenlik portalları ve yönetim merkezleri](portals.md)
