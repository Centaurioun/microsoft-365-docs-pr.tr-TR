---
title: Güvenlik panosuna genel bakış
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Tehdit Koruması Durumunu gözden geçirmek ve güvenlik uyarılarını görüntülemek ve üzerinde işlem yapmak için yeni Güvenlik Panosu'nu kullanın.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: f417c64329b0a8e276e34e65520b56f7d788171b
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497301"
---
# <a name="security-dashboard-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'ndeki güvenlik panosu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Temel işlevler ve Güvenlik panosunu açma

konumundaki Güvenlik & Uyumluluk Merkezi <https://protection.office.com> , kuruluşunuzun veri korumasını ve uyumluluğu yönetmesini sağlar. Gerekli izinlere sahip olduğunuzu varsayarsak, Güvenlik Panosu Tehdit Koruması Durumunuzu gözden geçirmenin yanı sıra güvenlik uyarılarını görüntülemenize ve üzerinde işlem yapmaya olanak tanır.

Genel bakış almak için videoyu izleyin ve daha fazla bilgi edinmek için bu makaleyi okuyun.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Kuruluşunuzun aboneliğinin içeriğine bağlı olarak, Güvenlik Panosu aşağıdaki bölümlerde açıklandığı gibi Tehdit Yönetimi Özeti, Tehdit Koruması Durumu, Genel Haftalık Tehdit Algılamaları, Kötü Amaçlı Yazılım ve daha fazlası gibi çeşitli pencere öğeleri içerir.

Güvenlik & Uyumluluk Merkezi'nde Güvenlik Panosu'nu görüntülemek için **Tehdit yönetimi** \> **Panosu'na** gidin. Doğrudan Güvenlik panosuna gitmek için kullanın <https://protection.office.com/searchandinvestigation/dashboard>.

