---
title: Adım 4. Cihazlarınız, bilgisayarlarınız ve diğer uç noktalarınız için uç nokta yönetimi dağıtma
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Cihazlarınızı, bilgisayarlarınızı ve diğer uç noktalarınızı yönetmek için Microsoft Endpoint Manager kullanın.
ms.openlocfilehash: 70377db41b9a35dd20d217bb207299cacf441b67
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731298"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Adım 4. Cihazlarınız, bilgisayarlarınız ve diğer uç noktalarınız için uç nokta yönetimi dağıtma

Hibrit çalışanlarla, giderek artan sayıda kişisel cihazı desteklemeniz gerekir. Uç nokta yönetimi, cihazlara kaynaklara erişim verilmeden önce belirli ölçütlere uymasını gerektiren ilke tabanlı bir güvenlik yaklaşımıdır. Microsoft Endpoint Manager, verilerinizi bulutta ve şirket içinde güvenli tutmak için modern yönetim özellikleri sunar. 

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview), önceden bildiğiniz ve kullanıyor olabileceğiniz aşağıdaki hizmetleri birleştirerek mobil cihazları, masaüstü bilgisayarları, sanal makineleri, ekli cihazları ve sunucuları yönetmeye yönelik hizmetler ve araçlar sağlar.

:::image type="content" source="../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png" alt-text="Microsoft 365 için uç nokta yönetimi bileşenleri" lightbox="../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png":::

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune, Microsoft 365'te bulunan mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir. 

- **MDM:** Kuruluşa ait cihazlar için ayarlar, özellikler ve güvenlik dahil olmak üzere tam denetim kullanabilirsiniz. Cihazlar, kurallar ve ayarlarla Intune ilkeleri aldıkları Intune "kaydedilir". Örneğin, parola ve PIN gereksinimlerini ayarlayabilir, VPN bağlantısı oluşturabilir, tehdit korumasını ayarlayabilir ve daha fazlasını yapabilirsiniz.

- **MAM:** Uzaktan çalışanlar, kendi cihazını getir (KCG) cihazları olarak da bilinen kişisel cihazları üzerinde tam denetim sahibi olmanız istemeyebilir. Karma çalışanlarınıza seçenekler verebilir ve kuruluşunuzu korumaya devam edebilirsiniz. Örneğin, karma çalışanlar kuruluş kaynaklarınıza tam erişim istediklerinde cihazlarını kaydedebilir. Ya da bu kullanıcılar yalnızca e-postaya veya Microsoft Teams'e erişmek istiyorsa, bu uygulamaları kullanmak için çok faktörlü kimlik doğrulaması (MFA) gerektiren uygulama koruma ilkelerini kullanın.

Daha fazla bilgi için bkz. [Intune temel çözümüyle cihazları yönetme](manage-devices-with-intune-overview.md).

## <a name="configuration-manager"></a>Yapılandırma Yöneticisi

Configuration Manager, ağınızdaki veya İnternet tabanlı masaüstlerini, sunucuları ve dizüstü bilgisayarları yönetmek için bir şirket içi yönetim çözümüdür. Uygulamaları, yazılım güncelleştirmelerini ve işletim sistemlerini dağıtmak için Configuration Manager kullanın. Ayrıca uyumluluğu izleyebilir, istemcileri gerçek zamanlı olarak sorgulayabilir ve üzerinde işlem yapabilir ve çok daha fazlasını yapabilirsiniz. Intune, Azure AD, Uç Nokta için Microsoft Defender ve diğer bulut hizmetleriyle tümleştirmek için buluta etkinleştirebilirsiniz. 

Daha fazla bilgi için bu [Configuration Manager genel bakışına](/mem/configmgr/core/understand/introduction) bakın.

## <a name="co-management"></a>Ortak yönetim

Ortak yönetim, Intune ve diğer Microsoft 365 bulut hizmetlerini kullanarak mevcut şirket içi Configuration Manager yatırımınızı bulutla birleştirir. farklı iş yükleri için yönetim yetkilisinin Configuration Manager mi yoksa Intune mi olduğunu seçersiniz. 

Ortak yönetim, Koşullu Erişim ve cihaz uyumluluğunu zorunlu tutma gibi Intune tabanlı bulut özelliklerini kullanır. Bazı görevleri şirket içinde tutarken, diğer görevleri bulutta çalıştırırsınız.

Daha fazla bilgi için bkz. [Ortak yönetime genel bakış](/mem/configmgr/comanage/overview).

## <a name="endpoint-analytics"></a>Uç Nokta Analizi

Uç nokta analizi, kullanıcı deneyimine ilişkin içgörüler sağlayarak kullanıcı verimliliğini artırmayı ve BT destek maliyetlerini düşürmeyi amaçlar. İçgörüler, BT'nin proaktif destekle son kullanıcı deneyimini iyileştirmesini ve yapılandırma değişikliklerinin kullanıcı etkisini değerlendirerek kullanıcı deneyimindeki gerilemeleri tespit etmesini sağlar.

Daha fazla bilgi için bkz [. Endpoint Analytics'e genel bakış](/mem/analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot, sıfır dokunmatik, self servis bir Windows dağıtım platformudur. Yeni cihazları ayarlamak ve önceden yapılandırmak ve üretken kullanıma hazır hale getirmek için kullandığınız bir teknoloji koleksiyonu içerir. Cihazları sıfırlamak, yeniden kullanmak ve kurtarmak için Windows Autopilot'ı da kullanabilirsiniz. 

Windows Autopilot, bt departmanının kolay ve basit bir işlemle yönetecek çok az ve hiç altyapısı olmayan cihazları önceden yapılandırmasına olanak tanır. 

- Kullanıcının bakış açısından, cihazını kullanıma hazır hale getirmek yalnızca birkaç basit işlem gerektirir. 
- BT uzmanı açısından bakıldığında, son kullanıcıdan gereken tek etkileşim bir ağa bağlanmak ve kimlik bilgilerini doğrulamaktır.

Daha fazla bilgi için bkz. [Windows Autopilot'a genel bakış](/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Uç nokta yönetimi için teknik kaynakları Yönetici

- [Microsoft 365 için cihaz yönetimi yol haritası](../enterprise/device-management-roadmap-microsoft-365.md)
- [Mobil cihaz yönetimi için farklı cihaz türlerini kaydetme](/mem/intune/enrollment/device-enrollment)
- [Son kullanıcılarınızı Microsoft Intune hakkında eğitme](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>4. Adımın Sonuçları

Mobil cihazları, masaüstü bilgisayarları, sanal makineleri, ekli cihazları ve sunucuları yönetmek için Endpoint Manager özellik ve özellikler paketini kullanıyorsunuz.

## <a name="next-step"></a>Sonraki adım

[![5. Adım: Uzaktan çalışan üretkenliği uygulamalarını ve hizmetlerini dağıtma.](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

Hibrit çalışanlarınızın Microsoft Teams gibi Microsoft 365 üretkenlik uygulamalarını kullanmasını sağlamak için 5. [Adımla](empower-people-to-work-remotely-teams-productivity-apps.md) devam edin.