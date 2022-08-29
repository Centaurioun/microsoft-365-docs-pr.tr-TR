---
title: Gönderimleri yönetme
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: seo-marvel-apr2020
description: Yöneticiler, Microsoft 365 Defender portalında Gönderiler portalını kullanarak engellenen, şüpheli e-posta, şüpheli kimlik avı e-postası, istenmeyen posta, diğer zararlı olabilecek iletiler, URL'ler ve e-posta eklerini yeniden keşfetmek üzere Microsoft'a yasal e-posta göndermeyi öğrenebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 692bef65a37f1411952e3848147913a64daf72a1
ms.sourcegitcommit: c81f6c39ed39d017f9d7c5f13148cd8d17b25c3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67393031"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-legitimate-email-getting-blocked-and-email-attachments-to-microsoft"></a>Şüpheli istenmeyen posta, kimlik avı, URL'ler, engellenen meşru e-postalar ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanın

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)

Exchange Online posta kutularına sahip Microsoft 365 kuruluşlarında, yöneticiler e-posta iletilerini, URL'leri ve ekleri tarama için Microsoft'a göndermek için Microsoft 365 Defender portalındaki Gönderimler portalını kullanabilir.

Analiz için bir e-posta iletisi gönderdiğinizde şunları alırsınız:

- **kimlik doğrulaması denetimi Email**: E-posta kimlik doğrulamasının teslim edildiğinde geçirilip geçirilmediğine veya başarısız olmasına ilişkin ayrıntılar.
- **İlke isabetleri**: Hizmet filtresi kararlarımızı geçersiz kılarak kiracınıza gelen e-postaya izin veren veya engelleyen ilkeler hakkında bilgiler.
- **Payload reputation/detonation**: İletideki URL'lerin ve eklerin güncel incelemesi.
- **Not veren analizi**: İletilerin kötü amaçlı olup olmadığını onaylamak için insan not verenler tarafından yapılan gözden geçirme.

> [!IMPORTANT]
> Payload reputation/detonation ve grader analizi tüm kiracılarda yapılmaz. Verilerin uyumluluk amacıyla kiracı sınırından ayrılması gerekmediğinde bilgilerin kuruluş dışına çıkışı engellenir.

E-posta iletilerini, URL'leri ve ekleri Microsoft'a göndermenin diğer yolları için bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md).

Değerlendirme için Microsoft'a ileti göndermek üzere Office 365 için Microsoft Defender'daki yönetici gönderimlerini kullanmayı öğrenmek için bu kısa videoyu izleyin.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBLPn]

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com/>açarsınız. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

