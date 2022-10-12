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
- tier1
- highpri
- purview-compliance
- SPO_Content
search.appverid:
- MET150
description: Uç nokta veri kaybı önleme konumlarını kullanmak için veri kaybı önleme (DLP) ilkelerini yapılandırmayı öğrenin.
ms.openlocfilehash: f8e74219a796b46f681caceefdb532e1678f0a74
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537016"
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


[!INCLUDE [purview-preview](../includes/purview-preview.md)]

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

## <a name="before-you-begin-scenario-4"></a>Senaryo 4'e başlamadan önce

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

Endpoint DLP ve Microsoft Edge Web tarayıcısı ile hassas öğelerin yanlışlıkla paylaşılmalarını izin verilmeyen bulut uygulamaları ve hizmetleriyle kısıtlayabilirsiniz. Edge, bir öğenin Bir Uç Nokta DLP ilkesi tarafından ne zaman kısıtlandığını anlar ve erişim kısıtlamalarını zorlar.

Düzgün yapılandırılmış bir DLP ilkesinde konum olarak **Cihazlar'ı** seçip Microsoft Edge tarayıcısını kullandığınızda, bu ayarlarda tanımladığınız izin verilmeyen tarayıcıların DLP ilke denetimlerinizle eşleşen hassas öğelere erişmesi engellenir. Bunun yerine kullanıcılar, DLP tarafından uygulanan kısıtlamaları anlayarak DLP ilkesindeki koşullar karşılandığında etkinlikleri engelleyebilecek veya kısıtlayan Microsoft Edge'i kullanmaya yönlendirilecektir.

Bu kısıtlamayı kullanmak için üç önemli parça yapılandırmanız gerekir:

1. Hassas öğelerin paylaşılmasını önlemek istediğiniz yerleri (hizmetler, etki alanları, IP adresleri) belirtin.

2. DLP ilkesi eşleşmesi gerçekleştiğinde belirli hassas öğelere erişmesine izin verilmeyen tarayıcıları ekleyin.

3. **Bulut hizmetlerine yükle** ve **İzin verilmeyen tarayıcıdan erişim'i** açarak karşıya yüklemenin bu konumlara kısıtlanması gereken hassas öğe türlerini tanımlamak için DLP ilkelerini yapılandırın.

İş gereksinimlerinizi karşılamak ve hassas verileri korumak için kısıtlamalarınızı genişletmek ve genişletmek için yeni hizmetler, uygulamalar ve ilkeler eklemeye devam edebilirsiniz. 

Bu yapılandırma, verilerinizin güvende kalmasını sağlarken kullanıcıların hassas olmayan öğelere erişmesini ve bunları paylaşmasını engelleyen veya kısıtlayan gereksiz kısıtlamaları da önler.

## <a name="scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains"></a>Senaryo 6 Hassas hizmet etki alanlarında kullanıcı etkinliklerini izleme veya kısıtlama

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
1. **Bu gruba yeni hizmet etki alanları ekle** bölümüne uygun değeri yazın. Gruba birden çok web sitesi ekleyebilir ve alt etki alanları için joker karakterler kullanabilirsiniz.  Örneğin, `www.contoso.com` yalnızca en üst düzey web sitesi için veya \*corp.contoso.com, hr.contoso.com fin.contoso.com için .contoso.com
1. **Kaydet**'i seçin.
1. **İlkeler'i** seçin.
1. Yalnızca **Cihazlara** uygulanan bir ilke oluşturun ve kapsamına girin. İlke oluşturma hakkında daha fazla bilgi için bkz. [DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md) .
1. **Kullanıcının Edge'den hassas bir siteye eriştiği** ve **Cihazlarda etkinlikleri denetle veya kısıtla** eylemini kullanan bir kural oluşturun.
1. **Hizmet etki alanı ve tarayıcı etkinlikleri** bölümünde **Kısıtlı bir bulut hizmeti etki alanına yükle'yi veya izin verilmeyen bir tarayıcıdan erişim'i** seçin ve eylemi **Yalnızca denetle** olarak ayarlayın. Bu, tüm site grupları için genel eylemi ayarlar.
1. İstediğiniz **Hassas site gruplarını** seçin.
1. **Ekle**'yi seçin.
1. İsteğE BAĞLI: Bir veya daha fazla site grubu için genel eyleme bir özel durum (genellikle izin verilenler listesi) oluşturmak istiyorsanız **, Hassas hizmet etki alanı özel durumlarını yapılandır'ı** seçin, özel durumun olmasını istediğiniz site grubunu ekleyin, istenen eylemi yapılandırın ve Yapılandırmayı **kaydedin** .
1. İzlemek veya kısıtlamak istediğiniz kullanıcı etkinliklerini ve bu etkinliklere yanıt olarak DLP'nizde gerçekleştirdiğiniz eylemleri seçin.
1. Kuralı ve ilkeyi yapılandırmayı tamamlayın ve uygulayın.

