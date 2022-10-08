---
title: Posta akışı panosunda posta akışı içgörüleri
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.collection: m365-security
ms.localizationpriority: medium
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Yöneticiler, Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosunda bulunan içgörüler ve raporlar hakkında bilgi edinebilir.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: bf5f71388683087260c37a719219e87205a4ec47
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091839"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Güvenlik ve Uyumluluk Merkezi'ndeki posta akışı içgörüleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Yöneticiler eğilimleri, içgörüleri keşfetmek ve kuruluşlarındaki posta akışıyla ilgili sorunları gidermek için eylemlerde bulunabilmek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosunu kullanabilir.

:::image type="content" source="../../media/mail-flow-dashboard-v2.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosu" lightbox="../../media/mail-flow-dashboard-v2.png":::

Kullanılabilir içgörüler şunlardır:

- [Otomatik iletilen iletiler içgörüsü](mfi-auto-forwarded-messages-report.md)
- [Olası posta döngüsü içgörülerini düzeltme](mfi-mail-loop-insight.md)<sup>1</sup>
- [Yavaş posta akışı kurallarını düzeltme içgörü](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>
- [Posta akışı haritası](mfi-mail-flow-map-report.md)
- [İletilen yeni etki alanları e-posta içgörüleri](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>
- [E-posta iletmeye yönelik yeni kullanıcılar içgörüleri](mfi-new-users-forwarding-email.md)<sup>2</sup>
- [Kabul edilmeyen etki alanı raporu](mfi-non-accepted-domain-report.md)
- [Teslim edilemedi raporu](mfi-non-delivery-report.md)
- [Giden ve gelen posta akışı içgörüsü](mfi-outbound-and-inbound-mail-flow.md)
- [Kuyrukların içgörüsü](mfi-queue-alerts-and-queues.md)
- [SMTP Kimlik Doğrulaması istemcileri içgörüleri ve raporu](mfi-smtp-auth-clients-report.md)
- [En iyi etki alanı posta akışı durumu içgörüsü](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Bu içgörü, Posta akışı panosunun **Sizin için önerilen** alanında yalnızca sorun algılandıktan sonra görünür. Aksi takdirde göremezsiniz.

<sup>2</sup> Bu içgörü Posta akışı panosunda görünmez, ancak sorun algılandıktan sonra [rapor](view-mail-flow-reports.md#forwarding-report) iletme sayfasında görünür. Aksi takdirde göremezsiniz.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Posta akışı panosunu görüntülemek için gereken izinler

Posta akışı panosu aşağıdaki rol gruplarının üyeleri tarafından kullanılabilir:

- Güvenlik & Uyumluluk Merkezi'nde **Kuruluş Yönetimi** (genel yöneticiler).

- Azure Active Directory'de **[Exchange Yöneticisi](/azure/active-directory/roles/permissions-reference#exchange-administrator)**.

- Güvenlik & Uyumluluk Merkezi'nde **MailFlow Yöneticisi**. Hesap aynı zamanda Kuruluş Yönetimi veya Exchange Yöneticisi rol gruplarının üyesi değilse aşağıdaki sorunları göz önünde bulundurun:
  - Kullanıcının doğrudan adresinde Güvenlik & Uyumluluk Merkezi'nde oturum açması <https://protection.office.com>gerekir.
  - Kullanıcının Posta akışı panosu üzerinde yalnızca salt okunur izni olur.
  - Kullanıcının Microsoft 365 yönetim merkezi erişimi olmaz.

İzinler hakkında daha fazla bilgi için bkz [. Güvenlik & Uyumluluk Merkezi'nde İzinler](permissions-in-the-security-and-compliance-center.md) ve [Kullanıcılara Güvenlik & Uyumluluk Merkezi'ne erişim verme](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Posta akışı panosu nerede bulunur?

Doğrudan Posta akışı panosuna gitmek için dosyasını açın <https://protection.office.com/mailflow/dashboard>.
