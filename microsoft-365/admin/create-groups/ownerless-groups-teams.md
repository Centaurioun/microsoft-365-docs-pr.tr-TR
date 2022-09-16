---
title: Sahipsiz Microsoft 365 gruplarını ve ekiplerini yönetme
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
description: Sahipsiz bir Microsoft 365 grubunda veya Microsoft Teams'de bir ekipte sahip olmaya üyeleri otomatik olarak davet etmeyi öğrenin.
ms.openlocfilehash: 3d140c7080feca76382e54049918d5e7866e29d5
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67743098"
---
# <a name="manage-ownerless-microsoft-365-groups-and-teams"></a>Sahipsiz Microsoft 365 gruplarını ve ekiplerini yönetme

Microsoft Teams'deki bir ekip veya Bir Microsoft 365 grubu ve ilgili hizmetleri, Microsoft 365'te bir sahibin hesabı silinir veya devre dışı bırakılırsa sahipsiz hale gelebilir. Gruplar ve ekipler, bir sahibin üye eklemesini veya kaldırmasını ve grup ayarlarını değiştirmesini gerektirir.

Genel Yönetici, Exchange Yöneticisi veya Grup Yöneticisi sahipsiz bir grubun veya ekibin en etkin üyelerine sahipliği kabul etmelerini otomatik olarak soran bir ilke oluşturabilir. Bir üye sahip olma davetini kabul ettiğinde, eylem uyumluluk portalı denetim günlüğüne kaydedilir. Konuklar hiçbir zaman sahip olmaya davet edilmemektedir.

İlkeyi oluştururken şunları belirtebilirsiniz:
- Güvenlik grubu belirterek kimlerin sahip olmaya davet edilebileceğini sınırlamak istiyorsanız
- Bildirimlerin gönderen adresi
- Bildirimlerin gönderileceği hafta sayısı
- İlkenin parçası olan gruplar veya ekipler

> [!Note]
> Kimlerin sahip olmaya davet edilebileceğini sınırlamak için bir güvenlik grubu kullanmak, kuruluşunuzdaki her Microsoft 365 grup üyesi için bir Azure AD Premium lisansına sahip olmanız gerekir ancak bu lisansa sahip olmanız gerekmez.

Sahipsiz grup veya ekip ilkesi ayarlamak için

1. Yönetim merkezinde Tüm \> **Ayarlar** \> **Kuruluş ayarlarını** **göster'e** gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Hizmetler** sekmesinde</a> **Microsoft 365 Grupları'yi** seçin.

1. **Sahip olmadığında, e-posta gönderin ve etkin grup üyelerinden sahip olmasını isteyin** onay kutusunu seçin.

1. Varsayılan yapılandırma ayarlarını korumak istiyorsanız **Kaydet'i** seçin, aksi takdirde **İlkeyi yapılandır'ı** seçin ve aşağıdaki adımları tamamlayın.

1. *Haftalık bildirim seçenekleri* sayfasında, sahiplik bildirimlerini kimlerin alabileceğini belirtin. Belirli üyelere izin vermeyi veya bunları engellemeyi seçerseniz, kullanmak istediğiniz güvenlik grubunu arayın ve ekleyin.

1. Bildirmek istediğiniz etkin üye sayısını yazın ve bildirimi göndermek için hafta sayısını seçin. (Bildirim listesi ilk bildirim sırasında oluşturulur ve değişmez.) **İleri'yi** seçin.

1. *Bu e-posta kimden geliyor sayfasında, e-posta* için bir gönderen seçin ve ardından **İleri'yi** seçin. Paylaşılan posta kutularının desteklenmediğini unutmayın. Gönderen bir kullanıcı posta kutusu veya grup posta kutusu olmalıdır.

1. *Konu ve ileti* sayfasında, e-postayı özelleştirin ve isteğe bağlı olarak bir **ilke kılavuzu URL'si** ekleyin ve **ardından İleri'yi** seçin.

1. *Hedeflenen grupları seçin* sayfasında **Belirli gruplar'ı** seçin ve bu ilkeye eklemek istediğiniz grupları ve ekipleri seçin veya **Tüm gruplar'ı** seçin.

1. **İleri**'yi seçin.

1. *Gözden geçir ve bitir* sayfasında ayarlarınızı onaylayın ve **Son'a** tıklayın ve ardından **Bitti'yi** seçin.

Bildirimler, ilke oluşturulduktan sonraki 24 saat içinde haftalık olarak gönderilir. Alıcılar bildirimleri başkalarına iletemez. Bildirimler ve yanıtlar denetim günlüğünde izlenir.

Grup başına en fazla iki grup üyesi, sahip olma davetini kabul edebilir. Hiçbir grup üyesi kabul etmediyse, yöneticinin [bir grup sahibi ataması](/admin/create-groups/add-or-remove-members-from-groups) gerekir.


