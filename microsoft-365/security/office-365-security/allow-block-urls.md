---
title: Kiracı İzin Ver/Engelle Listesini kullanarak URL'lere izin verme veya URL’leri engelleme
f1.keywords:
- NOCSH
ms.author: chrisda
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: Yöneticiler, Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde URL'lere nasıl izin vereceğinizi veya url'leri nasıl engelleyebileceğinizi öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f29e410a6457a4810bf98436f912a57866978241
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495115"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak URL'lere izin verme veya URL’leri engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bu makalede, Kiracı İzin Ver/Engelle Listesinde bulunan URL izin verme ve engelleme girdilerinin nasıl oluşturulacağı ve yönetileceğini açıklanmaktadır. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

URL'ler için izin verme ve engelleme girdilerini Microsoft 365 Defender Portalı'nda veya Exchange Online PowerShell'de yönetirsiniz.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. **Doğrudan Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın<https://security.microsoft.com/tenantAllowBlockList>. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell). Tek başına EOP PowerShell'e bağlanmak için bkz. [Exchange Online Protection PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- URL girişi söz dizimi için, bu makalenin [devamında yer alan Kiracı İzin Ver/Engelle Listesi bölümünün URL söz dizimine](#url-syntax-for-the-tenant-allowblock-list) bakın.

- URL'ler için izin verilen girdi sayısı üst sınırı 500, blok girdisi sayısı üst sınırı 500'dir (toplam 1000 URL girişi).

- URL girdisine en fazla 250 karakter girebilirsiniz.

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

## <a name="create-block-entries-for-urls"></a>URL'ler için blok girdileri oluşturma

URL'ler için blok girdileri oluşturmak için aşağıdaki seçeneklere sahipsiniz:

- [Microsoft 365 Defender portalındaki Gönderimler sayfası](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal)
- [Microsoft 365 Defender portalında](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) veya [PowerShell'de](#use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) Kiracı İzin Ver/Engelle Listesi

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-submissions-portal"></a>Gönderimler portalında URL'ler için blok girişleri oluşturmak için Microsoft 365 Defender portalını kullanın

URL'leri **Engellenmiş Olması Gerekir (Hatalı negatif)** olarak bildirmek için adresinde <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullandığınızda, Kiracı İzin Ver/Engelle Listesi'nde URL için bir blok girişi eklemek üzere **Bu dosyayı engelle'yi** seçebilirsiniz.

Yönergeler için bkz. [Sorgulanabilir URL'leri Microsoft'a bildirme](admin-submission.md#report-questionable-urls-to-microsoft).

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

URL'ler için blok girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturabilirsiniz.

Bu engellenen URL'leri içeren Email iletiler *yüksek güvenilirlikli kimlik avı* olarak engellenir.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **URL'ler** sekmesini seçin.

3. **URL'ler** sekmesinde Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

4. Görüntülenen **URL'leri engelle** açılır penceresinde aşağıdaki ayarları yapılandırın:

   - **Joker karakterli URL'ler ekleme**: Satır başına en fazla 20 URL girin. URL girişlerinin söz dizimi hakkında ayrıntılı bilgi için, bu makalenin devamında [yer alan Kiracı İzin Ver/Engelle Listesi bölümünün URL söz dizimine](#url-syntax-for-the-tenant-allowblock-list) bakın.

   - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
     - **Hiçbir zaman süresi dolmaz**
     - **1 gün**
     - **7 gün**
     - **30 gün**
     - **Belirli bir tarih**: En büyük değer bugünden itibaren 90 gündür.

   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

5. İşiniz bittiğinde **Ekle'ye** tıklayın.

#### <a name="use-powershell-to-create-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için blok girdileri oluşturmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate <Date> | -NoExpiration> [-Notes <String>]
```

Bu örnek, contoso.com ve tüm alt etki alanları (örneğin, contoso.com ve xyz.abc.contoso.com) için bir blok URL girişi ekler. ExpirationDate veya NoExpiration parametrelerini kullanmadığımız için girdinin süresi 30 gün sonra dolar.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal"></a>Gönderimler portalında URL'ler için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

URL izin verme girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturamazsınız. Bunun yerine, iletiyi hatalı pozitif olarak raporlamak için adresinde <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullanırsınız. Yönetici gönderimleri hakkında daha fazla bilgi için bkz [. Şüpheli istenmeyen postaları, kimlik avı, URL'leri, engellenen meşru e-postaları ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanma](admin-submission.md).

**Gönderimler** sayfasında URL'yi hatalı pozitif olarak raporlamak, Kiracı İzin Verme/Engelleme Listesi'nde URL için bir izin girişi ekler.

> [!IMPORTANT]
> Microsoft sizin için izin verme girdilerini yönettiği için, gereksiz URL izin verme girişleri kaldırılır. Bu davranış, kuruluşunuzu korur ve yanlış yapılandırılmış izin verme girdilerinin önlenmesine yardımcı olur. Karara katılmıyorsanız, URL'nin neden hala kötü kabul edildiğini saptamaya yardımcı olmak için bir destek olayı açmanız gerekebilir.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **URL'ler** sekmesini seçin

3. **URL'ler** sekmesinde Analiz için Microsoft'a Gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderme türünü seçin**: Değer **URL'sinin** seçili olduğunu doğrulayın.

   - **URL**: Tam URL'yi (örneğin, `https://www.fabrikam.com/marketing.html`) girin ve görüntülenen kutudan seçin.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmemeli (Hatalı pozitif)** seçeneğini belirleyin ve ardından aşağıdaki ayarları yapılandırın:

     - **Bu URL'ye izin ver**: Bu ayarı ![aç Aç..](../../media/scc-toggle-on.png)

         - **İzin ver girdisini kaldır:** Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **Belirli bir tarih**: En yüksek değer bugünden itibaren 30 gündür.

         - **Giriş notuna izin ver**: Bu URL'ye neden izin kullandığınızla ilgili isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

   :::image type="content" source="../../media/admin-submission-url-allow.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı pozitif (iyi) bir URL gönderin." lightbox="../../media/admin-submission-url-allow.png":::

5. Birkaç dakika sonra, URL izin ver girişi **Kiracı İzin Ver/Engelle Listesi** sayfasındaki **URL** sekmesinde görünür.

> [!NOTE]
>
> - URL yeniden algılandığında Güvenli [Bağlantılar](safe-links.md) patlama veya URL saygınlığı denetimleri için gönderilmez ve diğer tüm URL tabanlı filtreler atlanır.
> - Posta akışı sırasında, URL'yi içeren iletiler filtreleme yığınında URL olmayan diğer denetimleri geçirirse, iletiler teslim edilecek.

## <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için izin verme veya engelleme girdilerini görüntülemek için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **URL** sekmesini seçin. Aşağıdaki sütunlar kullanılabilir:

   - **Değer**: URL.
   - **Eylem**: **İzin Ver** veya **Engelle** değeri.
   - **Değiştiren**
   - **Son güncelleştirme**
   - **Kaldırma tarihi**: Son kullanma tarihi.
   - **Notlar**

   Artan veya azalan düzende sıralamak için sütun başlığına tıklayın.

   Grup simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Sonuçları **Yok** veya **Eyleme** göre gruplandırmak için **gruplandırın**.

   Ara simgesine tıklayın ![.](../../media/m365-cc-sc-search-icon.png) **Arama** yapın, bir değerin tamamını veya bir kısmını girin ve ardından belirli bir değeri bulmak için ENTER tuşuna basın. İşiniz bittiğinde Aramayı temizle simgesine tıklayın ![.](../../media/m365-cc-sc-close-icon.png) ögesini seçin.

   Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Sonuçları** filtrelemek için filtreleyin. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:

   - **Eylem**: **İzin Ver** ve **Engelle**.
   - **Süresi hiç dolmaz**: ![İki durumlu düğmeyi açın.](../../media/scc-toggle-on.png) veya ![Kapat'a geçin.](../../media/scc-toggle-off.png)
   - **Son güncelleştirme**: Başlangıç ve **Bitiş** **tarihleri'ne** tıklayın.
   - **Kaldırılacak yer**: Kimden ve **Bitiş** **tarihleri'ne** tıklayın.

   İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

### <a name="use-powershell-to-view-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için izin verme veya engelleme girdilerini görüntülemek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Allow] [-Block] [-Entry <URLValue>] [<-ExpirationDate <Date> | -NoExpiration>]
```

Bu örnek, tüm izin verilen ve engellenen URL'leri döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType Url
```

Bu örnek, sonuçları engellenen URL'lere göre filtreler.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için izin verme veya engelleme girdilerini değiştirmek için Microsoft 365 Defender portalını kullanın

Kiracı İzin Ver/Engelle listesindeki bir izin ver veya engelle URL girdisini değiştirdiğinizde, yalnızca son kullanma tarihini ve notları değiştirebilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **URL'ler** sekmesini seçin

3. **URL'ler** sekmesinde, değiştirmek istediğiniz girdinin onay kutusunu seçin ve düzenle simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **Düzenle** düğmesi.

4. Görüntülenen **URL'yi düzenle** açılır penceresinde aşağıdaki değerler kullanılabilir:

   - **Şunlardan sonra girişe izin ver** veya **Engelle girdisini kaldır**:
     - İzin verilen girişleri oluşturma tarihinden sonra en fazla 30 gün uzatabilirsiniz.
     - Blok girişlerini oluşturma tarihinden sonra en fazla 90 gün uzatabilir veya **Bunları Hiçbir zaman sona erme olarak ayarlayabilirsiniz**.

   - **İsteğe bağlı not**

   Bitirdiğinizde, **Kaydet**'i tıklatın.

> [!NOTE]
> Yalnızca girişlere izin ver için, onay kutusundan farklı bir satıra tıklayarak girdiyi seçerseniz Gönderimi görüntüle simgesini seçebilirsiniz ![.](../../media/m365-cc-sc-view-submission-icon.png) **Gönderiyi** , konumundaki **Gönderimler** sayfasına gitmek üzere görünen ayrıntılar açılır öğesinde <https://security.microsoft.com/reportsubmission>görüntüleyin.

### <a name="use-powershell-to-modify-allow-or-block-entries-for-urls-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki URL'ler için izin verme veya engelleme girdilerini değiştirmek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Bu örnek, belirtilen blok URL'si girişinin sona erme tarihini değiştirir.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Entries "~contoso.com" -ExpirationDate "9/1/2022"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden URL'ler için izin verme veya engelleme girdilerini kaldırmak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **URL'ler** sekmesini seçin.

3. **URL'ler** sekmesinde aşağıdaki adımlardan birini yapın:

   - Kaldırmak istediğiniz girdinin onay kutusunu seçin ve ardından Sil simgesine ![tıklayın.](../../media/m365-cc-sc-delete-icon.png) Görüntülenen **Sil** simgesi.
   - Onay kutusundan başka bir satıra tıklayarak kaldırmak istediğiniz girdiyi seçin. Görüntülenen ayrıntılar açılır listesinde Sil simgesine tıklayın ![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

4. Görüntülenen uyarı iletişim kutusunda **Sil'e** tıklayın.

> [!NOTE]
> Her onay kutusunu seçerek birden çok girdi seçebilir veya **Değer** sütun üst bilgisinin yanındaki onay kutusunu seçerek tüm girişleri seçebilirsiniz.

### <a name="use-powershell-to-remove-allow-or-block-entries-for-urls-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden URL'ler için izin verme veya engelleme girdilerini kaldırmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType Url <-Ids <Identity value> | -Entries <Value value>>
```

Bu örnek, belirtilen blok URL'si girişini Kiracı İzin Ver/Engelle Listesinden kaldırır.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Entries "~cohovineyard.com
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi için URL söz dizimi

- IPv4 ve IPv6 adreslerine izin verilir, ancak TCP/UDP bağlantı noktalarına izin verilmez.

- Dosya adı uzantılarına izin verilmez (örneğin, test.pdf).

- Unicode desteklenmez, ancak Punycode desteklenir.

- Aşağıdaki deyimlerin tümü doğruysa konak adlarına izin verilir:
  - Konak adı bir nokta içerir.
  - Noktanın solunda en az bir karakter vardır.
  - Noktanın sağında en az iki karakter vardır.

  Örneğin, `t.co` izin verilir veya `.com` `contoso.` izin verilmez.

- Alt yollar izinler için ima edilmemektedir.

  Örneğin, `contoso.com` içermez `contoso.com/a`.

- Aşağıdaki senaryolarda joker karakterlere (*) izin verilir:

  - Alt etki alanı belirtmek için sol joker karakterden sonra nokta gelmelidir. (yalnızca bloklar için geçerlidir)

    Örneğin, `*.contoso.com` izin verilir; `*contoso.com` izin verilmez.

  - Bir yol belirtmek için sağ joker karakter eğik çizgi (/) izlemelidir.

    Örneğin, `contoso.com/*` izin verilir veya `contoso.com*` `contoso.com/ab*` izin verilmez.

  - `*.com*` geçersiz (çözümlenebilir bir etki alanı değil ve sağ joker karakter eğik çizgi izlemez).

  - IP adreslerinde joker karakterlere izin verilmez.

- Tilde (~) karakteri aşağıdaki senaryolarda kullanılabilir:

  - Sol tilde bir etki alanı ve tüm alt etki alanları anlamına gelir.

    Örneğin `~contoso.com` ve `*.contoso.com`içerir`contoso.com`.

- Kullanıcı adı veya parola desteklenmez veya gerekli değildir.

- Tırnak işaretleri (' veya ") geçersiz karakterlerdir.

- Url mümkün olduğunda tüm yeniden yönlendirmeleri içermelidir.

### <a name="url-entry-scenarios"></a>URL giriş senaryoları

Geçerli URL girişleri ve sonuçları aşağıdaki bölümlerde açıklanmıştır.

#### <a name="scenario-no-wildcards"></a>Senaryo: Joker karakter yok

**Giriş**: `contoso.com`

- **Eşleşmeye izin ver**: contoso.com

- **Eşleşmemiş izin ver**:
  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **Blok eşleşmesi**:
  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **Blok eşleşmiyor**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Senaryo: Sol joker karakter (alt etki alanı)

> [!NOTE]
> Bu senaryo yalnızca bloklar için geçerlidir.

**Giriş**: `*.contoso.com`

- **Blok eşleşmesi**:
  - contoso.com
  - xyz.abc.contoso.com

- **Blok eşleşmiyor**:
  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Senaryo: Yolun en üstünde sağ joker karakter

**Giriş**: `contoso.com/a/*`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**:
  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Eşleşmedi** ve **Engelle eşleşmedi**:
  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Senaryo: Sol tilde

**Giriş**: `~contoso.com`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**:
  - contoso.com
  - contoso.com
  - xyz.abc.contoso.com

- **Eşleşmedi** ve **Engelle eşleşmedi**:
  - 123contoso.com
  - contoso.com/abc
  - contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Senaryo: Sağ joker karakter soneki

**Giriş**: `contoso.com/*`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**:
  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **eşleşmedi** ve **Engelle eşleşmedi**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Senaryo: Sol joker karakter alt etki alanı ve sağ joker karakter soneki

> [!NOTE]
> Bu senaryo yalnızca bloklar için geçerlidir.

**Giriş**: `*.contoso.com/*`

- **Blok eşleşmesi**:
  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - contoso.com/a
  - contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Blok eşleşmiyor**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Senaryo: Sol ve sağ tilde

**Giriş**: `~contoso.com~`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**:

  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/b
  - xyz.abc.contoso.com

- **Eşleşmedi** ve **Engelle eşleşmedi**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Senaryo: IP adresi

**Giriş**: `1.2.3.4`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**: 1.2.3.4

- **Eşleşmedi** ve **Engelle eşleşmedi**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Sağ joker karakterli IP adresi

**Giriş**: `1.2.3.4/*`

- **Eşleşmeye izin ver** ve **Eşleşmeyi engelle**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Geçersiz girdi örnekleri

Aşağıdaki girdiler geçersiz:

- **Eksik veya geçersiz etki alanı değerleri**:

  - Contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Metinde veya aralık karakterleri olmadan joker karakter**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Bağlantı noktaları olan IP adresleri**:

  - contoso.com:443
  - abc.contoso.com:25

- **Açıklayıcı olmayan joker karakterler**:

  - \*
  - \*.\*

- **Orta joker karakterler**:

  - conto\*so.com
  - conto~so.com

- **Çift joker karakter**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="related-articles"></a>İlgili makaleler

- [Şüpheli istenmeyen posta, kimlik avı, URL'ler, engellenen meşru e-postalar ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanın](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesindeki dosyalara izin ver veya bunları engelle](allow-block-files.md)
- [Kiracı İzin Ver/Engelle Listesinde e-postalara izin ver veya e-postaları engelle](allow-block-email-spoof.md)