## <a name="scenario-7-authorization-groups-preview"></a>Senaryo 7 Yetkilendirme grupları (önizleme)

> [!IMPORTANT]
> **Yazıcı gruplarını**, **Çıkarılabilir depolama cihaz gruplarını**, **Ağ paylaşım gruplarını** ve **Ağ özel durumlarını/VPN'yi** kullanabilmeniz için [buraya](https://forms.office.com/r/GNVTFvxuZv) kaydolmanız gerekir.

Bu senaryolar, etkinlik gezginine eklenen ve raporlayan cihazlarınız olmasını gerektirir. Henüz cihaz eklemediyseniz bkz [. Uç nokta veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md).

Yetkilendirme grupları çoğunlukla izin listeleri olarak kullanılır. Gruba genel ilke eylemlerinden farklı ilke eylemleri atamıştınız. Bu senaryoda, bir yazıcı grubu tanımlamayı ve ardından gruptaki yazıcılar dışında tüm yazdırma etkinlikleri için engelleme eylemleriyle bir ilke yapılandırmayı inceleyeceğiz. Bu yordamlar, **Kaldırılabilir depolama cihazı grupları** ve **Ağ paylaşımı grupları** için temelde aynıdır.

Bu senaryoda, hukuk departmanının sözleşmeleri yazdırmak için kullandığı bir yazıcı grubu tanımlayacağız. Sözleşmeleri diğer yazıcılara yazdırma engellenir.

### <a name="create-and-use-printer-groups"></a>Yazıcı grupları oluşturma ve kullanma

1. Microsoft Purview uyumluluk portalı **Veri kaybı önleme** > **Uç Noktası DLP ayarları** > **Yazıcı grupları'nı** açın.
1. **Yazıcı grubu oluştur'u** seçin ve gruba bir ad verin. Bu senaryoda kullanacağız `Legal printers`.
1. **Yazıcı ekle'yi** seçin ve bir ad belirtin. Yazıcıları şu şekilde tanımlayabilirsiniz:
    1. Kolay yazıcı adı 
    1. USB ürün kimliği
    1. USB satıcı kimliği
    1. IP aralığı
    1. Dosyaya yazdır
    1. Yazıcıda dağıtılan evrensel yazdırma
    1. Şirket yazıcısı
    1. Yerel ortama yazdır
1. **Kapat**'ı seçin.

### <a name="configure-policy-printing-actions"></a>İlke yazdırma eylemlerini yapılandırma

1. **İlkeler** sekmesini açın.

1. **İlke oluştur'u** seçin ve özel ilke şablonunu seçin.
1. Konumun kapsamını yalnızca **Cihazlar olarak belirleyin**.

1. Şu durumlarda bir kural oluşturun:
    1. **İçerik içeriği** =  **Eğitilebilir sınıflandırıcılar**, **Hukuk İşleri**
    1. **Eylem** =  **Cihazlarda etkinlikleri denetleme veya kısıtlama**
    1. Ardından **tüm uygulamalarda Dosya etkinlikleri'ne** tıklayın
    1. **Belirli bir etkinliğe kısıtlama uygula'yı** seçin
    1. **Yazdırma Bloğu'nu** =  seçin
1. **Farklı yazdırma kısıtlamaları seçin'i** seçin
1. **Yazıcı grubu kısıtlamaları'nın** altında **Grup ekle'yi** ve **yasal yazıcılar'ı** seçin.
1. **Eyleme** = **İzin Ver'i** ayarlayın.
    > [!TIP]
    > **İzin Ver** eylemi denetim günlüğüne kayıt ve denetim olayı kaydeder, ancak uyarı veya bildirim oluşturmaz. 
10. Kaydetmek.
11. **İlk değeri test etmek istediğim** varsayılan değeri kabul edin ve **Test modundayken ilke ipuçlarını göster'i** seçin. **İleri**'yi seçin.

12. Ayarlarınızı gözden geçirin ve **Gönder'i** seçin.

13. Yeni DLP ilkesi, ilke listesinde görünür.

## <a name="scenario-8-network-exceptions-preview"></a>Senaryo 8 Ağ özel durumları (önizleme)

> [!IMPORTANT]
> **Yazıcı gruplarını**, **Çıkarılabilir depolama cihaz gruplarını**, **Ağ paylaşım gruplarını** ve **Ağ özel durumlarını/VPN'yi** kullanabilmeniz için [buraya](https://forms.office.com/r/GNVTFvxuZv) kaydolmanız gerekir.

Bu senaryolar, etkinlik gezginine eklenen ve raporlayan cihazlarınız olmasını gerektirir. Henüz cihaz eklemediyseniz bkz [. Uç nokta veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md).

