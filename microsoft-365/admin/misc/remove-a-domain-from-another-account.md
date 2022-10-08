---
title: Etki alanını başka bir hesaptan kaldırma
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
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
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365'te self servis kullanıcı kaydı tarafından oluşturulan yönetilmeyen bir hesaba katılmayı öğrenin.
ms.openlocfilehash: ff8f3df50736123488205aae96899943fec20237
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68209590"
---
# <a name="perform-an-internal-admin-takeover"></a>İç yönetici devralma işlemi gerçekleştirme

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

Yöneticiyseniz ve self servis kullanıcı kaydı tarafından oluşturulan yönetilmeyen bir hesabı devralmak istiyorsanız, bunu iç yönetici devralma işlemi gerçekleştirerek yapabilirsiniz.

> [!NOTE]
> Azure AD kullanan herhangi bir bulut hizmeti için self servis kaydolma, kullanıcıyı yönetilmeyen veya "gölge" bir dizine Azure AD ve yönetilmeyen bir hesap oluşturur. Yönetilmeyen hesap, genel yönetici olmayan bir dizindir. Bir hesabın yönetilip yönetilmediğini belirlemek için bkz. [Kiracı Türünü Belirleme](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="before-you-begin"></a>Başlamadan önce

Bazen, başka biri bu etki alanı adıyla ilişkilendirilmiş bir e-posta adresi kullanarak Microsoft 365'e kaydolmuş olduğundan, kuruluş hesabınıza etki alanı ekleyemezsiniz. Ancak etki alanını diğer yönetilmeyen hesaptan kaldırabilir ve kuruluşunuz tarafından yönetilen hesabınıza ekleyebilirsiniz.

Etki alanını diğer hesaptan kaldırıp hesabınıza ekleyebilmeniz için önce yönetilmeyen hesaba katılmanız ve bu hesabın yöneticisi olmanız gerekir. Ardından, yönetilmeyen hesaptan etki alanını kaldırır, hesabınızda yeniden oturum açar ve etki alanını yönetilen hesabınıza eklersiniz.

Bu makaledeki adımlarda yalnızca diğer hesaba nasıl katılacağınız (1. ve 2. Adımlar) ve yönetilmeyen hesapta yönetici olmak için yönetici devralma sihirbazındaki adımları izleme (3. Adım) özetlenmiştir.

Yönetilmeyen hesabın yöneticisi olduktan sonra, yönetilmeyen hesaptan etki alanını kaldırabilir ve hesabınıza ekleyebilirsiniz. 

## <a name="step-1-verify-your-email-address"></a>1. Adım: E-posta adresinizi doğrulama

> [!NOTE]
> Hesabınızda self servis etkinleştirildiyse, kullanıcılar Power BI gibi ücretsiz hizmetlere kendi başlarına abone olabilir. Bu hizmetler özellikle bir self servis kullanıcı aboneliğinin yönetici olarak devralmak istediğiniz yönetilmeyen hesabı oluşturduğu durumlarda kullanılır. 1. Adımda, yönetilmeyen etki alanı hesabının yöneticisi olabilmeniz için Power BI kullanarak yönetici devralma sihirbazını başlatarak kaldırmak istediğiniz etki alanı için bir kullanıcı hesabı oluşturursunuz.

1. Power BI'a kaydolmak için [Power BI sitesine](https://powerbi.com) gidin ve Ücretsiz  > **Başlangıç ücretsiz deneme sürümünü** **başlat'ı**(Power BI Pro paylaş kutusunda) seçin. 

2. Kuruluşunuzun etki alanı adını (gibi `powerbiadmin@contoso.com`) kullanan bir kullanıcı hesabıyla kaydolun. Hesabınız zaten kullanılıyorsa geçerli parolanızı kullanarak oturum açın.

3. **Doğrulama kodu** için e-postanızı denetleyin ve e-posta adresinizi doğrulamak için kodu girin.

## <a name="step-2-create-a-new-account-for-admin-access"></a>2. Adım: Yönetici erişimi için yeni bir hesap oluşturma

1. Doğrulama kodunu girdiğinizde, yeni bir hesap oluşturabileceğiniz bir sayfaya getirilirsiniz.

2. Kullanıcı adı ve parola alanlarını kullanmak istediğiniz hesapla doldurun, ardından **Başlat'ı** seçin.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>3. Adım: Etki alanı sahipliğini doğrulama ve yönetici olma

1. 2. Adımı tamamladıktan sonra sol gezinti bölmesindeki yönetim merkezi simgesini seçin (alternatif olarak, bir tarayıcıya gidin ve yazın `https://admin.microsoft.com`).

    Yönetici devralma sihirbazına yönlendirilirsiniz.

1. **İleri'yi** seçin ve etki alanı kayıt şirketinize bir TXT kaydı ekleyerek devralmak istediğiniz etki alanının sahibi olduğunuzu doğrulayın. 

    Sihirbaz size eklenecek TXT kaydının yanı sıra kayıt şirketinizin web sitesine bir bağlantı ve adım adım yönergelerin bağlantısını sağlar.

1. **Artık yöneticisiniz** sayfasında Yönetim **merkezine git'i** seçin.

    Artık etki alanını diğer hesaptan kaldırmak için gereken yönetici ayrıcalıklarına sahipsiniz. 
## <a name="related-content"></a>İlgili içerik

YouTube: [Power BI ve Microsoft 365 için BT Yönetici Devralma işlemi yapmak için 3 adım](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)\
[Azure AD'da devralma Yönetici](/azure/active-directory/users-groups-roles/domains-admin-takeover) (makale)\
[Kuruluşunuzda self servis kaydolmayı kullanma](self-service-sign-up.md) (makale)\
[Power BI hizmeti yönetici rolünü anlama](/power-bi/service-admin-role) (makale)
