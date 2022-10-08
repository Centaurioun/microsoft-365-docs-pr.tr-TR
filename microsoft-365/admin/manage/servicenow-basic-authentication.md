---
title: ServiceNow ile destek tümleştirmesini yapılandırma - Temel Kimlik Doğrulaması
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow için Kapsamlı Sertifikalı uygulama yükleme ve yapılandırma kılavuzu.
ms.openlocfilehash: ed3e7340d91ad3ae997bb27400d81c46ace4773b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191309"
---
# <a name="configure-support-integration-with-servicenow---basic-authentication"></a>ServiceNow ile destek tümleştirmesini yapılandırma - Temel Kimlik Doğrulaması

## <a name="prerequisites-basic-authentication"></a>Önkoşullar (Temel Kimlik Doğrulaması)

Bu önkoşullar **, Microsoft 365 destek tümleştirmesini** ayarlamak için gereklidir.

1. \[AAD Yönetici\] Microsoft 365 kiracınızın altında Azure AD Uygulaması oluşturun.

    1. Microsoft 365 kiracı kimlik bilgilerinizle Azure Portalı'nda oturum açın ve yeni bir uygulama oluşturmak için [Uygulama kayıtları sayfasına](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) gidin.

    1. **Yalnızca bu kuruluş dizinindeki Hesaplar 'ı seçin ({Microsoft-365-tenant-name} yalnızca – Tek kiracı)** ve **Kaydet'i** seçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. **Kimlik doğrulaması'na** gidin ve **Platform ekle'yi** seçin. **Web** seçeneğini belirleyin ve yeniden yönlendirme URL'sini girin:`https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. Uygulama İstemcisi Kimliğini alın ve bir İstemci gizli dizisi oluşturun ve bu değeri alın.

1. \[ServiceNow Yönetici\] ServiceNow'da Giden OAuth Sağlayıcısını ayarlayın.

    Kapsam **Genel** olarak ayarlanmadıysa **Ayarlar &gt; Geliştirici &gt; Uygulamaları'na** gidin ve **Genel'e** geçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, sohbet veya kısa mesaj Açıklama otomatik olarak oluşturuldu":::

1. **Sistem OAuth &gt; Uygulama Kayıt Defteri'ne** gidin.

1. **Üçüncü taraf bir OAuth Sağlayıcısına bağlan** seçeneğini kullanarak ve şu değerleri girerek yeni bir uygulama oluşturun:

    - İstemci Kimliği: Bu, 1. adımda \#oluşturulan uygulamanın İstemci Kimliğidir.

    - İstemci Gizli Anahtarı: Bu, 1. adımda \#oluşturulan uygulamanın İstemci Gizli Anahtarı değeridir.

    - Varsayılan Verme türü: İstemci Kimlik Bilgileri

    - Belirteç URL'si: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Yeniden yönlendirme URL'si: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Gelen OAuth Sağlayıcısını ayarlayın.

    Kapsam **Genel** olarak ayarlanmadıysa, **Ayarlar &gt; Geliştirici &gt; Uygulamaları'na** gidip **Genel'e** geçerek bunu yapın.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, sohbet veya kısa mesaj Açıklama otomatik olarak oluşturuldu":::

1. **Sistem OAuth &gt; Uygulama Kayıt Defteri'ne** gidin.

1. **Dış istemciler için OAuth API uç noktası oluştur** seçeneğini kullanarak yeni bir uygulama oluşturun. Gelen OAuth sağlayıcısını adlandırın ve diğer tüm alanları varsayılan değerleriyle bırakın.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Tümleştirme kullanıcısı oluşturma.

    Bir tümleştirme kullanıcısı belirtmeniz gerekir. Mevcut bir tümleştirme kullanıcınız yoksa veya bu tümleştirme için özel olarak bir tümleştirme oluşturmak istiyorsanız Kuruluş **Kullanıcıları'na &gt;** giderek yeni bir kullanıcı oluşturun.

    Yeni bir tümleştirme kullanıcısı oluşturuyorsanız **Yalnızca Web hizmeti erişimi** seçeneğini işaretleyin. Bu kullanıcıya **olay\_yöneticisi** rolü de vermelisiniz.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[İsteğE BAĞLI\] Hizmetin IP adreslerinin Microsoft 365 destek tümleştirmesine izin verme

