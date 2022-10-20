---
title: Azure AD Kimlik Doğrulama Belirteci ile Microsoft 365 destek tümleştirmesini yapılandırma
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
ms.openlocfilehash: 724517e0ac268ecc1d857f59b3e0352cecfd1903
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68624851"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>Azure AD Kimlik Doğrulama Belirteci ile Microsoft 365 destek tümleştirmesini yapılandırma

## <a name="prerequisites-azure-ad-auth-token"></a>Önkoşullar (Azure AD Kimlik Doğrulama Belirteci)

Bu önkoşullar, Microsoft 365 destek tümleştirmesini ayarlamak için gereklidir.

1. \[AAD Yönetici\] Microsoft 365 kiracınız altında Giden için Azure AD Uygulaması Oluşturun.

    1. Microsoft 365 kiracı kimlik bilgilerinizle Azure Portalı'nda oturum açın ve yeni bir uygulama oluşturmak için [Uygulama kayıtları sayfasına](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) gidin.

    2. **Yalnızca bu kuruluş dizinindeki Hesaplar 'ı seçin ({Microsoft-365-tenant-name} yalnızca – Tek kiracı)** ve **Kaydet'i** seçin.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. **Kimlik doğrulaması'na** gidin ve **Platform ekle'yi** seçin. **Web** seçeneğini belirleyin ve yeniden yönlendirme URL'sini girin:`https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. Uygulama İstemcisi Kimliğini alın ve bir İstemci gizli dizisi oluşturun ve bu değeri alın.

