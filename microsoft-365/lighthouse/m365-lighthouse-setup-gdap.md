---
title: Müşterileriniz için GDAP'yı ayarlama
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: magarlan, chrigreen
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için müşterileriniz için GDAP'yi ayarlamayı öğrenin.
ms.openlocfilehash: b7baa473b19c2431edf1f5e85c9f106cc60e962d
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785913"
---
# <a name="set-up-gdap-for-your-customers"></a>Müşterileriniz için GDAP'yı ayarlama


> [!NOTE]
> Bu özellik müşterilerimiz için farklı hızlarda kullanıma sunmaktadır. Bu özelliği henüz görmüyorsanız, yakında görmeniz gerekir.

Microsoft 365 Lighthouse eklenen iş ortakları artık lisansları veya boyutları ne olursa olsun Lighthouse aracılığıyla tüm müşterilerini Ayrıntılı Yönetici Ayrıcalıkları (GDAP) ile ayarlayabilir. Lighthouse, iş ortaklarının kuruluşlarını hızla GDAP'a geçirmelerini ve müşterilere temsilci erişimi için en az ayrıcalık yolculuğuna başlamalarını sağlar. Yönettiğiniz müşteri kiracıları için kuruluşunuzu GDAP ile ayarlayarak, kuruluşunuzdaki kullanıcılar müşteri kiracılarını güvende tutarken işlerini yapmak için gerekli izinlere sahip olur.

DAP veya GDAP aracılığıyla temsilci erişimi, müşterilerin Lighthouse'a tamamen dahil olması için bir önkoşuldur. Bu nedenle, Lighthouse'da müşterilerinizi yönetmenin ilk adımı GDAP ilişkileri oluşturmak olabilir.

GDAP kurulum işlemi sırasında, kuruluşunuzdaki çalışanların iş işlevlerinin katmanlarına roller atayacak ve ardından bu katmanlı rolleri müşteri grupları için kullanıcılarla belirli güvenlik gruplarına atayacak GDAP şablonları oluşturacaksınız. GDAP rollerinin kapsamı [yerleşik Azure AD roller](/azure/active-directory/roles/permissions-reference) olarak belirlenmiştir ve GDAP'yi ayarladığınızda her katman için gereken bir dizi rol için öneriler görürsünüz.

## <a name="before-you-begin"></a>Başlamadan önce

- Kendi kiracınızda belirli izinlere sahip olmanız gerekir:

  - GDAP güvenlik grupları oluşturmak ve kullanıcı eklemek için Genel Yönetici, Kullanıcı Yöneticisi veya Grup Yöneticisi'nin GDAP rollerine erişimi olan kullanıcıları ayarlaması gerekir. Bu rolleri Azure Active Directory'de (ADD) atayabilirsiniz.

    - Tam zamanında (JIT) Yalnızca katmanını etkinleştirmek için Genel Yöneticiye veya Kullanıcı Yöneticisi ve Ayrıcalık Rolü Yöneticisi birleşimine sahip olmanız gerekir.

  - GDAP ilişkilerini oluşturmak ve tamamlamak için İş Ortağı Merkezi'ndeki Yönetici Aracıları grubunun üyesi olmanız gerekir.

- İş Ortağı Merkezi'nde kurumsal bayi ilişkisi veya mevcut bir temsilci ilişkisi (DAP veya GDAP) ile ayarlanmış olan müşteriler Lighthouse iş ortağı tarafından yönetilebilir.

- Yalnızca JIT katman izinlerini etkinleştirmek için bir Azure AD P2 lisansına da sahip olmanız gerekir.

## <a name="set-up-gdap-for-the-first-time"></a>GDAP'yi ilk kez ayarlama

GDAP'yi ilk kez ayarlarken, aşağıdaki bölümleri sırayla tamamlamanız gerekir. İşlem tamamlandıktan sonra geri dönüp istediğiniz bölümü gerektiği gibi düzenleyebilirsiniz.

Başlamak için: 

1. Lighthouse'un sol gezinti bölmesinde **Giriş'i seçin.**

2. **Kuruluşunuz için GDAP'yi ayarlama kartında** **Kurulumu başlat'ı seçin.**

