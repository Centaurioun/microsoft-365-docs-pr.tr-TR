---
title: Kimliğe bürünme içgörüleri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Yöneticiler kimliğe bürünme içgörülerinin nasıl çalıştığını öğrenebilir. E-posta kimlik doğrulama denetimlerini (SPF, DKIM veya DMARC) geçirmeyen etki alanlarından kuruluşlarına hangi gönderenlerin yasal olarak e-posta gönderdiğini hızla belirleyebilir.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c54bdbb4ee8c3bf068b40df8cd5ca0a58da2392f
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787770"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Office 365 için Defender'de kimliğe bürünme içgörüleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Kimliğe bürünme, e-posta iletisini gönderenin gerçek veya beklenen gönderen e-posta adresine çok benzediği yerdir. Saldırganlar genellikle, alıcının güvenini kazanmak amacıyla kimlik avı veya diğer tür saldırılarda kimliğine bürünen gönderen e-posta adreslerinin kimliğine bürünülmektedir. Temelde iki tür kimliğe bürünme vardır:

- **Etki alanı kimliğe bürünme: kimliğine** bürünülen gönderenin e-posta adresi lila@contoso.com yerine lila@ćóntoso.com.
- **Kullanıcı kimliğe bürünme: Kimliğine bürünülen** gönderenin e-posta adresi michelle@contoso.com yerine rnichell@contoso.com.

Kimliğine bürünülen etki alanı genellikle gerçek, kayıtlı bir [etki alanı](anti-spoofing-protection.md) olduğundan etki alanı kimliğe bürünme, etki alanı kimlik sahtekarlığından farklıdır. Kimliğine bürünülen etki alanındaki gönderenlerden gelen iletiler, kimlik sahtekarlık girişimlerini (SPF, DKIM ve DMARC) belirleyebilecek normal e-posta kimlik doğrulama denetimlerini geçirebilir ve genellikle geçirebilir.

Kimliğe bürünme koruması, Office 365 için Microsoft Defender özel kimlik avı önleme ilkesi ayarlarının bir parçasıdır. Bu ayarlar hakkında daha fazla bilgi için bkz[. Office 365 için Microsoft Defender kimlik avı önleme ilkelerindeki kimliğe bürünme ayarları](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Kimliğe bürünme koruması için yapılandırdığınız kimliğine bürünülen gönderenlerden veya gönderen etki alanlarından gelen iletileri hızla tanımlamak için Microsoft 365 Defender portalındaki kimliğe bürünme içgörülerini kullanabilirsiniz.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. Doğrudan **Kimlik avı** önleme sayfasına gitmek için kullanın <https://security.microsoft.com/antiphishing>. **Kimliğe Bürünme içgörü** sayfasına doğrudan gitmek için kullanın<https://security.microsoft.com/impersonationinsight>.

- Bu makaledeki yordamları gerçekleştirebilmeniz için önce Microsoft 365 Defender portalında size izinler atanmalıdır:
  - **Kuruluş Yönetimi**
  - **Güvenlik Yöneticisi**
  - **Güvenlik Okuyucusu**
  - **Genel Okuyucu**

  Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md).

  **Not**: kullanıcıları Microsoft 365 yönetim merkezi karşılık gelen Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365 Defender portalında gerekli izinleri _ve_ Microsoft 365'teki diğer özellikler için izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).

- Office 365 için Microsoft Defender kimlik avı önleme ilkelerinde kimliğe bürünme korumasını etkinleştirir ve yapılandırabilirsiniz. Kimliğe bürünme koruması varsayılan olarak etkin değildir. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında kimliğe bürünme içgörülerini açma

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, İlkeler **bölümünde** **Email & İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Kimlik avı önleme** bölümüne gidin. Doğrudan **Kimlik avı** önleme sayfasına gitmek için kullanın <https://security.microsoft.com/antiphishing>.

