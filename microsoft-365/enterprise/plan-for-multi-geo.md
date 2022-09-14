---
title: Microsoft 365 Multi-Geo planı
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Microsoft 365 Multi-Geo, çoklu coğrafi konumun nasıl çalıştığı ve veri depolama için hangi coğrafi konumların kullanılabilir olduğu hakkında bilgi edinin.
ms.openlocfilehash: 6237408442a33a3a54ba5267986a9e33219c4239
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670377"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo planı

Bu kılavuz, Microsoft 365 kiracılarını, veri yerleşimi gereksinimlerini karşılamak üzere şirketin varlığına uygun olarak ek coğrafyalara genişletilecek şekilde hazırlayan çok uluslu şirketlerin (MNC) yöneticileri için tasarlanmıştır.

Çok coğrafi bir yapılandırmada, Microsoft 365 kiracınız merkezi bir konumdan ve bir veya daha fazla uydu konumundan oluşur. Bu, birden çok coğrafi konuma yayılan tek bir kiracıdır. Coğrafi konumlar da dahil olmak üzere kiracı bilgileriniz Azure Active Directory'de (Azure AD) hakimdir.

Yapılandırmanın temel kavramlarını anlamanıza yardımcı olacak çok coğrafi terimlerden bazıları şunlardır:

- **Kiracı** – Microsoft 365'te bir kuruluşun temsilidir ve genellikle kendisiyle ilişkilendirilmiş bir veya daha fazla etki alanı vardır (örneğin, https://contoso.sharepoint.com).

- **Coğrafi konumlar** – Microsoft 365 kiracısında veri barındırmak için kullanılabilen coğrafi konumlar.

- **Uydu konumları** – Microsoft 365 kiracınızda veri barındırmak için yapılandırdığınız ek coğrafi konumlar. Çok coğrafi kiracılar, Kuzey Amerika ve Avrupa gibi birden fazla coğrafi konuma yayılmıştır.

- **Tercih Edilen Veri Konumu (PDL)** – Tek bir kullanıcının Exchange ve OneDrive verilerinin depolandığı coğrafi konum. Bu, yönetici tarafından kiracı için yapılandırılmış coğrafi konumlardan herhangi birine ayarlanabilir. Zaten bir OneDrive sitesi olan bir kullanıcının PDL'sini değiştirirseniz, OneDrive verilerinin otomatik olarak yeni coğrafi konuma taşınmadığını unutmayın. Daha fazla bilgi için bkz. [OneDrive kitaplığını farklı bir coğrafi konuma taşıma](move-onedrive-between-geo-locations.md) . Exchange posta kutuları varsa, posta kutusu otomatik olarak yeni tercih edilen veri konumuna taşınır.

Multi-Geo'ya olanak sağlamak için dört temel adım gerekir:

1. _Microsoft 365 hizmet planında Multi-Geo Capabilities eklemek_ için hesap ekibinizle birlikte çalışın.

2. İstediğiniz uydu konumlarını seçin ve bunları kiracınıza ekleyin.

3. Kullanıcılarınızın tercih edilen veri konumunu istenen uydu konumuna ayarlayın. Bir kullanıcı için yeni bir OneDrive sitesi veya Exchange posta kutusu sağlandığında, bu posta kutusu PDL'sine sağlanır.

