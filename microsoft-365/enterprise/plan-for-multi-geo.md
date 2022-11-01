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
ms.openlocfilehash: bc742ebc77f5b28fe10f071e66d2e9753f8ced47
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804936"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo planı

Bu kılavuz, Microsoft 365 _Kiracılarını_ _şirketin veri_ yerleşimi gereksinimlerini karşılama gereksinimine uygun olarak ek Coğrafyalara genişletilecek şekilde hazırlayan Kiracı yöneticileri için tasarlanmıştır.

Multi-Geo yapılandırmasında, Microsoft 365 _Kiracınız_ _Bir Birincil Sağlanan Coğrafya_ konumu ve bir veya daha fazla _Uydu Coğrafya_ konumundan oluşur. Bu, birden çok _Coğrafya_ konumuna yayılan tek bir _Kiracıdır_.

Multi-Geo yapılandırmasının temel kavramlarını anlamanıza yardımcı olmak için lütfen [Genel Bakış ve Tanımlar sayfasının Tanımlar bölümündeki terimleri](m365-dr-overview.md) gözden geçirin.

Multi-Geo'ya olanak sağlamak için dört temel adım gerekir:

1. _Microsoft 365 hizmet planında Multi-Geo Capabilities eklemek_ için hesap ekibinizle birlikte çalışın.

2. İstediğiniz _Uydu Coğrafya_ konumlarını seçin ve _bunları Kiracınıza_ ekleyin.

3. Kullanıcılarınızın Tercih Edilen Veri Konumunu istenen _Uydu Coğrafya_ konumuna ayarlayın. Bir kullanıcı için yeni bir OneDrive İş sitesi veya Exchange Online posta kutusu sağlandığında, bu kullanıcının PDL'sine sağlanır.

4. Kullanıcılarınızın mevcut OneDrive İş sitelerini _Birincil Sağlanan Coğrafya_ konumundan _uydu coğrafya_ veri konumlarına gerektiği gibi geçirin. (Exchange Online posta kutuları, kullanıcının PDL'sini ayarladığınızda otomatik olarak geçirilir.)

Bu adımların her biri hakkında ayrıntılı bilgi için bkz. [Microsoft 365 Multi-Geo'yi yapılandırma](multi-geo-tenant-configuration.md) .

OneDrive İş ve SharePoint Online sitelerini, Exchange Online posta kutularını ve Microsoft Teams'i barındırabileceğiniz _bir Uydu Coğrafya_ konumu olabilecek _Coğrafyalar_ için M365 Multi-Geo Genel Bakış sayfasının [Kullanılabilirlik bölümüne](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability) bakın. Multi-Geo'yı planladığınızda, Microsoft 365 _Kiracınıza_ eklemek istediğiniz konumların listesini yapın. Bir veya iki uydu konumuyla başlamanızı ve gerekirse kademeli olarak daha fazla coğrafi konuma genişletmenizi öneririz.

## <a name="best-practices"></a>En iyi uygulamalar

Bazı ilk testleri yapmak için Microsoft 365'te bir test kullanıcısı oluşturmanızı öneririz. Üretim kullanıcılarını Microsoft 365 Multi-Geo'ya eklemeye devam etmeden önce bu kullanıcıyla bazı test ve doğrulama adımlarını inceleyeceğiz.

Test kullanıcısıyla testi tamamladıktan sonra, OneDrive İş kullanan ve yeni bir coğrafi konumda Exchange Online ilk olarak BT departmanınızdan bir pilot grup seçin. Bu ilk grup için, henüz OneDrive İş olmayan kullanıcıları seçin. Bu ilk grupta beşten fazla kişi olmamasını ve toplu dağıtım yaklaşımını izleyerek aşamalı olarak genişletmenizi öneririz.

Microsoft 365'in OneDrive'ını hangi _Coğrafya_ konumunda sağlayabileceğini belirleyebilmesi için her kullanıcının _tercih edilen bir veri_ konumu (PDL) ayarlanmış olmalıdır. Kullanıcının tercih edilen veri konumu seçtiğiniz _Uydu Coğrafya_ konumlarından biriyle veya _Birincil Sağlanan Coğrafya_ ile eşleşmelidir. PDL alanı zorunlu olmasa da, tüm kullanıcılar için bir PDL'nin ayarlanmasını öneririz. PDL'siz bir kullanıcının iş yükleri _Birincil Sağlanan Coğrafya'da_ sağlanır.

Kullanıcılarınızın listesini oluşturun ve kullanıcı asıl adlarını (UPN) ve tercih edilen uygun veri konumu için konum kodunu ekleyin. Başlamak için test kullanıcınızı ve ilk pilot grubunuzu ekleyin. Yapılandırma yordamları için bu listeye ihtiyacınız olacaktır.

Kullanıcılarınız bir şirket içi Active Directory sisteminden Azure Active Directory'ye eşitlenmişse, tercih edilen veri konumunu Active Directory özniteliği olarak ayarlamanız ve Azure Active Directory Connect kullanarak eşitlemeniz gerekir. Azure AD PowerShell kullanarak eşitlenmiş kullanıcılar için tercih edilen veri konumunu doğrudan yapılandıramazsınız. Active Directory'de PDL'yi ayarlama ve Eşitleme adımları [Azure Active Directory Connect eşitlemesi: Microsoft 365 kaynakları için tercih edilen veri konumunu yapılandırma](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation) bölümünde ele alınmıştır.

SharePoint Online ve OneDrive İş ayarlarının ve hizmetlerinin çoğu çok coğrafi olarak algılandığından, Çok Coğrafi Kiracının yönetimi çok coğrafi olmayan bir _Kiracıdan_ _farklı olabilir._ Yapılandırmanıza devam etmeden önce [Çok coğrafi ortamı yönetme'yi](administering-a-multi-geo-environment.md) gözden geçirmenizi öneririz.

[Multi-Geo ortamında](multi-geo-user-experience.md) son kullanıcılarınızın deneyimi hakkında ayrıntılı bilgi için Çok coğrafi ortamda kullanıcı deneyimi makalesini okuyun.

Microsoft 365 Multi-Geo'yı yapılandırmaya başlamak için bkz. [Microsoft 365 Multi-Geo'yı yapılandırma](multi-geo-tenant-configuration.md).

Yapılandırmayı tamamladıktan sonra, kullanıcılarınızın tercih ettikleri veri konumlarından çalışmasını sağlamak için [kullanıcılarınızın OneDrive kitaplıklarını gerektiği gibi geçirmeyi](move-onedrive-between-geo-locations.md) unutmayın.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Multi-Geo eBulma yapılandırması](./multi-geo-ediscovery-configuration.md)