2. **Kimlik avı önleme** sayfasında kimliğe bürünme içgörüleri şöyle görünür:

   :::image type="content" source="../../media/m365-sc-impersonation-insight.png" alt-text="Microsoft 365 Defender portalındaki Kimlik avı önleme ilkesi sayfasındaki kimliğe bürünme içgörüleri." lightbox="../../media/m365-sc-impersonation-insight.png":::

   İçgörü iki moda sahiptir:

    - **İçgörü modu**: Kimlik avı önleme ilkelerinde kimliğe bürünme koruması etkinleştirilir ve yapılandırılırsa içgörü, son yedi gün içinde kimliğine bürünülen etki alanlarından ve kimliğine bürünülen kullanıcılardan (gönderenler) gelen algılanan iletilerin sayısını gösterir. Bu, tüm kimlik avı önleme ilkelerinden algılanan tüm kimliğine bürünülen gönderenlerin toplamıdır.
    - **Durum modu**: Herhangi bir etkin kimlik avı önleme ilkesinde kimliğe bürünme koruması etkinleştirilmemiş ve yapılandırılmamışsa, içgörü size son yedi gün içinde kimliğe bürünme koruması özelliklerimiz tarafından *kaç ileti* algılandığını gösterir.

Kimliğe bürünme algılamaları hakkındaki bilgileri görüntülemek için kimliğe bürünme içgörüsüsünde **Kimliğe bürünmeleri görüntüle'ye** tıklayın.

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Kimliğine bürünülen etki alanlarındaki gönderenlerden gelen iletiler hakkındaki bilgileri görüntüleme

**Kimliğe bürünme içgörüsüsünde** **Kimliğe bürünmeleri görüntüle'ye** tıkladıktan sonra görüntülenen Kimliğe Bürünme içgörüleri sayfasında **, Etki Alanları** sekmesinin seçili olduğunu doğrulayın. **Etki Alanları** sekmesi aşağıdaki bilgileri içerir:

- **Gönderen Etki Alanı**: E-posta iletisini göndermek için kullanılan etki alanı olan kimliğe bürünen etki alanı.
- **İleti sayısı**: Son 7 gün içinde gönderen etki alanının kimliğine bürünen ileti sayısı.
- **Kimliğe bürünme türü**: Bu değer kimliğe bürünme işleminin algılanan konumunu gösterir (örneğin, **Adresteki etki alanı**).
- **Kimliğine bürünülen etki alanları**: Kimliğine bürünülen etki alanı, kimlik avı önleme ilkesinde kimliğe bürünme koruması için yapılandırılan etki alanına benzer olmalıdır.
- **Etki alanı türü**: Bu değer şirket **etki alanları için Şirket etki alanı** veya özel etki alanları için **özel etki alanıdır** .
- **İlke**: Kimliğine bürünülen etki alanını algılayan kimlik avı önleme ilkesi.
- **Kimliğine bürünme izni verildi**: Aşağıdaki değerlerden biri:
  - **Evet**: Etki alanı kimlik avı önleme ilkesinde güvenilen etki alanı (kimliğe bürünme koruması için özel durum) olarak yapılandırıldı. Kimliğine bürünülen etki alanındaki gönderenlerden gelen iletiler algılandı, ancak izin verildi.
  - **Hayır**: Etki alanı kimlik avı önleme ilkesinde kimliğe bürünme koruması için yapılandırıldı. Kimliğine bürünülen etki alanındaki gönderenlerden gelen iletiler algılandı ve kimlik avı önleme ilkesindeki kimliğine bürünülen etki alanlarının eylemine göre işlem yapıldı.

Sonuçları sıralamak için seçili sütun başlıklarına tıklayabilirsiniz.

Sonuçları filtrelemek için Ara simgesini kullanabilirsiniz ![.](../../media/m365-cc-sc-search-icon.png) Sonuçları filtrelemek için virgülle ayrılmış bir değer listesi girmek için **arama** kutusu.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Kimliğine bürünülen etki alanlarındaki gönderenlerden gelen iletiler hakkındaki ayrıntıları görüntüleme

