---
title: Kiracı İzin Ver/Engelle Listesini kullanarak e-postalara izin verme veya e-postaları engelleme
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
description: Yöneticiler, Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde e-postalara ve sahte gönderen girişlerine izin verme veya bunları engelleme hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1537b32d56046da776024cef3acbd9eb2d8a4da3
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497571"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak e-postalara izin verme veya e-postaları engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bu makalede, Kiracı İzin Verme/Engelleme Listesi'nde bulunan etki alanları ve e-posta adresleri (sahte gönderenler dahil) için izin verme ve engelleme girdilerinin nasıl oluşturulacağı ve yönetileceğini açıklar. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

e-posta için izin verme ve engelleme girdilerini Microsoft 365 Defender Portalı'nda veya Exchange Online PowerShell'de yönetirsiniz.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. **Doğrudan Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın<https://security.microsoft.com/tenantAllowBlockList>. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell). Tek başına EOP PowerShell'e bağlanmak için bkz. [Exchange Online Protection PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Etki alanları ve e-posta adresleri için izin verilen girdi sayısı üst sınırı 500, blok girişi sayısı üst sınırı 500'dir (toplam 1000 etki alanı ve e-posta adresi girişi).

- Sahte gönderenler için en fazla giriş sayısı 1024'tür.

- Sahte gönderenlerin girdilerinin süresi hiçbir zaman dolmaz.

