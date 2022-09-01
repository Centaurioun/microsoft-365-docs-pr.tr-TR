---
title: Office 365 için Microsoft Defender'da Güvenli Belgeler
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 A5 veya E5 Güvenliğinde Güvenli Belgeler hakkında bilgi edinin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: e89a9194956334877e6c85d73afca44dd5d25759
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67496779"
---
# <a name="safe-documents-in-microsoft-365-a5-or-e5-security"></a>Microsoft 365 A5 veya E5 Güvenliğinde Güvenli Belgeler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Güvenli Belgeler, açık Office belgelerini [Korumalı Görünüm'de](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) veya Office [için Application Guard'da](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46) taramak için [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) bulut arka ucu kullanan premium bir özelliktir.

Kullanıcıların Güvenli Belgeler korumasını almak için yerel cihazlarında Uç Nokta için Defender'ın yüklü olması gerekmez. Kullanıcılar, aşağıdaki gereksinimlerin tümü karşılanırsa Güvenli Belgeler korumasına sahiptir:

- Güvenli Belgeler, bu makalede açıklandığı gibi kuruluşta etkindir.
- Gerekli lisans planındaki lisanslar kullanıcılara atanır. Güvenli Belgeler **, Office 365 SafeDocs** (veya **SAFEDOCS** veya **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) hizmet planı (hizmet olarak da bilinir) tarafından denetlenmektedir. Bu hizmet planı aşağıdaki lisans planlarında (lisans planları, Microsoft 365 planları veya ürünler olarak da bilinir) kullanılabilir:
  - Fakülteler için Microsoft 365 A5
  - Öğrenciler için Microsoft 365 A5
  - Microsoft 365 E5 Güvenlik

  Güvenli Belgeler Office 365 için Microsoft Defender lisans planlarına dahil değildir.

  Daha fazla bilgi için bkz [. Lisanslama için ürün adları ve hizmet planı tanımlayıcıları](/azure/active-directory/enterprise-users/licensing-service-plan-reference).

- Kurumlar için Microsoft 365 Uygulamaları (eski adıyla Office 365 ProPlus) 2004 veya sonraki bir sürümünü kullanıyorlar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. Doğrudan **Güvenli Ekler** sayfasına gitmek için kullanın <https://security.microsoft.com/safeattachmentv2>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Bu makaledeki yordamları gerçekleştirebilmeniz için **önce Exchange Online'da** izinlere ihtiyacınız vardır:
  - Güvenli Belgeler ayarlarını yapılandırmak için **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol gruplarının üyesi olmanız gerekir.
  - Güvenli Belgeler ayarlarına salt okunur erişim için **Genel Okuyucu** veya **Güvenlik Okuyucusu** rol gruplarının üyesi olmanız gerekir.

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri _ve_ izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  >
  > - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft verilerinizi nasıl işler?

