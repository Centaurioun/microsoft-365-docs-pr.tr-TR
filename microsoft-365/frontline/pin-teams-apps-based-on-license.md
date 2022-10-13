---
title: Teams uygulamalarını ön saf çalışanları için uyarlama
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Microsoft Teams'de ön cephe çalışanları için uyarlanmış uygulama deneyimi hakkında bilgi edinin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: debc8a975d132c83183fce4a4f0d4f6905dcbb40
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565990"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Teams uygulamalarını ön saf çalışanları için uyarlama

## <a name="overview"></a>Genel bakış

Teams, uygulamaları lisansa göre sabitler ve ön saha çalışanlarınıza Teams'de ihtiyaçlarına göre uyarlanmış kullanıma hazır bir deneyim sunar. 

Özel olarak uyarlanmış ön cephe uygulaması deneyimi sayesinde ön cephe çalışanlarınız, yöneticiden herhangi bir eyleme gerek kalmadan Teams'deki en ilgili uygulamaları alır.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>Özel ön cephe uygulama deneyimi

Uygulamalar, Teams mobil istemcilerinin (iOS ve Android) altındaki ve Teams masaüstü istemcisinin yanındaki çubuk olan uygulama çubuğuna sabitlenir. [F lisansı](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) olan kullanıcılar için aşağıdaki uygulamalar sabitlenmiştir:

