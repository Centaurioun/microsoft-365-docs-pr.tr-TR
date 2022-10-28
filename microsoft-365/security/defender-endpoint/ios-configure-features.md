---
title: iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın
description: iOS özelliklerinde Uç Nokta için Microsoft Defender nasıl dağıtılacağı açıklanır.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, ios, configure, features, ios
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 2b0046df2cd01ada1ce2816520c9878858a133f7
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68768257"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS üzerinde Uç Nokta için Defender, Web Koruması özelliğini sağlamak için bir VPN kullanır. Bu normal bir VPN değildir ve cihazın dışına trafiği almayan yerel/kendi kendini döngüye alan bir VPN'dir.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>iOS'ta Uç Nokta için Defender ile Koşullu Erişim

Microsoft Intune ve Azure Active Directory ile birlikte iOS'ta Uç Nokta için Microsoft Defender, cihaz risk puanına göre Cihaz uyumluluğu ve Koşullu Erişim ilkelerinin zorunlu tutmasını sağlar. Uç Nokta için Defender, Intune aracılığıyla bu özelliği kullanmak için dağıtabileceğiniz bir Mobile Threat Defense (MTD) çözümüdür.

iOS'ta Uç Nokta için Defender ile Koşullu Erişim'i ayarlama hakkında daha fazla bilgi için bkz. [Uç Nokta için Defender ve Intune](/mem/intune/protect/advanced-threat-protection).

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender tarafından jailbreak algılama

Uç Nokta için Microsoft Defender, jailbreak uygulanmış yönetilmeyen ve yönetilen cihazları algılama özelliğine sahiptir. Bir cihazın jailbreak işlemi gerçekleştirildiği algılanırsa, Microsoft 365 Defender portalına **yüksek** riskli bir uyarı bildirilir ve Cihaz risk puanına göre Koşullu Erişim ayarlanırsa cihazın şirket verilerine erişimi engellenir.

## <a name="web-protection-and-vpn"></a>Web Koruması ve VPN

Varsayılan olarak, iOS'ta Uç Nokta için Defender web koruma özelliğini içerir ve etkinleştirir. [Web koruması](web-protection-overview.md) , cihazların web tehditlerine karşı korunmasına ve kullanıcıların kimlik avı saldırılarına karşı korunmasına yardımcı olur. Web Koruması'nın bir parçası olarak kimlik avı önleme ve özel göstergelerin (URL ve IP adresleri) desteklendiğini unutmayın. Web İçeriği Filtreleme şu anda mobil platformlarda desteklenmiyor.

iOS'ta Uç Nokta için Defender bu özelliği sağlamak için bir VPN kullanır. Bunun yerel bir VPN olduğunu ve geleneksel VPN'nin aksine ağ trafiğinin cihazın dışına gönderilmediğini lütfen unutmayın.

Varsayılan olarak etkinleştirildiğinde VPN'yi devre dışı bırakmanızı gerektiren bazı durumlar olabilir. Örneğin, VPN yapılandırıldığında çalışmayan bazı uygulamaları çalıştırmak istiyorsunuz. Bu gibi durumlarda, aşağıdaki adımları izleyerek cihazdaki uygulamadan VPN'i devre dışı bırakabilirsiniz:

1. iOS cihazınızda **Ayarlar** uygulamasını açın, **Genel'e** ve ardından **VPN'ye** tıklayın veya dokunun.

2. Uç Nokta için Microsoft Defender için "i" düğmesine tıklayın veya dokunun.

3. VPN'yi devre dışı bırakmak için **İsteğe Bağlı Bağlan'ı** kapatın. 

   :::image type="content" source="images/ios-vpn-config.png" alt-text="VPN yapılandırması İsteğe bağlı bağlan seçeneği için iki durumlu düğme" lightbox="images/ios-vpn-config.png":::

> [!NOTE]
> VPN devre dışı bırakıldığında Web Koruması kullanılamaz. Web Koruması'nı yeniden etkinleştirmek için cihazda Uç Nokta için Microsoft Defender uygulamasını açın ve **VPN Başlat'a** tıklayın veya dokunun.