Şirketiniz İnternet erişimini kendi ilkelerinizle sınırlandırıyorsa, hem gelen hem de giden API erişimi için aşağıdaki IP adreslerine izin vererek Microsoft 365 destek tümleştirmesi hizmeti için ağ erişimini etkinleştirin:

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Bu terminal komutu, Microsoft 365 destek tümleştirmesi için hizmetin tüm etkin IP'lerini listeler: `nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Microsoft 365 destek Tümleştirme Uygulamasını yapılandırma

Microsoft 365 destek tümleştirme uygulaması Microsoft 365 desteği altında ayarlanabilir.

ServiceNow örneğinizle Microsoft 365 desteği arasındaki tümleştirmeyi ayarlamak için bu adımlar gereklidir.

1. \[ServiceNow Yönetici\] Kapsamı **Microsoft 365 destek tümleştirmesine** geçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Grafik kullanıcı arabirimi, tablo Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Tümleştirme iş akışını açmak için **Microsoft 365 Destek &gt; Kurulumu'na** gidin.

    > [!NOTE]
    > "'x\_mioms\_m365\_assis' kapsamındaki 'oauth\_varlığına karşı okuma işlemi' tablonun kapsamlar arası erişim ilkesi nedeniyle reddedildi" hatasını görürseniz, bunun nedeni tablo erişim ilkenizdir. Tablo oauth\_varlığı için **Tüm uygulama kapsamları &gt; Okunabilir'in** işaretli olduğundan emin olmanız gerekir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Devam etmek için **Kabul Et'i** seçin.

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-1.png" lightbox="../../media/ServiceNow-guide/snowbasic-1.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Ortamı ve kurulum türünü yapılandırın.

    Bu yükleme bir test ortamındaysa Bu bir test ortamıdır seçeneğini belirleyin. Kurulumdan sonra ve tüm testleriniz daha sonra tamamlandıktan sonra bu seçeneği hızla devre dışı bırakabileceksiniz.
    Örneğiniz gelen bağlantılar için Temel Kimlik Doğrulaması'na izin veriyorsa Evet'i seçin, aksi takdirde lütfen [AAD ile Gelişmiş Kurulum'a](servicenow-aad-oauth-token.md) bakın. :::image type="content" source="../../media/ServiceNow-guide/snowbasic-2.png" lightbox="../../media/ServiceNow-guide/snowbasic-2.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Microsoft 365 kiracı etki alanınızı girin.

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-3.png" lightbox="../../media/ServiceNow-guide/snowbasic-3.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Giden ayarlarını yapılandırın.
    1. Azure Active Directory (AAD) Uygulamasını kaydedin.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra **Bitti'ye** tıklayın. Aksi takdirde, AAD'de gerekli uygulama kaydını oluşturmak için sihirbazdaki yönergeleri izleyin.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-4.png" lightbox="../../media/ServiceNow-guide/snowbasic-4.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

    1. ServiceNow OAuth Uygulamasını kaydedin.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, yeni oluşturulan OAuth uygulama kaydını seçin ve İleri'ye tıklayın. Aksi takdirde, ServiceNow'da varlığı oluşturmak için yönergeleri izleyin ve ardından yeni uygulama kaydını seçin.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-5.png" lightbox="../../media/ServiceNow-guide/snowbasic-5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Gelen ayarlarını yapılandırın.
    1. Gelen OAuth API'sinin uç noktasını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, yeni oluşturulan OAuth uygulama kaydını seçin ve Bitti'ye tıklayın. Aksi takdirde, içindeki varlığı oluşturmak için yönergeleri izleyin ve ardından yeni REST uç nokta kaydını seçin.
     
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-6.png" lightbox="../../media/ServiceNow-guide/snowbasic-6.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

    1. Tümleştirme Kullanıcısını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, yeni oluşturulan tümleştirme kullanıcısını seçin ve İleri'ye tıklayın. Aksi takdirde, ServiceNow'da varlığı oluşturmak için yönergeleri izleyin ve ardından yeni tümleştirme kullanıcısını seçin.
    
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-7.png" lightbox="../../media/ServiceNow-guide/snowbasic-7.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::


1. \[Microsoft 365 Kiracı Yönetici\] Microsoft 365 Yönetici Portalında tümleştirmeyi tamamlayın.

    Aşağıdaki bilgilerin doğru olduğunu doğrulayın. Şu anda **İleri'yi** SEÇMEYİN.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama Açıklaması otomatik olarak oluşturuldu":::

1. **Microsoft 365 Yönetici Portal &gt; Ayarları &gt; Kuruluş ayarları &gt; Kuruluş profilleri'ne** gidin.

1. Destek tümleştirme ayarlarını yapılandırın:

    **ServiceNow** **dahili destek aracı** >  > **Temel bilgiler** sekmesini seçin ve **Kimlik Doğrulama Belirteci vermek için Uygulama Kimliği** alanına **Giden Uygulama** Kimliği değerini girin. Bu Giden Uygulama Kimliği, 6. Adım – [Önkoşul (Temel Kimlik Doğrulaması) adım 1'de oluşturulan Tümleştirmeyi Tamamlayın.\#](#prerequisites-basic-authentication)

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. **Depolar** sekmesinde **Yeni depo'yu** seçin ve aşağıdaki ayarlarla güncelleştirin:

    - Depo: 6. Adım – Tümleştirmeyi Tamamla'daki **Depo Kimliği** değeri.

    - Uç Nokta: 6. Adım – Tümleştirmeyi Tamamla'dan **Uç Nokta** değeri.

    - Kimlik doğrulama türü: **Temel Kimlik Doğrulaması'ı** seçin.

    - İstemci Kimliği: 6. Adım – Tümleştirmeyi Tamamla'dan **İstemci Kimliği** değeri.

    - İstemci gizli anahtarı: Önkoşullar (Temel Kimlik Doğrulaması) 3. adımda oluşturulan gelen OAuth sağlayıcısının gizli dizisi \#.

    - Yenileme belirteci süre sonu: 864000

    - Rest kullanıcı adı: 6. Adım – Tümleştirmeyi Tamamla'dan **Kullanıcı Adı** değeri.

    - Kalan kullanıcı parolası: [Önkoşullar (Temel Kimlik Doğrulaması) 4. adımda \#](#prerequisites-basic-authentication)oluşturulan tümleştirme kullanıcısının parolası.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="Grafik kullanıcı arabirimi, uygulama Açıklaması otomatik olarak oluşturur":::

1. ServiceNow'a Geri dön.

1. Tümleştirmeyi tamamlamak için **İleri'yi** seçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="Grafik kullanıcı arabirimi, uygulama, web sitesi Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Bağlantıyı test edin Önceki adımı tamamladıktan sonra **Bağlantıyı test et'e** tıklayın.
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-8.png" lightbox="../../media/ServiceNow-guide/snowbasic-8.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    Microsoft 365 destek tümleştirme uygulaması, tümleştirmenin çalıştığından emin olmak için testler yürütür. Yapılandırmayla ilgili bir sorun varsa, nelerin düzeltilmesi gerektiğini açıklayan bir hata iletisi görüntülenir. Aksi takdirde uygulama hazırdır.
     :::image type="content" source="../../media/ServiceNow-guide/snowbasic-9.png" lightbox="../../media/ServiceNow-guide/snowbasic-9.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Var olan bir kullanıcı için Microsoft destek tümleştirmesini etkinleştirin.

    Microsoft 365 destek tümleştirmesi, şu rollerden birine sahip kullanıcı için etkinleştirilir:

    - x\_mioms\_m365\_assis.insights\_kullanıcısı

    - x\_mioms\_m365\_assis.administrator

1. \[İSTEĞE BAĞLI\] [rol x_mioms_m365_assis.administrator bağlantısına sahip kullanıcı] Microsoft 365 Yönetici hesabı bağlayın.

    Herhangi bir kullanıcı x_mioms_m365_assis.administrator rolüne sahipse ve bir Microsoft 365 destek olayını yönetmek için farklı Microsoft 365 hesapları kullanıyorsa, Microsoft 365 yönetici e-postasını ayarlamak için Microsoft 365 destek > Bağlantı Hesabı'na gitmesi gerekir.
    
    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama Açıklaması otomatik olarak oluşturuldu":::
