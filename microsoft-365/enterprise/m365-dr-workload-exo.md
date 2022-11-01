---
title: Exchange Online için Data Residency
description: Exchange Online için Data Residency hakkında bilgi edinin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 17799d6d69daa50d6d9cb70ec3632314d5c64d3a
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806316"
---
# <a name="data-residency-for-exchange-online"></a>Exchange Online için Data Residency

## <a name="data-residency-commitments-available"></a>Data Residency Taahhütleri Kullanılabilir

### <a name="product-terms"></a>Ürün Koşulları

Gerekli Koşullar:

Kiracının Yerel Bölge Coğrafyası, Avrupa Birliği veya Birleşik Devletler dahil bir kaydolma ülkesi vardır.

_Geçerli dil için lütfen Gizlilik ve Güvenlik Ürün Koşulları <a href="https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all" target="_blank">**web sayfasına**</a> bakın ve "Core Online Services için Bekleyen Müşteri Verilerinin Konumu" başlıklı bölümü görüntüleyin._

**Taahhüt:**

>[!NOTE]
>Müşteri Avustralya, Brezilya, Kanada, Avrupa Birliği, Fransa, Almanya, Hindistan, Japonya, Norveç, Katar, Güney Afrika, Güney Kore, İsveç, İsviçre, Birleşik Arap Emirlikleri, Birleşik Krallık veya Birleşik Devletler kiracısını sağlarsa, Microsoft şu Müşteri Verilerini yalnızca bu Coğrafi Bölgede bekleyen olarak depolar: Exchange Online  posta kutusu içeriği (e-posta gövdesi, takvim girdileri ve e-posta eklerinin içeriği)

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. Kiracının _, Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi vardır.
1. Kiracı, kiracıdaki tüm kullanıcılar için geçerli bir Gelişmiş Data Residency aboneliğine sahiptir
1. Exchange Online aboneliği müşteri verileri Yerel Coğrafya veya Genişletilmiş Yerel Coğrafya'da sağlanır

**Taahhüt:**

