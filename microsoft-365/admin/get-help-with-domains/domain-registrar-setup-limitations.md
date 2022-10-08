---
title: Kurulum sınırlamaları olan etki alanı kayıt şirketleri
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: Bazı etki alanı kayıt şirketleri sınırlı hizmetler sunar, bu da tüm Microsoft özelliklerinin her etki alanıyla çalışmayacağı anlamına gelir.
ms.openlocfilehash: 361faf93e2b923b0c16ce7051f43663998be4dc7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191199"
---
# <a name="domain-registrars-with-setup-limitations"></a>Kurulum sınırlamaları olan etki alanı kayıt şirketleri

[Microsoft için DNSMadeEasy'de DNS kayıtları oluşturma](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[Microsoft için easyDNS'de DNS kayıtları oluşturma](#create-dns-records-at-easydns-for-microsoft)\
[Microsoft için Freenom'da DNS kayıtları oluşturma](#create-dns-records-at-freenom-for-microsoft)\
[Microsoft için MyDomain'de DNS kayıtları oluşturma](#create-dns-records-at-mydomain-for-microsoft)\
[Windows tabanlı DNS kullanarak Microsoft için DNS kayıtları oluşturma](#create-dns-records-for-microsoft-using-windows-based-dns)\
[Etki alanınız Google tarafından yönetildiğinde DNS kayıtları oluşturma (eNom)](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[Microsoft için 1&1 IONOS'ta DNS kayıtları oluşturma](#create-dns-records-at-11-ionos-for-microsoft)

Bazı etki alanı kayıt şirketleri önemli hizmet sınırlamalarına sahiptir ve bu da tüm Microsoft özelliklerinin her etki alanıyla çalışmayacağı anlamına gelir. Bu makalede bazı kayıt şirketleri için belirli sınırlamalar belirlenmiştir. 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>Microsoft için DNSMadeEasy'de DNS kayıtları oluşturma

DNSMadeEasy hesapları için, eklediğiniz etki alanı ayrı bir etki alanı kayıt şirketinden satın alınmıştır. DNSMadeEasy etki alanı kayıt hizmetleri sağlamaz. DNSMadeEasy'de oturum açabilmeniz ve DNS kaydı oluşturabilmeniz, sahipliği kanıtlamak için yeterli olur.

## <a name="create-dns-records-at-easydns-for-microsoft"></a>Microsoft için easyDNS'de DNS kayıtları oluşturma

SRV Kayıtları şu anda hiçbir easyDNS hizmet paketi altında kullanılamaz. Teams için gereken SRV kayıtlarını eklemek için easyDNS ile daha yüksek bir hizmet düzeyine yükseltmeniz gerekebilir.

## <a name="create-dns-records-at-freenom-for-microsoft"></a>Microsoft için Freenom'da DNS kayıtları oluşturma

Freenom web sitesi SRV kayıtlarını eklemeyi desteklemez, bu da birkaç Teams ve Email özelliğinin çalışmaymayacağı anlamına gelir. Hangi Microsoft planını kullanırsanız kullanın önemli hizmet sınırlamaları vardır ve farklı bir DNS barındırma sağlayıcısına geçmek isteyebilirsiniz.

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>Microsoft için MyDomain'de DNS kayıtları oluşturma

MyDomain web sitesi SRV kayıtlarını desteklemez; başka bir deyişle çeşitli Teams ve Email özellikleri çalışmaz. Hangi Microsoft planını kullanırsanız kullanın, DNS kayıtlarınızı MyDomain'de yönetiyorsanız önemli hizmet sınırlamaları vardır ve farklı bir DNS barındırma sağlayıcısına geçmek isteyebilirsiniz.

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows tabanlı DNS kullanarak Microsoft için DNS kayıtları oluşturma

Etki alanınızın DNS kayıtlarını içeren sayfaya gidin. Windows Server 2008'de çalışıyorsanız **Başlat**, **Çalıştır'a** gidin. Windows Server 2012'de çalışıyorsanız **Windows tuşuna** ve **r** tuşuna basın. **dnsmgmnt.msc** yazın ve **Tamam'ı** seçin. DNS Yöneticisi'nde **DNS sunucusu adı** olan  **arama bölgelerini ileriye doğru** genişletin. Etki alanınızı seçin. Artık DNS kayıtlarını oluşturmaya hazırsınız.

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Etki alanınız Google tarafından yönetildiğinde DNS kayıtları oluşturma (eNom)

Google Apps for Work hesabınıza kaydolarak etki alanınızı Google aracılığıyla satın aldıysanız, DNS kayıtlarınız Google tarafından yönetilir ancak eNom'a kaydedilir. Google Domains sayfasından eNom'a erişebilir ve DNS oluşturabilirsiniz.

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Microsoft için 1&1 IONOS'ta DNS kayıtları oluşturma

1&1 IONOS, etki alanının hem MX kaydına hem de en üst düzey Autodiscover CNAME kaydına sahip olmasına izin vermez. Bu, Microsoft için Exchange Online yapılandırma yöntemlerinizi sınırlar. Geçici bir çözüm vardır, ancak yalnızca 1&1 IONOS'ta alt etki alanları oluşturma deneyimine sahipseniz kullanmanızı öneririz.

Bu hizmet sınırlamasına rağmen 1&IONOS'ta kendi Microsoft DNS kayıtlarınızı yönetmeyi seçerseniz, bu makaledeki adımları izleyerek etki alanınızı doğrulayın ve e-posta, Skype Kurumsal Online vb. için DNS kayıtlarını ayarlayın.

1&1 IONOS, Microsoft e-posta hizmetleri için gereken CNAME kayıtlarıyla birlikte bir MX kaydı kullanabilmeniz için geçici bir çözüm gerektirir. Bu geçici çözüm, 1&1 IONOS'ta bir alt etki alanı kümesi oluşturmanızı ve bunları CNAME kayıtlarına atamanızı gerektirir.

> [!NOTE]
> Bu yordama başlamadan önce kullanılabilir en az iki alt etki alanınızın olduğundan emin olun. Bu çözümü yalnızca 1&1 IONOS'ta alt etki alanları oluşturma konusunda zaten deneyiminiz varsa öneririz.

### <a name="basic-cname-records"></a>Temel CNAME kayıtları

1.  Başlamak için 1&1 IONOS konumundaki etki alanları sayfanıza gidin. Oturum açmanız istenir.

1.  **Etki alanlarını yönet'i** seçin.

1.  Etki Alanı Merkezi sayfasında, güncelleştirmek istediğiniz etki alanını bulun ve ardından **Alt Etki Alanlarını Yönet'i** seçin. Şimdi iki alt etki alanı oluşturacak ve her biri için bir **Diğer Ad** değeri ayarlayacaksınız (Bu gereklidir çünkü 1&1 IONOS yalnızca bir üst düzey CNAME kaydını destekler, ancak Microsoft birkaç CNAME kaydı gerektirir.)

1.  İlk olarak, Otomatik Bulma alt etki alanını oluşturacaksınız. Alt Etki Alanına **Genel Bakış** bölümünde **Alt Etki Alanı Oluştur'u** seçin.

1.  Yeni alt etki alanının **Alt Etki Alanı Oluştur** kutusunda, yalnızca aşağıdaki tablodan **Alt Etki Alanı Oluştur** değerini yazın veya kopyalayıp yapıştırın. ( **Diğer ad** değerini sonraki bir adımda ekleyeceksiniz.)

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1.  **Alt Etki Alanı Oluştur'u** seçin.

1.  Alt Etki **Alanına Genel Bakış** bölümünde, yeni oluşturduğunuz otomatik bulma alt etki alanını bulun ve ardından bu alt etki alanı için Panel (v) denetimini seçin.

1.  Alt Etki Alanı **Ayarları** alanında **DNS Ayarlarını Düzenle'yi** seçin.

1.  **A/AAAA Kayıtları (IP Adresleri)** bölümünde, **IP adresi (A Kaydı)** alanında **CNAME'yi** seçin.

1. **Diğer Ad:** kutusunda, yalnızca aşağıdaki tabloda verilen **Diğer Ad** değerini yazın veya kopyalayıp yapıştırın.

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |autodiscover|autodiscover.outlook.com|

1. **Farkındayım** bildiriminin onay kutusunu seçin.

1. **Kaydet**'i seçin.

### <a name="additional-cname-records"></a>Ek CNAME kayıtları

Aşağıdaki yordamdaki ek CNAME kayıtları Skype Kurumsal Çevrimiçi hizmetleri etkinleştirir. Önceden oluşturduğunuz iki CNAME kaydı için kullandığınız adımların aynısını kullanın.

**Üçüncü alt etki alanını oluşturma (Lyncdiscover)**

1.  Alt Etki Alanına **Genel Bakış** bölümünde **Alt Etki Alanı Oluştur'u** seçin.

1.  Yeni alt etki alanının **Alt Etki Alanı Oluştur** kutusunda, yalnızca aşağıdaki tablodan **Alt Etki Alanı Oluştur** değerini yazın veya kopyalayıp yapıştırın. ( **Diğer ad** değerini sonraki bir adımda ekleyeceksiniz.)

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  **Alt Etki Alanı Oluştur'u** seçin.

1.  Etki Alanı Merkezi sayfasında **Alt Etki Alanlarını Yönet'i** seçin.

1.  **Alt Etki Alanına Genel Bakış** bölümünde, yeni oluşturduğunuz lyncdiscover alt etki alanını bulun ve ardından bu alt etki alanı için Panel (v) denetimini seçin. Alt Etki Alanı **Ayarları** alanında **DNS Ayarlarını Düzenle'yi** seçin.

1.  **A/AAAA Kayıtları (IP Adresleri)** bölümünde, **IP adresi (A Kaydı)** alanında **CNAME'yi** seçin.

1.  **Diğer Ad:** kutusunda, yalnızca aşağıdaki tabloda verilen **Diğer Ad** değerini yazın veya kopyalayıp yapıştırın.

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  **Farkındayım** bildiriminin onay kutusunu seçin ve ardından **Kaydet'i** seçin.

1.  **DNS Ayarlarını Düzenle** iletişim kutusunda **Evet'i** seçin.

**Dördüncü alt etki alanını (SIP) oluşturma**

1.  Alt Etki Alanına **Genel Bakış** bölümünde **Alt Etki Alanı Oluştur'u** seçin.

1.  Yeni alt etki alanının **Alt Etki Alanı Oluştur** kutusunda, yalnızca aşağıdaki tablodan **Alt Etki Alanı Oluştur** değerini yazın veya kopyalayıp yapıştırın. ( **Diğer ad** değerini daha sonra ekleyeceksiniz.)

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  **Alt Etki Alanı Oluştur'u** seçin.

1.  Etki Alanı Merkezi sayfasında **Alt Etki Alanlarını Yönet'i** seçin.

1.  **Alt Etki Alanına Genel Bakış** bölümünde, yeni oluşturduğunuz sip alt etki alanını bulun ve ardından bu alt etki alanı için Panel (v) denetimini seçin. <br/> Alt Etki Alanı **Ayarları** alanında **DNS Ayarlarını Düzenle'yi** seçin.

1.  **A/AAAA Kayıtları (IP Adresleri)** bölümünde, **IP adresi (A Kaydı)** alanında **CNAME'yi** seçin.

1.  **Diğer Ad:** kutusunda, yalnızca aşağıdaki tabloda verilen **Diğer Ad** değerini yazın veya kopyalayıp yapıştırın.

    |Alt Etki Alanı Oluştur|Diğer ad|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  **Farkındayım** bildiriminin onay kutusunu seçin ve ardından **Kaydet'i** seçin.

1.  **DNS Ayarlarını Düzenle** iletişim kutusunda **Evet'i** seçin.

### <a name="cname-records-needed-for-mdm"></a>MDM için gereken CNAME kayıtları

Diğer dört CNAME kaydı için kullandığınız ancak şu değerleri sağladığınız yordamı izleyin:

|Alt Etki Alanı Oluştur|Diğer ad|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|