> [!NOTE]
> Güvenlik Panosu'nu görüntülemek için genel yönetici, güvenlik yöneticisi veya güvenlik okuyucusu olmanız gerekir. Bazı pencere öğelerini görüntülemek için ek izinler gerekir. Daha fazla bilgi edinmek için [bkz. Güvenlik & Uyumluluk Merkezi'ndeki İzinler](permissions-in-the-security-and-compliance-center.md)[.

## <a name="threat-management-summary"></a>Tehdit Yönetimi Özeti

Tehdit Yönetimi Özeti pencere öğesi, kuruluşunuzun son yedi (7) gün içinde tehditlere karşı nasıl korunduğunu bir bakışta bildirir.

:::image type="content" source="../../media/SecDash-ThreatMgmtSummary.png" alt-text="Güvenlik Panosu - Tehdit Yönetimi Özeti pencere öğesi" lightbox="../../media/SecDash-ThreatMgmtSummary.png":::

Tehdit Yönetimi Özeti'nde göreceğiniz bilgiler, aboneliğinizin içeriğine bağlıdır. Aşağıdaki tabloda, Office 365 E3 ve Office 365 E5 için hangi bilgilerin dahil olduğu açıklanmaktadır.

|Office 365 E3|Office 365 E5|
|---|---|
|Kötü amaçlı yazılım iletileri engellendi<br>Kimlik avı iletileri engellendi<br>Kullanıcılar tarafından bildirilen iletiler<br><br><br><br>|Kötü amaçlı yazılım iletileri engellendi<br>Kimlik avı iletileri engellendi<br>Kullanıcılar tarafından bildirilen iletiler<br>Sıfır günlük kötü amaçlı yazılım engellendi<br>Gelişmiş kimlik avı iletileri algılandı<br>Kötü amaçlı URL'ler engellendi|

Tehdit Yönetimi Özeti pencere öğesini görüntülemek veya erişmek için Office 365 için Defender raporları görüntüleme izinleriniz olmalıdır. Daha fazla bilgi edinmek için bkz[. Office 365 için Defender raporlarını görüntülemek için hangi izinler gerekiyor?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Tehdit Koruması Durumu

Tehdit Koruması Durumu pencere öğesi, tehdit koruması etkinliğini, kimlik avı ve kötü amaçlı yazılımların popüler ve ayrıntılı bir görünümüyle gösterir.

:::image type="content" source="../../media/tpswidget.png" alt-text="Tehdit koruması durum pencere öğesi" lightbox="../../media/tpswidget.png":::

Ayrıntılar, Microsoft 365 aboneliğinizin [Office 365 için Microsoft Defender](exchange-online-protection-overview.md) Exchange Online Protection (EOP) içerip içermediğine [bağlıdır.](defender-for-office-365.md)

|Aboneliğiniz...|Bu ayrıntıları görürsünüz|
|---|---|
|EOP ama Office 365 için Microsoft Defender|EOP tarafından algılanan ve engellenen kötü amaçlı e-posta.<p> Bkz. [Tehdit Koruması Durumu raporu (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Office 365 için Microsoft Defender|EOP ve Office 365 için Defender tarafından algılanan ve engellenen kötü amaçlı içerik ve kötü amaçlı e-posta <p> Kötü amaçlı yazılımdan koruma altyapısı tarafından engellenen kötü amaçlı içeriğe sahip benzersiz e-posta iletilerinin toplam sayısı, [sıfır saatlik otomatik temizleme](zero-hour-auto-purge.md) ve Office 365 için Defender özellikleri ([güvenli bağlantılar](safe-links.md), [güvenli ekler](safe-attachments.md) ve [Office 365 için Defender kimlik avı önleme](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) dahil). <p> [Bkz. Tehdit koruması durum raporu](view-reports-for-mdo.md#threat-protection-status-report).|

Tehdit Koruması Durumu pencere öğesini görüntülemek veya erişmek için Office 365 için Defender raporları görüntüleme izinleriniz olmalıdır. Daha fazla bilgi edinmek için bkz[. Office 365 için Defender raporlarını görüntülemek için gereken izinler nelerdir?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Küresel Haftalık Tehdit Algılamaları

Genel Haftalık Tehdit Algılamaları pencere öğesi, son yedi (7) gün içinde e-posta iletilerinde kaç tehdit algılandığını gösterir.

:::image type="content" source="../../media/globalweeklythreatdetections.png" alt-text="Genel Haftalık Tehdit Algılamaları pencere öğesi" lightbox="../../media/globalweeklythreatdetections.png":::

Ölçümler aşağıdaki tabloda açıklandığı gibi hesaplanır:

|Metrik|Nasıl hesaplanır?|
|---|---|
|Taranan iletiler|Taranan e-posta iletilerinin sayısı alıcı sayısıyla çarpıldı|
|Tehditler durduruldu|Kötü amaçlı yazılım içerdiği belirlenen e-posta iletilerinin sayısı alıcı sayısıyla çarpıldı|
|[Office 365 için Defender](defender-for-office-365.md) tarafından engellendi|Office 365 için Defender tarafından engellenen e-posta iletilerinin sayısı, alıcı sayısıyla çarpılır|
|Teslimden sonra kaldırıldı|[Sıfır saatlik otomatik temizleme (ZAP)](zero-hour-auto-purge.md) tarafından kaldırılan iletilerin sayısı, alıcı sayısıyla çarpılır|

## <a name="malware"></a>Malware

Kötü amaçlı yazılım pencere öğeleri, son yedi (7) gün içindeki kötü amaçlı yazılım eğilimleri ve kötü amaçlı yazılım aile türleri hakkındaki ayrıntıları gösterir.

:::image type="content" source="../../media/malwarewidgetatpe5.png" alt-text="Kötü amaçlı yazılım eğilimleri ve aile türleri" lightbox="../../media/malwarewidgetatpe5.png":::

## <a name="insights"></a>Bilgi Edinme

İçgörüler yalnızca gözden geçirmeniz gereken önemli sorunları ortaya aktarmakla kalmaz, dikkate alınması gereken öneriler ve eylemler de içerir.

:::image type="content" source="../../media/smartinsights.png" alt-text="Akıllı içgörüler" lightbox="../../media/smartinsights.png":::

Örneğin, bazı kullanıcılar gereksiz posta seçeneklerini devre dışı bırakmış olduğundan kimlik avı e-posta iletilerinin teslim edildiğini görebilirsiniz. İçgörülerin nasıl çalıştığı hakkında daha fazla bilgi edinmek için [bkz. Güvenlik & Uyumluluk Merkezi'ndeki Raporlar ve içgörüler](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Tehdit araştırması ve yanıtı

Kuruluşunuzun aboneliği [Office 365 için Microsoft Defender Plan 2](office-365-ti.md) içeriyorsa Güvenlik Panonuzun gelişmiş tehdit araştırması ve yanıt araçlarını içeren bir bölümü vardır. Bu araçlar [otomatik araştırma ve yanıt özelliklerini](automated-investigation-response-office.md) içerir. Güvenliği [aşılmış kullanıcı hesaplarını hızla ele alma](address-compromised-users-quickly.md) gibi senaryolarda otomatik araştırma ve yanıt yararlı olabilir.

Daha fazla bilgi edinmek için bkz. [Office 365'da otomatik araştırma ve yanıt (AIR) kullanmaya başlama](office-365-air.md).

## <a name="trends"></a>Eğilim

Güvenlik Panosu'nun alt kısmında, kuruluşunuza yönelik e-posta akışı eğilimlerini özetleyen **Eğilimler** bölümü bulunur. Raporlar istenmeyen posta, kötü amaçlı yazılım, kimlik avı girişimleri ve iyi e-posta olarak kategorilere ayrılmış e-postalar hakkında bilgi sağlar. Rapordaki daha ayrıntılı bilgileri görüntülemek için bir kutucuğa tıklayın.

:::image type="content" source="../../media/trends.png" alt-text="Kuruluşa yönelik e-posta akışı eğilimlerini özetleyen Eğilimler bölümü" lightbox="../../media/trends.png":::

Kuruluşunuzun aboneliği [Office 365 için Defender Plan 2](office-365-ti.md) içeriyorsa, bu bölümde güvenlik ekibinizin yüksek öncelikli güvenlik uyarılarını görüntülemesine ve üzerinde işlem gerçekleştirmesine olanak tanıyan **son tehdit yönetimi uyarıları** raporunuz da olacaktır.

Gönderilen ve Alınan Email pencere öğesini görüntülemek veya erişmek için Office 365 için Defender raporları görüntüleme izinleriniz olmalıdır. Daha fazla bilgi edinmek için bkz[. Office 365 için Defender raporlarını görüntülemek için hangi izinler gerekiyor?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Son Tehdit Yönetimi Uyarıları pencere öğesini görüntülemek veya erişmek için uyarıları görüntüleme izinleriniz olmalıdır. Daha fazla bilgi edinmek için bkz. [Uyarıları görüntülemek için gereken RBAC izinleri](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-articles"></a>İlgili makaleler

[Güvenlik & Uyumluluk Merkezi'nde e-posta güvenlik raporlarını görüntüleme](view-email-security-reports.md)

[Office 365 için Microsoft Defender için raporları görüntüleme](view-reports-for-mdo.md)

[Office 365 için Defender](defender-for-office-365.md)

[Office 365 Tehdit araştırması ve yanıtı](office-365-ti.md)