1. \[AAD Yönetici\] Microsoft 365 kiracınız altında Rest için Azure AD Uygulaması oluşturun.

    1. Microsoft 365 kiracı kimlik bilgilerinizle [Azure Portalı'nda](https://portal.azure.com/) oturum açın ve yeni bir uygulama oluşturmak için Uygulama kayıtları sayfasına gidin.

    1. **Yalnızca {(Microsoft-365-tenant-name} yalnızca – Tek kiracı) kuruluş dizinindeki Hesaplar'ı** seçin.

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. Uygulama İstemcisi Kimliğini alın ve bir İstemci gizli dizisi oluşturun ve bu değeri alın.

1. \[AAD Yönetici\] Microsoft 365 kiracınız altında Rest User için bir Azure AD Uygulaması oluşturun.

    1. Microsoft 365 kiracı kimlik bilgilerinizle [Azure Portalı'nda](https://portal.azure.com/) oturum açın ve yeni bir uygulama oluşturmak için Uygulama kayıtları sayfasına gidin.

    1. **Yalnızca {(Microsoft-365-tenant-name} yalnızca – Tek kiracı) kuruluş dizinindeki Hesaplar'ı** seçin.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. Uygulama İstemcisi Kimliğini alın ve bir İstemci gizli dizisi oluşturun ve bu değeri alın.

1. \[ServiceNow Yönetici\] ServiceNow'da Giden OAuth Sağlayıcısını ayarlayın.

    Kapsam **Genel** olarak ayarlanmadıysa, **Ayarlar &gt; Geliştirici &gt; Uygulamaları'na** gidip **Genel'e** geçerek bunu yapın.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, sohbet veya kısa mesaj Açıklama otomatik olarak oluşturuldu":::

1. **Sistem OAuth &gt; Uygulama Kayıt Defteri'ne** gidin.

1. **Üçüncü taraf OAuth Sağlayıcısına bağlan** seçeneğini kullanarak ve şu değerleri girerek yeni bir uygulama oluşturun:

    - İstemci Kimliği: Bu, Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 1. adımda \#oluşturulan uygulamanın İstemci Kimliğidir.

    - İstemci Gizli Anahtarı: Bu, Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 1. adımda \#oluşturulan uygulamanın İstemci Gizli Anahtarı değeridir.

    - Varsayılan Verme türü: İstemci Kimlik Bilgileri

    - Belirteç URL'si: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - Yeniden yönlendirme URL'si: `https://{your-servicenow-instance}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] ServiceNow'da OIDC sağlayıcısını yapılandırmak için [çevrimiçi belgelere bakın](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html).

    Kapsam **Genel** olarak ayarlanmadıysa **Ayarlar &gt; Geliştirici &gt; Uygulamaları'na** gidin ve **Genel'e** geçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, sohbet veya kısa mesaj Açıklama otomatik olarak oluşturuldu":::

1. **Sistem OAuth &gt; Uygulama Kayıt Defteri'ne** gidin.

1. **Kimlik belirteçlerini doğrulamak için Yeni'yi ve ardından Yapılandır ve OIDC sağlayıcısı'na tıklayın**.

1. **OAuth OIDC Sağlayıcısı Yapılandırması'nda** **Ara'yı** seçin ve **oidc provider configuration.list altında şu değerlerle yeni bir OIDC\_sağlayıcı\_yapılandırması** oluşturun:

    - OIDC Sağlayıcısı: **{Tenant\_Name} Azure** (örnek: Contoso Azure)

    - OIDC Meta Veri URL'si: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appid**

    - UserField: **Kullanıcı Kimliği**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama Açıklaması otomatik olarak oluşturuldu":::

1. Bu yeni uygulamada alanları şu değerlerle doldurun:

    - Ad: **{Tenant\_Name}\_application\_inbound\_API** (örnek: contoso\_application\_inbound\_API)

    - İstemci Kimliği: Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 3. adımda \#oluşturulan uygulamanın İstemci Kimliği.

    - İstemci Gizli Anahtarı: Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 3. adımda \#oluşturulan uygulamanın Uygulama Gizli Dizisi.

    - OAuth OIDC Sağlayıcısı Yapılandırması: Önceki adımda oluşturulan OIDC sağlayıcısı

    - Yeniden yönlendirme URL'si: `https://{service-now-instance-name}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Tümleştirme Kullanıcıları Oluşturma.

    Bir tümleştirme kullanıcısı belirtmeniz gerekir. Mevcut bir tümleştirme kullanıcınız yoksa veya bu tümleştirme için özel olarak bir tümleştirme oluşturmak istiyorsanız Kuruluş **Kullanıcıları'na &gt;** giderek yeni bir kullanıcı oluşturun. **Kullanıcı Kimliği** değeri [, Önkoşullar (Azure AD Kimlik Doğrulama Belirteci)](#prerequisites-azure-ad-auth-token) içinde oluşturulan uygulama İstemci Kimliğidir.

    Yeni bir tümleştirme kullanıcısı oluşturuyorsanız **Yalnızca Web hizmeti erişimi** seçeneğini işaretleyin. Bu kullanıcıya **olay\_yöneticisi** rolü de vermelisiniz.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[İsteğE BAĞLI\] Hizmetin IP adreslerinin Microsoft 365 destek tümleştirmesine izin verme

Şirketiniz İnternet erişimini kendi ilkelerinizle sınırlandırıyorsa, hem gelen hem de giden API erişimi için aşağıdaki IP adreslerine izin vererek Microsoft 365 destek tümleştirmesi hizmeti için ağ erişimini etkinleştirin.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> Bu terminal komutu, Microsoft 365 destek tümleştirmesi için hizmetin tüm etkin IP'lerini listeler: `nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Microsoft 365 destek tümleştirme uygulamasını yapılandırma

Microsoft 365 destek tümleştirme uygulaması Microsoft 365 desteği altında ayarlanabilir.

ServiceNow örneğinizle Microsoft 365 desteği arasındaki tümleştirmeyi ayarlamak için bu adımlar gereklidir.

1. \[ServiceNow Yönetici\] Kapsamı **Microsoft 365 destek tümleştirmesine** geçin.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="Grafik kullanıcı arabirimi, tablo Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Tümleştirme iş akışını açmak için **Microsoft 365 Destek &gt; Kurulumu'na** gidin.

    > [!NOTE]
    > "'x\_mioms\_m365\_assis' kapsamındaki 'oauth\_varlığına karşı okuma işlemi' tablonun kapsamlar arası erişim ilkesi nedeniyle reddedildi" hatasını görürseniz, bunun nedeni tablo erişim ilkenizdir. Tablo oauth\_varlığı için **Tüm uygulama kapsamları &gt; Okunabilir'in** işaretli olduğundan emin olmanız gerekir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Devam etmek için onay istemini **kabul et'i** seçin.

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Ortamı ve kurulum türünü yapılandırın.
    Bu yükleme bir test ortamındaysa Bu bir test ortamıdır seçeneğini belirleyin. Kurulumdan sonra ve tüm testleriniz daha sonra tamamlandıktan sonra bu seçeneği hızla devre dışı bırakabileceksiniz.
    Örneğiniz gelen bağlantılar için Temel Kimlik Doğrulaması'na izin veriyorsa Evet'i seçin ve [Temel Kimlik Doğrulaması kurulum işlemine](servicenow-basic-authentication.md) bakın. Aksi takdirde **Hayır'ı** seçin ve **Kurulumu başlat'a** tıklayın. 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Microsoft 365 kiracı etki alanınızı girin.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Giden OAuth sağlayıcısını yapılandırın.
    1. Giden OAuth sağlayıcısını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra Bitti'ye tıklayın. Aksi takdirde, AAD'de gerekli uygulama kaydını oluşturmak için sihirbazdaki yönergeleri izleyin.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    1. ServiceNow OAuth Uygulamasını kaydedin.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, yeni oluşturulan OAuth uygulama kaydını seçin ve İleri'ye tıklayın. Aksi takdirde, ServiceNow'da varlığı oluşturmak için yönergeleri izleyin ve ardından yeni uygulama kaydını seçin.
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Gelen ayarlarını yapılandırın.
    1. Gelen AAD Uygulamasını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, sonraki adıma geçmek için Bitti'ye tıklayın. Aksi takdirde, gelen bağlantı için AAD Uygulama Kaydı oluşturmak üzere yönergeleri izleyin.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    1. ServiceNow Dış OpenID Connect Sağlayıcısını (OIDC Sağlayıcısı) yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra yeni oluşturulan varlığı seçin ve Bitti'ye tıklayın. Aksi takdirde, ServiceNow'da varlığı oluşturmak için yönergeleri izleyin ve ardından yeni Dış OIDC Sağlayıcısı uygulama kaydını seçin.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    1. Gelen Tümleştirme Kullanıcısı için AAD Uygulama Kaydını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra, sonraki adıma geçmek için Bitti'ye tıklayın. Aksi takdirde, gelen REST kullanıcısı (tümleştirme kullanıcısı) için AAD Uygulama Kaydı oluşturmak üzere yönergeleri izleyin.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    1. Tümleştirme Kullanıcısını yapılandırın.
    1. Önkoşullar bölümündeki yönergeleri tamamladıktan sonra yeni oluşturulan varlığı seçin ve İleri'ye tıklayın. Aksi takdirde ServiceNow'da tümleştirme kullanıcısı oluşturmak için yönergeleri izleyin ve varlığı seçin.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[Microsoft 365 Kiracı Yönetici\] Tümleştirmeyi tamamlayın.

    Aşağıdaki bilgilerin doğru olduğunu doğrulayın. Şu anda **İleri'yi** SEÇMEYİN.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

    1. **Microsoft 365 Yönetici Portal &gt; Ayarları &gt; Kuruluş ayarları &gt; Kuruluş profilleri'ne** gidin.

    1. Destek tümleştirme ayarlarını yapılandırın:

    **ServiceNow** **dahili destek aracı** >  > **Temel bilgiler** sekmesini seçin ve **Kimlik Doğrulama Belirteci vermek için Uygulama Kimliği** alanına **Giden Uygulama** Kimliği değerini girin. Bu Giden Uygulama Kimliği, [Önkoşullar (Azure AD Kimlik Doğrulama Belirteci)](#prerequisites-azure-ad-auth-token) içinde oluşturulan 6. Adım – Tümleştirmeyi Tamamlama'dadır.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

    1. **Depolar** sekmesinde **Yeni depo'yu** seçin ve aşağıdaki ayarlarla güncelleştirin:

    - Depo: "6. Adım – Tümleştirmeyi Tamamlama" bölümünde yer alan **Depo Kimliği** değeri.

    - Uç Nokta: "6. Adım – Tümleştirmeyi Tamamlama" adlı **uç nokta** değeri.

    - Kimlik doğrulama türü: **AAD Kimlik Doğrulaması'ı** seçin.

    - İstemci Kimliği: 6. Adım – Tümleştirmeyi Tamamla'dan **İstemci Kimliği** değeri.

    - İstemci gizli anahtarı: Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 2. adımda \#oluşturulan gelen OAuth sağlayıcısının gizli dizisi.

    - Rest kullanıcı adı: 6. Adım – Tümleştirmeyi Tamamla'daki **Kullanıcı Adı** değeri, Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 3. adımda \#oluşturulan uygulamanın **İstemci Kimliğidir**.

    - Rest kullanıcı parolası: Önkoşullar (Azure AD Kimlik Doğrulama Belirteci) 3. adımda \#oluşturulan uygulamanın Uygulama Gizli Dizisi.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="Grafik kullanıcı arabirimi, uygulama açıklaması otomatik olarak oluşturuldu":::

    1. ServiceNow'a Geri dön.

    1. Tümleştirmeyi tamamlamak için **İleri'yi** seçin.

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::
    Microsoft 365 destek tümleştirme uygulaması, tümleştirmenin çalıştığından emin olmak için testler yürütür. Yapılandırmayla ilgili bir sorun varsa, nelerin düzeltilmesi gerektiğini açıklayan bir hata iletisi görüntülenir. Aksi takdirde uygulama hazırdır.
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama, e-posta Açıklaması otomatik olarak oluşturuldu":::

1. \[ServiceNow Yönetici\] Var olan bir kullanıcı için Microsoft destek tümleştirmesini etkinleştirin.

    Microsoft 365 destek tümleştirmesi, şu rollerden birine sahip kullanıcı için etkinleştirilir:

    - x\_mioms\_m365\_assis.insights\_kullanıcısı

    - x\_mioms\_m365\_assis.administrator

1. \[İsteğE BAĞLI\] \[X\_mioms\_m365\_assis.administrator rolüne sahip kullanıcı Microsoft 365 yönetici hesabını bağla\] bağlantısı.

    Herhangi bir kullanıcı x\_mioms\_m365\_assis.administrator rolüne sahipse ve bir Microsoft 365 destek olayını yönetmek için farklı Microsoft 365 hesapları kullanıyorsa, Microsoft 365 yönetici e-postasını ayarlamak için Microsoft 365 destek &gt; Bağlantısı Hesabı'na gitmesi gerekir.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="Grafik kullanıcı arabirimi, metin, uygulama Açıklaması otomatik olarak oluşturuldu":::