- [Viva Bağlantılar](https://support.microsoft.com/office/your-intranet-is-now-in-microsoft-teams-8b4e7f76-f305-49a9-b6d2-09378476f95b) ([çok yakında](#coming-soon))
- [Etkinlik](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Sohbet](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Takım](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Görevler](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Vardiya](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Onaylar](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams mobil**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Teams mobilde uyarlanmış ön hat uygulama deneyimi" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams masaüstü**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Teams masaüstünde uyarlanmış ön cephe uygulaması deneyimi" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>denetimleri Yönetici

> [!NOTE]
> Bu özelliğin geçerli olması için genel (kuruluş genelinde varsayılan) [uygulama kurulum ilkesinde](/microsoftteams/teams-app-setup-policies) **Kullanıcı sabitleme** ayarının açık olması gerekir.

Uyarlanmış ön hat uygulama deneyimi, Teams yönetim merkezinin Uygulamaları [yönet](/microsoftteams/manage-apps#manage-org-wide-app-settings) sayfasındaki **Uyarlanmış uygulamaları göster** kuruluş genelinde uygulama ayarı tarafından denetleniyor. Özellik açıksa, kuruluşunuzda F lisansı olan tüm kullanıcılar uyarlanmış uygulama deneyimine sahip olur.

Kullanıcılara atanan özel [uygulama kurulum ilkelerinin](/microsoftteams/teams-app-setup-policies) öncelikli olduğunu unutmayın. Bu, kullanıcının kendisine atanmış bir özel uygulama kurulum ilkesi varsa, kullanıcının özel uygulama kurulum ilkesinde tanımlanan yapılandırmayı aldığı anlamına gelir. Özelliğin, genel uygulama kurulum ilkesi de dahil olmak üzere Teams uygulama ilkeleriyle nasıl çalıştığı hakkında daha fazla bilgi edinmek için bu makalenin devamında yer alan [Senaryolar](#scenarios) bölümüne bakın.

Bu özellik varsayılan olarak açıktır. Ancak, Microsoft tarafından sağlanan özel ön cephe uygulaması deneyimini istemiyorsanız özelliği kapatabilirsiniz. Özelliği kapatmak veya açmak için:

1. Microsoft Teams yönetim merkezinin sol gezinti bölmesinde **Teams uygulamaları Uygulamaları** > **yönet'e** gidin ve **ardından Kuruluş genelinde uygulama ayarları'nı** seçin.
2. **Uyarlanmış uygulamalar'ın** altında **Uyarlanmış uygulamaları göster iki durumlu** düğmesini **Kapalı** veya **Açık** olarak değiştirin.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams yönetim merkezinin Uygulamaları yönet sayfasındaki Uyarlanmış uygulamaları göster ayarının ekran görüntüsü" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Senaryo

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>Uyarlanmış ön cephe uygulama deneyimi genel uygulama kurulum ilkemi nasıl etkiler?

Uyarlanmış ön cephe uygulama deneyiminin genel uygulama kurulum ilkesiyle birlikte nasıl çalıştığını öğrenin. Bu tablodaki senaryolar, F lisansına ve genel uygulama kurulum ilkesine sahip ön cephe çalışanları için geçerlidir ve **Kullanıcı sabitleme** açık durumdadır.

|Eğer... |Sonra... |
|---------|---------|
|Ön cephe çalışanı genel uygulama kurulum ilkesine sahiptir ve özellik kapalıdır. |Ön cephe çalışanı, genel uygulama kurulum ilkesinde tanımlanan uygulamaları alır.|
|Ön cephe çalışanı genel uygulama kurulum ilkesine sahiptir ve özellik açık durumdadır.     | Ön cephe çalışanı, özel ön cephe uygulama deneyimini alır. Genel uygulama kurulum ilkesinde tanımlanan uygulamalar, uyarlanmış uygulamaların altına sabitlenir.      |
|Genel uygulama kurulum ilkesini güncelleştirirsiniz ve özellik açık durumdadır.     |Ön cephe çalışanı, uyarlanmış ön cephe uygulama deneyimini alır ve genel uygulama kurulum ilkesinde tanımlanan uygulamalar uyarlanmış uygulamaların altına sabitlenir.         |
|Ön cephe çalışanının genel uygulama kurulum ilkesi vardır ve **Kullanıcı sabitlemesi** kapalıdır. |Ön cephe çalışanı, genel uygulama kurulum ilkesinde tanımlanan uygulamaları alır.|
|Ön saf çalışanının genel uygulama kurulum ilkesi vardır ve genel uygulama kurulum ilkesi, uygulama listesindeki ikinci konuma bir iş kolu (LOB) uygulaması içerecek şekilde değiştirilir. |LOB uygulaması, uyarlanmış uygulamaların altına sabitlenir. Ön cephe çalışanı **, Kullanıcı sabitleme** açıksa uygulama sırasını değiştirebilir.         |
|Ön cephe çalışanı genel kurulum ilkesine sahiptir ve genel uygulama kurulum ilkesi, vardiyaları ilk konumda içerecek şekilde değiştirilir.  |Vardiyalar, uyarlanmış ön cephe uygulama deneyimi tarafından tanımlandığı gibi altıncı konuma sabitlenir. Ön cephe çalışanı **, Kullanıcı sabitleme** açıksa uygulama sırasını değiştirebilir.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Uyarlanmış ön cephe uygulama deneyimi diğer Teams uygulama ilkeleriyle nasıl çalışır?

Uyarlanmış ön cephe uygulama deneyiminin diğer Teams uygulama ilkeleriyle nasıl çalıştığını öğrenin.

|Eğer...  |Sonra... |
|---------|---------|
Özellik kapalı.   | Ön cephe çalışanı, genel uygulama kurulum ilkesinde veya kendilerine atanan özel uygulama kurulum ilkesinde tanımlanan uygulamaları alır.          |
|Ön cephe çalışanının özel bir uygulama kurulum ilkesi vardır ve özellik açık durumdadır.    |Ön cephe çalışanı, özel uygulama kurulum ilkesinde tanımlanan uygulamaları alır.          |
|Özel ön cephe uygulama deneyimindeki bir uygulama, bir kullanıcı veya kuruluşunuz için engellenir.      |Uyarlanmış ön cephe uygulama deneyimi [, uygulama izin ilkesine uyar](/microsoftteams/teams-app-permission-policies). Bir uygulama engellenirse ön cephe çalışanı engellenen uygulamayı görmez.           |
|Uyarlanmış ön cephe uygulama deneyimindeki bir uygulama, bir uygulama kurulum ilkesinde zaten tanımlanmıştır ve özellik açık durumdadır. |Uygulama, uyarlanmış uygulamalar listesi tarafından tanımlanan sıralamaya göre sabitlenir.        |
|Kullanıcının E, A veya G lisansı vardır ve özellik açık durumdadır.   | Kullanıcı, uyarlanmış ön cephe uygulaması deneyimini elde etmez. Şu anda bu deneyim yalnızca F lisansı olan kullanıcılar için geçerlidir.        |

> [!NOTE]
> Uyarlanmış ön cephe uygulama deneyiminde uygulamaların veya uygulamaların sırasını değiştiremezsiniz. Şimdilik, değişiklik yapmak istiyorsanız kendi özel deneyiminizi ayarlayabilirsiniz. Bunu yapmak için önce özelliği kapatın. Ardından [, özel bir uygulama kurulum ilkesi oluşturun](/microsoftteams/teams-app-setup-policies) ve [bunu kullanıcılara veya gruplara atayın](/microsoftteams/assign-policies-users-and-groups).

### <a name="coming-soon"></a>Çok yakında

 Viva Bağlantılar yakında ön cepheye özel uygulamalar deneyiminin bir parçası olacak. Özel uygulama deneyimini gören ön cephe kullanıcıları Viva Bağlantılar hem mobil hem de masaüstünde ilk konuma sabitlenmiş olur.

Bu deneyim, Kuruluşunuzun gereksinimlerine uyacak şekilde özelleştirilebilen Görevler, Vardiyalar, Onaylar ve En İyi Haberler gibi ilgili ön hat kartları içeren varsayılan bir pano içerir. Kuruluşunuz zaten bir Viva Bağlantılar giriş sitesi ayarladıysa, varsayılan deneyimden önceliklidir. Daha fazla bilgi için bkz. [Microsoft 365 yol haritası](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=99706).

**Teams mobil**

:::image type="content" source="media/tailored-teams-apps-viva-connections-mobile.png" alt-text="Teams mobil cihazlarda uyarlanmış ön hat uygulama deneyimindeki Viva Bağlantılar gösteren ekran görüntüsü." lightbox="media/tailored-teams-apps-viva-connections-mobile.png":::

**Teams masaüstü**

:::image type="content" source="media/tailored-teams-apps-viva-connections-desktop.png" alt-text="Teams masaüstünde uyarlanmış ön hat uygulama deneyiminde Viva Bağlantılar gösteren ekran görüntüsü." lightbox="media/tailored-teams-apps-viva-connections-desktop.png":::

## <a name="related-articles"></a>İlgili makaleler

- [Teams'de Walkie Talkie uygulamasını yönetme](/microsoftteams/walkie-talkie?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams'de Görevler uygulamasını yönetme](/microsoftteams/manage-tasks-app?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams'de Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams'de Onaylar uygulamasını yönetme](/microsoftteams/approval-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams'de uygulama kurulum ilkelerini yönetme](/microsoftteams/teams-app-setup-policies)
- [Teams'de uygulama izin ilkelerini yönetme](/microsoftteams/teams-app-permission-policies)
