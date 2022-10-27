---
title: Microsoft 365'te uygulamalara kullanıcı onaylarını yönetme
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Uygulamalara kullanıcı onayı ve üçüncü taraf uygulamaların kullanıcıların Microsoft 365 bilgilerine erişmesine izin vermek için bunları nasıl açacağınızı öğrenin.
ms.openlocfilehash: d194303f0c0c94495f723c80a8aaa3e38a01ea7a
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731227"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Microsoft 365'te uygulamalara kullanıcı onaylarını yönetme

Bu ayar, kullanıcıların oturum açma için OpenID Connect ve OAuth 2.0 kullanan uygulamalara onay verip veremeyeceğini ve verilere erişme isteklerini denetler. Bir uygulama kendi kuruluşunuzun içinden oluşturulabilir veya başka bir Office 365 kuruluşundan veya üçüncü taraflardan gelebilir.

Bu ayarı açarsanız, bu uygulamalar kullanıcılardan kuruluşunuzun verilerine erişmek için izin ister ve kullanıcılar buna izin verilip verilmeyeceğini seçebilir. Bu ayarı kapatırsanız, kullanıcıların kullanabilmesi için yöneticilerin bu uygulamaları onaylaması gerekir. Bu durumda, kullanıcıların engellenen herhangi bir uygulamayı kullanmak üzere yönetici onayı isteği gönderebilmesi için Azure portal bir yönetici onayı iş akışı ayarlamayı göz önünde bulundurun.

Bir kullanıcı, yalnızca sahip olduğu ve Office 365 bilgilerine erişmek isteyen uygulamalara erişim izni verebilir. Kullanıcılar, uygulamanın başka bir kullanıcının bilgilerine erişmesine izin veremez.

## <a name="turning-user-consent-on-or-off"></a>Kullanıcı onayınızı açma veya kapatma

Uygulamalar için Kullanıcı onayı özelliğini şu şekilde açabilir veya kapatabilirsiniz.

1. Yönetim merkezinde **Ayarlar** \> **Kuruluş ayarları** > [Hizmetler](https://go.microsoft.com/fwlink/p/?linkid=2053743) sayfasına gidin ve ardından **Uygulamalar için kullanıcı onayı'nı** seçin.

2. **Uygulamalara kullanıcı onayı** sayfasında, kullanıcı onayını açma veya kapatma seçeneğini belirleyin.

## <a name="related-content"></a>İlgili içerik 

[Yönetici onayı iş akışını yapılandırma](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (makale)\
[Uygulamalara yönelik onayı yönetme ve onay isteklerini değerlendirme](/azure/active-directory/manage-apps/manage-consent-requests) (makale)