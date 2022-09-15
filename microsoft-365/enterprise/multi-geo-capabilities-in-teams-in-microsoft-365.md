---
title: Microsoft Teams'de Multi-Geo Özellikleri
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
description: Teams'in Microsoft 365 Multi-Geo ile nasıl çalıştığı hakkında bilgi edinin.
ms.openlocfilehash: 9b00b36fb56259361c2cdf8ee1b7cd020923e7d8
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698341"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Microsoft Teams'deki Multi-Geo özellikleri

Teams'deki Multi-Geo özellikleri, Teams sohbet verilerinin belirtilen coğrafi konumda bekleyen konumda depolanmasını sağlar. Sohbet verileri özel iletiler, kanal iletileri ve sohbetlerde kullanılan görüntüler de dahil olmak üzere sohbet iletilerinden oluşur.

Teams, verilerin nerede depoleneceğini belirlemek için kullanıcılar ve gruplar için Tercih Edilen Veri Konumu'nı (PDL) kullanır. PDL ayarlanmadıysa veya geçersizse veriler kiracının merkezi konumunda depolanır.

> [!NOTE]
> Teams'deki Multi-Geo özellikleri Temmuz 2021'de kullanıma sunulmaya devam etti. Sohbetiniz ve kanal iletileriniz önümüzdeki birkaç çeyrekte otomatik olarak doğru coğrafi konuma geçirilecektir. Tüm yeni PDL değişiklikleri, kiracı ilk eşitlemeyi tamamladıktan sonra işlenir ve bunun ötesindeki yeni PDL değişiklikleri alındıkları sırayla kuyruğa alınır ve işlenir.

## <a name="user-chat"></a>Kullanıcı sohbeti

Kullanıcı sohbeti bire bir, bire çok ve özel toplantı iletileri içerir.

Yeni bir kullanıcı oluşturulduğunda, Teams kullanıcının PDL'sini okur ve tüm sohbet verilerini bu coğrafi konumda depolar.

Mevcut kullanıcılar için, bir yönetici bir kullanıcının PDL'sini ekler veya değiştirirse, o kullanıcının sohbet verileri belirtilen coğrafi konuma taşınacak bir geçiş kuyruğuna eklenir.

Bire bir veya bire çok sohbetin depolama konumu, sohbeti oluşturan kişinin PDL'sini temel alır. Kullanıcının PDL'i değiştirilirse sohbet yeni coğrafi konuma geçirilir. Toplantı sohbetinin depolama konumu, toplantı düzenleyicisinin PDL'sini temel alır.

Kullanıcının Teams verilerinin geçerli konumunu bulmak [için Teams PowerShell'e bağlanın](/powershell/module/teams/connect-microsoftteams) ve aşağıdaki komutu çalıştırın:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Kanal iletileri

Her Microsoft 365 grubunun, ilgili verilerin depolandığı coğrafi konumu gösteren Tercih Edilen Veri Konumu (PDL) vardır. Ekipler, ekip için kanal mesajlaşma verilerinin depolandığı yeri belirlemek için her ekiple ilişkili grup için PDL'yi kullanır. Bu, bir kanal toplantısında gerçekleşen özel kanalları ve sohbeti içerir.

Kullanıcı yeni bir ekip oluşturduğunda, bu kullanıcının PDL'i Microsoft 365 grubuna hangi PDL'nin atandığını belirler. Grup PDL' i, ekibin verilerinin nerede depolandığını belirler. Bu kullanıcının PDL'i daha sonra değişirse, grubun PDL'i değiştirilmez.

Mevcut ekipler için, bir yönetici bir ekibi destekleyen Microsoft 365 grubunun PDL'sini ekler veya değiştirirse, bu ekibin kanal mesajlaşma verileri belirtilen coğrafi konuma taşınacak bir geçiş kuyruğuna eklenir.

Microsoft 365 grubunun PDL'sini değiştirmek, Teams verilerini seçilen konuma geçirmek için kuyruğa alır. Ancak bu, SharePoint sitesini veya Grupla ilişkili dosyaları otomatik olarak geçirmez. [SharePoint sitesini farklı bir coğrafi konuma taşıma'daki](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) yordamları izleyerek siteyi ayrı olarak taşımanız gerekir. Farklı konumlardaki bir grup için Teams verilerini ve SharePoint verilerini önlemek için her iki adımı da uyguladığından emin olun.

Ekip verilerinin geçerli konumunu bulmak için [Teams PowerShell'e bağlanın](/powershell/module/teams/connect-microsoftteams) ve aşağıdaki komutu çalıştırın:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Kullanıcı Deneyimi

Teams Multi-Geo, son kullanıcıya sorunsuz bir şekilde sağlanır. Bir kullanıcının veya grubun PDL'sini değiştirdiğinizde, ilgili veriler geçiş için kuyruğa alır ve geçiş gerçekleşirken etkin olsalar bile kullanıcı veya Teams istemcisini etkilemeden geçiş otomatik olarak gerçekleşir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Multi-Geo kiracı yapılandırması](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Multi-Geo ortamı yönetme](administering-a-multi-geo-environment.md)

[Çok coğrafi bir ortamda Exchange Online posta kutularını yönetme](administering-exchange-online-multi-geo.md)