## <a name="disable-web-protection"></a>Web Korumasını Devre Dışı Bırak

Web Koruması, Uç Nokta için Defender'ın temel özelliklerinden biridir ve bu özelliği sağlamak için bir VPN gerektirir. Kullanılan VPN, geleneksel bir VPN değil yerel/geri döngü VPN'dir, ancak müşterilerin VPN'yi tercih etmemelerinin çeşitli nedenleri vardır. VPN ayarlamak istemeyen müşteriler, Bu özellik olmadan **Web Koruması'nın** devre dışı bırakılması ve Uç Nokta için Defender'ın dağıtılması seçeneği vardır. Diğer Uç Nokta için Defender özellikleri çalışmaya devam edecektir.

Bu yapılandırma hem kayıtlı (MDM) cihazlar hem de kayıtlı olmayan (MAM) cihazlar için kullanılabilir. MDM'ye sahip müşteriler için yöneticiler Web **Koruması'nı** Uygulama Yapılandırması'ndaki Yönetilen cihazlar aracılığıyla yapılandırabilir. Yöneticiler, MAM kullanarak kaydı olmayan müşteriler için **Web Koruması'nı** Uygulama Yapılandırması'ndaki Yönetilen uygulamalar aracılığıyla yapılandırabilir.

### <a name="configure-web-protection"></a>Web Korumasını Yapılandırma

