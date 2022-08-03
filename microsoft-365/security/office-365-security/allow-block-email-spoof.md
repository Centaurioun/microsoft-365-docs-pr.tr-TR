---
title: Kiracı İzin Ver/Engelle Listesini kullanarak e-postalara izin verme veya e-postaları engelleme
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
- MET150
ms.collection:
- M365-security-compliance
description: Yöneticiler, Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde e-postalara ve sahte gönderen girişlerine izin verme veya bunları engelleme hakkında bilgi edinebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 107aef5dd4cc3098d6e77f45e6b95352997ef738
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175014"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak e-postalara izin verme veya e-postaları engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Kiracı İzin Ver/Engelle Listesi'ni kullanarak e-postalara izin vermek veya e-postaları engellemek için Microsoft 365 Defender portalını veya PowerShell'i kullanabilirsiniz ...

## <a name="create-block-sender-entries"></a>Blok gönderen girdileri oluşturma 

### <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalını kullanma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **, Etki Alanları & adresleri** sekmesinin seçili olduğunu doğrulayın ve ardından Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

3. Görüntülenen **Etki alanlarını & adresleri engelle** açılır öğesinde aşağıdaki ayarları yapılandırın:
   - **Email adresleri veya etki alanları**: Satır başına en fazla 20 e-posta adresi veya etki alanı girin.
   - **Hiçbir zaman sona ermez**: Aşağıdaki adımlardan birini yapın:
     - Ayarın kapalı olduğunu doğrulayın (![Kapat.](../../media/scc-toggle-off.png)) ve **Girişlerin** sona erme tarihini belirtmek için Kaldır açık kutusunu kullanın.

       veya

     - Girişleri hiçbir zaman sona ermeyecek şekilde yapılandırmak için iki durumlu düğmeyi sağa taşıyın: ![İki durumlu düğmeyi açın.](../../media/scc-toggle-on.png).
   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

4. İşiniz bittiğinde **Ekle'ye** tıklayın.

> [!NOTE]
> Bu gönderenlerden gelen e-postalar _yüksek güvenilirlikli istenmeyen posta_ olarak engellenir (SCL = 9).
> Kuruluştaki kullanıcılar bu engellenen etki alanlarına ve adreslere e-posta gönderemez. Şu ifadeyi içeren bir teslim edilemedi raporu alır: "5.7.1 Bir veya daha fazla alıcı kuruluşunuzun kiracı izin verme/engelleme listesi ilkesi tarafından engellendiği için iletiniz teslim edilemiyor."

### <a name="use-powershell"></a>PowerShell kullanma

Kiracı İzin Ver/Engelle Listesi'ne blok gönderen girdileri eklemek için aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType <Sender> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Bu örnek, belirtilen gönderen için belirli bir tarihte süresi dolan bir engel gönderen girdisi ekler.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-sender-entries"></a>Gönderen girişlerine izin ver oluşturma 

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

Microsoft 365 Defender **Gönderiler sayfasında gönderenlere** (veya etki alanlarına) izin verin.

İzin verme girdileri eklemek için Kiracı İzin Ver/Engelle Listesi'ni doğrudan değiştiremezsiniz. Bunun yerine, engellenen iletiyi göndermek için [yönetici gönderimlerini](admin-submission.md) kullanın. Bu eylem, kiracıya karşılık gelen URL, dosya, sahte gönderen etki alanı çifti, kimliğine bürünülen etki alanı (veya kullanıcı) ve/veya göndereni Kiracı İzin Ver/Engelle Listesine ekler. Öğe engellenmemişse, izin verme oluşturulmaz. İletinin yanlış engellenmiş hatalı bir pozitif olduğu belirlendiği çoğu durumda, belirtilen son kullanma tarihinde izin ver girişi kaldırılır.

> [!IMPORTANT]
> - Microsoft sizin için izin verme girdilerini yönettiğinden, gerekmeyen gönderen, URL veya dosya izin girdileri kaldırılır. Bu davranış, kuruluşunuzu korur ve yanlış yapılandırılmış izin verme girdilerinin önlenmesine yardımcı olur. Karara katılmıyorsanız, iletinin neden hala kötü kabul edildiğini saptamak için bir destek olayı açmanız gerekebilir.


1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler &** **Gönderimler'e**\> gidin. Veya doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **, E-postalar** sekmesinin seçili olduğunu doğrulayın ve analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

3. Ağ iletisi kimliğini ekleyerek veya e-posta dosyasını karşıya yükleyerek ileti göndermek **için Gözden geçirmek üzere Microsoft'a gönder** açılır penceresini kullanın.

4. **Microsoft'a göndermek için bir neden seçin** bölümünde **Engellenmemiş olmalıdır (hatalı pozitif)** seçeneğini belirleyin.

5. Bu seçenek **gibi iletilere izin ver'i** açın.

