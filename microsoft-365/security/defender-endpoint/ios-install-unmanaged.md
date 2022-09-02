---
title: iOS özelliklerinde Uç Nokta için Microsoft Defender dağıtma
description: Uç Nokta için Microsoft Defender kaydedilmemiş iOS cihazlarına nasıl dağıtılacağı açıklanır.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, ios, configure, features, ios
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 14535c5bcf599d292be97d0bdbf2381eed066911
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520939"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>Kaydı kaldırılmış iOS cihazlarda Uç Nokta için Microsoft Defender dağıtma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS'ta Uç Nokta için Defender, Web Koruması özelliğini sağlamak için bir VPN kullanır. Bu normal bir VPN değildir ve cihazın dışına trafiği almayan yerel/kendi kendini döngüye alan bir VPN'dir.

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>Uygulama koruma ilkesinde (MAM) Uç Nokta için Microsoft Defender risk sinyallerini yapılandırma

Mobil Cihaz Yönetimi (MDM) senaryolarında kurumsal kullanıcıları zaten koruyan iOS'ta Uç Nokta için Microsoft Defender, artık Intune mobil cihaz yönetimi (MDM) kullanılarak kaydedilmemiş cihazlar için Mobil Uygulama Yönetimi (MAM) desteğini genişletiyor. Ayrıca bu destek, mobil uygulama yönetimi (MAM) için Intune kullanırken diğer kurumsal mobil yönetim çözümlerini kullanan müşterilere de genişletir. Bu özellik, bir uygulama içindeki kuruluşunuzun verilerini yönetmenize ve korumanıza olanak tanır.

iOS tehdit bilgilerindeki Uç Nokta için Microsoft Defender, bu uygulamaları korumak için Intune Uygulama Koruma İlkeleri tarafından kullanılır. Uygulama koruması ilkeleri (APP), kuruluşun verilerinin güvenli kalmasını veya yönetilen bir uygulamada yer almamasını sağlayan kurallardır. Yönetilen bir uygulamada uygulama koruma ilkeleri uygulanır ve Intune tarafından yönetilebilir.  

