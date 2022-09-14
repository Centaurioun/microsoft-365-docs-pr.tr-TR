---
title: DNS kayıtları oluşturmak için ihtiyacınız olan bilgileri toplayın
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
- highpri
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Etki alanınızı Microsoft 365 aboneliğinize bağlamak için DNS kayıtları oluşturmak için ihtiyacınız olan değerleri/bilgileri toplayın.
ms.openlocfilehash: dbc6aa42351e8533d3af6be7f9c59866e2aa8358
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67663857"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS kayıtları oluşturmak için ihtiyacınız olan bilgileri toplayın

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>1. Adım: TXT kayıt değerini bulma ve doğrulama

::: moniker range="o365-worldwide"

1. Microsoft 365 yönetim merkezi **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetim merkezinde **Ayarlar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end
    
2. **Etki alanları** sayfasında etki alanınızı seçin ve ardından **Kurulumu başlat'ı** seçin. Eklemeniz gereken değeri görmek için etki alanları kurulum sihirbazına dönersiniz.
    
3. **Etki Alanı Doğrulama** sayfasında Etki **alanının DNS kayıtlarına TXT kaydı ekle'yi** ve ardından **Devam'ı** seçin.
    
4. Gösterilen **TXT değerini** kopyalayın. Şuna benzer: **MS=msXXXXXXXX**. 
    
5. [Etki alanınızı bağlamak için DNS kayıtları ekleme'ye](create-dns-records-at-any-dns-hosting-provider.md) gidin ve DNS barındırma sağlayıcınızın web sitesinde kayıt ekleme adımlarını izleyin.
    
6. DNS ana bilgisayarınızda TXT kaydı (veya MX kaydı) oluşturma adımlarını izleyin ve ardından etki alanını Microsoft 365'te yeniden doğrulayın.

7. Etki alanı Microsoft 365'te doğrulandıktan sonra TXT kaydını (veya MX kaydını) DNS ana bilgisayarınızdan kaldırın.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>2. Adım: E-posta ve daha fazlası için MX kayıt değerini bulma

::: moniker range="o365-worldwide"

1. Microsoft 365 yönetim merkezi **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end

::: moniker range="o365-21vianet"

1. Yönetim merkezinde **Ayarlar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Etki Alanları</a> sayfasına gidin.

::: moniker-end
    
2. **Etki Alanları** sayfasında etki alanınızı seçin.
    
3. **DNS'yi Yönet'i** seçin, **Diğer Seçenekler** > **Kendi DNS'nizi ekleyin'i** seçin ve eklenecek DNS kayıtlarını görmek için **Devam'ı** seçin.
    
    DNS barındırma sağlayıcınızda değişiklikleri yaparken bu bilgilerin kullanılabilir durumda olmasını istersiniz, çünkü böylelikle değerleri kopyalayıp yapıştırabilirsiniz.
    
    Sayfada listelenen DNS kayıtları grubu **Etki alanı amacı**'nın altında listelenen seçimlerinize bağlıdır.
    
4. [Etki alanınızı bağlamak için DNS kayıtları ekleme'ye](create-dns-records-at-any-dns-hosting-provider.md) gidin ve DNS barındırma sağlayıcınızın web sitesinde kayıt ekleme adımlarını izleyin.

5. DNS ana bilgisayarınızda kayıtları oluşturma adımlarını izleyin.

## <a name="related-content"></a>İlgili içerik

[Etki Alanları SSS](../setup/domains-faq.yml) (makale)\
[Kendi etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](find-and-fix-issues.md) (makale)\
[Etki alanlarını yönetme](/admin) (sayfa bağlantısı)