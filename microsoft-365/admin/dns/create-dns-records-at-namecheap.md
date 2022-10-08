---
title: Namecheap'taki DNS kayıtlarınızı Microsoft 365'e bağlama
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Microsoft için Namecheap'ta etki alanınızı doğrulamayı ve e-posta, Skype Kurumsal Online ve diğer hizmetler için DNS kayıtlarını ayarlamayı öğrenin.
ms.openlocfilehash: 51461cd7456de10358c8fb9644c8fe8682e11757
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191485"
---
# <a name="connect-your-dns-records-at-namecheap-to-microsoft-365"></a>Namecheap'taki DNS kayıtlarınızı Microsoft 365'e bağlama

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**.

DNS barındırma sağlayıcınız Namecheap ise, etki alanınızı doğrulamak ve e-posta, Skype Kurumsal Online vb. için DNS kayıtlarını ayarlamak için bu makaledeki adımları izleyin.

Namecheap'ta bu kayıtları ekledikten sonra, etki alanınız Microsoft hizmetleriyle çalışacak şekilde ayarlanır.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Doğrulama için bir TXT kaydı ekleme

Etki alanınızı Microsoft ile kullanmadan önce, etki alanına sahip olduğunuzdan emin olmamız gerekir. Etki alanı kayıt şirketinizde hesabınızda oturum açıp DNS kaydını oluşturabilmek, Microsoft'a etki alanının sahibi olduğunuzu kanıtlar.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız ve Devam Etmeniz istenir.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap'ta oturum açın.":::

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Açılan listeden Etki Alanı Listesi'ni seçin.":::

1. Etki Alanı Listesi sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Gelişmiş DNS'yi seçin.":::

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ KAYIT EKLE'yi seçin.":::

1. **Tür** açılan listesinde **TXT Kaydı'nı** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="TXT Kaydı'nı seçin.":::

1. Yeni kayıt kutularına, aşağıdaki tablodaki değerleri yazın ya da bu tablodan kopyalayıp yapıştırın.

    (Açılan listeden **TTL** değerini seçin.)

    |Tür|Ana Bilgisayar|Değer|TTL|
    |---|---|---|---|
    |TXT|@|MS=ms *XXXXXXXX*  <br/>**Not:** Bu bir örnektir. Burada, tablodan belirli **Hedef veya İşaret Edilen Adres** değerinizi kullanın.  [Bunu nasıl bulabilirim?](../get-help-with-domains/information-for-dns-records.md)|30 dk|

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

1. Yeni oluşturduğunuz kaydın İnternet genelinde güncelleştirilebilmesi için devam etmeden önce birkaç dakika bekleyin.

Artık kaydı etki alanı kayıt şirketinizin sitesine eklediğinize göre, Microsoft'a geri dönüp kaydı istemeniz gerekir. Microsoft doğru TXT kaydını bulduğunda etki alanınız doğrulanır.

Microsoft 365'te kaydı doğrulamak için:

1. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Etki Alanları'na**</a> gidin.

1. Etki Alanları sayfasında, doğrulamakta olduğunuz etki alanını seçin ve **kurulumu başlat'ı** seçin.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Kurulumu başlat'ı seçin.":::

1. **Devam**'ı seçin.

1. **Etki alanını doğrula** sayfasında **Doğrula'yı** seçin.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Etki alanınız için e-postanın Microsoft'a gelmesi için bir MX kaydı ekleyin

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız ve Devam Etmeniz istenir.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap'ta oturum açın.":::

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Açılan listeden Etki Alanı Listesi'ni seçin.":::

1. **Etki Alanı Listesi** sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Gelişmiş DNS'yi seçin.":::

1. **POSTA AYARLARI** bölümünde, **Email İletme** açılan **listesinden Özel MX'i** seçin.

    (Sayfayı aşağı kaydırmanız gerekebilir.)

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="Özel MX'i seçin.":::

1. **Yeni Kayıt Ekle'yi** seçin.

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="YENI KAYıT EKLEYIN.":::

