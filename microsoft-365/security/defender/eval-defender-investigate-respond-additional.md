---
title: Pilot ortamda olay yanıtı özelliklerini Microsoft 365 Defender deneyin
description: Olayları önceliklendirmek ve yönetmek, araştırmaları otomatikleştirmek ve tehdit algılamada gelişmiş avcılığı kullanmak için Microsoft 365 Defender olay yanıtı özelliklerini deneyin.
keywords: Deneme Microsoft 365 Defender, Microsoft 365 Defender deneyin, Microsoft 365 Defender değerlendirin, değerlendirme laboratuvarı Microsoft 365 Defender Microsoft 365 Defender  pilot, siber güvenlik, gelişmiş kalıcı tehdit, kurumsal güvenlik, cihazlar, cihaz, kimlik, kullanıcılar, veriler, uygulamalar, olaylar, otomatik araştırma ve düzeltme, gelişmiş avcılık
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64e200acf8726a69e6f71784334345e5603b9677
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384546"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Pilot ortamda olay yanıtı özelliklerini Microsoft 365 Defender deneyin

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, pilot ortam kullanarak Microsoft 365 Defender bir olayın araştırılması ve yanıtlanması sürecinde [2. Adımdır](eval-defender-investigate-respond.md). Bu işlem hakkında daha fazla bilgi için [genel bakış](eval-defender-investigate-respond.md) makalesine bakın.

[Simülasyon saldırısı için bir olay yanıtı](eval-defender-investigate-respond-simulate-attack.md) gerçekleştirdikten sonra keşfedebileceğiniz bazı Microsoft 365 Defender özellikleri şunlardır:

