---
title: Office 365 için Microsoft Defender'de düzeltme eylemlerini gözden geçirme ve yönetme
keywords: AIR, autoIR, Uç Nokta için Microsoft Defender, otomatik, araştırma, yanıt, düzeltme, tehditler, gelişmiş, tehdit, koruma
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom: ''
description: Office 365 için Microsoft Defender Plan 2'de otomatik araştırma ve yanıt özelliklerindeki düzeltme eylemleri hakkında bilgi edinin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.date: 06/10/2021
ms.openlocfilehash: 82a81a4b34fb5842fe21ec61321fd6d592472ba3
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68543123"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Office 365'de düzeltme eylemlerini gözden geçirme ve yönetme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)

E-posta & işbirliği içeriğiyle ilgili otomatik araştırmalar *Kötü Amaçlı* veya *Şüpheli* gibi kararlara neden olduğundan, bazı düzeltme eylemleri oluşturulur. Office 365 için Microsoft Defender düzeltme eylemleri şunları içerebilir:

- E-posta iletilerini veya kümeleri geçici silme
- Dış posta iletmeyi kapatma

Bu düzeltme eylemleri, güvenlik operasyonları ekibiniz tarafından onaylanmadıkça ve onaylanana kadar yapılmaz. Otomatik araştırmalarınızın zamanında tamamlanması için bekleyen eylemleri en kısa sürede gözden geçirmenizi ve onaylamanızı öneririz. Herhangi bir eylem gerçekleştirmeden önce Arama & temizleme rolünün parçası olmanız gerekir.

Aynı kümelerle yinelenen veya çakışan araştırmalara yönelik ek denetimler ekledik. Aynı araştırma kümesi önceki saat içinde zaten onaylandıysa, yeni yinelenen düzeltme yeniden işlenmez. Bu davranış yinelenen araştırmaları veya araştırma kanıtlarını kaldırmaz; düzeltme işleme hızını artırmak için onaylanan eylemlerin yinelenenlerini kaldırır. Yinelenen onaylanan küme araştırmalarında [işlem merkezi](https://security.microsoft.com/action-center/history) yan panelinde eylem ayrıntılarını görmezsiniz. 

## <a name="approve-or-reject-pending-actions"></a>Bekleyen eylemleri onaylama (veya reddetme)

Otomatik araştırma eylemlerini bulmanın ve gerçekleştirmenin dört farklı yolu vardır:

- [Olay kuyruğu](https://security.microsoft.com/incidents)
- Araştırmanın kendisi (Olay aracılığıyla veya bir uyarıdan erişilir)
- [İşlem merkezi](https://security.microsoft.com/action-center/pending)
- [Araştırma ve düzeltme araştırmaları kuyruğu](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Olay kuyruğu

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Olaylar** **& uyarılar** \> Güvenlik olayları sayfasındaki **Olaylar** sayfasına gidin. Doğrudan **Olaylar** sayfasına gitmek için kullanın <https://security.microsoft.com/incidents>.
2. **Olaylar** sayfasında bir olay adı seçerek özet sayfasını açın.
3. **Kanıt ve Yanıt** sekmesini seçin.
4. Listeden bir öğe seçin. Yan bölmesi açılır.
5. Yan bölmede onaylayın veya eylemleri reddedin.

## <a name="action-center"></a>İşlem merkezi

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**İşlem merkezi'ni** seçerek **İşlem merkezi** sayfasına gidin. Doğrudan **İşlem merkezi** sayfasına gitmek için kullanın <https://security.microsoft.com/action-center/pending>.
2. **İşlem merkezi** sayfasında **Bekleyen** sekmesinin seçili olduğunu doğrulayın ve onay bekleyen eylemlerin listesini gözden geçirin.
   - Araştırma hakkında daha fazla ayrıntı görüntülemek için **Araştırma sayfasını aç'ı** seçin.
   - Bekleyen bir eylem başlatmak için **Onayla'yı** seçin.
   - Bekleyen bir eylemin gerçekleştirilmesini önlemek için **Reddet'i** seçin.

## <a name="investigation-and-remediation-investigations-queue"></a>Araştırma ve düzeltme araştırmaları kuyruğu

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Email & işbirliği** \> **Araştırmalarındaki Tehdit araştırması** sayfasına gidin. **Doğrudan Tehdit araştırması** sayfasına gitmek için kullanın<https://security.microsoft.com/airinvestigation>.
2. **Tehdit araştırması** sayfasında, ve listesinden durumu **Bekleyen eylem** olan bir öğe bulun.
3. Yeni pencerede aç simgesine tıklayın ![.](../../media/m365-cc-sc-open-icon.png) Liste zamanında (**Kimlik** ve **Durum** arasında) **yeni pencerede açın**.
4. Açılan sayfada onaylayın veya eylemleri reddedin.

## <a name="change-or-undo-one-remediation-action"></a>Bir düzeltme eylemini değiştirme veya geri alma

Gönderilen eylemleri yeniden gözden geçirmenin iki farklı yolu vardır:

- [Birleşik işlem merkezi](https://security.microsoft.com/action-center) aracılığıyla.
- Ancak [Office işlem merkezi](https://security.microsoft.com/threatincidents).

## <a name="change-or-undo-through-the-unified-action-center"></a>Birleşik işlem merkezi aracılığıyla değiştirme veya geri alma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>İşlem merkezi'ni seçerek birleşik işlem **merkezine** gidin. Doğrudan birleşik işlem merkezine gitmek için kullanın <https://security.microsoft.com/action-center/>.
2. **İşlem merkezi** sayfasında **Geçmiş** sekmesini seçin ve ardından değiştirmek veya geri almak istediğiniz eylemi seçin.
3. Ekranın sağ tarafındaki bölmede uygun eylemi seçin (**gelen kutusuna gitme**, **gereksiz öğeye gitme**, **silinmiş öğelere gitme**, **geçici silme** veya **sabit silme**).

## <a name="change-or-undo-through-the-office-action-center"></a>Office işlem merkezi aracılığıyla değiştirme veya geri alma

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Email & işbirliği** \> **gözden geçirme** \> **İşlem merkezi'ndeki** Office işlem merkezine gidin. Doğrudan Office işlem merkezine gitmek için kullanın <https://security.microsoft.com/threatincidents>.
2. **İşlem merkezi** sayfasında uygun düzeltmeyi seçin.
3. Yan panelde posta gönderimleri girdisine tıklayın ve listenin yüklenmesini bekleyin.
4. En üstteki Eylem düğmesinin etkinleştirilmesini bekleyin ve eylem türünü değiştirmek için Eylem düğmesini seçin.
5. Bu, uygun eylemleri oluşturur.

## <a name="next-steps"></a>Sonraki adımlar

- [Tehdit Gezgini'ni kullanma](threat-explorer.md)
- [Yönetici /El ile Eylemler](remediate-malicious-email-delivered-office-365.md)
- [Otomatik araştırma ve yanıt özelliklerinde hatalı pozitif/negatifleri bildirme](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Ayrıca bkz.

- [otomatik araştırmanın ayrıntılarını ve sonuçlarını Office 365](air-view-investigation-results.md)
