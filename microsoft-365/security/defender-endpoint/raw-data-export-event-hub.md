---
title: Uç Nokta için Microsoft Defender olaylarını Azure Event Hubs akışla aktar
description: Gelişmiş Tehdit Avcılığı olaylarını Olay Hub'ınıza akışla aktarmaya Uç Nokta için Microsoft Defender yapılandırmayı öğrenin.
keywords: ham veri dışarı aktarma, akış API'si, API, Azure Event Hubs, Azure depolama, depolama hesabı, Gelişmiş Tehdit Avcılığı, ham veri paylaşımı
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: bf0c8d2a09d9dfc91e49351dce1f60ba10680787
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68632678"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Gelişmiş Tehdit Avcılığı olaylarını Azure Event Hubs akışı yapmak için Uç Nokta için Microsoft Defender yapılandırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="before-you-begin"></a>Başlamadan önce

1. Kiracınızda bir [olay hub'ı](/azure/event-hubs/) oluşturun.

2. [Azure kiracınızda](https://ms.portal.azure.com/) oturum açın, **Aboneliğiniz > Kaynak Sağlayıcılarınız > Abonelikler'e gidin > Microsoft.insights'a kaydolun**.

## <a name="enable-raw-data-streaming"></a>Ham veri akışını etkinleştirme

1. [Microsoft 365 Defender](https://security.microsoft.com) ***Genel Yönetici** _ veya _*_Güvenlik Yöneticisi_** olarak oturum açın.

2. Microsoft Defender portalında [Veri dışarı aktarma ayarları sayfasına](https://security.microsoft.com/interoperability/dataexport) gidin.

3. **Veri dışarı aktarma ayarları ekle'ye** tıklayın.

4. Yeni ayarlarınız için bir ad seçin.

5. **Olayları Azure Event Hubs ilet'i** seçin.

6. **Event Hubs adınızı** ve **Event Hubs kaynak kimliğinizi** yazın.

   **Event Hubs kaynak kimliğinizi** almak için [Azure](https://ms.portal.azure.com/) > özellikler sekmesindeki \> Azure Event Hubs ad alanı sayfanıza gidin ve **Kaynak Kimliği** altındaki metni kopyalayın:

   :::image type="content" source="images/event-hub-resource-id.png" alt-text="Event Hubs kaynağı Kimliği-1" lightbox="images/event-hub-resource-id.png":::

7. Akış yapmak istediğiniz olayları seçin ve **Kaydet'e** tıklayın.

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>Azure Event Hubs'deki olayların şeması

```json
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Azure Event Hubs'deki her olay hub'ı iletisi kayıtların listesini içerir.

- Her kayıt olay adını, Uç Nokta için Microsoft Defender olayı aldığı zamanı, ait olduğu kiracıyı (yalnızca kiracınızdan olayları alırsınız) ve JSON biçimindeki olayı "**properties**" adlı bir özellikte içerir.

- Uç Nokta için Microsoft Defender olaylarının şeması hakkında daha fazla bilgi için bkz. [Gelişmiş Avcılık'a genel bakış](advanced-hunting-overview.md).

- Gelişmiş Avcılık'ta **DeviceInfo** tablosunda, cihazın grubunu içeren **MachineGroup** adlı bir sütun bulunur. Burada her etkinlik bu sütunla da donatılacaktır. Daha fazla bilgi için bkz [. Cihaz Grupları](machine-groups.md) .
    > [!NOTE]
    > Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

## <a name="data-types-mapping"></a>Veri türleri eşlemesi

Olay özelliklerinin veri türlerini almak için aşağıdakileri yapın:

1. [Microsoft 365 Defender](https://security.microsoft.com) oturum açın ve [Gelişmiş Tehdit Avcılığı sayfasına](https://security.microsoft.com/hunting-package) gidin.

2. Her olay için veri türleri eşlemesini almak için aşağıdaki sorguyu çalıştırın:

   ```kusto
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Cihaz Bilgileri olayına bir örnek aşağıda verilmiştir:

  :::image type="content" source="images/machine-info-datatype-example.png" alt-text="Event Hubs kaynağı Kimliği-2" lightbox="images/machine-info-datatype-example.png":::

## <a name="related-topics"></a>İlgili konular

- [Gelişmiş Avcılık'a Genel Bakış](advanced-hunting-overview.md)
- [akış API'sini Uç Nokta için Microsoft Defender](raw-data-export.md)
- [Azure depolama hesabınıza Uç Nokta için Microsoft Defender olayları akışla aktarma](raw-data-export-storage.md)
- [Azure Event Hubs belgeleri](/azure/event-hubs/)
- [Bağlantı sorunlarını giderme - Azure Event Hubs](/azure/event-hubs/troubleshooting-guide)
