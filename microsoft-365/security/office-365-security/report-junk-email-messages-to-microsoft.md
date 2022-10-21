---
title: İstenmeyen postaları, istenmeyen posta olmayanları, kimlik avı, şüpheli e-postaları ve dosyaları Microsoft'a bildirin
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- m365-security
description: Şüpheli bir e-postayı veya dosyayı Microsoft'a Nasıl yaparım? bildirdiniz? İletileri, URL'leri, e-posta eklerini ve dosyaları analiz için Microsoft'a bildirin. İstenmeyen posta ve kimlik avı e-postalarını bildirmeyi öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3d27b7d3e76454245c7d429fc025237b1c84f690
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662983"
---
# <a name="how-do-i-report-a-suspicious-email-or-file-to-microsoft"></a>Şüpheli bir e-postayı veya dosyayı Microsoft'a Nasıl yaparım? bildirdiniz?

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Şüpheli e-postalar veya dosyalarla ne yapacağız merak mı ediyorsunuz? Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, *kullanıcıların* ve *yöneticilerin* şüpheli bir e-posta iletisini, URL'yi veya e-posta eklerini Microsoft'a bildirmenin farklı yolları vardır.

Ayrıca, Uç Nokta için Microsoft Defender yöneticileri olan Microsoft 365 kuruluşları da dosyaları raporlamak için çeşitli yöntemlere sahiptir.

Birleşik gönderim deneyimi hakkında daha fazla bilgi gösteren bu videoyu izleyin.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE50HhM]

## <a name="report-a-suspicious-email-to-microsoft"></a>Şüpheli bir e-postayı Microsoft'a bildirme

|Yöntem|Gönderim türü|Açıklama|
|---|---|---|
|[Şüpheli istenmeyen posta, kimlik avı, URL'ler ve e-posta eklerini Microsoft'a göndermek için Gönderimler portalını kullanın](admin-submission.md)|Yönetici|Exchange Online posta kutuları olan kuruluşlardaki yöneticiler için önerilen raporlama yöntemi (tek başına EOP'de kullanılamaz).|
|[Rapor İletisini veya Rapor Kimlik Avı eklentilerini etkinleştirme](enable-the-report-message-add-in.md)|Kullanıcı|Outlook ve Web üzerinde Outlook (eski adıyla Outlook Web App) ile çalışır. <br/><br/> Aboneliğinize bağlı olarak, kullanıcıların eklentilerle bildirdiği iletiler [Yönetici Gönderimler portalında](admin-submission.md), [Otomatik araştırma ve yanıt (AIR) sonuçlarında](air-view-investigation-results.md), [Kullanıcı tarafından bildirilen iletiler raporunda](view-email-security-reports.md#user-reported-messages-report) ve [Gezgin'de](threat-explorer-views.md#email--submissions) kullanılabilir. <br/><br/> Bildirilen iletileri, belirttiğiniz bir posta kutusuna kopyalanacak veya yeniden yönlendirilecek şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı gönderim ilkeleri](user-submission.md).
|[Outlook'ta yanlış pozitifleri ve yanlış negatifleri bildirme](report-false-positives-and-false-negatives.md)|Kullanıcı|Rapor İletisi özelliğini kullanarak hatalı pozitif sonuçları (engellenmiş veya gereksiz klasöre gönderilmiş iyi e-posta) ve hatalı negatifleri (gelen kutusuna teslim edilen istenmeyen e-posta veya kimlik avı) Exchange Online Protection (EOP) adresine gönderin.|
|[Kullanıcıların Microsoft'a ne bildirdiğini görmek için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Yönetici|Kullanıcılar analiz için Microsoft'a ileti bildirdiğinde size bildirimde bulunmanızı sağlayan bir posta akışı kuralı (taşıma kuralı olarak da bilinir) oluşturmayı öğrenin.|
|[Dosyaları analiz için gönderin](../intelligence/submission-guide.md)|Yönetici|E-posta eklerini ve diğer şüpheli dosyaları analiz için Microsoft'a gönderin.|

> [!NOTE]
> Bir e-posta varlığını Microsoft'a bildirdiğinizde, e-postayla ilişkili her şeyi kopyalayarak sürekli algoritma incelemelerimize ekleriz. Bu kopya e-posta içeriğini, e-posta üst bilgilerini ve e-posta yönlendirmeyle ilgili verileri içerir. Tüm ileti ekleri de eklenir.
>
> Microsoft, geri bildiriminizi kuruluşunuzun daha önce açıklanan tüm bilgileri analiz etme izni olarak değerlendirerek ileti hijyen algoritmalarına ince ayar uygular. mesajınızı ABD'deki güvenli denetimli veri merkezlerimizde tutuyoruz. Gönderim, siz bize sağladıktan en fazla 30 gün sonra silinir. Microsoft personeli gönderdiğiniz iletileri ve ekleri okuyabilir ve bu normalde Microsoft 365'te e-posta için izin verilmez. Ancak, e-postanız sizinle Microsoft arasında gizli olarak ele alınmaya devam eder ve e-postanızı veya eklerinizi gözden geçirme işleminin bir parçası olarak başka bir tarafa sağlamayacağız.
