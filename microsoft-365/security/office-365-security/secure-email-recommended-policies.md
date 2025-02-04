---
title: Güvenli e-posta önerilen ilkeler - Kurumsal | için Microsoft 365 Microsoft Docs
description: E-posta ilkelerinin ve yapılandırmalarının nasıl uygulanacağı hakkında Microsoft önerilerine yönelik ilkeleri açıklar.
ms.author: dansimp
author: dansimp
manager: Laurawi
ms.service: microsoft-365-security
ms.topic: conceptual
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- m365-security
- remotework
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 210657acdb3d9c61e76abed681c465cad2c049e1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640092"
---
# <a name="policy-recommendations-for-securing-email"></a>E-postanın güvenliğini sağlamaya yönelik ilke önerileri

Bu makalede, modern kimlik doğrulaması ve koşullu erişimi destekleyen kurumsal e-posta ve e-posta istemcilerini korumak için önerilen Sıfır Güven kimlik ve cihaz erişim ilkelerinin nasıl uygulandığı açıklanır. Bu kılavuz [, Ortak kimlik ve cihaz erişim ilkelerine](identity-access-policies.md) dayalıdır ve ayrıca birkaç ek öneri içerir.

Bu öneriler, gereksinimlerinizin ayrıntı düzeyine göre uygulanabilecek üç farklı güvenlik ve koruma katmanını temel alır: **başlangıç noktası**, **kuruluş** ve **özel güvenlik**. Bu güvenlik katmanları ve önerilen istemci işletim sistemleri hakkında daha fazla bilgi edinmek için önerilen [güvenlik ilkeleri ve yapılandırmalarına giriş](microsoft-365-policies-configurations.md) bölümünde bu önerilere başvurabilirsiniz.

