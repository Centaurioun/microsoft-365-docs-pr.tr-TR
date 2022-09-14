---
title: Etki alanı kayıt şirketinizi bulma
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC aramasını kullanarak etki alanı kayıt şirketinizi ve DNS barındırma sağlayıcınızı bulmayı öğrenin.
ms.openlocfilehash: f48be0f1d1c28ce9a9d76ef278411245faa3d4da
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67664263"
---
# <a name="find-your-domain-registrar"></a>Etki alanı kayıt şirketinizi bulma

 Aradığınızı bulamazsanız, **[etki alanları SSS bölümüne bakın](../setup/domains-faq.yml)**.

## <a name="domain-registrar"></a>Etki alanı kayıt şirketi

### <a name="find-your-domain-name-registrar"></a>Etki alanı adı kayıt şirketinizi bulma

> [!NOTE]
> Yalnızca *.COM*, *.NET*, and *.EDU* ile biten etki alanları bu araçla kullanılabilir.

1. [InterNIC arama sayfası](https://go.microsoft.com/fwlink/p/?LinkId=402770)’nda, **Whois arama** kutusuna, etki alanınızı yazın. Örneğin,  *contoso.com.*

2. **Etki Alanı** seçimini yapın ve sonra **Gönder**'i tıklatın.

3. **Whois Search Results** (Whois Arama Sonuçları) sayfasında, **Registrar** (Kayıt Şirketi) girişini bulun. Bu girişte, etki alanınız için kayıt şirketi hizmeti sağlayan kuruluş listelenir.

## <a name="dns-hosting-provider"></a>DNS barındırma hizmet sağlayıcısı

### <a name="find-your-dns-hosting-provider"></a>DNS barındırma hizmet sağlayıcınızı bulma

> [!NOTE]
> Yalnızca *.COM*, *.NET*, and *.EDU* ile biten etki alanları bu araçla kullanılabilir.

1. [InterNIC arama sayfasında](https://go.microsoft.com/fwlink/p/?LinkId=402770), **Whois Search** kutusuna etki alanınızı yazın. Örneğin, contoso.com.

2. **Etki Alanı** seçimini yapın ve sonra **Gönder**'i tıklatın.

3. 
            **Whois Search Results** (Whois Arama Sonuçları) sayfasında, ilk **Name Server** (Ad Sunucusu) girişini bulun.

4. İki nokta işaretinden (:) sonra görünen ad sunucusu (NS) bilgilerini kopyalayıp sayfanın en üstündeki **Ara** kutusuna yapıştırın. **Ad sunucusu**’nu seçin ve **Gönder**'i tıklatın.

5. 
            **Whois Arama Sonuçları** sayfasında **Kayıt Şirketi** girişini bulun. Bu girişte, etki alanınızın ad sunucusunun sahibi olan DNS hizmeti sağlayıcısı listelenir.

---

