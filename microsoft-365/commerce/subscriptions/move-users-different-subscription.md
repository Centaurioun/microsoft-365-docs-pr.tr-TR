---
title: Kullanıcıları farklı bir aboneliğe taşıma
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- manage_licenses
search.appverid: MET150
description: Kullanıcıları abonelikler arasında taşımayı öğrenin.
ms.date: 05/12/2022
ms.openlocfilehash: 230996448d333076d150a0ff051f268e72d55363
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719458"
---
# <a name="move-users-to-a-different-subscription"></a>Kullanıcıları farklı bir aboneliğe taşıma

Birden fazla ürününüz varsa, bir ürün için lisansı olan kullanıcılarınız varsa ancak bunları başka bir ürüne taşımak istiyorsanız, mevcut lisanslarını farklı bir ürünle değiştirebilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Lisansları atamak için Genel, Lisans veya Kullanıcı yöneticisi olmanız gerekir. Daha fazla bilgi için bkz. [Microsoft 365 yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).

## <a name="move-users-to-a-different-subscription"></a>Kullanıcıları farklı bir aboneliğe taşıma

::: moniker range="o365-worldwide"

1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Yönetici merkezinde, **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Etkin kullanıcılar</a> sayfasına gidin.

::: moniker-end

2. Mevcut lisanslarını değiştirmek istediğiniz kullanıcıların adlarının yanındaki onay kutularını seçin.

3. Üst kısımda **Ürün lisanslarını yönet'i** seçin.

4. **Ürün lisanslarını yönet** bölmesinde **Değiştir'i** seçin ve kullanıcılara atamak istediğiniz lisansları seçin.

5. Alt kısımda **Değişiklikleri** \> Kaydet **Kapat'ı** seçin.

## <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>İş için Microsoft 365 planlarını değiştirmeden önce verileri yedekleme

Bir kullanıcı veriyle ilgili daha az hizmet içeren başka bir aboneliğe geçerse veya bir kullanıcı kuruluştan ayrılırsa, yeni aboneliğe geçmeden önce Microsoft 365'te depolanan verilerinin bir kopyasını indirebilirsiniz.

Kullanıcıyı aynı veya daha fazla hizmete sahip bir aboneliğe taşıyorsanız, kullanıcı verilerini yedeklemeniz gerekmez.
  
### <a name="save-a-copy-of-outlook-information"></a>Outlook bilgilerinin bir kopyasını kaydetme

Kullanıcıların Outlook'u varsa, planları değiştirilmeden önce [e-postayı, kişileri ve takvimi bir Outlook .pst dosyasına aktarabilir veya yedekleyebilirler](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) .
  
Yeni plana geçiş tamamlandıktan sonra, kullanıcılar [Outlook .pst dosyasından e-postayı, kişileri ve takvimi içeri aktarabilir](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
### <a name="save-files-stored-in-onedrive-for-business"></a>OneDrive İş'de depolanan dosyaları kaydetme

Kullanıcılar, farklı bir aboneliğe geçmeden önce [OneDrive veya SharePoint'ten](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) bilgisayarlarının sabit sürücüsündeki bir klasör veya kuruluşun ağındaki dosya paylaşımı gibi farklı bir konuma dosya ve klasör indirebilir.
  
### <a name="save-yammer-information"></a>Yammer bilgilerini kaydetme

Yöneticiler tüm iletileri, notları, dosyaları, konuları, kullanıcıları ve grupları bir .zip dosyasına aktarabilir. Daha fazla bilgi için bkz. [Yammer Kurumsal'dan verileri dışarı aktarma](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Geliştiriciler bunu yapmak için [Yammer API'sini](https://go.microsoft.com/fwlink/p/?linkid=842495) de kullanabilir.
  
### <a name="how-to-save-sharepoint-information"></a>SharePoint bilgilerini kaydetme

Bir kullanıcı SharePoint Online'ı olmayan bir aboneliğe geçirilirse, **SharePoint** kutucuğu artık Microsoft 365 menüsünde görünmez.
  
Ancak, yeni abonelik, geçiş yaptıkları kuruluşla aynı kuruluş içinde olduğu sürece, kullanıcılar SharePoint ekip sitesine erişmeye devam edebilir. Ekip sitesinin doğrudan URL'sini kullanarak not defterlerini, belgeleri, görevleri ve takvimleri görüntüleyebilir ve güncelleştirebilirler.
  
> [!TIP]
> Kullanıcıların abonelikleri değiştirilmeden önce ekip sitesine gitmelerini ve URL'yi tarayıcılarında sık kullanılan veya yer işareti olarak kaydetmelerini öneririz.
  
Varsayılan olarak, ekip web sitesinin URL'si şu biçimdedir:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

burada  _\<orgDomain\>_ kuruluşun URL'sidir.
  
Örneğin, kuruluşun etki alanı contoso.onmicrosoft.com ise, ekip sitesinin doğrudan URL'si olur `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Elbette, kullanıcılar sharepoint online belgelerini SharePoint ekip sitesinden kendi yerel bilgisayarlarına veya başka bir konuma istedikleri zaman indirebilirler.

## <a name="next-steps"></a>Sonraki adımlar

[Kullanılmayan lisansları diğer kullanıcılara yeniden atamayacaksanız](../../managed-desktop/get-started/assign-licenses.md), ihtiyacınız olandan daha fazla lisans için ödeme yapmanıza gerek kalmaması için [lisansları aboneliğinizden kaldırmayı](../../commerce/licenses/buy-licenses.md) göz önünde bulundurun.

## <a name="related-content"></a>İlgili içerik

[Kullanıcılara lisans atama](../../admin/manage/assign-licenses-to-users.md) (makale)\
[Aboneliğinizden lisansları kaldırma](../licenses/buy-licenses.md) (makale)\
[Planları el ile değiştirme](change-plans-manually.md) (makale)\
[İş için Microsoft 365'teki abonelikleri ve lisansları anlama](../licenses/subscriptions-and-licenses.md) (makale)\
[Başka bir iş için Microsoft 365 aboneliği satın alma](../try-or-buy-microsoft-365.md) (makale)
