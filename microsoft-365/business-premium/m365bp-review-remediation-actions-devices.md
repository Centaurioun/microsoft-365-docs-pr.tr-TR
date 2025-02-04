---
title: Microsoft 365 İş Ekstra'de düzeltme eylemlerini gözden geçirme
description: İşlem merkezinde otomatik olarak alınan veya onay bekleyen düzeltmelerin nasıl görüntülendiğini görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: 1ae134f0c6a00fa00d5a5196b9dc20b9419033da
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097961"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>Microsoft 365 İş Ekstra'de düzeltme eylemlerini gözden geçirme

Tamam, bir güvenlik ihlali keşfettiniz ama ne yapacaksınız? Doğasına bağlı.

Karantinaya dosya gönderme, işlemin çalışmasını durdurma veya zamanlanmış bir görevi tamamen kaldırma gibi düzeltme eylemlerine örnek olarak verilebilir. Tüm düzeltme eylemleri, konumunda [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)bulunan İşlem merkezinde izlenir.

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="M365'teki İşlem Merkezi'nin ekran görüntüsü.":::

**Bu makalede şunlar açıklanmaktadır**:

- [İşlem merkezini kullanma](#how-to-use-your-action-center).
- [Düzeltme eylemi türleri](#types-of-remediation-actions).


## <a name="how-to-use-your-action-center"></a>İşlem merkezinizi kullanma

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **İşlem merkezi'ni** seçin.

3. Bekleyen eylemleri görüntülemek ve onaylamak (veya reddetmek) için **Beklemede** sekmesini seçin. Bu tür eylemler virüsten koruma/kötü amaçlı yazılımdan koruma, otomatik araştırma, el ile yanıt etkinlikleri veya canlı yanıt oturumlarından kaynaklanabilir.

4. Tamamlanan eylemlerin listesini görüntülemek için **Geçmiş** sekmesini seçin.

## <a name="types-of-remediation-actions"></a>Düzeltme eylemi türleri

Aboneliğiniz algılanan tehditler için birkaç farklı düzeltme eylemi türü içerir. Bu eylemler el ile yanıt eylemlerini, otomatik araştırmadan sonraki eylemleri ve canlı yanıt eylemlerini içerir.

Aşağıdaki tabloda, kullanılabilen düzeltme eylemleri listelenir:

| Kaynak  | Eylem  |
|---------|---------|
| [Otomatik araştırma](../security/defender-endpoint/automated-investigations.md)      | - Dosyayı karantinaya al <br/>- Kayıt defteri anahtarını kaldırma <br/>- Bir işlemi sonlandırma <br/>- Hizmeti durdurma <br/>- Sürücüyü devre dışı bırakma <br/>- Zamanlanmış görevi kaldırma        |
| [El ile yanıt eylemleri](../security/defender-endpoint/respond-machine-alerts.md)   | - Virüsten koruma taraması çalıştırma <br/>- Cihazı yalıtma <br/>- Durdurma ve karantinaya al <br/>- Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme       |
| [Canlı yanıt](../security/defender-endpoint/live-response.md)   | - Adli veri toplama <br/>- Bir dosyayı analiz etme <br/>- Betik çalıştırma <br/>- Şüpheli bir varlığı analiz için Microsoft'a gönderme <br/>- Dosyayı düzeltme <br/>- Tehditleri proaktif olarak avlama         |