1. Yeni kaydın kutularına, aşağıdaki tabloda yer alan değerleri yazın veya kopyalayıp yapıştırın.

    ( **Öncelik** kutusu, **Değer** kutusunun sağındaki adlandırılmamış kutudur. Açılan listeden **TTL** değerini seçin.)

    |Tür|Ana Bilgisayar|Değer|Öncelik|TTL|
    |---|---|---|---|---|
    |MX Kaydı|@|\<*domain-key*\>.mail.protection.outlook.com.  <br/> **Bu değer nokta (.) ile bitmelidir.** <br/> **Not:** Microsoft hesabınızdan alın *\<domain-key\>* .  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)|0  <br/> Öncelik hakkında daha fazla bilgi için bkz. [MX önceliği nedir?](../setup/domains-faq.yml)|30 dk|

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

1. Başka MX kayıtları varsa, aşağıdaki iki adımlık işlemi kullanarak bunların her birini kaldırın:

    İlk olarak, kaldırmak istediğiniz kayıt için **Sil'i** (çöp kutusu) seçin.

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="Sil'i seçin.":::

    İkinci olarak, silme işlemini onaylamak için **Evet'i** seçin.

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="Evet'i seçin.":::

    Bu yordamda daha önce eklediğiniz kayıt dışında tüm MX kayıtlarını kaldırın.

## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft için gereken CNAME kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız ve Devam Etmeniz istenir.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap'ta oturum açın.":::

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Etki Alanı Listesi'ne tıklayın.":::

1. **Etki Alanı Listesi** sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Gelişmiş DNS'yi seçin.":::

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ KAYIT EKLE'yi seçin.":::

1. **Tür** açılan listesinde **CNAME Kaydı'nı** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="CNAME Kaydı'nı seçin.":::

1. Yeni kaydın boş kutularında, **Kayıt Türü** için **CNAME**'yi seçin ve ardından aşağıdaki tablonun ilk satırında yer alan değerleri yazın ya da kopyalayıp yapıştırın.

    |Tür|Ana Bilgisayar|Değer|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>SPF'nin gereksiz e-postaları önlemesine yardımcı olmak için TXT kaydı ekleme

> [!IMPORTANT]
> Bir etki alanına yönelik SPF için birden fazla TXT kaydına sahip olamazsınız. Etki alanınızda birden fazla SPF kaydı varsa bu durum, e-posta hatalarının yanı sıra teslimat ve istenmeyen posta sınıflandırma sorunlarına neden olabilir. Etki alanınız için zaten bir SPF kaydınız varsa, Microsoft için yeni bir tane oluşturmayın. Bunun yerine, her iki değer kümesini içeren *tek*  bir SPF kaydına sahip olmak için gerekli Microsoft değerlerini geçerli kayda ekleyin.

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız ve Devam Etmeniz istenir.

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Etki Alanı Listesi'ne tıklayın.":::

1. **Etki Alanı Listesi** sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Gelişmiş DNS'yi seçin.":::

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ KAYIT EKLE'yi seçin.":::

1. **Tür** açılan listesinde **TXT Kaydı'nı** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="TXT Kaydı'nı seçin.":::

1. Yeni kaydın kutularına aşağıdaki tabloda yer alan aşağıdaki değerleri yazın veya kopyalayıp yapıştırın.

    (Açılan listeden **TTL** değerini seçin.)

    |Tür|Ana Bilgisayar|Değer|TTL|
    |---|---|---|---|
    |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **Not:** Tüm aralıkların doğru kalması için bu girdiyi kopyalayıp yapıştırmanızı öneririz.|30 dk|

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

## <a name="advanced-option-skype-for-business"></a>Gelişmiş seçenek: Skype Kurumsal

Bu seçeneği yalnızca kuruluşunuz Microsoft Teams'in yanı sıra sohbet, konferans aramaları ve görüntülü aramalar gibi çevrimiçi iletişim hizmetleri için Skype Kurumsal kullanıyorsa belirtin. Skype için 4 kayıt gerekir: Kullanıcıdan kullanıcıya iletişim için 2 SRV kaydı ve oturum açmak ve kullanıcıları hizmete bağlamak için 2 CNAME kaydı.

