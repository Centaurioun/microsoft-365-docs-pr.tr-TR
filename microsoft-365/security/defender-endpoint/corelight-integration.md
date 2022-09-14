---
title: Uç Nokta için Microsoft Defender'de Corelight tümleştirmesini etkinleştirme
description: Ağın MDE'nin dağıtılmadığı alanlarda IoT/OT cihazlarına odaklanan görünürlük elde etmek için Corelight tümleştirmesini etkinleştirin
keywords: siem bağlayıcısını, siem'i, bağlayıcıyı, güvenlik bilgilerini ve olayları etkinleştirme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 5e558b5488c0311d398b626321e2d1fa32d3f130
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67678591"
---
# <a name="enable-corelight-data-integration"></a>Corelight veri tümleştirmesini etkinleştirin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Microsoft, kuruluşunuz genelinde IoT/OT cihazlarını keşfetmenize yardımcı olmak için sektörün önde gelen açık ağ algılama ve yanıt (NDR) platformunun sağlayıcısı [Corelight](https://corelight.com/integrations/iot-security) ile iş ortaklığı yaptı. Corelight ağ gereçlerinden gönderilen verilerin kullanılması Microsoft 365 Defender, yönetilmeyen diğer cihazlarla veya dış ağlarla iletişim de dahil olmak üzere yönetilmeyen cihazların ağ etkinliklerine daha fazla görünürlük sağlar.

Bu veri kaynağı etkinleştirildiğinde Corelight ağ gereçlerinden gelen tüm olaylar Microsoft 365 Defender gönderilir. Bu etkinlikleri, Uç Nokta için Microsoft Defender cihaz envanterinde bulunan yönetilmeyen cihazlar zaman çizelgesinde görüntüleyebilirsiniz. Daha fazla bilgi için bkz [. Cihaz bulma](device-discovery.md).

## <a name="prerequisites"></a>Önkoşullar

1. Corelight veri tümleştirmesini ayarlamak için kullanıcının aşağıdaki rollere sahip olması gerekir:
   - Azure Active Directory'de Kiracı Genel Yöneticisi
   - IoT için Microsoft Defender tümleştirmesi için kullanılacak Azure aboneliğinin Güvenlik Yöneticisi
2. Eklenen IoT için Defender planı. Daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender ile IoT için Microsoft Defender'ı ekleme](enable-microsoft-defender-for-iot-integration.md).

## <a name="enabling-the-corelight-integration"></a>Corelight tümleştirmesini etkinleştirme

Corelight tümleştirmesini etkinleştirmek için aşağıdaki adımları uygulamanız gerekir:

[1. Adım: Corelight'ı veri kaynağı olarak açma](#step-1-turn-on-corelight-as-a-data-source)<br>
[2. Adım: Corelight'ın olayları Microsoft 365 Defender göndermesine izin verme](#step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender)<br>
[3. Adım: Corelight gerecinizi Microsoft 365 Defender'a veri gönderecek şekilde yapılandırma](#step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender)

### <a name="step-1-turn-on-corelight-as-a-data-source"></a>1. Adım: Corelight'ı veri kaynağı olarak açma

1. Portalın gezinti bölmesinde [https://security.microsoft.com](https://security.microsoft.com/) **Ayarlar** \> **Cihaz bulma** \> **Veri kaynakları'nı** seçin.

   :::image type="content" source="../../media/defender-endpoint/enable-corelight.png" alt-text="Microsoft 365 Defender portalındaki veri kaynakları sayfası" lightbox="../../media/defender-endpoint/enable-corelight.png":::

2. **Corelight verilerini M365D'ye gönder'i** ve **ardından Kaydet'i** seçin.

### <a name="step-2-provide-permission-for-corelight-to-send-events-to-microsoft-365-defender"></a>2. Adım: Corelight'ın olayları Microsoft 365 Defender göndermesine izin verme

> [!NOTE]
> Corelight'a kuruluşunuzdaki kaynaklara erişim izni vermek için genel yönetici olmanız gerekir.

1. Kiracı Genel Yöneticisi olarak, izin vermek için bu [bağlantıya](<https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=d8be544e-9d1a-4825-a5cb-fb447457f692&response_type=code&sso_reload=true>) gidin.
2. Portala [https://security.microsoft.com](https://security.microsoft.com/) gidin, **Ayarlar** \> **Microsoft 365 Defender'ı** seçin ve **Kiracı Kimliğini** not alın. Corelight gerecinizi yapılandırırken bu bilgilere ihtiyacınız olacaktır.

### <a name="step-3-configure-your-corelight-appliance-to-send-data-to-microsoft-365-defender"></a>3. Adım: Corelight gerecinizi Microsoft 365 Defender'a veri gönderecek şekilde yapılandırma

> [!NOTE]
> Tümleştirme Corelight Algılayıcısı yazılımı v25 ve sonraki sürümlerde kullanılabilir.
> 
> Çözümün çalışması için algılayıcınızın hem Defender hem de Corelight bulut hizmetlerine ulaşması için İnternet bağlantısına ihtiyacınız olacaktır.

#### <a name="enable-the-integration-in-the-corelight-web-interface"></a>Corelight web arabiriminde tümleştirmeyi etkinleştirme

1. Corelight web arabiriminde **Algılayıcı** \> **Dışarı Aktarma'ya** gidin.

   :::image type="content" source="images/exporttodefender.png" alt-text="Kafka dışarı aktarma" lightbox="images/exporttodefender.png":::

2. **Microsoft Defender'a Dışarı Aktarma'yı** etkinleştirin.
3. Microsoft 356 Defender Kiracı Kimliğinizi girin.
4. İsteğe bağlı olarak şunları yapabilirsiniz:
    - **Zeek Günlükleri'ni Dışla olarak** ayarlayın. Eklemeniz gereken en az günlük kümesi şunlardır: dns, conn, files, http, ssl, ssh, x509, snmp, smtp, ftp, sip, dhcp ve notice.
    - **Microsoft Defender Günlük Filtresi** oluşturmayı seçin.
5. **Değişiklikleri Uygula'yı** seçin.

#### <a name="enable-the-integration-in-the-corelight-client"></a>corelight-client'da tümleştirmeyi etkinleştirme

1. corelight-client'da aşağıdaki komutu kullanarak **Microsoft Defender'a Aktar'ı** etkinleştirin:

    ``` command
    corelight-client configuration update \
    --bro.export.defender.enable True
    ```

2. Kiracı kimliğinizi ayarlama

3. İsteğe bağlı olarak, belirli günlükleri dışlamak veya bir Microsoft Defender günlük filtresi oluşturmak için aşağıdaki komutu kullanabilirsiniz. Eklemeniz gereken en az günlük kümesi şunlardır: dns, conn, files, http, ssl, ssh, x509, snmp, smtp, ftp, sip, dhcp ve notice.

   ``` command
     corelight-client configuration update \
    --bro.export.defender.exclude=<logs_to_exclude> \
    --bro.export.defender.filter=<logs_to_filter>
   ```

## <a name="see-also"></a>Ayrıca bkz.

- [Cihaz keşfi hakkında SSS](device-discovery-faq.md)
