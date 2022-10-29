---
title: Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Teams'deki Vardiyaları Mavi Yonder Workforce Management ile tümleştirmek için Vardiyalar bağlayıcısı sihirbazını kullanmayı öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 322f665746211098b04ba8482eeb764007dfb55a
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785165"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management

## <a name="overview"></a>Genel bakış

[!INCLUDE [shifts-connector-wizard-intro](includes/shifts-connector-wizard-intro.md)]

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Vardiyaları Blue Yonder Workforce Management ile tümleştirme

[Blue Yonder için Microsoft Teams Vardiyaları bağlayıcısı](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder), zamanlamalarınızı yönetmek ve güncel tutmak için Vardiyaları Blue Yonder Workforce Management (Blue Yonder WFM) ile tümleştirmenize olanak tanır. Bu makalede, bağlayıcı üzerinden Blue Yonder WFM bağlantısı kurmak için sihirbazı nasıl çalıştırabileceğiniz konusunda size yol gösteririz.

> [!NOTE]
> Shift'leri Blue Yonder WFM ile tümleştirmek için PowerShell'i de kullanabilirsiniz. Daha fazla bilgi edinmek için bkz. [PowerShell kullanarak Shifts'i Blue Yonder'a bağlama Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Başlamadan önce

Sihirbazı çalıştırmak için Microsoft 365 genel yöneticisi olmanız gerekir.

### <a name="prerequisites"></a>Önkoşullar
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](includes/shifts-connector-prerequisites.md)]

