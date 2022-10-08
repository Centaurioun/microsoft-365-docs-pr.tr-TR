---
title: Microsoft 365'e aynı anda birkaç kullanıcı ekleme - yardım Yönetici
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
- admindeeplinkMAC
ms.collection:
- scotvorg
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: "İş için Microsoft 365'e elektronik tablodaki veya CSV biçimlendirilmiş başka bir dosyadaki listeden birden çok kullanıcı eklemeyi öğrenin. YouTube'da Microsoft 365'e hesap eklemeyi açıklayan bir video izleyin. Bu işlemin sonunda, hesabı olan her kullanıcının bir Microsoft 365 posta kutusu olacaktır. "
ms.openlocfilehash: c8453e5634245897a06867b422349c3350de03ae
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201187"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>Microsoft 365'e aynı anda birkaç kullanıcı ekleme - yardım Yönetici

Ekibinizdeki her kişinin oturum açıp e-posta ve Office gibi Microsoft 365 hizmetlerine erişebilmesi için önce bir kullanıcı hesabına ihtiyacı vardır. Çok fazla kişi varsa, Excel elektronik tablosundan veya CSV biçiminde kaydedilmiş başka bir dosyadan bu kişilerin hesaplarını bir kerede ekleyebilirsiniz. [CSV biçiminin ne olduğundan emin değil misiniz](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?
  
> [!NOTE]
> Yeni Microsoft 365 yönetim merkezini kullanmıyorsanız, Giriş sayfasının üst kısmında bulunan **Yeni yönetim merkezini deneyin** iki durumlu düğmesini seçerek yönetim merkezini açabilirsiniz.

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi birden çok kullanıcı ekleme

1. İş veya okul hesabınızla Microsoft 365'te oturum açın.

2. Yönetim merkezinde **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Etkin kullanıcılar'ı**</a> seçin.

3. **Birden çok kullanıcı ekle'yi** seçin.

4. **Birden çok kullanıcıyı içeri aktar** panelinde, dilerseniz örnek verilerin dolu veya boş olduğu örnek bir CSV dosyası indirebilirsiniz.

    Elektronik tablonuzun örnekle **aynı sütun başlıklarını** (Kullanıcı Adı, Ad vb.) içermesi gerekir. Şablonu kullanıyorsanız, şablonu Not Defteri gibi bir metin düzenleme aracında açın ve 1. satırdaki tüm verileri tek başına bırakmayı ve yalnızca 2. ve altındaki satırlara veri girmeyi göz önünde bulundurun.

    Elektronik tablonuzda her kullanıcı için kullanıcı adı (bob@contoso.com gibi) ve görünen ad (Bob Kelly gibi) değerleri de bulunmalıdır.

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. Kutuya bir dosya yolu girin veya **Gözat**'ı seçip CSV dosyasının konumuna gidin ve sonra **Doğrula**'yı seçin.
  
    Dosyayla ilgili bir sorun varsa bunları panelden görebilirsiniz. Bir günlük dosyası da indirebilirsiniz.

6. **Kullanıcı seçeneklerini ayarla** iletişim kutusunda oturum açma durumunu ayarlayabilir ve tüm kullanıcılara atanacak ürün lisansını seçebilirsiniz.

7. **Sonucunuzu görüntüleyin** iletişim kutusunda sonuçları kendinize ya da başka kullanıcılara gönderebilir (parolalar düz metin şeklinde olur), kaç kullanıcının oluşturulduğunu ve yeni kullanıcılar için daha fazla lisans satın almanız gerekip gerekmediğini görebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- Artık bu kişilerin hesapları olduğuna göre, [PC veya Mac bilgisayara Microsoft 365 veya Office 2016'yı indirmeleri ve yüklemeleri veya yeniden yüklemeleri](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) gerekir. Ekibinizdeki her kişi Microsoft 365'i en fazla 5 bilgisayara veya Mac bilgisayara yükleyebilir.

- Ayrıca her kişi iPhone, iPad ve Android telefonlar ve tabletler gibi en fazla 5 tablet ve 5 telefonda [bir mobil cihazda Office uygulamalarını ve e-postalarını ayarlayabilir](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) . Bu şekilde Office dosyalarını her yerden düzenleyebilirler.

    Kurulum adımlarının uçtan uca listesi için bkz. [İş için Microsoft 365'i ayarlama](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) .

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>Microsoft 365'e kullanıcı ekleme hakkında daha fazla bilgi

### <a name="not-sure-what-csv-format-is"></a>CSV biçiminin ne olduğu konusunda emin değil misiniz?

A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.
  
Başlangıç noktası olarak [bu örnek elektronik tabloyu](https://www.microsoft.com/download/details.aspx?id=45485) indirebilirsiniz. Microsoft 365'in ilk satırda sütun başlıkları gerektirdiğini unutmayın, bu nedenle bunları başka bir şeyle değiştirmeyin. 
  
Dosyayı yeni adla kaydedin ve CSV biçimini belirtin.
  
![Excel'de csv biçiminde dosya kaydetmenin resmi.](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.
  
![Excel'den alabileceğiniz ve dosyayı gerçekten CSV biçimi olarak kaydetmek isteyip istemediğinizi soran istemin resmi.](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>Elektronik tablonuzu biçimlendirme ipuçları

- **Örnek elektronik tablodaki gibi örnek sütun başlıklarına ihtiyacım var mı?** Evet. Örnek elektronik tablonun ilk satırında sütun başlıkları vardır. Bu başlıklar gereklidir. Microsoft 365'e eklemek istediğiniz her kullanıcı için başlığın altında bir satır oluşturun. Sütun başlıklarından herhangi birini ekler, değiştirir veya silerseniz, Microsoft 365 dosyadaki bilgilerden kullanıcı oluşturamayabilir.

- **What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.

- **Elektronik tablo ne kadar küçük veya büyük olabilir?** Elektronik tabloda en az iki satır olmalıdır. One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet.

- **Hangi dilleri kullanabilirim?** Elektronik tablonuzu oluştururken, kullanıcı verileri sütun etiketlerini herhangi bir dilde veya karakterde girebilirsiniz, ancak örnekte gösterildiği gibi etiketlerin sırasını değiştirmemelisiniz. You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.

- **What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.

- **Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.

|**Kullanıcı verisi sütun etiketi**|**En fazla karakter uzunluğu**|
|:-----|:-----|
|Kullanıcı Adı (Gerekli)  <br/> |79 işareti (@), name@domain biçiminde..\<extension\>. Kullanıcının diğer adı 50 karakteri ve etki alanı adı 48 karakteri aşamaz.  <br/> |
|Ad  <br/> |64  <br/> |
|Soyadı  <br/> |64  <br/> |
|Görünen Ad (gerekli)  <br/> |256  <br/> |
|İş Unvanı  <br/> |64  <br/> |
|Bölüm  <br/> |64  <br/> |
|Ofis Numarası  <br/> |128  <br/> |
|Ofis Telefonu  <br/> |64  <br/> |
|Cep Telefonu  <br/> |64  <br/> |
|Faks  <br/> |64  <br/> |
|Adres  <br/> |1023  <br/> |
|Şehir  <br/> |128  <br/> |
|Eyalet veya İl  <br/> |128  <br/> |
|ZIP veya Posta Kodu  <br/> |40  <br/> |
|Ülke veya Bölge  <br/> |128  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>Microsoft 365'e kullanıcı eklerken hala sorun mu yaşıyorsunuz?

- **Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.

- **Microsoft 365'teki yeni kullanıcıları hemen görmüyorsanız birkaç dakika bekleyin.** Değişikliklerin Microsoft 365'teki tüm hizmetlere gitmesi biraz zaman alabilir. 

## <a name="related-articles"></a>İlgili makaleler

[Kullanıcıları Microsoft 365'e tek tek veya toplu olarak ekleme](/office365/admin/add-users/add-users)