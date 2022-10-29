---
title: Bilinen Blue Yonder sorunları için Teams Shifts bağlayıcısı
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: troubleshooting
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Vardiyaları Blue Yonder Workforce Management ile tümleştirmek için Mavi Yonder için Team Shifts bağlayıcısını kullanırken karşılaşılan bilinen sorunları listeler.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: dd53e2075dfd87cde5bd303e6bb61b992f54af7f
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785935"
---
# <a name="known-issues-teams-shifts-connector-for-blue-yonder"></a>Bilinen sorunlar: Blue Yonder için Teams Vardiyaları bağlayıcısı

Bu makalede [, Mavi Yonder için Microsoft Teams Vardiyaları bağlayıcısının](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) bilinen sorunları listelenmiştir.

## <a name="you-can-map-an-instance-to-more-than-one-team-using-powershell-or-microsoft-graph"></a>PowerShell veya Microsoft Graph kullanarak bir örneği birden fazla ekiple eşleyebilirsiniz

Mavi Yonder Workforce Management örneği, bir bağlantıda belirli bir anda yalnızca bir ekiple eşlenmelidir.

Bununla birlikte, bağlantı kurmak için PowerShell veya Microsoft Graph kullandığınızda, bir örneği birden fazla ekiple eşlemek mümkündür. Eşitleme sorunlarına ve beklenmeyen davranışlara neden olabileceğinden bir örneği birden çok ekiple eşlemekten kaçınmanızı öneririz.

## <a name="related-articles"></a>İlgili makaleler

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Shifts bağlayıcısı sihirbazını kullanarak Shifts'i Mavi Yonder'a bağlama Workforce Management](shifts-connector-wizard.md)
- [PowerShell kullanarak Vardiyaları Mavi Yonder'a bağlama Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Microsoft 365 yönetim merkezi kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management](shifts-connector-blue-yonder-admin-center-manage.md)
- [PowerShell kullanarak Blue Yonder ile Vardiyalar bağlantınızı yönetme Workforce Management](shifts-connector-powershell-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