|Yeteneği |Açıklama |
|:-------|:-----|
| [Olayların önceliklerini belirleme](#prioritize-incidents) | Bundan sonra hangi olayların ele alındığını belirlemek için olay kuyruğunun filtresini ve sıralamasını kullanın. |
| [Olayları yönetme](#manage-incidents) | Doğru atamayı sağlamak, etiketler ve açıklamalar eklemek ve bir olayı çözmek için olay özelliklerini değiştirin. |
| [Otomatik araştırma ve yanıt](#examine-automated-investigation-and-response-with-the-action-center) | Güvenlik operasyonları ekibinizin tehditleri daha verimli ve etkili bir şekilde ele almasına yardımcı olmak için otomatik araştırma ve yanıt (AIR) özelliklerini kullanın. İşlem merkezi, bekleyen düzeltme eylemlerini onaylama gibi olay ve uyarı görevleri için "tek bir cam bölmesi" deneyimidir. |
| [Gelişmiş avcılık örneği](#use-advanced-hunting) | Ağınızdaki olayları proaktif olarak incelemek ve tehdit göstergelerini ve varlıklarını bulmak için sorguları kullanın. Ayrıca, bir olayın araştırılması ve düzeltilmesi sırasında gelişmiş avcılık kullanırsınız. |


## <a name="prioritize-incidents"></a>Olaylara öncelik belirleyin

**olaylar & uyarıları > Microsoft 365 Defender** <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portalının</a> hızlı başlatılması sırasında olaylar bölümünden olay kuyruğuna ulaşabilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 Defender portalındaki Olaylar & uyarıları bölümü" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::


**En son olaylar ve uyarılar** bölümü, alınan uyarı sayısının ve son 24 saat içinde oluşturulan olayların grafiğini gösterir.

Olayların listesini incelemek ve bunların atama ve araştırma açısından önemini önceliklendirmek için şunları yapabilirsiniz: 

- Olayın veya etkilenen varlıkların farklı özelliklerine görünürlük sağlamak için özelleştirilebilir sütunları yapılandırın ( **Sütunları seç'i** seçin). Bu, analiz için olayların önceliklendirilmesiyle ilgili bilinçli bir karar vermenize yardımcı olur.

- Belirli bir senaryoya veya tehdide odaklanmak için filtrelemeyi kullanın. Olay kuyruğuna filtre uygulamak, hangi olayların hemen ilgilenilmesi gerektiğini belirlemeye yardımcı olabilir. 

Varsayılan olay kuyruğundan **Filtreler'i** seçerek belirli bir olay kümesini belirtebileceğiniz **filtreler** bölmesini görebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Microsoft 365 Defender portalındaki Olaylar & uyarıları bölümünün Filtreler bölmesi" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

Daha fazla bilgi için bkz. [Olayları önceliklendirme](incident-queue.md).

## <a name="manage-incidents"></a>Olayları yönetin

Olayları bir olayın **Olay yönetme** bölmesinden yönetebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Microsoft 365 Defender portalındaki Olaylar & uyarıları bölümünün Olay yönetme bölmesi" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Bu bölmeyi aşağıdaki olay **yönet** bağlantısından görüntüleyebilirsiniz:

- Olay kuyruğundaki bir olayın Özellikler bölmesi.
- Bir olayın **özet** sayfası.

Olaylarınızı yönetmek için kullanabileceğiniz yöntemler şunlardır:

- Olay adını düzenleme

  Güvenlik ekibinizin en iyi yöntemlerine göre otomatik olarak atanan adı değiştirin.
  
- Olay etiketleri ekleme

  Güvenlik ekibinizin olayları sınıflandırmak için kullandığı ve daha sonra filtrelenebilen etiketler ekleyin.
  
- Olayı atama

  Daha sonra filtrelenebilen bir kullanıcı hesabı adına atayın.
  
- Bir olayı çözme

  Düzeltildikten sonra olayı kapatın.
  
- Sınıflandırmasını ve belirlenmesini ayarlama

  Bir olayı çözümlerken tehdit türünü sınıflandırın ve seçin.
  
- Açıklama ekleme

  Güvenlik ekibinizin en iyi yöntemlerini temel alan ilerleme durumu, notlar veya diğer bilgiler için açıklamaları kullanın. Açıklama geçmişinin tamamı, bir olayın ayrıntılar sayfasındaki **Açıklamalar ve geçmiş** seçeneğinden kullanılabilir.

Daha fazla bilgi için bkz. [Olayları yönetme](manage-incidents.md).

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>İşlem merkezi ile otomatik araştırmayı ve yanıtı inceleme

Kuruluşunuz için otomatik araştırma ve yanıt özelliklerinin nasıl yapılandırıldığına bağlı olarak, düzeltme eylemleri otomatik olarak veya yalnızca güvenlik operasyonları ekibinizin onayıyla gerçekleştirilen işlemlerdir. Bekleyen veya tamamlanan tüm eylemler, cihazlarınız, e-posta & işbirliği içeriği ve kimlikleri tek bir konumda bekleyen ve tamamlanan düzeltme eylemlerini listeleyen [İşlem merkezinde](m365d-action-center.md) listelenir.

İşte bir örnek.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender portalındaki Birleşik İşlem merkezi" lightbox="../../media/m3d-action-center-unified.png":::

İşlem merkezinden bekleyen eylemleri seçebilir ve ardından açılır bölmede bunları onaylayabilir veya reddedebilirsiniz. İşte bir örnek.

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Microsoft 365 Defender portalında bir eylemi onaylama veya reddetme seçeneklerinin görüntülendiği bölme" lightbox="../../media/air-actioncenter-itemselected.png":::


Otomatik araştırmalarınızın zamanında devam edebilmesi ve tamamlayabilmesi için bekleyen eylemleri en kısa sürede onaylayın (veya reddedin).

Daha fazla bilgi için bkz [. Otomatik araştırma ve yanıt ve](m365d-autoir.md) [İşlem merkezi](m365d-action-center.md).

## <a name="use-advanced-hunting"></a>Gelişmiş avcılığı kullanma

> [!NOTE]
> Gelişmiş tehdit avcılığı simülasyonunda size yol gösterirken, gelişmiş avlanma kavramlarını anlamak, portalda nerede bulabileceğinizi görmek ve güvenlik operasyonlarınızda size nasıl yardımcı olabileceğini öğrenmek için aşağıdaki videoyu izleyin.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


[İsteğe bağlı dosyasız PowerShell saldırı benzetimi](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) kimlik bilgisi erişim aşamasına ulaşmış gerçek bir saldırıysa, oluşturulan uyarılardan ve etkilenen varlıklardan zaten bildiklerinizi kullanarak ağdaki olayları ve kayıtları proaktif olarak aramak için araştırmanın herhangi bir noktasında gelişmiş avcılığı kullanabilirsiniz. 

Örneğin, [Kullanıcı ve IP adresi keşfi (SMB)](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity) uyarısında yer alan bilgilere dayanarak, tabloyu kullanarak `IdentityDirectoryEvents` tüm SMB oturum numaralandırma olaylarını bulabilir veya tabloyu kullanarak `IdentityQueryEvents` Kimlik için Microsoft Defender verilerdeki diğer çeşitli protokollerde daha fazla bulma etkinliği bulabilirsiniz.


### <a name="hunting-environment-requirements"></a>Avlanma ortamı gereksinimleri

Bu benzetim için tek bir iç posta kutusu ve cihaz gereklidir. Test iletisini göndermek için bir dış e-posta hesabına da ihtiyacınız olacaktır.

1. Kiracınızın [Microsoft 365 Defender etkinleştirdiğini](m365d-enable.md#confirm-that-the-service-is-on) doğrulayın.
2. E-posta almak için kullanılacak hedef posta kutusunu belirleyin.

   - Bu posta kutusu Office 365 için Microsoft Defender tarafından izlenmelidir

   - Gereksinim 3'ten gelen cihazın bu posta kutusuna erişmesi gerekiyor

3. Test cihazını yapılandırma:

    a. Windows 10 sürüm 1903 veya sonraki bir sürümü kullandığınızdan emin olun.

    b. Test cihazını test etki alanına ekleyin.

    c. [Microsoft Defender Virüsten Koruma'nı açın](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Microsoft Defender Virüsten Koruma'yı etkinleştirme konusunda sorun yaşıyorsanız [bu sorun giderme konusuna bakın](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

    d. [Uç Nokta için Microsoft Defender'a ekleme](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Simülasyonu çalıştırma

1. Dış e-posta hesabından, tehdit avcılığı ortamı gereksinimleri bölümünün 2. adımında tanımlanan posta kutusuna bir e-posta gönderin. Mevcut e-posta filtresi ilkeleri aracılığıyla izin verilecek bir ek ekleyin. Bu dosyanın kötü amaçlı veya yürütülebilir olması gerekmez. Önerilen dosya türleri <i>.pdf</i>, <i>.exe</i> (izin veriliyorsa) veya Word dosyası gibi bir Office belge türüdür.

2. Tehdit avcılığı ortamı gereksinimleri bölümünün 3. adımında tanımlandığı şekilde yapılandırılan cihazdan gönderilen e-postayı açın. Eki açın veya dosyayı cihaza kaydedin.

#### <a name="go-hunting"></a>Avlanmaya git

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalını</a> açın.

2. Gezinti **bölmesinden Tehdit Avcılığı > Gelişmiş avcılık'ı** seçin.

3. E-posta olaylarını toplayarak başlayan bir sorgu oluşturun.

   1. **Sorgu > Yeni'yi** seçin.

   1. **Gelişmiş avcılık** altındaki **Email** gruplarında **EmailEvents'e** çift tıklayın. Bunu sorgu penceresinde görmeniz gerekir.

      ```console
      EmailEvents
      ```

   1. Sorgunun zaman çerçevesini son 24 saat olarak değiştirin. Yukarıdaki simülasyonu çalıştırdığınızda gönderdiğiniz e-postanın son 24 saat içinde olduğunu varsayarsak, aksi takdirde zaman dilimini gerektiği gibi değiştirin.

   1. **Sorguyu çalıştır'ı** seçin. Pilot ortamınıza bağlı olarak farklı sonuçlar elde edebilirsiniz.

      > [!NOTE]
      > Veri dönüşünü sınırlamak için filtreleme seçenekleri için sonraki adıma bakın.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-1.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Avcılık sayfası" lightbox="../../media/advanced-hunting-incident-response-try-1.png":::

        > [!NOTE]
        > Gelişmiş tehdit avcılığı sorgu sonuçlarını tablo verileri olarak görüntüler. Ayrıca, verileri grafikler gibi diğer biçim türlerinde de görüntülemeyi tercih edebilirsiniz.

   1. Sonuçlara bakın ve açtığınız e-postayı tanımlayıp tanımlayabildiğinize bakın. İletinin gelişmiş avcılıkta görünmesi iki saat kadar sürebilir. Sonuçları daraltmak için sorgunuza **where** koşulunu ekleyerek yalnızca SenderMailFromDomain olarak "yahoo.com" olan e-postaları arayabilirsiniz. İşte bir örnek.

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Kaydı inceleyebilmeniz için sorgudan elde edilen satırlara tıklayın.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-2.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Avcılık sayfasının Kaydı incele bölümü" lightbox="../../media/advanced-hunting-incident-response-try-2.png":::

4. Artık e-postayı görebildiğinizi doğruladığınıza göre ekler için bir filtre ekleyin. Ortamda ekleri olan tüm e-postalara odaklanın. Bu simülasyon için, ortamınızdan gönderilen e-postalara değil, gelen e-postalara odaklanın. İletinizi bulmak için eklediğiniz filtreleri kaldırın ve "| burada **AttachmentCount > 0** ve **EmailDirection** == **"Gelen""**

   Aşağıdaki sorgu, tüm e-posta olayları için ilk sorgunuzdan daha kısa bir liste içeren sonucu gösterir:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Ardından, sonuç kümenize ek hakkındaki bilgileri (örneğin: dosya adı, karmalar) ekleyin. Bunu yapmak için **EmailAttachmentInfo** tablosuna katılın. Bu örnekte, birleştirme için kullanılacak ortak alanlar **NetworkMessageId** ve **RecipientObjectId'dir**.

   Aşağıdaki sorgu ayrıca ek bir "| satırı içerir **project-rename EmailTimestamp=Timestamp**", bir sonraki adımda ekleyeceğiniz dosya eylemleriyle ilgili zaman damgaları yerine e-postayla hangi zaman damgasının ilişkili olduğunu belirlemenize yardımcı olur.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Ardından, **e-postaAttachmentInfo** tablosundaki **SHA256** değerini kullanarak bu karma için **DeviceFileEvents'i** (uç noktada gerçekleşen dosya eylemleri) bulun. Buradaki ortak alan ekin SHA256 karması olacaktır.

   Sonuçta elde edilen tablo artık uç noktadan (Uç Nokta için Microsoft Defender) cihaz adı, hangi eylemin yapıldığı (bu durumda yalnızca DosyaOluşturan olayları içerecek şekilde filtrelenmiş) ve dosyanın depolandığı yer gibi ayrıntıları içerir. İşlemle ilişkili hesap adı da eklenir.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Şimdi kullanıcının eki açtığı veya kaydettiği tüm gelen e-postaları tanımlayan bir sorgu oluşturdunuz. Ayrıca bu sorguyu belirli gönderen etki alanları, dosya boyutları, dosya türleri vb. için filtrelemek üzere daraltabilirsiniz.

7. İşlevler, bir dosya hakkında yaygınlığı, imzalayan ve veren bilgileri gibi daha fazla TI verisi çekmenizi sağlayan özel bir birleştirme türüdür. Dosya hakkında daha fazla ayrıntı almak için **FileProfile()** işlevi zenginleştirmesini kullanın:

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Algılama oluşturma

Gelecekte olup olmadığı konusunda **uyarı almak** istediğiniz bilgileri tanımlayan bir sorgu oluşturduktan sonra, sorgudan özel bir algılama oluşturabilirsiniz.

Özel algılamalar, ayarladığınız sıklığa göre sorguyu çalıştırır ve sorguların sonuçları, seçtiğiniz etkilenen varlıklara göre güvenlik uyarıları oluşturur. Bu uyarılar olaylarla ilişkilendirilecek ve ürünlerden biri tarafından oluşturulan diğer güvenlik uyarıları olarak önceliklendirilebilir.

1. Sorgu sayfasında, Go tehdit avcılığı yönergelerinin 7. adımına eklenen 7. ve 8. satırları kaldırın ve **Algılama kuralı oluştur'a** tıklayın.

   :::image type="content" source="../../media/advanced-hunting-incident-response-try-3.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Tehdit Avcılığı sayfasının Sorgu düzenleme bölümü" lightbox="../../media/advanced-hunting-incident-response-try-3.png":::

   > [!NOTE]
   > **Algılama kuralı oluştur'a** tıklarsanız ve sorgunuzda söz dizimi hataları varsa, algılama kuralınız kaydedilmez. Hata olmadığından emin olmak için sorgunuzu bir kez daha denetleyin.

2. Güvenlik ekibinin uyarıyı, neden oluşturulduğunu ve hangi eylemleri gerçekleştirmesini beklediğinizi anlamasını sağlayacak bilgilerle gerekli alanları doldurun.

   :::image type="content" source="../../media/mtp/fig23.png" alt-text="Microsoft 365 Defender portalındaki Uyarı ayrıntıları sayfası" lightbox="../../media/mtp/fig23.png":::

   Bir sonraki kullanıcıya bu algılama kuralı uyarısı hakkında bilinçli bir karar vermeye yardımcı olmak için alanları net bir şekilde doldurduğunuzdan emin olun

3. Bu uyarıda hangi varlıkların etkilendiğini seçin. Bu durumda **Cihaz** ve **Posta Kutusu'ni** seçin.

   :::image type="content" source="../../media/mtp/fig24.png" alt-text="Microsoft 365 Defender portalındaki Etkilenen varlıklar ayrıntıları sayfası" lightbox="../../media/mtp/fig24.png":::

4. Uyarı tetiklendiğinde gerçekleştirilecek eylemleri belirleyin. Bu durumda, başka eylemler gerçekleştirilebilse de bir virüsten koruma taraması çalıştırın.

   :::image type="content" source="../../media/mtp/fig25.png" alt-text="Microsoft 365 Defender portalındaki Eylemler sayfası" lightbox="../../media/mtp/fig25.png":::

5. Uyarı kuralının kapsamını seçin. Bu sorgu cihazları içerdiğinden, cihaz grupları Uç Nokta için Microsoft Defender bağlama göre bu özel algılamayla ilgilidir. Etkilenen varlıklar olarak cihaz içermeyen bir özel algılama oluştururken kapsam uygulanmaz.

   :::image type="content" source="../../media/mtp/fig26.png" alt-text="Microsoft 365 Defender portalındaki Kapsam sayfası" lightbox="../../media/mtp/fig26.png":::


   Bu pilot için, bu kuralı üretim ortamınızdaki test cihazlarının bir alt kümesiyle sınırlamak isteyebilirsiniz.

6. **Oluştur**’u seçin. Ardından gezinti **panelinden Özel algılama kuralları'nı** seçin.

   :::image type="content" source="../../media/mtp/fig27a.png" alt-text="Microsoft 365 Defender portalında Özel algılama kuralları kuralları seçeneği" lightbox="../../media/mtp/fig27a.png":::

   :::image type="content" source="../../media/mtp/fig27b.png" alt-text="Microsoft 365 Defender portalında algılama kurallarını ve yürütme ayrıntılarını gösteren sayfa" lightbox="../../media/mtp/fig27b.png":::

   Bu sayfadan, ayrıntılar sayfasını açacak algılama kuralını seçebilirsiniz.

   :::image type="content" source="../../media/mtp/fig28.png" alt-text="Microsoft 365 Defender portalında tetiklenen uyarıların ayrıntılarını gösteren sayfa" lightbox="../../media/mtp/fig28.png":::


### <a name="expert-training-on-advanced-hunting"></a>Gelişmiş avcılık konusunda uzman eğitimi

**Saldırganı izlemek** , yeni güvenlik analistleri ve deneyimli tehdit avcıları için bir web yayını serisidir. Gelişmiş avcılık ile ilgili temel bilgileri kullanarak kendi gelişmiş sorgularınızı oluşturma konusunda size yol gösterir. 

Başlamak için bkz. [Gelişmiş avcılık konusunda uzman eğitimi alma](advanced-hunting-expert-training.md) .

### <a name="navigation-you-may-need"></a>İhtiyaç duyabileceğiniz gezinti

[Microsoft 365 Defender Değerlendirme Ortamı Oluşturma](eval-create-eval-environment.md)
