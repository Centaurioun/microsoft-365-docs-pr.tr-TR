---
title: Microsoft 365'i herhangi bir etki alanı kayıt şirketiyle ayarlamak için ad sunucularını değiştirme
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: E-posta ve Skype Kurumsal Online gibi hizmetlerinizin kendi etki alanı adınızı kullanması için Microsoft 365'te etki alanınızı eklemeyi ve ayarlamayı öğrenin.
ms.openlocfilehash: f66099b7496bc60a7b12618785d1596eab70b174
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728697"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Microsoft 365'i herhangi bir etki alanı kayıt şirketiyle ayarlamak için ad sunucularını değiştirme

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

E-posta ve Teams gibi hizmetlerinizin kendi etki alanı adınızı kullanması için Microsoft 365'te etki alanınızı eklemek ve ayarlamak için bu yönergeleri izleyin. Bunu yapmak için etki alanınızı doğrulayacak ve ardından doğru DNS kayıtlarının sizin için ayarlanabilmesi için etki alanınızın ad sunucularını Microsoft 365 olarak değiştireceksiniz. Aşağıdaki deyimler durumunuzu açıklıyorsa şu adımları izleyin:

- Kendi etki alanınız var ve Bunu Microsoft 365 ile çalışacak şekilde ayarlamak istiyorsunuz.

- DNS kayıtlarınızı Microsoft 365'in yönetmesini istiyorsunuz. (İsterseniz [DNS kayıtlarınızı kendiniz yönetebilirsiniz](../setup/add-domain.md).)

## <a name="add-a-txt-or-mx-record-for-verification"></a>Doğrulama için bir TXT veya MX kaydı ekleyin

> [!NOTE]
> You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.

Etki alanınızı Microsoft 365 ile kullanmadan önce, etki alanına sahip olduğunuzdan emin olmamız gerekir. Etki alanı kayıt şirketinizde hesabınızda oturum açıp DNS kaydını oluşturabilmek, Microsoft 365'e etki alanının sahibi olduğunuzu kanıtlar.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>DNS barındırma sağlayıcınızın web sitesinde yeni kayıt oluşturabileceğiniz alanı bulun

1. DNS barındırma hizmet sağlayıcınızın web sitesinde oturum açın.

2. Etki alanınızı seçin.

3. Etki alanınızla ilgili DNS kayıtlarını düzenleyebileceğiniz sayfayı bulun.

### <a name="create-the-record"></a>Kaydı oluşturma

Oluşturduğunuz kaydın TXT veya MX olmasına bağlı olarak, aşağıdakilerden birini yapın:

**TXT kaydı oluşturuyorsanız, şu değerleri kullanın:**

<br>

****

|Kayıt türü|Diğer ad veya ana bilgisayar adı|Değer|TTL|
|---|---|---|---|
|TXT|Aşağıdakilerden birini yapın: **@** yazın, alanı boş bırakın veya etki alanı adınızı yazın.  <p> **Not**: Farklı DNS konaklarının bu alan için farklı gereksinimleri vardır.|MS=ms *XXXXXXXX* <p> **Not:** Bu bir örnektir. Burada, Microsoft 365'teki tablodan belirli **Hedef veya İşaret Edilen Adres** değerinizi kullanın. [Bunu nasıl bulabilirim?](../get-help-with-domains/information-for-dns-records.md)|Bu değeri **1 saat** veya buna eşdeğer dakika sayısına ( **60** ), saniye sayısına ( **3600** ), vb. ayarlayın.    |
|||||

**MX kaydı oluşturuyorsanız, şu değerleri kullanın:**

<br>

****

|Kayıt türü|Diğer ad veya ana bilgisayar adı|Değer|Öncelik|TTL|
|---|---|---|---|---|
|MX|**@** veya etki alanı adınızı yazın. |MS=ms *XXXXXXXX* **Not:** Bu bir örnektir. Burada, Microsoft 365'teki tablodan belirli **Hedef veya İşaret Edilen Adres** değerinizi kullanın. [Bunu nasıl bulabilirim?](../get-help-with-domains/information-for-dns-records.md)|**Öncelik** için, posta akışı için kullanılan MX kaydıyla çakışmaları önlemek için, mevcut MX kayıtlarının önceliğine göre daha düşük bir öncelik kullanın. Öncelik hakkında daha fazla bilgi için bkz. [MX önceliği nedir?](../setup/domains-faq.yml)|Bu değeri **1 saat** veya buna eşdeğer dakika sayısına ( **60** ), saniye sayısına ( **3600** ), vb. ayarlayın.|
||||||

