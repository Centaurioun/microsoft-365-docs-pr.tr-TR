---
title: Microsoft 365 Lighthouse'de denetim günlüklerini gözden geçirme
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: vivkuma
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için denetim günlüklerini gözden geçirmeyi öğrenin.
ms.openlocfilehash: 0bf1a5b30cba065756c885efe8408a718d1858a2
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68196061"
---
# <a name="review-audit-logs-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'de denetim günlüklerini gözden geçirme

Microsoft 365 Lighthouse denetim günlükleri Lighthouse veya diğer Microsoft 365 hizmetlerinde değişiklik oluşturan eylemleri kaydeder. Oluştur, düzenle, sil, ata ve uzak eylemlerin tümü gözden geçirebileceğiniz denetim olayları oluşturur. Varsayılan olarak, denetim tüm müşteriler için etkindir. Devre dışı bırakılamaz.

## <a name="before-you-begin"></a>Başlamadan önce

Denetim günlüklerini görüntülemek için aşağıdaki izinlerden birine sahip olmanız gerekir:

- Azure Active Directory (Azure AD) rolü - İş ortağı kiracısının Genel Yöneticisi

- Microsoft İş Ortağı Merkezi rolü - Yönetici Aracısı

## <a name="review-audit-logs"></a>Denetim günlüklerini gözden geçirme

1. Lighthouse'un sol gezinti bölmesinde **Denetim günlükleri'ni** seçin.

    > [!NOTE]
    > Yeni günlüklerin görülmesi 1 saat kadar sürebilir. En son değişiklikleri görmek için ilgili hizmete gidin.

2. Aşağıdaki seçenekleri kullanarak günlükleri gerektiği gibi filtreleyin:

    - **Tarih aralığı** - Önceki ay, hafta veya gün.
    - **Kiracılar** - Kiracı etiketleri veya müşteri kiracı adları.
    - **Etkinlik** - Gerçekleştirilen eyleme karşılık gelen Microsoft 365 etkinlik türü. Daha fazla bilgi için [Etkinlikler](#activities) tablosuna bakın.
    - **Başlatan** - Eylemi başlatan kişi.

3. **İstek** gövdesi de dahil olmak üzere tüm ayrıntıları görmek için listeden bir günlük seçin.

    Günlük verilerini virgülle ayrılmış değerler (.csv) dosyasına aktarmak için **Dışarı Aktar'ı** seçin.

## <a name="activities"></a>Faaliyetleri

Aşağıdaki tabloda Lighthouse denetim günlüklerinde yakalanan etkinlikler listelenir. Yeni eylemler oluşturulduktan sonra liste değiştirilebilir. Hangi eylemin başlatıldığını görmek için denetim günlüğünde listelenen etkinliği kullanabilirsiniz.<br><br>

| Etkinlik adı | Lighthouse'da alan | Eylem başlatıldı | Hizmet etkilendi |
|--|--|--|--|
| **uygulama** veya **dağıtma** | Kiracı | Dağıtım planı uygulama | Azure AD, Microsoft Endpoint Manager (MEM) |
| **assignTag** | Kiracı | Müşteriden etiket uygulama | Lighthouse |
| **changeDeploymentStatus** veya **assign** | Kiracı | Dağıtım planı için eylem planı durumunu güncelleştirme | Lighthouse |
| **offboardTenant** | Kiracı | Müşteriyi devre dışı bırakma | Lighthouse |
| **resetTenantOnboardingStatus** | Kiracı | Müşteriyi yeniden etkinleştirme | Lighthouse |
| **tenantTags** | Kiracı | Etiket oluşturma veya silme | Lighthouse |
| **tenantCustomizedInformation** | Kiracı | Müşteri web sitesi veya iletişim bilgilerini oluşturma, güncelleştirme veya silme | Lighthouse |
| **unassignTag** | Kiracı | Müşteriden etiket kaldırma | Lighthouse |
| **Doğrulamak** | Kiracı | Dağıtım planını test edin | Azure AD |
| **blockUserSignin** | Kullanıcılar | Oturum açmayı engelle | Azure AD |
| **confirmUsersCompromised** | Kullanıcılar | Bir kullanıcının gizliliğinin tehlikeye girdiğini onaylama | Azure AD |
| **dismissUsersRisk** | Kullanıcılar | Kullanıcı riskini kapatma | Azure AD |
| **resetUserPassword** | Kullanıcılar | Parolayı sıfırlayın | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | Kullanıcılar | Güvenlik varsayılanlarıyla çok faktörlü kimlik doğrulamasını (MFA) etkinleştirme | Azure AD |
| **restartCihaz** | Aygıtları | Yeniden başlatma | Mem |
| **syncDevice** | Aygıtları | Eşitleme | Mem |
| **rebootNow** | Tehdit yönetimi | Yeni -den başlatma | Mem |
| **yeniden sağlama** | Windows 365 | Sağlamayı yeniden deneyin | Windows 365 |
| **windowsDefenderScanFull** | Tehdit yönetimi | Tam tarama | Mem |
| **windowsDefenderScan** | Tehdit yönetimi | Hızlı tarama | Mem |
| **windowsDefenderUpdateSignatures** | Tehdit yönetimi | Virüsten korumayı güncelleştirme | Mem |

## <a name="next-steps"></a>Sonraki adımlar

Gerekirse daha fazla denetim olayına erişmek için Microsoft Graph API kullanın. Daha fazla bilgi için bkz. [Microsoft 365 Lighthouse API'sini kullanarak çok kiracılı yönetime genel bakış](/graph/managedtenants-concept-overview).

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)\
[Microsoft 365 Lighthouse'de Azure Active Directory rollerinizi görüntüleme](m365-lighthouse-view-your-roles.md) (makale)