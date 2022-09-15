---
title: Microsoft 365 grupları ve Microsoft Teams için kuruluş ve yaşam döngüsü idaresini planlama
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365'te işbirliği araçları için yaşam döngüsü idare seçenekleri hakkında bilgi edin
ms.openlocfilehash: 0b4ca2da65736d703f1a33df7e43e7488dd6dd0e
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727204"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 grupları ve Microsoft Teams için kuruluş ve yaşam döngüsü idaresini planlama

Microsoft 365 grupları, kuruluşunuzun gerektirdiği idare özelliklerini uygulamak için zengin bir araç kümesine sahiptir. 

Aşağıdaki bölümde özellikler açıklanır, en iyi yöntemler önerilir ve idare gereksinimlerini ve bunların nasıl karşıleneceğini belirlemek için doğru soruları sormak için rehberlik sağlanır.

## <a name="control-who-can-create-microsoft-365-groups"></a>Microsoft 365 gruplarını kimlerin oluşturabileceğini denetleme

Gruplar son kullanıcılar tarafından Outlook, SharePoint, Teams ve diğer ortamlar da dahil olmak üzere birden çok son noktadan oluşturulabilir.

![görüntü desc.](../media/04.png)

Grup sahiplerini güçlendirmek ve kullanıcıların işlerini daha kolay yapmalarına yardımcı olmak için self servis kullanmanızı kesinlikle öneririz. Birçok Microsoft 365 hizmeti hizmetin çalışması için grupların oluşturulmasını gerektirdiğinden, grup ve ekip oluşturmayı sınırlamak kullanıcıların üretkenliğini yavaşlatabilir.

Grup oluşturma için aşağıdaki idare seçeneklerini göz önünde bulundurun:

- Grup yayılmasını sınırlamak için, kullanılmayan grupları otomatik olarak silmek için [grupların süre sonu ilkelerini](microsoft-365-groups-expiration-policy.md) kullanın.
- Grup oluşturmayı, tüm tam zamanlı çalışanlar gibi [dinamik üyeliği olan bir güvenlik grubunun üyeleriyle](/azure/active-directory/users-groups-roles/groups-create-rule) sınırlayın.
- Grup oluşturmayı bir güvenlik grubuyla sınırlayın ve kullanıcıların güvenlik grubuna üye olmak için kuruluşunuzun grup kullanım ilkelerindeki eğitimi tamamlamasını zorunlu kılar.

Kimlerin grup oluşturabileceğini sınırlamak istiyorsanız, bunu yapılandırma hakkında bilgi için bkz. [Microsoft 365 gruplarını kimlerin oluşturabileceğini yönetme](manage-creation-of-groups.md) .

## <a name="group-delete-restore-and-archiving"></a>Grup silme, geri yükleme ve arşivleme

Bir Microsoft 365 grubu silindiğinde, varsayılan olarak 30 gün boyunca korunur. Bu 30 günlük süre "geçici silme" olarak adlandırılır, çünkü grubu hala geri yükleyebilirsiniz. 30 gün sonra, grup ve onunla ilişkilendirilmiş içerik kalıcı olarak silinir ve geri yüklenemez.

Sohbeti, dosyaları veya postayı korumak için bekletme ilkeleriniz varsa, grup silindikten sonra bu öğeler korunur. Ayrıntılar için bkz [. Bekletme ilkeleri hakkında bilgi edinin](../compliance/retention.md) .

Bir grubu silmek ancak gruba bağlı bir veya daha fazla hizmetten içeriği korumak istiyorsanız, bilgi için [bkz. Grupları, ekipleri ve Yammer'ı arşivleyin](end-life-cycle-groups-teams-sites-yammer.md) .

## <a name="group-naming-policy"></a>Grup adlandırma ilkesi

Grupları adlandırma ilkesi, grupları iki şekilde yönetmenize yardımcı olabilir:

- Bir ön ek/sonek adlandırma ilkesi, bir grup adının başında veya sonunda sabit dizeleri veya Azure AD özniteliklerini ve ilişkili e-posta adresini zorunlu kılmak için kullanılabilir. Bunu yaparak, bölüm adlarının veya bölgelerin grup adlarında eklenmesini sağlayabilirsiniz.
- Engellenen sözcükler ilkesi, yöneticilerin adları gibi belirli sözcüklerin grup adlarında kullanılmamasını sağlayabilir.

Adlandırma ilkeleri, grup bağlantılı hizmetlerden herhangi birinden gruplar oluşturulduğunda uygulanır.

Gruplar için adlandırma ilkeleri kullanmaya karar verirseniz bkz. [adlandırma ilkesi Microsoft 365 Grupları](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Grup süre sonu ilkesi

Bir süre sonu belirtebilirsiniz ve bu sürenin sonuna ulaşan ve yenilenmeyen tüm gruplar silinir. Süre sonu, grup oluşturulduğunda veya son yenilendiği tarihte başlar.

Grupların süresinin dolmasına ayarladıktan sonra:
- Süre sonu yaklaştığında grubun sahiplerine grubu yenilemeleri bildirilir.
- Etkin gruplar otomatik olarak yenilenir.
- Yenilenmeyen tüm gruplar silinir.
- Silinen tüm gruplar, grup sahipleri veya yönetici tarafından 30 gün içinde geri yüklenebilir.

Süre sonu ilkeleri, artık kullanımda olmayan grupların silindiğinden emin olarak grup yayılmasını sınırlamanın iyi bir yoludur. Grup süre sonu ilkesi oluşturmak istiyorsanız bkz. [Microsoft 365 Grupları Süre Sonu İlkesi](microsoft-365-groups-expiration-policy.md).

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Eski bir çalışanı kaldırın ve verileri güvenli hale getirin](/microsoft-365/admin/add-users/remove-former-employee)
