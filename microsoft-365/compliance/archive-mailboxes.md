---
title: Microsoft Purview için arşiv posta kutuları hakkında bilgi edinin
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Ek posta kutusu depolama alanı sağlamak için posta kutularını arşivle hakkında bilgi edinin.
ms.openlocfilehash: 38635b5f640ae14a2b9294cf11d22a41bce71b1f
ms.sourcegitcommit: 6f36cb8c69090c62a006d461bfc5aa1139cf09a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67631329"
---
# <a name="learn-about-archive-mailboxes"></a>Arşiv posta kutuları hakkında daha fazla bilgi edinme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft Purview'da posta kutusu arşivleme bazen *Yerinde Arşivleme* olarak da adlandırılır ve kullanıcılara fazladan posta kutusu depolama alanı sağlar. Arşiv posta kutularını açtıktan sonra, kullanıcının geçerli posta kutusu *birincil posta kutusu* olur ve arşiv posta kutusu olarak adlandırılan ek bir *posta kutusu* oluşturulur. her iki posta kutusu da Microsoft Purview uyumluluk portalı İçerik araması, Microsoft 365 saklama ve Dava Tutma gibi uyumluluk özellikleri için kullanıcının posta kutusu olarak kabul edilir.

Kullanıcılar Outlook ve Web üzerinde Outlook kullanarak arşiv posta kutularındaki iletilere erişebilir ve iletileri depolayabilir. Kullanıcılar ayrıca iletileri birincil posta kutularıyla arşiv posta kutuları arasında taşıyabilir veya kopyalayabilir. Ayrıca Silinmiş Öğeleri Kurtar aracını kullanarak, silinmiş öğeleri arşiv posta kutularındaki Kurtarılabilir Öğeler klasöründen de kurtarabilirler.

## <a name="managing-archive-mailboxes-with-messaging-records-management-mrm"></a>Arşiv posta kutularını mesajlaşma kayıtları yönetimi (MRM) ile yönetme

İletiler, mesajlaşma kayıtları yönetiminden (MRM) [varsayılan Exchange bekletme ilkesi](/exchange/security-and-compliance/messaging-records-management/default-retention-policy) tarafından arşiv posta kutusuna da taşınabilir. Bu varsayılan ilke her posta kutusuna otomatik olarak atanır ve aşağıdakileri yapar:

  - kullanıcının birincil posta kutusundan iki yaş veya daha eski öğeleri arşiv posta kutusuna taşır.

  - Kullanıcının birincil posta kutusunda bulunan Kurtarılabilir Öğeler klasöründen 14 gün veya daha eski öğeleri arşiv posta kutularındaki Kurtarılabilir Öğeler klasörüne taşır.

Kuruluşunuzun MRM ilkesini [bekletme etiketleriyle](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) özelleştirebilirsiniz. Örnek yapılandırma için bkz. [Kuruluşunuzdaki posta kutuları için arşiv ve silme ilkesi ayarlama](set-up-an-archive-and-deletion-policy-for-mailboxes.md).

> [!NOTE]
> Microsoft 365 bekletme ilkeleri ve bekletme etiketleri gibi MRM de belirli bir süre sonra e-postaları otomatik olarak silebilir. Microsoft 365 saklamadan daha eski bir teknoloji olan MRM, Microsoft Purview'un bekletme ilkeleri ve bekletme etiketleriyle yan yana çalışmaya devam eder. Daha fazla bilgi için bkz. [Eski özellikler yerine bekletme ilkelerini ve bekletme etiketlerini kullanma](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features).

## <a name="auto-expanding-archiving"></a>Arşivlemeyi otomatik olarak genişletme 

Kullanıcının arşiv posta kutusu etkinleştirildikten sonra 100 GB'a kadar ek depolama alanı kullanılabilir. Kullanıcıların daha fazla depolama alanına ihtiyacı varsa arşiv posta kutularında 1,5 TB'a kadar ek depolama alanı sağlamak için otomatik genişletme arşivlemeyi etkinleştirin. Daha fazla bilgi için bkz. [Arşivlemeyi otomatik olarak genişletme hakkında bilgi edinin](autoexpanding-archiving.md).

## <a name="next-steps"></a>Sonraki adımlar

Bkz [. Microsoft 365'te arşiv posta kutularını etkinleştirme](enable-archive-mailboxes.md).
