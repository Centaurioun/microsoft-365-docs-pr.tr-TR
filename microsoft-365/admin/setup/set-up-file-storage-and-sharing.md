---
title: OneDrive dosya depolama ve paylaşımını ayarlama
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- SPO_Content
ms.custom:
- VSBFY23
- IT_Networking
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- ODB150
- ODB160
ms.assetid: 7aa9cdc8-2245-4218-81ee-86fa7c35f1de
description: Microsoft 365 depolama ve Microsoft 365 dosya paylaşımı için OneDrive'ı ve ekip sitesini kullanmayı öğrenin.
ms.openlocfilehash: 7e8a56b6ad1199ddc857919eb6b00f6ef2538d3b
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085695"
---
# <a name="set-up-file-storage-and-sharing-in-microsoft-365"></a>Microsoft 365'te dosya depolama ve paylaşımı ayarlama

İşletmeniz için dosya depolama ve paylaşım ayarlamanın en iyi yollarından biri, OneDrive ve ekip sitesini birlikte kullanmaktır. Küçük bir işletmeniz ve az sayıda çalışanınız varsa, bu seçenek sizin için idealdir.

## <a name="watch-where-to-store-files-in-office-365"></a>İzleyin: dosyaları Office 365'da nerede depolar?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FTHX] 

Bu videoyu faydalı bulduysanız, [küçük işletmelere ve Microsoft 365’i ilk kez kullananlara yönelik eğitim serisinin tamamına göz atın](../../business-video/index.yml).

## <a name="microsoft-365-document-storage-and-management"></a>Microsoft 365 belge depolama ve yönetimi

- OneDrive, dosyaların zaman zaman paylaşılmasıyla birlikte bireysel kullanım için tasarlanmıştır.