- Microsoft'a ileti ve dosya göndermek için aşağıdaki rollerden birine sahip olmanız gerekir:
  - [Microsoft 365 Defender portalında](permissions-microsoft-365-security-center.md) **Güvenlik Yöneticisi** veya **Güvenlik Okuyucusu**.

    Bu rollerden birinin, bu makalenin sonraki bölümlerinde açıklandığı gibi [özel posta kutusuna kullanıcı gönderimlerini görüntülemek için](#view-user-submissions-to-microsoft) gerekli olduğunu unutmayın.

- Posta kutusunda hala kullanılabiliyorsa ve kullanıcı veya başka bir yönetici tarafından temizlenmediyse, yöneticiler 30 gün kadar eski iletiler gönderebilir.

- Yönetici gönderimleri aşağıdaki fiyatlarla kısıtlanır:
  - Herhangi bir 15 dakika içinde en fazla gönderim: 150 gönderim
  - 24 saatlik bir süre içinde aynı gönderimler: 3 gönderim
  - 15 dakikalık bir süre içinde aynı gönderimler: 1 gönderim

- Kullanıcıların iletileri ve dosyaları Microsoft'a nasıl gönderebileceği hakkında daha fazla bilgi için bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md).

## <a name="report-questionable-email-to-microsoft"></a>Sorgulanabilir e-postayı Microsoft'a bildirme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **E-postalar** sekmesinin seçili olduğunu doğrulayın.

3. **E-postalar** sekmesinde Analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderim türünü seçin**: **Email** değerinin seçili olduğunu doğrulayın.

   - **Ağ iletisi kimliğini ekleyin veya e-posta dosyasını karşıya yükleyin**: Aşağıdaki seçeneklerden birini seçin:

     - **E-posta ağ iletisi kimliğini ekleyin**: Bu, karantinaya alınan iletilerdeki **X-MS-Exchange-Organization-Network-Message-Id** üst bilgisinde veya **X-MS-Office365-Filtering-Correlation-Id** üst bilgisinde bulunan bir GUID değeridir.

     - **E-posta dosyasını (.msg veya .eml) karşıya yükleyin**: **Dosyalara gözat'a** tıklayın. Açılan iletişim kutusunda .eml veya .msg dosyasını bulup seçin ve **aç'a** tıklayın.

   - **Sorunu olan bir alıcı seçin**: İlke denetimini çalıştırmak istediğiniz alıcıyı belirtin. İlke denetimi, e-postanın kullanıcı veya kuruluş ilkeleri nedeniyle taramayı atlayıp atlamadığını belirler.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmemesi gerektiğini doğrulayın (Hatalı pozitif)** seçildi.

     - **E-posta şu şekilde kategorilere ayrılmış olmalıdır**: **Kimlik Avı**, **Kötü Amaçlı Yazılım** veya **İstenmeyen Posta'yı** seçin. Emin değilseniz, en iyi kararınızı kullanın.

     - **Bu gönderenden veya etki alanından gelen tüm e-postaları engelle**: Kiracı İzin Ver/Engelle Listesinde gönderen için bir engelleme girdisi oluşturmak için bu seçeneği belirleyin. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

       Bu seçeneği seçtikten sonra aşağıdaki ayarlar kullanılabilir:

       - Varsayılan olarak **Gönderen** seçilidir, ancak bunun yerine **Etki Alanı'yı** seçebilirsiniz.

       - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **90 gün**
           - **Hiçbir zaman süresi dolmaz**
           - **Belirli bir tarih**

       - **Giriş notunu engelle**: Bu e-postaya neden izin kullandığınız hakkında isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

> :::image type="content" source="../../media/admin-submission-email-block.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı negatif (hatalı) bir e-posta gönderin." lightbox="../../media/admin-submission-email-block.png":::

> [!NOTE]
> Kimlik [sahtekarlık zekası](learn-about-spoof-intelligence.md) tarafından yanlış engellenen iletiler için, Kiracı İzin Ver/Engelle Listesinde etki alanı çifti için bir blok girdisi oluşturulmaz.
>
> [Etki alanı veya kullanıcı kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) tarafından yanlış engellenen iletiler için, Kiracı İzin Ver/Engelle Listesi'nde etki alanı veya gönderen için bir engelleme girdisi oluşturulmaz. Bunun yerine, etki alanı veya gönderen, iletiyi algılayan [kimlik avı önleme ilkesinin](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies) **Güvenilen gönderenler ve etki alanları bölümüne** eklenir.
>
> Bir dosyayı **Engellenmemeli (Hatalı pozitif)** olarak raporlamak için bkz. [gönderimler portalında etki alanları ve e-posta adresleri için izin verme girdileri oluşturmak üzere Microsoft 365 Defender portalını kullanma](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal).

## <a name="report-questionable-email-attachments-to-microsoft"></a>Sorgulanabilir e-posta eklerini Microsoft'a bildirme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderiler** sayfasında **ekleri Email** sekmesini seçin.

3. **Email ekler** sekmesinde Analiz için Microsoft'a Gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderim türünü seçin**: **Ekin seçili Email** değeri doğrulayın.

   - **Dosya**: Dosyalara **gözat'a** tıklayarak göndermek istediğiniz dosyayı bulun ve seçin.

     > [!NOTE]
     > Dosya gönderimleri, verilerin ortamdan ayrılmasına izin verilmeyen bulutlarda kullanılamaz. **Dosyalara göz atma** gri renktedir.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmiş Olması Gerektiğini Doğrula (Hatalı negatif)** öğesinin seçili olduğunu doğrulayın.

     - **E-posta şu şekilde kategorilere ayrılmış olmalıdır**: **Kimlik Avı** veya **Kötü Amaçlı Yazılım'ı** seçin. Emin değilseniz, en iyi kararınızı kullanın.

     - **Bu dosyayı engelle**: Kiracı İzin Ver/Engelle Listesinde gönderen için bir blok girdisi oluşturmak için bu seçeneği belirleyin. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

       Bu seçeneği seçtikten sonra aşağıdaki ayarlar kullanılabilir:

       - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **90 gün**
           - **Hiçbir zaman süresi dolmaz**
           - **Belirli bir tarih**

       - **Giriş notunu engelle**: Bu e-postaya neden izin kullandığınız hakkında isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

> :::image type="content" source="../../media/admin-submission-file-block.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı negatif (hatalı) bir e-posta eki gönderin." lightbox="../../media/admin-submission-file-block.png":::

 > [!NOTE]
 > Bir dosyayı **Engellenmemeli (Hatalı pozitif)** olarak raporlamak için bkz. [Gönderimler portalında dosyalar için izin verme girdileri oluşturmak üzere Microsoft 365 Defender portalını kullanma](allow-block-files.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-files-in-the-submissions-portal).

## <a name="report-questionable-urls-to-microsoft"></a>Sorgulanabilir URL'leri Microsoft'a bildirme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **URL'ler** sekmesini seçin.

3. **URL'ler** sekmesinde Analiz için Microsoft'a Gönder simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) **Analiz için Microsoft'a gönderin**.