4. Kullanıcılarınızın mevcut OneDrive sitelerini merkezi konumdan tercih ettikleri veri konumuna gerektiği gibi geçirin. (Kullanıcının PDL'sini ayarladığınızda Exchange posta kutuları otomatik olarak geçirilir.)

Bu adımların her biri hakkında ayrıntılı bilgi için bkz. [Microsoft 365 Multi-Geo'yi yapılandırma](multi-geo-tenant-configuration.md) .

> [!IMPORTANT]
> Microsoft 365 Multi-Geo'nun performans iyileştirmesi için tasarlanmadığını, veri yerleşimi gereksinimlerini karşılamak için tasarlandığını unutmayın. Microsoft 365 için performans iyileştirmesi hakkında bilgi için bkz. [Microsoft 365 için ağ planlama ve performans ayarlama](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) veya destek grubunuza başvurun.

Aşağıdaki konumlardan herhangi birini, OneDrive ve SharePoint sitelerini ve Exchange posta kutularını barındırabileceğiniz uydu konumları olacak şekilde yapılandırabilirsiniz. Birden çok coğrafi alanı planladığınızda, Microsoft 365 kiracınıza eklemek istediğiniz konumların listesini yapın. Bir veya iki uydu konumuyla başlamanızı ve gerekirse kademeli olarak daha fazla coğrafi konuma genişletmenizi öneririz.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Multi-geo'yı yapılandırırken, Microsoft 365'e geçiş yaparken şirket içi altyapınızı birleştirme fırsatını değerlendirin. Örneğin, Singapur ve Malezya'da şirket içi çiftlikleriniz varsa, veri yerleşimi gereksinimlerinin bunu yapmanıza olanak sağlaması koşuluyla bunları APC uydu konumunda birleştirebilirsiniz.

## <a name="best-practices"></a>En iyi uygulamalar

Bazı ilk testleri yapmak için Microsoft 365'te bir test kullanıcısı oluşturmanızı öneririz. Üretim kullanıcılarını Microsoft 365 Multi-Geo'ya eklemeye devam etmeden önce bu kullanıcıyla bazı test ve doğrulama adımlarını inceleyeceğiz.

Test kullanıcısıyla testi tamamladıktan sonra, OneDrive ve Exchange'i yeni bir coğrafi konumda ilk kullanan kişi olmak için bt departmanınızdan bir pilot grup seçin. Bu ilk grup için henüz OneDrive'ı olmayan kullanıcıları seçin. Bu ilk grupta beşten fazla kişi olmamasını ve toplu dağıtım yaklaşımını izleyerek aşamalı olarak genişletmenizi öneririz.

Microsoft 365'in OneDrive'ını hangi coğrafi konumda sağlayabileceğinizi belirleyebilmesi için her kullanıcının *tercih edilen bir veri konumu* (PDL) ayarlanmış olmalıdır. Kullanıcının tercih ettiği veri konumu seçtiğiniz uydu konumlarından biriyle veya merkezi konumunuzla eşleşmelidir. PDL alanı zorunlu olmasa da, tüm kullanıcılar için bir PDL'nin ayarlanmasını öneririz. PDL olmayan bir kullanıcının iş yükleri merkezi konumda sağlanır.

Kullanıcılarınızın listesini oluşturun ve kullanıcı asıl adlarını (UPN) ve tercih edilen uygun veri konumu için konum kodunu ekleyin. Başlamak için test kullanıcınızı ve ilk pilot grubunuzu ekleyin. Yapılandırma yordamları için bu listeye ihtiyacınız olacaktır.

Kullanıcılarınız bir şirket içi Active Directory sisteminden Azure Active Directory'ye eşitlenmişse, tercih edilen veri konumunu Active Directory özniteliği olarak ayarlamanız ve Azure Active Directory Connect kullanarak eşitlemeniz gerekir. Azure AD PowerShell kullanarak eşitlenmiş kullanıcılar için tercih edilen veri konumunu doğrudan yapılandıramazsınız. Active Directory'de PDL'yi ayarlama ve Eşitleme adımları [Azure Active Directory Connect eşitlemesi: Microsoft 365 kaynakları için tercih edilen veri konumunu yapılandırma](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation) bölümünde ele alınmıştır.

SharePoint ve OneDrive ayarlarının ve hizmetlerinin çoğu çok coğrafi olarak algılandığından, çok coğrafi bir kiracının yönetimi çok coğrafi olmayan bir kiracıdan farklı olabilir. Yapılandırmanıza devam etmeden önce [Çok coğrafi ortamı yönetme'yi](administering-a-multi-geo-environment.md) gözden geçirmenizi öneririz.

Son kullanıcılarınızın [çok coğrafi ortamdaki](multi-geo-user-experience.md) deneyimi hakkında ayrıntılı bilgi için Çok coğrafi ortamda kullanıcı deneyimi makalesini okuyun.

Microsoft 365 Multi-Geo'yı yapılandırmaya başlamak için bkz. [Microsoft 365 Multi-Geo'yı yapılandırma](multi-geo-tenant-configuration.md).

Yapılandırmayı tamamladıktan sonra, kullanıcılarınızın tercih ettikleri veri konumlarından çalışmasını sağlamak için [kullanıcılarınızın OneDrive kitaplıklarını gerektiği gibi geçirmeyi](move-onedrive-between-geo-locations.md) unutmayın.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Multi-Geo eBulma yapılandırması](./multi-geo-ediscovery-configuration.md)