Ürün Koşulları aracılığıyla sağlanan belirli taahhütleri anlamak için lütfen [ADR taahhüdü sayfasına](m365-dr-commitments.md#exchange-online) bakın. Kabul edilen verilere örnek olarak şunlar verilebilir: kullanıcı posta kutuları, kaynak posta kutuları ve arşiv posta kutuları dahil olmak üzere tüm posta kutusu türleri.

### <a name="multi-geo-add-on"></a>Multi-Geo eklentisi

Gerekli Koşullar:

1. Kiracılar, _Uydu Coğrafya'ya_ atanan tüm kullanıcıları kapsayan geçerli bir Multi-Geo aboneliğine sahiptir.
1. Müşterinin etkin bir Kurumsal Anlaşma olması gerekir.
1. Satın alınan toplam Multi-Geo birimi, kiracıdaki toplam uygun koltukların %5'inden büyük olmalıdır.

**Taahhüt:**

Müşteriler, Desteklenen posta kutusu türüne Multi-Geo tarafından desteklenen bir Uydu Coğrafya atayabilir. Ayrıntılar için [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) sayfasının Microsoft 365 Multi-Geo kullanılabilirlik bölümüne bakın. Ürün koşulları tarafından tanımlanan posta kutusu için Office 365 Hizmetleri için Bekleyen Veriler, atanan Uydu Coğrafyasında depolanmalıdır. Desteklenen posta kutusu türleri Exchange Online kullanıcı birincil ve arşiv posta kutularını, kaynak posta kutularını, Microsoft 365 Grubu posta kutularını ve paylaşılan posta kutularını içerir.

## <a name="multi-geo-capabilities-in-exchange-online"></a>Exchange Online'da Multi-Geo Capabilities

Müşteriler bir kullanıcıya Multi-Geo tarafından desteklenen bir _Uydu Coğrafya_ atayabilir. Ayrıntılar için [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) sayfasının Microsoft 365 Multi-Geo kullanılabilirlik bölümüne bakın. Kullanıcının Office 365 Hizmetleri için Bekleyen Verileri, ürün koşulları tarafından tanımlandığı şekilde atanan _Uydu Coğrafyasında_ depolanmalıdır. Bu, kullanıcı posta kutuları, kaynak posta kutuları, Microsoft 365 Grup posta kutuları, paylaşılan posta kutuları ve arşiv posta kutuları dahil olmak üzere tüm Exchange Online posta kutularını içerir.

Posta kutularını _Uydu Coğrafya_ konumlarına şu şekilde yerleştirebilirsiniz:

1. Doğrudan _Uydu Coğrafya_ konumunda yeni bir Exchange Online posta kutusu oluşturma.
1. Kullanıcının tercih edilen veri konumunu değiştirerek mevcut bir Exchange Online posta kutusunu _Uydu Coğrafya_ konumuna taşıma.
1. Bir şirket içi Exchange kuruluşundan doğrudan _Uydu Coğrafya_ konumuna posta kutusu ekleme.

### <a name="mailbox-placement-and-moves"></a>Posta kutusu yerleşimi ve taşımaları

Microsoft önkoşul Multi-Geo yapılandırma adımlarını tamamladıktan sonra, Exchange Online Azure AD'deki kullanıcı nesnelerinde PreferredDataLocation özniteliğini kabul eder.
Exchange Online, AAD'deki PreferredDataLocation özelliğini Exchange Online dizin hizmetindeki MailboxRegion özelliğiyle eşitler. MailboxRegion değeri, kullanıcı posta kutularının ve ilişkili arşiv posta kutularının yerleştirileceği Makro _Bölgesi Coğrafyasını veya Yerel Bölge Coğrafyasını_ belirler. Kullanıcının birincil posta kutusunu ve arşiv posta kutularını farklı _Coğrafya_ konumlarında bulunacak şekilde yapılandırmak mümkün değildir. Kullanıcı nesnesi başına yalnızca bir _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ yapılandırılabilir.

- PreferredDataLocation, mevcut posta kutusu olan bir kullanıcıda yapılandırıldığında, posta kutusu yeniden konumlandırma kuyruğuna alınır ve otomatik olarak belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası'na_ taşınır.
- PreferredDataLocation mevcut posta kutusu olmayan bir kullanıcıda yapılandırıldığında, posta kutusunu sağladığınızda, belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası'na_ sağlanır.
- Bir kullanıcıda PreferredDataLocation belirtilmediğinde, posta kutusunu sağladığınızda Birincil _Sağlanan Coğrafya'da_ sağlanır.
- PreferredDataLocation kodu yanlışsa (örneğin NAM yerine NAN yazım hatası), posta kutusu _Birincil Sağlanan Coğrafya'da_ sağlanır.

>[!NOTE]
>Çoklu coğrafi özellikler ve Skype Kurumsal Çevrimiçi olarak barındırılan çevrimiçi toplantılar, hizmetleri bulmak için kullanıcı nesnelerinde PreferredDataLocation özelliğini kullanır. Bölgesel olarak barındırılan toplantılar için kullanıcı nesnelerinde PreferredDataLocation değerlerini yapılandırırsanız, Microsoft 365 kiracısında Multi-Geo etkinleştirildikten sonra bu kullanıcıların posta kutusu otomatik olarak belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyasına_ taşınır.

### <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Exchange Online'da Multi-Geo için özellik sınırlamaları

- Exchange yönetim merkezinde (EAC) kullanılabilen güvenlik ve uyumluluk özellikleri (örneğin, denetim ve eBulma) Multi-Geo kuruluşlarında kullanılamaz. Bunun yerine, güvenlik ve uyumluluk özelliklerini yapılandırmak için Microsoft 365 Güvenlik & Uyumluluk Merkezi'ni kullanmanız gerekir.
- Mac için Outlook kullanıcılar, posta kutularını yeni bir _Coğrafya_ konumuna taşırken Çevrimiçi Arşiv klasörüne geçici erişim kaybıyla karşılaşabilir. Bu koşul, kullanıcının birincil posta kutuları ve arşiv posta kutuları farklı _Coğrafya_ konumlarında olduğunda oluşur, çünkü coğrafi konumlar arası posta kutusu taşıma işlemleri farklı zamanlarda tamamlanabilir.
- Kullanıcılar, Web üzerinde Outlook(eski adıyla Outlook Web App veya OWA) _coğrafya konumlarında_ posta kutusu klasörlerini paylaşamaz. Örneğin, Avrupa Birliği'ndeki bir kullanıcı Birleşik Devletler bulunan bir posta kutusunda paylaşılan klasörü açmak için Web üzerinde Outlook kullanamaz. Ancak Web üzerinde Outlook kullanıcıları, başka bir kişinin posta kutusunu Outlook Web App ayrı bir tarayıcı penceresinde açma başlığı altında açıklandığı gibi ayrı bir tarayıcı penceresi kullanarak farklı _Coğrafya_ konumlarındaki diğer posta kutularını açabilir.

>[!NOTE]
>Coğrafi konumlar arası posta kutusu klasör paylaşımı, Windows üzerinde Outlook'ta desteklenir.

- Ortak klasörler Multi-Geo kuruluşlarında desteklenir. Ancak, ortak klasörler _Birincil Sağlanan Coğrafya_ konumunda kalmalıdır. Ortak klasörleri uydu coğrafi konumlarına taşıyamazsınız.
- Multi-Geo ortamında, coğrafi bölgeler arası posta kutusu denetimi desteklenmez. Örneğin, kullanıcıya farklı bir _Coğrafya_ konumundaki paylaşılan posta kutusuna erişim izinleri atanmışsa, bu kullanıcı tarafından gerçekleştirilen posta kutusu eylemleri paylaşılan posta kutusunun posta kutusu denetim günlüğüne kaydedilmez. Exchange yöneticisi denetim olayları da yalnızca varsayılan konum için kullanılabilir. Daha fazla bilgi için bkz. Posta kutusu denetimini yönetme.

### <a name="administering-exchange-multi-geo"></a>Exchange Multi-Geo Yönetimi

#### <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Multi-Geo ortamında Exchange Online posta kutularını yönetme

Exchange Online PowerShell, Microsoft 365 ortamınızdaki Multi-Geo özelliklerini görüntülemek ve yapılandırmak için gereklidir. Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

Kullanıcı nesnelerinde **PreferredDataLocation** özelliğini görmek için v1.x'te [Microsoft Azure Active Directory PowerShell Modülü](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 veya üzeri gerekir. AAD Connect aracılığıyla AAD'ye eşitlenen kullanıcı nesnelerinin **PreferredDataLocation** değeri AAD PowerShell aracılığıyla doğrudan değiştirilemez. Yalnızca bulut kullanıcı nesneleri AAD PowerShell aracılığıyla değiştirilebilir. Azure AD PowerShell'e bağlanmak için bkz. [PowerShell'e bağlanma](connect-to-microsoft-365-powershell.md).

