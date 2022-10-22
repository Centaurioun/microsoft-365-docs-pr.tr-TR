---
title: Microsoft Syntex'te modern şablon oluşturma
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft Syntex'te modern bir şablon oluşturmayı öğrenin.
ms.openlocfilehash: af64b97c104e218ca851182ce043e3a65e72a159
ms.sourcegitcommit: a250d043a2e42ecbc7b86147468d1660af5a6ba7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68673139"
---
# <a name="create-a-modern-template-in-microsoft-syntex"></a>Microsoft Syntex'te modern şablon oluşturma

## <a name="upload-a-document-to-create-a-modern-template"></a>Modern şablon oluşturmak için belgeyi karşıya yükleme

Modern bir şablon oluşturmak için bu adımları izleyin.

1. SharePoint belge kitaplığından Yeni **Modern şablon oluştur'u** >  seçin.

   ![Modern şablon oluştur seçeneğinin vurgulandığı belge kitaplığının ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-1.png)

2. Kuruluşunuzun SharePoint veya OneDrive'ından ya da yerel depolama alanınızdan karşıya yüklemek için bir Word belgesi seçin.

   ![Belgeyi seçtiğiniz karşıya yükleme sayfasının ekran görüntüsü.](../media/content-understanding/content-assembly-pick-a-file.png)

3. Belgeyi karşıya yükledikten sonra, belge şablon stüdyosunda görüntülenir ve burada alanları ekleyerek belgeyi şablona dönüştürebilirsiniz.

   ![Şablon görüntüleyicisindeki belgenin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-3.png)

4. Şablon stüdyosunun sol üst köşesinde şablonun adını seçin. Varsayılan ad, şablonu oluşturmak için kullanılan belgenin adıdır. Şablonu yeniden adlandırmak istiyorsanız, varsayılan adı veya adın yanındaki kalem simgesini seçin, yeni adı yazın ve **ardından Enter'ı** seçin.

   ![Yeniden adlandırmayı seçecek belgenin adını gösteren şablon görüntüleyicisinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-3a.png)

