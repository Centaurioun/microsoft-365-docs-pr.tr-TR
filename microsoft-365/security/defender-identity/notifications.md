---
title: Microsoft 365 Defender bildirimleri Kimlik için Microsoft Defender
description: Microsoft 365 Defender'da Kimlik için Microsoft Defender bildirimleri ayarlamayı öğrenin.
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 7015e87d79a01888a1315de597eecd39263e5d66
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682315"
---
# <a name="defender-for-identity-notifications-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Kimlik için Defender bildirimleri

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede, [Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) bildirimleriyle nasıl çalışılacağını açıklanmaktadır[.](/microsoft-365/security/defender/overview-security-center)

> [!IMPORTANT]
> Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

## <a name="health-issues-notifications"></a>Sistem durumu sorunları bildirimleri

Microsoft 365 Defender'da, Kimlik için Defender'da sistem durumu sorunlarının e-posta bildirimleri için alıcı ekleyebilirsiniz.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

  :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ad sütunundaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::


1. **Sistem durumu sorunları bildirimleri'ni** seçin.

1. Alıcının e-posta adresini girin. **Ekle**'yi seçin.

   :::image type="content" source="../../media/defender-identity/health-email-recipient.png" alt-text="Sistem durumu sorunları bildirimleri alt menüsü öğesi" lightbox="../../media/defender-identity/health-email-recipient.png":::

1. Kimlik için Defender bir sistem durumu sorunu algıladığında, alıcılar ayrıntıları içeren bir e-posta bildirimi alır.

   :::image type="content" source="../../media/defender-identity/health-email.png" alt-text="Sistem durumu sorunu e-postası" lightbox="../../media/defender-identity/health-email.png":::

    > [!NOTE]
    > E-posta, sorunla ilgili diğer ayrıntılar için iki bağlantı sağlar. **MDI Sistem Durumu Merkezi'ne** veya **M365D'deki yeni Sistem Sağlığı Merkezi'ne** gidebilirsiniz.

## <a name="alert-notifications"></a>Uyarı bildirimleri

Microsoft 365 Defender'da, algılanan uyarıların e-posta bildirimleri için alıcı ekleyebilirsiniz.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

1. **Uyarı bildirimleri'ni** seçin.

1. Alıcının e-posta adresini girin. **Ekle**'yi seçin.

   :::image type="content" source="../../media/defender-identity/alert-email-recipient.png" alt-text="Uyarı bildirimleri alt menüsü öğesi" lightbox="../../media/defender-identity/alert-email-recipient.png":::

## <a name="syslog-notifications"></a>Syslog bildirimleri

Kimlik için Defender, syslog sunucunuza belirli bir algılayıcı aracılığıyla güvenlik ve sistem durumu uyarıları göndererek şüpheli etkinlikleri algıladığında sizi bilgilendirebilir.

> [!NOTE]
> Kimlik için Defender'ı Microsoft Sentinel ile tümleştirmeyi öğrenmek için bkz. [Microsoft Sentinel ile tümleştirme Microsoft 365 Defender](/azure/sentinel/microsoft-365-defender-sentinel-integration).

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ad sütunundaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

1. **Syslog bildirimleri'ni** seçin.

1. Syslog bildirimini etkinleştirmek için **Syslog hizmeti** iki durumlu düğmesini **açık** konuma ayarlayın.

   :::image type="content" source="../../media/defender-identity/syslog-service.png" alt-text="Etkinleştirilebilen Syslog hizmeti seçeneği" lightbox="../../media/defender-identity/syslog-service.png":::

1. **Hizmeti yapılandır'ı** seçin. Syslog hizmetinin ayrıntılarını girebileceğiniz bir bölme açılır.

   :::image type="content" source="../../media/defender-identity/syslog-sensor.png" alt-text="Syslog hizmeti ayrıntılarını girdiğiniz sayfa" lightbox="../../media/defender-identity/syslog-sensor.png":::

1. Aşağıdaki ayrıntıları girin:

    - **Algılayıcı** - Açılan listeden uyarıları gönderecek algılayıcıyı seçin.
    - **Hizmet uç noktası** ve **Bağlantı Noktası** - Syslog sunucusu için IP adresini veya tam etki alanı adını (FQDN) girin ve bağlantı noktası numarasını belirtin. Yalnızca bir Syslog uç noktası yapılandırabilirsiniz.
    - **Aktarım** - **Aktarım** protokollerini (TCP veya UDP) seçin.
    - **Biçim** - Biçimi seçin (RFC 3164 veya RFC 5424).

1. **Test SIEM bildirimi gönder'i** seçin ve ardından iletinin Syslog altyapı çözümünüzde alındığını doğrulayın.

1. **Kaydet**'i seçin.

1. **Syslog hizmetini** yapılandırdıktan sonra, Syslog sunucunuza gönderilecek bildirim türlerini (uyarılar veya sistem durumu sorunları) seçebilirsiniz.

   :::image type="content" source="../../media/defender-identity/syslog-configured.png" alt-text="Syslog hizmeti yapılandırıldı seçeneği işaretli" lightbox="../../media/defender-identity/syslog-configured.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Kimlik için Defender güvenlik uyarılarını yönetme](manage-security-alerts.md)
