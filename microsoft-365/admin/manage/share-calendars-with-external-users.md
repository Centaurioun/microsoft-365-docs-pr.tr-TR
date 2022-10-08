---
title: Dış kullanıcılarla takvimleri paylaşma
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Kullanıcıların takvimlerini kuruluş içindeki veya dışındaki herkesle paylaşabilmesi için Microsoft 365 yönetim merkezi takvim paylaşımını etkinleştirin.
ms.openlocfilehash: 4f05db60bbbf1da70ae07e80c4828d0f7672e0d0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68206729"
---
# <a name="share-microsoft-365-calendars-with-external-users"></a>Microsoft 365 takvimlerini dış kullanıcılarla paylaşma

Bazen kullanıcılarınızın kuruluşunuzun dışındaki kişilerle toplantı zamanlaması gerekir. Microsoft 365, ortak toplantı zamanlarını bulma sürecini basitleştirmek için takvimleri bu kişilerin kullanımına açmanızı sağlar. Bunlar, kuruluşunuzdaki kullanıcılar için serbest ve meşgul zamanlarını görmesi gereken ancak Microsoft 365 kuruluşunuz için kullanıcı hesapları olmayan kişilerdir.

Microsoft 365 yönetim merkezi kuruluşunuzdaki tüm kullanıcılar için takvim paylaşımını etkinleştirebilirsiniz. Paylaşım etkinleştirildikten sonra kullanıcılarınız Outlook Web App kullanarak takvimlerini kuruluş içindeki veya dışındaki herkesle paylaşabilir. Kuruluşun içindeki Kişiler, paylaşılan takvimi kendi takvimiyle birlikte görüntüleyebilir. Kuruluşun dışındaki kişilere ise takvimi görüntülemek için kullanabilecekleri bir URL gönderilir. Kuruluşunuzdaki kullanıcılar ne zaman ve ne kadar paylaşacaklarına karar verir.

> [!NOTE]
> Takvimleri Exchange Server 2013 (şirket içi çözüm) kullanan bir kuruluşla paylaşmak istiyorsanız, Exchange yöneticisinin bulutla bir kimlik doğrulama ilişkisi ayarlaması gerekir. Bu, federasyon olarak bilinir ve en düşük yazılım gereksinimlerini karşılamalıdır. Daha fazla bilgi için bkz [. Paylaşım](/exchange/sharing-exchange-2013-help) .
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanarak takvim paylaşımını etkinleştirme

1. Yönetim merkezinde **Genel Yönetici** olarak oturum açın, **Ayarlar** \> **Kuruluş ayarları'na** gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Hizmetler** sekmesinde</a> **Takvim'i** seçin.
  
3. **Takvim** sayfasında, kullanıcıların takvimlerini kuruluşunuzun dışında Microsoft 365 veya Exchange'e sahip kişilerle paylaşmasına izin vermek isteyip istemediğinizi seçin. Anonim kullanıcıların (kimlik bilgileri olmayan kullanıcıların) takvimlere e-posta daveti aracılığıyla erişmesine izin vermek isteyip istemediğinizi seçin.

4. Kullanıcıların kullanımına sunulabilecek takvim bilgilerinin türünü seçin. Tüm bilgilere izin verebilir veya yalnızca zamana veya zamana, konuya ve konuma sınırlayabilirsiniz.

## <a name="external-sharing-sync-interval"></a>Dış paylaşım eşitleme aralığı

Kiracınızın dışında paylaşım için anlık eşitleme şu anda desteklenmiyor. Bu yapılandırmalarda paylaşabilirsiniz ancak eşitleme düzenli aralıklarla gerçekleşir. İki tür kiracılar arası paylaşım vardır:

1. **Microsoft 365'i başka bir Microsoft 365 kullanıcısına (dış paylaşım etkinse)**: Tamamen paylaşılan bir takvim oluşturulur, ancak eşitleme yaklaşık olarak üç saatte bir gerçekleşir. Bu kurulum için anında eşitleme sonunda etkinleştirilecektir.

2. **Outlook.com bir kullanıcıya Microsoft 365**: Dış paylaşım devre dışı bırakılırsa, başka bir Microsoft 365 kullanıcısına paylaşım da bu gruba girer. Paylaşım sırasında, alıcının herhangi bir takvim hizmetine eklemek için kullanabileceği bir ICS URL'si oluşturulur. ICS aboneliğiyle, alıcının takvim hizmeti yeni güncelleştirmeleri almak için ICS aboneliğinin ne zaman eşitlenmesini seçer. Alıcı bir Outlook.com veya Microsoft 365 kullanıcısıysa, eşitleme yaklaşık üç saatte bir gerçekleşir.

## <a name="invite-people-to-access-calendars"></a>Kişileri takvimlere erişmeleri için davet etme

Paylaşım etkinleştirildikten sonra, takvim sahipleri davetleri belirli kullanıcılara genişletebilir.

1. [Web üzerinde Outlook'u](https://outlook.office365.com) açın.

2. Sayfanın üst kısmında uygulama başlatıcıyı ve **ardından Takvim'i** seçin. Varsayılan olarak, birincil takviminiz "Takvim" olarak adlandırılır. Başka takvimler oluşturduysanız, paylaşmak üzere bunlardan birini seçebilirsiniz. Başkalarının sahip olduğu takvimleri paylaşamazsınız.

3. E-postada **paylaşım daveti gönder** kutusuna takviminizi paylaşmak istediğiniz kişinin adını veya e-posta adresini girin.

4. Bu kişinin ne kadar bilgi görmesini istediğinizi seçin:

     - **Meşgul olduğum zamanları görüntüleyebilir** , kişinin ne zaman meşgul olduğunuzu görmesine izin verir ancak olay konumu gibi ayrıntıları içermez.

     - **Başlıkları ve konumları görüntüleyebilir** , kişinin meşgul olduğunuz zamanları ve etkinliklerin başlığını ve konumunu görmesine olanak tanır.

     - **Tüm ayrıntıları görüntüleyebilir** , kişinin etkinliklerinizin tüm ayrıntılarını görmesine olanak tanır.

     - **Düzenleyebilir özelliği** , kişinin etkinliklerinizin tüm ayrıntılarını görmesine ve takviminizi düzenlemesine olanak tanır (yalnızca kuruluşunuzdaki kişilerle paylaşırken kullanılabilir).

5. **Paylaş'ı** seçin. 

## <a name="related-content"></a>İlgili içerik

[Site için dış paylaşımı açma veya kapatma](/sharepoint/change-external-sharing-site) (makale)\
[Microsoft 365 yönetim merkezi genel bakış](../admin-overview/admin-center-overview.md) (video)\
[E-posta ve takvimleri yönetme](/admin) (bağlantı sayfası)