6. **Sonra kaldır** açılan listesinden, izin verme seçeneğinin ne kadar süreyle çalışmasını istediğinizi belirtin.

7. **İsteğe Bağlı Not** kutusunu kullanarak neden izin ver'i eklediğinizi ekleyin. 

8. İşiniz bittiğinde **Gönder** düğmesini seçin.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Analiz örneği için Microsoft'a kötü amaçlı yazılım gönderin." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - Posta akışı sırasında, hangi filtrelerin postanın kötü amaçlı olduğunu belirlediği temelinde, izinler eklenir. Örneğin, gönderen ve URL hatalı olarak belirlenir, her birine bir izin eklenir.
> - Bu varlıkla (gönderen, etki alanı, URL, dosya) yeniden karşılaşıldığında, bu varlıkla ilişkili tüm filtreler atlanır.
> - Posta akışı sırasında, filtrelerin geri kalanı bu varlığı içeren e-postayı temiz bulursa, e-posta teslim edilecek. Örneğin, bir gönderen izin verir (kimlik doğrulaması geçtiğinde), bir ek veya URL ile ilişkili kötü amaçlı yazılım ve yüksek güvenilirlikli kimlik avı dışındaki tüm kararları atlar.

## <a name="view-sender-entries"></a>Gönderen girdilerini görüntüleme 

Kiracı İzin Ver/Engelle Listesi'nde engelleyici gönderen girdilerini görüntülemek için aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType <Sender> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```
Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-sender-entries"></a>Gönderen girdilerini değiştirme 

Kiracı İzin Ver/Engelle Listesi'nde gönderen girişlerine izin vermek veya bunları engellemek için aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-sender-entries"></a>Gönderen girdilerini kaldırma 

Kiracı İzin Ver/Engelle Listesinden izin ver veya engelle gönderen girdilerini kaldırmak için aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN">
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>Sahte gönderen girişleri için etki alanı çifti söz dizimi

Kiracı İzin Ver/Engelle Listesindeki kimlik sahtekarı bir gönderen için etki alanı çifti aşağıdaki söz dizimini kullanır: `<Spoofed user>, <Sending infrastructure>`.

- **Kimlik sahtekarı kullanıcı**: Bu değer, e-posta istemcilerindeki **Kimden** kutusunda görüntülenen sahte kullanıcının e-posta adresini içerir. Bu adres, adres olarak `5322.From` da bilinir. Geçerli değerler şunlardır:
  - Tek bir e-posta adresi (örneğin, chris@contoso.com).
  - E-posta etki alanı (örneğin, contoso.com).
  - Joker karakter (örneğin, \*).

- **Altyapı gönderiliyor**: Bu değer, sahte kullanıcıdan gelen iletilerin kaynağını gösterir. Geçerli değerler şunlardır:
  - Kaynak e-posta sunucusunun IP adresinin (örneğin, fabrikam.com) ters DNS aramasında (PTR kaydı) bulunan etki alanı.
  - Kaynak IP adresinin PTR kaydı yoksa, gönderen altyapı /24 olarak \<source IP\>tanımlanır (örneğin, 192.168.100.100/24).
  - Doğrulanmış bir DKIM etki alanı.

Sahte gönderenleri tanımlamak için geçerli etki alanı çiftlerinin bazı örnekleri aşağıda verilmiştir:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Sahte gönderen girdisi sayısı üst sınırı 1000'dir.

Etki alanı çifti eklemek yalnızca kimlik sahtekarlığına sahip kullanıcının *ve* gönderen altyapının *birleşimine* izin verir veya engeller. Kimlik sahtekarı olan kullanıcının herhangi bir kaynaktan gelen e-postasına izin vermez veya sahte kullanıcı için gönderen altyapı kaynağından gelen e-postaya izin vermez.

Örneğin, aşağıdaki etki alanı çifti için bir izin ver girdisi eklersiniz:

- **Etki alanı**: gmail.com
- **Altyapı**: tms.mx.com

Yalnızca bu etki alanından gelen _ve_ altyapı çifti gönderen iletilerin kimlik sahtekarlığına izin verilir. gmail.com sahtekarlık yapmaya çalışan diğer gönderenlere izin verilmez. diğer etki alanlarındaki tms.mx.com gelen gönderenlerden gelen iletiler kimlik sahtekarlığına göre denetleniyor.

## <a name="create-blocked-spoofed-sender-entries"></a>Engellenen sahte gönderen girdileri oluşturma

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

> [!NOTE]
> Bu gönderenlerden gelen Email _kimlik avı_ olarak engellenir.
>
> Yalnızca kimlik sahtekarlığına neden olan kullanıcı _ile_ etki alanı çiftinde tanımlanan gönderme _altyapısının birleşimine_ özellikle izin verilir veya kimlik sahtekarlığına engellenir.
>
> Bir etki alanı çifti için izin ver veya engelle girdisi yapılandırdığınızda, bu etki alanı çiftinden gelen iletiler artık kimlik sahtekarı zeka içgörülerinde görünmez.
>
> Sahte gönderenlerin girdilerinin süresi hiçbir zaman dolmaz.

