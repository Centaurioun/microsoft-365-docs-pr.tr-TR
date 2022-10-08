---
title: Shifts bağlayıcı sihirbazını kullanarak Shifts'i UKG Boyutlarına bağlama
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Vardiyalar bağlayıcısı sihirbazını kullanarak Teams'deki Vardiyaları UKG Boyutları ile tümleştirmeyi öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 4dc87f3590d7b6213c207ae10d855c0171d8c78f
ms.sourcegitcommit: 176bbd29c92e1c0812e8bcd1e1e4938a3e1d7331
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68470200"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-ukg-dimensions"></a>Shifts bağlayıcı sihirbazını kullanarak Shifts'i UKG Boyutlarına bağlama

## <a name="overview"></a>Genel bakış

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[!INCLUDE [shifts-connector-wizard-intro](includes/shifts-connector-wizard-intro.md)]

## <a name="integrate-shifts-with-ukg-dimensions"></a>Vardiyaları UKG Boyutlarıyla Tümleştirme

[UKG Boyutları için Microsoft Teams Vardiyaları bağlayıcısı](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions), zamanlamalarınızı yönetmek ve güncel tutmak için Vardiyaları UKG Boyutları ile tümleştirmenize olanak tanır. Bu makalede, bağlayıcı aracılığıyla UKG Dimensions'a bağlantı kurmak için sihirbazı nasıl çalıştırabileceğiniz konusunda size yol gösteririz.

> [!NOTE]
> Shift'leri UKG Boyutları ile tümleştirmek için PowerShell'i de kullanabilirsiniz. Daha fazla bilgi edinmek için bkz. [PowerShell kullanarak Vardiyaları UKG Boyutlarına bağlama](shifts-connector-ukg-powershell-setup.md).

## <a name="before-you-begin"></a>Başlamadan önce

Sihirbazı çalıştırmak için Microsoft 365 genel yöneticisi olmanız gerekir.

<a name="prerequisites"> </a>
### <a name="prerequisites"></a>Önkoşullar
[!INCLUDE [shifts-connector-ukg-prerequisites](includes/shifts-connector-ukg-prerequisites.md)]