Bu öneriler, kullanıcılarınızın mobil cihazlarda iOS ve Android için Outlook da dahil olmak üzere modern e-posta istemcilerini kullanmasını gerektirir. iOS ve Android için Outlook, Office 365 en iyi özellikleri için destek sağlar. Bu mobil Outlook uygulamaları, mobil kullanımı destekleyen ve diğer Microsoft bulut güvenliği özellikleriyle birlikte çalışan güvenlik özellikleriyle de tasarlanır. Daha fazla bilgi için bkz. [iOS ve Android için Outlook SSS](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Ortak ilkeleri e-posta içerecek şekilde güncelleştirme

Aşağıdaki diyagramda e-postayı korumak için ortak kimlik ve cihaz erişim ilkelerinden hangi ilkelerin güncelleştirildiği gösterilmektedir.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png" alt-text="Microsoft Exchange erişimini korumaya yönelik ilke güncelleştirmelerinin özeti" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png":::

ActiveSync istemcilerini engellemek için Exchange Online için yeni bir ilke ekli olduğunu unutmayın. Bu, Outlook Mobile'ın kullanımını zorlar.

Exchange Online ve Outlook'u ayarlarken ilkelerin kapsamına eklediyseniz, yalnızca ActiveSync istemcilerini engellemek için yeni ilke oluşturmanız gerekir. Aşağıdaki tabloda listelenen ilkeleri gözden geçirin ve önerilen eklemeleri yapın veya bunların zaten dahil olduğunu onaylayın. Her ilke [, Ortak kimlik ve cihaz erişim ilkelerindeki](identity-access-policies.md) ilişkili yapılandırma yönergelerine bağlanır.

|Koruma düzeyi|İlkeler|Daha fazla bilgi|
|---|---|---|
|**Başlangıç noktası**|[Oturum açma riski *orta* veya *yüksek* olduğunda MFA gerektirme](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Bulut uygulamalarının atamasında Exchange Online ekleme|
||[Modern kimlik doğrulamayı desteklemeyen istemcileri engelleme](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Bulut uygulamalarının atamasında Exchange Online ekleme|
||[APP veri koruma ilkelerini uygulama](identity-access-policies.md#apply-app-data-protection-policies)|Outlook'un uygulama listesine eklendiğinden emin olun. Her platform (iOS, Android, Windows) için ilkeyi güncelleştirin|
||[Onaylı uygulamalar ve APP koruması gerektirme](identity-access-policies.md#require-approved-apps-and-app-protection)|Bulut uygulamaları listesine Exchange Online ekleme|
||[ActiveSync istemcilerini engelleme](#block-activesync-clients)|Bu yeni ilkeyi ekle|
|**Enterprise**|[Oturum açma riski *düşük*, *orta* veya *yüksek* olduğunda MFA gerektirme](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Bulut uygulamalarının atamasında Exchange Online ekleme|
||[Uyumlu bilgisayarlar *ve* mobil cihazlar gerektirme](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Bulut uygulamaları listesine Exchange Online ekleme|
|**Özel güvenlik**|[*Her zaman* MFA iste](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Bulut uygulamalarının atamasında Exchange Online ekleme|

## <a name="block-activesync-clients"></a>ActiveSync istemcilerini engelleme

Exchange ActiveSync masaüstü ve mobil cihazlarda mesajlaşma ve takvim verilerini eşitlemek için kullanılabilir.

Mobil cihazlarda, Intune uygulama koruma ilkelerini desteklemeyen istemciler (veya uygulama koruma ilkesinde tanımlanmayan desteklenen istemciler) ve temel kimlik doğrulaması kullanan Exchange ActiveSync istemciler, içinde oluşturulan [Koşullu Erişim ilkesine göre engellenir Exchange ActiveSync modern kimlik doğrulama özellikli istemciler Onaylı uygulamalar ve APP koruması gerektir](identity-access-policies.md#require-approved-apps-and-app-protection).

Diğer cihazlarda temel kimlik doğrulamasını kullanarak Exchange ActiveSync engellemek için [Tüm cihazlarda Exchange ActiveSync engelleme](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#block-exchange-activesync-on-all-devices) bölümünde verilen adımları izleyin; bu da mobil olmayan cihazlarda temel kimlik doğrulaması kullanan Exchange ActiveSync istemcilerinin Exchange Online.

Ayrıca, tüm istemci erişim isteklerini modern kimlik doğrulaması kullanmaya zorlayan [Temel kimlik doğrulamasını devre dışı bırakmak](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) için kimlik doğrulama ilkelerini de kullanabilirsiniz.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Web üzerinde Outlook'den Exchange Online erişimini sınırlama

Kullanıcıların yönetilmeyen cihazlardaki ekleri Web üzerinde Outlook indirme özelliğini kısıtlayabilirsiniz. Bu cihazlardaki kullanıcılar, dosyaları cihaza sızdırıp depolamadan Office Online'ı kullanarak bu dosyaları görüntüleyebilir ve düzenleyebilir. Ayrıca, kullanıcıların yönetilmeyen bir cihazda ekleri görmesini de engelleyebilirsiniz.

Adımlar şunlardır:

1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Henüz bir OWA posta kutusu ilkeniz yoksa [, New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) cmdlet'iyle bir tane oluşturun.
3. Eklerin görüntülenmesine izin vermek ancak indirilmek istemiyorsanız şu komutu kullanın:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Ekleri engellemek istiyorsanız şu komutu kullanın:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure portal şu ayarlarla yeni bir Koşullu Erişim ilkesi oluşturun:

   **Atama** \> **Kullanıcılar ve gruplar**: Dahil etmek ve dışlamak için uygun kullanıcıları ve grupları seçin.

   **Atama** \> **Bulut uygulamaları veya eylemleri** \> **Bulut uygulamaları** \> **Içerir** \> **Uygulamaları seçin**: **Office 365 Exchange Online'yi** seçin

   **Erişim denetimleri** \> **Oturum**: **Uygulama tarafından zorlanan kısıtlamaları kullan'ı** seçin

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS ve Android cihazlarının Outlook kullanmasını gerektir

iOS ve Android cihaz kullanıcılarının yalnızca iOS ve Android için Outlook'u kullanarak iş veya okul içeriğine erişebilmesini sağlamak için, bu olası kullanıcıları hedefleyen bir Koşullu Erişim ilkesine ihtiyacınız vardır.

[iOS ve Android için Outlook'u kullanarak mesajlaşma işbirliği erişimini yönetme](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access) başlığında bu ilkeyi yapılandırma adımlarına bakın.

## <a name="set-up-message-encryption"></a>İleti şifrelemeyi ayarlama

Azure Information Protection'daki koruma özelliklerinden yararlanan Microsoft Purview İleti Şifrelemesi ile kuruluşunuz korumalı e-postaları herhangi bir cihazdaki herkesle kolayca paylaşabilir. Kullanıcılar, diğer Microsoft 365 kuruluşlarının yanı sıra Outlook.com, Gmail ve diğer e-posta hizmetlerini kullanan müşterilerle korumalı iletiler gönderebilir ve alabilir.

Daha fazla bilgi için bkz[. Yeni Office 365 İleti Şifrelemesi özelliklerini ayarlama](../../compliance/set-up-new-message-encryption-capabilities.md).

## <a name="next-steps"></a>Sonraki adımlar

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Microsoft 365 bulut uygulamaları için İlkeler" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

Koşullu Erişim ilkelerini yapılandırma:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