- Kimlik sahtekarlığına neden olan gönderen girdilerinin söz dizimi hakkında ayrıntılı bilgi için, bu makalenin devamında yer alan Sahte [gönderen girişleri için etki alanı çifti söz dizimi](#domain-pair-syntax-for-spoofed-sender-entries) bölümüne bakın.

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

## <a name="domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki etki alanları ve e-posta adresleri

### <a name="create-block-entries-for-domains-and-email-addresses"></a>Etki alanları ve e-posta adresleri için blok girdileri oluşturma

Etki alanları ve e-posta adresleri için blok girdileri oluşturmak için aşağıdaki seçeneklere sahipsiniz:

- [Microsoft 365 Defender portalındaki Gönderimler sayfası](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- [Microsoft 365 Defender portalında](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list) veya [PowerShell'de](#use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list) Kiracı İzin Ver/Engelle Listesi

Sahte gönderenler için blok girdileri oluşturmak için, bu [makalenin devamında yer alan Kiracı İzin Ver/Engelle Listesi'ndeki Sahte gönderenler için izin ver veya engelle girdilerini görüntülemek için Microsoft 365 Defender portalını kullanma](#use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list) bölümüne bakın.

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>gönderimler portalında etki alanları ve e-posta adresleri için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

E-posta iletilerini **engellenmiş olması gerekir (Hatalı negatif)** olarak raporlamak için adresinde <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullandığınızda, Kiracı İzin Ver/Engelle Listesi'nde etki alanı veya gönderen için bir engelleme girdisi eklemek üzere **Bu alıcıdan gelen tüm e-postaları engelle'yi** seçebilirsiniz.

Yönergeler için bkz. [Sorgulanabilir e-postayı Microsoft'a bildirme](admin-submission.md#report-questionable-email-to-microsoft).

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde etki alanları ve e-posta adresleri için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Etki alanları ve e-posta adresleri için blok girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturabilirsiniz.

Bu gönderenlerden gelen Email iletileri *yüksek güvenilirlikli istenmeyen posta* olarak işaretlenir (SCL = 9). İletilere ne olacağı, alıcı için iletiyi algılayan [istenmeyen posta önleme ilkesi](configure-your-spam-filter-policies.md) tarafından belirlenir. Varsayılan istenmeyen posta önleme ilkesinde ve yeni özel ilkelerde, yüksek güvenilirlikli istenmeyen posta olarak işaretlenmiş iletiler varsayılan olarak Gereksiz Email klasörüne teslim edilir. Standart ve Katı [önceden ayarlanmış güvenlik ilkelerinde](preset-security-policies.md) yüksek güvenilirlikli istenmeyen posta iletileri karantinaya alınır.

> [!NOTE]
> Kuruluştaki kullanıcılar bu engellenen etki alanlarına ve adreslere e-posta gönderemez. Aşağıdaki teslim edilmedi raporunu (NDR veya geri dönen ileti olarak da bilinir) alırlar: `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.`

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **Etki Alanları & adresleri** sekmesinin seçili olduğunu doğrulayın.

3. **Etki Alanları & adresleri** sekmesinde Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

4. Görüntülenen **Etki alanlarını & adresleri engelle** açılır öğesinde aşağıdaki ayarları yapılandırın:

   - **Etki alanları & adresleri**: Satır başına en fazla 20 e-posta adresi veya etki alanı girin.

   - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
     - **1 gün**
     - **7 gün**
     - **30 gün**
     - **Hiçbir zaman süresi dolmaz**
     - **Belirli bir tarih**: En büyük değer bugünden itibaren 90 gündür.

   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

5. İşiniz bittiğinde **Ekle'ye** tıklayın.

##### <a name="use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde etki alanları ve e-posta adresleri için blok girdileri oluşturmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "DomainOrEmailAddress1","DomainOrEmailAddress1",..."DomainOrEmailAddressN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Bu örnek, belirtilen e-posta adresi için belirli bir tarihte süresi dolan bir blok girdisi ekler.

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com","test2@anotherattackerdomain.com" -ExpirationDate 8/20/2022
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>Gönderimler portalında etki alanları ve e-posta adresleri için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Etki alanları ve e-posta adresleri için izin verme girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturamazsınız. Bunun yerine, iletiyi hatalı pozitif olarak raporlamak için adresinde <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullanırsınız. Yönetici gönderimleri hakkında daha fazla bilgi için bkz [. Şüpheli istenmeyen postaları, kimlik avı, URL'leri, engellenen meşru e-postaları ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanma](admin-submission.md).

> [!NOTE]
> Microsoft sizin için izin verme girdilerini yönettiği için etki alanları ve e-posta adresleri için gereksiz izin verme girdileri kaldırılır. Bu davranış, kuruluşunuzu korur ve yanlış yapılandırılmış izin verme girdilerinin önlenmesine yardımcı olur. Karara katılmıyorsanız, iletinin neden hala kötü kabul edildiğini saptamak için bir destek olayı açmanız gerekebilir.
>
> Etki alanı veya e-posta adresi henüz engellenmemişse, etki alanı veya e-posta adresi için izin ver girişi oluşturulmaz.
>
> İletinin yanlış engellenmiş hatalı bir pozitif olduğu belirlendiği çoğu durumda, belirtilen son kullanma tarihinde izin ver girişi kaldırılır.
>
> Sahte gönderenler için izin verme girdileri oluşturmak için, bu makalenin devamında Sahte [gönderenler için izin verme girdileri oluşturma](#create-allow-entries-for-spoofed-senders) bölümüne bakın.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **E-postalar** sekmesinin seçili olduğunu doğrulayın.

3. **E-postalar** sekmesinde Analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderim türünü seçin**: **Email** değerinin seçili olduğunu doğrulayın.

   - **Ağ iletisi kimliğini ekleyin veya e-posta dosyasını karşıya yükleyin**: Aşağıdaki seçeneklerden birini seçin:

     - **E-posta ağ iletisi kimliğini ekleyin**: Bu, karantinaya alınan iletilerdeki **X-MS-Exchange-Organization-Network-Message-Id** üst bilgisinde veya **X-MS-Office365-Filtering-Correlation-Id** üst bilgisinde bulunan bir GUID değeridir.

     - **E-posta dosyasını (.msg veya .eml) karşıya yükleyin**: **Dosyalara gözat'a** tıklayın. Açılan iletişim kutusunda .eml veya .msg dosyasını bulup seçin ve **aç'a** tıklayın.

   - **Sorunu olan bir alıcı seçin**: İlke denetimini çalıştırmak istediğiniz alıcıyı belirtin. İlke denetimi, e-postanın kullanıcı veya kuruluş ilkeleri nedeniyle engellenip engellenmediğini belirler.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmemeli (Hatalı pozitif)** seçeneğini belirleyin ve ardından aşağıdaki ayarları yapılandırın:

     - **Benzer özniteliklere (URL, gönderen vb.) sahip e-postalara izin ver**: Bu ayarı ![Aç..](../../media/scc-toggle-on.png).

         - **İzin ver girdisini kaldır:** Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **Belirli bir tarih**: En yüksek değer bugünden itibaren 30 gündür.

         - **Giriş notuna izin ver**: Bu e-postaya neden izin kullandığınızla ilgili isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

   :::image type="content" source="../../media/admin-submission-email-allow.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı pozitif (iyi) bir e-posta gönderin." lightbox="../../media/admin-submission-email-allow.png":::

5. Birkaç dakika sonra İzin **Ver/Engelle Listesi** sayfasındaki **Etki Alanları & adresleri** sekmesinde izin ver girişi görünür.

> [!NOTE]
>
> - İletinin kötü amaçlı olduğunu belirleyen filtrelere bağlı olarak posta akışı sırasında izinler eklenir. Örneğin, gönderen ve iletideki bir URL'nin hatalı olduğu belirlendiyse, gönderen için bir izin girdisi oluşturulur ve URL için bir izin girdisi oluşturulur.
> - Bu varlıkla (etki alanı veya e-posta adresi, URL, dosya) yeniden karşılaşıldığında, bu varlıkla ilişkili tüm filtreler atlanır.
> - Posta akışı sırasında, etki alanından veya e-posta adresinden gelen iletiler filtreleme yığınında başka denetimler geçirirse, iletiler teslim edilecek. Örneğin, [e-posta kimlik doğrulaması](email-validation-and-authentication.md) geçerse, izin ver girişindeki bir gönderenden gelen bir ileti teslim edilecek.

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini görüntülemek için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Etki Alanları & adresleri** sekmesinin seçili olduğunu doğrulayın. Aşağıdaki sütunlar kullanılabilir:

   - **Değer**: Etki alanı veya e-posta adresi.
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

#### <a name="use-powershell-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini görüntülemek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType Sender [-Allow] [-Block] [-Entry <Domain or Email address value>] [<-ExpirationDate Date | -NoExpiration>]
```

Bu örnek, etki alanları ve e-posta adresleri için tüm izin ver ve engelle girdilerini döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType Sender
```

Bu örnek, etki alanları ve e-posta adresleri için blok girdilerinin sonuçlarını filtreler.

```powershell
Get-TenantAllowBlockListItems -ListType Sender -Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini değiştirmek için Microsoft 365 Defender portalını kullanın

Kiracı İzin Ver/Engelle listesindeki etki alanları ve e-posta adresleri için izin ver veya engelle girdisini değiştirdiğinizde, yalnızca son kullanma tarihini ve notları değiştirebilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Etki Alanları & adresleri** sekmesinin seçili olduğunu doğrulayın.

3. **Etki Alanları & adresleri** sekmesinde, değiştirmek istediğiniz girdinin onay kutusunu seçin ve düzenle simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **Düzenle** düğmesi.

4. Aşağıdaki ayarlar, görüntülenen **Etki alanını düzenle & adresleri** açılır öğesinde kullanılabilir:

   - **Şunlardan sonra girişe izin ver** veya **Engelle girdisini kaldır**:
     - İzin verilen girişleri oluşturma tarihinden sonra en fazla 30 gün uzatabilirsiniz.
     - Blok girişlerini oluşturma tarihinden sonra en fazla 90 gün uzatabilir veya **Bunları Hiçbir zaman sona erme olarak ayarlayabilirsiniz**.

   - **İsteğe bağlı not**

   Bitirdiğinizde, **Kaydet**'i tıklatın.

> [!NOTE]
> Yalnızca girişlere izin ver için, onay kutusundan farklı bir satıra tıklayarak girdiyi seçerseniz Gönderimi görüntüle simgesini seçebilirsiniz ![.](../../media/m365-cc-sc-view-submission-icon.png) **Gönderiyi** , konumundaki **Gönderimler** sayfasına gitmek üzere görünen ayrıntılar açılır öğesinde <https://security.microsoft.com/reportsubmission>görüntüleyin.

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini değiştirmek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Bu örnek, etki alanları ve e-posta adresleri için belirtilen blok girişinin sona erme tarihini değiştirir.

```powershell
Set-TenantAllowBlockListItems -ListType Sender -Entries "julia@fabrikam.com" -ExpirationDate "9/1/2022"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini kaldırmak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Etki Alanları & adresleri** sekmesinin seçili olduğunu doğrulayın.

3. **Etki Alanları & adresleri** sekmesinde aşağıdaki adımlardan birini yapın:

   - Kaldırmak istediğiniz girdinin onay kutusunu seçin ve ardından Sil simgesine ![tıklayın.](../../media/m365-cc-sc-delete-icon.png) Görüntülenen **Sil** simgesi.
   - Onay kutusundan başka bir satıra tıklayarak kaldırmak istediğiniz girdiyi seçin. Görüntülenen ayrıntılar açılır listesinde Sil simgesine tıklayın ![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

4. Görüntülenen uyarı iletişim kutusunda **Sil'e** tıklayın.

> [!NOTE]
> Her onay kutusunu seçerek birden çok girdi seçebilir veya **Değer** sütun üst bilgisinin yanındaki onay kutusunu seçerek tüm girişleri seçebilirsiniz.

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-domains-and-email-addresses-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden etki alanları ve e-posta adresleri için izin verme veya engelleme girdilerini kaldırmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>>
```

Bu örnek, etki alanları ve e-posta adresleri için belirtilen blok girişini Kiracı İzin Ver/Engelle Listesinden kaldırır.

```powershell
Remove-TenantAllowBlockListItems -ListType Sender -Entries "adatum.com"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde kimlik sahtekarlığına neden olan gönderenler

### <a name="create-allow-entries-for-spoofed-senders"></a>Sahte gönderenler için izin verme girdileri oluşturma

Sahte gönderenler için blok girdileri oluşturmak için aşağıdaki seçeneklere sahipsiniz:

- [Microsoft 365 Defender portalındaki Gönderimler sayfası](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- [Microsoft 365 Defender portalında](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list) veya [PowerShell'de](#use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list) Kiracı İzin Ver/Engelle Listesi

> [!NOTE]
> Sahte gönderenler için girişlere izin ver, kuruluş içi, kuruluşlar arası ve DMARC kimlik sahtekarlığına dikkat eder.
>
> Yalnızca kimlik sahtekarlığına neden olan kullanıcının *ve* [etki alanı çiftinde](#domain-pair-syntax-for-spoofed-sender-entries) tanımlanan gönderen altyapının kimlik sahtekarlığına izin verilir.
>
> Bir etki alanı çifti için izin ver girişi yapılandırdığınızda, bu etki alanı çiftinden gelen iletiler artık [kimlik sahtekarı zeka içgörülerinde](learn-about-spoof-intelligence.md) görünmez.
>
> Sahte gönderenler için girişlerin süresi hiçbir zaman dolmaz.

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-submissions-portal"></a>Gönderiler portalında sahte gönderenler için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

[Sahtekarlık zekası](learn-about-spoof-intelligence.md) tarafından engellenen iletilerin **Gönderimler** sayfasından Microsoft'a gönderilmesi, göndereni Kiracı İzin Ver/Engelle **Listesi'ndeki Kimlik Sahtekarı gönderenler** sekmesinde izin ver girişi olarak ekler.

> [!NOTE]
> Sahte zeka içgörüsünde kararı geçersiz kıldığınızda, sahte gönderen yalnızca Kiracı İzin Ver/Engelle Listesi'ndeki Sahte **Gönderenler** sekmesinde görünen el ile izin ver veya engelle girdisine dönüşür.
>
> Gönderen kimlik bilgileri sahtekarlığına engellenmemişse, e-posta iletisinin Microsoft'a gönderilmesi Kiracı İzin Ver/Engelle Listesi'nde izin verme girdisi oluşturmaz.

İletiyi raporlama yönergeleri, [Gönderiler portalında etki alanları ve e-posta adresleri için izin veren girişler oluşturmak üzere Microsoft 365 Defender portalını kullanma başlığındaki adımlarla](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal) neredeyse aynıdır.

Tek farklar şunlardır:

- 4. Adımdaki **İzin ver girdisini kaldır** ayarı anlamsızdır çünkü sahte gönderenlerin girdilerinin süresi hiçbir zaman dolmaz.
- 4. Adım'daki **Giriş notuna izin ver** ayarı, Kiracı İzin Ver/Engelle Listesindeki sahte gönderenlerin girdilerine uygulanmaz.

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenler için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Kiracı İzin Ver/Engelle Listesi'nde, kimlik sahtekarlığına maruz olan gönderenler algılanıp kimlik sahtekarı [zekası](learn-about-spoof-intelligence.md) tarafından engellenmeden önce izin verme girdileri oluşturabilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında Sahte **gönderenler** sekmesini seçin ve ekle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Ekle'yi seçin**.

3. Görüntülenen **Yeni etki alanı çiftleri ekle** açılır penceresinde aşağıdaki ayarları yapılandırın:

   - **Joker karakterlerle etki alanı çiftleri ekleme**: Satır başına en fazla 20 etki alanı çifti girin. Kimlik sahtekarlığına neden olan gönderen girdilerinin söz dizimi hakkında ayrıntılı bilgi için, bu makalenin devamında yer alan Sahte [gönderen girişleri için etki alanı çifti söz dizimi](#domain-pair-syntax-for-spoofed-sender-entries) bölümüne bakın.

   - **Kimlik sahtekarı türü**: Aşağıdaki değerlerden birini seçin:
     - **İç**: Sahte gönderen, kuruluşunuza ait bir etki alanındadır ( [kabul edilen bir etki alanı](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Dış**: Sahte gönderen bir dış etki alanında.

   - **Eylem**: **İzin Ver** veya **Engelle'yi** seçin.

   İşiniz bittiğinde **Ekle'ye** tıklayın.

##### <a name="use-powershell-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenler için izin verme girdileri oluşturmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

Bu örnek, kaynak contoso.com gönderen bob@contoso.com için bir izin verme girdisi oluşturur.

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure contoso.com -SpoofedUser bob@contoso.com -SpoofType External
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenler için blok girdileri oluşturmak için Microsoft 365 Defender portalını kullanın

Kimlik sahtekarlığına neden olan gönderenler için blok girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturursunuz.

> [!NOTE]
> Bu gönderenlerden gelen Email iletileri *kimlik avı* olarak engellenir.
>
> Yalnızca kimlik sahtekarlığına neden olan kullanıcının *ve* [etki alanı çiftinde](#domain-pair-syntax-for-spoofed-sender-entries) tanımlanan gönderme altyapısının bileşiminin kimlik sahtekarlığına engellenmesi gerekir.
>
> Bir etki alanı çifti için bir blok girdisi yapılandırdığınızda, bu etki alanı çiftinden gelen iletiler artık [kimlik sahtekarı zeka içgörülerinde](learn-about-spoof-intelligence.md) görünmez.
>
> Sahte gönderenlerin girdilerinin süresi hiçbir zaman dolmaz.

İletiyi raporlama yönergeleri, [Gönderiler portalında etki alanları ve e-posta adresleri için izin veren girişler oluşturmak üzere Microsoft 365 Defender portalını kullanma başlığındaki adımlarla](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal) neredeyse aynıdır.

Tek fark: 4. Adım'daki **Eylem** değeri için **İzin Ver** yerine **Engelle'yi** seçin.

#### <a name="use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenler için blok girdileri oluşturmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Block -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

Bu örnek, 172.17.17.17/24 kaynağından gönderen laura@adatum.com için bir blok girdisi oluşturur.

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure 172.17.17.17/24 -SpoofedUser laura@adatum.com -SpoofType External
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde kimlik sahtekarlığına neden olan gönderenlerin izin verme veya engelleme girdilerini görüntülemek için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Kurallar** bölümünde **İlkeler & kurallar** \> **Tehdit İlkeleri** \> **Kiracı İzin Ver/Engelle Listeleri'ne** gidin. İsterseniz, doğrudan **Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kimlik sahtekarı gönderenler** sekmesinin seçili olduğunu doğrulayın. Aşağıdaki sütunlar kullanılabilir:

   - **Sahte kullanıcı**
   - **Altyapı gönderme**
   - **Kimlik sahtekarı türü**: **İç** veya **Dış** değeri.
   - **Eylem**: **Engelle** veya **İzin Ver** değeri.

   Artan veya azalan düzende sıralamak için sütun başlığına tıklayabilirsiniz.

   Grup simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Sonuçları **Yok**, **Eylem** veya **Kimlik Sahtekarı türüne** göre gruplandırmak için **gruplandırın**.

   Ara simgesine tıklayın ![.](../../media/m365-cc-sc-search-icon.png) **Arama** yapın, bir değerin tamamını veya bir kısmını girin ve ardından belirli bir değeri bulmak için ENTER tuşuna basın. İşiniz bittiğinde Aramayı temizle simgesine tıklayın ![.](../../media/m365-cc-sc-close-icon.png) **Aramayı temizle'yi seçin**.

   Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Sonuçları** filtrelemek için filtreleyin. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:

   - **Eylem**: **İzin Ver** ve **Engelle**.
   - **Kimlik sahtekarı türü**: **İç** ve **Dış**.

   İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

#### <a name="use-powershell-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenlerin izin verme veya engelleme girdilerini görüntülemek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

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

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Verme/Engelleme Listesi'nde kimlik sahtekarlığına neden olan gönderenlerin izin verme veya engelleme girdilerini değiştirmek için Microsoft 365 Defender portalını kullanın

Kiracı İzin Ver/Engelle listesindeki sahte gönderenler için bir izin ver veya engelle girdisini değiştirdiğinizde, girişi yalnızca **İzin Ver'den** **Engelle'ye** veya tam tersi olarak değiştirebilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Sahte gönderenler** sekmesini seçin.

3. **Sahte gönderenler** sekmesinde, değiştirmek istediğiniz girdiyi seçin ve düzenle simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **Düzenle** düğmesi.

4. Görüntülenen Sahte **göndereni düzenle** açılır listesinde **İzin Ver** veya **Engelle'yi** seçin.

5. Bitirdiğinizde, **Kaydet**'i tıklatın.

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde sahte gönderenlerin izin verme veya engelleme girdilerini değiştirmek için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListSpoofItems -Identity Default -Ids <Identity value> -Action <Allow | Block>
```

Bu örnek sahte gönderen girdisini izin ver'den engellemeye değiştirir.

```powershell
Set-TenantAllowBlockListItems -Identity Default -Ids 3429424b-781a-53c3-17f9-c0b5faa02847 -Action Block
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesi'nde kimlik sahtekarlığına neden olan gönderenlerin izin verme veya engelleme girdilerini kaldırmak için Microsoft 365 Defender portalını kullanın

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Sahte gönderenler** sekmesini seçin.

3. **Sahte gönderenler** sekmesinde, kaldırmak istediğiniz girdiyi seçin ve sil simgesine ![tıklayın.](../../media/m365-cc-sc-delete-icon.png) Görüntülenen **Sil** simgesi.

4. Görüntülenen uyarı iletişim kutusunda **Sil'e** tıklayın.

> [!NOTE]
> Her onay kutusunu seçerek veya **Spoofed kullanıcı** sütun üst bilgisinin yanındaki onay kutusunu seçerek tüm girişleri seçerek birden çok girdi seçebilirsiniz.

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-spoofed-senders-from-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinden sahte gönderenlere yönelik izin verme veya engelleme girdilerini kaldırmak için PowerShell kullanma

[Exchange Online PowerShell'de](/powershell/exchange/connect-to-exchange-online-powershell) aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids <Identity value>
```

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids d86b3b4b-e751-a8eb-88cc-fe1e33ce3d0c
```

Bu örnek, belirtilen sahte göndereni kaldırır. ids parametre değerini Get-TenantAllowBlockListSpoofItems komutunun çıktısındaki Identity özelliğinden alırsınız.

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

### <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>Sahte gönderen girişleri için etki alanı çifti söz dizimi

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

Etki alanı çifti eklemek yalnızca kimlik sahtekarlığına sahip kullanıcının *ve* gönderen altyapının *birleşimine* izin verir veya engeller. Kimlik sahtekarı olan kullanıcının herhangi bir kaynaktan gelen e-postasına izin vermez veya sahte kullanıcı için gönderen altyapı kaynağından gelen e-postaya izin vermez.

Örneğin, aşağıdaki etki alanı çifti için bir izin ver girdisi eklersiniz:

- **Etki alanı**: gmail.com
- **Altyapı gönderme**: tms.mx.com

Yalnızca bu etki alanından gelen *ve* altyapı çifti gönderen iletilerin kimlik sahtekarlığına izin verilir. gmail.com sahtekarlık yapmaya çalışan diğer gönderenlere izin verilmez. diğer etki alanlarındaki tms.mx.com gelen gönderenlerden gelen iletiler kimlik sahtekarlığına göre denetleniyor.

> [!NOTE]
> Joker karakterleri gönderen altyapıda veya kimlik sahtekarlığına neden olan kullanıcıda belirtebilirsiniz, ancak her ikisinde de aynı anda belirtemezsiniz. Örneğin, `*, *` izin verilmez.

## <a name="about-impersonated-domains-or-senders"></a>Kimliğine bürünülen etki alanları veya gönderenler hakkında

Office 365 için Microsoft Defender olan kuruluşlarda, [etki alanı veya gönderen kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) tarafından kimliğe bürünme olarak algılanan iletiler için Kiracı/İzin Ver/Engelle Listesinde izin verme girdileri oluşturamazsınız.

Gönderiler portalında <https://security.microsoft.com/reportsubmission>  kimliğine bürünme olarak yanlış engellenmiş bir iletinin bildirilmesi, göndereni veya etki alanını Kiracı İzin Ver/Engelle Listesi'ne izin verme girdisi olarak eklemez.

Bunun yerine, etki alanı veya gönderen, iletiyi algılayan [kimlik avı önleme ilkesinin](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies) **Güvenilen gönderenler ve etki alanları bölümüne** eklenir.

İletiyi raporlama yönergeleri, [Gönderiler portalında etki alanları ve e-posta adresleri için izin verme girdileri oluşturmak üzere Microsoft 365 Defender portalını kullanma başlığındaki adımlarla](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal) aynıdır.

> [!NOTE]
> Şu anda Graf Kimliğe Bürünme işlemine buradan bakılmaz.

## <a name="related-articles"></a>İlgili makaleler

- [Şüpheli istenmeyen posta, kimlik avı, URL'ler, engellenen meşru e-postalar ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanın](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesindeki dosyalara izin ver veya bunları engelle](allow-block-files.md)
- [Kiracı İzin Ver/Engelle Listesinde URL'lere izin ver veya url'leri engelle](allow-block-urls.md)