Exchange Online Multi-Geo ortamlarda, kiracınıza Coğrafi Bölgeler eklemek için el ile herhangi bir adım uygulamanız gerekmez. Çok coğrafi konumun Exchange Online için hazır olduğunu belirten İleti Merkezi gönderisini aldıktan sonra, tüm kullanılabilir Coğrafyalar kullanımınız için hazır ve yapılandırılır.

#### <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Exchange Online PowerShell kullanarak coğrafi konuma doğrudan bağlanma

Exchange Online PowerShell genellikle _Birincil Sağlanan Coğrafya_ konumuna bağlanır. Ancak doğrudan _Uydu Coğrafya_ konumlarına da bağlanabilirsiniz. Performans geliştirmeleri nedeniyle, yalnızca bu konumdaki kullanıcıları yönetirken _doğrudan Uydu Coğrafya_ konumuna bağlanmanızı öneririz.

Exchange Online PowerShell modülünü yükleme ve kullanma gereksinimleri, **[Exchange Online PowerShell modülünü yükleme ve koruma](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-module)** başlığında açıklanmıştır.

Exchange Online PowerShell'i belirli bir _Coğrafya_ konumuna bağlamak için ConnectionUri parametresi normal bağlantı yönergelerinden farklıdır. Komutların ve değerlerin geri kalanı aynıdır.

Özellikle, ConnectionUri değerinin sonuna ?email=\<emailaddress\> değerini eklemeniz gerekir. \<emailaddress\>hedef _Coğrafya_ konumundaki **herhangi bir** posta kutusunun e-posta adresidir. Bu posta kutusuna ilişkin izinleriniz veya kimlik bilgilerinizle olan ilişkinin bir faktörü yoktur; e-posta adresi Exchange Online PowerShell'e nereye bağlanacaklarını söyler.
  
Microsoft 365 veya Microsoft 365 GCC müşterilerinin genellikle Exchange Online PowerShell'e bağlanmak için _ConnectionUri_ parametresini kullanması gerekmez. Ancak, belirli bir _Coğrafya_ konumuna bağlanmak için değerde ?email=\<emailaddress\> kullanabilmeniz için ConnectionUri parametresini kullanmanız gerekir.
  
