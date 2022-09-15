---
title: api sürüm notlarını Uç Nokta için Microsoft Defender
description: Uç Nokta için Microsoft Defender API kümesinde yapılan güncelleştirmeler için sürüm notları.
keywords: Uç Nokta için Microsoft Defender API sürüm notları, mde, API'ler, Uç Nokta için Microsoft Defender API'leri, güncelleştirmeler, notlar, sürüm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 50eee5a10311e08a706c8cc412c4a01e95ffad57
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698473"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>api sürüm notlarını Uç Nokta için Microsoft Defender

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Aşağıdaki bilgiler, Uç Nokta için Microsoft Defender API'lerinde yapılan güncelleştirmeleri ve bunların yapıldığı tarihleri listeler.

> [!TIP]
> RSS akışı: Aşağıdaki URL'yi kopyalayıp akış okuyucunuza yapıştırarak bu sayfa güncelleştirildiğinde bildirim alın:
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Sürüm notları - en yeniden en eskiye (dd.mm.yyyy)

### <a name="08082022"></a>08.08.2022

- Yeni Cihaz Durumunu Dışarı Aktarma API yöntemi eklendi - GET /api/public/avdeviceshealth [Cihaz sistem durumunu dışarı aktarma yöntemleri ve özellikleri](device-health-api-methods-properties.md)

### <a name="06102021"></a>06.10.2021

- Yeni Dışarı aktarma değerlendirmesi API yöntemi eklendi - _Delta Export yazılım güvenlik açıkları değerlendirmesi (JSON yanıtı)_ [Cihaz başına dışarı aktarma değerlendirme yöntemleri ve özellikleri](get-assessment-methods-properties.md).

### <a name="05252021"></a>05.25.2021

- [Cihaz başına yeni API Dışarı Aktarma değerlendirme yöntemleri ve özellikleri](get-assessment-methods-properties.md) eklendi.

### <a name="03052021"></a>03.05.2021

- Yeni API eklendi: [Düzeltme etkinliği yöntemleri ve özellikleri](get-remediation-methods-properties.md).

### <a name="10022021"></a>10.02.2021

- Yeni API eklendi: [Toplu güncelleştirme uyarıları](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- [Gelişmiş Tehdit Avcılığı API'sine](run-advanced-query-api.md) yönelik hız sınırlamaları dakikada 15 ile 45 istek olarak güncelleştirildi.

### <a name="21012021"></a>21.01.2021

- Yeni API eklendi: [Cihazları etikete göre bulma](machine-tags.md).
- Yeni API eklendi: [Göstergeleri İçeri Aktar](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Uyarı kanıtı güncelleştirildi: ***detectionStatus** _, _*_parentProcessFilePath_*_ ve _ *_parentProcessFileName_** özellikleri eklendi.
- [Uyarı varlığı](alerts.md) güncelleştirildi: ***detectorId*** özelliği eklendi.

### <a name="15122020"></a>15.12.2020

- [Cihaz](machine.md) varlığı güncelleştirildi: ***IpInterfaces*** listesi eklendi. Bkz [. Cihazları listeleme](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Yeni API eklendi: [Cihaz değerini ayarlayın](set-device-value.md).
- [Cihaz](machine.md) varlığı güncelleştirildi: ***deviceValue*** özelliği eklendi.

### <a name="01092020"></a>01.09.2020

- Uyarı varlığını ilgili Kanıt ile genişletme seçeneği eklendi. Bkz. [Uyarıları Listeleme](get-alerts.md).