4. Görüntülenen **Analiz için Microsoft'a gönder** açılır öğesinde aşağıdaki bilgileri girin:

   - **Gönderme türünü seçin**: Değer **URL'sinin** seçili olduğunu doğrulayın.

   - **URL**: Tam URL'yi (örneğin, `https://www.fabrikam.com/marketing.html`) girin ve görüntülenen kutudan seçin.

     > [!NOTE]
     > URL gönderimleri, verilerin ortamdan ayrılmasına izin verilmeyen bulutlarda kullanılamaz. **URL** gri renkte.

   - **Microsoft'a göndermek için bir neden seçin**: **Engellenmiş Olması Gerektiğini Doğrula (Hatalı negatif)** öğesinin seçili olduğunu doğrulayın.

     - **E-posta şu şekilde kategorilere ayrılmış olmalıdır**: **Kimlik Avı** veya **Kötü Amaçlı Yazılım'ı** seçin. Emin değilseniz, en iyi kararınızı kullanın.

     - **Bu URL'yi engelle**: Kiracı İzin Ver/Engelle Listesinde gönderen için bir blok girdisi oluşturmak için bu seçeneği belirleyin. Kiracı İzin Ver/Engelle Listesi hakkında daha fazla bilgi için bkz. [Kiracı İzin Ver/Engelle Listesi'nde izin verme ve bloklarınızı yönetme](manage-tenant-allow-block-list.md).

       Bu seçeneği seçtikten sonra aşağıdaki ayarlar kullanılabilir:

       - **Engelleme girdisini kaldır**: Varsayılan değer **30 gündür**, ancak aşağıdaki değerlerden birini seçebilirsiniz:
           - **1 gün**
           - **7 gün**
           - **30 gün**
           - **90 gün**
           - **Hiçbir zaman süresi dolmaz**
           - **Belirli bir tarih**

       - **Giriş notunu engelle**: Bu e-postaya neden izin kullandığınız hakkında isteğe bağlı bilgileri girin.

   İşiniz bittiğinde **Gönder'e** ve ardından **Bitti'ye** tıklayın.

> :::image type="content" source="../../media/admin-submission-url-block.png" alt-text="Defender portalındaki Gönderimler sayfasında analiz için Microsoft'a hatalı negatif (hatalı) bir URL gönderin." lightbox="../../media/admin-submission-url-block.png":::

 > [!NOTE]
 > Url'yi **Engellenmemesi Gerekir (Hatalı pozitif)** olarak bildirmek için bkz. [Gönderimler portalında URL'ler için izin veren girişler oluşturmak üzere Microsoft 365 Defender portalını kullanma](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal).

