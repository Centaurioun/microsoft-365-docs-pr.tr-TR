---
title: Uç Nokta DLP'lerini kullanma
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Uç nokta veri kaybı önleme konumlarını kullanmak için veri kaybı önleme (DLP) ilkelerini yapılandırmayı öğrenin.
ms.openlocfilehash: 2fef9c2d89d741c70f3d2d903f41fa8a354d4a79
ms.sourcegitcommit: 979343980f05ceb546ca0df23562504aaca34b88
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2022
ms.locfileid: "66912640"
---
# <a name="using-endpoint-data-loss-prevention"></a>Uç noktada veri kaybı önlemeyi kullanma

Uç Nokta DLP özelliklerini ve DLP ilkelerinde nasıl ortaya çıkardıklarını öğrenmek için izlemeniz gereken bazı senaryolar oluşturduk.

> [!IMPORTANT]
> Bu Uç Nokta DLP senaryoları, DLP ilkelerini oluşturmaya ve ayarlamaya yönelik resmi yordamlar değildir. Genel durumlarda DLP ilkeleriyle çalışmanız gerektiğinde aşağıdaki konulara bakın:
>
>- [Microsoft Purview Veri Kaybı Önleme hakkında bilgi edinin](dlp-learn-about-dlp.md)
>- [Varsayılan DLP ilkesini kullanmaya başlama](get-started-with-the-default-dlp-policy.md)
>- [Bir şablondan DLP ilkesi oluşturma](create-a-dlp-policy-from-a-template.md)
>- [Bir DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md)


## <a name="before-you-begin"></a>Başlamadan önce

### <a name="skusubscriptions-licensing"></a>SKU/abonelik lisanslama

