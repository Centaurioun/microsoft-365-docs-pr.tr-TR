---
title: İş için Microsoft Defender'de düzeltme eylemlerini gözden geçirme
description: İş için Defender ile algılanan tehditlere karşı alınan düzeltmeleri görüntüleyin. eylemleri Microsoft 365 Defender portalındaki İşlem merkezinde görüntüleyebilirsiniz.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: f31f478fda2f8f2540dd524c2dbaf1113801dca8
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598010"
---
# <a name="review-remediation-actions-in-the-action-center"></a>İşlem merkezindeki düzeltme eylemlerini gözden geçirme

Tehditler algılandıkçe düzeltme eylemleri devreye girer. Belirli bir tehdide ve güvenlik ayarlarınızın nasıl yapılandırıldığına bağlı olarak, düzeltme eylemleri otomatik olarak veya yalnızca onaylandığında gerçekleştirilebilir. Düzeltme eylemlerine örnek olarak şunlar verilebilir: 
- Karantinaya dosya gönderme
- İşlemin çalışmasını durdurma
- Zamanlanmış görevi kaldırma

Tüm düzeltme eylemleri İşlem merkezinde izlenir.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="İşlem merkezinin ekran görüntüsü":::

**Bu makalede şunlar açıklanmaktadır**:

- [İşlem merkezini kullanma](#how-to-use-the-action-center)
- [Düzeltme eylemleri](#remediation-actions)


## <a name="how-to-use-the-action-center"></a>İşlem merkezini kullanma

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **İşlem merkezi'ni** seçin.

3. Bekleyen eylemleri görüntülemek ve onaylamak (veya reddetmek) için **Beklemede** sekmesini seçin. Eylemler virüsten koruma/kötü amaçlı yazılımdan koruma, otomatik araştırma, el ile yanıt etkinlikleri veya canlı yanıt oturumlarından kaynaklanabilir.

4. Tamamlanan eylemlerin listesini görüntülemek için **Geçmiş** sekmesini seçin.

## <a name="remediation-actions"></a>Düzeltme eylemleri

İş için Defender çeşitli düzeltme eylemleri içerir. Bu eylemler el ile yanıt eylemlerini, otomatik araştırmadan sonraki eylemleri ve canlı yanıt eylemlerini içerir.

Aşağıdaki tabloda, kullanılabilen düzeltme eylemleri listelenir.

| Kaynak  | Eylem  |
|---------|---------|
| [Otomatik araştırma](../defender-endpoint/automated-investigations.md)      |<ul><li>Dosyayı karantinaya al</li><li>Kayıt defteri anahtarını kaldırma</li><li>İşlemi sonlandırma</li><li>Hizmeti durdurma</li><li>Sürücüyü devre dışı bırakma</li><li>Zamanlanmış görevi kaldırma </li></ul> |
| [El ile yanıt eylemleri](../defender-endpoint/respond-machine-alerts.md)   |<ul><li>Antivirüs taraması başlat</li><li>Cihazı yalıtma</li><li>Durdurma ve karantinaya al</li><li>Bir dosyayı engellemek veya dosyaya izin vermek için gösterge ekleme</li></ul> |
| [Canlı yanıt](../defender-endpoint/live-response.md)   |<ul><li>Adli veri toplama</li><li>Dosyayı analiz etme</li><li>Betik çalıştırma</li><li>Şüpheli bir varlığı analiz için Microsoft'a gönderme</li><li>Dosyayı düzeltme </li><li>Tehditleri proaktif olarak avlama</li></ul>|

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İş için Defender'da cihazları yönetme](mdb-manage-devices.md)
