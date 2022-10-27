---
title: Amazon Web Services'teki (AWS) DNS kayıtlarınızı Microsoft 365'e bağlama
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
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Etki alanınızı doğrulamayı ve Microsoft için Amazon Web Services'te (AWS) e-posta, Skype Kurumsal Online ve diğer hizmetler için DNS kayıtlarını ayarlamayı öğrenin.
ms.openlocfilehash: 9938168c3fb29e4d6bd862414f309c8b58db1223
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719172"
---
# <a name="connect-your-dns-records-at-amazon-web-services-aws-to-microsoft-365"></a>Amazon Web Services'teki (AWS) DNS kayıtlarınızı Microsoft 365'e bağlama

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

DNS barındırma sağlayıcınız AWS ise, etki alanınızı doğrulamak ve e-posta, Skype Kurumsal için DNS kayıtlarını ayarlamak vb. için bu makaledeki adımları izleyin.

AWS'de bu kayıtları ekledikten sonra etki alanınız Microsoft hizmetleriyle çalışacak şekilde ayarlanır.

> [!NOTE]
> Genellikle, DNS değişikliklerinin etkili olması yaklaşık 15 dakika sürer. Bununla birlikte, yaptığınız değişikliğin İnternet'in DNS sistemi genelinde güncelleştirilmesi bazen daha uzun sürebilir. DNS kayıtlarını ekledikten sonra posta akışıyla veya diğer sorunlarla karşılaşıyorsanız, bkz. [Etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Doğrulama için bir TXT kaydı ekleme

Etki alanınızı Microsoft ile kullanmadan önce, etki alanına sahip olduğunuzdan emin olmamız gerekir. Etki alanı kayıt şirketinizde hesabınızda oturum açıp DNS kaydını oluşturabilmek, Microsoft'a etki alanının sahibi olduğunuzu kanıtlar.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Doğrulamak istediğiniz etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Doğrulamak istediğiniz etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** ve **Yönlendirme ilkesi** değerlerini seçin.)

    > [!TIP]
    > Ekrandaki yönergeler tarafından gereken tırnak işaretleri otomatik olarak gelir. Bunları el ile yazmanız gerekmez.

    |Kayıt adı|Kayıt türü|Değer|TTL (Saniye)|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |(Bu alanı boş bırakın.)|TXT - E-posta gönderenleri doğrulamak için kullanılır|MS=ms *XXXXXXXX* <br/> **Not:** Bu bir örnektir. Burada, Microsoft 365'teki tablodan belirli **Hedef veya İşaret Edilen Adres** değerinizi kullanın. [Bunu nasıl bulabilirim?](../get-help-with-domains/information-for-dns-records.md)|300|Basit|

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

   Yeni oluşturduğunuz kaydın İnternet genelinde güncelleştirilebilmesi için devam etmeden önce birkaç dakika bekleyin.

Artık kaydı etki alanı kayıt şirketinizin sitesine eklediğinize göre, Microsoft'a geri dönüp kayıt için arama isteğinde bulunacaksınız. Microsoft doğru TXT kaydını bulduğunda etki alanınız doğrulanır.

Microsoft 365'te kaydı doğrulamak için:

1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Etki Alanları'na**</a> gidin.

1. Etki Alanları sayfasında, doğrulamakta olduğunuz etki alanını seçin ve **kurulumu başlat'ı** seçin.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Kurulumu başlat'ı seçin.":::

1. **Devam**'ı seçin.

1. **Etki alanını doğrula** sayfasında **Doğrula'yı** seçin.