## <a name="view-email-admin-submissions-to-microsoft"></a>Microsoft'a e-posta yöneticisi gönderimlerini görüntüleme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **E-postalar** sekmesinin seçili olduğunu doğrulayın.

   - Kullanılabilir bir sütun üst bilgisine tıklayarak girişleri sıralayabilirsiniz.

   - Sütunları özelleştir simgesine tıklayın ![.](../../media/m365-cc-sc-customize-icon.png) Görüntülemek istediğiniz sütunları seçmek için sütunları **özelleştirin**. Varsayılan değerler yıldız işaretiyle (\*):
     - **Gönderim adı**<sup>\*</sup>
     - **Gönderen**<sup>\*</sup>
     - **Alıcı**
     - **Gönderilme tarihi**<sup>\*</sup>
     - **Gönderme nedeni**<sup>\*</sup>
     - **Durum**<sup>\*</sup>
     - **Sonuç**<sup>\*</sup>
     - **Filtre kararı**
     - **Teslim/Engelleme nedeni**
     - **Gönderim Kimliği**
     - **Ağ İletisi Kimliği/Nesne Kimliği**
     - **Yön**
     - **Gönderen IP'i**
     - **Toplu uyumlu düzey (BCL)**
     - **Hedef**
     - **İlke eylemi**
     - **Gönderen**
     - **Kimlik avı benzetimi**
     - **Etiketler**<sup>\*</sup>
     - **İzin ver**

     İşiniz bittiğinde **Uygula'ya** tıklayın.

     :::image type="content" source="../../media/admin-submission-email-customize-columns.png" alt-text="E-posta yöneticisi gönderimleri için sütunları özelleştir seçeneği." lightbox="../../media/admin-submission-email-customize-columns.png":::

   - Girişleri filtrelemek için Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Filtrele'ye bakın**. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:
     - **Gönderilme tarihi**: **Başlangıç tarihi** ve **Bitiş tarihi** değerleri.
     - **Gönderme Kimliği**: Her gönderime atanan bir GUID değeri.
     - **Ağ İletisi Kimliği**
     - **Gönderen**
     - **Alıcı**
     - **Ad**
     - **Gönderen**
     - **Gönderme nedeni**: **Gereksiz değil**, **Kimlik Avı**, **Kötü Amaçlı Yazılım** ve **İstenmeyen Posta** değerleri.
     - **Durum**: **Bekleyen** ve **Tamamlanan** değerler.
     - **Etiketler**: Varsayılan değer **Tümü'dür** veya açılan listeden bir [kullanıcı etiketi](user-tags.md) seçin.

     İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

     :::image type="content" source="../../media/admin-submission-email-filters.png" alt-text="E-posta yöneticisi gönderimleri için filtre seçenekleri." lightbox="../../media/admin-submission-email-filters.png":::

   - Girişleri gruplandırmak için Gruplandır simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Açılan listeden aşağıdaki değerlerden birini **gruplandırın** ve seçin:
     - **Yok**
     - **Neden**
     - **Durum**
     - **Sonuç**
     - **Etiketler**

   - Girdileri dışarı aktarmak için Dışarı Aktar simgesine tıklayın ![.](../../media/m365-cc-sc-download-icon.png) **Dışarı aktarın**. Görüntülenen iletişim kutusunda .csv dosyasını kaydedin.

## <a name="view-email-attachment-admin-submissions-to-microsoft"></a>Microsoft'a e-posta eki yönetici gönderimlerini görüntüleme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderiler** sayfasında, **Email ekler** sekmesinin seçili olduğunu doğrulayın.

   - Kullanılabilir bir sütun üst bilgisine tıklayarak girişleri sıralayabilirsiniz.

   - Sütunları özelleştir simgesine tıklayın ![.](../../media/m365-cc-sc-customize-icon.png) Görüntülemek istediğiniz sütunları seçmek için sütunları **özelleştirin**. Varsayılan değerler yıldız işaretiyle (\*):
     - **Ek dosya adı**<sup>\*</sup>
     - **Gönderilme tarihi**<sup>\*</sup>
     - **Gönderme nedeni**<sup>\*</sup>
     - **Durum**<sup>\*</sup>
     - **Sonuç**<sup>\*</sup>
     - **Filtre kararı**
     - **Teslim/Engelleme nedeni**
     - **Gönderim Kimliği**
     - **Nesne Kimliği**
     - **İlke eylemi**
     - **Gönderen**
     - **Etiketler**<sup>\*</sup>
     - **İzin ver**

     İşiniz bittiğinde **Uygula'ya** tıklayın.

     :::image type="content" source="../../media/admin-submission-file-customize-columns.png" alt-text="E-posta eki yönetici gönderimleri için sütun seçeneklerini özelleştirin.":::

   - Girişleri filtrelemek için Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Filtrele'ye bakın**. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:
     - **Gönderilme tarihi**: **Başlangıç tarihi** ve **Bitiş tarihi**.
     - **Gönderme Kimliği**: Her gönderime atanan bir GUID değeri.
     - **Ek dosya adı**
     - **Gönderen**
     - **Gönderme nedeni**
     - **Durum**
     - **Etiketler**: Varsayılan değer **Tümü'dür** veya açılan listeden bir [kullanıcı etiketi](user-tags.md) seçin.

     İşiniz bittiğinde **Uygula'ya** tıklayın.

     :::image type="content" source="../../media/admin-submission-file-filters.png" alt-text="E-posta eki yönetici gönderimleri için filtre seçenekleri.":::

   - Girişleri gruplandırmak için Gruplandır simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Açılan listeden aşağıdaki değerlerden birini **gruplandırın** ve seçin:
     - **Yok**
     - **Neden**
     - **Durum**
     - **Sonuç**
     - **Etiketler**

   - Girdileri dışarı aktarmak için Dışarı Aktar simgesine tıklayın ![.](../../media/m365-cc-sc-download-icon.png) **Dışarı aktarın**. Görüntülenen iletişim kutusunda .csv dosyasını kaydedin.