**Kimliğe Bürünme içgörüleri** sayfasındaki **Etki Alanları** sekmesinde, kullanılabilir kimliğe bürünme algılamalarından birini seçin. Görüntülenen ayrıntılar açılır öğesi aşağıdaki bilgileri ve özellikleri içerir:

- **Değiştireceğiniz seçim kimliğe bürünme ilkesi**: Değiştirmek istediğiniz etkilenen kimlik avı önleme ilkesini seçin. Yalnızca ilkede kimliğine bürünülen etki alanının tanımlandığı ilkeler kullanılabilir. Kimliğe bürünülen etki alanını algılamaktan sorumlu olan ilkeyi (büyük olasılıkla alıcıya ve ilkenin önceliğine göre) görmek için önceki sayfaya bakın.
- **Kimliğe bürünmeye izin verilenler listesine ekle**: Seçtiğiniz kimlik avı önleme ilkesi için **güvenilir gönderenler ve etki alanları** (kimliğe bürünme özel durumları) için göndereni eklemek veya kaldırmak için bu iki durumlu düğmeyi kullanın:
  - Bu giriş **için Kimliğine bürünme izni verilen** değeri **Hayır** ise, iki durumlu düğme kapalıdır. Bu etki alanındaki tüm gönderenleri kimliğe bürünme korumasıyla değerlendirmeden muaf tutabilmek için iki durumlu düğmeyi açık konuma getirin: ![Açık.](../../media/scc-toggle-on.png). Etki alanı, kimlik avı önleme ilkesinin kimliğe bürünme koruma ayarlarındaki **Güvenilen etki alanları** listesine eklenir.
  - Bu girdi **için Kimliğine bürünme izni verilen** değeri **Evet** ise, iki durumlu düğme açık olur. Bu etki alanındaki tüm gönderenleri kimliğe bürünme korumasıyla değerlendirmeye döndürmek için, geçiş düğmesini kapalı konuma getirin: ![Kapalı.](../../media/scc-toggle-off.png). Etki alanı, kimlik avı önleme ilkesinin kimliğe bürünme koruması ayarlarında **Güvenilen etki alanları** listesinden kaldırılır.
