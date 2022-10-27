---
title: Outlook mobil uygulamalarında oturum açmak için QR kodu kullanma
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier3
- scotvorg
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: Outlook Mobile'da kimlik doğrulaması yapmak ve indirmek için QR kodu kullanmayı öğrenin.
ms.openlocfilehash: 21314cf560e8a3556a7289d95c244e3e3795200d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718666"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Outlook mobil uygulamalarında oturum açmak için QR kodu kullanma

Microsoft 365 yöneticisi olarak, kullanıcılarınızın kullanıcı adlarını ve parolalarını girmek zorunda kalmadan mobil cihazlarında Android için Outlook veya iOS uygulamasında oturum açmalarını sağlayabilirsiniz. Kullanıcılar qr kodunu tarayarak güvenli bir şekilde kimlik doğrulaması yapabilir ve Outlook Mobile'da oturum açabilir.

Web üzerinde Outlook veya diğer masaüstü Outlook uygulamalarında kullanıcılar, mobil cihazlarında Outlook'u kullanabileceklerini bildiren bildirimler görebilir. Bu bildirimler Exchange PowerShell kullanılarak yönetici tarafından yönetilebilir. Kullanıcılar uygulamayı mobil cihazlarına indirmek için kendilerine sms kısa mesaj göndermeyi seçerse, bilgisayarlarında bir QR kodu görünür. Telefon veya tabletlerinde Outlook'ta oturum açmak için QR kodunu tarayabilecekler. Bu QR kodu, yalnızca bir kez kullanılabilen kısa ömürlü bir belirteçtir.

Bildirim yalnızca aşağıdaki koşullar karşılandığında oluşturulur:

1. QR kodu deneyimi kiracı için etkindir (bu deneyim varsayılan olarak etkindir).

2. Kullanıcı iOS ve Android için Outlook'u henüz kullanmıyor.

3. Kullanıcının okuma bölmesinde boş bir durumu var (ilk e-postayı otomatik olarak açma seçeneğini belirlemez).

4. Kullanıcı bildirimi kapatmadı.

> [!NOTE]
> Bazı durumlarda, kullanıcılarınızın QR kodunu oluşturmak için bilgisayarlarında yeniden kimlik doğrulaması yapması gerekir.

## <a name="use-exchange-powershell"></a>Exchange PowerShell kullanma

Bu özellik varsayılan olarak açıktır. Bu özelliği devre dışı bırakmak için aşağıdaki adımları izleyin.

1. [Exchange PowerShell'e bağlanın](/powershell/exchange/connect-to-exchange-online-powershell).
2. PowerShell'i kullanarak, kullanıcılarınıza Outlook mobil uygulamaları hakkında bilgi veren bildirimleri devre dışı bırakabilirsiniz. Bu, QR kodu oturum açma akışının gösterilmesini de engeller.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

> [!NOTE]
> Exchange PowerShell komutunu kullanırken değişikliklerin yayılması 8 saat kadar sürebilir.

## <a name="related-content"></a>İlgili içerik

[Standart veya Hedefli sürüm seçeneklerini ayarlama](release-options-in-office-365.md) (makale)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (makale)