## <a name="view-urls-admin-submissions-to-microsoft"></a>Microsoft'a yapılan URL'ler yönetici gönderimlerini görüntüleme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **URL'ler** sekmesinin seçili olduğunu doğrulayın.

   - Kullanılabilir bir sütun üst bilgisine tıklayarak girişleri sıralayabilirsiniz.

   - Sütunları özelleştir simgesine tıklayın ![.](../../media/m365-cc-sc-customize-icon.png) Görüntülemek istediğiniz sütunları seçmek için sütunları **özelleştirin**. Varsayılan değerler yıldız işaretiyle (\*):
     - **Url**<sup>\*</sup>
     - **Gönderilme tarihi**<sup>\*</sup>
     - **Gönderme nedeni**<sup>\*</sup>
     - **Durum**<sup>\*</sup>
     - **Sonuç**<sup>\*</sup>
     - **Filtre kararı**
     - **Teslim/Engelleme nedeni**
     - **Gönderim Kimliği**
     - **Nesne Kimliği**
     - **İlke eylemi**
     - **Gönderen**
     - **Etiketler**<sup>\*</sup>
     - **İzin ver**

     İşiniz bittiğinde **Uygula'ya** tıklayın.

     :::image type="content" source="../../media/admin-submission-url-customize-columns.png" alt-text="URL yöneticisi gönderimleri için sütun seçeneklerini özelleştirin.":::

   - Girişleri filtrelemek için Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Filtrele'ye bakın**. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:
     - **Gönderilme tarihi**: **Başlangıç tarihi** ve **Bitiş tarihi**.
     - **Gönderme Kimliği**: Her gönderime atanan bir GUID değeri.
     - **Url**
     - **Gönderen**
     - **Gönderme nedeni**
     - **Durum**
     - **Etiketler**: Varsayılan değer **Tümü'dür** veya açılan listeden bir [kullanıcı etiketi](user-tags.md) seçin.

     İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

     :::image type="content" source="../../media/admin-submission-url-filters.png" alt-text="URL yöneticisi gönderimleri için filtre seçenekleri.":::

   - Girişleri gruplandırmak için Gruplandır simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Açılan listeden aşağıdaki değerlerden birini **gruplandırın** ve seçin:
     - **Yok**
     - **Neden**
     - **Durum**
     - **Sonuç**
     - **Etiketler**

   - Girdileri dışarı aktarmak için Dışarı Aktar simgesine tıklayın ![.](../../media/m365-cc-sc-download-icon.png) **Dışarı aktarın**. Görüntülenen iletişim kutusunda .csv dosyasını kaydedin.

## <a name="admin-submission-result-details"></a>gönderim sonucu ayrıntılarını Yönetici

Yönetici gönderimlerinde gönderilen iletiler Microsoft tarafından gözden geçirilir ve gönderim ayrıntıları açılır öğesinde gösterilen sonuçlar:

- Teslim sırasında gönderenin e-posta kimlik doğrulamasında hata olup olmadığı.
- İletiyle ilgili kararı etkilemiş veya geçersiz kılmış olabilecek bir ilke eşleşmesi hakkında bilgi.
- İletide yer alan URL’lerin veya dosyaların kötü amaçlı olup olmadığını görmek için geçerli etkisizleştirme sonuçları.
- Not verenlerden geri bildirim.

Geçersiz kılma bulunduysa, sonucun birkaç dakika içinde kullanılabilir olması gerekir. E-posta kimlik doğrulamasında bir sorun yoksa veya teslim bir geçersiz kılmadan etkilenmediyse, not verenlerin geri bildirimleri bir gün kadar sürebilir.

