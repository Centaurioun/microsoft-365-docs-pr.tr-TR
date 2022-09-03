---
title: Microsoft 365 Lighthouse'de self servis parola sıfırlamayı yönetme
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için self servis parola sıfırlamayı yönetmeyi öğrenin.
ms.openlocfilehash: bcfbd9ad05a433fb9b98125fe6447d9086096a1a
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599120"
---
# <a name="manage-self-service-password-reset-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'de self servis parola sıfırlamayı yönetme

Microsoft 365 Lighthouse, iş ortaklarının Azure Active Directory (Azure AD) self servis parola sıfırlamayı (SSPR) yönetmesini sağlar. SSPR, kullanıcılara yönetici veya yardım masası katılımı olmadan parolalarını değiştirme veya sıfırlama olanağı sağlar. Kullanıcının hesabı kilitliyse veya parolasını unutursa, engellemesini kaldırmak ve işe geri dönmek için istemleri izleyebilir. Bu özellik, kullanıcı cihazında veya uygulamada oturum açamazsa yardım masası çağrılarını ve üretkenlik kaybını azaltır.

## <a name="before-you-begin"></a>Başlamadan önce

Kiracı listede görünmeden önce aşağıdaki koşulların karşılanması gerekir:

- Müşteri kiracısının her kullanıcı için bir Azure AD Premium lisansı olmalıdır. SSPR'yi hangi lisansların desteklediği hakkında daha fazla bilgi için bkz. [Azure Active Directory self servis parola sıfırlama için lisans gereksinimleri](/azure/active-directory/authentication/concept-sspr-licensing).

- Müşteri kiracısının Lighthouse içinde etkin olması gerekir. Kiracının etkin olup olmadığını belirlemeyi öğrenmek için [Microsoft 365 Lighthouse'daki Windows 365 (Bulut Bilgisayarlar) sayfasına genel bakış bölümüne](m365-lighthouse-tenants-page-overview.md) bakın.

## <a name="view-sspr-tenant-status"></a>SSPR kiracı durumunu görüntüleme

- Lighthouse'un sol gezinti bölmesinde **Kullanıcılar** > **Parola sıfırlama'yı** seçin.

Parola sıfırlama sayfası, önerilen ayarlar, SSPR'ye kaydolmamış kullanıcı sayısı ve yönettiğiniz kuruluşlar genelinde SSPR dağıtım ilerleme durumunun kiracıya göre ayrıntılı dökümü aracılığıyla SSPR'yi etkinleştiren kiracılara genel bir bakış sağlar.

## <a name="enable-sspr-for-a-tenant"></a>Kiracı için SSPR'yi etkinleştirme

1. Lighthouse'un sol gezinti bölmesinde **Kullanıcılar** > **Parola sıfırlama'yı** seçin.

2. **Parola sıfırlama** sayfasında, ayrıntılar bölmesini açmak için listeden bir kiracı seçin.

3. **Azure Active Directory'ye (Azure AD) gitmek için Azure Active Directory'de SSPR ayarlarını düzenle'yi** seçin.

4. Azure AD'de, tüm veya seçili kullanıcılar için SSPR'yi etkinleştirin. Daha fazla bilgi edinmek için bkz [. Öğretici: Azure Active Directory self servis parola sıfırlamayı kullanarak kullanıcıların hesap kilidini açmalarını veya parola sıfırlamalarını sağlama](/azure/active-directory/authentication/tutorial-enable-sspr).

## <a name="notify-users-to-register-for-sspr"></a>Kullanıcılara SSPR'ye kaydolmalarını bildirme

1. Lighthouse'un sol gezinti bölmesinde **Kullanıcılar** > **Parola sıfırlama'yı** seçin.

2. **Parola sıfırlama** sayfasında, ayrıntılar bölmesini açmak için listeden bir kiracı seçin.

3. Bildirmek istediğiniz kullanıcıları seçin.

4. **E-posta oluştur'u** seçin.

Lighthouse varsayılan e-posta istemcinizi açar ve E-posta iletisini SSPR'ye kaydolma yönergeleriyle önceden doldurulur. Seçilen tüm kullanıcılar Gizli satırına eklenir. Kullanıcılara tek tek e-posta göndermeyi tercih ederseniz, kullanıcı adının yanındaki e-posta simgesini seçebilirsiniz.

Farklı bir e-posta hesabı kullanmak istiyorsanız, kullanıcı listesini bir dosyaya aktarabilirsiniz. Ayrıca, şirketinizin markasıyla özelleştirebileceğiniz örnek e-posta şablonlarını da indirebilirsiniz.

## <a name="related-content"></a>İlgili içerik

[Azure Active Directory self servis parola sıfırlama dağıtımı planlama](/azure/active-directory/authentication/howto-sspr-deployment) (makale)\
[Öğretici: Azure Active Directory self servis parola sıfırlamayı (makale)\ kullanarak kullanıcıların hesap kilidini açmalarını veya parolaları sıfırlamalarını sağlama](/azure/active-directory/authentication/tutorial-enable-sspr)
[Azure AD'de SSPR'yi etkinleştirme ve yapılandırma](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (video)\
[Microsoft 365 Lighthouse'de çok faktörlü kimlik doğrulamasını yönetme](m365-lighthouse-manage-mfa.md) (makale)
