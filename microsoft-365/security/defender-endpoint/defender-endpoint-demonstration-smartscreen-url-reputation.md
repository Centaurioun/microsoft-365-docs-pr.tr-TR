---
title: SmartScreen URL'si saygınlığı tanıtımlarını Uç Nokta için Microsoft Defender
description: Microsoft Defender SmartScreen'in URL saygınlığına göre kimlik avı ve kötü amaçlı yazılım web sitelerini nasıl tanımladığı gösterilir.
keywords: Uç Nokta için Microsoft Defender, web sitesi kimlik avı koruması, web sitesi kötü amaçlı yazılım koruması, URL saygınlığı, tanıtım,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: 3f00b4cf32c3813bfcf67e2390f503156097d9f2
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729643"
---
# <a name="url-reputation-demonstrations"></a>URL saygınlığı tanıtımları

Microsoft Defender SmartScreen'in URL saygınlığına göre kimlik avı ve kötü amaçlı yazılım web sitelerini tanımlamanıza nasıl yardımcı olduğunu test edin.
Senaryo gereksinimleri ve kurulumu

- Windows 10 veya 11
- Microsoft Edge tarayıcısı gerekli
- Daha fazla bilgi için bkz. [SmartScreen Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

## <a name="smartscreen-for-microsoft-edge-url-scenario-demonstrations"></a>Microsoft Edge URL senaryosu tanıtımları için SmartScreen

### <a name="is-this-phishing"></a>Bu kimlik avı mı?

Kullanıcıyı şüpheli bir sayfaya uyarır ve geri bildirim ister:

- [Bu Kimlik Avı mı?](https://demo.smartscreen.msft.net/other/areyousure.html)

  Bu bağlantının başlatılması, aşağıdaki ekran görüntüsüne benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-url-reputation-is-this-phishing.png" alt-text="SmartScreen, sitenin bir kimlik avı sitesi olduğu ve muhtemelen güvenli olmayabilecek bir site olduğu konusunda kullanıcıyı uyarır":::

### <a name="phishing-page"></a>Kimlik Avı Sayfası

Kimlik avı için bilinen ve engellenmesi gereken bir sayfa:

- [Bilinen bir Kimlik Avı sayfası](https://demo.smartscreen.msft.net/phishingdemo.html)

  Bu bağlantının başlatılması aşağıdaki örneğe benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-url-reputation-this-is-phishing.png" alt-text="SmartScreen, sitenin kimlik avı tehditleri içerdiğini bildirir":::

### <a name="malware-page"></a>Kötü amaçlı yazılım sayfası

Kötü amaçlı yazılımları barındıran ve engellenmesi gereken bir sayfa:

- [Bilinen bir kötü amaçlı yazılım sayfası](https://demo.smartscreen.msft.net/other/malware.html)

  Bu bağlantının başlatılması, aşağıdaki ekran görüntüsüne benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-url-reputation-malware-page.png" alt-text="SmartScreen, sitenin zararlı programlar içerdiğini bildiği konusunda kullanıcıyı uyarır":::

### <a name="blocked-download"></a>İndirme engellendi

URL saygınlığı nedeniyle indirmesi engellendi

- [URL saygınlığı nedeniyle indirme engellendi](https://demo.smartscreen.msft.net/download/malwaredemo/freevideo.exe)

  Bu bağlantının başlatılması, Kötü Amaçlı Yazılım sayfa iletisine benzer bir ileti işlemelidir.

### <a name="exploit-page"></a>Yararlanma sayfası

Tarayıcı güvenlik açığına saldıran bir sayfa

- [Bilinen tarayıcı açık sayfası](https://demo.smartscreen.msft.net/other/exploit.html)

  Bu bağlantının başlatılması, Kötü Amaçlı Yazılım sayfa iletisine benzer bir ileti işlemelidir.

### <a name="malvertising"></a>Malvertising

Kötü amaçlı bir reklamı barındıran zararsız bir sayfa

- [Kötü amaçlı reklamlar içerdiği bilinen bir sayfa](https://demo.smartscreen.msft.net/other/exploit_frame.html)

  Bu bağlantının başlatılması, aşağıdaki ekran görüntüsüne benzer bir ileti işlemelidir:

  :::image type="content" source="images/smartscreen-url-reputation-malvertising.png" alt-text="SmartScreen'in kötü amaçlı olduğu algılanan bir sayfadaki çerçeveye nasıl yanıt verdiğini gösteren bir gösterim. Yalnızca kötü amaçlı çerçeve engellenir":::

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Defender SmartScreen Belgeleri](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