- Eşlemek istediğiniz ekiplerin herhangi bir zamanlaması yoktur. Bir ekibin mevcut bir zamanlaması varsa, bir Blue Yonder WFM örneğini eşlemeden önce [zamanlamayı ekipten kaldırın](#remove-schedules-from-teams-you-want-to-map). Aksi takdirde yinelenen vardiyalar görürsünüz.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Eşlemek istediğiniz ekiplerden zamanlamaları kaldırma
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM örneklerini zamanlamaları olan mevcut ekiplere eşlerseniz bu adımı tamamlayın. Zamanlamaları olmayan ekiplere eşlediğiniz veya eşleyebileceğiniz yeni ekipler oluşturuyorsanız bu adımı atlayabilirsiniz.

Zamanlamaları ekiplerden kaldırmak için PowerShell'i kullanın.

1. İlk olarak, PowerShell modüllerini yüklemeniz ve ayarlamanız gerekir. [Ortamınızı ayarlama adımlarını](shifts-connector-powershell-manage.md#set-up-your-environment) izleyin
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
1. Bağlayıcınızı seçin sayfasında **Blue Yonder Workforce Management'ı** seçin ve ardından **İleri'yi** seçerek Mavi Yonder WFM bağlantısı oluşturun.

### <a name="enter-connection-details"></a>Bağlantı ayrıntılarını girin
<a name="connection_details"> </a>

1. Bağlantı ayrıntıları sayfasında bağlantınıza benzersiz bir ad verin. 128 karakterden uzun olamaz veya özel karakter olamaz.
    :::image type="content" source="media/shifts-connector-wizard-connection-details.png" alt-text="Bağlantı ayarlarını gösteren sihirbazın Bağlantı ayrıntıları sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFM hizmet hesabı adınızı ve parola ve hizmet URL'lerinizi girin.
1. İşiniz bittiğinde, girdiğiniz ayarlarla bağlantıyı test etmek için **İleri'yi** seçin.

### <a name="choose-sync-settings"></a>Eşitleme ayarlarını seçme
<a name="sync"> </a>

Eşitleme ayarları sayfasında, Blue Yonder WFM'dan Vardiyalar'a eşitlenecek bilgileri, eşitleme sıklığını ve Vardiya kullanıcılarının verilerde değişiklik yapıp yapamayacağını seçersiniz.

1. Microsoft 365 sistem hesabınızı girin.
    :::image type="content" source="media/shifts-connector-wizard-sync-settings.png" alt-text="Eşitleme ayarlarını gösteren sihirbazın Eşitleme ayarları sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. **Email bildirim alıcıları'nın** altında, bu bağlantı hakkında e-posta bildirimlerini kimlerin alacağını seçin. Tek tek kullanıcılar ve gruplar ekleyebilirsiniz. E-posta bildirimleri, bağlantı kurulum durumu ve bağlantı kurulduktan sonra oluşabilecek sorunlar veya hatalar hakkında bilgi içerir.
1. Eşitleme ayarlarınızı seçin:
    1. **Zamanlama ve vardiyalar'ın** altında, Shifts kullanıcılarının görebileceği veya değiştirebileceği Mavi Yonder WFM verilerini seçin ve ardından eşitleme sıklığını ayarlayın.
    1. **Zaman kartı'nın** altında Shifts kullanıcılarının zaman girdileriyle yapabilecekleri eylemi seçin.
    1. **İstekler'in** altında, Shifts kullanıcılarının görebileceği ve oluşturabileceği istek türlerini seçin.

    > [!IMPORTANT]
    > Açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmak için aşağıdaki seçeneklerden birini seçtiyseniz, Vardiyalar'da özelliği gizlemek için yapmanız gereken başka bir adım vardır.
    >
    > - Açık vardiyalar: **Vardiya kullanıcıları Blue Yonder WFM verilerini görmez**
    > - Değiştirme istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
    > - zaman aşımı istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
    >
    > Sihirbazı çalıştırdıktan sonra, bu makalenin devamında [açık vardiyaları devre dışı bırakma, vardiya isteklerini açma, değiştirme istekleri ve izin istekleri](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) bölümündeki adımları izlediğinize emin olun.
 
1. Ayarlarınızı seçmeyi bitirdiğinizde **Bağlantı oluştur'u** seçin.

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Mavi Yonder Workforce Management örneklerini ekiplere eşleme
<a name="sites"> </a>

Shift'lere bağlanmak istediğiniz Mavi Yonder WFM örneklerini seçin ve ardından her örneği Teams'deki bir ekiple eşleyin. En fazla 100 örneği eşleyebilirsiniz. Bunu yapmanın iki yolu vardır:

- [Örnekleri ekiplere el ile eşleme](#manually-map-instances-to-teams)
- [Eşlemelerinizi tanımlayan bir CSV dosyası hazırlama ve karşıya yükleme](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>Örnekleri ekiplere el ile eşleme

Eşlemek istediğiniz örnekleri seçin.

:::image type="content" source="media/shifts-connector-wizard-sites.png" alt-text="Mavi Yonder WFM örneklerinin listesini gösteren sihirbazın ekran görüntüsü." lightbox="media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Ardından her örneği Teams'deki bir ekiple eşleyin. Bir örneği mevcut bir ekiple eşleyebilir veya yeni bir ekip oluşturabilirsiniz.
:::image type="content" source="media/shifts-connector-wizard-search-team.png" alt-text="Arama ekibi seçeneğini ve yeni bir ekip oluşturma seçeneğini gösteren bölmenin ekran görüntüsü." lightbox="media/shifts-connector-wizard-search-team.png":::

[!INCLUDE [shifts-connector-manually-map-instances](includes/shifts-connector-manually-map-instances.md)]

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Örnekleri ekiplere eşlemek için CSV dosyası kullanma

1. **Toplu moda geç'i** seçin.
1. Eşlemelerinizi tanımlamak için kullanabileceğiniz bir eşleme şablonu indirmek için şablon **dosyasını indir'i** seçin.

    :::image type="content" source="media/shifts-connector-wizard-mapping-file.png" alt-text="Sihirbazın Eşleme dosyasını karşıya yükleme sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-mapping-file.png":::

1. Eşleme dosyanızı oluşturmak için şablonu kullanın. İlk sütundan başlayarak aşağıdaki sırayla bu sütunları içerir. Yıldız işareti (*) gerekli bir sütunu gösterir.

    |Sütun adı  |Açıklama  |
    |---------|---------|
    |**Mavi Yonder Örnek Kimliği*** |Blue Yonder WFM örnek kimliği.|
    |**Mavi Yonder Örneği Adı**|Blue Yonder WFM örnek adı.|
    |**Ekip Kimliği*** |Ekip kimliği.|
    |**Ekip Adı**|Ekip adı.|
    |**Saat dilimi*** |tz veritabanı biçimindeki saat dilimi. Örneğin, Avrupa/Londra.|

    > [!NOTE]
    > Örnekleri ekiplere eşlemek için yalnızca gerekli sütunları (Mavi Yonder Örnek Kimliği, Ekip Kimliği, Saat dilimi) doldurmanız gerekir.

    Aşağıda eşleme dosyasının nasıl göründüğüne bir örnek verilmiş.

    |Mavi Yonder Örnek Kimliği|Mavi Yonder Örneği Adı|Ekip Kimliği|Ekip Adı|Saat dilimi|
    |---------|---------|---------|---------|---------|
    |2111|Contoso ABD Ekibi|3a4d78a-2261|ABD Ekibi|Amerika/Los_Angeles|
    |3212|Contoso Uk Ekibi|2d1f6c2e-5272|Birleşik Krallık Ekibi|Avrupa/Londra|
    |4865||bfa6o89e-1328||Amerika/Toronto|

1. Eşleme dosyanızı oluşturduğunuzda, karşıya yüklemek için **Gözat'ı** seçin. Sihirbaz dosyanızı doğrular. Hata bulursa hataların listesini ve bunları düzeltmenizi isteyen bir ileti görürsünüz. Aksi takdirde, sonraki adıma devam etmek için bir ileti görürsünüz.  
1. **İleri**'yi seçin.

### <a name="review-and-finish"></a>Gözden geçirme ve bitirme

Ayarlarınızı gözden geçirin. Ekip eşlemelerinde değişiklik yapmanız gerekiyorsa, bunu yapmak için **Düzenle'yi** seçin. Hazır olduğunuzda **Son'u** seçin.

:::image type="content" source="media/shifts-connector-wizard-review.png" alt-text="Eşlemeleri gösteren sihirbazın Gözden Geçir sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-review.png":::

İsteğinizi aldığımızı onaylamak için bir ileti ve bir işlem kimliği görürsünüz. İşlem kimliğini not edin. Bağlantınızın kurulum durumunu denetlemek için buna ihtiyacınız olacaktır.

:::image type="content" source="media/shifts-connector-wizard-operation-id.png" alt-text="Onay iletisini ve işlem kimliğini gösteren sihirbaz sayfasının ekran görüntüsü." lightbox="media/shifts-connector-wizard-operation-id.png":::

Sihirbaz, bağlantıyı ayarlama işlemini başlatır ve örnekleri seçtiğiniz ekiplerle eşler. Bu işlemin tamamlanması biraz zaman alabilir. Seçtiğiniz alıcılar kurulum durumu hakkında e-posta bildirimleri alır.

**Sihirbazdan çıkmak için Bitti'yi** seçin.

Yoldasınız ama işiniz daha bitmedi! E-postanızı kontrol edin. İsteğinizi aldığımıza dair bir onay ve kurulum durumunu nasıl denetleyebileceğinize ilişkin bir [bağlantı](shifts-connector-powershell-manage.md#check-connection-setup-status) alırsınız.

> [!NOTE]
> Bir bağlantı kurulduktan sonra bir sorun veya hata oluşursa, e-postayla bildirim alırsınız. Sorunu gidermek için e-postadaki yönergeleri izleyin.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini ve izin isteklerini devre dışı bırakma

> [!IMPORTANT]
> Bu adımları yalnızca sihirbazda açık vardiyaları, açık vardiya isteklerini, değiştirme isteklerini veya izin isteklerini devre dışı bırakmak için aşağıdaki seçeneklerden birini seçtiyseniz izleyin. Bu adımın tamamlanması, Vardiyalar'daki özelliği gizler.
>
> - Açık vardiyalar: **Vardiya kullanıcıları Blue Yonder WFM verilerini görmez**
> - Değiştirme istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
> - zaman aşımı istekleri: **Özellik tüm kullanıcılar için devre dışı bırakıldı**
>
> Bu ikinci adım olmadan, kullanıcılar özelliği Vardiyalar'da görmeye devam eder ve kullanmaya çalışırlarsa "desteklenmeyen işlem" hata iletisini alır.

Vardiyalarda açık vardiyaları, değiştirme isteklerini ve izin isteklerini gizlemek için Graph API [zamanlama kaynak türünü](/graph/api/resources/schedule) kullanarak bir Blue Yonder WFM örneğine ```false``` eşlediğiniz her takım için aşağıdaki parametreleri olarak ayarlayın:

- Vardiyaları açma: ```openShiftsEnabled```
- Değiştirme istekleri:  ```swapShiftsRequestsEnabled```
- zaman aşımı istekleri: ```timeOffRequestsEnabled```

Vardiyalar'da açık vardiya isteklerini gizlemek için Vardiyalar'daki **Ayarlar'a** gidin ve **Vardiyaları aç** ayarını kapatın.

## <a name="manage-your-connection"></a>Bağlantınızı yönetme
<a name="update_connection"> </a>

Bağlantı kurulduktan sonra, Microsoft 365 yönetim merkezi veya PowerShell kullanarak bu bağlantıyı yönetebilir ve bu bağlantıda değişiklik yapabilirsiniz.

### <a name="use-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanma

Bağlayıcı Yönetimi sayfasında, ayarladığınız her bağlantının yanı sıra sistem durumu ve eşitleme aralığı ayrıntıları gibi bilgiler listelenir. Bağlantılarınızdan herhangi birinde değişiklik yapmak için sihirbaza da erişebilirsiniz. Örneğin, eşitleme ayarlarını ve ekip eşlemelerini güncelleştirebilirsiniz.

Daha fazla bilgi edinmek için bkz. [Microsoft 365 yönetim merkezi kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-blue-yonder-admin-center-manage.md).

### <a name="use-powershell"></a>PowerShell kullanma

PowerShell'i kullanarak hata raporunu görüntüleyebilir, bağlantı ayarlarını değiştirebilir, eşitlemeyi devre dışı bırakabilir ve daha fazlasını yapabilirsiniz. Adım adım yönergeler için bkz. [PowerShell kullanarak Blue Yonder Workforce Management Vardiyalar bağlantınızı yönetme](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>İlgili makaleler

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Teams'de Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
