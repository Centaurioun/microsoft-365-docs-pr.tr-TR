---
title: Event Hubs'ınızı yapılandırma
description: Event Hubs'ınızı yapılandırmayı öğrenin
keywords: olay hub'ı, yapılandırma, içgörüler
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: 3c8de468422b5da737b5446c5eac172b71e0ecd8
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68055666"
---
# <a name="configure-your-event-hubs"></a>Event Hubs'ınızı yapılandırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Event Hubs'ınızı, olayları Microsoft 365 Defender alabilmesi için yapılandırmayı öğrenin.

## <a name="set-up-the-required-resource-provider-in-the-event-hubs-subscription"></a>Event Hubs aboneliğinde gerekli Kaynak Sağlayıcısını ayarlama

1. [Azure portalda](https://portal.azure.com) oturum açın.
1. **Abonelikler** > **{Olay hub'larının }** > **Kaynak sağlayıcılarına** dağıtılacağı aboneliği seçin.
1. **Microsoft.Insights** Sağlayıcısının kayıtlı olup olmadığını doğrulayın. Aksi takdirde kaydedin.

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="Microsoft Azure portal hizmet sağlayıcıları listesi sayfası" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>Azure Active Directory Uygulama Kaydını Ayarlama

> [!NOTE]
> Yönetici rolünüz olmalıdır veya Yönetici olmayanların uygulamaları kaydetmesine izin vermek için Azure Active Directory (AAD) ayarlanmalıdır. Hizmet sorumlusuna bir rol atamak için Sahip veya Kullanıcı Erişimi Yöneticisi rolüne de sahip olmanız gerekir. Daha fazla bilgi için bkz. [Portalda hizmet sorumlusu & Azure AD uygulaması oluşturma - Microsoft Docs Microsoft kimlik platformu\|](/azure/active-directory/develop/howto-create-service-principal-portal).

1. **Azure Active Directory'de** \> yeni bir kayıt oluşturun (doğal olarak bir hizmet sorumlusu oluşturur) **Uygulama kayıtları** \> **Yeni kayıt.**

1. Formu yalnızca Ad ile doldurun (Yeniden Yönlendirme URI'sine gerek yoktur).

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="Microsoft Azure portal uygulama adı görüntüleme bölümü" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="Microsoft Azure portal Genel Bakış bilgileri bölümü" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. **Sertifikalar & gizli diziler** **Yeni istemci gizli** dizisi'ne tıklayarak gizli dizi \> oluşturun:

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="Microsoft Azure portal'daki gizli dizi bölümü" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::

Bu istemci gizli anahtarı değeri, Microsoft Graph API'leri tarafından kayıtlı olan bu uygulamanın kimliğini doğrulamak için kullanılır.

> [!WARNING]
> **İstemci gizli dizisine yeniden erişemeyeceksiniz, bu nedenle gizli diziyi kaydettiğinizden emin olun**.

## <a name="set-up-event-hubs-namespace"></a>Event Hubs ad alanını ayarlama

1. Event Hubs Ad Alanı Oluşturma:

    **Olay Hub'ı \> Ekle'ye** gidin ve beklediğiniz yüke uygun fiyatlandırma katmanını, aktarım hızı birimlerini ve Otomatik Şişirme'yi (standart fiyatlandırma ve özellikler altında gerektirir) seçin. Daha fazla bilgi için bkz [. Fiyatlandırma - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/).

    > [!NOTE]
    > Mevcut bir olay hub'ını kullanabilirsiniz, ancak aktarım hızı ve ölçeklendirme ad alanı düzeyinde ayarlanır, bu nedenle bir olay hub'ını kendi ad alanına yerleştirmeniz önerilir.

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="Microsoft Azure portal event hubs bölümü" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. Ayrıca bu Event Hubs Ad Alanının Kaynak Kimliğine de ihtiyacınız olacaktır. Azure Event Hubs ad alanı sayfanıza \> gidin Özellikler. Kaynak Kimliği altındaki metni kopyalayın ve aşağıdaki Microsoft 365 Yapılandırması bölümünde kullanılmak üzere kaydedin.

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="Microsoft Azure portal event hubs özellikleri bölümü" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::

### <a name="add-permissions"></a>İzin ekleme

Event Hubs veri yönetimine katılan varlıklara aşağıdaki rollere izin eklemeniz gerekir:

- **Katkıda Bulunan**: Bu rolle ilgili izinler, Microsoft 365 Defender portalında oturum açan varlığa eklenir.
- **Okuyucu** ve **Azure Olay Hub'ı veri Alıcısı**: Bu rollerle ilgili izinler, hizmet **sorumlusu** rolüne atanmış olan ve Azure Active Directory uygulamasında oturum açan varlığa atanır.

Bu rollerin eklendiğinden emin olmak için aşağıdaki adımı gerçekleştirin:

**Rol atamaları** altında **Olay Hub'ı Ad Alanı** \> **Access Control (IAM)** \> **Ekle** ve doğrula'ya gidin.

:::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="Microsoft Azure portal uygulama kayıt hizmeti sorumlusu bölümü" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hubs"></a>Event Hubs'ı ayarlama

**Seçenek 1:**

Ad Alanınızda bir Event Hubs oluşturabilirsiniz ve dışarı aktarmak için seçtiğiniz **tüm** Olay Türleri (Tablolar) bu **olay** hub'ına yazılır.

**Seçenek 2:**

Tüm Olay Türlerini (Tabloları) tek bir Olay Hub'ına aktarmak yerine, her tabloyu Event Hubs Ad Alanınızın içindeki farklı Event Hub'lara (Olay Türü başına bir Olay Hub'ı) dışarı aktarabilirsiniz.

Bu seçenekte Microsoft 365 Defender sizin için Event Hubs oluşturur.

> [!NOTE]
> Olay Hub'ı Kümesinin parçası **olmayan** bir Olay Hub'ı Ad Alanı kullanıyorsanız, Olay Hub'ı Ad Alanı başına 10 Olay Hub'ı ile ilgili Azure sınırlaması nedeniyle tanımladığınız her Dışarı Aktarma Ayarında dışarı aktarılacak en fazla 10 Olay Türü (Tablo) seçebilirsiniz.

Örneğin:

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="Microsoft Azure portal bir olay hub'ları bölümü" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

Bu seçeneği belirlerseniz, [E-posta tablolarını göndermek için Microsoft 365 Defender yapılandırma](#configure-microsoft-365-defender-to-send-email-tables) bölümüne atlayabilirsiniz.

**Olay Hub'ı + Olay Hub'ı** seçerek Ad Alanınızda **Event Hubs**\> oluşturun.

Bölüm Sayısı paralellik aracılığıyla daha fazla aktarım hızı sağlar, bu nedenle beklediğiniz yüke göre bu sayıyı artırmanız önerilir. Varsayılan İleti Saklama ve Yakalama değerleri 1 ve Kapalı önerilir.

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="Microsoft Azure portal'de olay hub'ları oluşturma bölümü" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::

Bu Event Hub'lar için (ad alanı için değil), Gönder, Talepleri Dinle ile Paylaşılan Erişim İlkesi yapılandırmanız gerekir. **Olay Hub'ı** \> **Paylaşılan erişim ilkeleri** \> **+ Ekle'ye** tıklayın ve bir İlke adı verin (başka bir yerde kullanılmaz) ve Gönder ve **Dinle'yi** işaretleyin.

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="Microsoft Azure portal Paylaşılan erişim ilkeleri sayfası" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>E-posta tablolarını göndermek için Microsoft 365 Defender yapılandırma

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hubs"></a>Event Hubs aracılığıyla splunk'a Email tabloları Microsoft 365 Defender göndermeyi ayarlama

1. Aşağıdaki tüm rol gereksinimlerini karşılayan bir hesapla <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> oturum açın:

    - Dışarı aktaracağın Event Hubs için Event Hubs *Ad Alanı* Kaynağı düzeyinde veya daha yüksek bir düzeyde katkıda bulunan rolü. Bu izin olmadan, ayarları kaydetmeye çalıştığınızda dışarı aktarma hatası alırsınız.

    - Microsoft 365 Defender ve Azure'a bağlı kiracıda Genel Yönetici veya Güvenlik Yönetici Rolü.

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="Microsoft 365 Defender portalının Ayarlar sayfası" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. **Ham Veri Dışarı Aktarma \> +Ekle'ye** tıklayın.

    Şimdi yukarıda kaydettiğiniz verileri kullanacaksınız.

    **Ad**: Bu değer yereldir ve ortamınızda çalışan her şey olmalıdır.

    **Olayları olay hub'ına iletme**: Bu onay kutusunu seçin.

    **Event-Hub Kaynak Kimliği**: Bu değer, Event Hubs'ı ayarlarken kaydettiğiniz Event Hubs Ad Alanı Kaynak Kimliğidir.

    **Event-Hub adı**: Event Hubs Ad Alanınızın içinde bir Event Hubs oluşturduysanız, yukarıda kaydettiğiniz Event Hubs adını yapıştırın.

    Microsoft 365 Defender sizin için Olay Türleri (Tablolar) başına Olay Hub'ları oluşturmasına izin vermeyi seçerseniz, bu alanı boş bırakın.

    **Olay Türleri**: Event Hubs'a iletmek istediğiniz Gelişmiş Avcılık tablolarını seçin ve ardından özel uygulamanıza iletin. Uyarı tabloları Microsoft 365 Defender, Cihazlar tabloları Uç Nokta için Microsoft Defender (EDR) ve Email tablolar Office 365 için Microsoft Defender. Email Olayları tüm Email İşlemlerini kaydeder. URL (Güvenli Bağlantılar), Ek (Güvenli Ekler) ve Teslim Sonrası Olayları (ZAP) da kaydedilir ve NetworkMessageId alanındaki Email Olaylarına eklenebilir.

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="Microsoft Azure portal Akış API'sinin ayarlar sayfası" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. **Gönder'e** tıkladığından emin olun.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hubs"></a>Olayların Event Hubs'a aktarıldığını doğrulayın

Temel bir Gelişmiş Tehdit Avcılığı sorgusu çalıştırarak olayların Event Hubs'a gönderildiğini doğrulayabilirsiniz. **Tehdit Avcılığı** \> **Gelişmiş Tehdit Avcılığı** \> **Sorgusu'na** tıklayın ve aşağıdaki sorguyu girin:

```console
EmailEvents
|join kind=fullouter EmailAttachmentInfo on NetworkMessageId
|join kind=fullouter EmailUrlInfo on NetworkMessageId
|join kind=fullouter EmailPostDeliveryEvents on NetworkMessageId
|where Timestamp > ago(1h)
|count
```

Bu sorgu, son bir saatte diğer tüm tablolarda kaç e-posta alındığını gösterir. Ayrıca olay hub'larına aktarılabilir olaylar görüp görmediğinizi de gösterir. Bu sayı 0 gösteriyorsa Event Hubs'a giden hiçbir veri görmezsiniz.

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="Microsoft Azure portal gelişmiş avcılık sayfası" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

Dışarı aktarabileceğiniz veriler olduğunu doğruladıktan sonra, iletilerin geldiğini doğrulamak için Event Hubs sayfasını görüntüleyebilirsiniz. Bu işlem bir saate kadar sürebilir.

1. Azure'da **Olay** Hub'ı'na \> gidin **Ad Alanı** \> **Olay Hub'ına** tıklayın **Olay Hub'ına**\> tıklayın.
1. **Genel Bakış'ın** altında aşağı kaydırın ve İletiler grafiğinde Gelen İletiler'i görmeniz gerekir. Herhangi bir sonuç görmüyorsanız, özel uygulamanızın alacağı hiçbir ileti olmayacaktır.

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="Microsoft 365 Azure portal Genel Bakış sayfası" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
