---
title: Kiracı İzin Ver/Engelle Listesini kullanarak dosyalara izin verme veya dosyaları engelleme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Yöneticiler, Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde dosyalara izin verme veya dosyaları engelleme hakkında bilgi edinebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 415dc4605c0e519052c3f03e6843cf7a41bd3a56
ms.sourcegitcommit: c81f6c39ed39d017f9d7c5f13148cd8d17b25c3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67393089"
---
# <a name="allow-or-block-files-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak dosyalara izin verme veya dosyaları engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bu makalede, Kiracı İzin Ver/Engelle Listesinde bulunan dosya izin verme ve engelleme girdilerinin nasıl yönetileceğini açıklar. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

Microsoft 365 Defender Portalı'nda veya Exchange Online PowerShell'de dosyalar için izin verme ve engelleme girdilerini yönetirsiniz.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. **Doğrudan Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın<https://security.microsoft.com/tenantAllowBlockList>. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell). Tek başına EOP PowerShell'e bağlanmak için bkz. [Exchange Online Protection PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Dosyanın SHA256 karma değerini kullanarak dosyaları belirtirsiniz. Windows'da bir dosyanın SHA256 karma değerini bulmak için komut isteminde aşağıdaki komutu çalıştırın:

  ```DOS
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Örnek değer: `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. Algısal karma (pHash) değerleri desteklenmez.

- Dosyalar için izin verilen girdi sayısı üst sınırı 500, blok girdisi sayısı üst sınırı 500'dir (toplam 1000 dosya girdisi).

- Dosya girdisine en fazla 64 karakter girebilirsiniz.

- Bir girdinin 30 dakika içinde etkin olması gerekir, ancak girdinin etkin olması 24 saat kadar sürebilir.

- Bu makaledeki yordamları gerçekleştirmeden önce Exchange Online'de izinlerin atanmış olması gerekir:
  - Kiracı İzin Ver/Engelle Listesinden değer eklemek ve kaldırmak için aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:
    - **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol grubu (**Güvenlik yöneticisi rolü**)
    - **Güvenlik İşleci** rol grubu (**Kiracı AllowBlockList Manager**).
  - Kiracı İzin Ver/Engelle Listesi'ne salt okunur erişim için aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:
    - **Genel Okuyucu**  rol grubu
    - **Güvenlik Okuyucusu** rol grubu
    - **Yalnızca Görüntüle yapılandırma** rol grubu

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  **Notlar**:

  - kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri *ve* izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

## <a name="create-block-entries-for-files"></a>Dosyalar için blok girdileri oluşturma

Dosyalar için blok girdileri oluşturmak için aşağıdaki seçeneklere sahipsiniz:

