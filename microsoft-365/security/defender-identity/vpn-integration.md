---
title: Microsoft 365 Defender'da Identity VPN tümleştirmesi için Microsoft Defender
description: Microsoft Defender for Identity için VPN'i farklı bir ağ bağlantılarında tümleştirerek finansal bilgileri Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.openlocfilehash: 9f542d2b5a25a8274d74e0ee3dbfc40fdc119926
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2021
ms.locfileid: "63005009"
---
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Microsoft 365 Defender'te Identity VPN tümleştirmesi için Defender

**Aşağıdakiler için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Defender

Bu makalede, aynı e-postada Identity için [Microsoft Defender](/defender-for-identity) ile [VPN'Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Sonuçların yakınmasının bir <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">parçası Microsoft 365 Defender</a>, kimlik için Defender portalında yer alan konumlarından bazı seçenekler ve ayrıntılar değiştirilmiştir. Hem tanıdık hem de yeni özellikleri nerede bulamıyorum? bulmak için lütfen aşağıdaki ayrıntıları okuyun.

[!INCLUDE [Product long](includes/product-long.md)] VPN çözümlerinden finansal bilgileri toplayabilirsiniz. Yapılandırıldığında, kullanıcının profil sayfasında VPN bağlantılarından alınan IP adresleri ve bağlantıların kaynaklandığı konumlar gibi bilgiler yer almaktadır. Bu, hem kullanıcı etkinliği hakkında ek bilgi hem de olağandışı VPN bağlantıları için yeni bir algılama sağlayarak araştırma sürecini tamamlar. Dış IP adresini bir konuma çözümleme çağrısı anonimdir. Bu aramada hiçbir kişisel tanımlayıcı gönderilmez.

[!INCLUDE [Product short](includes/product-short.md)] VPN çözümünüzle tümleştirerek algılayıcılara iletili YARıÇAP muhasebe olaylarını dinleyerek [!INCLUDE [Product short](includes/product-short.md)] tümleşiktir. Bu mekanizma standart YARıÇAP Finansal ([RFC 2866](https://tools.ietf.org/html/rfc2866)) tabanlıdır ve aşağıdaki VPN satıcıları desteklemektedir:

- Microsoft
- F5
- Onay Noktası
- Cisco ASA

## <a name="prerequisites"></a>Önkoşullar

VPN tümleştirmeyi etkinleştirmek için aşağıdaki parametreleri ayar mutlaka ayarlayın:

- Algılayıcılar ve/veya tek başına algılayıcılar [!INCLUDE [Product short](includes/product-short.md)] üzerinde bağlantı noktası [!INCLUDE [Product short](includes/product-short.md)] UDP 1813'ü açın.

> [!NOTE]
>
> - Yarıçap **Finansal'ı** etkinleştirerek, [!INCLUDE [Product short](includes/product-short.md)] **[!INCLUDE [Product long](includes/product-long.md)]** algılayıcı UDP 1813'te gelen RADIUS Accounting'e izin vermek için Algılayıcı olarak adlandırılan önceden Windows güvenlik duvarı ilkesi etkinleştirir.
> - FEDERAL Bilgi İşleme Standartlarına (FIPS) bağlı ortamlarda VPN tümleştirmesi desteklenmiyor

Aşağıdaki örnekte VPN yapılandırma işlemini açıklamak için Microsoft Yönlendirme ve Uzak Erişim Sunucusu (RRAS) kullanılır.

Üçüncü taraf bir VPN çözümü kullanıyorsanız, YARıÇAP Finansal'ı etkinleştirme yönergeleri için onların belgelerine bakın.

## <a name="configure-radius-accounting-on-the-vpn-system"></a>VPN sisteminde RADIUS Accounting'i yapılandırma

RRAS sunucunuzda aşağıdaki adımları gerçekleştirin.

1. Yönlendirme ve **Uzaktan Erişim konsolu'nu** açın.
1. Sunucu adına sağ tıklayın ve Özellikler'i **seçin**.
1. Güvenlik **sekmesindeki Finansal** sağlayıcı'nın **altında YARıÇAP** **Finansal'ı seçin ve ardından** **Yapılandır'ı seçin**.

    ![YARıÇAP kurulumu.](../../media/defender-identity/radius-setup.png)

1. YARıÇAP Sunucusu **Ekle penceresinde** , en yakın **algılayıcının** (ağ bağlantısı olan [!INCLUDE [Product short](includes/product-short.md)] ) Sunucu adını yazın. Yüksek kullanılabilirlik için YARıÇAP Sunucuları olarak ek [!INCLUDE [Product short](includes/product-short.md)] algılayıcılar eklemeniz gerekir. Bağlantı **Noktası altında**, varsayılan 1813'in yapılandırılmış olduğundan emin olun. **Değiştir'i** seçin ve yeni bir alfasayısal karakter paylaşılan gizli dize yazın. Yeni paylaşılan gizli dizeyi, daha sonra Yapılandırma sırasında doldurmanız gerekeceğimiz şekilde not [!INCLUDE [Product short](includes/product-short.md)] alır. YARıÇAP Hesabını **Gönder Açık ve Finansal Kapalı iletilerini işaretleyin ve** tüm **açık iletişim** kutularında Tamam'ı seçin.

    ![VPN kurulumu'nı seçin.](../../media/defender-identity/vpn-set-accounting.png)

## <a name="configure-vpn-in-defender-for-identity"></a>Kimlik için Defender'da VPN'yi yapılandırma

[!INCLUDE [Product short](includes/product-short.md)] bilgisayarların ağa bağlanarak şüpheli VPN bağlantılarını algılayabilecek konumların profillerini oluşturmalarına yardımcı olan VPN verilerini toplar.

VPN verilerini aynı Microsoft 365 Defender[!INCLUDE [Product short](includes/product-short.md)]:

1. Daha <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, Kimlikler'Ayarlar'e **gidin**.

    ![Kimlikler'Ayarlar ardından Kimlikler'e gidin.](../../media/defender-identity/settings-identities.png)

1. **VPN'yi seçin**.
1. Yarıçap **muhasebeini etkinleştir'i** seçin ve daha **önce** RRAS VPN Sunucunuzda yapılandırmış olduğunuz Paylaşılan Gizli'yi yazın. Ardından **Kaydet'i seçin**.

    ![VPN tümleştirmesi.](../../media/defender-identity/vpn-integration.png)

Bu etkinleştirildikten sonra tüm Identity algılayıcıları için Defender algılayıcıları YARıÇAP finansal olayları için 1813 bağlantı noktasını dinler ve VPN kurulumunuz tamamlanır.

Kimlik için Defender algılayıcısı VPN olaylarını aldığında ve bunları işleme için Identity bulut hizmeti için Defender'a gönderdikten sonra, varlık profili ayrı erişilen VPN konumlarını ve profilde bulunan etkinliklerin konumları belirtecek.

## <a name="see-also"></a>Ayrıca bkz.

- [E-postada uyarıları Microsoft 365 Defender](../defender/investigate-alerts.md)