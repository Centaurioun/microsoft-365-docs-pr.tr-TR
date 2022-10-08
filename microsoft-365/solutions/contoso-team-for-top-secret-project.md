---
title: Contoso Corporation'ın çok gizli projesi için yalıtılmış ekip
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- highpri
- M365-security-compliance
ms.custom: Ent_Architecture
description: "Özet: Contoso'nun yeni bir ürün ve hizmet paketi geliştirmek için çok gizli bir proje için güvenlik yalıtımına sahip bir ekibi nasıl kullandığı."
ms.openlocfilehash: 33a13b778c51690200e5e590fb2c56faeff8de0f
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67987136"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation'ın çok gizli projesi için yalıtılmış ekip

Contoso'nun CEO'su, bir yöneticinin kuruluş dışından sonraki beş yıl içinde Contoso'nun kârını iki katına çıkarabilecek yeni bir ürün ve hizmet paketinin geliştirilmesini emretti. İş, mühendislik ve pazar planını geliştirmeye yönelik çok gizli proje **Project 2X** olarak adlandırıldı ve şirket genelinde önemli personel işe alındı. 

Araştırma ve geliştirme zaman çizelgeleri sıkıydı, bu da işbirliğinin verimli olması ve güvenli toplantılar, devam eden konuşmalar ve dosya depolama sağlaması gerektiği anlamına geliyordu.

Project 2X için elde edilen teslim edilebilir öğeler iş planları, ürün ve mühendislik belirtimleri ile Word, Excel ve PowerPoint dosyaları biçiminde pazarlama malzemeleri ve zamanlamalarıydı. 

Hassas doğası gereği bu dosyalara erişim şunlardır:

- Project 2X ekip üyeleri ve üst düzey liderlik ile sınırlıdır.
- Dosyalar güvenli klasörlerinin dışına dağıtılmış olsa bile yalnızca Project 2X ekip üyelerine ve üst düzey liderlere erişim izni verme izinleriyle şifrelenir ve korunur.

Contoso BT personeli, Project 2X ve bu adımlar için [güvenlik yalıtımına sahip bir ekip](secure-teams-security-isolation.md) kullandı.

## <a name="step-1-created-a-private-team"></a>1. Adım: Özel ekip oluşturma

İlk olarak, ekip için temel alınan SharePoint sitesine erişimi korumak için Contoso BT yöneticileri [önerilen SharePoint erişim ilkelerini](../security/office-365-security/sharepoint-file-access-policies.md) yapılandırdı.

Ardından Contoso BT yöneticisi Project 2X adlı yeni bir özel ekip oluşturdu ve Project 2X personelinin kullanıcı hesaplarını üye olarak ekledi. Ayrıca ekibi yalnızca Project 2X ekip sahiplerinin özel kanallar oluşturabilmesi için yapılandırdılar.

Yapılandırma ayrıntıları için bkz. [Özel ekip oluşturma](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>2. Adım: Project 2X ekibi için duyarlılık etiketi oluşturuldu

Contoso yöneticileri **, Project 2X** adlı şu yeni bir duyarlılık etiketi oluşturdu:

- Şifreleme etkinleştirildi.
- Project 2X Microsoft 365 grubu için izin Co-Author izinler.
- Üst Düzey Liderlik grubu için İzin Verilen Görüntüleyici izinleri.
- Yönetilmeyen cihazlara erişim engellendi.

Temel alınan Project 2X SharePoint sitesinin **Belgeler** bölümündeki dosyalar şu şekilde korundu:

- Yalnızca Project 2X Microsoft 365 grubunun üyelerine tam izin veren ve Üst Düzey Liderlik grubuna yönelik okuma izinlerine izin veren site izinleri.
- Siteden taşındığında veya kopyalandığında dosyayla birlikte gelen şifreleme ve izinlere sahip Project 2X duyarlılık etiketi.

Yapılandırma ayrıntıları için bkz. [Duyarlılık etiketi oluşturma](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>3. Adım: Temel alınan SharePoint sitesini yapılandırdı

İlk olarak, ekip için temel alınan SharePoint sitesine erişimi korumak için Contoso BT yöneticileri [önerilen SharePoint erişim ilkelerini](../security/office-365-security/sharepoint-file-access-policies.md) yapılandırdı.

Ardından site için ek izin ayarları yapılandırdılar:

- Project 2X grup üyelerinin siteye erişimi paylaşmasını önlemek için. Yapılandırma ayrıntıları için bkz. [Güvenlik yalıtımı olan bir ekip için SharePoint ayarları](secure-teams-security-isolation.md#sharepoint-settings).
- Üst Düzey Liderlik grubu için Okuma izinleri için.

Daha sonra, Project 2X grup üyelerinin siteye erişimi paylaşmasını önlemek için site için ek izin ayarları yapılandırdılar. 

Project 2X için özel kanallar oluşturulurken, grup sahibi konuk paylaşımını devre dışı bırakmış ve varsayılan paylaşım bağlantısını **Belirli kişiler** değerine ayarlamıştır.

Project 2X ekibinin güvenlik yalıtımıyla elde edilen yapılandırması aşağıdadır.

![Project 2X ekibinin sonuçta elde edilen yapılandırması.](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>4. Adım: Eğitilmiş Project 2X ekip üyeleri

Contoso güvenlik personeli Project 2X ekip üyelerini aşağıdaki adımlardan geçen zorunlu bir kursta eğitti:

- Yeni Project 2X ekibine erişme, toplantıları ve sohbetleri kullanma ve ekip dosyaları üzerinde işbirliği yapma.
- Ekipte yeni dosyalar oluşturma ve yerel olarak oluşturulan yeni dosyaları karşıya yükleme.
- Project 2X duyarlılık etiketiyle dosyaları etiketleme.
- Project 2X etiketinin bir dosyayı ekipten ayrıldığında bile nasıl koruyup koruyup koruyamayacaklarını gösteren bir gösterim.

Sonuç olarak, Project 2X ekip üyelerinin sohbetler, toplantılar ve dosyalar için güvenli bir ortamda işbirliği yapmış olduğu güvenli bir ortam elde edildi.

Aşağıda, Project 2X duyarlılık etiketinin atandığı temel Project 2X sitesinde depolanan bir dosya örneği verilmiştir.

![Temel alınan Project 2X sitesinde depolanan bir dosya örneği.](../media/contoso-team-for-top-secret-project-example.png)

Birkaç örnekte, Project 2X ekip üyeleri çevrimdışı çalışma için Project 2X etiketiyle korunan dosyaları yerel bir sürücüye indirdi. 

Ancak, bunları açarken kimlik bilgileri istendikten sonra, hatalarını fark ettiler ve onları sildiler.

Teams'in işbirliği ortamı ve Microsoft 365'in güvenlik özellikleri nedeniyle Project 2X'in ayrıntıları proje süresi boyunca gizli tutuldu. Contoso planlarını duyurdu ve yeni ürün ve hizmetleri müşterilerinin ve yatırımcılarının ve rakiplerinin zevkine sunma sürecinde.

## <a name="next-step"></a>Sonraki adım

Kuruluşunuzda [güvenlik yalıtımı olan bir ekip dağıtın](secure-teams-security-isolation.md).