Güvenli Belgeler, korunmanızı sağlamak için dosyaları analiz için [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) buluta gönderir. Uç Nokta için Microsoft Defender verilerinizi nasıl işlediğine ilişkin ayrıntıları burada bulabilirsiniz: [Uç Nokta için Microsoft Defender veri depolama ve gizlilik](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Güvenli Belgeler tarafından gönderilen dosyalar, analiz için gereken sürenin (genellikle 24 saatten kısa) ötesinde Uç Nokta için Defender'da korunmaz.

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Güvenli Belgeleri yapılandırmak için Microsoft 365 Defender portalını kullanma

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, İlkeler **bölümünde** **Email & İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Güvenli Ekler'e** gidin. Doğrudan **Güvenli Ekler** sayfasına gitmek için kullanın <https://security.microsoft.com/safeattachmentv2>.

2. **Güvenli Ekler** sayfasında **Genel ayarlar'a** tıklayın.

3. Görüntülenen **Genel ayarlar** açılır penceresinde aşağıdaki ayarları yapılandırın:
   - **Office istemcileri için Güvenli Belgeler'i açma**: Özelliği açmak için iki durumlu düğmeyi sağa taşıyın: ![Açık.](../../media/scc-toggle-on.png).
   - **Güvenli Belgeler dosyayı kötü amaçlı olarak tanımlasa bile kişilerin Korumalı Görünüm'e tıklamasına izin verin**: Bu seçeneği kapalı bırakmanızı öneririz (düğmeyi sola bırakın: ![Geçiş kapalı.](../../media/scc-toggle-off.png))

   Bitirdiğinizde, **Kaydet**'i tıklatın.

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="Güvenli Ekler sayfasında Genel ayarlar'ı seçtikten sonra Güvenli Belgeler ayarları" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Güvenli Belgeleri yapılandırmak için Exchange Online PowerShell kullanma

Güvenli Belgeleri yapılandırmak için PowerShell'i kullanmayı tercih ederseniz, PowerShell'Exchange Online aşağıdaki söz dizimini kullanın:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ parametresi, tüm kuruluş için Güvenli Belgeleri etkinleştirir veya devre dışı bırakır.
- _AllowSafeDocsOpen_ parametresi, belgenin kötü amaçlı olarak tanımlanması durumunda kullanıcıların Korumalı Görünüm'den (belgeyi açma) ayrılmasını sağlar veya engeller.

Bu örnek, kuruluşun tamamı için Güvenli Belgeler'i etkinleştirir ve kullanıcıların Korumalı Görünüm'den kötü amaçlı olarak tanımlanan belgeleri açmasını engeller.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="configure-individual-access-to-safe-documents"></a>Güvenli Belgelere tek tek erişimi yapılandırma

Güvenli Belgeler özelliğine seçmeli olarak izin vermek veya erişimi engellemek istiyorsanız şu adımları izleyin:

1. Microsoft 365 Defender portalında Güvenli Belgeler'i açın veya bu makalede daha önce açıklandığı gibi PowerShell'i Exchange Online.
2. Belirli bir lisans planı için belirli kullanıcılar için [belirli Microsoft 365 hizmetlerini devre dışı bırakma bölümünde açıklandığı gibi, belirli kullanıcılar için Güvenli Belgeleri devre dışı bırakmak için](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan) Azure AD PowerShell kullanın.

  PowerShell'de devre dışı bırakılabilir hizmet planının adı **SAFEDOCS'tir**.

Daha fazla bilgi için, aşağıdaki konulara bakın:

- [PowerShell ile Microsoft 365 lisanslarını ve hizmetlerini görüntüleme](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [PowerShell ile Microsoft 365 hesap lisansı ve hizmet ayrıntılarını görüntüleme](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [Lisanslama için ürün adları ve hizmet planı tanımlayıcıları](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Denetim özelliklerini etkinleştirmek için Uç Nokta için Microsoft Defender hizmetine ekleme

Denetim özelliklerini etkinleştirmek için yerel cihazın Uç Nokta için Microsoft Defender yüklü olması gerekir. Uç Nokta için Microsoft Defender dağıtmak için dağıtımın çeşitli aşamalarından geçmeniz gerekir. Ekledikten sonra, Microsoft 365 Defender portalında denetim özelliklerini yapılandırabilirsiniz.

Daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender hizmetine ekleme](/microsoft-365/security/defender-endpoint/onboarding). Ek yardıma ihtiyacınız varsa Uç Nokta için Microsoft Defender [ekleme sorunlarını giderme konusuna](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding) bakın.

### <a name="how-do-i-know-this-worked"></a>Nasıl yaparım? çalıştığını biliyor musun?

Güvenli Belgeleri etkinleştirip yapılandırdığınızdan emin olmak için aşağıdaki adımlardan birini yapın:

- Microsoft 365 Defender portalında, genel **ayarlar** **bölümündeki Email &** **İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Güvenli Ekler'e** \> gidin ve **Office istemcileri için Güvenli Belgeleri aç'ı** **ve Güvenli Belgeler dosyayı kötü amaçlı ayarlar olarak tanımlasa bile kişilerin Korumalı Görünüm'e tıklamasına izin verin**.

- Exchange Online PowerShell'de aşağıdaki komutu çalıştırın ve özellik değerlerini doğrulayın:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Güvenli Belgeler korumasını test etmek için aşağıdaki dosyalar kullanılabilir. Bu dosyalar kötü amaçlı yazılımdan koruma ve virüsten koruma çözümlerini test etmek için EICAR.TXT dosyasına benzer. Dosyalar zararlı değildir, ancak Güvenli Belgeler korumasını tetikler.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
