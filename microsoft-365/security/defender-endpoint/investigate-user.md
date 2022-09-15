---
title: Uç Nokta için Microsoft Defender'de kullanıcı hesabını araştırma
description: Olası güvenliği aşılmış kimlik bilgileri için bir kullanıcı hesabını araştırın veya araştırma sırasında ilişkili kullanıcı hesabında özetleyin.
keywords: araştırma, hesap, kullanıcı, kullanıcı varlığı, uyarı, Uç Nokta için Microsoft Defender
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ff507a45e27ecd67f1d56aaf46ed095d200d925f
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711422"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de kullanıcı hesabını araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Kullanıcı hesabı varlıklarını araştırma

En etkin uyarılara sahip kullanıcı hesaplarını tanımlayın (panoda "Risk altındaki kullanıcılar" olarak görüntülenir) ve güvenliği aşılmış olabilecek kimlik bilgileri olaylarını araştırın veya ilgili kullanıcı hesabıyla cihazlar arasında olası yanal hareketi belirlemek için bir uyarıyı veya cihazı araştırırken ilgili kullanıcı hesabında özetleyin.

Kullanıcı hesabı bilgilerini aşağıdaki görünümlerde bulabilirsiniz:

- Pano
- Uyarı kuyruğu
- Cihaz ayrıntıları sayfası

Bu görünümlerde tıklanabilir bir kullanıcı hesabı bağlantısı bulunur ve bu bağlantı sizi kullanıcı hesabıyla ilgili diğer ayrıntıların gösterildiği kullanıcı hesabı ayrıntıları sayfasına götürür.

Bir kullanıcı hesabı varlığını araştırdığınızda şunları görürsünüz:

- Kullanıcı hesabı ayrıntıları, Kimlik için Microsoft Defender uyarıları ve cihazlarda oturum açma, rol, oturum açma türü ve diğer ayrıntılar
- Olaylara ve kullanıcının cihazlarına genel bakış
- Bu kullanıcıyla ilgili uyarılar
- Kuruluşta gözlemlenen (oturum açmış cihazlar)

:::image type="content" source="images/atp-user-details-view.png" alt-text="Kullanıcı hesabı varlık ayrıntıları sayfası" lightbox="images/atp-user-details-view.png":::

### <a name="user-details"></a>Kullanıcı ayrıntıları

Soldaki **Kullanıcı ayrıntıları** bölmesi, ilgili açık olaylar, etkin uyarılar, SAM adı, SID, Kimlik için Microsoft Defender uyarıları, kullanıcının oturum açtığı cihaz sayısı, kullanıcının ilk ve son görüldüğü zaman, rol ve oturum açma türleri gibi kullanıcı hakkında bilgi sağlar. Etkinleştirdiğiniz tümleştirme özelliklerine bağlı olarak diğer ayrıntıları görürsünüz. Örneğin, Skype Kurumsal tümleştirmesini etkinleştirirseniz portaldan kullanıcıyla iletişim kurabilirsiniz. **Azure ATP uyarıları** bölümünde, Kimlik için Microsoft Defender özelliğini etkinleştirdiyseniz ve kullanıcıyla ilgili uyarılar varsa sizi Kimlik için Microsoft Defender sayfasına götürecek bir bağlantı bulunur. Kimlik için Microsoft Defender sayfasında uyarılar hakkında daha fazla bilgi sağlanır.

> [!NOTE]
> Bu özelliği kullanmak için hem Kimlik için Microsoft Defender hem de Uç Nokta için Defender'da tümleştirmeyi etkinleştirmeniz gerekir. Uç Nokta için Defender'da bu özelliği gelişmiş özelliklerde etkinleştirebilirsiniz. Gelişmiş özellikleri etkinleştirme hakkında daha fazla bilgi için bkz. [Gelişmiş özellikleri açma](advanced-features.md).

Kuruluşta Genel Bakış, Uyarılar ve Gözlemlenenler, kullanıcı hesabıyla ilgili çeşitli öznitelikleri görüntüleyen farklı sekmelerdir.


>[!NOTE]
>Linux cihazları için oturum açmış kullanıcılar hakkındaki bilgiler görüntülenmez.


### <a name="overview"></a>Genel bakış

**Genel Bakış** sekmesi, olay ayrıntılarını ve kullanıcının oturum açtığı cihazların listesini gösterir. Her cihaz için oturum açma olaylarının ayrıntılarını görmek için bunları genişletebilirsiniz.

### <a name="alerts"></a>Uyarılar

**Uyarılar** sekmesi, kullanıcı hesabıyla ilişkili uyarıların listesini sağlar. Bu liste [, Uyarı kuyruğunun](alerts-queue.md) filtrelenmiş bir görünümüdür ve kullanıcı bağlamının seçili kullanıcı hesabı olduğu uyarıları, son etkinliğin algılandığı tarihi, uyarının kısa bir açıklamasını, uyarıyla ilişkili cihazı, uyarının önem derecesini, uyarının kuyruktaki durumunu ve uyarının kime atandığını gösterir.

### <a name="observed-in-organization"></a>Kuruluşta gözlemlenen

**Kuruluşta gözlemlenen** sekmesi, bu kullanıcının oturum açtığının gözlemlendiği cihazların listesini, bu cihazların her biri için en sık ve en az sıklıkta oturum açan kullanıcı hesabını ve her cihazda gözlemlenen toplam kullanıcıları görmek için bir tarih aralığı belirtmenize olanak tanır.

Kuruluşta gözlemlenenler tablosunda bir öğe seçildiğinde öğe genişletilecek ve cihaz hakkında daha fazla ayrıntı gösterilecektir. Bir öğenin içindeki bağlantıyı doğrudan seçtiğinizde ilgili sayfaya gönderilirsiniz.

## <a name="search-for-specific-user-accounts"></a>Belirli kullanıcı hesaplarını arama

1. **Arama çubuğu** açılan menüsünden **Kullanıcı'yı** seçin.
2. **Arama** alanına kullanıcı hesabını girin.
3. Arama simgesine tıklayın veya **Enter tuşuna** basın.

Sorgu metniyle eşleşen kullanıcıların listesi görüntülenir. Kullanıcı hesabının etki alanını ve adını, kullanıcı hesabının son görüldüğü zamanı ve son 30 gün içinde oturum açtığı gözlemlenen toplam cihaz sayısını görürsünüz.

Sonuçları aşağıdaki zaman aralıklarına göre filtreleyebilirsiniz:

- 1 gün
- 3 gün
- 7 gün
- 30 gün
- 6 ay

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender Uyarıları kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
- [Uç Nokta için Microsoft Defender uyarılarını yönetme](manage-alerts.md)
- [Uç Nokta için Microsoft Defender uyarılarını araştırma](investigate-alerts.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir dosyayı araştırma](investigate-files.md)
- [Uç Nokta Cihazları için Defender listesindeki cihazları araştırma](investigate-machines.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir IP adresini araştırma](investigate-ip.md)
- [Uç Nokta için Defender uyarısıyla ilişkilendirilmiş bir etki alanını araştırma](investigate-domain.md)
