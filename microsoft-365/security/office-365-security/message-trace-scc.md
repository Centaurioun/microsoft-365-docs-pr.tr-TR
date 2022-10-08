---
title: Microsoft 365 Defender portalında ileti izleme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, iletilere ne olduğunu öğrenmek için Microsoft 365 Defender portalındaki ileti izleme bağlantısını kullanabilir.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 7412cade7e934ca7095e308a40558084a8404ddf
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086973"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında ileti izleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

İleti izleme, Exchange Online kuruluşunuzda gezinen e-posta iletilerini izler. Bir iletinin hizmet tarafından alındığını, reddedildiğini, ertelendiğini veya teslim edildiğini belirleyebilirsiniz. Ayrıca iletinin son durumuna ulaşmadan önce hangi eylemlerin gerçekleştirildiğini de gösterir.

İleti izlemedeki bilgileri, iletilere ne olduğuyla ilgili kullanıcı sorularını verimli bir şekilde yanıtlamak, posta akışı sorunlarını gidermek ve ilke değişikliklerini doğrulamak için kullanabilirsiniz.

> [!NOTE]
> Microsoft 365 Defender portalındaki ileti izleme, Yalnızca Exchange yönetim merkezindeki İleti izlemesine bir geçiştir. Daha fazla bilgi için bkz. [Modern Exchange yönetim merkezinde ileti izleme](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- İleti izleme özelliğini kullanmak için **Exchange Online'da Kuruluş Yönetimi**, **Uyumluluk Yönetimi** veya **Yardım Masası** rol gruplarının  üyesi olmanız gerekir. Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  **Notlar**: Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne üyelik, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri _ve_ izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).

- İleti izlemesinin sonuçlarında görüntülenen ileti sayısı üst sınırı, seçtiğiniz rapor türüne bağlıdır (ayrıntılar için [Rapor türünü seçme](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) bölümüne bakın). Exchange Online PowerShell veya tek başına EOP PowerShell'deki [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet'i sonuçlardaki tüm iletileri döndürür.

## <a name="open-message-trace"></a>İleti izlemeyi açma

konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **Exchange ileti izlemesine** gidin. doğrudan ileti izleme sayfasına gitmek için kullanın <https://admin.exchange.microsoft.com/#/messagetrace>.

Bu noktada, EAC'deki ileti izleme açılır. Daha fazla bilgi için bkz. [Modern Exchange yönetim merkezinde ileti izleme](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).