### <a name="save-the-record"></a>Kaydı kaydetme

Artık kaydı etki alanı kayıt şirketinizin sitesine eklediğinize göre, Microsoft 365'e geri dönüp Microsoft 365'in kaydı aramasını isteyebilirsiniz.

Microsoft 365 doğru TXT kaydını bulduğunda etki alanınız doğrulanır.

1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

2. **Etki Alanları** sayfasında, doğruladığınız etki alanını seçin.

3. **Kurulum** sayfasında **Kurulumu başlat'ı** seçin.

4. **Etki alanını doğrula** sayfasında **Doğrula'yı** seçin.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>Etki alanınızın ad sunucusu (NS) kayıtlarını değiştirin

Microsoft 365'te etki alanları kurulum sihirbazının son adımına gittiğinizde, bir göreviniz kalır. Etki alanınızı e-posta gibi Microsoft 365 hizmetleriyle ayarlamak için, etki alanı kayıt şirketinizde etki alanınızın ad sunucusu (veya NS) kayıtlarını Microsoft 365 birincil ve ikincil ad sunucularına işaret eden şekilde değiştirirsiniz. Ardından, DNS'nizi Microsoft 365 barındırdığından, hizmetleriniz için gerekli DNS kayıtları sizin için otomatik olarak ayarlanır. Etki alanı kayıt şirketinizin web sitesinde sağlanıyor olabilecek adımları izleyerek ad sunucusu kayıtlarını kendiniz güncelleştirebilirsiniz. DNS hakkında bilginiz yoksa, etki alanı kayıt şirketi desteğine başvurun.

::: moniker range="o365-worldwide"

Etki alanı kayıt şirketinizin web sitesinde etki alanınızın ad sunucularını kendiniz değiştirmek için şu adımları izleyin:

1. Etki alanı kayıt şirketinin web sitesinde etki alanınızın ad sunucularını değiştirebileceğiniz alanı veya özel ad sunucularını kullanabileceğiniz bir alanı bulun.

2. Ad sunucusu kayıtları oluşturun veya mevcut ad sunucusu kayıtlarını aşağıdaki değerlerle eşleşecek şekilde düzenleyin:

    - Ad sunucusu: ns1.bdm.microsoftonline.com
    - İkinci ad sunucusu: ns2.bdm.microsoftonline.com
    - Üçüncü ad sunucusu: ns3.bdm.microsoftonline.com
    - Dördüncü ad sunucusu: ns4.bdm.microsoftonline.com

   > [!TIP]
   > Dört kaydı da eklemek en iyisidir, ancak kayıt şirketiniz yalnızca iki kaydı destekliyorsa **ns1.bdm.microsoftonline.com** ve **ns2.bdm.microsoftonline.com** ekleyin.

3. Değişikliklerinizi kaydedin.

> [!CAUTION]
> Etki alanınızın NS kayıtlarını Microsoft 365 ad sunucularına işaret etmek üzere değiştirdiğinizde, etki alanınızla ilişkili olan tüm hizmetler etkilenir. Sihirbazın herhangi bir adımını, örneğin e-posta adreslerini ekleme adımını atladıysanız veya etki alanınızı bloglar, alış veriş sepetleri veya başka hizmetler için kullanıyorsanız, gereken bazı ek adımlar vardır. Bunları uygulamazsanız, bu değişiklik hizmet e-posta erişiminin kaybolması veya mevcut web sitenize erişilememesi gibi, hizmetlerde kesintilere yol açabilir.

::: moniker-end

::: moniker range="o365-21vianet"

1. Etki alanı kayıt şirketinizin web sitesinde etki alanınızın ad sunucularını düzenleyebileceğiniz yeri bulun.

2. İki ad sunucusu kaydı oluşturun veya varolan ad sunucusu kayıtlarını aşağıdaki değerlerle eşleşecek şekilde düzenleyin:

   - Ad sunucusu: ns1.dns.partner.microsoftonline.cn
   - İkinci ad sunucusu: ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > En az iki ad sunucusu kaydı kullanmanız gerekir. Listelenen başka ad sunucuları varsa, bunları silebilir veya **ns3.dns.partner.microsoftonline.cn** ve **ns4.dns.partner.microsoftonline.cn** olarak değiştirebilirsiniz.