> [!NOTE]
> Genellikle, DNS değişikliklerinin etkili olması yaklaşık 15 dakika sürer. Bununla birlikte, yaptığınız değişikliğin İnternet'in DNS sistemi genelinde güncelleştirilmesi bazen daha uzun sürebilir. DNS kayıtlarını ekledikten sonra posta akışıyla veya diğer sorunlarla karşılaşıyorsanız, bkz. [Etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Etki alanınız için e-postanın Microsoft 365'e gelmesi için bir MX kaydı ekleyin

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** ve **Yönlendirme ilkesi** değerlerini seçin.)

    > [!TIP]
    > Ekrandaki yönergeler tarafından gereken tırnak işaretleri otomatik olarak gelir. Bunları el ile yazmanız gerekmez.

    |Kayıt adı|Kayıt türü|Değer|TTL (Saniye)|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |(Bu alanı boş bırakın.)|MX - Posta sunucularını belirtir|0.mail.protection.outlook.com *\<domain-key\>*. <br/> The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space. <br/> **Bu değer nokta (.) ile bitmelidir.** <br/> **Not:** Microsoft 365 hesabınızdan alın \<*domain-key*\> . [Bunu nasıl bulabilirim?](../get-help-with-domains/information-for-dns-records.md)|300|Basit yönlendirme|

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-mx-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

1. Başka MX kayıtları varsa, kaydı seçip **Sil'i** seçerek bunları kaldırın.

## <a name="add-the-cname-record-required-for-microsoft-365"></a>Microsoft 365 için gereken CNAME kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** ve **Yönlendirme ilkesi** değerlerini seçin.)

    |Kayıt adı|Kayıt türü|Değer|TTL|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover|CNAME - Trafiği başka bir etki alanı adına yönlendirir|autodiscover.outlook.com. <br/> **Bu değer nokta (.) ile bitmelidir.**|300|Basit|

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>SPF'nin gereksiz e-postaları önlemesine yardımcı olmak için TXT kaydı ekleme

> [!IMPORTANT]
> Bir etki alanına yönelik SPF için birden fazla TXT kaydına sahip olamazsınız. Etki alanınızda birden fazla SPF kaydı varsa bu durum, e-posta hatalarının yanı sıra teslimat ve istenmeyen posta sınıflandırma sorunlarına neden olabilir. Etki alanınız için zaten bir SPF kaydınız varsa, Microsoft için yeni bir tane oluşturmayın. Bunun yerine, her iki değer kümesini içeren *tek* bir SPF kaydına sahip olmak için gerekli Microsoft değerlerini geçerli kayda ekleyin. Örneklere mi ihtiyacınız var? [Microsoft için bu Dış Etki Alanı Adı Sistemi kayıtlarına](../../enterprise/external-domain-name-system-records.md) göz atın. SPF kaydınızı doğrulamak için bu[SPF doğrulama araçlarından](../setup/domains-faq.yml) birini kullanabilirsiniz.

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** değerini seçin.)

    |Kayıt türü|Değer|
    |:-----|:-----|
    |TXT- E-posta gönderenleri doğrulamak ve uygulamaya özgü değerler için kullanılır|v=spf1 include:spf.protection.outlook.com -all <br/> (Ekrandaki yönergeler için gereken tırnak işaretleri otomatik olarak gelir. Bunları el ile yazmanız gerekmez.) <br/> **Not:** Tüm aralıkların doğru kalması için bu girdiyi kopyalayıp yapıştırmanızı öneririz.|

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

## <a name="advanced-option-skype-for-business"></a>Gelişmiş seçenek: Skype Kurumsal

Bu seçeneği yalnızca kuruluşunuz Microsoft Teams'in yanı sıra sohbet, konferans aramaları ve görüntülü aramalar gibi çevrimiçi iletişim hizmetleri için Skype Kurumsal kullanıyorsa belirtin. Skype için 4 kayıt gerekir: Kullanıcıdan kullanıcıya iletişim için 2 SRV kaydı ve oturum açmak ve kullanıcıları hizmete bağlamak için 2 CNAME kaydı.

### <a name="add-the-two-required-srv-records"></a>Gerekli iki SRV kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılır listelerden **Tür** ve **Yönlendirme İlkesi** değerlerini seçin.)

    |Kayıt adı|Kayıt türü|Değer|TTL (Saniye)|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - Sunucuları tanımlayan uygulamaya özgü değerler|100 1 443 sipdir.online.lync.com. **Bu değer nokta (.) ile bitmelidir.**> <br/> **Not:** Tüm aralıkların doğru kalması için bu girdiyi kopyalayıp yapıştırmanızı öneririz.|300|Basit|
    |_sipfederationtls._tcp|SRV - Sunucuları tanımlayan uygulamaya özgü değerler|100 1 5061 sipfed.online.lync.com. **Bu değer nokta (.) ile bitmelidir.** <br/> **Not:** Tüm aralıkların doğru kalması için bu girdiyi kopyalayıp yapıştırmanızı öneririz.|300|Basit|

