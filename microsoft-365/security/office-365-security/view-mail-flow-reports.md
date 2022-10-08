---
title: Raporlar panosunda posta akışı raporlarını görüntüleme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- m365-security
description: Yöneticiler, Güvenlik & Uyumluluk Merkezi'ndeki Raporlar panosunda bulunan posta akışı raporları hakkında bilgi edinebilir.
ms.custom: ''
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 81555650f71692864dc00abad9c65df883cf9955
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048516"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'ndeki Raporlar panosunda posta akışı raporlarını görüntüleme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Bu makaledeki raporların çoğu Microsoft 365 Defender portalında veya Exchange yönetim merkezinde (EAC) de kullanılabilir. Daha fazla bilgi için, aşağıdaki konulara bakın:
>
> - [Yeni Exchange yönetim merkezinde posta akışı raporları](/exchange/monitoring/mail-flow-reports/mail-flow-reports)
> - [Microsoft 365 Defender portalında e-posta güvenlik raporlarını görüntüleme](view-email-security-reports.md)

Güvenlik & Uyumluluk Merkezi'ndeki [Posta akışı panosunda](mail-flow-insights-v2.md) bulunan posta akışı raporlarına ek olarak, Microsoft 365 kuruluşunuzu izlemenize yardımcı olmak için Raporlar panosunda çeşitli ek posta akışı raporları bulunur.

[Gerekli izinlere](#what-permissions-are-needed-to-view-these-reports) sahipseniz, Bu raporları Güvenlik & Uyumluluk Merkezi'nde **Raporlar** \> **Panosu'na**<https://protection.office.com> giderek görüntüleyebilirsiniz. Doğrudan Raporlar panosuna gitmek için öğesini açın <https://protection.office.com/insightdashboard>.

:::image type="content" source="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Raporlar panosu" lightbox="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png":::

## <a name="connector-report"></a>Bağlayıcı raporu

> [!NOTE]
> Bu raporun yerini **Gelen iletiler raporu** ve EAC'deki **Giden iletiler raporu** almıştır. Daha fazla bilgi için bkz [. Yeni EAC'de gelen iletiler ve Giden iletiler raporları](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports).

## <a name="exchange-transport-rule-report"></a>Exchange aktarım kuralı raporu

**Exchange aktarım kuralı raporu**, posta akışı kurallarının (taşıma kuralları olarak da bilinir) kuruluşunuzdaki gelen ve giden iletiler üzerindeki etkisini gösterir.

Raporu görüntülemek için adresinde Güvenlik & Uyumluluk Merkezi'ni <https://protection.office.com>açın, **Raporlar** \> **Panosu'na** gidin ve **Exchange Aktarım kuralı'nı** seçin. Doğrudan rapora gitmek için dosyasını açın <https://security.microsoft.com/reports/ETRRuleReport>.

:::image type="content" source="../../media/scc-transport-rule-report-widget.png" alt-text="Raporlar panosundaki Exchange aktarım kuralı pencere öğesi" lightbox="../../media/scc-transport-rule-report-widget.png":::

> [!NOTE]
> **Exchange aktarım kuralı raporu** artık EAC'de kullanılabilir. Daha fazla bilgi için bkz. [Yeni EAC'de Exchange aktarım kuralı raporu](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report).

## <a name="forwarding-report"></a>Raporu iletme

> [!NOTE]
> **İletme raporu** artık EAC'de kullanılabilir. Daha fazla bilgi için bkz. [Yeni EAC'de otomatik iletilen iletiler raporu](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).

## <a name="mailflow-status-report"></a>Posta akışı durum raporu

**Posta akışı durum raporu**, [gönderilen ve alınan e-posta raporuna](#sent-and-received-email-report) benzer ve kenarda izin verilen veya engellenen e-postalar hakkında ek bilgiler bulunur. Bu, uç koruma bilgilerini içeren tek rapordur ve hizmete Exchange Online Protection (EOP) tarafından değerlendirilmek üzere izin verilmeden önce ne kadar e-postanın engellendiğini gösterir. Bir ileti beş alıcıya gönderiliyorsa bunu bir ileti değil beş farklı ileti olarak saymamızı anlamak önemlidir.

Raporu görüntülemek için [Güvenlik & Uyumluluk Merkezi'ni](https://protection.office.com) açın, **Raporlar** \> **Panosu'na** gidin ve **Posta akışı durum raporu'nu** seçin. Doğrudan **Posta akışı durum raporuna** gitmek için dosyasını açın <https://security.microsoft.com/reports/mailflowStatusReport>.

:::image type="content" source="../../media/scc-mail-flow-status-report-widget.png" alt-text="Raporlar panosundaki Posta akışı durum raporu pencere öğesi" lightbox="../../media/scc-mail-flow-status-report-widget.png":::

> [!NOTE]
> Güvenlik & Uyumluluk Merkezi'nde (protection.office.com) bu raporun pencere öğesine tıkladığınızda artık Microsoft 365 Defender portalındaki (security.microsoft.com) raporun tamamına yönlendirilirsiniz. Raporla ilgili ayrıntılar için bkz. [Posta akışı durum raporu](view-email-security-reports.md#mailflow-status-report).

## <a name="sent-and-received-email-report"></a>Gönderilen ve alınan e-posta raporu

> [!NOTE]
> Bu raporun yerini [Posta akışı durum raporu](#mailflow-status-report) almıştır.

## <a name="top-senders-and-recipients-report"></a>En çok gönderenler ve alıcılar raporu

**En çok gönderenler ve alıcılar**, kuruluşunuzdaki en çok gönderenlerin yanı sıra EOP ve Office 365 için Defender koruma özellikleri tarafından algılanan iletiler için en çok kullanılan alıcıları gösterir.

Raporu görüntülemek için adresinde Güvenlik & Uyumluluk Merkezi'ni <https://protection.office.com>açın, **Raporlar** \> **Panosu'na** gidin ve **En çok gönderenler ve alıcılar'ı** seçin. Doğrudan rapora gitmek için aşağıdaki URL'lerden birini açın:

- Office 365 için Defender:<https://protection.office.com/TopSenderRecipientsATP>
- EOP: <https://protection.office.com/TopSenderRecipients>

:::image type="content" source="../../media/scc-top-senders-and-recipients-widget.png" alt-text="Raporlar panosundaki En çok gönderenler ve alıcılar pencere öğesi" lightbox="../../media/scc-top-senders-and-recipients-widget.png":::

> [!NOTE]
> Güvenlik & Uyumluluk Merkezi'nde bu raporun pencere öğesine tıklanması sizi protection.office.com bir sayfaya götürür ancak sayfa içeriği Microsoft 365 Defender portalındandır. Raporla ilgili ayrıntılar için bkz [. En çok gönderenler ve alıcılar raporu](view-email-security-reports.md#top-senders-and-recipients-report).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Bu raporları görüntülemek için hangi izinler gerekiyor?

Bu makalede açıklanan raporları görüntülemek ve kullanmak için Güvenlik & Uyumluluk Merkezi'nde aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:

- **Kuruluş Yönetimi**
- **Güvenlik Yöneticisi**
- **Güvenlik Okuyucusu**
- **Genel Okuyucu**

Daha fazla bilgi için bkz [. Güvenlik & Uyumluluk Merkezi'ndeki İzinler](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> kullanıcıları Microsoft 365 yönetim merkezi karşılık gelen Azure Active Directory rolüne eklemek, kullanıcılara Güvenlik & Uyumluluk Merkezi'nde gerekli izinleri _ve_ Microsoft 365'teki diğer özellikler için izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).