Tam lisanslama ayrıntıları için bkz. [Bilgi koruması için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

## <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>Senaryo 1: Şablondan ilke oluşturma, yalnızca denetim

Bu senaryolar, etkinlik gezginine eklenen ve raporlayan cihazlarınız olmasını gerektirir. Henüz cihaz eklemediyseniz bkz [. Uç nokta veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md).

1. [Veri kaybı önleme sayfasını](https://compliance.microsoft.com/datalossprevention?viewid=policies) açın.

2. **İlke oluştur'u** seçin.

3. Bu senaryo için **Gizlilik'i**, ardından **ABD Kişisel Bilgiler (PII) Verileri'ni** ve **ardından İleri'yi** seçin.

4. **Cihazlar** dışındaki tüm konumlar için **Durum** alanını kapalı konuma getirin. **İleri**'yi seçin.

5. **Şablon seçiminden varsayılan Ayarları gözden geçir ve özelleştir'i** kabul edin ve **İleri'yi** seçin.

6. Varsayılan **Koruma eylemleri** değerlerini kabul edin ve **İleri'yi** seçin.

7. **Windows cihazlarında Etkinlikleri denetle veya kısıtla'yı** seçin ve eylemleri **Yalnızca denetle** olarak bırakın. **İleri**'yi seçin.

8. **İlk değeri test etmek istediğim** varsayılan değeri kabul edin ve **Test modundayken ilke ipuçlarını göster'i** seçin. **İleri**'yi seçin.

9. Ayarlarınızı gözden geçirin ve **Gönder'i** seçin.

10. Yeni DLP ilkesi, ilke listesinde görünür.

11. İzlenen uç noktalardan gelen veriler için Etkinlik gezgini'ne bakın. Cihazlar için konum filtresini ayarlayın ve ilkeyi ekleyin, ardından bu ilkenin etkisini görmek için ilke adına göre filtreleyin; Gerekirse etkinlik [gezginini kullanmaya başlama](data-classification-activity-explorer.md) bölümüne bakın.

12. ABD Kişisel Bilgiler (PII) Veri koşulunu tetikleyecek içerik içeren bir test öğesini kuruluşunuzun dışındaki biriyle paylaşmaya çalışın. Bu, ilkeyi tetiklemelidir.

13. Olay için Etkinlik gezgini'ni denetleyin.

## <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>Senaryo 2: Mevcut ilkeyi değiştirme, uyarı ayarlama

1. [Veri kaybı önleme sayfasını](https://compliance.microsoft.com/datalossprevention?viewid=policies) açın.

2. 1. senaryoda oluşturduğunuz **ABD Kişisel Bilgiler (PII) Veri** ilkesini seçin.

3. **İlkeyi düzenle'yi** seçin.

4. **Gelişmiş DLP kuralları** sayfasına gidin ve **Algılanan düşük hacimli abd kişisel bilgi kaynağını** düzenleyin.

5. **Olay raporları** bölümüne gidin ve **Kural eşleşmesi gerçekleştiğinde Yöneticilere uyarı gönder** seçeneğini **Açık** olarak ayarlayın. Email uyarıları otomatik olarak yöneticiye ve alıcı listesine eklediğiniz diğer kişilere gönderilir. 

![olay raporlarını açın.](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. Bu senaryonun amaçları doğrultusunda, **bir etkinlik kuralla her eşleştiğinde Uyarı gönder'i** seçin.

7. **Kaydet**'i seçin.

8. **İleri'yi** seçip İlke değişikliklerini **gönder'i** seçerek önceki tüm ayarlarınızı koruyun.

9. ABD Kişisel Bilgiler (PII) Veri koşulunu tetikleyecek içerik içeren bir test öğesini kuruluşunuzun dışındaki biriyle paylaşmaya çalışın. Bu, ilkeyi tetiklemelidir.

10. Olay için Etkinlik gezgini'ni denetleyin.

## <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>Senaryo 3: Var olan ilkeyi değiştirme, geçersiz kılmaya izin ver eylemini engelleme

1. [Veri kaybı önleme sayfasını](https://compliance.microsoft.com/datalossprevention?viewid=policies) açın.

2. 1. senaryoda oluşturduğunuz **ABD Kişisel Bilgiler (PII) Veri** ilkesini seçin.

3. **İlkeyi düzenle'yi** seçin.

4. **Gelişmiş DLP kuralları** sayfasına gidin ve **Algılanan düşük hacimli abd kişisel bilgi kaynağını** düzenleyin.

5. Ekranı aşağı kaydırarak **Windows cihazındaki etkinlikleri denetle veya kısıtla** bölümüne gelin ve her etkinlik için ilgili eylemi  **Geçersiz kılmayla engelle** olarak ayarlayın.

   > [!div class="mx-imgBorder"]
   > ![engellemeyi geçersiz kılma eylemiyle ayarlayın.](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. **Kaydet**'i seçin.

7. **ABD Kişisel Olarak Tanımlanabilir Inf algılanan yüksek hacimli içerik** için 4-7 arası adımları yineleyin.

8. **İleri'yi** seçip İlke değişikliklerini **gönder'i** seçerek önceki tüm ayarlarınızı koruyun.

9. ABD Kişisel Bilgiler (PII) Veri koşulunu tetikleyecek içerik içeren bir test öğesini kuruluşunuzun dışındaki biriyle paylaşmaya çalışın. Bu, ilkeyi tetiklemelidir.

   İstemci cihazında şuna benzer bir açılır pencere görürsünüz:

   > [!div class="mx-imgBorder"]
   > ![endpoint dlp istemcisi engellenen geçersiz kılma bildirimi.](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. Olay için Etkinlik gezgini'ni denetleyin.

## <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>Senaryo 4: Otomatik karantina (önizleme) ile bulut eşitleme uygulamalarından DLP bildirimlerini döngüye almaktan kaçının

### <a name="before-you-begin"></a>Başlamadan önce

Bu senaryoda, dosyaları **Son Derece Gizli** duyarlılık etiketiyle OneDrive ile eşitleme engellenir. Bu, birden çok bileşen ve yordam içeren karmaşık bir senaryodur. Size gerekenler:

- Yerel OneDrive klasörünü OneDrive bulut depolama alanıyla zaten eşitleyen, hedeflenecek bir AAD kullanıcı hesabı ve eklenen bir Windows 10 bilgisayar.
- Duyarlılık etiketleri yapılandırılır ve yayımlanır; bkz. [Duyarlılık etiketlerini kullanmaya başlama](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels) ve [Duyarlılık etiketleri ve ilkeleri oluşturma ve yapılandırma](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies).

Üç prosedür vardır.

1. Uç Nokta DLP Otomatik karantina ayarlarını yapılandırın.
2. **Çok Gizli** duyarlılık etiketine sahip hassas öğeleri engelleyen bir ilke oluşturun.
3. Windows 10 cihazında ilkenin hedeflendiği bir Word belgesi oluşturun, etiketi uygulayın ve eşitlenen kullanıcı hesapları yerel OneDrive klasörüne kopyalayın.  

### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>Uç Nokta DLP'sinde izin verilmeyen uygulama ve Otomatik karantina ayarlarını yapılandırma

1. [Uç Nokta DLP ayarlarını](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings) açma

2. **İzin verilmeyen uygulamalar'ı** genişletin.

3. **İzin verilmeyen uygulamaları ekle veya düzenle'yi** seçin ve *OneDrive'ı* görünen ad olarak ekleyin ve yürütülebilir ad *onedrive.exe* onedrive.exe **Son Derece Gizli** etiketindeki öğelere erişmesini engelleyin.

4. **Otomatik karantinaya al** ve **Kaydet'i** seçin.

5. **Otomatik karantina ayarları'nın** altında **Otomatik karantina ayarlarını düzenle'yi** seçin.

6. **İzin verilmeyen uygulamalar için Otomatik karantinayı** etkinleştirin.

7. Yerel makinelerde özgün hassas dosyaların taşınmasını istediğiniz klasörün yolunu girin. Örneğin:
   
    *Isaiah langer* kullanıcı adı için **'%homedrive%%homepath%\Microsoft DLP\Quarantine'**, taşınan öğeleri şu adlı klasöre yerleştirir:  

    *C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive*

    ve özgün dosya adına bir tarih ve saat damgası ekleyin.
    
    > [!NOTE]
    > DLP Otomatik Karantina, izin verilmeyen her uygulama için dosyalar için alt klasörler oluşturur. Bu nedenle, izin verilmeyen uygulamalar listenizde hem *Not Defteri* hem de *OneDrive* varsa, **\OneDrive** için bir alt klasör ve **\Not Defteri** için başka bir alt klasör oluşturulur.

8. **Dosyaları aşağıdaki metni içeren bir .txt dosyasıyla değiştir'i** seçin ve yer tutucu dosyaya istediğiniz metni girin. Örneğin *, 1.docxauto quar* adlı bir dosya için:
    
    > %%FileName%% kuruluşunuzun veri kaybı önleme (DLP) ilkesi %%PolicyName%% ile koruduğu ve karantina klasörüne taşınan hassas bilgileri içerir: %%QuarantinePath%%
    
    şu iletiyi içeren bir metin dosyası bırakır:
    
    > auto quar 1.docx, kuruluşunuzun veri kaybı önleme (DLP) ilkesiyle koruduğu ve karantina klasörüne taşınan hassas bilgileri içerir: C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive\auto quar 1_20210728_151541.docx.

9. **Kaydet'i** seçin

### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>Duyarlılık etiketi Son Derece Gizli olan dosyaların OneDrive eşitlemesini engellemek için bir ilke yapılandırma

1. [Veri kaybı önleme sayfasını](https://compliance.microsoft.com/datalossprevention?viewid=policies) açın.

2. **İlke oluştur'u** seçin.

3. Bu senaryo için **Özel'i**, özel **ilke'yi** ve **ardından İleri'yi** seçin.

4. **Ad** ve **Açıklama** alanlarını doldurun, **İleri'yi** seçin.

5. **Cihazlar** dışındaki tüm konumlar için **Durum** alanını kapalı konuma getirin. Bunu test etmek istediğiniz belirli bir son kullanıcı hesabınız varsa, bunu kapsamda seçtiğinizden emin olun. **İleri**'yi seçin.

6. Varsayılan **Gelişmiş DLP kuralları oluştur veya özelleştir** seçimini kabul edin ve **İleri'yi** seçin.

7. Şu değerlerle bir kural oluşturun:
    1. **Adı** >  *Senaryo 4 Otomatik karantina*.
    1. **Koşul -ları** >  **İçerik içeriği** >  **Duyarlılık etiketleri** >  **Çok Gizli**.
    1.  **Eylem** >  **Windows cihazlarında** >  etkinlikleri denetleme veya kısıtlama **İzin verilmeyen uygulamalarla** >  erişim **Engelle'ye bakın**. Bu senaryonun amaçları doğrultusunda diğer tüm etkinlikleri temizleyin.
    1. **Kullanıcı bildirimleri** >  **Açık**.
    1. **Uç nokta cihazları** > Etkin olmayan **bir etkinlik olduğunda Kullanıcılara ilke ipucu bildirimi göster'i** seçin.
    
8. **Kaydet ve** **İleri'yi** seçin.

9. **Hemen aç'ı** seçin. **İleri**'yi seçin.

10. Ayarlarınızı gözden geçirin ve **Gönder'i** seçin.

    > [!NOTE]
    > Yeni ilkenin çoğaltılması ve hedef Windows 10 bilgisayara uygulanması için en az bir saat bekleyin.

11. Yeni DLP ilkesi, ilke listesinde görünür.

### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Windows 10 cihazda Otomatik karantinayı test etme

1. [Son Derece Gizli 5. adım duyarlılık etiketine sahip dosyaların OneDrive eşitlemesini engellemek için ilke yapılandırma](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential) bölümünde belirttiğiniz kullanıcı hesabıyla Windows 10 bilgisayarda oturum açın.

2. İçeriği OneDrive ile eşitlenmeyecek bir klasör oluşturun. Örneğin:

    *C:\otomatik karantina kaynak klasörü*

3. Microsoft Word'u açın ve otomatik karantina kaynak klasöründe bir dosya oluşturun. **Son derece gizli** duyarlılık etiketini uygulayın; Bkz. [Office'te dosyalarınıza ve e-postanıza duyarlılık etiketleri uygulama](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

4. Yeni oluşturduğunuz dosyayı OneDrive eşitleme klasörünüze kopyalayın. Eyleme izin verilmediğini ve dosyanın karantinaya alınacağını belirten bir kullanıcı bildirimi görüntülenmelidir. Örneğin, kullanıcı adı *Isaiah Langer* ve *otomatik karantina belgesi* başlıklı belge 1.docxşu iletiyi görürsünüz:

    ![Belirtilen dosya için OneDrive eşitleme eylemine izin verilmediğini ve dosyanın karantinaya alınacağını belirten veri kaybı önleme kullanıcı bildirimi açılır penceresi.](../media/auto-quarantine-user-notification-toast.png)
    
    İleti şu şekildedir:
    
    > Otomatikquarantine belgesinin bu uygulamayla 1.docx açılmasına izin verilmez. Dosya 'C:\Users\IsaiahLanger\Microsoft DLP\OneDrive' için karantinaya alınacaktır

5. **Kapat'ı** seçin.

6. Yer tutucu metin dosyasını açın. Otomatik **karantina belgesi 1.docx_ *date_time*.txt** olarak adlandırılır. 

7. Karantina klasörünü açın ve özgün dosyanın orada olduğunu onaylayın.
 
8. İzlenen uç noktalardan gelen veriler için Etkinlik gezgini'ne bakın. Cihazlar için konum filtresini ayarlayın ve ilkeyi ekleyin, ardından bu ilkenin etkisini görmek için ilke adına göre filtreleyin; Gerekirse etkinlik [gezginini kullanmaya başlama](data-classification-activity-explorer.md) bölümüne bakın.

9. Olay için Etkinlik gezgini'ni denetleyin.

## <a name="scenario-5-restrict-unintentional-sharing-to-unallowed-cloud-apps-and-services"></a>Senaryo 5: İstenmeyen paylaşımı izin verilmeyen bulut uygulamaları ve hizmetleriyle kısıtlama

Endpoint DLP ve Microisoft Edge Web tarayıcısı ile hassas öğelerin yanlışlıkla paylaşılmasıyla izin verilmeyen bulut uygulamaları ve hizmetleri kısıtlayabilirsiniz. Edge, bir öğenin Bir Uç Nokta DLP ilkesi tarafından ne zaman kısıtlandığını anlar ve erişim kısıtlamalarını zorlar.

Düzgün yapılandırılmış bir DLP ilkesinde konum olarak **Cihazlar'ı** seçip Microsoft Edge tarayıcısını kullandığınızda, bu ayarlarda tanımladığınız izin verilmeyen tarayıcıların DLP ilke denetimlerinizle eşleşen hassas öğelere erişmesi engellenir. Bunun yerine kullanıcılar, DLP tarafından uygulanan kısıtlamaları anlayarak DLP ilkesindeki koşullar karşılandığında etkinlikleri engelleyebilecek veya kısıtlayan Microsoft Edge'i kullanmaya yönlendirilecektir.

Bu kısıtlamayı kullanmak için üç önemli parça yapılandırmanız gerekir:

1. Hassas öğelerin paylaşılmasını önlemek istediğiniz yerleri (hizmetler, etki alanları, IP adresleri) belirtin.

2. DLP ilkesi eşleşmesi gerçekleştiğinde belirli hassas öğelere erişmesine izin verilmeyen tarayıcıları ekleyin.

3. **Bulut hizmetlerine yükle** ve **İzin verilmeyen tarayıcıdan erişim'i** açarak karşıya yüklemenin bu konumlara kısıtlanması gereken hassas öğe türlerini tanımlamak için DLP ilkelerini yapılandırın.

İş gereksinimlerinizi karşılamak ve hassas verileri korumak için kısıtlamalarınızı genişletmek ve genişletmek için yeni hizmetler, uygulamalar ve ilkeler eklemeye devam edebilirsiniz. 

Bu yapılandırma, verilerinizin güvende kalmasını sağlarken kullanıcıların hassas olmayan öğelere erişmesini ve bunları paylaşmasını engelleyen veya kısıtlayan gereksiz kısıtlamaları da önler.

## <a name="scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains-preview"></a>Senaryo 6 Hassas hizmet etki alanlarında kullanıcı etkinliklerini izleme veya kısıtlama (önizleme)

Bir web sitesinde bu kullanıcı etkinliklerini denetlemek, geçersiz kılmayla engellemek veya engellemek istediğinizde bu senaryoyı kullanın.

- web sitesinden yazdırma
- web sitesinden veri kopyalama
- web sitesini yerel dosyalar olarak kaydetme

Kullanıcının Web sitesine Microsoft Edge üzerinden erişmesi gerekir.

### <a name="supported-syntax-for-designating-websites-in-a-website-group"></a>Web sitesi grubundaki web sitelerini belirlemeye yönelik desteklenen söz dizimi

Web sitesi gruplarınızdaki etki alanlarını, alt etki alanlarını, web sitelerini ve alt siteleri dahil etmek ve dışlamak için esnek bir söz dizimi kullanabilirsiniz.

- tüm etki alanlarını veya tüm alt etki alanlarını belirtmek için joker karakter olarak kullanın `*`
- yalnızca belirli bir sitenin kapsamını bulmak için URL'nin sonunda sonlandırıcı olarak kullanın `/` .

Sonlandırma `/`olmadan bir URL eklediğinizde, bu URL'nin kapsamı bu site ve tüm alt siteler olarak belirlenmiştir.

Bu söz dizimi tüm http/https web siteleri için geçerlidir.

İşte birkaç örnek:


|Web sitesi grubuna eklediğiniz URL  |URL eşleşecek  | URL eşleşmiyor|
|---------|---------|---------|
|contoso.com  | //<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/ </br> //<!--nourl-->contoso.com/allsubsites1 </br> //<!--nourl-->contoso.com/allsubsites1/allsubsites2|        //<!--nourl-->allsubdomains.contoso.com </br> //<!--nourl-->allsubdomains.contoso.com.au    |
|contoso.com/     |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/         |//<!--nourl-->contoso.com/allsubsites1 </br> //<!--nourl-->contoso.com/allsubsites1/allsubsites2 </br> //<!--nourl-->allsubdomains.contoso.com </br> //<!--nourl-->allsubdomains.contoso.com/au   |
|*.contoso.com   | //<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/allsubsites </br> //<!--nourl-->contoso.com/allsubsites1/allsubsites2 </br> //<!--nourl-->allsubdomains.contoso.com </br> //<!--nourl-->allsubdomains.contoso.com/allsubsites </br> //<!--nourl-->allsubdomains1/allsubdomains2/contoso.com/allsubsites1/allsubsites2         | //<!--nourl-->allsubdomains.contoso.com.au|
|*.contoso.com/xyz     |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/xyz </br> //<!--nourl-->contoso.con/xyz/allsubsites/ </br> //<!--nourl-->allsubdomains.contoso.com/xyz </br> //<!--nourl-->allsubdomains.contoso.com/xyz/allsubsites </br> //<!--nourl-->allsubdomains1.allsubdomains2.contoso.com/xyz/allsubsites </br> //<!--nourl-->allsubdomains1.allsubdomains2.contoso.com/xyz/allsubsites1/allsubsites2         | //<!--nourl-->contoso.com/xyz </br> //<!--nourl-->allsubdomains.contoso.com/xyz/|
|*.contoso.com/xyz/     |//<!--nourl-->contoso.com/xyz </br> //<!--nourl-->allsubdomains.contoso.com/xyz         |//<!--nourl-->contoso.com </br> //<!--nourl-->contoso.com/xyz/allsubsites/ </br> //<!--nourl-->allsubdomains.contoso.com/xyz/allsubsites/ </br> //<!--nourl-->allsubdomains1.allsubdomains2.contoso.com/xyz/allsubsites/ </br> //<!--nourl-->allsubdomains1.allsubdomains2.contoso.com/xyz/allsubsites1/allsubsites2|


### <a name="configure-sensitive-service-domains"></a>Hassas hizmet etki alanlarını yapılandırma

1. Microsoft Purview uyumluluk portalı **Veri kaybı önleme** > **Uç Noktası DLP ayarlarını** >  açın **Hassas verilere** >  yönelik tarayıcı ve etki alanı kısıtlamaları **Hassas hizmet etki alanları**.
1. **Yeni bir hassas hizmet etki alanı grubu ekle'yi** seçin.
1. Grubu adlandırın.
1. İstediğiniz **Eşleşme türünü** seçin. **URL**, **IP adresi**, **IP adresi aralığı** arasından seçim yapabilirsiniz.
1. **Bu gruba yeni hizmet etki alanları ekle** bölümüne uygun değeri yazın. Gruba birden çok web sitesi ekleyebilir ve alt etki alanları için joker karakterler kullanabilirsiniz.  Örneğin, yalnızca en üst düzey web sitesi için www.contoso.com veya corp.contoso.com, hr.contoso.com fin.contoso.com için *.contoso.com
1. **Kaydet**'i seçin.
1. **İlkeler'i** seçin.
1. Yalnızca **Cihazlara** uygulanan bir ilke oluşturun ve kapsamına girin. İlke oluşturma hakkında daha fazla bilgi için bkz. [DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md) .
1. **Kullanıcının Edge'den hassas bir siteye eriştiği** bir kural ve **Kullanıcılar Windows cihazlarında Microsoft Edge tarayıcısında hassas sitelere eriştiğinde etkinlikleri denetle veya kısıtla** eylemini oluşturun.
1. Eylemde **Hassas site grupları ekle veya kaldır'ı** seçin.
1. İstediğiniz **Hassas site gruplarını** seçin.
1. **Ekle**'yi seçin.
1. İzlemek veya kısıtlamak istediğiniz kullanıcı etkinliklerini ve bu etkinliklere yanıt olarak DLP'nizde gerçekleştirdiğiniz eylemleri seçin.
1. Kuralı ve ilkeyi yapılandırmayı tamamlayın ve uygulayın.


## <a name="see-also"></a>Ayrıca bkz.

- [Uç nokta veri kaybı önleme hakkında daha fazla bilgi edinme](endpoint-dlp-learn-about.md)
- [Uç noktada veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md)
- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md)
- [Bir DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md)
- [Etkinlik gezginini kullanmaya başlama](data-classification-activity-explorer.md)
- [Uç Nokta için Microsoft Defender](/windows/security/threat-protection/)
- [Windows 10 ve Windows 11 cihazlarını Microsoft Purview'a eklemeye genel bakış](/microsoft-365/compliance/device-onboarding-overview)
- [Microsoft 365 aboneliği](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory 'ye (AAD) katılmış](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium tabanlı yeni Microsoft Edge'i indirin](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [Varsayılan DLP ilkesini kullanmaya başlama](get-started-with-the-default-dlp-policy.md)
- [Bir şablondan DLP ilkesi oluşturma](create-a-dlp-policy-from-a-template.md)
