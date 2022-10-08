---
title: Kimlik sahtekarlığına neden olan gönderenleri kimlik sahtekarlık zekası ilkesini ve kimlik sahtekarı zeka içgörülerini kullanarak yönetme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- m365-security
description: Yöneticiler, kimlik sahtekarlığına neden olan gönderenlere izin vermek veya bunları engellemek için kimlik sahtekarlık zekası ilkesini ve sahte zeka içgörülerini kullanmayı öğrenebilir.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6cc9c53ab93d3f97e3547adb9b5354e52e6c4e98
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066332"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>EOP'de sahte zeka ilkesini ve sahte zeka içgörülerini kullanarak sahte gönderenleri yönetme

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Microsoft 365 Defender portalındaki sahte gönderen yönetimi artık yalnızca Kiracı İzin Ver/Engelle Listesi'ndeki Kimlik **Sahtekarı gönderenler** sekmesinde kullanılabilir. Microsoft 365 Defender portalındaki geçerli yordamlar için bkz. [EOP'de sahte zeka içgörüleri](learn-about-spoof-intelligence.md).
>
> Exchange Online PowerShell veya Tek Başına EOP PowerShell'de sahte gönderen yönetimi yalnızca ilgili **\*-TenantAllowBlockListSpoofItems**, **Get-SpoofIntelligenceInsight** ve **Get-SpoofMailReport** cmdlet'lerine geçiriliyor. Bu cmdlet'leri kullanan yordamlar için aşağıdaki makalelere bakın:
>
> - [Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenlerin izin verme veya engelleme girdilerini görüntülemek için PowerShell kullanma](allow-block-email-spoof.md#use-powershell-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [Sahte gönderenler için izin verme girdileri oluşturmak için PowerShell kullanma](allow-block-email-spoof.md#use-powershell-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [Sahte gönderenler için blok girdileri oluşturmak için PowerShell kullanma](allow-block-email-spoof.md#use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenlerin izin verme veya engelleme girdilerini değiştirmek için PowerShell kullanma](allow-block-email-spoof.md#use-powershell-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)
> - [Kiracı İzin Ver/Engelle Listesinden sahte gönderenlere yönelik izin verme veya engelleme girdilerini kaldırmak için PowerShell kullanma](allow-block-email-spoof.md#use-powershell-to-remove-allow-or-block-entries-for-spoofed-senders-from-the-tenant-allowblock-list)
>
> **Get-PhishFilterPolicy** ve **Set-PhishFilterPolicy** cmdlet'lerini kullanan daha eski sahte gönderen yönetimi deneyimi kullanım dışı bırakılıyor, ancak cmdlet'ler her yerde kaldırılana kadar eksiksizlik için bu makalede sunulmaya devam ediyor.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell). Tek başına EOP PowerShell'e bağlanmak için bkz. [Exchange Online Protection PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bu makaledeki yordamları gerçekleştirebilmeniz için **önce Exchange Online'de** izinlerin atanmış olması gerekir:
  - Kimlik sahtekarlık zekası ilkesini değiştirmek veya kimlik sahtekarlık zekasını etkinleştirmek veya devre dışı bırakmak için şunlara üye olmanız gerekir:
    - **Kuruluş Yönetimi**
    - **Güvenlik Yöneticisi** <u>ve</u> **Yalnızca Görüntüleme Yapılandırması** veya **Yalnızca Görüntüleme Kuruluş Yönetimi**.
  - Kimlik sahtekarı zeka ilkesine salt okunur erişim için **Genel Okuyucu** veya **Güvenlik Okuyucusu** rol gruplarının üyesi olmanız gerekir.

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  **Notlar**:

  - kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri _ve_ izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

- Kimlik sahtekarlığı zekası seçenekleri [kimlik avı önleme ilkelerindeki kimlik sahtekarlığı ayarlarında](set-up-anti-phishing-policies.md#spoof-settings) açıklanmıştır.

- Kimlik avı önleme ilkelerinde kimlik sahtekarlığı zekası ayarlarını etkinleştirebilir, devre dışı bırakabilir ve yapılandırabilirsiniz. Aboneliğinizi temel alan yönergeler için aşağıdaki konulardan birine bakın:

  - [EOP'de kimlik avı önleme ilkelerini yapılandırın](configure-anti-phishing-policies-eop.md).
  - [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini yapılandırın](configure-mdo-anti-phishing-policies.md).

- Kimlik sahtekarlığı zekası için önerilen ayarlarımız için bkz. [EOP kimlik avı önleme ilkesi ayarları](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).

## <a name="use-powershell-to-manage-spoofed-senders"></a>Sahte gönderenleri yönetmek için PowerShell kullanma

Kimlik sahtekarlık zekasında izin verilen ve engellenen gönderenleri görüntülemek için aşağıdaki söz dizimini kullanın:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Bu örnek, etki alanlarınızdaki kullanıcıları yanıltmalarına izin verilen tüm gönderenler hakkında ayrıntılı bilgiler döndürür.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Kimlik sahtekarlığına izin verilen ve engellenen gönderenleri yapılandırmak için şu adımları izleyin:

1. Aşağıdaki komutu çalıştırarak **Get-PhishFilterPolicy** cmdlet'inin çıkışını csv dosyasına yazarak algılanan sahte gönderenlerin geçerli listesini yakalayın:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Aşağıdaki değerleri eklemek veya değiştirmek için CSV dosyasını düzenleyin:
   - **Gönderen** (kaynak sunucunun PTR kaydındaki etki alanı, IP/24 adresi veya doğrulanmış DKIM etki alanı)
   - **SpoofedUser**: Aşağıdaki değerlerden biri:
     - İç kullanıcının e-posta adresi.
     - Dış kullanıcının e-posta etki alanı.
     - Sahte e-posta adresinden bağımsız olarak belirtilen **Gönderenden** gelen tüm sahte iletileri engellemek veya bu iletilere izin vermek istediğinizi belirten boş bir değer.
   - **AllowedToSpoof** (Evet veya Hayır)
   - **SpoofType** (İç veya Dış)

   Dosyayı kaydedin, dosyayı okuyun ve aşağıdaki komutu çalıştırarak içeriği adlı `$UpdateSpoofedSenders` bir değişken olarak depolayın:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. `$UpdateSpoofedSenders` Aşağıdaki komutu çalıştırarak kimlik sahtekarlığı zeka ilkesini yapılandırmak için değişkenini kullanın:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>Bu yordamların işe yaramış olduğunu nasıl anlarsınız?

Kimlik sahtekarlığına izin verilen ve kimlik sahtekarlığına izin verilmeyen gönderenlerle kimlik sahtekarlık zekası yapılandırdığınızdan emin olmak için PowerShell'de aşağıdaki komutları çalıştırarak kimlik sahtekarlığına izin verilen ve kimlik sahtekarlığına izin verilmeyen gönderenleri görüntüleyin:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell'de, tüm sahte gönderenlerin listesini bir CSV dosyasına aktarmak için aşağıdaki komutu çalıştırın:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
