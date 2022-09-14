---
title: Microsoft 365 Defender'da VPN tümleştirmesi Kimlik için Microsoft Defender
description: Kimlik için Microsoft Defender için VPN'i Microsoft 365 Defender ile tümleştirerek muhasebe bilgilerini toplamayı öğrenin
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 02a0ecf0dea5b4e3fc820280a389c30b79b5fb43
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682293"
---
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Microsoft 365 Defender'de Kimlik için Defender VPN tümleştirmesi

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede vpn'i [Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) ile tümleştirme açıklanmaktadır[](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
><a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

[!INCLUDE [Product long](includes/product-long.md)] VPN çözümlerinden muhasebe bilgilerini toplayabilir. Yapılandırıldığında, kullanıcının profil sayfası VPN bağlantılarından ip adresleri ve bağlantıların kaynaklandığı konumlar gibi bilgileri içerir. Bu, kullanıcı etkinliği hakkında ek bilgiler ve anormal VPN bağlantıları için yeni bir algılama sağlayarak araştırma sürecini tamamlar. Dış IP adresini bir konuma çözümleme çağrısı anonimdir. Bu çağrıda hiçbir kişisel tanımlayıcı gönderilmez.

[!INCLUDE [Product short](includes/product-short.md)] algılayıcılara iletilen [!INCLUDE [Product short](includes/product-short.md)] RADIUS muhasebe olaylarını dinleyerek VPN çözümünüzle tümleşir. Bu mekanizma standart RADIUS Accounting'i ([RFC 2866](https://tools.ietf.org/html/rfc2866)) temel alır ve aşağıdaki VPN satıcıları desteklenir:

- Microsoft
- F5
- Check Point
- Cisco ASA

## <a name="prerequisites"></a>Önkoşullar

VPN tümleştirmesini etkinleştirmek için aşağıdaki parametreleri ayarladığınızdan emin olun:

- Algılayıcılarınızda ve/veya [!INCLUDE [Product short](includes/product-short.md)] tek başına algılayıcılarınızda [!INCLUDE [Product short](includes/product-short.md)] UDP 1813 bağlantı noktasını açın.

> [!NOTE]
>
> - Algılayıcı, [!INCLUDE [Product short](includes/product-short.md)] **Radius Accounting'i** etkinleştirerek UDP 1813 numaralı bağlantı noktasında gelen RADIUS Accounting'e izin vermek için Algılayıcı adlı **[!INCLUDE [Product long](includes/product-long.md)]** önceden sağlanan bir Windows güvenlik duvarı ilkesini etkinleştirir.
> - VPN tümleştirmesi, Federal Bilgi İşleme Standartlarına (FIPS) bağlı ortamlarda desteklenmez

Aşağıdaki örnekte VPN yapılandırma işlemini açıklamak için Microsoft Yönlendirme ve Uzaktan Erişim Sunucusu (RRAS) gerçekleştirilir.

Üçüncü taraf VPN çözümü kullanıyorsanız RADIUS Accounting'i etkinleştirme yönergeleri için onların belgelerine bakın.

## <a name="configure-radius-accounting-on-the-vpn-system"></a>VPN sisteminde RADIUS Accounting'i yapılandırma

RRAS sunucunuzda aşağıdaki adımları gerçekleştirin.

1. **Yönlendirme ve Uzaktan Erişim** konsolunu açın.
1. Sunucu adına sağ tıklayın ve **Özellikler'i** seçin.
1. **Güvenlik** sekmesindeki **Muhasebe sağlayıcısı'nın** altında **RADIUS Accounting'i** ve **ardından Yapılandır'ı** seçin.

   :::image type="content" source="../../media/defender-identity/radius-setup.png" alt-text="RADIUS kurulumu" lightbox="../../media/defender-identity/radius-setup.png":::

1. **RADIUS Sunucusu Ekle** penceresinde, en [!INCLUDE [Product short](includes/product-short.md)] yakın algılayıcının (ağ bağlantısı olan) **Sunucu adını** yazın. Yüksek kullanılabilirlik için RADIUS Sunucuları olarak ek [!INCLUDE [Product short](includes/product-short.md)] algılayıcılar ekleyebilirsiniz. **Bağlantı noktası'nın** altında varsayılan 1813'ün yapılandırıldığından emin olun. **Değiştir'i** seçin ve alfasayısal karakterlerden oluşan yeni bir paylaşılan gizli dizi yazın. Yeni paylaşılan gizli dizi dizesini not alın çünkü daha sonra Yapılandırma sırasında [!INCLUDE [Product short](includes/product-short.md)] doldurmanız gerekir. **RADIUS Hesabı Açık ve Hesap Dışı İletileri Gönder** kutusunu işaretleyin ve tüm açık iletişim kutularında **Tamam'ı** seçin.

   :::image type="content" source="../../media/defender-identity/vpn-set-accounting.png" alt-text="VPN kurulumu" lightbox="../../media/defender-identity/vpn-set-accounting.png":::

## <a name="configure-vpn-in-defender-for-identity"></a>Kimlik için Defender'da VPN yapılandırma

[!INCLUDE [Product short](includes/product-short.md)] bilgisayarların ağa bağlandığı konumların profilinin alınmasına ve şüpheli VPN bağlantılarının algılanabilmesine yardımcı olan VPN verilerini toplar.

Microsoft 365 Defender'de [!INCLUDE [Product short](includes/product-short.md)] VPN verilerini yapılandırmak için:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ayarlar menü öğesinin altındaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

1. **VPN'i** seçin.
1. **Yarıçap hesaplamasını etkinleştir'i** seçin ve RRAS VPN Sunucunuzda daha önce yapılandırdığınız **Paylaşılan Gizli Dizi'yi** yazın. Ardından **Kaydet'i** seçin.

   :::image type="content" source="../../media/defender-identity/vpn-integration.png" alt-text="VPN tümleştirmesi" lightbox="../../media/defender-identity/vpn-integration.png":::

Bu etkinleştirildikten sonra, tüm Kimlik için Defender algılayıcıları RADIUS muhasebe olayları için 1813 numaralı bağlantı noktasını dinler ve VPN kurulumunuz tamamlanır.

Kimlik için Defender algılayıcısı VPN olaylarını aldıktan ve bunları işlemek üzere Kimlik için Defender bulut hizmetine gönderdikten sonra varlık profili, farklı erişimli VPN konumlarını ve profildeki etkinliklerin konumları göstereceğini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 Defender'da uyarıları araştırma](../defender/investigate-alerts.md)