<!---
5. Create placeholders for all dynamic text in the document that users might want to change from one document to another. For example, you might want to create a placeholder for input such as company name, client name, address, phone number, or date.

    To create a placeholder, select the text (such as the date). The **All placeholders** panel will open, where you'll give the placeholder a relevant name and choose the type of input you want to associate with the placeholder.
 
   ![Screenshot of the template viewer showing a field highlighted and the All placeholders panel.](../media/content-understanding/content-assembly-create-template-4b.png)

   Currently, there are three ways for users to fill in a placeholder:

   - [Enter text or select a date](#associate-a-placeholder-by-entering-text-or-selecting-a-date)
   - [Select from choices in a column of a list or library](#associate-a-placeholder-by-selecting-from-choices-in-a-column-of-a-list-or-library)
   - [Select from managed metadata term set or term](#associate-a-placeholder-by-selecting-from-managed-metadata-term-set-or-term)

   > [!NOTE]
   > You can create placeholders for text, and also placeholders for text within cells in a table. However, images, smart art, complete tables, and bulleted lists are currently not supported.   
--->

## <a name="associate-fields-with-different-data-sources"></a>Alanları farklı veri kaynaklarıyla ilişkilendirme

Alanları ve yer tutucuları şu şekilde ilişkilendirebilirsiniz:

- [Metin girme veya tarih seçme](#associate-a-placeholder-by-entering-text-or-selecting-a-date)

- [Liste veya kitaplığın sütunundaki seçenekler arasından seçim yapma](#associate-a-placeholder-by-selecting-from-choices-in-a-column-of-a-list-or-library)

- [Yönetilen meta veri terim kümesinden veya terimden seçme](#associate-a-placeholder-by-selecting-from-a-managed-metadata-term-set-or-term)

### <a name="associate-a-placeholder-by-entering-text-or-selecting-a-date"></a>Metin girerek veya tarih seçerek yer tutucuyu ilişkilendirme

**Tüm yer tutucular** panelinde:

1. **Ad** alanına yer tutucu için uygun bir ad girin.

   ![El ile giriş için Tüm yer tutucular panelini gösteren şablon görüntüleyicisinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-5a.png)

2. **Yazarların bu yer tutucuyu nasıl doldurduğu** bölümünde **Metin girin'i seçin veya bir tarih seçin**.

3. **Bilgi türü** alanında, yer tutucuyla ilişkilendirmek istediğiniz veri türünü seçin. Şu anda altı seçenek vardır: **Tek satırlı metin**, **Birden çok metin satırı**, **Sayı**, **Tarih ve saat**, **Email** ve **Köprü**.

4. **Ekle**'yi seçin.

   > [!NOTE]
   > AA/GG/YYYY, DD/AA/YYYY, YYYY/AA/GG ve Ay DD gibi birden çok tarih biçimlendiricisi yapılandırabilirsiniz; ayrıca saati hem 12 saat hem de 24 saatlik biçimde ayarlayabilirsiniz. 

### <a name="associate-a-placeholder-by-selecting-from-choices-in-a-column-of-a-list-or-library"></a>Bir liste veya kitaplığın sütunundaki seçenekler arasından seçim yaparak yer tutucuyu ilişkilendirme

**Tüm yer tutucular** panelinde:

1. **Ad** alanına yer tutucu için uygun bir ad girin.

   ![SharePoint listesinden giriş için Tüm yer tutucular panelini gösteren şablon görüntüleyicisinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-6a.png)

2. **Yazarların bu yer tutucuyu nasıl doldurduğu** bölümünde, **liste veya kitaplığın sütunundaki seçeneklerden seç'i** ve ardından **Seç'i** seçin.

3. **Kaynak sütun eklemek için liste seçin** sayfasında, kullanmak istediğiniz listeyi seçin ve ardından **İleri'yi** seçin.

   ![Listeleri gösteren kaynak sütun eklemek için liste seçin sayfasının ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-7.png)

4. **Var olan liste sayfasında Kaynak sütun seçin** sayfasında, yer tutucuyla ilişkilendirmek istediğiniz sütun adını seçin ve ardından **Kaydet'i** seçin.

   ![Mevcut liste sayfasından sütun adlarını gösteren Kaynak sütun seçin öğesinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-8.png)

    Listelerin özgün sayfasını yeniden görmek istiyorsanız listenin en altındaki **Git (liste adı)** bağlantısını seçin.

5. İşiniz bittiğinde, liste alanının yer tutucuyla ilişkilendirildiğini görürsünüz.

   ![Yer tutucuyla ilişkilendirilmiş liste alanını gösteren Tüm yer tutucular panelinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-9.png)

6. Kullanıcıların el ile giriş ekleyebilmesini istiyorsanız, listeden seçim yapmaya ek olarak **Yazarların yeni seçenekler eklemesine izin ver'i** seçin. Bu durumda, el ile giriş veri türü için varsayılan değer *Tek satır metindir*. Ayrıca, yazarların giriş yaptığı değerler yalnızca belgeyi oluşturmak için kullanılır. SharePoint listesine eklenmez.

### <a name="associate-a-placeholder-by-selecting-from-a-managed-metadata-term-set-or-term"></a>Yönetilen meta veri terim kümesinden veya terimden seçim yaparak yer tutucuyu ilişkilendirme

**Tüm yer tutucular** panelinde:

1. **Ad** alanına yer tutucu için uygun bir ad girin.

   ![Bir terim veya terim kümesinden giriş için Tüm yer tutucular panelini gösteren şablon görüntüleyicisinin ekran görüntüsü.](../media/content-understanding/content-assembly-create-template-term.png)

2. **Yazarların bu yer tutucuyu nasıl doldurduğu** bölümünde **Yönetilen meta veri terim kümesinden veya teriminden seç'i** ve ardından **Seç'i** seçin.

3. **Terim kümelerini veya terimleri seçin** sayfasında, yer tutucuyla ilişkilendirilecek terim kümesini veya terimi arayın veya seçin ve ardından **Kaydet'i** seçin.

   ![Terim kümelerini veya terimleri seçin sayfasının ekran görüntüsü.](../media/content-understanding/content-assembly-select-term.png)

4. İşiniz bittiğinde, seçilen terim kümesinin veya terimin yer tutucuyla ilişkilendirildiğini görürsünüz. 

   ![İlişkili terim kümesini veya terimi gösteren Tüm yer tutucular panelinin ekran görüntüsü.](../media/content-understanding/content-assembly-associated-term.png)

5. Kullanıcıların terim kümesine veya terime karşılık gelen birden çok değer ekleyebilmesini istiyorsanız **Birden çok değere izin ver'i** seçin. Ayrıca terim kümesi açık terim kümesi olarak yapılandırılmışsa **Yeni değerlere izin ver'i** seçebilirsiniz. Bu seçeneği etkinleştirirseniz, modern şablondan belge oluşturan kullanıcılar terim kümesine yeni terimler ekleyebilir ve bu terimleri yer tutucu değerler olarak ekleyebilir.

   > [!TIP]
   > **Yeni değerlere izin ver** seçeneğini etkinleştirdiğinizde (yalnızca açık terim kümeleri için izin verilir), kullanıcıların terim deposuna yedekli terimler ekleme olasılığı daha yüksektir. Yedekli terimler, yöneticilerin terim kümesini yönetmesini zorlaştırabilir.

## <a name="save-a-modern-template-as-a-draft"></a>Modern şablonu taslak olarak kaydetme

Gerekli olduğunu düşündüğünüz kadar alan oluşturabilirsiniz. İşiniz bittiğinde, şablonu taslak olarak kaydetmeyi seçebilirsiniz.

1. Şablonu taslak olarak kaydetmek için **Taslağı kaydet'i** seçin ve daha sonra erişebilirsiniz.

2. **Modern şablonlar'daki** **Taslak şablonları** açılan menüsünden kaydedilmiş taslakları görüntülemek, düzenlemek veya yayımlamak için belge kitaplığından **Yeni** > **Düzenle menüsünü** seçin.

## <a name="publish-a-modern-template"></a>Modern şablon yayımlama

Şablona tüm ilgili alanları eklemeyi tamamladığınızda ve belge kitaplığındaki diğer kullanıcılar tarafından kullanılabilir hale getirmek istediğinizde, şablonu yayımlayabilirsiniz.

1. Belge oluşturmak için kuruluştaki diğer kullanıcılar tarafından kullanılacak şablonu yayımlamak için **Yayımla'yı** seçin.

2. Yayımlanan *şablonları* **Modern** **şablonlar bölümündeki Yayımlanan şablonlar** açılan menüsünde görüntülemek, düzenlemek veya yayımdan kaldırmak için belge kitaplığından **Yeni** > **Düzenle menüsünü** seçin. 

## <a name="see-also"></a>Ayrıca bkz.

[Modern şablonu düzenleme](content-assembly-edit-template.md)