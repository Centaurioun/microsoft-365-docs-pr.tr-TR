---
title: LinkedIn verilerini arşivleye bağlayıcı ayarlama
description: Yöneticilerin LinkedIn Şirket Sayfasından Microsoft 365'e veri aktarmak için yerel bağlayıcı & nasıl kurabileceğini öğrenin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 260409689360bf2bc24c28b619dca6fd55833288
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68534046"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>LinkedIn verilerini arşivleye bağlayıcı ayarlama

LinkedIn Şirket sayfalarından verileri içeri aktarmak ve arşivlemek için Microsoft Purview uyumluluk portalı bir bağlayıcı kullanın. Bağlayıcıyı ayarlayıp yapılandırdıktan sonra, her 24 saatte bir belirli LinkedIn Şirket sayfasının hesabına bağlanır. Bağlayıcı, Şirket sayfasına gönderilen iletileri e-posta iletisine dönüştürür ve ardından bu öğeleri Microsoft 365'teki bir posta kutusuna aktarır.

LinkedIn Şirket sayfası verileri bir posta kutusunda depolandıktan sonra, LinkedIn verilerine Dava Tutma, İçerik Arama, In-Place Arşivleme, Denetim ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Örneğin, İçerik Arama'yı kullanarak bu öğeleri arayabilir veya depolama posta kutusunu Microsoft Purview eKeşif (Premium) durumdaki bir koruyucuyla ilişkilendirebilirsiniz. Microsoft 365'te LinkedIn verilerini içeri aktarmak ve arşivlerken bağlayıcı oluşturmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- LinkedIn Şirket Sayfası bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Arşivlediğiniz LinkedIn Şirket Sayfası'nın yöneticisi olan linkedIn kullanıcı hesabının oturum açma kimlik bilgilerine (e-posta adresi veya telefon numarası ve parola) sahip olmanız gerekir. Bağlayıcıyı ayarlarken LinkedIn'de oturum açmak için bu kimlik bilgilerini kullanırsınız.

- LinkedIn bağlayıcısı tek bir günde toplam 200.000 öğeyi içeri aktarabilir. Bir günde 200.000'den fazla LinkedIn öğesi varsa, bu öğelerin hiçbiri Microsoft 365'e aktarılamaz.

## <a name="create-a-linkedin-connector"></a>LinkedIn bağlayıcısı oluşturma

1. Veri **bağlayıcıları** > **LinkedIn Şirket sayfaları'na**<https://compliance.microsoft.com> gidin ve bunu seçin.

2. **LinkedIn şirket sayfaları** ürün sayfasında **Bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. **LinkedIn ile oturum aç** sayfasında **LinkedIn ile oturum aç'ı** seçin.

   LinkedIn oturum açma sayfası görüntülenir.

   ![LinkedIn oturum açma sayfası.](../media/LinkedInSigninPage.png)

5. LinkedIn oturum açma sayfasında, arşivlemesini istediğiniz şirket sayfasıyla ilişkili LinkedIn hesabının e-posta adresini (veya telefon numarasını) ve parolasını girin ve oturum **aç'ı** seçin.

   Oturum açtığınız hesapla ilişkilendirilmiş tüm LinkedIn Şirket Sayfalarının listesiyle bir sihirbaz sayfası görüntülenir. Bağlayıcı yalnızca bir şirket sayfası için yapılandırılabilir. Kuruluşunuzun birden çok LinkedIn Şirket Sayfası varsa, her biri için bir bağlayıcı oluşturmanız gerekir.

   ![LinkedIn Şirket Sayfalarının listesini içeren bir sayfa görüntülenir.](../media/LinkedInSelectCompanyPage.png)

6. Öğeleri arşivlemesini istediğiniz şirket sayfasını seçin ve ardından **İleri'yi** seçin.

7. **Depolama konumu seçin** sayfasında, kutudan öğesini seçin, LinkedIn öğelerinin içeri aktarılacağı Microsoft 365 posta kutusunun e-posta adresini seçin ve ardından **İleri'yi** seçin. Öğeler bu posta kutusundaki gelen kutusu klasörüne aktarılır. Kullanılan posta kutusunun Exchange Online Plan 1 veya Plan 2 lisansı olmalıdır.

8. Bağlayıcı ayarlarını gözden geçirmek için **İleri'yi** seçin ve ardından bağlayıcı kurulumunu tamamlamak için **Son'u** seçin.

Bağlayıcıyı oluşturduktan sonra, yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına geri dönebilirsiniz (bağlayıcı listesini güncelleştirmek için gerekirse **Yenile'yi** seçin). **Durum** sütunundaki değer **Başlamayı bekliyor** şeklindedir. İlk içeri aktarma işleminin başlatılması 24 saat kadar sürer. Bağlayıcı ilk kez çalıştırılıp LinkedIn öğelerini içeri aktardıktan sonra bağlayıcı 24 saatte bir çalıştırılır ve linkedin şirket sayfasında son 24 saat içinde oluşturulan tüm yeni öğeleri içeri aktarır.

Diğer ayrıntıları görüntülemek için **Veri bağlayıcıları** sayfasındaki listeden bağlayıcıyı seçerek açılır sayfayı görüntüleyin. **Durum'un** altında, görüntülenen tarih aralığı bağlayıcı oluşturulduğunda seçilen yaş filtresini gösterir.

## <a name="more-information"></a>Daha fazla bilgi

LinkedIn öğeleri, Microsoft 365'teki depolama posta kutusunun gelen kutusundaki LinkedIn alt klasörüne aktarılır. Bunlar e-posta iletileri olarak görünür.
