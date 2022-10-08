---
title: Windows tabanlı DNS kullanarak Microsoft için DNS kayıtları oluşturma
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Microsoft için Windows tabanlı DNS'de etki alanınızı doğrulamayı ve e-posta, Skype Kurumsal Online ve diğer hizmetler için DNS kayıtlarını ayarlamayı öğrenin.
ms.openlocfilehash: 8a72bb2a6620f5eb52153c8d4c237a2733b21fcd
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68206949"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Windows tabanlı DNS kullanarak Microsoft için DNS kayıtları oluşturma

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
   
Windows tabanlı DNS kullanarak DNS kayıtlarınızı kendiniz barındırıyorsanız, bu makalede verilen adımları izleyerek e-posta, Skype Kurumsal Çevrimiçi, vb. için kayıtlarınızı ayarlayın.
  
Başlamak için [, dns kayıtlarınızı güncelleştirebilmek için Windows tabanlı DNS'de bulmanız](#find-your-dns-records-in-windows-based-dns) gerekir. Ayrıca, şirket içi Active Directory Microsoft ile eşitlemeyi planlıyorsanız bkz. Şirket [içi Active Directory'nizde UPN olarak kullanılan yönlendirilebilir olmayan e-posta adresi](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
DNS kayıtlarını ekledikten sonra posta akışıyla ilgili sorunlar veya diğer sorunlar için bkz. [Etki alanı adınızı veya DNS kayıtlarınızı değiştirdikten sonra sorunları giderme](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows tabanlı DNS'te DNS raporlarınızı bulun
<a name="BKMK_find_your_dns_1"> </a> Etki alanınız için DNS kayıtlarının bulunduğu sayfaya gidin. Windows Server 2008'de çalışıyorsanız **Çalıştırmayı** **Başlat'a** >  gidin. Windows Server 2012'de çalışıyorsanız Windows tuşuna ve **r** tuşuna basın. **dnsmgmnt.msc** yazın ve **Tamam'ı** seçin. DNS Yöneticisi'nde **İleriye Doğru Arama Bölgeleri'ne genişletin\<DNS server name\>\>**. Etki alanınızı seçin. Artık DNS kayıtlarını oluşturmaya hazırsınız.
   
## <a name="add-mx-record"></a>MX kaydını ekleme
<a name="BKMK_add_MX"> </a>

Etki alanınız için e-postanın Microsoft'a gelmesi için bir MX kaydı ekleyin.
- Ekleyeceğiniz MX kaydı şuna benzer bir değer ( **İşaret edilen adres** değeri) içerir: \<MX token\>.mail.protection.outlook.com, burada \<MX token\> MSxxx gibi bir değerdir. 
- Microsoft'ta DNS kayıtları ekle sayfasının Exchange Online bölümündeki MX satırından, İşaret edilen adres altında listelenen değeri kopyalayın. Bu değeri, bu görevde oluşturduğunuz kayıtta kullanacaksınız. 
- Etki alanının DNS Yöneticisi sayfasında **Eylem** > **Posta Exchanger (MX)** bölümüne gidin. Etki alanının bu sayfasını bulmak için bkz. [Windows tabanlı DNS'de DNS kayıtlarınızı bulma](#find-your-dns-records-in-windows-based-dns).  
- **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun: 
    - Ana Bilgisayar Adı:  
    - @Address: Microsoft'tan kopyaladığınız İşaret edilen adres değerini buraya yapıştırın.  
    - Pref: 
- **Değişiklikleri Kaydet**'i seçin.
- Geçersiz MX kayıtlarını kaldırın. Bu etki alanı için e-postayı başka bir yere yönlendiren eski MX kayıtlarınız varsa, her eski kaydın yanındaki onay kutusunu seçin ve ardından **Tamam'ı Sil'i** >  seçin. 
   
## <a name="add-cname-records"></a>CNAME kayıtlarını ekleme
<a name="BKMK_add_CNAME"> </a>

Microsoft için gereken CNAME kayıtlarını ekleyin. Microsoft'ta başka CNAME kayıtları listeleniyorsa, burada gösterilen genel adımların aynısını izleyerek bunları ekleyin.
  
> [!IMPORTANT]
> Microsoft için Mobile Cihaz Yönetimi (MDM) kullanıyorsanız iki ek CNAME kaydı oluşturmanız gerekir. Diğer dört CNAME kaydı için kullandığınız yordamı uygulayın ancak değerleri aşağıdaki tablodan sağlayın. (MDM'niz yoksa bu adımı atlayabilirsiniz.) 

- Etki alanının DNS Yöneticisi sayfasında **Eylem** > **CNAME (CNAME)** bölümüne gidin.
- **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    - Ana Bilgisayar Adı: otomatik bulma
    - Şunu yazın: 
    - CNAMEAddress: autodiscover.outlook.com
- **O K'yi** seçin.

SIP CNAME kaydını ekleyin. 
- Etki alanının DNS Yöneticisi sayfasında **Eylem** \> **CNAME (CNAME)** bölümüne gidin. 
- **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    - Ana Bilgisayar Adı: sip
    - Tür: CNAME
    - Adres: sipdir.online.lync.com
- **Tamam**'ı seçin.

Skype Kurumsal Çevrimiçi Otomatik Bulma CNAME kaydını ekleyin.  
- Etki alanının DNS Yöneticisi sayfasında **Eylem** \> **CNAME (CNAME)** bölümüne gidin. **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    - Ana Bilgisayar Adı: lyncdiscover
    - Tür: CNAME
    - Adres: webdir.online.lync.com
- **Tamam**'ı seçin.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Microsoft için Mobile Cihaz Yönetimi (MDM) için iki CNAME kaydı ekleme

> [!IMPORTANT]
> Microsoft için Mobile Cihaz Yönetimi (MDM) kullanıyorsanız iki ek CNAME kaydı oluşturmanız gerekir. Diğer dört CNAME kaydı için kullandığınız yordamı uygulayın ancak değerleri aşağıdaki tablodan sağlayın. >(MDM'niz yoksa bu adımı atlayabilirsiniz.) 
  

MDM Enterpriseregistration CNAME kaydını ekleyin.  
- Etki alanının DNS Yöneticisi sayfasında **Eylem** \> **CNAME (CNAME)** bölümüne gidin. 
- **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
- Ana Bilgisayar Adı: enterpriseregistration
- Tür: CNAME
- Adres: enterpriseregistration.windows.net
- **Tamam**'ı seçin. 

MDM Enterpriseenrollment CNAME kaydını ekleyin. 
-  Etki alanının DNS Yöneticisi sayfasında **Eylem** \> **CNAME (CNAME)** bölümüne gidin. 
-  **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    - Ana Bilgisayar Adı: enterpriseenrollment
    - Tür: CNAME
    - Adres: enterpriseenrollment-s.manage.microsoft.com
- **Tamam**'ı seçin.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>SPF'nin gereksiz e-postaları önlemesine yardımcı olmak için TXT kaydı ekleme
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Bir etki alanına yönelik SPF için birden fazla TXT kaydına sahip olamazsınız. Etki alanınızda birden fazla SPF kaydı varsa bu durum, e-posta hatalarının yanı sıra teslimat ve istenmeyen posta sınıflandırma sorunlarına neden olabilir. Etki alanınız için zaten bir SPF kaydınız varsa, Microsoft için yeni bir tane oluşturmayın. Bunun yerine, her iki değer kümesini içeren  *tek*  bir SPF kaydına sahip olmak için gerekli Microsoft değerlerini geçerli kayda ekleyin. 
  
Gereksiz e-postayı engellemeye yardımcı olmak üzere etki alanınız için SPF TXT kaydını ekleyin.
  
- You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them. 
- Etki alanınızın DNS Yöneticisi sayfasında **Eylem** \> **Metni (TXT)** bölümüne gidin. 
-  **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun. 
 > [!IMPORTANT]
> Windows DNS Yöneticisi'nin bazı sürümlerinde, bir txt kaydı oluşturduğunuzda ana etki alanının varsayılan olarak üst etki alanı olması için etki alanı ayarlanmış olabilir. Bu durumda, TXT kaydı eklerken, ana bilgisayar adını @ veya etki alanı adı olarak ayarlamak yerine boş (değer yok) olarak ayarlayın. 

-  Konak türü: @
-  Kayıt Türü: TXT
-  Adres: v=spf1 include:spf.protection.outlook.com -all 
         
-  **Tamam**'ı seçin.
   
## <a name="add-srv-records"></a>SRV kayıtlarını ekleme
<a name="BKMK_add_SRV"> </a>

Microsoft için gereken iki SRV kaydını ekleyin.

Skype Kurumsal Çevrimiçi web konferansı için SIP SRV kaydını ekleyin.  <br/> 
-  Etki alanınızın DNS Yöneticisi sayfasında **Eylem** \> **Diğer Yeni Kayıtlar'a** gidin. 
-   **Kaynak Kaydı Türü** penceresinde **Hizmet Konumu (SRV)** öğesini ve ardından **Kayıt Oluştur'u** seçin. 
-   **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    -  Hizmet: _sip
    -  Protokol: _tls
    -  Öncelik: 100
    -  Ağırlık: 1
    -  Bağlantı noktası: 443
    -  Hedef (Konak adı): sipdir.online.lync.com
-  **Tamam**'ı seçin. 


Skype Kurumsal Çevrimiçi federasyonu için SIP SRV kaydını ekleyin.  
-  Etki alanınızın DNS Yöneticisi sayfasında **Eylem** \> **Diğer Yeni Kayıtlar'a** gidin.  
-  **Kaynak Kaydı Türü** penceresinde **Hizmet Konumu (SRV)** öğesini ve ardından **Kayıt Oluştur'u** seçin. 
-   **Yeni Kaynak Kaydı** iletişim kutusunda, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun:  
    -  Hizmet: _sipfederationtls
    -  Protokol: _tcp
    -  Öncelik: 100
    -  Ağırlık: 1
    -  Bağlantı noktası: 5061
    -  Hedef (Konak adı): sipfed.online.lync.com
-  **Tamam**'ı seçin. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Henüz eklemediyseniz, etki alanına sahip olduğunuzu doğrulamak için kayıt ekleme
<a name="BKMK_verify"> </a>

Microsoft hizmetlerinizi ayarlamak için DNS kayıtlarını eklemeden önce, Microsoft'un eklediğiniz etki alanının sahibi olduğunuzu onaylaması gerekir. Bunu yapmak için, aşağıdaki adımları izleyerek bir kayıt eklersiniz.
  
> [!NOTE]
> Bu kayıt yalnızca etki alanının sahibi olduğunuzu doğrulamak için kullanılır; başka hiçbir şeyi etkilemez. 
  

1. Microsoft'tan bilgi toplayın.  <br/> 
2. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin. 
3. **Etki Alanları** sayfasında, doğrulamakta olduğunuz etki alanının **Eylemler** sütununda **Kurulumu başlat'ı** seçin. 
4. **Microsoft'a etki alanı ekle** sayfasında **Başlangıç adımı 1'i** seçin. 
5. **Etki alanınızın sahibi olduğunuzu onaylayın** sayfasında, **Bu adımı gerçekleştirmek için yönergelere bakın** açılan listesinde **Genel yönergeler'i** seçin. 
6. Tablodan Hedef veya İşaret Edilen Adres değerini kopyalayın. Sonraki adım için buna ihtiyacınız olacak. Tüm aralıkların doğru kalması için bu değeri kopyalayıp yapıştırmanızı öneririz.

TXT kaydı ekleyin. 
-  Etki alanınızın DNS Yöneticisi sayfasında **Eylem** \> **Metni (TXT)** bölümüne gidin. 
-   **Yeni Kaynak Kaydı** iletişim kutusunda **Düzenle'yi** seçin.  
-  **Yeni Kaynak Kaydı** iletişim kutusunun **Özel Ana Bilgisayar Adları** alanında, alanların tam olarak aşağıdaki değerlere ayarlandığından emin olun. 

> [!IMPORTANT] 
> Windows DNS Yöneticisi'nin bazı sürümlerinde, bir txt kaydı oluşturduğunuzda ana etki alanının varsayılan olarak üst etki alanı olması için etki alanı ayarlanmış olabilir. Bu durumda, TXT kaydı eklerken, ana bilgisayar adını @ veya etki alanı adı olarak ayarlamak yerine boş (değer yok) olarak ayarlayın. 

- Ana Bilgisayar Adı: @
- Tür: TXT
- Adres: Microsoft'tan kopyaladığınız Hedef veya İşaret Edilen Adres değerini buraya yapıştırın.  
- **Tamam Bitti'yi** >  seçin.

Microsoft'ta etki alanınızı doğrulayın.  
> [!IMPORTANT]
> Bunu yapmadan önce yaklaşık 15 dakika bekleyin, böylece yeni oluşturduğunuz kayıt İnternet üzerinden güncelleştirilebilir.       

- Microsoft'a Geri dön ve doğrulama denetimi istemek için aşağıdaki adımları izleyin. Denetimde, önceki adımda eklediğiniz TXT kaydı aranır. Doğru TXT kaydı bulunduğunda, etki alanı doğrulanır.  
1. Yönetim merkezinde **, Kurulum** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.
2. **Etki Alanları** sayfasında, doğrulamakta olduğunuz etki alanının **Eylem** sütununda **Kurulumu başlat'ı** seçin. 
3. **Etki alanınızın sahibi olduğunuzu onaylayın** sayfasında **bitti, şimdi doğrula'yı** seçin ve onay iletişim kutusunda **Son'u** seçin. 
   
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Şirket içi Active Directory'nizde UPN olarak kullanılan yönlendirilemeyen e-posta adresi
<a name="BKMK_ADNote"> </a>

şirket içi Active Directory Microsoft ile eşitlemeyi planlıyorsanız, Active Directory kullanıcı asıl adı (UPN) son ekinin geçerli bir etki alanı soneki olduğundan ve @contoso.local gibi desteklenmeyen bir etki alanı soneki olmadığından emin olmak istersiniz. UPN son ekinizi değiştirmeniz gerekiyorsa bkz. [Dizin eşitlemesi için yönlendirilebilir olmayan bir etki alanı hazırlama](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>İlgili içerik

[Bir etki alanını Micrsoft 365'ten başka bir ana bilgisayara](../get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host.md) aktarma (makale)\
[Özel etki alanımdan Microsoft 365](../misc/pilot-microsoft-365-from-my-custom-domain.md) pilotu (makale)\
[Etki alanları hakkında SSS](../setup/domains-faq.yml) (makale)