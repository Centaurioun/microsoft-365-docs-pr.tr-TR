---
title: Yönetilmeyen hesapta doğrulanmış bir etki alanını taşıma
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
description: Yönetilmeyen bir hesaba katılarak etki alanını hesaptan kaldırmayı ve etki alanını hesabınıza eklemeyi öğrenin.
ms.openlocfilehash: 7b7befdae4279b4b08ff076b88ed552b2bc411c3
ms.sourcegitcommit: c757f434da78bae71d4b476e14836fdf4da9f31e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2022
ms.locfileid: "67884382"
---
# <a name="move-a-domain-verified-in-an-unmanaged-account"></a>Yönetilmeyen hesapta doğrulanmış bir etki alanını taşıma

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

Yöneticiyseniz ve Microsoft 365 hesabınıza etki alanı eklemeye çalıştıysanız ancak etki alanı yönetilmeyen bir hesap için doğrulandığından engellendiyseniz, etki alanını kaldırmak ve hesabınıza eklemek için yönetilmeyen hesapta yönetici olabilirsiniz.

> [!NOTE]
> Azure AD kullanan herhangi bir bulut hizmeti için self servis kaydolma, kullanıcıyı yönetilmeyen veya "gölge" bir dizine Azure AD ve yönetilmeyen bir hesap oluşturur. Yönetilmeyen hesap, genel yönetici olmayan bir dizindir. Bir hesabın yönetilip yönetilmediğini belirlemek için bkz. [Kiracı Türünü Belirleme](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).
  
## <a name="before-you-begin"></a>Başlamadan önce

Bazen, başka biri bu etki alanı adıyla ilişkilendirilmiş bir e-posta adresi kullanarak Microsoft 365'e kaydolmuş olduğundan, kuruluş hesabınıza etki alanı ekleyemezsiniz. Ancak etki alanını diğer yönetilmeyen hesaptan kaldırabilir ve kuruluş hesabınıza ekleyebilirsiniz.

İlk olarak yönetilmeyen hesaba katılmanız ve bu hesabın yöneticisi olmanız gerekir (Adım 1 - 3). Ardından, etki alanını hesaptan kaldırabilir (4. Adım), kuruluş hesabınızda yeniden oturum açabilir ve etki alanını hesabınıza ekleyebilirsiniz (5. Adım).

## <a name="step-1-get-an-invitation-to-join-the-unmanaged-account"></a>1. Adım: Yönetilmeyen hesaba katılma daveti alma

Hesabınıza etki alanı eklemeyi denedikten sonra, birinin e-posta adresini kullanarak Microsoft 365'e kaydolduğunu belirten bir ileti alabilirsiniz. 1. adım, diğer hesaba katılma daveti istemek ve yönetici devralma işlemine başlamaktır.

1. **Microsoft 365 yönetim merkezi > Ayarlar** > **Etki Alanları****+ Etki alanı** >  ekle'ye gidin ve etki alanı adını ekleyin.

1. Diğer kişiler zaten etki alanı için bir e-posta adresi kullanarak kaydolduğunuz için etki alanını ekleyemediğinizi belirten bir ileti görürseniz, hesap kullanıcı adınızı girin ve **daveti bana gönder'i** seçin.

1. Yönetilmeyen hesapta oturum açabilmeniz için geçerli hesabınızın oturumunu kapatın.

    Yönetilmeyen hesaba katılmanıza yardımcı olacak bir davet için e-postanızı denetleyin ve e-postada sağlanan bağlantıyı seçin.

    E-posta adresinizi doğrulamak için e-postadan **doğrulama kodunu** girin.

## <a name="step-2-complete-signup-with-email-instructions"></a>2. Adım: E-posta yönergeleriyle kaydolmayı tamamlama

1. Doğrulama kodunu girdiğinizde, yeni bir hesap oluşturabileceğiniz bir sayfaya getirilirsiniz.

2. Kullanıcı adı ve parola alanlarını kullanmak istediğiniz hesapla doldurun ve hesabı oluşturma adımlarını tamamlayın.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>3. Adım: Etki alanı sahipliğini doğrulama ve yönetici olma

1. 2. Adımı tamamladıktan sonra sol gezinti bölmesindeki yönetim merkezi simgesini seçin (alternatif olarak, bir tarayıcıya gidin ve yazın `https://admin.microsoft.com`).

    Yönetici devralma sihirbazına yönlendirilirsiniz.

1. **İleri'yi** seçin ve etki alanı kayıt şirketinize bir TXT kaydı ekleyerek devralmak istediğiniz etki alanının sahibi olduğunuzu doğrulayın.

    Sihirbaz size eklenecek TXT kaydının yanı sıra kayıt şirketinizin web sitesine bir bağlantı ve adım adım yönergelerin bağlantısını sağlar.

1. **Artık yöneticisiniz** sayfasında Yönetim **merkezine git'i** seçin.

    Artık etki alanını eski yönetilmeyen hesaptan kaldırmak için gereken yönetici ayrıcalıklarına sahipsiniz.

## <a name="step-4-remove-a-domain-from-the-unmanaged-account"></a>4. Adım: Yönetilmeyen hesaptan etki alanını kaldırma

1. 2. Adımda katıldığınız hesap için **Kullanıcılar** > **Etkin kullanıcılar'a** gidin ve oturum açtığınız kullanıcı adının Görünen adını seçin.

1. **Kullanıcı adı'nın** altında **Kullanıcı adını yönet'i** seçin ve açılan listeden onmicrosoft.com etki alanını seçerek kullanıcıyı onmicrosoft etki alanına taşıyın.

1. Hesabın oturumunu kapatın ve yeni `username@account.onmicrosoft.com`kullanarak yeniden oturum açın.

1. **Ayarlar** > **Etki Alanları'nı** seçin, diğer hesaba eklemek istediğiniz etki alanını bulun ve **Etki alanını kaldır'ı** seçin.

    Varsayılan olarak başka bir etki alanı seçmeniz istenirse, onmicrosoft.com etki alanını seçin.

    Diğer kullanıcılar etki alanını kullanıyorsa, bunları kaldırmanız gerekir. **Otomatik olarak kaldırma**, kullanıcıları el ile etki alanınıza taşıma veya kullanıcıları tamamen kaldırma seçeneklerinden birini belirleyin.

   > [!NOTE]
   > Etki alanının hesaptan kaldırılması biraz zaman alabildiği için yeniden denetleyin. Etki alanı hesaptan kaybolduğunda kaldırma işlemi tamamlanır.

1. Hesabın oturumunu kapatın.

## <a name="step-5-add-the-domain-to-your-account"></a>5. Adım: Etki alanını hesabınıza ekleme

1. Etki alanını eklemek istediğiniz hesapta oturum açın.

1. **Ayarlar** > **Etki Alanları** > **+ Etki alanı ekle'yi** seçin ve ardından bu hesaptaki etki alanı sahipliğini doğrulamak ve etki alanını hesabınıza eklemeyi tamamlamak üzere sihirbaz adımlarına devam etmek için etki alanı adını girin.
  
## <a name="related-content"></a>İlgili içerik

[İç yönetici devralma gerçekleştirme](become-the-admin.md) (makale)