- [Microsoft 365 Defender portalındaki Gönderimler sayfası](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-submissions-portal)
- [Microsoft 365 Defender portalında](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-tenant-allowblock-list) veya [PowerShell'de](#use-powershell-to-create-block-entries-for-files-in-the-tenant-allowblock-list) Kiracı İzin Ver/Engelle Listesi

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-submissions-portal"></a>Gönderimler portalında dosyalar için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanma

Dosyaları **engellenmiş olmalıdır (Hatalı negatif)** olarak raporlamak için konumundaki <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullandığınızda, Kiracı İzin Ver/Engelle Listesi'nde dosya için bir blok girdisi eklemek üzere **Bu dosyayı engelle'yi** seçebilirsiniz.

Yönergeler için bkz. [Sorgulanabilir e-posta eklerini Microsoft'a bildirme](admin-submission.md#report-questionable-email-attachments-to-microsoft).

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'ndeki dosyalar için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Dosyalar için blok girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturursunuz.

> [!NOTE]
> Email bu engellenen dosyaları içeren iletiler *kötü amaçlı yazılım* olarak engellenir.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **Dosyalar** sekmesini seçin.

3. **Dosyalar** sekmesinde Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

4. Görüntülenen **Dosyaları engelle** açılır öğesinde aşağıdaki ayarları yapılandırın:

   - **Dosya karmaları ekleme**: Satır başına en fazla 20 SHA256 karma değeri girin.

   - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
     - **1 gün**
     - **7 gün**
     - **30 gün**
     - **Hiçbir zaman süresi dolmaz**
     - **Belirli bir tarih**: En büyük değer bugünden itibaren 90 gündür.

   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

5. İşiniz bittiğinde **Ekle'ye** tıklayın.

#### <a name="use-powershell-to-create-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki dosyalar için blok girdileri oluşturmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Bu örnek, belirtilen dosyalar için hiçbir zaman süresi dolmamış bir blok dosyası girdisi ekler.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-files-in-the-submissions-portal"></a>Gönderimler portalında dosyalar için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Dosyalar için izin verme girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturamazsınız. Bunun yerine, iletiyi hatalı pozitif olarak raporlamak için adresinde <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullanırsınız. Yönetici gönderimleri hakkında daha fazla bilgi için bkz [. Şüpheli istenmeyen postaları, kimlik avı, URL'leri, engellenen meşru e-postaları ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanma](admin-submission.md).

**Dosyayı Gönderiler** sayfasında hatalı pozitif olarak raporlamak, Kiracı İzin Ver/Engelle Listesi'nde dosya için bir izin girdisi ekler.

> [!IMPORTANT]
> Microsoft sizin için izin girdilerini yönettiği için, dosyalar için gereksiz izin verme girdileri kaldırılır. Bu davranış, kuruluşunuzu korur ve yanlış yapılandırılmış izin verme girdilerinin önlenmesine yardımcı olur. Karara katılmıyorsanız, bir dosyanın neden hala kötü kabul edildiğini saptamaya yardımcı olmak için bir destek olayı açmanız gerekebilir.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderiler** sayfasında **ekleri Email** sekmesini seçin.

3. **Email ekler** sekmesinde Analiz için Microsoft'a Gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderim türünü seçin**: **Ekin seçili Email** değeri doğrulayın.

   - **Dosya**: Dosyalara **gözat'a** tıklayarak göndermek istediğiniz dosyayı bulun ve seçin.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmemeli (Hatalı pozitif)** seçeneğini belirleyin ve ardından aşağıdaki ayarları yapılandırın:

     - **Bu dosyaya izin ver**: Bu ayarı ![aç Aç.](../../media/scc-toggle-on.png).

         - **İzin ver girdisini kaldır:** Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **Belirli bir tarih**: En yüksek değer bugünden itibaren 30 gündür.

         - **Giriş notuna izin ver**: Bu dosyaya neden izin kullandığınızla ilgili isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

   :::image type="content" source="../../media/admin-submission-file-allow.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı pozitif (iyi) bir e-posta eki gönderin." lightbox="../../media/admin-submission-file-allow.png":::

5. Birkaç dakika sonra İzin Ver girişi **Kiracı İzin Ver/Engelle Listesi** sayfasındaki **Dosyalar** sekmesinde görünür.

> [!NOTE]
> Dosyayla yeniden karşılaşıldığında, [Güvenli Ekler](safe-attachments.md) patlama veya dosya saygınlığı denetimleri için gönderilmez ve diğer tüm dosya tabanlı filtreler atlanır. Posta akışı sırasında, dosyayı içeren iletiler filtreleme yığınında diğer dosya dışı denetimleri geçirirse, iletiler teslim edilecek.

## <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki dosyalar için izin ver veya engelle girdilerini görüntülemek için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Dosyalar** sekmesini seçin. Aşağıdaki sütunlar kullanılabilir:

   - **Değer**: Dosya karması.
   - **Eylem**: **İzin Ver** veya **Engelle** değeri.
   - **Değiştiren**
   - **Son güncelleştirme**
   - **Kaldırma tarihi**: Son kullanma tarihi.
   - **Notlar**

   Artan veya azalan düzende sıralamak için sütun başlığına tıklayabilirsiniz.

   Grup simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Sonuçları **Yok** veya **Eyleme** göre gruplandırmak için **gruplandırın**.

   Ara simgesine tıklayın ![.](../../media/m365-cc-sc-search-icon.png) **Arama** yapın, bir değerin tamamını veya bir kısmını girin ve ardından belirli bir değeri bulmak için ENTER tuşuna basın. İşiniz bittiğinde Aramayı temizle simgesine tıklayın ![.](../../media/m365-cc-sc-close-icon.png) **Aramayı temizle'yi seçin**.

   Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Sonuçları** filtrelemek için filtreleyin. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:

   - **Eylem**: **İzin Ver** ve **Engelle**.
   - **Süresi hiç dolmaz**: ![İki durumlu düğmeyi açın.](../../media/scc-toggle-on.png) veya ![Kapat'a geçin.](../../media/scc-toggle-off.png)
   - **Son güncelleştirme**: Başlangıç ve **Bitiş** **tarihleri'ne** tıklayın.
   - **Kaldırılacak yer**: Kimden ve **Bitiş** **tarihleri'ne** tıklayın.

   İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

### <a name="use-powershell-to-view-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki dosyalar için izin ver veya engelle girdilerini görüntülemek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType FileHash [-Allow] [-Block] [-Entry <FileHashValue>] [<-ExpirationDate Date | -NoExpiration>]
```

Bu örnek, tüm izin verilen ve engellenen dosyaları döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash
```

Bu örnek, belirtilen dosya karması değeri için bilgi döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Bu örnek, sonuçları engellenen dosyalara göre filtreler.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki dosyalar için izin ver veya engelle girdilerini değiştirmek için Microsoft 365 Defender portalını kullanın

Kiracı İzin Ver/Engelle listesinde bir izin ver veya engelle dosya girdisini değiştirdiğinizde, yalnızca son kullanma tarihini ve notları değiştirebilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Dosyalar** sekmesini seçin

3. **Dosyalar** sekmesinde, değiştirmek istediğiniz girdinin onay kutusunu seçin ve düzenle simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **Düzenle** düğmesi.

4. Görüntülenen **Dosyayı düzenle** açılır penceresinde aşağıdaki ayarlar kullanılabilir:

   - **Şunlardan sonra girişe izin ver** veya **Engelle girdisini kaldır**:
     - İzin verilen girişleri oluşturma tarihinden sonra en fazla 30 gün uzatabilirsiniz.
     - Blok girişlerini oluşturma tarihinden sonra en fazla 90 gün uzatabilir veya **Bunları Hiçbir zaman sona erme olarak ayarlayabilirsiniz**.

   - **İsteğe bağlı not**

   Bitirdiğinizde, **Kaydet**'i tıklatın.

> [!NOTE]
> Yalnızca girişlere izin ver için, onay kutusundan farklı bir satıra tıklayarak girdiyi seçerseniz Gönderimi görüntüle simgesini seçebilirsiniz ![.](../../media/m365-cc-sc-view-submission-icon.png) **Gönderiyi** , konumundaki **Gönderimler** sayfasına gitmek üzere görünen ayrıntılar açılır öğesinde <https://security.microsoft.com/reportsubmission>görüntüleyin.

### <a name="use-powershell-to-modify-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki dosyalar için izin ver veya engelle girdilerini değiştirmek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash> <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Bu örnek, belirtilen dosya bloğu girişinin sona erme tarihini değiştirir.

```powershell
Set-TenantAllowBlockListItems -ListType FileHash -Entries "27c5973b2451db9deeb01114a0f39e2cbcd2f868d08cedb3e210ab3ece102214" -ExpirationDate "9/1/2022"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-files-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden dosyalar için izin ver veya engelle girdilerini kaldırmak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Dosyalar** sekmesini seçin.

3. **Dosyalar** sekmesinde aşağıdaki adımlardan birini yapın:

   - Kaldırmak istediğiniz girdinin onay kutusunu seçin ve ardından Sil simgesine ![tıklayın.](../../media/m365-cc-sc-delete-icon.png) Görüntülenen **Sil** simgesi.
   - Onay kutusundan başka bir satıra tıklayarak kaldırmak istediğiniz girdiyi seçin. Görüntülenen ayrıntılar açılır listesinde Sil simgesine tıklayın ![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

4. Görüntülenen uyarı iletişim kutusunda **Sil'e** tıklayın.

> [!NOTE]
> Her onay kutusunu seçerek birden çok girdi seçebilir veya **Değer** sütun üst bilgisinin yanındaki onay kutusunu seçerek tüm girişleri seçebilirsiniz.

### <a name="use-powershell-to-remove-allow-or-block-entries-for-files-from-the-tenant-allowblock-list"></a>PowerShell kullanarak Kiracı İzin Ver/Engelle Listesinden dosyalar için izin ver veya engelle girdilerini kaldırın

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType FileHash <-Ids <Identity value> | -Entries <Value value>>
```

Bu örnek, belirtilen dosya bloğunu Kiracı İzin Ver/Engelle Listesinden kaldırır.

```powershell
Remove-TenantAllowBlockListItems -ListType FileHash -Entries "27c5973b2451db9deeb01114a0f39e2cbcd2f868d08cedb3e210ab3ece102214"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="related-articles"></a>İlgili makaleler

- [Şüpheli istenmeyen posta, kimlik avı, URL'ler, engellenen meşru e-postalar ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanın](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesinde e-postalara izin ver veya e-postaları engelle](allow-block-email-spoof.md)
- [Kiracı İzin Ver/Engelle Listesinde URL'lere izin ver veya url'leri engelle](allow-block-urls.md)
