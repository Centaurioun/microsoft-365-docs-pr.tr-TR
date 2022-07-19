---
title: Kiracı İzin Ver/Engelle Listesini kullanarak dosyalara izin verme veya dosyaları engelleme
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
description: Yöneticiler, Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde dosyalara izin verme veya dosyaları engelleme hakkında bilgi edinebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a85af4beda791fb9cc2382a48a701406941d0325
ms.sourcegitcommit: 7df8adc9e67ab65e413d7ea7bb0dcb9fd2da1a11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66861952"
---
# <a name="allow-or-block-files-using-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesini kullanarak dosyalara izin verme veya dosyaları engelleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Kiracı İzin Ver/Engelle Listesi'ndeki dosyalara izin vermek veya dosyaları engellemek için Microsoft 365 Defender portalını veya PowerShell'i kullanabilirsiniz.

## <a name="create-block-file-entries"></a>Blok dosyası girdileri oluşturma 

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İlkeler & kuralları** \> **Tehdit İlkeleri** \> **Kuralları** bölümüne **Kiracı İzin Ver/Listeleri Engelle** bölümüne \> gidin. Ya da doğrudan **Kiracı İzin Ver/Engelle Listesi** sayfasına gitmek için kullanın <https://security.microsoft.com/tenantAllowBlockList>.

2. **Kiracı İzin Ver/Engelle Listesi** sayfasında **Dosyalar** sekmesini seçin ve ardından Engelle simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Engelle'ye bakın**.

3. Görüntülenen **Dosyaları engelle** açılır öğesinde aşağıdaki ayarları yapılandırın:
   - **Dosya karmaları ekleme**: Satır başına en fazla 20 SHA256 karma değeri girin.
   - **Hiçbir zaman sona ermez**: Aşağıdaki adımlardan birini yapın:
     - Ayarın kapalı olduğunu doğrulayın (![Kapat.](../../media/scc-toggle-off.png)) ve **Girişlerin** sona erme tarihini belirtmek için Kaldır açık kutusunu kullanın.

     veya

     - Girişleri hiçbir zaman sona ermeyecek şekilde yapılandırmak için iki durumlu düğmeyi sağa taşıyın: ![İki durumlu düğmeyi açın.](../../media/scc-toggle-on.png).
   - **İsteğe bağlı not**: Girişler için açıklayıcı metin girin.

4. İşiniz bittiğinde **Ekle'ye** tıklayın.

> [!NOTE]
> Bu dosyaları içeren e-postalar _kötü amaçlı yazılım_ olarak engellenir.

### <a name="use-powershell"></a>PowerShell kullanma

Kiracı İzin Ver/Engelle Listesi'ne blok dosyası girdileri eklemek için aşağıdaki söz dizimini kullanın:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

Bu örnek, belirtilen dosyalar için hiçbir zaman süresi dolmamış bir blok dosyası girdisi ekler.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-file-entries"></a>İzin ver dosya girdileri oluşturma

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defender kullanma

Microsoft 365 Defender **Gönderiler** sayfasında Dosyalara İzin Ver.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler &** **Gönderimler'e**\> gidin. Veya doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderiler** sayfasında **ekleri Email** sekmesini seçin ve analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

3. Dosyayı veya dosyaları ekleyerek ileti göndermek **için Gözden geçirmek üzere Microsoft'a gönder** açılır penceresini kullanın.

4. **Microsoft'a göndermek için bir neden seçin** bölümünde **Engellenmemiş olmalıdır (hatalı pozitif)** seçeneğini belirleyin.

5. **Bu gibi dosyalara izin ver** seçeneğini açın.

6. **Sonra kaldır** açılan listesinden, izin verme seçeneğinin ne kadar süreyle çalışmasını istediğinizi belirtin.

7. **İsteğe Bağlı Notu** kullanarak neden allow eklediğinizi ekleyin. 

8. İşiniz bittiğinde **Gönder** düğmesine tıklayın.

  :::image type="content" source="../../media/submit-email-for-analysis.png" alt-text="Analiz için e-posta gönderin." lightbox="../../media/submit-email-for-analysis.png":::

> [!NOTE]
>
> Dosyayla yeniden karşılaşıldığında, patlama veya itibar denetimleri için gönderilmez ve diğer tüm dosya tabanlı filtreler atlanır. Posta akışı sırasında, filtrelerin geri kalanı temizlenecek dosyayı içeren e-postayı bulursa, e-posta teslim edilecek.

## <a name="view-file-entries"></a>Dosya girdilerini görüntüleme 

Kiracı İzin Ver/Engelle Listesi'nde blok dosyası girdilerini görüntülemek için aşağıdaki söz dizimini kullanın:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

Bu örnek, belirtilen dosya karması değeri için bilgi döndürür.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-file-entries"></a>Dosya girdilerini değiştirme

Kiracı İzin Ver/Engelle Listesi'ndeki izin ver veya engelle dosya girdilerini değiştirmek için aşağıdaki söz dizimini kullanın:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-file-entries"></a>Dosya girdilerini kaldırma 

Kiracı İzin Ver/Engelle Listesinden izin ver veya engelle dosya girdilerini kaldırmak için aşağıdaki söz dizimini kullanın:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN">
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="related-articles"></a>İlgili makaleler

- [Yönetici gönderimleri](admin-submission.md)
- [Hatalı pozitifleri ve hatalı negatifleri raporlama](report-false-positives-and-false-negatives.md)
- [Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin](manage-tenant-allow-block-list.md)
- [Kiracı İzin Ver/Engelle Listesinde e-postalara izin ver veya e-postaları engelle](allow-block-email-spoof.md)
- [Kiracı İzin Ver/Engelle Listesinde URL'lere izin ver veya url'leri engelle](allow-block-urls.md)