## <a name="view-user-submissions-to-microsoft"></a>Microsoft'a kullanıcı gönderimlerini görüntüleme

[Rapor İletisi eklentisini](enable-the-report-message-add-in.md), [Rapor Kimlik Avı eklentisini](enable-the-report-phish-add-in.md) dağıttıysanız veya kişiler [Web üzerinde Outlook'da yerleşik raporlamayı](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) kullanıyorsa, **kullanıcının bildirdiği ileti** sekmesinde kullanıcıların ne bildirdiğini görebilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Eylemler & Gönderimler sayfasındaki Gönderimler** \> **sayfasına gidin**. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Gönderimler** sayfasında **Kullanıcı tarafından bildirilen iletiler** sekmesini seçin.

   - Sütunları özelleştir simgesine tıklayın ![.](../../media/m365-cc-sc-customize-icon.png) Görüntülemek istediğiniz sütunları seçmek için sütunları **özelleştirin**. Varsayılan değerler yıldız işaretiyle (\*):
     - **Email konu**<sup>\*</sup>
     - **Rapor eden**<sup>\*</sup>
     - **Bildirilen tarih**<sup>\*</sup>
     - **Gönderen**<sup>\*</sup>
     - **Bildirilen neden**<sup>\*</sup>
     - **Sonuç**<sup>\*</sup>
     - **İleti bildirilen kimlik**
     - **Ağ İletisi Kimliği**
     - **Gönderen IP'i**
     - **Bildirilen kaynak**
     - **Kimlik avı benzetimi**
     - **Yönetici gönderimine dönüştürüldü**
     - **Etiketler**<sup>\*</sup>
     - **olarak işaretlendi**<sup>\*</sup>
     - **İşaretlenen**
     - **İşaretlenen tarih**

     İşiniz bittiğinde **Uygula'ya** tıklayın.

   - Girişleri filtrelemek için Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Filtrele'ye bakın**. Görüntülenen **Filtre** açılır penceresinde aşağıdaki değerler kullanılabilir:
     - **Bildirilen tarih**: **Başlangıç tarihi** ve **Bitiş tarihi**.
     - **Rapor eden**
     - **Email konu**
     - **İleti bildirilen kimlik**
     - **Ağ İletisi Kimliği**
     - **Gönderen**
     - **Bildirilen neden**: **Gereksiz değil**, **Kimlik Avı veya İstenmeyen** **Posta** değerleri.
     - **Bildirilen kaynak**: **Microsoft eklentisi** veya **Üçüncü taraf eklentisi** değerleri.
     - **Kimlik avı benzetimi**: **Evet** veya **Hayır** değerleri.
     - **Yönetici gönderimine dönüştürüldü**: **Evet** veya **Hayır** değerleri.
     - **Etiketler**: Varsayılan değer **Tümü'dür** veya açılan listeden bir [kullanıcı etiketi](user-tags.md) seçin.

     İşiniz bittiğinde **Uygula'ya** tıklayın. Mevcut filtreleri temizlemek için **Filtreyi** temizle simgesi](../../media/m365-cc-sc-clear-filters-icon.png) Filtre açılır öğesindeki **Filtreleri temizle'ye** tıklayın![.

     > :::image type="content" source="../../media/admin-submission-user-reported-filters.png" alt-text="Kullanıcı gönderimleri için filtre seçenekleri." lightbox="../../media/admin-submission-user-reported-filters.png":::

   - Girişleri gruplandırmak için Gruplandır simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) Açılan listeden aşağıdaki değerlerden birini **gruplandırın** ve seçin:
     - **Yok**
     - **Neden**
     - **Gönderen**
     - **Rapor eden**
     - **Sonuç**
     - **Bildirilen kaynak**
     - **Kimlik avı benzetimi**
     - **Yönetici gönderimine dönüştürüldü**
     - **Etiketler**

   - Girdileri dışarı aktarmak için Dışarı Aktar simgesine tıklayın ![.](../../media/m365-cc-sc-download-icon.png) **Dışarı aktarın**. Görüntülenen iletişim kutusunda .csv dosyasını kaydedin.

   - Kullanıcıları bilgilendirmek için bkz. [Yönetici Bildirilen iletileri gözden geçirme](admin-review-reported-message.md)

> [!NOTE]
> Kuruluşlar, kullanıcı tarafından bildirilen iletileri [yalnızca özel posta kutusuna](user-submission.md) gönderecek şekilde yapılandırılmışsa, bildirilen iletiler **Kullanıcı tarafından bildirilen iletiler'de** görünür ancak sonuçları her zaman boş olur (çünkü bunlar yeniden taramazlardı).

## <a name="undo-user-submissions"></a>Kullanıcı gönderimlerini geri alma

Kullanıcı özel posta kutusuna şüpheli bir e-posta gönderdikten sonra, kullanıcı ve yöneticinin gönderimi geri alma seçeneği yoktur. Kullanıcı e-postayı kurtarmak isterse, Silinmiş Öğeler veya Gereksiz Email klasörlerinde kurtarma için kullanılabilir.

## <a name="convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>Kullanıcı tarafından bildirilen iletileri özel posta kutusundan yönetici gönderimine dönüştürme

Özel posta kutusunu, iletileri Microsoft'a göndermeden kullanıcı tarafından bildirilen iletileri kesecek şekilde yapılandırdıysanız, analiz için belirli iletileri bulabilir ve Microsoft'a gönderebilirsiniz.

**Kullanıcı tarafından bildirilen iletiler** sekmesinde, listeden bir ileti seçin ve Analiz için Microsoft'a gönder simgesine tıklayın![.](../../media/m365-cc-sc-submit-user-reported-message-icon.png) **Analiz için Microsoft'a gönderin** ve açılan listeden aşağıdaki değerlerden birini seçin:

- **Rapor temizleme**
- **Kimlik avı bildirme**
- **Kötü amaçlı yazılımları bildirme**
- **İstenmeyen posta bildirme**
- **Araştırmayı tetikleme**

  :::image type="content" source="../../media/admin-submission-user-reported-submit-button-options.png" alt-text="Eylem düğmesindeki Yeni seçenekler" lightbox="../../media/admin-submission-user-reported-submit-button-options.png":::

İleti Microsoft'a bildirilirse, **Yöneticiye dönüştürülen gönderim** değeri **hayır'dan** **evet'e** dönüşür. İlgili kullanıcı tarafından bildirilen iletinin gönderim açılır öğesi içindeki taşma **menüsünden Dönüştürülmüş yönetici gönderimini görüntüle'ye** tıklayarak doğrudan yönetici gönderimine erişebilirsiniz.

:::image type="content" source="../../media/view-converted-admin-submission.png" alt-text="Kullanıcı tarafından bildirilen bir iletiden oluşturulan yönetici gönderimini görüntüleme seçeneği.":::

## <a name="view-associated-alert-for-user-and-admin-email-submissions"></a>Kullanıcı ve yönetici e-posta gönderimleri için ilişkili uyarıyı görüntüleme

> [!IMPORTANT]
> Bu bölümdeki bilgiler yalnızca plan 2 veya üzeri Office 365 için Defender için geçerlidir.
>
> Şu anda, kullanıcı gönderimleri yalnızca kimlik avı olarak bildirilen iletiler için uyarılar oluşturur.

Bildirilen her kullanıcı için kimlik avı iletisi ve yönetici e-posta gönderimi için ilgili uyarı oluşturulur.

Kullanıcı tarafından bildirilen kimlik avı iletisine karşılık gelen uyarıyı görüntülemek için **, Kullanıcı tarafından bildirilen iletiler** sekmesini seçin ve ardından iletiye çift tıklayarak gönderim açılır öğesini açın. Diğer seçenekler simgesine tıklayın ![.](../../media/m365-cc-sc-more-actions-icon.png) **Diğer seçenekler** ve ardından  **Uyarıyı görüntüle'yi** seçin.

:::image type="content" source="../../media/alert-from-user-submission.png" alt-text="Kullanıcı tarafından bildirilen kimlik avı iletisinden ilgili uyarıyı görüntüleme seçeneği.":::

Yönetici e-posta gönderimlerine karşılık gelen uyarıyı görüntülemek için **E-postalar** sekmesini seçin ve ardından iletiye çift tıklayarak gönderim açılır öğesini açın. **E-posta varlığını aç** seçeneğinde **Uyarıyı görüntüle'yi** seçin.

:::image type="content" source="../../media/alert-from-admin-submission.png" alt-text="Bir yönetici gönderiminden ilgili uyarıyı görüntüleme seçeneği.":::