- Bunu neden yakaladığımızı.
- Yapmanız gerekenler.
- Kimliğine bürünülen etki alanını listeleyen bir etki alanı özeti.
- WhoIs verileri gönderen hakkında.
- Gönderen hakkında ek ayrıntıları görmek için [Tehdit Gezgini'ni](threat-explorer.md) açma bağlantısı.
- Kuruluşunuza teslim edilen aynı gönderenden gelen benzer iletiler.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Kimliğine bürünülen gönderenlerden gelen iletiler hakkındaki bilgileri görüntüleme

**Kimliğe bürünme içgörüsüsünde** **Kimliğe bürünmeleri görüntüle'ye** tıkladıktan sonra görüntülenen Kimliğe Bürünme içgörüleri sayfasında **Kullanıcılar** sekmesine tıklayın. **Kullanıcılar** sekmesi aşağıdaki bilgileri içerir:

- **Gönderen**: E-posta iletisini gönderen kimliğine bürünen gönderenin e-posta adresi.
- **İleti sayısı**: Son 7 gün içinde kimliğe bürünen gönderenden gelen ileti sayısı.
- **Kimliğe bürünme türü**: Bu değer **görünen addaki Kullanıcı değeridir**.
- **Kimliğine bürünülen kullanıcılar**: Kimliğine bürünülen gönderenin e-posta adresi, kimlik avı önleme ilkesinde kimliğe bürünme koruması için yapılandırılan kullanıcıya benzer olmalıdır.
- **Kullanıcı türü**: Bu değer uygulanan koruma türünü gösterir (örneğin, **Korumalı kullanıcı** veya **Posta Kutusu Yönetim Bilgileri**).
- **İlke**: Kimliğine bürünülen göndereni algılayan kimlik avı önleme ilkesi.
- **Kimliğine bürünme izni verildi**: Aşağıdaki değerlerden biri:
  - **Evet**: Gönderen, kimlik avı önleme ilkesinde güvenilir kullanıcı (kimliğe bürünme koruması için özel durum) olarak yapılandırıldı. Kimliğine bürünülen gönderenden gelen iletiler algılandı, ancak izin verildi.
  - **Hayır**: Gönderen, kimlik avı önleme ilkesinde kimliğe bürünme koruması için yapılandırıldı. Kimliğine bürünülen gönderenden gelen iletiler algılandı ve kimlik avı önleme ilkesindeki kimliğine bürünülen kullanıcılara yönelik eyleme göre işlem yapıldı.

Sonuçları sıralamak için seçili sütun başlıklarına tıklayabilirsiniz.

Sonuçları filtrelemek için, Sonuçları filtrelemek üzere virgülle ayrılmış bir değer listesi girmek için **Göndereni** filtrele kutusunu kullanabilirsiniz.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Kimliğine bürünülen gönderenlerden gelen iletiler hakkındaki ayrıntıları görüntüleme

**Kimliğe Bürünme içgörüleri** sayfasındaki **Kullanıcılar** sekmesinde, kullanılabilir kimliğe bürünme algılamalarından birini seçin. Görüntülenen ayrıntılar açılır öğesi aşağıdaki bilgileri ve özellikleri içerir:

- **Değiştireceğiniz seçim kimliğe bürünme ilkesi**: Değiştirmek istediğiniz etkilenen kimlik avı önleme ilkesini seçin. Yalnızca ilkede kimliğine bürünülen gönderenin tanımlandığı ilkeler kullanılabilir. Kimliğine bürünülen göndereni (büyük olasılıkla alıcıya ve ilkenin önceliğine göre) algılamaktan sorumlu olan ilkeyi görmek için önceki sayfaya bakın.
- **Kimliğe bürünmeye izin verilenler listesine ekle**: Seçtiğiniz kimlik avı önleme ilkesi için **güvenilir gönderenler ve etki alanları** (kimliğe bürünme özel durumları) için göndereni eklemek veya kaldırmak için bu iki durumlu düğmeyi kullanın:
  - Bu giriş **için Kimliğine bürünme izni verilen** değeri **Hayır** ise, iki durumlu düğme kapalıdır. Kimliğe bürünme koruması ile göndereni değerlendirmeden muaf tutabilmek için iki durumlu düğmeyi açık konuma getirin: ![Açık.](../../media/scc-toggle-on.png). Gönderen, kimlik avı önleme ilkesinin kimliğe bürünme koruması ayarlarında **Güvenilen kullanıcılar** listesine eklenir.
  - Bu girdi **için Kimliğine bürünme izni verilen** değeri **Evet** ise, iki durumlu düğme açık olur. Kimliğe bürünme korumasıyla göndereni değerlendirmeye döndürmek için iki durumlu düğmeyi kapalı konuma getirin: ![Kapalı.](../../media/scc-toggle-off.png). Gönderen, kimlik avı önleme ilkesinin kimliğe bürünme koruması ayarlarında **Güvenilen kullanıcılar** listesinden kaldırılır.
- Bunu neden yakaladığımızı.
- Yapmanız gerekenler.
- Kimliğine bürünülen göndereni listeleyen bir gönderen özeti.
- WhoIs verileri gönderen hakkında.
- Gönderen hakkında ek ayrıntıları görmek için [Tehdit Gezgini'ni](threat-explorer.md) açma bağlantısı.
- Kuruluşunuza teslim edilen aynı gönderenden gelen benzer iletiler.
