---
title: Microsoft 365 Defender'da algılayıcı durumunu ve ayarlarını Kimlik için Microsoft Defender
description: Kimlik için Microsoft Defender algılayıcılarını yapılandırmayı ve bunların sistem durumunu Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: d06e01582e4d6912f683921f31becdfe74255907
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682359"
---
# <a name="microsoft-defender-for-identity-sensor-health-and-settings-in-microsoft-365-defender"></a>Microsoft 365 Defender'da algılayıcı durumunu ve ayarlarını Kimlik için Microsoft Defender

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede, [Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) algılayıcılarını yapılandırma ve izleme açıklanmaktadır[.](/microsoft-365/security/defender/overview-security-center)

>[!IMPORTANT]
>Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

## <a name="view-defender-for-identity-sensor-settings-and-status"></a>Kimlik için Defender algılayıcı ayarlarını ve durumunu görüntüleme

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ayarlar sayfasında Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

1. Tüm Kimlik için Defender algılayıcılarınızın görüntülendiği **Algılayıcılar** sayfasını seçin. Her algılayıcı için adını, etki alanı üyeliğini, sürüm numarasını, güncelleştirmelerin geciktirilmesi gerekiyorsa hizmet durumunu, güncelleştirme durumunu, sistem durumunu, sistem durumu sorunlarını ve algılayıcının ne zaman oluşturulduğunu görürsünüz.

    [![Algılayıcı sayfası.](../../media/defender-identity/sensor-page.png)](../../media/defender-identity/sensor-page.png#lightbox)

    >[!NOTE]
    >Kimlik için Defender portalında algılayıcı ayarları ve sistem durumu bilgileri ayrı konumlardaydı. Microsoft 365 Defender artık aynı sayfada olduklarını unutmayın.

1. **Filtreler'i** seçerseniz hangi filtrelerin kullanılabilir olacağını seçebilirsiniz. Ardından her filtreyle hangi algılayıcıların görüntüleneceğini seçebilirsiniz.

    [![Algılayıcı filtreleri.](../../media/defender-identity/sensor-filters.png)](../../media/defender-identity/sensor-filters.png#lightbox)

    :::image type="content" source="../../media/defender-identity/filtered-sensor.png" alt-text="Filtrelenmiş algılayıcı" lightbox="../../media/defender-identity/filtered-sensor.png":::

1. Algılayıcılardan birini seçerseniz algılayıcı ve sistem durumu hakkında bilgi içeren bir bölme görüntülenir.

    [![Algılayıcı ayrıntıları.](../../media/defender-identity/sensor-details.png)](../../media/defender-identity/sensor-details.png#lightbox)

1. Sistem durumu sorunlarından herhangi birini seçerseniz, bunlar hakkında daha fazla ayrıntı içeren bir bölme alırsınız. Kapalı bir sorun seçerseniz, buradan yeniden açabilirsiniz.

   :::image type="content" source="../../media/defender-identity/issue-details.png" alt-text="Sorun ayrıntıları" lightbox="../../media/defender-identity/issue-details.png":::
    

1. **Algılayıcıyı yönet'i** seçerseniz algılayıcı ayrıntılarını yapılandırabileceğiniz bir bölme açılır.

   :::image type="content" source="../../media/defender-identity/manage-sensor.png" alt-text="Algılayıcıyı yönet seçeneği" lightbox="../../media/defender-identity/manage-sensor.png":::

   :::image type="content" source="../../media/defender-identity/configure-sensor-details.png" alt-text="Algılayıcı ayarlarını yapılandırdığınız sayfa" lightbox="../../media/defender-identity/configure-sensor-details.png":::

1. **Algılayıcılar** sayfasında, **Dışarı Aktar'ı** seçerek algılayıcı listenizi bir .csv dosyasına aktarabilirsiniz.

   :::image type="content" source="../../media/defender-identity/export-sensors.png" alt-text="Algılayıcıların dışarı aktarma listesi" lightbox="../../media/defender-identity/export-sensors.png":::

## <a name="add-a-sensor"></a>Algılayıcı ekleme

**Algılayıcılar** sayfasından yeni bir algılayıcı ekleyebilirsiniz.

1. **Algılayıcı ekle'yi** seçin.

   :::image type="content" source="../../media/defender-identity/add-sensor.png" alt-text="Algılayıcı ekle seçeneği" lightbox="../../media/defender-identity/add-sensor.png":::

1. Algılayıcı yükleyicisini ve oluşturulan erişim anahtarını indirmek için size bir düğme sağlayan bir bölme açılır.

   :::image type="content" source="../../media/defender-identity/installer-access-key.png" alt-text="Yükleyiciyi indirme ve anahtarı yeniden oluşturma seçenekleri" lightbox="../../media/defender-identity/installer-access-key.png":::

1. Paketi yerel olarak kaydetmek için **Yükleyiciyi indir'i** seçin. Zip dosyası aşağıdaki dosyaları içerir:

    - Kimlik için Defender algılayıcı yükleyicisi

    - Kimlik için Defender bulut hizmetine bağlanmak için gerekli bilgileri içeren yapılandırma ayarı dosyası

1. **Erişim anahtarını** kopyalayın. Kimlik için Defender algılayıcısının Kimlik için Defender örneğine bağlanması için erişim anahtarı gereklidir. Erişim anahtarı, algılayıcı dağıtımı için tek seferlik bir paroladır ve bundan sonra tüm iletişim kimlik doğrulaması ve TLS şifrelemesi için sertifikalar kullanılarak gerçekleştirilir. Yeni erişim **anahtarını yeniden oluşturmanız** gerekirse Yeniden oluştur tuşunu kullanın. Daha önce dağıtılan algılayıcıları etkilemez çünkü yalnızca algılayıcının ilk kaydı için kullanılır.

1. Paketi, Kimlik için Defender algılayıcısını yüklediğiniz ayrılmış sunucuya veya etki alanı denetleyicisine kopyalayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Kimlik için Defender güvenlik uyarılarını yönetme](manage-security-alerts.md)