3. Değişikliklerinizi kaydedin.

> [!CAUTION]
> Etki alanınızın NS kayıtlarını 21Vianet ad sunucuları tarafından sağlanan Office 365 işaret etmek üzere değiştirdiğinizde, etki alanınızla ilişkili olan tüm hizmetler etkilenir. Sihirbazın herhangi bir adımını, örneğin e-posta adreslerini ekleme adımını atladıysanız veya etki alanınızı bloglar, alış veriş sepetleri veya başka hizmetler için kullanıyorsanız, gereken bazı ek adımlar vardır. Bunları uygulamazsanız, bu değişiklik hizmet e-posta erişiminin kaybolması veya mevcut web sitenize erişilememesi gibi, hizmetlerde kesintilere yol açabilir.

::: moniker-end

Örneğin, e-posta ve web sitesi barındırma için gerekli olabilecek bazı ek adımlar şunlardır:

- NS kayıtlarınızı değiştirmeden önce etki alanınızı kullanan tüm e-posta adreslerini Microsoft 365'e taşıyın.

- Şu anda bir web sitesi adresiyle kullanılan bir etki alanı eklemek ister misiniz, örneğin `https://www.fourthcoffee.com`? Etki alanının NS kayıtlarını Microsoft 365'e işaret eden bir şekilde değiştirdikten sonra da kullanıcıların web sitesine ulaşabilmesi için, etki alanını eklerken aşağıdaki adımları uygulayabilirsiniz.

1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Etki Alanları</a> sayfasına gidin.

2. **Etki Alanları** sayfasında bir etki alanı seçin.

3. Etki alanı ayrıntıları sayfasında **DNS kayıtları** sekmesini seçin.

4. **Kayıt ekle'yi** seçin.

5. **Özel DNS kaydı ekle** bölmesindeki **Tür** açılan **listesindeN A (Adres)'** i seçin.

6. **Ana bilgisayar adı veya Diğer Ad** kutusuna yazın **@**.

7. **IP Adresi** kutusuna, şu anda barındırıldığı web sitesinin statik IP adresini yazın. Örneğin, 172.16.140.1.

   > [!IMPORTANT]
   > Bu, _dinamik_ IP adresi değil, web sitesi için _statik_ bir IP adresi olmalıdır. Genel web siteniz için statik bir IP adresi alabildiğinizden emin olmak için web sitenizi barındıran siteye bakın.

8. Kaydın TTL ayarını değiştirmek istiyorsanız, **TTL** açılan listesinden yeni bir süre seçin. Aksi takdirde 9. adıma geçin.

9. **Kaydet**'i seçin.

Buna ek olarak, müşterilerin web sitenizi bulmalarına yardım etmek için bir CNAME kaydı da oluşturabilirsiniz.

1. **Kayıt ekle'yi** seçin.
2. **Özel DNS kaydı ekle** bölmesindeki **Tür** açılan **listesindeN CNAME (Diğer Ad)** öğesini seçin.
3. **Ana bilgisayar adı veya Diğer Ad** kutusuna **www** yazın.
4. **İşaret edilen adres** kutusuna web siteniz için tam etki alanı adını (FQDN) yazın. Örneğin **, contoso.com**.
5. Kaydın TTL ayarını değiştirmek istiyorsanız, **TTL** açılan listesinden yeni bir süre seçin. Aksi takdirde 6. adıma geçin.
6. **Kaydet**'i seçin.

Ad sunucusu kayıtları Microsoft'a işaret etmek üzere güncelleştirildikten sonra etki alanı kurulumunuz tamamlanır. Email Microsoft'a yönlendirilir ve web sitesi adresinize giden trafik geçerli web sitesi barındırma sağlayıcınıza gitmeye devam eder.'

> [!NOTE]
> Ad sunucusu kaydı güncelleştirmelerinizin İnternet DNS sistemi genelinde güncelleştirilmesi birkaç saat sürebilir. Ardından Microsoft e-postanız ve diğer hizmetlerin tümü etki alanınızla çalışacak şekilde ayarlanır.

## <a name="related-content"></a>İlgili içerik

[Etki alanınızı bağlamak için DNS kayıtları ekleme](create-dns-records-at-any-dns-hosting-provider.md) (makale)\
[Kendi etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](find-and-fix-issues.md) (makale)\
[Etki alanlarını yönetme](/admin) (sayfa bağlantısı)