#### <a name="connect-to-a-_geography_-location-in-exchange-online-powershell"></a>Exchange Online PowerShell'de _Coğrafya_ konumuna bağlanma

Aşağıdaki bağlantı yönergeleri, çok faktörlü kimlik doğrulaması (MFA) için yapılandırılmış veya yapılandırılmamış hesaplarda çalışır.

1. Windows PowerShell bir pencerede aşağıdaki komutu çalıştırarak EXO V2 modülünü yükleyin:

  ```powershell
   Import-Module ExchangeOnlineManagement
   ```
  
1. Aşağıdaki örnekte, admin@contoso.onmicrosoft.com yönetici hesabıdır ve hedef coğrafi konum, posta kutusunun olga@contoso.onmicrosoft.com bulunduğu yerdir.
  
  ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```
  
1. Görüntülenen istemde admin@contoso.onmicrosoft.com parolasını girin. Hesap MFA için yapılandırılmışsa, güvenlik kodunu da girmeniz gerekir.
  
#### <a name="view-the-available-_geography_-locations-that-are-configured-in-your-exchange-online-organization"></a>Exchange Online kuruluşunuzda yapılandırılan kullanılabilir _Coğrafya_ konumlarını görüntüleme

Microsoft 365 _Multi-Geo'da yapılandırılmış Coğrafya_ konumlarının listesini görmek için PowerShell'Exchange Online aşağıdaki komutu çalıştırın:

  ```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```
  
#### <a name="view-the-_primary-provisioned-geography_-location-for-your-exchange-online-organization"></a>Exchange Online kuruluşunuz için _Birincil Sağlanan Coğrafya_ konumunu görüntüleme

Kiracınızın _Birincil Sağlanan Coğrafya_ konumunu görüntülemek için PowerShell'Exchange Online aşağıdaki komutu çalıştırın:

 ```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

#### <a name="find-the-_geography_-location-of-a-mailbox"></a>Posta kutusunun _Coğrafya_ konumunu bulma

Exchange Online PowerShell'deki **Get-Mailbox** cmdlet'i posta kutularında aşağıdaki çok coğrafi ilişkili özellikleri görüntüler:

- **Veritabanı**: Veritabanı adının ilk 3 harfi, posta kutusunun şu anda nerede olduğunu bildiren _Coğrafya_ koduna karşılık gelir. Çevrimiçi Arşiv Posta Kutuları için **ArchiveDatabase** özelliği kullanılmalıdır.
- **MailboxRegion**: Yönetici tarafından ayarlanan _Coğrafya_ konum kodunu belirtir (Azure AD PreferredDataLocation öğesinden eşitlenir).
- **MailboxRegionLastUpdateTime**: MailboxRegion'ın en son ne zaman güncelleştirildiğini gösterir (otomatik veya el ile).

