---
title: Uygulama başlatıcıya özel kutucuklar ekleme
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Uygulama başlatıcıya özel kutucuklar ekleyerek e-postanıza, belgelerinize, uygulamalarınıza, SharePoint sitelerinize, dış sitelerinize ve diğer kaynaklarınıza hızlı bağlantılar oluşturun.
ms.openlocfilehash: b7e23f8f21ea99232f7051b0cbeaaad5ad699095
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166757"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Uygulama başlatıcıya özel kutucuklar ekleme

Microsoft 365'te, Uygulama başlatıcıyı kullanarak e-postanıza, takvimlerinize, belgelerinize ve uygulamalarınıza hızlı ve kolay bir şekilde ulaşabilirsiniz ([daha fazla bilgi edinin](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Bunlar, Microsoft 365 ile edindiğiniz uygulamaların yanı sıra [SharePoint Mağazası'ndan](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) veya [Azure AD](/previous-versions/office/office-365-api/) eklediğiniz özel uygulamalardır.
  
You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site. 
  
![Uygulama başlatıcı.](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Uygulama başlatıcıya özel kutucuk ekleme

1. Yönetim merkezinde Genel Yönetici olarak oturum açın, **Ayarlar** > **Kuruluş Ayarları'na** gidin ve **Kuruluş profili** sekmesini seçin.
    
2. **Kuruluş profili** sekmesinde **Özel uygulama başlatıcı kutucukları'nı** seçin.
  
3. **Özel kutucuk ekle'yi** seçin. 
  
4. Yeni kutucuk için **Kutucuk adı** girin. Bu ad, kutucuk içinde görünür. 
    
5. Kutucuk için **web sitesinin URL'sini** girin. Bu, kullanıcılarınızın uygulama başlatıcıdaki kutucuğu seçtiklerinde gitmesini istediğiniz konumdur. URL'de HTTPS kullanın.

    > [!TIP]
    > Bir SharePoint sitesi için kutucuk oluşturuyorsanız, bu siteye gidin, URL'yi kopyalayın ve buraya yapıştırın. Varsayılan ekip sitenizin URL'si şöyle görünür: `https://<company_name>.sharepoint.com` 
  
6. Kutucuk için **resmin URL'sini** girin. Resim, Uygulamalarım sayfasında ve uygulama başlatıcısında görüntülenir.

    > [!TIP]
    > Görüntü 60x60 piksel olmalıdır ve kimlik doğrulaması gerektirmeden kuruluşunuzdaki herkesin kullanımına açık olmalıdır.

7. Kutucuk için bir **Açıklama** girin. Uygulamalarım sayfasında kutucuğu seçip **Uygulama ayrıntıları'nı** seçtiğinizde bunu görürsünüz. 
  
8. Özel kutucuğu oluşturmak için **Değişiklikleri kaydet'i** seçin. 
    
    Özel kutucuğunuz, siz ve kullanıcılarınız için **Tümü** sekmesindeki uygulama başlatıcıda önümüzdeki 24 saat içinde görünür. 

    > [!NOTE]
    > Önceki adımlarda oluşturulmuş özel kutucuğu görmüyorsanız, size atanmış bir Exchange Online posta kutunuzun olduğundan ve posta kutunuzda en az bir defa oturum açtığınızdan emin olun. Bu adımlar Microsoft 365'teki özel kutucuklar için gereklidir. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Yönetim merkezinde **Ayarlar** > **Kuruluş Ayarları** > **Kuruluş profili** sekmesine gidin.
    
2. **Kuruluş profili** sayfasında **Özel Uygulama başlatıcı kutucukları'na** gidin. **Özel Kutucuğunuzun** yanındaki üç noktayı ve **Özel kutucuğu düzenle'yi** seçin.

3. Özel kutucuk için **Kutucuk adı**, **URL**, **Açıklama** veya **Resim URL'si**'ni güncelleştirin ([Uygulama başlatıcıya özel kutucuk ekleme](#add-a-custom-tile-to-the-app-launcher) bakın).
    
4. **Kapat'ı Güncelleştir'i** \> seçin. 
    
Özel kutucukları silmek için **, Özel kutucuklar** penceresinde kutucuğu seçin, **Kutucuğu** >  kaldır **Sil'i** seçin. 
  
## <a name="next-steps"></a>Sonraki adımlar

 Microsoft 365'in görünümünü kuruluşunuzun markasıyla eşleşecek şekilde özelleştirmek için bkz. [Microsoft 365 temasını özelleştirme](../setup/customize-your-organization-theme.md).

## <a name="related-content"></a>İlgili içerik

[Uygulamaları kullanıcılarınızın uygulama başlatıcısına sabitleme](pin-apps-to-app-launcher.md) (makale)\
[İş için Microsoft 365 kullanıcılarınızı en son Office istemcisine](../setup/upgrade-users-to-latest-office-client.md) yükseltin (makale)\
[Yönetim merkezinde eklentileri yönetme](../manage/manage-addins-in-the-admin-center.md) (makale)