### <a name="add-the-two-required-srv-records"></a>Gerekli iki SRV kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız istenir.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap'ta oturum açın.":::

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Etki Alanı Listesi'ni seçin.":::

1. **Etki Alanı Listesi** sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Gelişmiş DNS'yi seçin.":::

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ KAYIT EKLE'yi seçin.":::

1. **Tür** açılan listesinde **SRV Kaydı'nı** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="SRV Kaydı türünü seçin.":::

1. Yeni kayıtların boş kutularına, aşağıdaki tablonun ilk satırında yer alan değerleri yazın veya kopyalayıp yapıştırın.

    |Hizmet|Protokol|Öncelik|Ağırlık|Bağlantı noktası|Hedef|TTL|
    |---|---|---|---|---|---|---|
    |_Sıp|_Tls|100|1|443|sipdir.online.lync.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|
    |_sipfederationtls|_Tcp|100|1|5061|sipfed.online.lync.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|

     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

1. Tablonun ikinci satırından değerleri seçerek diğer SRV kaydını ekleyin.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Skype Kurumsal için gereken iki CNAME kaydını ekleme

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ AD EKLE'yi seçin.":::

1. **Tür** açılan listesinde **CNAME'i** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="CNAME'i seçin.":::

1. Yeni kayıtların boş kutularına, tablonun ilk satırındaki değerleri yazın veya kopyalayıp yapıştırın.

    |Tür|Ana Bilgisayar|Değer|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|
    |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Tablodan CNAME değerlerini kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** (onay işareti) denetimini seçin.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

1. Tablonun ikinci satırından değerleri seçerek diğer CNAME kaydını ekleyin.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Gelişmiş seçenek: Microsoft 365 için Intune ve Mobil Cihaz Yönetimi

Bu hizmet, etki alanınıza bağlanan mobil cihazları güvenli ve uzaktan yönetmenize yardımcı olur. Mobil Cihaz Yönetimi, kullanıcıların cihazları hizmete kaydedebilmesi için iki CNAME kaydına ihtiyaç duyar.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Mobile Cihaz Yönetimi için gereken iki CNAME kaydını ekleme

1. Başlamak için [bu bağlantıyı](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) kullanarak Namecheap'taki etki alanları sayfanıza gidin. Oturum açmanız istenir.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap'ta oturum açın.":::

1. Giriş sayfasındaki **Hesap'ın** altında, açılan listeden **Etki Alanı Listesi'ni** seçin.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Etki Alanı Listesi'ne tıklayın.":::

1. **Etki Alanı Listesi** sayfasında, düzenlemek istediğiniz etki alanını seçin ve ardından **Yönet'i** seçin.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Yönet'i seçin.":::

1. **Gelişmiş DNS'yi** seçin.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Açılan listeden DNS Kayıtlarını Yönet'i seçin.":::

1. **KONAK KAYITLARI** bölümünde **YENİ KAYIT EKLE'yi** seçin.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="YENİ KAYIT EKLE'yi seçin.":::

1. **Tür** açılan listesinde **CNAME Kaydı'nı** seçin.

    > [!NOTE]
    > **Yeni KAYıT EKLE'yi** seçtiğinizde **Tür** açılan menüsü otomatik olarak görüntülenir.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="CNAME Kaydı'nı seçin.":::

1. Yeni kayıtların boş kutularına, tablonun ilk satırındaki değerleri yazın veya kopyalayıp yapıştırın.

    |Tür|Ana Bilgisayar|Değer|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Bu değer nokta (.) ile bitmelidir.**|Otomatik|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Tablodaki değerleri kopyalayıp yapıştırın.":::

1. **Değişiklikleri Kaydet** denetimini seçin.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Değişiklikleri Kaydet denetimini seçin.":::

1. Tablonun ikinci satırından değerleri seçerek diğer CNAME kaydını ekleyin.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