1. **Web Korumasını Devre Dışı Bırak (MDM)** Kayıtlı cihazlar için **Web Koruması'nı** devre dışı bırakmak için aşağıdaki adımları kullanın.

    - [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen cihazlar** **ekle'ye** >  gidin.
    - İlkeye **iOS/iPadOS > Platform** adını verin.
    - Hedef uygulama olarak Uç Nokta için Microsoft Defender seçin.
    - Ayarlar sayfasında Yapılandırma tasarımcısını kullan'ı seçin ve anahtar ve değer türü olarak **WebProtection** değerini **Dize** olarak ekleyin.
        - Varsayılan olarak **, WebProtection= true**.
        - Yönetici web korumasını kapatmak için **WebProtection = false** yapması gerekir.
        - Defender, kullanıcı uygulamayı her açtığında sinyali Microsoft 365 Defender portalına gönderir.
        - İleri'ye tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.

1. **Web Korumasını Devre Dışı Bırakma (MAM)** Kaydı kaldırılan cihazlarda **Web Koruması'nı** devre dışı bırakmak için aşağıdaki adımları kullanın.

    - [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen uygulamalar** **ekle'ye** >  gidin.
    - İlkeye bir ad verin.
    - Genel Uygulamaları Seç'in altında hedef uygulama olarak Uç Nokta için Microsoft Defender'ı seçin.
    - Ayarlar sayfasında, Genel Yapılandırma Ayarları'nın altında anahtar olarak **WebProtection** ve **false** olarak değer ekleyin.
        - Varsayılan olarak **, WebProtection= true**.
        - Yönetici web korumasını kapatmak için **WebProtection = false** yapması gerekir.
        - Defender, kullanıcı uygulamayı her açtığında sinyali Microsoft 365 Defender portalına gönderir.
        - İleri'ye tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.

## <a name="configure-network-protection"></a>Ağ Korumasını Yapılandırma


Uç nokta için Microsoft Defender'da ağ koruması varsayılan olarak devre dışıdır. Yöneticiler, iOS cihazlarında Ağ koruması için MAM desteğini yapılandırmak için aşağıdaki adımları kullanabilir. iOS cihazlarında (MAM yapılandırması için doğrulayıcı cihaz kaydı gereklidir). Ağ Koruması başlatma işlemi için son kullanıcının uygulamayı bir kez açması gerekir. 

1. Microsoft Endpoint Manager Yönetici Uygulamalar > Uygulama yapılandırma ilkeleri'ne gidin. Yeni bir Uygulama yapılandırma ilkesi oluşturun.
   :::image type="content" source="images/addiosconfig.png" alt-text="Yapılandırma ilkesi ekleyin." lightbox="images/addiosconfig.png":::

2. İlkeyi benzersiz olarak tanımlamak için bir ad ve açıklama sağlayın. Ardından 'Genel uygulamaları seç'e tıklayın ve Platform iOS/IPadOS için 'Microsoft Defender' öğesini seçin :::image type="content" source="images/nameiosconfig.png" alt-text="Yapılandırmayı adlandırın." lightbox="images/nameiosconfig.png":::

3. Ayarlar sayfasında, Ağ Koruması'nı devre dışı bırakmak için anahtar olarak 'DefenderNetworkProtectionEnable' değerini ve 'true' olarak değerini ekleyin. (Ağ koruması varsayılan olarak devre dışıdır) :::image type="content" source="images/addiosconfigvalue.png" alt-text="Yapılandırma değeri ekleyin." lightbox="images/addiosconfigvalue.png":::

4. Ağ korumasıyla ilgili diğer yapılandırmalar için aşağıdaki anahtarları ve uygun değeri ekleyin.

    |Tuş| Varsayılan (true-enable, false-disable)|Açıklama|
    |---|---|---|
    |DefenderOpenNetworkDetection|0|1- Etkinleştir, 0 - Devre Dışı Bırak; Bu ayar, son kullanıcı algılama deneyimi olmadan açık ağ algılama bilgilendirme uyarılarını etkinleştirmek veya devre dışı bırakmak için BT Yönetici tarafından yönetilir|
    |DefenderEndUserTrustFlowEnable| False | Kullanıcıların Ağlara ve Sertifikalara Güvenmesini Sağlama|
    |DefenderNetworkProtectionAutoRemediation| True |Bu ayar, bir kullanıcı daha güvenli WIFI erişim noktalarına geçme veya Defender tarafından algılanan şüpheli sertifikaları silme gibi düzeltme etkinlikleri gerçekleştirdiğinde gönderilen düzeltme uyarılarını etkinleştirmek veya devre dışı bırakmak için BT yöneticisi tarafından kullanılır|
    |DefenderNetworkProtectionPrivacy| True |Bu ayar, ağ korumasında gizliliği etkinleştirmek veya devre dışı bırakmak için BT yöneticisi tarafından yönetilir|
  
5. Atamalar bölümünde yönetici, ilkeye dahil etmek ve ilkeden dışlamak için kullanıcı gruplarını seçebilir.
   :::image type="content" source="images/assigniosconfig.png" alt-text="Yapılandırmayı atayın." lightbox="images/assigniosconfig.png":::

6. Yapılandırma ilkesini gözden geçirin ve oluşturun.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Birden çok VPN profilinin birlikte bulunması

Apple iOS, cihaz genelinde birden çok VPN'in aynı anda etkin olmasını desteklemez. Cihazda birden çok VPN profili bulunabilir ancak aynı anda yalnızca bir VPN etkin olabilir.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Uygulama koruma ilkesinde (MAM) Uç Nokta için Microsoft Defender risk sinyalini yapılandırma

Uç Nokta için Microsoft Defender, iOS/iPadOS'ta Uygulama Koruma İlkeleri'nde (MAM olarak da bilinir) kullanılacak tehdit sinyalleri gönderecek şekilde yapılandırılabilir. Bu özellik sayesinde, şirket verilerine erişimi kayıtlı olmayan cihazlardan korumak için de Uç Nokta için Microsoft Defender kullanabilirsiniz.

Uç Nokta için Microsoft Defender ile uygulama koruma ilkelerini ayarlama adımları aşağıdadır:

1. Microsoft Endpoint Manager kiracınızdan Uç Nokta için Microsoft Defender bağlantısını ayarlayın. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Kiracı Yönetim** \> **Bağlayıcıları ve belirteçleri Uç Nokta için Microsoft Defender (Platformlar** \> arası altında) veya **Endpoint Security** \> **Uç Nokta için Microsoft Defender** (Kurulum altında) bölümüne gidin ve  **iOS için Uygulama Koruma İlkesi Ayarları**.

2. Kaydet'i seçin. **Bağlantı durumunun** artık **Etkin** olarak ayarlandığını görmeniz gerekir.

3. Uygulama koruma ilkesi oluşturma: Uç Nokta için Microsoft Defender bağlayıcı kurulumunuz tamamlandıktan sonra, yeni bir ilke oluşturmak veya var olan bir ilkeyi güncelleştirmek için **Uygulamalar** \> **Uygulama koruması ilkeleri'ne** gidin (İlke'nin altında).

4. Kuruluşunuzun ilkeniz için gerektirdiği platform, **Uygulamalar, Veri koruması, Erişim gereksinimleri** ayarlarını seçin.

5. **Koşullu başlatma** \> **Cihaz koşulları** altında **İzin verilen en fazla cihaz tehdit düzeyi** ayarını bulacaksınız. Bunun Düşük, Orta, Yüksek veya Güvenli olarak yapılandırılması gerekir. Kullanabileceğiniz eylemler **Erişimi engelle** veya **Verileri sil** olacaktır. Bağlayıcınızın bu ayardan önce ayarlandığından emin olmak için bilgilendirici bir iletişim kutusu görebilirsiniz. Bağlayıcınız zaten ayarlanmışsa, bu iletişim kutusunu yoksayabilirsiniz.

6. Ödevler ile bitirin ve ilkenizi kaydedin.

MAM veya uygulama koruma ilkesi hakkında daha fazla ayrıntı için bkz. [iOS uygulama koruma ilkesi ayarları](/mem/intune/apps/app-protection-policy-settings-ios).

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM için veya kaydı kaldırılmış cihazlarda Uç Nokta için Microsoft Defender dağıtma

iOS'ta Uç Nokta için Microsoft Defender, Uygulama Koruma İlkesi senaryosuna olanak tanır ve Apple uygulama mağazasında kullanılabilir. Son kullanıcılar uygulamanın en son sürümünü doğrudan Apple uygulama mağazasından yüklemelidir.

## <a name="privacy-controls"></a>Gizlilik Denetimleri

iOS'ta Uç Nokta için Microsoft Defender, hem Yöneticiler hem de Son Kullanıcılar için Gizlilik Denetimleri'ni etkinleştirir. Bu, kayıtlı (MDM) ve kaydı kaldırılmış (MAM) cihazlar için denetimleri içerir.
MDM'ye sahip müşteriler için yöneticiler, Uygulama Yapılandırması'ndaki Yönetilen cihazlar aracılığıyla Gizlilik Denetimlerini yapılandırabilir. Mam kullanarak kayıt olmayan müşteriler için yöneticiler, Uygulama Yapılandırması'ndaki Yönetilen uygulamalar aracılığıyla Gizlilik Denetimlerini yapılandırabilir. Son Kullanıcılar, Defender Uygulama ayarlarından Gizlilik Ayarlarını da yapılandırabilirsiniz.

### <a name="configure-privacy-in-phish-alert-report"></a>Kimlik avı uyarısı raporunda gizliliği yapılandırma

Müşteriler artık iOS'ta Uç Nokta için Microsoft Defender tarafından gönderilen kimlik avı raporu için gizlilik denetimini etkinleştirebilir. Bu, bir kimlik avı web sitesi algılandığında ve Uç Nokta için Microsoft Defender tarafından engellendiğinde etki alanı adının kimlik avı uyarısının bir parçası olarak gönderilmemesini sağlar.

1. **Yönetici Gizlilik Denetimleri (MDM)** Kayıtlı cihazlar için kimlik avı uyarısı raporunun bir parçası olarak etki alanı adını toplamamak ve gizliliği etkinleştirmek için aşağıdaki adımları kullanın.

    - [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen cihazlar** **ekle'ye** >  gidin.

    - İlkeye **iOS/iPadOS > Platform** adını verin, profil türünü seçin.

    - Hedef uygulama olarak **Uç Nokta için Microsoft Defender'ı** seçin.

    - Ayarlar sayfasında **Yapılandırma tasarımcısını kullan'ı** seçin ve anahtar ve değer türü Olarak **DefenderExcludeURLInReport** değerini **Boole olarak** ekleyin.

      - Gizliliği etkinleştirmek ve etki alanı adını toplamamak için olarak `true` değer girin ve bu ilkeyi kullanıcılara atayın. Varsayılan olarak, bu değer olarak `false`ayarlanır.

      - olarak ayarlanmış `true`anahtara sahip kullanıcılar için, kötü amaçlı bir site algılandığında ve Uç Nokta için Defender tarafından engellendiğinde kimlik avı uyarısı etki alanı adı bilgilerini içermez.

    - **İleri'ye** tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.

1. **Yönetici Gizlilik Denetimleri (MAM)** Gizliliği etkinleştirmek ve kaydı kaldırılan cihazlar için kimlik avı uyarısı raporunun bir parçası olarak etki alanı adını toplamamak için aşağıdaki adımları kullanın.

    - [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen uygulamalar** **ekle'ye** >  gidin.

    - İlkeye bir ad verin.

    - Genel Uygulamaları Seç'in altında hedef uygulama olarak **Uç Nokta için Microsoft Defender'ı** seçin.

    - Ayarlar sayfasında,  **Genel Yapılandırma Ayarları** altında **Anahtar olarak DefenderExcludeURLInReport** değerini ve **true** değerini ekleyin.

      - Gizliliği etkinleştirmek ve etki alanı adını toplamamak için olarak `true` değer girin ve bu ilkeyi kullanıcılara atayın. Varsayılan olarak, bu değer olarak `false`ayarlanır.

      - olarak ayarlanmış `true`anahtara sahip kullanıcılar için, kötü amaçlı bir site algılandığında ve Uç Nokta için Defender tarafından engellendiğinde kimlik avı uyarısı etki alanı adı bilgilerini içermez.

    - **İleri'ye** tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.

1. **Son Kullanıcı Gizlilik Denetimleri** Bu denetimler, son kullanıcının kendi kuruluşuyla paylaşılan bilgileri yapılandırmasına yardımcı olur.
    - Denetimli cihazlar için Son Kullanıcı denetimleri görünmez. Yönetici ayarlara karar verir ve ayarları denetler.
    - Ancak Denetimsiz cihazlar için denetim **Ayarlar > Gizlilik** altında görüntülenir
        - Kullanıcılar **Güvenli Olmayan Site Bilgileri** için bir geçiş düğmesi görür.
        - Bu iki durumlu düğme yalnızca Yönetici **DefenderExcludeURLInReport = true** olarak ayarlamışsa görünür
        - kullanıcılar, Yönetici tarafından etkinleştirilirse, güvenli olmayan site bilgilerini Kuruluşlarına göndermek isteyip istemediklerine karar verebilir.
        - Varsayılan olarak olarak olarak ayarlanır `true`, güvenli olmayan site bilgileri gönderilir.
        - Kullanıcı bunu `false`olarak değiştirirse, güvenli olmayan site ayrıntıları gönderilmez.

Yukarıdaki gizlilik denetimlerini açmak veya kapatmak, cihaz uyumluluk denetimini veya koşullu erişimi etkilemez.

## <a name="optional-permissions"></a>İsteğe Bağlı İzinler

iOS'ta Uç Nokta için Microsoft Defender, ekleme akışında **İsteğe Bağlı İzinler'i** etkinleştirir. Şu anda ekleme akışında Uç Nokta için Defender'ın gerektirdiği izinler zorunludur. Bu özellik sayesinde yöneticiler, ekleme sırasında zorunlu **VPN İznini** zorunlu tutmadan KCG cihazlarına Uç Nokta için Defender'ı dağıtabilir. Son kullanıcılar zorunlu izinler olmadan uygulamayı ekleyebilir ve daha sonra bu izinleri gözden geçirebilir. Bu özellik şu anda yalnızca kayıtlı cihazlar (MDM) için mevcuttur.

### <a name="configure-optional-permission"></a>İsteğe Bağlı İzni Yapılandırma

1. **Yönetici akışı (MDM)** Kayıtlı cihazlar için **İsteğe bağlı VPN** iznini etkinleştirmek için aşağıdaki adımları kullanın.

    - [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen cihazlar** **ekle'ye** >  gidin.

    - İlkeye bir ad verin, **iOS/iPadOS > Platform'u** seçin.

    - Hedef uygulama olarak **Uç Nokta için Microsoft Defender'ı** seçin.

    - Ayarlar sayfasında **Yapılandırma tasarımcısını kullan'ı** seçin ve anahtar ve değer türü olarak **DefenderOptionalVPN'i** **Boole olarak** ekleyin.

      - İsteğe bağlı VPN iznini etkinleştirmek için olarak `true` değer girin ve bu ilkeyi kullanıcılara atayın. Varsayılan olarak, bu değer olarak `false`ayarlanır.
      - anahtar ayarı olarak `true`ayarlanmış kullanıcılar için kullanıcılar, VPN izni vermeden uygulamayı ekleyebilecektir.

    - **İleri'ye** tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.
1. **Son Kullanıcı akışı** - Kullanıcı, ekleme işlemini başlatmak için uygulamayı yükleyip açar.
    - Yöneticinin kurulumu İsteğe bağlı izinler varsa, kullanıcı VPN iznini **atlayabilir** ve ekleme işlemini tamamlayabilir.
    - Kullanıcı VPN'yi atlamış olsa bile cihaz eklenebilir ve sinyal gönderilir.
    - Devre dışı bırakıldığından `VPN` etkin `Web Protection` olmaz.
    - Daha sonra Kullanıcı, uygulamasını Uygulamanın içinden etkinleştirebilir `Web Protection` . Bu, cihaza VPN yapılandırmasını yükler.

> [!NOTE]
>**İsteğe bağlı İzin****, Web Korumasını Devre Dışı Bırak'tan** farklıdır. İsteğe bağlı VPN İzni yalnızca ekleme sırasında iznin atlanmasına yardımcı olur, ancak son kullanıcının daha sonra gözden geçirip etkinleştirmesi için kullanılabilir. **Web Korumasını Devre Dışı Bırak** özelliği kullanıcıların Web Koruması olmadan Uç Nokta için Defender uygulamasını eklemesine olanak tanır. Daha sonra etkinleştirilemez.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Jailbreak uygulanmış cihazlara karşı uyumluluk ilkesini yapılandırma

Şirket verilerinin jailbreak uygulanmış iOS cihazlarında erişilmeye karşı korunması için, Intune'de aşağıdaki uyumluluk ilkesini ayarlamanızı öneririz.

> [!NOTE]
> Jailbreak algılama, iOS'ta Uç Nokta için Microsoft Defender tarafından sağlanan bir özelliktir. Ancak, bu ilkeyi jailbreak senaryolarına karşı ek bir savunma katmanı olarak ayarlamanızı öneririz.

Jailbreak uygulanmış cihazlara karşı uyumluluk ilkesi oluşturmak için aşağıdaki adımları izleyin.

1. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Cihaz** > **Uyumluluk ilkeleri** > **İlke Oluştur'a** gidin. Platform olarak "iOS/iPadOS" öğesini seçin ve **Oluştur'a** tıklayın.

   :::image type="content" source="images/ios-jb-policy.png" alt-text="İlke Oluştur sekmesi" lightbox="images/ios-jb-policy.png":::

1. İlkenin adını belirtin, örneğin "Jailbreak için Uyumluluk İlkesi".

1. Uyumluluk ayarları sayfasında **Cihaz Durumu** bölümünü genişletmek için tıklayın ve **Jailbreak uygulanmış cihazlar** için **engelle** alanına tıklayın.

   :::image type="content" source="images/ios-jb-settings.png" alt-text="Uyumluluk ayarları sekmesi" lightbox="images/ios-jb-settings.png":::

1. **Uyumsuzluk eylemleri** bölümünde, gereksinimlerinize göre eylemleri seçin ve **İleri'yi** seçin.

   :::image type="content" source="images/ios-jb-actions.png" alt-text="Uyumsuzluk eylemleri sekmesi" lightbox="images/ios-jb-actions.png":::

1. **Atamalar** bölümünde, bu ilke için eklemek istediğiniz kullanıcı gruplarını seçin ve ardından **İleri'yi** seçin.

1. **Gözden Geçir+Oluştur** bölümünde, girilen tüm bilgilerin doğru olduğunu doğrulayın ve **Oluştur'u** seçin.

## <a name="configure-custom-indicators"></a>Özel göstergeleri yapılandırma

iOS'ta Uç Nokta için Defender, yöneticilerin iOS cihazlarında da özel göstergeler yapılandırmasına olanak tanır. Özel göstergeleri yapılandırma hakkında daha fazla bilgi için bkz. [Göstergeleri yönetme](/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> iOS üzerinde Uç Nokta için Defender yalnızca IP adresleri ve URL'ler/etki alanları için özel göstergeler oluşturmayı destekler.

## <a name="configure-vulnerability-assessment-of-apps"></a>Uygulamaların güvenlik açığı değerlendirmesini yapılandırma

>[!Note]
>iOS için Uç Nokta için Microsoft Defender'deki uygulamaların Güvenlik Açığı Değerlendirmesi artık genel önizleme aşamasındadır. Aşağıdaki bilgiler, ürünün ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen ön sürümüyle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez. Önizlemeye katılmak istiyorsanız lütfen kiracı adınızı ve kimliğinizi **mdatpmobile@microsoft.com** bizimle paylaşın.

iOS üzerinde Uç Nokta için Defender, yalnızca kayıtlı (MDM) cihazlar için uygulamaların güvenlik açığı değerlendirmelerini destekler.

Yöneticiler, uygulamaların güvenlik açığı değerlendirmesini yapılandırmak için aşağıdaki adımları kullanabilir.

### <a name="on-a-supervised-device"></a>Denetimli Cihazda

1. Cihazın [Denetimli modda](ios-install.md#complete-deployment-for-supervised-devices) yapılandırıldığından emin olun.
1. [Özelliği Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) etkinleştirmek için **Endpoint Security** >  **Uç Nokta için Microsoft Defender** >  **iOS/iPadOS cihazları için Uygulama eşitlemeyi etkinleştir'e** gidin.

     :::image type="content" source="images/tvm-app-sync-toggle.png" alt-text="Uygulama eşitleme iki durumlu düğmesiSup" lightbox="images/tvm-app-sync-toggle.png":::

### <a name="on-an-unsupervised-device"></a>Denetimsiz Cihazda

1. [Özelliği Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) etkinleştirmek için **Endpoint Security** >  **Uç Nokta için Microsoft Defender** >  **iOS/iPadOS cihazları için Uygulama eşitlemeyi etkinleştir'e** gidin.

   :::image type="content" source="images/tvm-app-sync-toggle.png" alt-text="Uygulama eşitleme iki durumlu düğmesi" lightbox="images/tvm-app-sync-toggle.png":::

1. Yönetilmeyen uygulamalar da dahil olmak üzere tüm uygulamaların listesini almak için **, Kişisel iOS/iPad OS Cihazlarında Tam uygulama envanteri verilerini gönder** iki durumlu düğmesini etkinleştirin.

    :::image type="content" source="images/tvm-full-app-data.png" alt-text="Tam Uygulama Verileri" lightbox="images/tvm-full-app-data.png":::

1. Gizlilik ayarını yapılandırmak için aşağıdaki adımları kullanın.
    - **Uygulamalar** > **Uygulama yapılandırma ilkeleri** > **Yönetilen cihazlar** **ekle'ye** >  gidin.
    - İlkeye **Platform** > **iOS/iPadOS** adını verin.
    - Hedef uygulama olarak **Uç Nokta için Microsoft Defender'ı** seçin.
    - Ayarlar sayfasında Yapılandırma tasarımcısını kullan'ı seçin ve anahtar ve değer türü olarak **DefenderTVMPrivacyMode** değerini **Dize** olarak ekleyin
        - Gizliliği devre dışı bırakmak ve yüklü uygulamaların listesini toplamak için olarak `False` değer girin ve bu ilkeyi kullanıcılara atayın. 
        - Bu değer, denetimsiz cihazlar için varsayılan olarak olarak ayarlanır `True` .
        - anahtarı olarak `False`ayarlanmış kullanıcılar için Uç Nokta için Defender, güvenlik açığı değerlendirmesi için cihazda yüklü uygulamaların listesini gönderir.
    - **İleri'ye** tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.
    - Yukarıdaki gizlilik denetimlerini açmak veya kapatmak, cihaz uyumluluk denetimini veya koşullu erişimi etkilemez.
1. Yapılandırma uygulandıktan sonra, son kullanıcının gizlilik ayarını **onaylaması** için uygulamayı açması gerekir.
    - Gizlilik onayı ekranı yalnızca denetimsiz cihazlar için gelir.
    - Yalnızca son kullanıcı gizliliği onaylarsa uygulama bilgileri Uç Nokta için Defender konsoluna gönderilir.

        :::image type="content" source="images/tvm-user-privacy.png" alt-text="TVM Gizliliği" lightbox="images/tvm-user-privacy.png":::

İstemci sürümleri hedef iOS cihazlarına dağıtıldıktan sonra işlem başlatılır. Bu cihazlarda bulunan güvenlik açıkları Defender Güvenlik Açığı Yönetimi panosunda gösterilmeye başlar. İşlemin tamamlanması birkaç saat (en fazla 24 saat) sürebilir. Özellikle tüm uygulama listesinin yazılım envanterinde gösterilmesi için.

## <a name="configure-option-to-send-in-app-feedback"></a>Uygulama içi geri bildirim gönderme seçeneğini yapılandırma

Müşteriler artık Uç Nokta için Defender uygulamasında Microsoft'a geri bildirim verileri gönderme özelliğini yapılandırma seçeneğine sahiptir. Geri bildirim verileri, Microsoft'un ürünleri geliştirmelerine ve sorunları gidermelerine yardımcı olur.

> [!NOTE]
> ABD Kamu bulut müşterileri için geri bildirim veri toplama varsayılan olarak **devre dışıdır** .

Microsoft'a geri bildirim verileri gönderme seçeneğini yapılandırmak için aşağıdaki adımları kullanın:

1. [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Uygulamalar Uygulama** > **yapılandırma ilkeleri** > **Yönetilen cihazlar** **ekle'ye** >  gidin.

1. İlkeye **iOS/iPadOS > Platform** adını verin, profil türünü seçin.

1. Hedef uygulama olarak **Uç Nokta için Microsoft Defender'ı** seçin.

1. Ayarlar sayfasında **Yapılandırma tasarımcısını kullan'ı** seçin ve anahtar ve değer türü olarak **DefenderSendFeedback** değerini **Boole olarak** ekleyin.

   - Son kullanıcıların geri bildirim sağlama becerisini kaldırmak için değeri olarak `false` ayarlayın ve bu ilkeyi kullanıcılara atayın. Varsayılan olarak, bu değer olarak `true`ayarlanır. US Government müşterileri için varsayılan değer 'false' olarak ayarlanır.

   - anahtar kümesi olan `true`kullanıcılar için, uygulama içinde Microsoft'a Geri Bildirim verileri gönderme seçeneği vardır (Menü > Geri Bildirim & Yardım > Microsoft'a Geri Bildirim Gönder)

1. **İleri'ye** tıklayın ve bu profili hedeflenen cihazlara/kullanıcılara atayın.

## <a name="report-unsafe-site"></a>Güvenli olmayan siteyi bildir

Kimlik avı web siteleri, kişisel veya finansal bilgilerinizi almak amacıyla güvenilir web sitelerini taklit ediyor. Kimlik avı sitesi olabilecek bir web sitesini bildirmek istiyorsanız [Ağ koruması hakkında geri bildirim sağlayın](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) sayfasını ziyaret edin.
