---
title: Etki alanını kaldırma
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Eski bir etki alanını Microsoft 365'ten kaldırmayı ve kullanıcıları ve grupları başka bir etki alanına taşımayı veya aboneliğinizi iptal etmeyi öğrenin.
ms.openlocfilehash: 76b64bc8e937a83ab4333cdd6ff774525f7ddd99
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731359"
---
# <a name="remove-a-domain"></a>Etki alanını kaldırma

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

Etki alanınızı farklı bir Microsoft 365 abonelik planına eklemek istediğiniz için mi kaldırıyorsunuz? Yoksa yalnızca aboneliğinizi iptal etmek mi istiyorsunuz? [Planınızı veya aboneliğinizi değiştirebilir](../../commerce/subscriptions/switch-to-a-different-plan.md) veya [aboneliğinizi iptal edebilirsiniz](../../commerce/subscriptions/cancel-your-subscription.md).

> [!TIP]
> Bu konuda verilen adımlarla ilgili yardıma ihtiyacınız varsa[bir Microsoft küçük işletme uzmanıyla çalışmayı](https://go.microsoft.com/fwlink/?linkid=2186871) göz önünde bulundurun. İşletme Yardımı ile, işletmenizi büyütürken katılımdan gündelik kullanıma kadar her aşamada siz ve çalışanlarınız günün 24 saati küçük işletme uzmanlarına erişebilirsiniz.

### <a name="step-1-move-users-to-another-domain"></a>1. Adım: Kullanıcıları başka bir etki alanına taşıma

#### <a name="move-users"></a>Kullanıcıları taşıma

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Yönetim merkezine</a> gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Yönetim merkezine</a> gidin.

::: moniker-end

2. **Etkin Kullanıcılar'ı** >  seçin.

3. Taşımak istediğiniz tüm kullanıcıların adlarının yanındaki kutuları seçin.

4. Sayfanın üst kısmında Etki **alanlarını değiştir'i** seçin.

5. **Etki alanlarını değiştir** bölmesinde farklı bir etki alanı seçin.

You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

#### <a name="move-yourself"></a>Kendinizi hareket ettirin

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Yönetim merkezine</a> gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Yönetim merkezine</a> gidin.

::: moniker-end

2. **Etkin Kullanıcılar'a** \> gidin ve listeden hesabınızı seçin.

3. **Hesap** sekmesinde **Kullanıcı adını yönet'i** seçin ve ardından farklı bir etki alanı seçin.

4. Üst kısımda hesap adınızı ve ardından **Oturumu Kapat'ı** seçin.

5. Yeni etki alanıyla ve aynı parolayla oturum açın.

Kullanıcıları başka bir etki alanına taşımak için PowerShell'i de kullanabilirsiniz. Daha fazla bilgi için bkz. [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) . Varsayılan etki alanını ayarlamak için [Set-MsolDomain](/powershell/module/msonline/set-msoldomain) komutunu kullanın.

### <a name="step-2-move-groups-to-another-domain"></a>2. Adım: Grupları başka bir etki alanına taşıma

::: moniker range="o365-worldwide"

1. Yönetim merkezinde **Gruplar Grupları** \> sayfasına gidin.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Yönetim merkezinde</a> **Gruplar Grupları** > sayfasına gidin.

::: moniker-end

2. Grup adını seçin ve **genel sekmesinde** **Email adresin altında Birincil'i**, **Düzenle'yi** seçin.

3. Başka bir etki alanı seçmek için açılan listeyi kullanın.

4. **Kaydet'i** ve ardından **Kapat'ı** seçin. Kaldırmak istediğiniz etki alanıyla ilişkilendirilmiş tüm gruplar veya dağıtım liseleri için bu işlemi yineleyin.

### <a name="step-3-remove-the-old-domain"></a>3. Adım: Eski etki alanını kaldırma

::: moniker range="o365-worldwide"

> [!NOTE]
> Özel bir etki alanını kaldırıyorsanız devam etmeden önce [özel etki alanını kaldırma](#remove-a-custom-domain) konusuna bakın.

1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetim merkezinde **, Kurulum** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end

2. **Etki Alanları** sayfasında, kaldırmak istediğiniz etki alanını seçin.

3. Sağ bölmede **Kaldır'ı** seçin.

4. Ek istemleri izleyin ve **kapat'ı** seçin.




### <a name="remove-a-custom-domain"></a>Özel etki alanını kaldırma

Aboneliğinizi iptal ediyorsanız ve özel bir etki alanı kullanıyorsanız, aboneliğinizi iptal etmeden önce yapmanız gereken birkaç ek adım vardır. 

#### <a name="change-your-domain-nameserver-records-if-needed"></a>Etki alanı ad sunucusu kayıtlarınızı değiştirme (gerekirse)

Özel bir etki alanı ayarladıysanız, etki alanının Microsoft 365 hizmetleriyle çalışması için DNS kayıtları eklediniz. Etki alanınızı kaldırmadan önce, DNS ana bilgisayarınızda etki alanı MX kaydınız gibi DNS kayıtlarını güncelleştirdiğinizden emin olun.

Örneğin, DNS ana bilgisayarınızda MX kaydını değiştirin. etki alanınıza gönderilen Email Microsoft adresinize gelmeyi durdurur ve bunun yerine yeni e-posta sağlayıcınıza gider. (MX kaydı, etki alanınıza yönlendirilen e-postanın nereye gönderileceğini belirler.)

- Ad sunucusu (NS) [kayıtlarınız Microsoft 365 ad sunucularını gösteriyorsa](../../admin/setup/add-domain.md), NS kayıtlarınızı yeni DNS ana bilgisayarınıza işaret edecek şekilde değiştirene kadar MX kaydınızda yapılan değişiklikler geçerli olmaz (bkz. 2. Adım).

- MX kaydını güncelleştirmeden önce, kullanıcılarınıza e-postalarını değiştirmeyi planladığınız tarihi ve kullanmayı planladığınız yeni e-posta sağlayıcısını bildirin. Ayrıca, kullanıcılarınız mevcut Microsoft e-postalarını yeni sağlayıcıya taşımak isterse ek adımlar atmalıdır.

- MX kaydını değiştirdiğiniz gün [verilerinizi kaydettiğinizden](/microsoft-365/commerce/subscriptions/cancel-your-subscription#save-your-data) ve [gerekirse Office'i kaldırdığınızdan](/microsoft-365/commerce/subscriptions/cancel-your-subscription#uninstall-office-optional) emin olun.

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>Etki alanı MX'inizi ve diğer DNS kayıtlarınızı güncelleştirin (özel bir etki alanı kullanıyorsanız)

Etki alanınızı ayarlarken ad sunucusu (NS) kayıtlarınızı Microsoft 365'e geçirdiyseniz, kullanmayı planladığınız DNS ana bilgisayarında MX kaydınızı ve diğer DNS kayıtlarınızı ayarlamanız veya güncelleştirmeniz ve ardından NS kaydınızı bu DNS ana bilgisayarıyla değiştirmeniz gerekir.

Etki alanınızı ayarlarken NS kayıtlarını değiştirmediyseniz, MX kaydını değiştirdiğinizde postanız hemen yeni adrese gider.

NS kayıtlarınızı değiştirmek için bkz. [Microsoft 365'i herhangi bir etki alanı kayıt şirketiyle ayarlamak için ad sunucularını değiştirme](../../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).



## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Etki alanının kaldırılması ne kadar sürer?

Güvenlik grupları, dağıtım listeleri, kullanıcılar, diğer adlar, paylaşılan posta kutuları, kaynak posta kutuları ve Microsoft 365 grupları gibi birçok yerde başvurulmazsa Microsoft 365'in etki alanını kaldırması beş dakika kadar sürebilir. Etki alanını kullanan çok fazla başvuru varsa, etki alanının kaldırılması saatler (bir gün) sürebilir.

If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) for more information. To set the default domain, use [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>Yine de yardım mı gerekiyor?

::: moniker range="o365-worldwide"

> [!NOTE]
> Hesabınızdan [".onmicrosoft.com"](../setup/domains-faq.yml) etki alanını kaldıramazsınız. Bir etki alanını kaldırdığınızda, kullanıcı hesapları ".onmicrosoft.com" adresine Birincil SMTP/UserprincipalName olarak geri döner.

Hala çalışmıyor mu? Etki alanınızın el ile kaldırılması gerekebilir. [Bize telefon edin](../../business-video/get-help-support.md) ve bununla ilgilenmenize yardım edelim!

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> [Hesabınızdan ".partner.onmschina.cn"](../setup/domains-faq.yml) etki alanını kaldıramazsınız. Bir etki alanını kaldırdığınızda, kullanıcı hesapları ".partner.onmschina.cn" adresine Birincil SMTP/UserprincipalName olarak geri döner.

Hala çalışmıyor mu? Etki alanınızın el ile kaldırılması gerekebilir. [Bize telefon edin](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) ve bununla ilgilenmenize yardım edelim!

::: moniker-end

## <a name="related-content"></a>İlgili içerik

[Etki alanları hakkında SSS](../setup/domains-faq.yml) (makale)

[Farklı bir İş için Microsoft 365 planına geçme](../../commerce/subscriptions/switch-to-a-different-plan.md) (makale)

[Aboneliğinizi iptal etme](../../commerce/subscriptions/cancel-your-subscription.md) (makale)