iOS'ta Uç Nokta için Microsoft Defender, MAM'ın her iki yapılandırmasını da destekler
- **MDM + MAM Intune**: BT yöneticileri yalnızca Intune mobil cihaz yönetimi (MDM) ile kaydedilen cihazlarda Uygulama Koruma İlkelerini kullanarak uygulamaları yönetebilir.
- **Cihaz kaydı olmadan MAM: Cihaz** kaydı olmayan MAM veya MAM-WE, BT yöneticilerinin Intune MDM'ye kayıtlı olmayan cihazlarda [Uygulama Koruma İlkeleri'ni](/mem/intune/apps/app-protection-policy) kullanarak uygulamaları yönetmesine olanak tanır. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarıyla kaydedilen cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Yukarıdaki yapılandırmaların her ikisinde de kullanarak uygulamaları yönetmek için müşterilerin [Microsoft Endpoint Manager yönetim merkezinde Intune](https://go.microsoft.com/fwlink/?linkid=2109431) kullanması gerekir

Bu özelliği etkinleştirmek için bir yöneticinin Uç Nokta için Microsoft Defender ile Intune arasındaki bağlantıyı yapılandırması, uygulama koruma ilkesini oluşturması ve ilkeyi hedeflenen cihazlara ve uygulamalara uygulaması gerekir. 
 
Son kullanıcıların Uç Nokta için Microsoft Defender cihazlarına yüklemek ve ekleme akışını etkinleştirmek için de adımlar atması gerekir.

### <a name="pre-requisites"></a>Önkoşullar

1. **Bağlayıcının etkinleştirildiğini doğrulayın**. <br> [Birleşik güvenlik konsolunda](https://security.microsoft.com) **Ayarlar** > **Uç Noktaları** > **Gelişmiş Özellikler'e** gidin ve **Microsoft Intune bağlantısının** etkinleştirildiğinden emin olun.

  :::image type="content" source="images/enable-intune-connection.png" alt-text="Uç Nokta için Defender - Intune bağlayıcısı" lightbox="images/enable-intune-connection.png":::

  
2. **Bağlayıcının Intune portalında etkinleştirildiğini doğrulayın**. <br> [Microsoft Endpoint Manager yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) **Endpoint Security** >  **Uç Nokta için Microsoft Defender'ye** gidin ve Bağlantı durumunun etkinleştirildiğinden emin olun.

  :::image type="content" source="images/app-settings.png" alt-text="Uygulama ayarları" lightbox="images/app-settings.png":::

### <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
 
Bir uygulama koruma ilkesi oluşturarak Uç Nokta için Microsoft Defender risk sinyallerine göre yönetilen bir uygulamanın erişimini engelleyin veya verileri silin.
Uç Nokta için Microsoft Defender, uygulama koruma ilkelerinde (MAM olarak da bilinir) kullanılacak tehdit sinyalleri gönderecek şekilde yapılandırılabilir. Bu özellik sayesinde yönetilen uygulamaları korumak için Uç Nokta için Microsoft Defender kullanabilirsiniz.

1. İlke oluşturma <br>
Uygulama koruması ilkeleri (APP), kuruluşun verilerinin güvenli kalmasını veya yönetilen bir uygulamada yer almamasını sağlayan kurallardır. İlke, kullanıcı "şirket" verilerine erişmeye veya verileri taşımaya çalıştığında uygulanan bir kural ya da kullanıcı uygulamanın içindeyken yasaklanan veya izlenen bir dizi eylem olabilir. 

:::image type="content" source="images/create-policy.png" alt-text="Uygulama koruması ilkeleri menü öğesindeki İlke oluştur sekmesi" lightbox="images/create-policy.png":::

2. Uygulama ekleme <br>
    a. Bu ilkeyi farklı cihazlardaki uygulamalara nasıl uygulamak istediğinizi seçin. Ardından en az bir uygulama ekleyin. <br>
    Bu ilkenin yönetilmeyen cihazlar için geçerli olup olmadığını belirtmek için bu seçeneği kullanın. ayrıca, ilkenizi herhangi bir yönetim durumundaki cihazlardaki uygulamalara hedeflemeyi de seçebilirsiniz.
Mobil uygulama yönetimi cihaz yönetimi gerektirmediğinden, şirket verilerini hem yönetilen hem de yönetilmeyen cihazlarda koruyabilirsiniz. Yönetim, cihaz yönetimi gereksinimini ortadan kaldıran kullanıcı kimliğine göre ortalanır. Şirketler, uygulama koruma ilkelerini aynı anda MDM ile veya MDM olmadan kullanabilir. Örneğin, hem şirket tarafından verilen bir telefonu hem de kendi kişisel tabletini kullanan bir çalışanı düşünün. Şirket telefonu MDM'ye kaydedilir ve uygulama koruma ilkeleriyle korunurken, kişisel cihaz yalnızca uygulama koruma ilkeleriyle korunur.

    b. Uygulamalar'ı seçin<br>
    Yönetilen uygulama, uygulama koruma ilkelerinin uygulandığı ve Intune tarafından yönetilebilen bir uygulamadır. [Intune SDK](/mem/intune/developer/app-sdk) ile tümleştirilmiş veya Intune App Wrapping Tool tarafından sarmalanmış tüm uygulamalar Intune uygulama koruma İlkeleri kullanılarak [yönetilebilir.](/mem/intune/developer/apps-prepare-mobile-application-management) Bu araçlar kullanılarak oluşturulmuş ve genel kullanıma açık [Microsoft Intune korumalı uygulamaların](/mem/intune/apps/apps-supported-intune-apps) resmi listesine bakın.

    *Örnek: Yönetilen uygulama olarak Outlook*

     :::image type="content" source="images/managed-app.png" alt-text="Sol gezinti bölmesindeki Microsoft Outlook menü öğesi" lightbox="images/managed-app.png":::
  

 3. Koruma ilkeniz için oturum açma güvenlik gereksinimlerini ayarlayın. <br>
**Cihaz Koşulları'nda** **İzin verilen en yüksek cihaz tehdit düzeyi > Ayar'ı** seçin ve bir değer girin. Ardından  **Eylem: "Erişimi Engelle" seçeneğini** belirleyin. iOS'ta Uç Nokta için Microsoft Defender bu Cihaz Tehdit Düzeyini paylaşır.

    
   :::image type="content" source="images/conditional-launch.png" alt-text="Cihaz koşulları bölmesi" lightbox="images/conditional-launch.png":::

4. İlkenin uygulanması gereken kullanıcı gruplarını atayın.<br>
  **Dahil edilen gruplar'ı** seçin. Ardından ilgili grupları ekleyin. 


MAM veya uygulama koruma ilkesi hakkında daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](/mem/intune/apps/app-protection-policy-settings-ios).

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM için veya kaydı kaldırılmış cihazlarda Uç Nokta için Microsoft Defender dağıtma

iOS'ta Uç Nokta için Microsoft Defender, uygulama koruma ilkesi senaryosuna olanak tanır ve Apple uygulama mağazasında kullanılabilir.

Uygulamalar için uygulama koruma ilkeleri, Uç Nokta için Microsoft Defender cihaz risk sinyallerini içerecek şekilde yapılandırıldığında, kullanıcılar bu tür uygulamaları kullanırken Uç Nokta için Microsoft Defender yükleyecek şekilde yönlendirilir. Alternatif olarak, kullanıcılar uygulamanın en son sürümünü doğrudan Apple uygulama mağazasından da yükleyebilir.
