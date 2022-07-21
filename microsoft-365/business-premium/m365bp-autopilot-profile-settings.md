---
title: Autopilot Profili ayarları hakkında
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Autopilot profilleri, Windows'un kullanıcı cihazlarına nasıl yükleneceğini denetlemenize yardımcı olur. Profiller, Cortana yüklemesini atlama gibi varsayılan ve isteğe bağlı ayarları içerir.
ms.openlocfilehash: 9fcec0d34a23a56943a1a17d7e7f74435910055e
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894733"
---
# <a name="about-autopilot-profile-settings"></a>Autopilot Profili ayarları hakkında

## <a name="autopilot-profile-settings"></a>Autopilot profil ayarları

Windows'un kullanıcı cihazlarına nasıl yükleneceğini denetlemek için Autopilot profillerini kullanabilirsiniz. Profiller aşağıdaki ayarları içerir.
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>Otomatik olarak ayarlanan autopilot varsayılan özellikleri (gerekli)
  
| Ayar | Açıklama |
|:-----|:-----|
|Cortana, OneDrive ve OEM kaydını atlama  |Cortana ve kişisel OneDrive gibi tüketici uygulamalarının yüklenmesini atlar. Kullanıcı cihazda yerel yönetici olduğu sürece cihaz kullanıcısı bunları daha sonra yükleyebilir. Cihaz Microsoft 365 İş Ekstra tarafından yönetileceğinden özgün üretici kaydı atlanır.  |
|Şirket markanızla oturum açma deneyimi  |Şirketinizde [Microsoft 365 Oturum Açma'ya şirket markanızı ekleyin sayfası](../admin/setup/customize-sign-in-page.md) varsa, cihaz kullanıcısı oturum açarken bu deneyimi elde eder.  |
|Yapılandırılmış AAD hesaplarıyla MDM otomatik kaydı.  |Kullanıcı kimliği Azure Active Directory tarafından yönetilir ve kullanıcılar Microsoft 365 İş Ekstra kimlik bilgileriyle Windows ve Microsoft 365'te oturum açar.  |

## <a name="optional-settings"></a>İsteğe bağlı ayarlar
  
| Ayar | Açıklama |
|:-----|:-----|
|Gizlilik ayarlarını atla (Varsayılan olarak Kapalı)  |Bu seçenek **Açık** olarak ayarlanırsa, cihaz kullanıcısı ilk kez oturum açtığında cihaz ve Windows lisans sözleşmesini görmez.  |
|Kullanıcının yerel yönetici olmasına izin verme  |Bu seçenek **Açık** olarak ayarlanırsa, cihaz kullanıcısı Cortana gibi kişisel uygulamaları yükleyemez.|

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)