3. Aşağıdaki bölümleri sırayla tamamlayın.

    [1. Adım: İzin katmanlarını tanımlama](#step-1-define-tiers-of-permissions)

    [2. Adım: GDAP şablonları oluşturma](#step-2-create-gdap-templates)

    [3. Adım: Güvenlik grupları oluşturma](#step-3-create-security-groups)

    [4. Adım: Müşteri kiracılarını atama](#step-4-assign-customer-tenants)

    [5. Adım: Ayarları gözden geçirme](#step-5-review-settings)

### <a name="step-1-define-tiers-of-permissions"></a>1. Adım: İzin katmanlarını tanımlama

Çalışanlarınızın iş işlevlerine göre her katman için gereken rolleri seçin.

1. **İzin katmanlarını tanımla** sayfasında, çalışanlarınızın iş işlevlerine göre her katman için gereken rolleri seçin. Yapabilecekleriniz

    - Önerilen yapılandırmaları benimseme veya

    - Her katmana el ile bir rol atayın.

2. Sonraki bölüme gitmek için **İleri'yi** seçin veya Kaydet **ve kapat'ı** seçerek ayarlarınızı kaydedin ve GDAP Kurulumu'dan çıkın.

Katmanları kuruluş gereksinimlerinize uyacak şekilde yeniden adlandırabilirsiniz. Önerilerin içindeki her katmandan rolleri kaldırabilirsiniz. Bazı roller farklı katmanlara eklenemez; örneğin, Yalnızca JIT katmanındaki roller başka bir katmana eklenemez.

### <a name="step-2-create-gdap-templates"></a>2. Adım: GDAP şablonları oluşturma

GDAP şablonu bir koleksiyondur:

- Rollere sahip katmanlar

- Katman başına güvenlik grupları

- Her güvenlik grubundaki kullanıcılar
 
GDAP şablonu oluşturmak için:

1. **GDAP şablonları oluştur** sayfasında **Şablon oluştur'u** seçin.

2. Şablon bölmesinde, uygun alanlara şablon adını ve açıklamasını girin.

3. Listeden bir veya daha fazla katman seçin.

4. **Kaydet**'i seçin.

5. Sonraki bölüme gitmek için **İleri'yi** seçin veya kaydet **ve kapat'ı** seçerek ayarlarınızı kaydedin ve GDAP Kurulumu'dan çıkın.

### <a name="step-3-create-security-groups"></a>3. Adım: Güvenlik grupları oluşturma

Her şablon için katman başına en az bir güvenlik grubu gerekir. İlk şablon için yeni bir güvenlik grubu oluşturacaksınız, ancak sonraki şablonlarda isterseniz grupları yeniden kullanabilirsiniz.

1. **Güvenlik grupları oluştur** sayfasında **Güvenlik grubu oluştur'u** seçin.

2. Güvenlik grubu bölmesinde ad ve açıklama girin.

3. **Kullanıcı ekle'yi** seçin.

4. Kullanıcı ekle listesinden, bu güvenlik grubuna eklemek istediğiniz kullanıcıları seçin.

5. **Kaydet'i seçin.**

6. **Kaydet'i** yeniden seçin.

7. Sonraki bölüme gitmek için **İleri'yi** seçin veya Kaydet **ve kapat'ı** seçerek ayarlarınızı kaydedin ve GDAP Kurulumu'dan çıkın.

### <a name="step-4-assign-customer-tenants"></a>4. Adım: Müşteri kiracılarını atama

Her şablona müşteri grupları atayın. Her müşteri yalnızca bir şablona atanabilir, bu nedenle seçildikten sonra bu müşteri kiracısı sonraki şablonlarda seçenek olarak görüntülenmez.

Bir müşteri kiracısını yeniden atamak istiyorsanız GDAP Kurulumu'nu yeniden çalıştırın ve mevcut atamadan bu müşterinin seçimini kaldırın. Ardından bunu farklı bir şablona yeniden atayabilirsiniz. Sağ üst köşedeki arama kutusunu kullanarak listeyi filtreleyebilirsiniz.

1. **Müşteri kiracıları ata** sayfasında, oluşturduğunuz güvenlik grubuyla ilişkilendirmek istediğiniz kiracıları seçin.

2. Sonraki bölüme gitmek için **İleri'yi** seçin veya Kaydet **ve kapat'ı** seçerek ayarlarınızı kaydedin ve GDAP Kurulumu'dan çıkın.

### <a name="step-5-review-settings"></a>5. Adım: Ayarları gözden geçirme

1. **Ayarları gözden geçir** sayfasında, oluşturduğunuz ayarları gözden geçirin ve **son'u seçin.**

2. **Bitti'yi seçin.**

Müşteri kiracılarından herhangi biri zaten bir DAP ilişkisine sahipse, onay yok penceresi sırasında bu ayarlar otomatik olarak uygulanır. DAP'ı olmayan müşteriler için veya onay penceresi kapatılmadıysa **Son'un** seçilmesi sizi her müşteri için gereken onay bağlantılarının oluşturulduğu son sayfaya götürür. Müşteri GDAP ilişkisine onay verdikten sonra, ayarların geri kalanı otomatik olarak uygulanır.

GDAP kurulumunu tamamladıktan sonra katmanlarda, rollerde, güvenlik gruplarında veya şablonlarda güncelleştirme veya değişiklik yapmak için farklı adımlara gidebilirsiniz. GDAP ilişkileri İş Ortağı Merkezi'nde de görünür ve güvenlik grupları da Azure AD görünür.

## <a name="related-content"></a>İlgili içerik

[İzinlere genel bakış](m365-lighthouse-overview-of-permissions.md) (makale)\
[Portal güvenliğini yapılandırma](m365-lighthouse-configure-portal-security.md) (makale)\
[Ayrıntılı yönetici ayrıcalıklarına (GDAP) giriş (](/partner-center/gdap-introduction) makale)\
[yerleşik rolleri Azure AD](/azure/active-directory/roles/permissions-reference) (makale)\
[Azure Active Directory'de gruplar ve erişim hakları hakkında bilgi edinin](/azure/active-directory/fundamentals/concept-learn-about-groups) (makale)\
[Azure AD yetkilendirme yönetimi nedir?](/azure/active-directory/governance/entitlement-management-overview) (makale)