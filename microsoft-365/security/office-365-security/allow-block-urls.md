---
title: Kiracı İzin Ver/Engelle Listesini kullanarak URL'lere izin verme veya URL’leri engelleme
f1.keywords:
- NOCSH
ms.author: dansimp
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 69d9b4725e0a2c57dac8bb711655b9e0ff02e3e5
ms.sourcegitcommit: 7df8adc9e67ab65e413d7ea7bb0dcb9fd2da1a11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66861955"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak URL'lere izin verme veya URL’leri engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Kiracı İzin Ver/Engelle Listesi'ndeki URL'lere izin vermek veya url'leri engellemek için Microsoft 365 Defender portalını veya PowerShell'i kullanabilirsiniz.

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

## <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde blok URL'si girdileri oluşturma

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **URL'ler** sekmesinin seçili olduğunu doğrulayın ve ardından Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

3. Görüntülenen **URL'leri engelle** açılır penceresinde aşağıdaki ayarları yapılandırın:
   - **Joker karakterli URL'ler ekleme**: Satır başına en fazla 20 URL girin. URL girişlerinin söz dizimi hakkında ayrıntılı bilgi için [Kiracı İzin Verme/Engelleme Listesini Yönetme](tenant-allow-block-list.md) bölümündeki URL söz dizimi bölümüne bakın.
   - **Hiçbir zaman sona ermez**: Aşağıdaki adımlardan birini yapın:
     - Ayarın kapalı olduğunu doğrulayın (![Kapat.](../../media/scc-toggle-off.png)) ve **Girişlerin** sona erme tarihini belirtmek için Kaldır açık kutusunu kullanın.

       veya

     - Girişleri hiçbir zaman sona ermeyecek şekilde yapılandırmak için iki durumlu düğmeyi sağa taşıyın: ![İki durumlu düğmeyi açın.](../../media/scc-toggle-on.png).
   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

4. İşiniz bittiğinde **Ekle'ye** tıklayın.

> [!NOTE]
> Bu URL'leri içeren e-postalar _kimlik avı_ olarak engellenir.

### <a name="use-powershell"></a>PowerShell kullanma

Kiracı İzin Ver/Engelle Listesi'ne blok URL'si girdileri eklemek için aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType <Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Bu örnek, contoso.com ve tüm alt etki alanları (örneğin, contoso.com ve xyz.abc.contoso.com) için bir blok URL girişi ekler. ExpirationDate veya NoExpiration parametrelerini kullanmadığımız için girdinin süresi 30 gün sonra dolar.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-url-entries"></a>İzin ver URL girişleri oluşturma

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

Microsoft 365 Defender'daki **Gönderimler sayfasında URL'lere** izin verin.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler &** **Gönderimler'e**\> gidin. Veya doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **URL'ler** sekmesini seçin ve analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

3. URL'yi ekleyerek ileti göndermek **için Gözden geçirmek üzere Microsoft'a gönder** açılır penceresini kullanın.

4. **Microsoft'a göndermek için bir neden seçin** bölümünde **Engellenmemiş olmalıdır (hatalı pozitif)** seçeneğini belirleyin.

5. **Bu tür URL'lere izin ver** seçeneğini açın.

6. **Sonra kaldır** açılan listesinden, izin verme seçeneğinin ne kadar süreyle çalışmasını istediğinizi belirtin.

7. **İsteğe Bağlı Notu** kullanarak neden allow eklediğinizi ekleyin. 

8. İşiniz bittiğinde **Gönder** düğmesine tıklayın.

    :::image type="content" source="../../media/submit-url-for-analysis.png" alt-text="Analiz için URL gönderme" lightbox="../../media/submit-url-for-analysis.png":::

> [!NOTE]
>
> - URL ile yeniden karşılaşıldığında, URL patlama veya saygınlık denetimleri için gönderilmez ve diğer tüm URL tabanlı filtreler atlanır.
> - Bu nedenle, bir e-posta (bu URL'yi içeren) için, posta akışı sırasında filtrelerin geri kalanı e-postanın temiz olduğunu bulursa e-posta teslim edilecek.

## <a name="view-url-entries"></a>URL girişlerini görüntüleme

Kiracı İzin Ver/Engelle Listesinde blok URL girişlerini görüntülemek için aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType <URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

Bu örnek tüm engellenen URL'leri döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-url-entries"></a>URL girişlerini değiştirme 

Kiracı İzin Ver/Engelle Listesi'nde URL girişlerine izin verme veya engellemeyi değiştirmek için aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Bu örnek, belirtilen blok URL'si girişinin sona erme tarihini değiştirir.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-url-entries"></a>URL girdilerini kaldırma 

Kiracı İzin Ver/Engelle Listesinden izin ver veya url girişlerini engelle girdilerini kaldırmak için aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN">
```
Bu örnek, belirtilen blok URL'si girişini Kiracı İzin Ver/Engelle Listesinden kaldırır.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="related-articles"></a>İlgili makaleler

- [Yönetici gönderimleri](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesindeki dosyalara izin ver veya bunları engelle](allow-block-files.md)
- [Kiracı İzin Ver/Engelle Listesinde e-postalara izin ver veya e-postaları engelle](allow-block-email-spoof.md)
