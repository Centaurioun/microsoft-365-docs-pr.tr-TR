---
title: MSCommerce PowerShell modülü için AllowSelfServicePurchase kullanma
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: ''
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
search.appverid:
- MET150
description: Self servis satın alma özelliğini açmak veya kapatmak için AllowSelfServicePurchase PowerShell cmdlet'ini kullanmayı öğrenin.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 08/09/2022
ms.openlocfilehash: 080b12672607301b9dcc9977c1c93ad9b48d43cd
ms.sourcegitcommit: f72ea75c6d5c1bca0e0ed8fd228d3a84c6104361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67301910"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>MSCommerce PowerShell modülü için AllowSelfServicePurchase kullanma

**MSCommerce** PowerShell modülü artık [PowerShell Galerisi'de](https://aka.ms/allowselfservicepurchase-powershell-gallery) kullanılabilir. Modül, **allowSelfServicePurchase** için kuruluşunuzdaki kullanıcıların self servis satın alma işlemi yapıp yapamayacağını denetlemenize olanak tanıyan bir **PolicyID** parametre değeri içerir.

**MSCommerce** PowerShell modülünü kullanarak şunları yapabilirsiniz:

- **AllowSelfServicePurchase** parametre değerinin varsayılan durumunu (etkin, devre dışı veya ödeme yöntemi olmadan denemelere izin ver) görüntüleyin
- Geçerli ürünlerin listesini ve self servis satın alma özelliğinin etkinleştirilip etkinleştirilmediğini, devre dışı bırakılıp bırakılmadığını veya ödeme yöntemi olmadan denemelere izin verilip verilmediğini görüntüleyin
- Belirli bir ürünü etkinleştirmek veya devre dışı bırakmak için geçerli ayarı görüntüleme veya değiştirme
- Ödeme yöntemleri olmadan denemeler için ayarı görüntüleme veya değiştirme

## <a name="requirements"></a>Gereksinimler

**MSCommerce** PowerShell modülünü kullanmak için şunları yapmanız gerekir:

- Windows 10 cihazı
- PowerShell 5 veya üzeri. PowerShell 6.x/7.x şu anda bu modülde desteklenmiyor.
- Cihaz için yönetici izni
- Kiracınız için genel veya Faturalama Yönetici rolü

## <a name="install-the-mscommerce-powershell-module"></a>MSCommerce PowerShell modülünü yükleme

**MSCommerce** PowerShell modülünü Windows 10 cihazınıza bir kez yükler ve ardından başlattığınız her PowerShell oturumuna aktarırsınız. **MSCommerce** PowerShell modülünü [PowerShell Galerisi](https://aka.ms/allowselfservicepurchase-powershell-gallery) indirin.

**MSCommerce** PowerShell modülünü **PowerShellGet** ile yüklemek için aşağıdaki komutu çalıştırın:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>MSCommerce'i PowerShell oturumuna aktarma

Modülü Windows 10 cihazınıza yükledikten sonra, başlattığınız her PowerShell oturumuna aktarırsınız. Bir PowerShell oturumuna aktarmak için aşağıdaki komutu çalıştırın:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Kimlik bilgilerinizle MSCommerce'e bağlanma

Kimlik bilgilerinizle PowerShell modülüne bağlanmak için aşağıdaki komutu çalıştırın.

```powershell
Connect-MSCommerce
```

Bu komut, geçerli PowerShell oturumunu bir Azure Active Directory kiracısına bağlar. Komut, bağlanmak istediğiniz kiracı için bir kullanıcı adı ve parola ister. Kimlik bilgileriniz için çok faktörlü kimlik doğrulaması etkinleştirildiyse, oturum açmak için etkileşimli seçeneği kullanırsınız.

## <a name="view-details-for-allowselfservicepurchase"></a>AllowSelfServicePurchase için ayrıntıları görüntüleme

**AllowSelfServicePurchase** parametre değerinin açıklamasını ve kuruluşunuza bağlı olarak varsayılan durumu görüntülemek için aşağıdaki komutu çalıştırın:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Self servis satın alma ürünlerinin listesini ve durumlarını görüntüleme

Kullanılabilir tüm self servis satın alma ürünlerinin listesini ve her birinin durumunu görüntülemek için aşağıdaki komutu çalıştırın:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

Aşağıdaki tabloda, kullanılabilir ürünler ve **bunların ProductId'leri** listelenir.

| Ürün | Productıd |
|-----------------------------|--------------|
| Kullanıcı başına Power Apps* | CFQ7TTC0LH2H |
| Kullanıcı başına Power Automate | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (tek başına) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1* | CFQ7TTC0HDB1 |
| Project Plan 3* | CFQ7TTC0HDB0 |
| Visio Plan 1* | CFQ7TTC0HD33 |
| Visio Plan 2* | CFQ7TTC0HD32 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows Hibrit Avantajı ile Windows 365 Business | CFQ7TTC0HX99 |
| Microsoft 365 F3 | CFQ7TTC0LH05 |
| Dynamics 365 Marketing | CFQ7TTC0LH3N |
| Dynamics 365 Marketing Attach | CFQ7TTC0LHWP | 
| Dynamics 365 Marketing Ek Uygulaması | CFQ7TTC0LHVK |
| Dynamics 365 Marketing Ek Üretim Dışı Uygulama | CFQ7TTC0LHWM |

*Bu kimlikler değişti. Eski kimlikleri kullanan ürünleri daha önce engellediyseniz, yeni kimlikler kullanılarak otomatik olarak engellenir. Ek çalışma gerekmez.

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>AllowSelfServicePurchase durumunu görüntüleme veya ayarlama

Kullanıcıların self servis satın alma işlemi yapmalarına izin vermek veya bunları engellemek için **AllowSelfServicePurchase** **için Value** parametresini ayarlayabilirsiniz. Kullanıcıların onaylanan ürünler listesinden ürünleri denemesine izin vermek için **OnlyTrialsWithoutPaymentMethod** değerini de kullanabilirsiniz. Kullanıcılar ürünü yalnızca **AllowSelfServicePurchase** etkinleştirildiğinde deneme süresi sona erdikten sonra satın alabilir.

**OnlyTrialsWithoutPaymentMethod** değeri, satın almaları engellemeye devam ederken geçici denemelere izin verir.

Aşağıdaki tabloda **Value** parametresinin ayarları açıklanmaktadır.

| **Ayar** | **Etki** |
|---|---|
| Etkin | Kullanıcılar self servis satın alma işlemleri yapabilir ve ürün için denemeler alabilir. |
| OnlyTrialsWithoutPaymentMethod | Kullanıcılar self servis satın alma işlemi yapamaz ancak ürün için denemeler alabilir. Deneme süresi dolduktan sonra tam sürümü satın alamıyorlar. |
| Devre dışı | Kullanıcılar self servis satın alma işlemi yapamaz veya ürün için deneme sürümü edinemez. |

Belirli bir ürünün ilke ayarını almak için aşağıdaki komutu çalıştırın:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Belirli bir ürün için ilke ayarını etkinleştirmek için aşağıdaki komutu çalıştırın:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "Enabled"
```

Belirli bir ürünün ilke ayarını devre dışı bırakmak için aşağıdaki komutu çalıştırın:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "Disabled"
```

Kullanıcıların ödeme yöntemi olmadan belirli bir ürünü denemesine izin vermek için aşağıdaki komutu çalıştırın:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Value "OnlyTrialsWithoutPaymentMethod" 
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>AllowSelfServicePurchase'ı devre dışı bırakmak için örnek betik

Aşağıdaki örnekte **MSCommerce** modülünü içeri aktarma, hesabınızla oturum açma, kullanıcı başına Power Automate için **ProductId** değerini alma ve bu ürün için **AllowSelfServicePurchase'ı** devre dışı bırakma konusunda size yol gösterilir.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate per user'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Value "Disabled"
```

Ürün için birden çok değer varsa, aşağıdaki örnekte gösterildiği gibi komutu her değer için ayrı ayrı çalıştırabilirsiniz:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Value "Disabled"
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Value "Disabled"
```

## <a name="troubleshooting"></a>Sorun giderme

### <a name="problem"></a>Sorun

Aşağıdaki hata iletisini görürsünüz:

> HandleError: policyId 'AllowSelfServicePurchase' ile alınamadı, ErrorMessage - Temel alınan bağlantı kapatıldı: Gönderme sırasında beklenmeyen bir hata oluştu.

Bunun nedeni Aktarım Katmanı Güvenliği'nin (TLS) eski bir sürümü olabilir. Bu hizmeti bağlamak için TLS 1.2 veya üzerini kullanmanız gerekir

### <a name="solution"></a>Çözüm

TLS 1.2'ye yükseltin. Aşağıdaki söz dizimi ServicePointManager Güvenlik Protokolü'ni TLS1.2 olarak güncelleştirir:

```powershell
 [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
```

Daha fazla bilgi için bkz. [TLS 1.2'yi etkinleştirme](/mem/configmgr/core/plan-design/security/enable-tls-1-2).

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>İlgili içerik

[Self servis satın almaları yönetme (Yönetici)](manage-self-service-purchases-admins.md) (makale)\
[Self servis satın alma hakkında SSS](self-service-purchase-faq.yml) (makale)