1. Diğer SRV kaydını eklemek için **Başka bir kayıt ekle'yi** seçin, tablonun bir sonraki satırında yer alan değerleri kullanarak bir kayıt oluşturun ve sonra kayıt **oluştur'u** yeniden seçin.

   :::image type="content" source="../../media/dns-aws/aws-domians-srv-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

> [!NOTE]
> Genellikle, DNS değişikliklerinin etkili olması yaklaşık 15 dakika sürer. Bununla birlikte, yaptığınız değişikliğin İnternet'in DNS sistemi genelinde güncelleştirilmesi bazen daha uzun sürebilir. DNS kayıtlarını ekledikten sonra posta akışıyla veya diğer sorunlarla karşılaşıyorsanız, bkz. [Etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype Kurumsal için gereken iki CNAME kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** ve **Yönlendirme ilkesi** değerlerini seçin.)

    |Kayıt adı|Kayıt türü|Değer|TTL|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |sip|CNAME - Kurallı ad|sipdir.online.lync.com. <br/> **Bu değer nokta (.) ile bitmelidir.**|300|Basit|
    |lyncdiscover|CNAME - Kurallı ad|webdir.online.lync.com. <br/> **Bu değer nokta (.) ile bitmelidir.**|300|Basit|

1. Diğer CNAME kaydını eklemek için **Başka bir kayıt ekle'yi** seçin, tablonun bir sonraki satırında yer alan değerleri kullanarak bir kayıt oluşturun.

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Gelişmiş seçenek: Microsoft 365 için Intune ve Mobil Cihaz Yönetimi

Bu hizmet, etki alanınıza bağlanan mobil cihazları güvenli ve uzaktan yönetmenize yardımcı olur. Mobil Cihaz Yönetimi, kullanıcıların cihazları hizmete kaydedebilmesi için iki CNAME kaydına ihtiyaç duyar.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile Cihaz Yönetimi için gereken iki CNAME kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://console.aws.amazon.com/route53/home) kullanarak AWS'deki etki alanları sayfanıza gidin. İlk önce oturum açmanız istenir.

1. Giriş sayfasındaki **Etki Alanları'nın** altında **Kayıtlı etki alanları'nı** seçin.

1. **Etki Alanı Adı'nın** altında, Microsoft 365'te ayarlamak istediğiniz etki alanını seçin.

    **Not**: Etki alanınız için barındırılan bölge oluşturmadıysanız Barındırılan **bölge oluştur'u** seçin ve sonraki adıma geçmeden önce adımları tamamlayın.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Etki alanının adını seçin.":::

1. **DNS'yi Yönet'i** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Açılan listeden DNS'yi yönet'i seçin.":::

1. **Etki alanı adı'nın** altında, doğrulamak istediğiniz etki alanının barındırılan bölge sürümü için etki alanı adını seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Etki alanının adını seçin.":::

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Kayıt oluştur'u seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listelerden **Tür** ve **Yönlendirme ilkesi** değerlerini seçin.)

    |Kayıt adı|Kayıt türü|Değer|TTL|Yönlendirme ilkesi|
    |:-----|:-----|:-----|:-----|:-----|
    |enterpriseregistration|CNAME - Kurallı ad|enterpriseregistration.windows.net. <br/> **Bu değer nokta (.) ile bitmelidir.**|300|Basit|
    |enterpriseenrollment|CNAME - Kurallı ad|enterpriseenrollment-s.manage.microsoft.com. <br/> **Bu değer nokta (.) ile bitmelidir.**|300|Basit|

1. Diğer CNAME kaydını eklemek için **Başka bir kayıt ekle'yi** seçin, tablonun bir sonraki satırında yer alan değerleri kullanarak bir kayıt oluşturun.

1. **Kayıt oluştur'u** seçin.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Kayıt oluştur'u seçin.":::

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