- Eşlemek istediğiniz ekiplerin herhangi bir zamanlaması yoktur. Bir ekibin mevcut bir zamanlaması varsa, UKG Dimensions örneğini eşlemeden önce [zamanlamayı ekipten kaldırın](#remove-schedules-from-teams-you-want-to-map) . Aksi takdirde yinelenen vardiyalar görürsünüz.

<a name="remove_schedules"> </a>
## <a name="remove-schedules-from-teams-you-want-to-map"></a>Eşlemek istediğiniz ekiplerden zamanlamaları kaldırma

> [!NOTE]
> UKG Dimensions örneklerini zamanlamaları olan mevcut ekiplere eşlerseniz bu adımı tamamlayın. Zamanlamaları olmayan ekiplere eşlediğiniz veya eşleyebileceğiniz yeni ekipler oluşturuyorsanız bu adımı atlayabilirsiniz.

Zamanlamaları ekiplerden kaldırmak için PowerShell'i kullanın.

1. İlk olarak, PowerShell modüllerini yüklemeniz ve ayarlamanız gerekir. [Ortamınızı ayarlama adımlarını](shifts-connector-ukg-powershell-manage.md#set-up-your-environment) izleyin
1. Aşağıdaki komutu çalıştırın:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    parametresine yönelik senaryoların listesini almak için `EntityType` [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) komutunu çalıştırın. Zamanlama verileri, belirttiğiniz tarih ve saat aralığı için kaldırılır.

Daha fazla bilgi için bkz [. Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord).

## <a name="run-the-wizard"></a>Sihirbazı çalıştırma

### <a name="get-started"></a>Kullanmaya başlayın

1. [Microsoft 365 yönetim merkezi](https://admin.microsoft.com/) sol gezinti bölmesinde **Kurulum'u** seçin ve ardından **Uygulamalar ve e-posta** bölümüne gidin.
1. **İş gücü yönetim sisteminizi bağlayın'ı** seçin. Burada Vardiyalar bağlayıcıları ve Vardiyaları WFM sisteminize bağladığınızda ön cephe çalışanı ve yönetici deneyimi hakkında daha fazla bilgi edinebilirsiniz.
    :::image type="content" source="media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 yönetim merkezi Shifts bağlayıcı sihirbazının ayrıntılar sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-get-started.png":::
1. Hazır olduğunuzda **Başlarken'i** seçin.
1. Bağlayıcınızı seçin sayfasında **UKG Boyutları'nı** seçin ve ardından **İleri'yi** seçerek bir UKG Boyutlar bağlantısı oluşturun.

<a name="connection_details"> </a>
### <a name="enter-connection-details"></a>Bağlantı ayrıntılarını girin

1. Bağlantı ayrıntıları sayfasında bağlantınıza benzersiz bir ad verin. 128 karakterden uzun olamaz veya özel karakter olamaz.
    :::image type="content" source="media/shifts-connector-wizard-ukg-connection-details.png" alt-text="Bağlantı ayarlarını gösteren sihirbazın Bağlantı ayrıntıları sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-connection-details.png":::
1. UKG Dimensions hizmet hesabı adınızı (UKG Dimensions'ta oluşturulan tüm örneklere erişim sağlayan) ve parola ve hizmet URL'lerini girin.
1. İşiniz bittiğinde, girdiğiniz ayarlarla bağlantıyı test etmek için **İleri'yi** seçin.

<a name="sync"> </a>
### <a name="choose-sync-settings"></a>Eşitleme ayarlarını seçme

Eşitleme ayarları sayfasında UKG Boyutları'ndan Vardiyalar'a eşitlenecek bilgileri, eşitleme sıklığını ve Shifts kullanıcılarının verilerde değişiklik yapıp yapamayacağını seçersiniz.

1. Microsoft 365 sistem hesabınızı girin.
    :::image type="content" source="media/shifts-connector-wizard-ukg-sync-settings.png" alt-text="Eşitleme ayarlarını gösteren sihirbazın Eşitleme ayarları sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-sync-settings.png":::
<a name="email"> </a>
1. **Email bildirim alıcıları'nın** altında, bu bağlantı hakkında e-posta bildirimlerini kimlerin alacağını seçin. Tek tek kullanıcılar ve gruplar ekleyebilirsiniz. E-posta bildirimleri, bağlantı kurulum durumu ve bağlantı kurulduktan sonra oluşabilecek sorunlar veya hatalar hakkında bilgi içerir.
1. Eşitleme ayarlarınızı seçin:
    1. **Zamanlama ve vardiyalar'ın** altında, Shifts kullanıcılarının görebileceği veya değiştirebileceği UKG Boyutları verilerini seçin ve ardından eşitleme sıklığını ayarlayın.
    1. **Zaman kartı'nın** altında Shifts kullanıcılarının zaman girdileriyle yapabilecekleri eylemi seçin.
    1. **İstekler'in** altında, Shifts kullanıcılarının görebileceği ve oluşturabileceği istek türlerini seçin.

    > [!IMPORTANT]
    > Açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmak için aşağıdaki seçeneklerden birini seçtiyseniz, Vardiyalar'da özelliği gizlemek için yapmanız gereken başka bir adım vardır.
    >
    > - Açık vardiyalar: **Vardiyalar kullanıcıları UKG Boyutları verilerini görmez**
    > - Değiştirme istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
    > - zaman aşımı istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
    >
    > Sihirbazı çalıştırdıktan sonra, bu makalenin devamında [açık vardiyaları devre dışı bırakma, vardiya isteklerini açma, değiştirme istekleri ve izin istekleri](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) bölümündeki adımları izlediğinize emin olun.
 
1. Ayarlarınızı seçmeyi bitirdiğinizde **Bağlantı oluştur'u** seçin.

<a name="instances"> </a>
### <a name="map-ukg-dimensions-instances-to-teams"></a>UKG Dimensions örneklerini ekiplerle eşleme

Shifts'e bağlamak istediğiniz UKG Dimensions örneklerini seçin ve ardından her örneği Teams'deki bir ekiple eşleyin. En fazla 100 örneği eşleyebilirsiniz. Bunu yapmanın iki yolu vardır:

- [Örnekleri ekiplere el ile eşleme](#manually-map-instances-to-teams)
- [Eşlemelerinizi tanımlayan bir CSV dosyası hazırlama ve karşıya yükleme](#use-a-csv-file-to-map-instances-to-teams)

<a name="map_manual"> </a>
#### <a name="manually-map-instances-to-teams"></a>Örnekleri ekiplere el ile eşleme

Eşlemek istediğiniz örnekleri seçin.

:::image type="content" source="media/shifts-connector-wizard-ukg-sites.png" alt-text="UKG Dimensions örneklerinin listesini gösteren sihirbazın ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-sites.png":::

Ardından her örneği Teams'deki bir ekiple eşleyin. Bir örneği mevcut bir ekiple eşleyebilir veya yeni bir ekip oluşturabilirsiniz.
:::image type="content" source="media/shifts-connector-wizard-ukg-search-team.png" alt-text="Arama ekibi seçeneğini ve yeni bir ekip oluşturma seçeneğini gösteren bölmenin ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-search-team.png":::

[!INCLUDE [shifts-connector-manually-map-instances](includes/shifts-connector-manually-map-instances.md)]

<a name="map_csv"> </a>
#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Örnekleri ekiplere eşlemek için CSV dosyası kullanma

1. **Toplu moda geç'i** seçin.
1. Eşlemelerinizi tanımlamak için kullanabileceğiniz bir eşleme şablonu indirmek için şablon **dosyasını indir'i** seçin.

    :::image type="content" source="media/shifts-connector-wizard-ukg-mapping-file.png" alt-text="Sihirbazın Eşleme dosyasını karşıya yükleme sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-mapping-file.png":::

1. Eşleme dosyanızı oluşturmak için şablonu kullanın. İlk sütundan başlayarak aşağıdaki sırayla bu sütunları içerir. Yıldız işareti (*) gerekli bir sütunu gösterir.

    |Sütun adı  |Açıklama  |
    |---------|---------|
    |**UKG Boyutlar Örnek Kimliği*** |UKG Boyutlar WFM örnek kimliği.|
    |**UKG Boyutlar Örneği Adı**|UKG Boyutlar WFM örnek adı.|
    |**Ekip Kimliği*** |Ekip kimliği.|
    |**Ekip Adı**|Ekip adı.|
    |**Saat dilimi*** |tz veritabanı biçimindeki saat dilimi. Örneğin, Avrupa/Londra.|

    > [!NOTE]
    > Örnekleri ekiplere eşlemek için yalnızca gerekli sütunları (UKG Boyutlar Örnek Kimliği, Ekip Kimliği, Saat dilimi) doldurmanız gerekir.

    Eşleme dosyanızı oluşturmanıza yardımcı olmak için şablonda tüm UKG Dimensions örneklerinizin listesi ve ardından ekiplerinizin listesi (en fazla 1000) ve bunlara karşılık gelen ekip kimlikleri yer alır.

    Aşağıda eşleme dosyasının nasıl göründüğüne bir örnek verilmiş.

    |UKG Boyutlar Örnek Kimliği|UKG Boyutlar Örneği Adı|Ekip Kimliği|Ekip Adı|Saat dilimi|
    |---------|---------|---------|---------|---------|
    |4201|CO/Avustralya|ee0bbc99-7120||Avustralya/Sidney|
    |4203|CO/US|90db4db7-be44|ABD Ekibi|Amerika/New_York|
    |4251||c88b4ead-c965||Avrupa/Londra|

1. Eşleme dosyanızı oluşturduğunuzda, karşıya yüklemek için **Gözat'ı** seçin. Sihirbaz dosyanızı doğrular. Hata bulursa hataların listesini ve bunları düzeltmenizi isteyen bir ileti görürsünüz. Aksi takdirde, sonraki adıma devam etmek için bir ileti görürsünüz.  
1. **İleri**'yi seçin.

### <a name="review-and-finish"></a>Gözden geçirme ve bitirme

Ayarlarınızı gözden geçirin. Ekip eşlemelerinde değişiklik yapmanız gerekiyorsa, bunu yapmak için **Düzenle'yi** seçin. Hazır olduğunuzda **Son'u** seçin.

:::image type="content" source="media/shifts-connector-wizard-ukg-review.png" alt-text="Eşlemeleri gösteren sihirbazın Gözden Geçir sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-review.png":::

İsteğinizi aldığımızı onaylamak için bir ileti ve bir işlem kimliği görürsünüz. İşlem kimliğini not edin. Bağlantınızın kurulum durumunu denetlemek için buna ihtiyacınız olacaktır.

:::image type="content" source="media/shifts-connector-wizard-ukg-operation-id.png" alt-text="Onay iletisini ve işlem kimliğini gösteren sihirbaz sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-ukg-operation-id.png":::

Sihirbaz, bağlantıyı ayarlama işlemini başlatır ve örnekleri seçtiğiniz ekiplerle eşler. Bu işlemin tamamlanması biraz zaman alabilir. Seçtiğiniz alıcılar kurulum durumu hakkında e-posta bildirimleri alır.

**Sihirbazdan çıkmak için Bitti'yi** seçin.

Yoldasınız ama işiniz daha bitmedi! E-postanızı kontrol edin. İsteğinizi aldığımıza dair bir onay ve kurulum durumunu nasıl denetleyebileceğinize ilişkin bir [bağlantı](shifts-connector-ukg-powershell-manage.md#check-connection-setup-status) alırsınız.

> [!NOTE]
> Bir bağlantı kurulduktan sonra bir sorun veya hata oluşursa, e-postayla bildirim alırsınız. Sorunu gidermek için e-postadaki yönergeleri izleyin.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini ve izin isteklerini devre dışı bırakma

> [!IMPORTANT]
> Bu adımları yalnızca sihirbazda açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmak için aşağıdaki seçeneklerden birini seçtiyseniz izleyin. Bu adımın tamamlanması, Vardiyalar'daki özelliği gizler.
>
> - Açık vardiyalar: **Vardiyalar kullanıcıları UKG Boyutları verilerini görmez**
> - Değiştirme istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
> - zaman aşımı istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
>
> Bu ikinci adım olmadan, kullanıcılar özelliği Vardiyalar'da görmeye devam eder ve kullanmaya çalışırlarsa "desteklenmeyen işlem" hata iletisini alır.

Vardiyalarda açık vardiyaları, değiştirme isteklerini ve izin isteklerini gizlemek için Graph API [zamanlama kaynak türünü](/graph/api/resources/schedule) kullanarak bir UKG Dimensions örneğine eşlediğiniz her ekip için aşağıdaki parametreleri ```false``` olarak ayarlayın:

- Vardiyaları açma: ```openShiftsEnabled```
- Değiştirme istekleri:  ```swapShiftsRequestsEnabled```
- zaman aşımı istekleri: ```timeOffRequestsEnabled```

Vardiyalar'da açık vardiya isteklerini gizlemek için Vardiyalar'daki **Ayarlar'a** gidin ve **Vardiyaları aç** ayarını kapatın.

<a name="manage"> </a>
## <a name="manage-your-connection"></a>Bağlantınızı yönetme

Bağlantı kurulduktan sonra, Microsoft 365 yönetim merkezi veya PowerShell kullanarak bu bağlantıyı yönetebilir ve bu bağlantıda değişiklik yapabilirsiniz.

### <a name="use-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanma

Bağlayıcı Yönetimi sayfasında, ayarladığınız her bağlantının yanı sıra sistem durumu ve eşitleme aralığı ayrıntıları gibi bilgiler listelenir. Bağlantılarınızdan herhangi birinde değişiklik yapmak için sihirbaza da erişebilirsiniz. Örneğin, eşitleme ayarlarını ve ekip eşlemelerini güncelleştirebilirsiniz.

Daha fazla bilgi edinmek için bkz. [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanma](shifts-connector-ukg-admin-center-manage.md).

### <a name="use-powershell"></a>PowerShell kullanma

PowerShell'i kullanarak hata raporunu görüntüleyebilir, bağlantı ayarlarını değiştirebilir, eşitlemeyi devre dışı bırakabilir ve daha fazlasını yapabilirsiniz. Adım adım yönergeler için bkz. [PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md).

## <a name="related-articles"></a>İlgili makaleler

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Teams'de Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