Bu senaryoda, karma çalışanların kuruluş kaynaklarına erişmek için kullandığı VPN'lerin listesini tanımlayacağız.

### <a name="create-and-use-a-network-exception"></a>Ağ özel durumu oluşturma ve kullanma

Ağ özel durumları, kullanıcıların dosyaya eriştiği ağı temel alarak dosya etkinliklerinde İzin Ver, Yalnızca Denetle, Geçersiz kılma ile engelle ve Engelle eylemlerini yapılandırmanıza olanak tanır. Tanımladığınız [VPN ayarları](dlp-configure-endpoint-settings.md#vpn-settings-preview) listesinden ve **Kurumsal ağ** seçeneğinden seçim yapabilirsiniz. Eylemler, bu kullanıcı etkinliklerine tek tek veya toplu olarak uygulanabilir:

- Panoya kopyala
- USB çıkarılabilir cihaza kopyalama
- Ağ paylaşımına kopyalama
- Yazdırma
- İzin verilmeyen Bluetooth uygulamasını kullanarak kopyalama veya taşıma
- RDP kullanarak kopyalama veya taşıma

#### <a name="get-the-server-address-or-network-address"></a>Sunucu adresini veya Ağ adresini alma

1. DLP tarafından izlenen bir Windows cihazında yönetici olarak **bir Windows PowerShell** penceresi açın.
1. Bu cmdlet'i çalıştırın

```powershell-interactive
Get-VpnConnection
```

3. Bu cmdlet'i çalıştırmak birden çok alan ve değer döndürür.
1. **ServerAddress** alanını bulun ve bu değeri kaydedin. VPN listesinde bir VPN girişi oluşturduğunuzda bunu kullanacaksınız.
1. **Ad** alanını bulun ve bu değeri kaydedin. **AD** alanı, VPN listesinde bir VPN girişi oluşturduğunuzda **Ağ adresi** alanına eşler.

#### <a name="add-a-vpn"></a>VPN ekleme

1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) >  **Veri kaybı önleme** > **Uç Noktası DLP ayarları****VPN ayarlarını** >  açın.
1. **VPN adresleri ekle veya düzenle'yi** seçin.
1. Get-VpnConnection'ı çalıştırmak için **Sunucu adresini** veya **Ağ adresini** belirtin.
1. **Kaydet**'i seçin.
1. Öğeyi kapatın.

#### <a name="configure-policy-actions"></a>İlke eylemlerini yapılandırma

1. **İlkeler** sekmesini açın.

1. **İlke oluştur'u** seçin ve özel ilke şablonunu seçin.
1. Konumun kapsamını yalnızca **Cihazlar olarak belirleyin**.

1. Şu durumlarda bir kural oluşturun:
    1. **İçerik içeriği** =  **Eğitilebilir sınıflandırıcılar**, **Hukuk İşleri**
    1. **Eylem** =  **Cihazlarda etkinlikleri denetleme veya kısıtlama**
    1. Ardından **tüm uygulamalarda Dosya etkinlikleri'ne** tıklayın
    1. **Belirli bir etkinliğe kısıtlama uygula'yı** seçin
    1. **Ağ özel durumlarını** yapılandırmak istediğiniz eylemleri seçin.
1. **Panoya kopyala'yı** ve **Yalnızca denetle** eylemini seçin
1. **Panoya farklı kopya kısıtlamalarını seçin'i** seçin.
1. **VPN'i** seçin ve eylemi **Geçersiz kılma ile engelle** olarak ayarlayın.

> [!IMPORTANT]
> Bir kullanıcının VPN üzerinden bağlandıkları etkinlikleri denetlemek istediğinizde VPN'yi seçmeniz ve VPN'yi **Ağ özel durumları** yapılandırmasında en yüksek öncelik haline *getirmeniz gerekir*. Aksi takdirde, **Kurumsal ağ** seçeneği belirlenirse, **Kurumsal ağ** girişi için tanımlanan eylem zorlanır.

> [!CAUTION]
> **Tüm etkinliklere uygula** seçeneği, burada tanımlanan ağ özel durumlarını kopyalar ve yazdır ve **ağ paylaşımına kopyala** **gibi** yapılandırılan diğer tüm belirli etkinliklere uygular. **_Bu, diğer etkinliklerdeki ağ özel durumlarının üzerine yazar Son kaydedilen yapılandırma kazanır._**  

8. Kaydetmek.
1. **İlk değeri test etmek istediğim** varsayılan değeri kabul edin ve **Test modundayken ilke ipuçlarını göster'i** seçin. **İleri**'yi seçin.

1. Ayarlarınızı gözden geçirin ve **Gönder'i** seçin.

1. Yeni DLP ilkesi, ilke listesinde görünür.
 
 
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
