---
title: Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu
description: Cihaz durumu algılamalarını, virüsten koruma durumunu, işletim sistemi platformunu ve Windows 10 durumu ve uyumluluk raporunu kullanarak farklı sürümleri izleme
keywords: health state, antivirus, os platform, windows 10 version, version, health, compliance, state
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
ms.openlocfilehash: eaa9d05fd62127949e6a0b40de8d42a79c446d4d
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2021
ms.locfileid: "62996992"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'da cihaz durumu ve uyumluluk raporu

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aşağıdakiler için geçerlidir:**
- [Uç Nokta Planı 2 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Uç Nokta için Microsoft Defender'ı mı deneyimliysiniz? [Ücretsiz deneme için kaydol'](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cihaz durumu raporu, kurum cihazları hakkında üst düzey bilgiler sağlar. Rapor, algılayıcıların durumu, virüsten koruma durumu, işletim sistemi platformları ve 11. Windows 10 sürümlerini Windows popüler bilgileri içerir.

Pano iki bölüm halinde yapılandırılmıştır:

:::image type="content" alt-text="Cihaz raporunun resmi." source="images/device-reports.png" lightbox="images/device-reports.png":::


<br>

****

|Bölüm|Açıklama|
|---|---|
|1|Cihaz eğilimleri|
|2|Cihaz özeti (geçerli gün)|
|||

## <a name="device-trends"></a>Cihaz eğilimleri

Varsayılan olarak, cihaz eğilimleri cihaz bilgilerini 30 gün içinde son tam gün içinde sona eriyor. Kuruluşta oluşan eğilimlere daha iyi bir bakış açısı elde etmek için gösterilen zaman dönemini ayarlayarak raporlama dönemine ince ayarlarabilirsiniz. Zaman aralığını ayarlamak için, açılan liste seçeneklerinden bir zaman aralığı seçin:

- 30 gün
- Üç ay
- Altı ay
- Özel

> [!NOTE]
> Bu filtreler yalnızca cihaz eğilimleri bölümüne uygulanır. Cihaz özeti bölümünü etkilemez.

## <a name="device-summary"></a>Cihaz özeti

Cihaz eğilimleri popüler cihaz bilgilerini gösterirken, cihaz özeti geçerli güne göre cihaz bilgilerini gösterir.

> [!NOTE]
> Özet bölümüne yansıtilen veriler, geçerli tarihten 180 gün önce kapsamdadır. Örneğin, bugünün tarihi 27 Mart 2019 ise, özet bölümündeki veriler 28 Eylül 2018'den 27 Mart 2019'a kadar olan sayıları yansıtacak.
>
> Eğilimler bölümüne uygulanan filtre özet bölümüne uygulanmaz.

Cihaz eğilimleri bölümü, ilgili filtrenin uygulandığı cihazlar listesinde detaya gitmelerini sağlar. Örneğin, Algılayıcı durumu kartında Etkin Değil çubuğuna tıklamak, size yalnızca algılayıcı durumu etkin olmayan cihazların sonuçlarının yer alan cihazlar listesini getirir.

## <a name="device-attributes"></a>Cihaz öznitelikleri

Rapor, aşağıdaki cihaz özniteliklerini görüntüleyen kartlardan yapılır:

- **Sağlık durumu**: Cihazlar üzerinde algılayıcı durumu hakkında bilgi gösterir, etkin olan, engelli iletişimlere, etkin olmayan cihazlara ya da algılayıcı verilerini gören cihazların toplu bir görünümünü sağlar.
- **Etkin cihaz sayısı ve Windows 10 virüsten** koruma durumu: Cihaz sayısını ve cihaz Microsoft Defender Virüsten Koruma.
- **işletim sistemi platformları**: Kuruluş içinde var olan işletim sistemi platformlarının dağıtımını gösterir.
- **Windows 10:** Diğer cihazların ve Windows 10 sürümlerinin dağılımını gösterir.

## <a name="filter-data"></a>Verilere filtre uygulama

Belirli özniteliklere sahip cihazları eklemek veya dışarıda tutmak için sağlanan filtreleri kullanın.

Cihaz özniteliklerinden uygulamak için birden çok filtre seçebilirsiniz.

> [!NOTE]
> Bu filtreler **rapora** tüm kartlar için uygulanır.

Örneğin, Etkin algılayıcı durumuna sahip Windows 10 cihazlarla ilgili verileri göstermek için:

1. Filtreler **altında > Algılayıcı durumu durumu > etkindir**.
2. Ardından işletim **sistemi platformları ve > Windows 10**.
3. **Uygula'ya seçin**.

## <a name="related-topic"></a>İlgili konu

- [Tehdit koruması raporu](threat-protection-reports.md)