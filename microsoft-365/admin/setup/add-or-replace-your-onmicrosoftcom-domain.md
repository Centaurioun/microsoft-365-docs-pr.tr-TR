---
title: Microsoft 365'te onmicrosoft.com geri dönüş etki alanınızı ekleme ve değiştirme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- business_assist
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ''
description: Yeni bir onmicrosoft.com etki alanı oluşturmayı ve yeni geri dönüş etki alanınız yapmayı öğrenin.
ms.openlocfilehash: 66f5562b4a2ba46f662a54ff33d953c4e617ce3a
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2022
ms.locfileid: "67087319"
---
# <a name="add-and-replace-your-onmicrosoftcom-fallback-domain-in-microsoft-365"></a>Microsoft 365'te onmicrosoft.com geri dönüş etki alanınızı ekleme ve değiştirme

Microsoft 365'e kaydolduysanız, Bir etki alanınız yoksa veya Microsoft 365'e bağlamak istemiyorsanız (örneğin, *tailspintoys.onmicrosoft.com* ) Microsoft bir onmicrosoft.com etki alanı ( **geri dönüş** etki alanınız) sağlar. Geri dönüş etki alanınız varsayılan olarak şu durumlarda kullanılır:

- Kullanıcı adları ve e-posta adresleri
- Microsoft 365 teams & e-posta diğer adlarını gruplandırıyor
- Otomatik etki alanı bağımlılığı taşımaları

Microsoft 365 ortamınız için varsayılan e-posta yönlendirme adresi görevi görür. Kullanıcı bir posta kutusuyla ayarlandığında, e-posta geri dönüş etki alanına yönlendirilir.  Özel bir etki alanı kullanılsa bile (örneğin, tailspintoys.com), bu özel etki alanı Microsoft 365 ortamınızdan silinirse, geri dönüş etki alanı kullanıcınızın e-postasının başarıyla yönlendirilmesini sağlar.

geri dönüş etki alanınızı Microsoft 365 yönetim merkezi değiştirebilirsiniz. Müşterilerin geri dönüş etki alanını değiştirmelerinin yaygın nedenleri şunlardır:

- Microsoft 365'e ilk kaydolduğunda kullanılacak şirket adını bilmemek. Şirket adını bildiklerine göre, kullanıcılarının uygun oturum açma hesabı adları olmasını istiyorlar. 
- Yeni bir site oluştururken SharePoint URL'lerinin nasıl görüneceğini değiştirmek istiyor. Microsoft 365 ortamınızdaki SharePoint URL'leri, geri dönüş etki alanı adınıza göre oluşturulur. İlk kaydolduğunuz sırada doğru şirket adını kullanmadıysanız, yeni SharePoint siteleri oluşturduğunuzda sitelerinizin SharePoint URL'leri bu adı kullanmaya devam eder. 


Ek onmicrosoft.com etki alanları ekleyebilirsiniz ancak geri dönüş etki alanınız olarak yalnızca bir onmicrosoft.com etki alanı kullanılabilir. Bu makaledeki adımlar şunların nasıl yapılacağını açıklar:
- Yeni onmicrosoft.com etki alanı oluşturma
- Geri dönüş etki alanınız olarak atayın

> [!NOTE]
> Microsoft 365 ortamınızda toplam beş onmicrosoft.com etki alanı sınırlıdır. Eklendikten sonra kaldırılamazlar. 
  
## <a name="before-you-begin"></a>Başlamadan önce