- Ekip sitesi, dosyaları düzenli olarak paylaşmak ve dosyalar üzerinde işbirliği yapmak için tasarlanmıştır. Ekip sitesi, birden çok kişinin sahip olduğu ve üzerinde işbirliği yapabilen paylaşılan sahipliği olan dosyaları depolamak için idealdir. Ekip sitesi eklemek için bir Microsoft Ekibi oluşturun. [Daha fazla bilgi için bkz. Teams'de ekip oluşturma](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b).

Hem OneDrive hem de ekip siteleri, siz ve çalışanlarınız için her yerden erişim sağlar.
  
![Microsoft 365 ürünlerinin OneDrive veya Ekip sitelerini nasıl kullanabileceğini gösteren diyagram.](../../media/7493131e-665f-4dbd-9a60-f5612aea7e42.png)
  
OneDrive ve ekip sitelerini birlikte kullandığınızda her konumda nelerin depolabileceğinize ilişkin öneriler şunlardır:<br/>

  
|Depolama konumu|Ne için?|Burada depolanabilecek öğeler|
|:-----|:-----|:-----|
|**OneDrive** |OneDrive'da içerik depolamak, dosyaları bilgisayarınızda depolamaya benzer; başka hiç kimse bunlara kolayca erişemez.<br/> Daha fazla bilgi için bkz. [OneDrive İş nedir?](https://support.microsoft.com/office/187f90af-056f-47c0-9656-cc0ddca7fdc2) <br/> |Diğer ekip üyelerinin üzerinde birlikte çalışması veya düzenli olarak erişmesi gerekmeyen iş dosyaları.<br/> |
|**SharePoint ekip siteleri** <br/> |Işbirliği. Bir Microsoft 365 grubu oluşturduğunuzda (örneğin, Microsoft 365 yönetim merkezi, Outlook'ta veya Microsoft Teams'de bir ekip oluşturarak), bu grup için bir SharePoint ekip sitesi oluşturulur. Benzer şekilde, SharePoint giriş sayfasından veya yeni SharePoint yönetim merkezinden yeni bir SharePoint ekip sitesi oluşturduğunuzda, bir Microsoft 365 grubu da oluşturulur. Daha fazla bilgi için bkz [. SharePoint ekip sitesi nedir?](https://support.microsoft.com/office/75545757-36c3-46a7-beed-0aaa74f0401e) ve [SharePoint Online'da ekip sitesi oluşturma](https://support.microsoft.com/office/ef10c1e7-15f3-42a3-98aa-b5972711777d).  <br/> |Paylaşılan sahipliği olan dosyalar. Kuruluşunuzdaki her çalışma birimi için ayrı ekip siteleri öneririz. Örneğin, personeli ve finansal belgeleri küçük bir ekipte özel tutmak için ayrı bir ekip sitesi oluşturun.  <br/> |

> [!NOTE]
> SharePoint'in işletmeniz için kullanabileceğiniz başka tür siteleri de vardır. Geniş bir hedef kitleye yönelik bilgileri yayımlamak için intranetinizdeki [iletişim sitelerini](https://support.microsoft.com/office/7fb44b20-a72f-4d2c-9173-fc8f59ba50eb) kullanabilirsiniz. Ayrıca [hub sitelerini](https://support.microsoft.com/office/fe26ae84-14b7-45b6-a6d1-948b3966427f) kullanarak intranetinizdeki siteleri bağlayabilirsiniz.
  
## <a name="start-using-onedrive-and-your-team-site"></a>OneDrive'ı ve ekip sitenizi kullanmaya başlama

### <a name="team-members-can-store-their-own-files-in-onedrive"></a>Ekip üyeleri kendi dosyalarını OneDrive'da depolayabilir

İşletmenizde microsoft 365 lisansı atanmış (ve SharePoint Online seçilmiş) her kişi OneDrive bulut depolama alanına sahip olur. İşle ilgili dosyaları herhangi bir cihazdan erişim için burada depolayabilirler ve yalnızca bu kullanıcı tarafından kullanılabilir. Örneğin, bir teklif taslağını, toplantı notlarını veya sunacakları tanıtım metnini depolayabilirler.
  
Çalışanlar OneDrive dosyalarını ve klasörlerini de paylaşabilir. Bir çalışan dışarıdaysa veya şirketten ayrılırsa, diğerleri OneDrive'da depolanan paylaşılan dosyalara (OneDrive ekip klasörü paylaşımı) erişebilir.
  
Ekibinizdeki her kişi OneDrive'ı şu şekilde ayarlayabilir ve dosyaları paylaşabilir.

1. <a href="https://admin.microsoft.com/ " target="_blank">Microsoft 365 yönetim merkezi</a> gidin ve kullanıcı adınız ve parolanızla oturum açın.

2. Uygulama başlatıcıdan **OneDrive'ı** seçin.

3. OneDrive'da ekip üyeleri kendi işle ilgili dosyalarını depolayabilir. Tek tek dosyaları veya bir klasörün tamamını paylaşabilirsiniz. Bir dosya veya klasör seçin, sağ tıklayın ve ardından **Paylaş'ı** seçin.

    ![Klasör paylaşma.](../../media/e8df9df3-aea5-404d-a320-92d7826c260c.png)
  
4. **Bağlantı Gönder** sayfasında, bağlantıya **sahip herkes görüntüleyebilir ve düzenleyebilir varsayılan seçimini değiştirmeyin**.

    Klasöre erişimi olmasını istediğiniz ekip üyelerinin adlarını veya e-posta adreslerini yazın ve isteğe bağlı bir ileti ekleyin.

    Gönderilecek e-postanın kendi kopyasını istiyorsanız, e-posta adresinizi listeye ekleyin.

    ![Yazmayı ve bir ad seçmeyi gösteren bağlantı paylaş iletişim kutusu.](../../media/877e6587-db9d-4903-a87b-11e570eee926.png)
  
5. Paylaşmak istediğiniz kişileri girmeyi bitirdiğinizde **Gönder'i** seçin. E-posta, seçtiğiniz kişilere hemen gönderilir.

    ![Ad listesini gösteren bir bağlantı paylaşın.](../../media/e85625ea-7655-43f3-8623-72db68d0ea39.png)
  
6. E-posta şöyle görünür. 

    ![OneDrive klasörünü paylaşma bağlantısıyla Email.](../../media/750c92e1-f14f-404c-a6a3-2095e26c680c.png)
  
### <a name="upload-files-to-a-team-site-for-online-collaboration"></a>Çevrimiçi işbirliği için dosyaları ekip sitesine yükleme

Ekip siteleri, dosyaları depolamak için belge kitaplığı olarak adlandırılan bir yerle birlikte gelir.  
  
Dosyaları ekleme adımları şunlardır:
  
1. Ekip sitenizin giriş sayfasında, sol taraftaki gezinti **menüsünden Belgeler'i** seçin. Bu seçenek **Belge kitaplığına** gitmenizi sağlar.
  
2. Microsoft 365'te oturumunuz açıkken görev çubuğunuzdan veya başka bir konumdan Windows **Dosya Gezgini** açın. Ekip sitenize yüklemek istediğiniz dosyalara gidin.

3. Ekip sitenize yüklemek istediğiniz dosyaları seçin ve belge **kitaplığına** sürükleyin.
  
4. İşlem tamamlandığında dosyalar hem ekip sitenizde hem de bilgisayarınızda depolanır.
  
5. Dosyaları bilgisayarınızdan silebilirsiniz. Bir sonraki adımda, [çevrimiçi dosyaları PC veya Mac'inizle eşitleyin](#sync-online-files-with-your-pc-or-mac), bilgisayarınızda bu dosyalar için yeni bir konum oluşturacaksınız.

    Ekip sitenize yüklenecek çok sayıda dosyanız veya büyük dosyalarınız varsa, [büyük veya çok sayıda dosyayı kitaplığa yüklemeyle](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) ilgili bu ipuçlarını okuyun.

    Daha fazla depolama alanı gerekiyorsa bkz. [Aboneliğinizde depolama alanını değiştirme](../../commerce/add-storage-space.md).

### <a name="sync-online-files-with-your-pc-or-mac"></a>Çevrimiçi dosyaları PC veya Mac'inizle eşitleme

Dosyaları ekip sitenize eklediğinize göre, artık bunları PC veya Mac'inizle eşitlenmek üzere ayarlayabilirsiniz. Bu şekilde, Microsoft Edge, Chrome veya başka bir tarayıcıda çalışmak yerine PC veya Mac bilgisayarınızdan dosyalarınızda çalışabilirsiniz. Ayrıca dosyalarınızın bilgisayarınızda eşitlenmiş olarak bulunması, İnternet'e bağlı değilken bir dosyaya ihtiyacınız olması durumunda işe yarayabilir.
  
Dosyaları bilgisayarınızla eşitlenecek şekilde ayarladıktan sonra, İnternet'e bağlı olduğunuzda, bunlar otomatik olarak eşitlenir.
  
Ekip sitenizdeki dosyaları masaüstü bilgisayarınızla şu şekilde eşitleyebilirsiniz:
  
1. Ekip sitenizin giriş sayfasında, sol taraftaki gezinti **menüsünden Belgeler'i** seçin. Bu sizi Belgeler kitaplığınıza götürür.

    > [!TIP]
    > Ekip sitenizdeki dosyaları eşitlerken, sitedeki her dosya kitaplığını eşitlersiniz, sitenin tamamını eşitlemezsiniz.
  
2. Tüm dosyaları eşitlemek için **Eşitle'yi** seçin. Veya eşitlemek istediğiniz belirli bir klasöre göz atın.

3. Uygulamalar arasında geçiş yapmanız istenirse **Evet'i** seçin. OneDrive, eşitlemeyi yapan işlemdir.
  
4. Ardından **OneDrive'ı ayarlama** istemi alırsanız iş veya okul hesabınızla oturum açın.

    ![OneDrive kurulum ekranı.](../../media/82cbb1ac-2ac5-42bd-82de-ba710bf46145.png)
  
5. OneDrive'ınızı henüz eşitlemediyseniz **Bu, OneDrive klasörünüzdür** ekranını görebilirsiniz. **OneDrive klasörünüz altındaki yolu kontrol** edin. Farklı bir yol kullanmak istiyorsanız **Konumu Değiştir'i** ve ardından **İleri'yi** seçin.

    ![Bu ekranda yerel klasörünüzü değiştirin.](../../media/6395485a-e729-4a9a-8e7d-b35e662435da.png)
  
6. Ekip sitelerinizdeki dosyalar, kuruluşunuzun adının altında Dosya Gezgini sol bölmesinde görünür. OneDrive'daki dosyalar "OneDrive - \<Name of Organization\>" altında görünür

    ![Yerel klasörünüzde nelerin eşitlendiğini görün.](../../media/93e2ca9f-4b5b-4930-a94d-ebc5b95aca84.png)
  
7. Eşitlemeyi bilgisayarınızda ekibin klasöründeki bir dosyayı açarak test edin. Bir değişiklik yapın ve **kaydet'i** seçin.

## <a name="best-practices-for-file-storage-and-sharing"></a>Dosya depolama ve paylaşım için en iyi yöntemler

OneDrive'dan veya SharePoint ekip sitenizden en iyi şekilde yararlanın.
  
### <a name="file-storage-and-collaboration-recommendations-for-other-types-of-small-businesses"></a>Diğer küçük işletme türleri için dosya depolama ve birlikte çalışma önerileri

- **Tek mülkiyet:** OneDrive'ı kullanarak kendi dosyalarınızı depolayın ve büyük/küçük harf temelinde müşterilerle paylaşın.

- **Ortak sahiplik:** Her iki sahip de OneDrive'ı kullanır ve dosyaları ileri geri paylaşır.

- **Dosyalara erişmesi gereken dış istemcilere veya iş ortaklarına sahip işletmeler**: Belirli bir müşteriye yönelik belgeleri depolamak ve paylaşmak için yeni bir ekip sitesi oluşturun. Siteyi yalnızca o müşteriye erişim izni verecek şekilde ayarlayın. Daha sonra bir müşterinin yanlışlıkla başka bir müşteriye yönelik bilgilere erişeceği konusunda endişelenmeniz gerekmez.

### <a name="keep-private-files-private"></a>Özel dosyaları gizli tutma

OneDrive'da bir dosyayı depoladığınızda, başkalarıyla paylaşmadığınız sürece dosyaya yalnızca siz erişebilirsiniz. Dosyaları paylaşırken, iletilebilen bir bağlantı oluşturmayı veya yalnızca belirli kişilerle paylaşmayı seçebilirsiniz. Ayrıca, OneDrive'da genel, kişisel veya tek tek projeler gibi farklı amaçlara yönelik klasörler de oluşturabilirsiniz. Her klasör farklı bir kişi veya grupla paylaşılabilir veya kimseyle paylaşılmaz.
  
Paylaşım hakkında daha fazla bilgi için bkz. [Microsoft 365 ile dosya ve klasör paylaşma](https://support.microsoft.com/office/72f26d6c-bf9e-432c-8b96-e3c2437f5b65).
  
### <a name="track-how-much-space-you-have-left"></a>Ne kadar alanınız kaldığını izleme

OneDrive'da ne kadar depolama alanınız kaldığını görmek için bkz. [OneDrive İş depolama alanınızı yönetme](https://support.microsoft.com/office/31519161-059C-4764-B6F8-F5CD29F7FE68).
  
### <a name="what-files-can-be-stored-in-onedrive-and-a-team-site"></a>OneDrive'da ve ekip sitesinde hangi dosyalar depolanabilir?

Neredeyse tüm dosya türlerini karşıya yükleyebilmenize karşın, dosya adlarındaki bazı dosya ad ve karakterlere izin verilmez. Daha fazla bilgi için bkz. [OneDrive İş geçersiz dosya karakterleri ve dosya türleri](https://support.microsoft.com/office/64883A5D-228E-48F5-B3D2-EB39E07630FA).
  
### <a name="enable-or-disable-third-party-storage-services"></a>Üçüncü taraf depolama hizmetlerini etkinleştirme veya devre dışı bırakma

Microsoft 365'te kullanıcılarınız için üçüncü taraf depolamayı etkinleştirerek, OneDrive ve ekip sitelerinin yanı sıra Dropbox gibi hizmetleri kullanarak belgeleri depolayabilir ve paylaşabilirsiniz. Bu, kullanıcılarınızın iş projelerinde zaten kullanıyor olabileceği veya kullanmayı tercih edebileceği hizmetleri sağlamak için mükemmel bir yol olabilir. Kuruluşunuzda Office kullanan kişilerin dosyaları üçüncü taraf bir hizmette açmasını istemiyorsanız, kapatmak için bu adımları izleyin.
  
> [!IMPORTANT]
> Üçüncü taraf depolama varsayılan olarak etkindir, bu nedenle kullanıcılarınız tarafından kullanılabilir olmasını istemiyorsanız bu adımları hemen gerçekleştirmeniz gerekir.
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Yönetim merkezinde</a> oturum açın.

2. **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Kuruluş ayarları**</a> sayfasına gidin.

3. **Hizmetler** sekmesinde **Web üzerinde Office'yi** seçin.

4. Üçüncü taraf depolamayı açmak veya kapatmak için onay kutusunu seçin veya seçimini kaldırın, ardından **Değişiklikleri kaydet'i** seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Ekip sitenizi dosya depolama ve paylaşım için özelleştirin](customize-team-site.md). Bu adımları izleyerek daha fazla depolama alanı ve işbirliği özelliklerinden nasıl yararlanacağınızı öğrenebilirsiniz.

- **Tablet ve telefonlarınızda Office uygulamalarını ayarlama**. OneDrive'da ve ekip sitelerinde depolanan dosyaları tablet veya telefonunuzdan **düzenleyebilmek** için bunu yapmanız gerekir. Tabletiniz veya telefonunuz için Office uygulamalarını yüklemezseniz dosyaları görüntüleyebilir ancak düzenleyemezsiniz.

  - [Microsoft 365 ile Android'de Office'i yükleme ve ayarlama](https://support.microsoft.com/office/cafe9d6f-8b0c-4b03-b20a-12438a82a22d)

  - [Microsoft 365 ile iPhone veya iPad'de Office'i yükleme ve ayarlama](https://support.microsoft.com/office/9df6d10c-7281-4671-8666-6ca8e339b628)

  - [Microsoft 365 ile Windows Phone'de Office'i ayarlama](https://support.microsoft.com/office/2b7c1b51-a717-45d6-90c9-ee1c1c5ee0b7)

## <a name="related-content"></a>İlgili içerik

[Aboneliğiniz için depolama alanı ekleme](../../commerce/add-storage-space.md) (makale)\
[Microsoft 365 İş ile dosya ve klasör paylaşma](https://support.microsoft.com/office/share-files-and-folders-with-microsoft-365-business-72f26d6c-bf9e-432c-8b96-e3c2437f5b65) (video)\
[Ekip sitenizi dosya depolama ve paylaşım için özelleştirme](customize-team-site.md) (makale)