Posta kutusunun bu özelliklerini görmek için aşağıdaki söz dizimini kullanın:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

  Örneğin, posta kutusu chris@contoso.onmicrosoft.com _coğrafya_ konumu bilgilerini görmek için aşağıdaki komutu çalıştırın:

  ```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

  Komutun çıkışı şöyle görünür:

  ```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```
  
 > [!NOTE]
 >Veritabanı adındaki _Coğrafya_ konum kodu **MailboxRegion** değeriyle eşleşmiyorsa, posta kutusu otomatik olarak yeniden konumlandırma kuyruğuna alınır ve **MailboxRegion** değeri tarafından belirtilen _Coğrafya_ konumuna taşınır (Exchange Online bu özellik değerleri arasında uyuşmazlık arar).

#### <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Mevcut yalnızca bulut posta kutusunu belirli bir coğrafi konuma taşıma

Yalnızca bulut kullanıcısı, AAD Connect aracılığıyla kiracıyla eşitlenmemiş bir kullanıcıdır. Bu kullanıcı doğrudan Azure AD oluşturuldu. Windows PowerShell için Azure AD Modülündeki  **Get-MsolUser** ve **Set-MsolUser** cmdlet'lerini kullanarak yalnızca bulut kullanıcısının posta kutusunun depolanacağı Coğrafya konumunu görüntüleyin veya belirtin.

Kullanıcının **PreferredDataLocation** değerini görüntülemek için powershell Azure AD şu söz dizimini kullanın:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Örneğin, kullanıcı michelle@contoso.onmicrosoft.com **PreferredDataLocation** değerini görmek için aşağıdaki komutu çalıştırın:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Yalnızca bulutta bulunan bir kullanıcı nesnesinin **PreferredDataLocation** değerini değiştirmek için PowerShell Azure AD de aşağıdaki söz dizimini kullanın:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Örneğin, kullanıcı michelle@contoso.onmicrosoft.com **PreferredDataLocation** değerini Avrupa Birliği (EUR) coğrafi konumuna ayarlamak için aşağıdaki komutu çalıştırın:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Daha önce belirtildiği gibi, şirket içi Active Directory eşitlenmiş kullanıcı nesneleri için bu yordamı kullanamazsınız. Active Directory'de **PreferredDataLocation** değerini değiştirmeniz ve AAD Connect kullanarak eşitlemeniz gerekir. Daha fazla bilgi için bkz. [Azure Active Directory Connect eşitlemesi: Microsoft 365 kaynakları için tercih edilen veri konumunu yapılandırma](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Posta kutusunun yeni bir coğrafi konuma taşınma süresi çeşitli faktörlere bağlıdır:
>
>   - Posta kutusunun boyutu ve türü.
>   - Taşınan posta kutularının sayısı.
>   - Taşıma kaynaklarının kullanılabilirliği.

#### <a name="move-an-inactive-mailbox-to-a-specific-_geography_"></a>Etkin olmayan posta kutusunu belirli bir _Coğrafyaya_ taşıma
  
Uyumluluk amacıyla korunan etkin olmayan posta kutularını (örneğin, Dava Tutmadaki posta kutuları) **PreferredDataLocation** değerlerini değiştirerek taşıyamazsınız. Etkin olmayan posta kutusunu farklı bir _Coğrafyaya_ taşımak için aşağıdaki adımları uygulayın:

1. Etkin olmayan posta kutusunu kurtarın. Yönergeler için bkz [. Etkin olmayan posta kutusunu kurtarma](/microsoft-365/compliance/recover-an-inactive-mailbox).

1. Yönetilen Klasör Yardımcısı'nın kurtarılan posta kutusunu işlemesini önlemek için yerine posta kutusunun \<MailboxIdentity\> adını, diğer adını, hesabını veya e-posta adresini yazın ve [Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki komutu çalıştırın:

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

1. Kurtarılan posta kutusuna **bir Exchange Online Plan 2** lisansı atayın. Bu adım, posta kutusunu Dava Tutma'ya geri yerleştirmek için gereklidir. Yönergeler için bkz. [Kullanıcılara lisans atama](/microsoft-365/admin/manage/assign-licenses-to-users).

1. Önceki bölümde açıklandığı gibi posta kutusunda **PreferredDataLocation** değerini yapılandırın.

1. Posta kutusunun yeni coğrafi konuma taşındığını onayladıktan sonra, kurtarılan posta kutusunu Dava Tutma'ya geri yerleştirin. Yönergeler için bkz [. Dava Tutma'ya posta kutusu yerleştirme](/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).

1. Dava Tutma'nın yerinde olduğunu doğruladıktan sonra, Yönetilen Klasör Yardımcısı'nın posta kutusunun adını, diğer adını, hesabını veya e-posta adresini değiştirip \<MailboxIdentity\> [Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki komutu çalıştırarak posta kutusunu yeniden işlemesine izin verin:

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

1. Posta kutusuyla ilişkili kullanıcı hesabını kaldırarak posta kutusunu yeniden devre dışı bırak. Yönergeler için bkz. [Kuruluşunuzdan kullanıcı silme](/admin/add-users/delete-a-user). Bu adım, diğer kullanımlar için Exchange Online Plan 2 lisansını da yayınlar.

**Not**: Etkin olmayan bir posta kutusunu farklı bir coğrafi konuma taşıdığınızda, içerik arama sonuçlarını veya eski coğrafi konumdan posta kutusunda arama yapma özelliğini etkileyebilirsiniz. Daha fazla bilgi için bkz [. Multi-Geo ortamlarında içerik arama ve dışarı aktarma](/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).
  
#### <a name="create-new-cloud-mailboxes-in-a-specific-_geography_-location"></a>Belirli bir _Coğrafya_ konumunda yeni bulut posta kutuları oluşturma

Belirli bir _Coğrafi_ konumda yeni bir posta kutusu oluşturmak için şu adımlardan birini uygulamanız gerekir:

- Exchange Online'de posta kutusunu _oluşturmadan önce_[, önceki Yalnızca bulut posta kutusunu belirli bir _Coğrafi_ konuma taşıma](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) bölümünde açıklandığı gibi **PreferredDataLocation** değerini yapılandırın. Örneğin, lisans atamadan önce kullanıcıda **PreferredDataLocation** değerini yapılandırın.

- **PreferredDataLocation** değerini ayarladığınız anda bir lisans atayın.

Belirli bir _Coğrafi_ konumda yeni bir yalnızca bulut lisanslı kullanıcı (AAD Connect eşitlenmemiş) oluşturmak için powershell Azure AD aşağıdaki söz dizimini kullanın:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

Bu örnekte Elizabeth Brunner için aşağıdaki değerlerle yeni bir kullanıcı hesabı oluşturulur:

- Kullanıcı asıl adı: ebrunner@contoso.onmicrosoft.com
- Ad: Elizabeth
- Soyadı: Brunner
- Görünen ad: Elizabeth Brunner
- Parola: rastgele oluşturulur ve komutun sonuçlarında gösterilir ( _çünkü Password_ parametresini kullanmıyoruz)
- Lisans: `contoso:ENTERPRISEPREMIUM` (E5)
- Konum: Avustralya (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Azure AD PowerShell'de yeni kullanıcı hesapları oluşturma ve LicenseAssignment değerlerini bulma hakkında daha fazla bilgi için bkz. [PowerShell ile kullanıcı hesapları oluşturma](create-user-accounts-with-microsoft-365-powershell.md) ve [PowerShell ile lisansları ve hizmetleri görüntüleme](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Bir posta kutusunu etkinleştirmek için Exchange Online PowerShell kullanıyorsanız ve posta kutusunun doğrudan **PreferredDataLocation** içinde belirtilen _Coğrafi_ konumda oluşturulması gerekiyorsa, doğrudan bulut hizmetinde **Enable-Mailbox** veya **New-Mailbox** gibi bir Exchange Online cmdlet'i kullanmanız gerekir. Şirket içi Exchange PowerShell'de **Enable-RemoteMailbox** cmdlet'ini kullanırsanız, posta kutusu _Birincil Sağlanan Coğrafya_ konumunda oluşturulur.

#### <a name="onboard-existing-on-premises-mailboxes-in-a-specific-_geography_-location"></a>Mevcut şirket içi posta kutularını belirli bir _Coğrafya_ konumuna ekleme

[EAC'deki Geçiş panosu](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) ve Exchange Online PowerShell'deki [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet'i dahil olmak üzere bir posta kutusunu şirket içi Exchange kuruluşundan Exchange Online geçirmek için standart ekleme araçlarını ve işlemlerini kullanabilirsiniz.

İlk adım, eklenecek her posta kutusu için bir kullanıcı nesnesi olduğunu ve Azure AD doğru **PreferredDataLocation** değerinin yapılandırıldığını doğrulamaktır. Ekleme araçları **PreferredDataLocation** değerine saygı gösterir ve posta kutularını doğrudan belirtilen coğrafi konuma geçirir.

Alternatif olarak, Exchange Online PowerShell'deki [New-MoveRequest](/powershell/module/exchange/new-moverequest) cmdlet'ini kullanarak posta kutularını doğrudan belirli bir _Coğrafi_ konuma eklemek için aşağıdaki adımları kullanabilirsiniz.

1. Eklenecek her posta kutusu için kullanıcı nesnesinin mevcut olduğunu ve **PreferredDataLocation** öğesinin Azure AD istenen değere ayarlandığını doğrulayın. **PreferredDataLocation** değeri, Exchange Online karşılık gelen posta kullanıcı nesnesinin **MailboxRegion** özniteliğiyle eşitlenir.

1. Bu konunun önceki bölümlerinde yer alan bağlantı yönergelerini kullanarak doğrudan belirli _Uydu Coğrafya_ konumuna bağlanın.

1. Exchange Online PowerShell'de, aşağıdaki komutu çalıştırarak bir değişkende posta kutusu geçişi gerçekleştirmek için kullanılan şirket içi yönetici kimlik bilgilerini depolayın:

   ```powershell
   $RC = Get-Credential
   ```

1. Exchange Online PowerShell'de aşağıdaki örneğe benzer yeni bir **New-MoveRequest** oluşturun:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

1. Şirket içi Exchange'den şu anda bağlı olduğunuz uydu coğrafi konumuna geçirmeniz gereken her posta kutusu için 4. adımı yineleyin.

1. Başka posta kutularını farklı uydu coğrafi konumlarına geçirmeniz gerekiyorsa, her bir konum için 2 ile 4 arasındaki adımları yineleyin.

## <a name="multi-geo-reporting"></a>Multi-Geo raporlama
  
> [!NOTE]
> Çoklu coğrafi raporlama özelliği şu anda Önizleme aşamasındadır, tüm kuruluşlarda kullanılamaz ve değiştirilebilir.

Microsoft 365 yönetim merkezi'daki **Multi-Geo Kullanım Raporları**_, coğrafi_ konuma göre kullanıcı sayısını görüntüler. Rapor geçerli ayın kullanıcı dağıtımını görüntüler ve son 6 aya ilişkin geçmiş verileri sağlar.

## <a name="migration"></a>Geçiş

Her kullanıcının tek bir _kiracı için yeni_ veri merkezine taşınması zaman aldığından, taşıma sırasında bazı kullanıcılar eski veri merkezi Coğrafyası'nda, diğerleri ise yeni  veri merkezi _Coğrafyası'nda_ olur. Bu, birden çok posta kutusuna erişmeyi içeren bazı özelliklerin, taşıma işleminin bir döneminde tam olarak çalışmayabileceği ve bunun da haftalar sürebileceği anlamına gelir. Bu özellikler aşağıdaki bölümlerde açıklanmıştır.

### <a name="open-shared-folder-in-outlook-web-access"></a>Outlook Web Access'te "Paylaşılan Klasör" seçeneğini açma

Bazı kullanıcılar, "Paylaşılan Klasör" özelliğini kullanarak Outlook Web Access'te başka bir posta kutusundan (kullanıcının okuma veya yazma izinlerine sahip olduğu) paylaşılan posta klasörünü açar. Aşağıdaki tabloda, posta kutusu taşıma sırasında paylaşılan klasörlere erişimin nasıl çalıştığı açıklanmaktadır. Paylaşılan posta kutusuna tam izinlere sahip kullanıcıların taşıma sırasında Outlook Web Access'i kullanarak posta kutusunu açabileceğini lütfen unutmayın.

| Yapılandırma | Açıklama |
|:-----|:-----|
|Kullanıcının başka bir posta kutusu için posta kutusu klasörü izni var  <br/> |Potansiyel olarak sınırlı.  <br/> Kiracı taşıma sırasında A Kullanıcısı ve B Posta Kutusu aynı _Coğrafyada_ değilse, A Kullanıcısı B Posta Kutusu'nun B Posta Kutusu'nda yalnızca belirli bir klasöre izni varsa, Outlook Web Access'te B Posta Kutusu klasörünü açamaz.  <br/> Paylaşılan klasör eklemek için sol gezinti panelinde kullanıcı adına sağ tıklayın ve **Paylaşılan klasör ekle'yi** seçin.  <br/> |
|Başka bir posta kutusuna tam posta kutusu izni olan kullanıcı  <br/> |Tam olarak desteklenir.  <br/> A Kullanıcısının B Posta Kutusu için "Tam Erişim" izni varsa, A Kullanıcısı Outlook Web Access'in sol gezinti panelinde paylaşılan klasöre tıklayarak B Posta Kutusu'nun gösterildiği bir pencere açabilir.  Kullanıcı, taşıma sırasında herhangi bir olumsuz etki olmadan Outlook Web Access'i kullanarak paylaşılan posta kutusunu açabilir. Sınırlama yalnızca posta kutusunda klasör düzeyinde paylaşım için geçerlidir.

Exchange Online sırasında Microsoft 365'e e-posta verilerini geçirme işlemi yaygın bir senaryodur ve desteklenir. Veri merkezi coğrafi bölgeleri arasında bulut geçişi, şirket içi bulut posta kutusu geçişlerini engellemez.

### <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

Gerçek veri konumunu Kiracı Yönetici Merkezi'nde bulabilirsiniz.  Kiracı yöneticisi olarak, Yönetici->Ayarları->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek kaydedilmiş veriler için gerçek veri konumunu bulabilirsiniz.
