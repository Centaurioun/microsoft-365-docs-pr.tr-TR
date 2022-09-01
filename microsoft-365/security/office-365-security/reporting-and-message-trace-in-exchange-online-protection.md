---
title: Raporlama ve ileti izleme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: Bu makalede, Microsoft Exchange Online Koruması (EOP) yöneticilerinin kullanabileceği raporlar ve sorun giderme araçları hakkında bilgi edineceksiniz.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: c8bca790e7916daacada685f15581f6c5fbcf6f2
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495800"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP'de raporlama ve ileti izleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında EOP, kuruluşunuzun genel durumunu ve durumunu belirlemenize yardımcı olabilecek birçok farklı rapor sunar. Ayrıca belirli olayları gidermenize yardımcı olacak araçlar (örneğin, hedeflenen alıcılarına ulaşılmayan bir ileti) ve uyumluluk gereksinimlerine yardımcı olacak denetim raporları da vardır.

## <a name="usage-reports"></a>Kullanım raporları

- **Microsoft 365 grupları etkinliği**: Oluşturulan ve kullanılan Microsoft 365 gruplarının sayısı hakkındaki bilgileri görüntüleyin. Daha fazla bilgi için bkz. [Yönetim merkezinde Microsoft 365 Raporları - Microsoft 365 grupları](../../admin/activity-reports/office-365-groups.md).
- **Email etkinliği**: Tüm kuruluşunuzda ve belirli kullanıcılar tarafından gönderilen, alınan ve okunan ileti sayısı hakkındaki bilgileri görüntüleyin. Daha fazla bilgi için bkz. [Yönetim merkezinde Microsoft 365 Raporları - Email etkinliği](../../admin/activity-reports/email-activity.md).
- **Uygulama kullanımını Email**: Kullanılan e-posta uygulamaları hakkındaki bilgileri görüntüleyin. Bu, her uygulama için toplam bağlantı sayısını ve bağlanan Outlook sürümlerini içerir. Daha fazla bilgi için bkz. [Yönetim merkezinde Microsoft 365 Raporları - uygulama kullanımı Email](../../admin/activity-reports/email-apps-usage.md).
- **Posta kutusu kullanımı**: Posta kutuları için kullanılan depolama alanı, kota tüketimi, öğe sayısı ve son etkinlik (gönderme veya okuma etkinliği) hakkındaki bilgileri görüntüleyin. Daha fazla bilgi için bkz. [Yönetim merkezinde Microsoft 365 Raporları - Posta kutusu kullanımı](../../admin/activity-reports/mailbox-usage.md).

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 defender portalındaki güvenlik raporları

Bu gelişmiş raporlar, EOP yöneticileri için özet bilgileri ve daha fazla ayrıntı için detaya gitme özelliğini içeren etkileşimli bir raporlama deneyimi sağlar.

- **Office 365 için Defender**: Office 365 için Microsoft Defender parçası olan Güvenli Bağlantılar ve Güvenli Ekler hakkındaki bilgileri görüntüleyin. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında Office 365 için Defender raporlarını görüntüleme](view-reports-for-mdo.md).
- **EOP**: Kötü amaçlı yazılım algılamaları, sahte posta, istenmeyen posta algılamaları ve kuruluşunuza gelen ve kuruluşunuzdan gelen posta akışı hakkındaki bilgileri görüntüleyin. Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında e-posta güvenlik raporlarını görüntüleme](view-email-security-reports.md).

## <a name="mail-flow-insights-in-the-security--compliance-center"></a>Güvenlik ve Uyumluluk Merkezi'ndeki posta akışı içgörüleri

Daha fazla bilgi için [bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).

## <a name="custom-reports-using-microsoft-graph"></a>Microsoft Graph kullanan özel raporlar

Program aracılığıyla Microsoft Graph kullanarak yönetim merkezinde kullanılabilen raporlar oluşturun. Daha fazla bilgi için bkz. [Microsoft Graph'a Genel Bakış](/graph/overview) ve [Microsoft Graph'ta Office 365 kullanım raporlarıyla çalışma](/graph/api/resources/report).

## <a name="message-trace"></a>İleti izleme

EOP üzerinden seyahat eden e-posta iletilerini izler. Bir e-posta iletisinin hizmet tarafından alındığını, reddedildiğini, ertelendiğini veya teslim edildiğini belirleyebilirsiniz. Ayrıca iletinin son durumuna ulaşmadan önce hangi eylemlerin gerçekleştirildiğini de gösterir.

Bu bilgileri, kullanıcınızın sorularını verimli bir şekilde yanıtlamak, posta akışı sorunlarını gidermek, ilke değişikliklerini doğrulamak ve yardım için teknik desteğe başvurma gereksinimini azaltmak için kullanabilirsiniz.

[bkz. Microsoft 365 Defender portalında ileti izleme](message-trace-scc.md).

## <a name="audit-logging"></a>Denetim günlüğü

Yöneticiler tarafından kuruluşunuzda yapılan belirli değişiklikleri izler. Bu raporlar, yapılandırma sorunlarını gidermenize veya güvenlik veya uyumlulukla ilgili sorunların nedenini bulmanıza yardımcı olabilir. Bkz[. Exchange Online'de raporları denetleme](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Raporlama ve ileti izleme verilerinin kullanılabilirliği ve gecikme süresi

Aşağıdaki tabloda EOP raporlama ve ileti izleme verilerinin ne zaman ve ne kadar süreyle kullanılabilir olduğu açıklanmaktadır.

|Rapor türü|Için kullanılabilir veriler (geriye bakma dönemi)|Gecikme|
|---|---|---|
|Posta koruma özet raporları|90 gün|İleti verileri toplama işlemi çoğunlukla 24-48 saat içinde tamamlanır. Bazı küçük artımlı toplu değişiklikler 5 güne kadar gerçekleşebilir.|
|Posta koruma ayrıntı raporları|90 gün|7 günden daha eski olan ayrıntılı veriler için veriler 24 saat içinde görünmelidir ancak 48 saate kadar tamamlanmayabilir. Bazı küçük artımlı değişiklikler 5 güne kadar gerçekleşebilir. <p> 7 günden eski iletilerin ayrıntılı raporlarını görüntülemek için sonuçlar birkaç saat kadar sürebilir.|
|İleti izleme verileri|90 gün|7 günden daha eski iletiler için bir ileti izlemesi çalıştırdığınızda, iletiler 5-30 dakika içinde görünmelidir.<p> 7 günden eski iletiler için bir ileti izlemesi çalıştırdığınızda, sonuçlar birkaç saat kadar sürebilir.|

> [!NOTE]
> Yönetim merkezi veya uzak PowerShell aracılığıyla istense de veri kullanılabilirliği ve gecikme süresi aynıdır.
