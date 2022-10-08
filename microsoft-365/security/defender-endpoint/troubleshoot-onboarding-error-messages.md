---
title: Ekleme sorunlarını ve hata iletilerini giderme
description: Uç Nokta için Microsoft Defender kurulumunu tamamlarken ekleme sorunlarını ve hata iletisini giderin.
keywords: sorun giderme, sorun giderme, Azure Active Directory, ekleme, hata iletisi, hata iletileri, uç nokta için Microsoft Defender
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
- tier3
ms.topic: troubleshooting
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 83dfcb73e9d73df22348e490fbd232bb7d0d4e63
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231736"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>Abonelik ve portal erişimi sorunlarını giderin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

Bu sayfa, Uç Nokta için Microsoft Defender hizmetinizi ayarlarken oluşabilecek sorunları gidermek için ayrıntılı adımlar sağlar.

Bir hata iletisi alırsanız, Microsoft 365 Defender sorunun ne olduğuna ilişkin ayrıntılı bir açıklama sağlar ve ilgili bağlantılar sağlanır.

## <a name="no-subscriptions-found"></a>Abonelik bulunamadı

Microsoft 365 Defender erişirken **Abonelik bulunamadı** iletisini alıyorsanız bu, portalda kullanıcı oturum açmak için kullanılan Azure Active Directory'nin (Azure AD) Uç Nokta için Microsoft Defender lisansına sahip olmadığı anlamına gelir.

Olası nedenler:

- Windows E5 ve Office E5 lisansları ayrı lisanslardır.
- Lisans satın alındı ancak bu Azure AD örneğine sağlanmamış.
  - Bu bir lisans sağlama sorunu olabilir.
  - Lisansı yanlışlıkla hizmette kimlik doğrulaması için kullanılandan farklı bir Microsoft Azure AD sağladınız olabilir.

Her iki durumda da [Genel Uç Nokta için Microsoft Defender Desteği](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) veya [Toplu lisans desteği konusunda Microsoft desteğine](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx) başvurmanız gerekir.

:::image type="content" source="images/atp-no-subscriptions-found.png" alt-text="Abonelik bulunamadı sayfası" lightbox="images/atp-no-subscriptions-found.png":::

## <a name="your-subscription-has-expired"></a>Aboneliğinizin süresi doldu

Microsoft 365 Defender erişirken **Aboneliğinizin süresi doldu** iletisini alırsanız çevrimiçi hizmet aboneliğinizin süresi dolmuştur. diğer çevrimiçi hizmet abonelikleri gibi Uç Nokta için Microsoft Defender aboneliğin de son kullanma tarihi vardır.

Lisansı istediğiniz zaman yenilemeyi veya genişletmeyi seçebilirsiniz. Son kullanma tarihinden sonra portala erişirken, lisansı yenilememeyi seçerseniz **aboneliğinizin süresi doldu** iletisine cihaz çıkarma paketini indirme seçeneği sunulur.

> [!NOTE]
> Güvenlik nedeniyle, cihazları kullanıma almak için kullanılan paketin süresi, indirildiği tarihten 30 gün sonra dolar. Bir cihaza gönderilen süresi dolan çıkarma paketleri reddedilir. Bir çıkarma paketini indirirken paketlerin son kullanma tarihi size bildirilir ve paket adına da eklenir.

:::image type="content" source="images/atp-subscription-expired.png" alt-text="Aboneliğin süresi doldu bildirim iletisi" lightbox="images/atp-subscription-expired.png":::

## <a name="you-are-not-authorized-to-access-the-portal"></a>Portala erişme yetkiniz yok

**Portala erişim yetkiniz yok** iletisini alırsanız, Uç Nokta için Microsoft Defender bir güvenlik izleme, olay araştırması ve yanıt ürünü olduğunu ve bu nedenle bu ürüne erişimin kullanıcı tarafından kısıtlandığını ve denetlendiğini unutmayın.
Daha fazla bilgi için bkz. [**Portala kullanıcı erişimi atama**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).

:::image type="content" source="images/atp-not-authorized-to-access-portal.png" alt-text="Erişime izin verilmeyen bildirim iletisi" lightbox="images/atp-not-authorized-to-access-portal.png":::

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>Veriler şu anda portalın bazı bölümlerinde kullanılamıyor

Portal panosunda ve diğer bölümlerde "Veriler şu anda kullanılamıyor" gibi bir hata iletisi gösteriliyorsa:

:::image type="content" source="images/atp-data-not-available.png" alt-text="Veri kullanım dışı bildirimi iletisi" lightbox="images/atp-data-not-available.png":::

Web tarayıcınızda altındaki ve tüm alt etki alanlarına izin vermeniz `security.windows.com` gerekir. Örneğin, `*.security.windows.com`.

## <a name="portal-communication-issues"></a>Portal iletişim sorunları

Portala erişme, eksik veriler veya portalın bazı bölümlerine kısıtlı erişimle ilgili sorunlarla karşılaşırsanız, aşağıdaki URL'lere izin verildiğini ve iletişim için açıldığını doğrulamanız gerekir.

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.security.microsoft.com`
- `https://automatediracs-eus-prd.security.microsoft.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com`
- `https://security.microsoft.com`
- `https://static2.sharepointonline.com`