Etki alanlarını eklemek, değiştirmek veya kaldırmak için, bir [işletme veya kurumsal planın](https://products.office.com/business/office) **Etki Alanı Adı Yöneticisi** veya **Genel Yöneticisi** **olmanız gerekir**. Bu değişiklikler kiracının tamamını etkiler; *Özelleştirilmiş yöneticiler* veya *normal kullanıcılar* bu değişiklikleri yapamaz.


## <a name="add-a-new-onmicrosoftcom-domain"></a>Yeni onmicrosoft.com etki alanı ekleme

1. Microsoft 365 yönetim merkezi **Ayarlar'ı** ve ardından **Etki Alanları'nı** seçin.
2. varsayılan onmicrosoft.com etki alanınızı seçin.

    ![Etki alanları sayfası.](../../media/onmicrosoft-domains.png)
  
3. Etki alanı özellikleri sayfasının **Bu etki alanı hakkında** bölümünde **Onmicrosoft etki alanı ekle'yi** seçin.

    ![Bu etki alanları sayfası hakkında.](../../media/add-onmicrosoft-domain-link.png)

4. **Onmicrosoft etki alanı ekle** sayfasında, **Etki alanı adı** kutusuna yeni onmicrosoft.com etki alanınızın adını yazın. 

    ![Onmicrosoft etki alanı ekle sayfasının ekran görüntüsü.](../../media/add-an-onmicrosoftcom-domain-page.png)

    > [!NOTE]
    > Girdiğiniz etki alanı adının yazım ve doğruluğunu doğruladığınızdan emin olun. Beş onmicrosoft.com etki alanıyla sınırlısınız ve şu anda oluşturulduktan sonra silinemezler.     

5. **Etki alanı ekle'yi** seçin. Başarıyla eklendiğinde bunu belirten bir ileti görürsünüz. 
    
    ![Başarıyla eklenen etki alanının ekran görüntüsü.](../../media/domain-added.png)



## <a name="make-your-new-onmicrosoftcom-domain-your-fallback-domain"></a>Yeni onmicrosoft.com etki alanınızı geri dönüş etki alanınız yapın


> [!NOTE]
> Geri dönüş etki alanınızı yeni bir onmicrosoft.com etki alanına dönüştürmeden önce, onmicrosoft.com SharePoint etki alanınızı değiştirmeyi düşünebilirsiniz. Ek bir onmicrosoft etki alanı oluşturup bunu geri dönüş etki alanınız olarak kullanmak SharePoint Online için yeniden adlandırma yapmaz. Mevcut SharePoint ve OneDrive URL'leriniz aynı kalır.  SharePoint etki alanı yeniden adlandırma önizlemesinde sağlanan PowerShell adımlarını kullanarak.onmicrosoft [SharePoint etki alanınızı](/sharepoint/change-your-sharepoint-domain-name) değiştirebilirsiniz (şu anda 1.000'den az sitesi olan tüm kiracılar tarafından kullanılabilir).

Yeni onmicrosoft.com etki alanınızı oluşturduktan sonra geri dönüş etki alanınızla değiştirmek için aşağıdakileri yapın.

1. Microsoft 365 yönetim merkezi **Ayarlar'ı** ve ardından **Etki Alanları'nı** seçin. 

2. Oluşturduğunuz yeni onmicrosoft.com etki alanını seçin.

    ![Bir etki alanı seçin.](../../media/onmicrosoft-domains-added.png) 

3. Etki alanının özellik sayfasında **Geri dönüş etki alanı yap'ı** seçin.
 
    ![Yeni bir geri dönüş etki alanı seçme işleminin ekran görüntüsü.](../../media/new-fallback.png) 

4. Sayfada geri dönüş etki alanınızın yeni etki alanına değiştiğini belirten bir ileti görüntülenir.

    ![Yeni geri dönüş etki alanı başarıyla eklendi.](../../media/fallback-success.png) 

## <a name="related-content"></a>İlgili içerik

[Etki alanları hakkında SSS](domains-faq.yml) (makale)</br>
[Etki alanı nedir?](../get-help-with-domains/what-is-a-domain.md) (makale)</br>
[Microsoft 365'te etki alanı adı satın alma](../get-help-with-domains/buy-a-domain-name.md) (makale)</br>
[Etki alanınıza bağlanmak için DNS kayıtları ekleme](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (makale)</br>
[Microsoft 365'i herhangi bir etki alanı kayıt şirketiyle ayarlamak için ad sunucularını değiştirme](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (makale)