1. Microsoft 365 Defender portalında **İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında Sahte **gönderenler** sekmesini seçin ve ardından Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Ekle'yi seçin**.

3. Görüntülenen **Yeni etki alanı çiftleri ekle** açılır penceresinde aşağıdaki ayarları yapılandırın:
   - **Joker karakterlerle yeni etki alanı çiftleri ekleyin**: Satır başına en fazla 20 etki alanı çifti girin. Kimlik sahtekarlığına neden olan gönderen girdilerinin söz dizimi hakkında ayrıntılı bilgi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](tenant-allow-block-list.md).
   - **Kimlik sahtekarı türü**: Aşağıdaki değerlerden birini seçin:
     - **İç**: Sahte gönderen, kuruluşunuza ait bir etki alanındadır ( [kabul edilen bir etki alanı](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Dış**: Sahte gönderen bir dış etki alanında.
   - **Eylem**: **Engelle'yi** seçin.

4. İşiniz bittiğinde **Ekle'ye** tıklayın.

> [!NOTE]
> Bu gönderenlerden gelen e-postalar _kimlik avı_ olarak engellenir.

### <a name="use-powershell"></a>PowerShell kullanma

Kiracı İzin Ver/Engelle Listesi'ne sahte gönderen girdileri eklemek için aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

## <a name="create-allowed-spoofed-sender-entries"></a>İzin verilen sahte gönderen girdileri oluşturma 

### <a name="use-the-tenant-allowblock-list-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Kiracı İzin Ver/Engelle Listesini Kullanma

> [!NOTE]
>
> - Yalnızca kimlik sahtekarlığına neden olan kullanıcı _ile_ etki alanı çiftinde tanımlanan gönderme _altyapısının birleşimine_ özellikle izin verilir veya kimlik sahtekarlığına engellenir.
> - Bir etki alanı çifti için izin ver veya engelle girdisi yapılandırdığınızda, bu etki alanı çiftinden gelen iletiler artık kimlik sahtekarı zeka içgörülerinde görünmez.
> - Sahte gönderenlerin girdilerinin süresi hiçbir zaman dolmaz.

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>**, Kurallar** bölümünde **Email & işbirliği** \> **İlkeleri & kuralları** \> **Tehdit ilkeleri** \> **Kiracı İzin Ver/Engelle Listelerine** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında Sahte **gönderenler** sekmesini seçin ve ekle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Ekle'yi seçin**.

3. Görüntülenen **Yeni etki alanı çiftleri ekle** açılır penceresinde aşağıdaki ayarları yapılandırın:
   - **Joker karakterlerle yeni etki alanı çiftleri ekleyin**: Satır başına en fazla 20 etki alanı çifti girin. Kimlik sahtekarlığına neden olan gönderen girdilerinin söz dizimi hakkında ayrıntılı bilgi için bkz. [Kiracı İzin Verme/Engelleme Listesini Yönetme](tenant-allow-block-list.md).
   - **Kimlik sahtekarı türü**: Aşağıdaki değerlerden birini seçin:
     - **İç**: Sahte gönderen, kuruluşunuza ait bir etki alanındadır ( [kabul edilen bir etki alanı](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Dış**: Sahte gönderen bir dış etki alanında.
   - **Eylem**: **İzin Ver'i** seçin.

4. İşiniz bittiğinde **Ekle'ye** tıklayın.

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Yönetici Gönderimini kullanma

Ayrıca, Microsoft 365 Defender'daki Gönderiler sayfasını kullanarak sahte **gönderenlere** izin verebilirsiniz.

Engellenen iletiyi göndermek için [yönetici gönderimlerini](admin-submission.md) kullanın. Bu eylem, kiracıya karşılık gelen URL, dosya, sahte gönderen etki alanı çifti, kimliğine bürünülen etki alanı (veya kullanıcı) ve/veya göndereni Kiracı İzin Ver/Engelle Listesine ekler. Öğe engellenmemişse, izin verme oluşturulmaz. 

> [!IMPORTANT]
>
> - Sahtekarlık, kuruluş içi, kuruluşlar arası ve DMARC kimlik sahtekarlığına dikkat edilmesini sağlar.
> - Yönetici gönderimindeki isteğe bağlı not, kimlik sahtekarlığına izin verir için geçerli değildir.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler &** **Gönderimler'e**\> gidin. Veya doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **, E-postalar** sekmesinin seçili olduğunu doğrulayın ve analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

3. Ağ iletisi kimliğini ekleyerek veya e-posta dosyasını karşıya yükleyerek ileti göndermek **için Gözden geçirmek üzere Microsoft'a gönder** açılır penceresini kullanın.

4. **Microsoft'a göndermek için bir neden seçin** bölümünde **Engellenmemiş olmalıdır (hatalı pozitif)** seçeneğini belirleyin.

5. Bu seçenek **gibi iletilere izin ver'i** açın.

6. **Sonra kaldır** açılan listesinden, kimlik sahtekarlığına uygulanmıyor olsa da izin verme seçeneğinin ne kadar süreyle çalışmasını istediğinizi belirtin.

7. İşiniz bittiğinde **Gönder** düğmesini seçin.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Analiz örneği için Microsoft'a kötü amaçlı yazılım gönderin." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - Sahte gönderen etki alanı çifti oluşturulur ve **Kiracı izin ver/engelle listesi** sayfasının altındaki Sahte **gönderenler** sekmesinde görünür.


### <a name="use-powershell"></a>PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/exchange-online-powershell) Kiracı İzin Ver/Engelle Listesi'ne sahte gönderen girdileri eklemek için aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

## <a name="view-spoofed-sender-entries"></a>Sahte gönderen girdilerini görüntüleme

Kiracı İzin Ver/Engelle Listesi'nde sahte gönderen girdilerini görüntülemek için aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

Bu örnek, Kiracı İzin Ver/Engelle Listesindeki tüm sahte gönderen girdilerini döndürür.

```powershell
Get-TenantAllowBlockListSpoofItems
```

Bu örnek, iç olan tüm sahte gönderen girişlerini döndürür.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

Bu örnek, dış olan tüm engellenen sahte gönderen girdilerini döndürür.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).

## <a name="modify-spoofed-sender-entries"></a>Sahte gönderen girdilerini değiştirme 

Kiracı İzin Ver/Engelle Listesi'nde sahte gönderen girişlerine izin vermek veya bunları engellemek için aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

Bu örnek sahte gönderen girdisini izin ver'den engellemeye değiştirir.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

## <a name="remove-spoofed-sender-entries"></a>Sahte gönderen girdilerini kaldırma 

Kiracı İzin Ver/Engelle Listesinden kimlik sahtekarlığına izin verme veya engelleme girdilerini kaldırmak için aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

## <a name="create-impersonated-sender-entries"></a>Kimliğine bürünülen gönderen girdileri oluşturma

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Yönetici Gönderimini kullanma

Ayrıca, Microsoft 365 Defender gönderiler sayfasını kullanarak kimliğine bürünülen **gönderenlere** izin verebilirsiniz.

Engellenen iletiyi göndermek için [yönetici gönderimlerini](admin-submission.md) kullanın. Bu eylem, kiracıya karşılık gelen URL, dosya, sahte gönderen etki alanı çifti, kimliğine bürünülen etki alanı (veya kullanıcı) ve/veya göndereni Kiracı İzin Ver/Engelle Listesine ekler. Öğe engellenmemişse, izin verme oluşturulmaz. 

> [!IMPORTANT]
>
> - Kimliğe bürünme, etki alanı ve kullanıcı kimliğe bürünme ile ilgilenmenize olanak tanır.
> - Graf Kimliğe Bürünme işlemi şimdilik buradan gerçekleştirilmiyor.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler &** **Gönderimler'e**\> gidin. Veya doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **, E-postalar** sekmesinin seçili olduğunu doğrulayın ve analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

3. Ağ iletisi kimliğini ekleyerek veya e-posta dosyasını karşıya yükleyerek ileti göndermek **için Gözden geçirmek üzere Microsoft'a gönder** açılır penceresini kullanın.

4. **Microsoft'a göndermek için bir neden seçin** bölümünde **Engellenmemiş olmalıdır (hatalı pozitif)** seçeneğini belirleyin.

5. Bu seçenek **gibi iletilere izin ver'i** açın.

6. **Sonra kaldır** açılan listesinden, kimliğine bürünülen izinler için geçerli olmasa da izin verme seçeneğinin ne kadar süreyle çalışmasını istediğinizi belirtin.

7. İşiniz bittiğinde **Gönder** düğmesini seçin.

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="Analiz örneği için Microsoft'a kötü amaçlı yazılım gönderin." lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
> Kimliğine bürünülen etki alanı (veya kullanıcı), konumundaki kimlik avı önleme ilkesinin <https://security.microsoft.com/antiphishing>**Güvenilen gönderenler ve etki alanları** bölümünde oluşturulur ve görünür.

## <a name="related-articles"></a>İlgili makaleler

- [Yönetici gönderimleri](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesindeki dosyalara izin ver veya bunları engelle](allow-block-files.md)
- [Kiracı İzin Ver/Engelle Listesinde URL'lere izin ver veya url'leri engelle](allow-block-urls.md)
