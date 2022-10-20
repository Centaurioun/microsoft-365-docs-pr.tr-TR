---
title: Microsoft 365 Defender'da özel algılama kuralları oluşturma ve yönetme
description: Gelişmiş tehdit avcılığı sorgularını temel alan özel algılama kuralları oluşturmayı ve yönetmeyi öğrenin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgulama, telemetri, özel algılamalar, kurallar, şema, kusto, RBAC, izinler, Uç Nokta için Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-m365-defender
- tier2
ms.topic: conceptual
ms.openlocfilehash: 3a02055f13fae9f944eaf66e0addd6db55137f1d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639477"
---
# <a name="create-and-manage-custom-detections-rules"></a>Özel algılama kuralları oluşturma ve yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender

Özel algılama kuralları, [gelişmiş tehdit avcılığı](advanced-hunting-overview.md) sorgularını kullanarak tasarlayabileceğiniz ve ayarlayabileceğiniz kurallardır. Bu kurallar, şüpheli ihlal etkinliği ve yanlış yapılandırılmış uç noktalar dahil olmak üzere çeşitli olayları ve sistem durumlarını proaktif olarak izlemenize olanak sağlar. Bunları düzenli aralıklarla çalışacak şekilde ayarlayabilir, uyarılar oluşturabilir ve her eşleşme olduğunda yanıt eylemleri gerçekleştirebilirsiniz.

## <a name="required-permissions-for-managing-custom-detections"></a>Özel algılamaları yönetmek için gerekli izinler

Özel algılamaları yönetmek için şu rollerden birine atanmış olmanız gerekir:

- **Güvenlik yöneticisi**: Bu [Azure Active Directory rolüne](/azure/active-directory/roles/permissions-reference#security-administrator) sahip kullanıcılar Microsoft 365 Defender portalında ve diğer portallarda ve hizmetlerde güvenlik ayarlarını yönetebilir.

- **Güvenlik operatörü**: Bu [Azure Active Directory rolüne](/azure/active-directory/roles/permissions-reference#security-operator) sahip kullanıcılar uyarıları yönetebilir ve Microsoft 365 Defender portalındaki tüm bilgiler de dahil olmak üzere güvenlikle ilgili özelliklere genel salt okunur erişime sahip olabilir. Bu rol, yalnızca rol tabanlı erişim denetimi (RBAC) Uç Nokta için Microsoft Defender kapalı olduğunda özel algılamaları yönetmek için yeterlidir. RBAC'yi yapılandırdıysanız, Uç Nokta için Defender **için güvenlik ayarlarını yönetme** iznine de ihtiyacınız vardır.

Ayrıca, belirli Microsoft 365 Defender çözümlerinden gelen verilere uygulanan özel algılamaları, bunlar için izinleriniz varsa yönetebilirsiniz. Örneğin, yalnızca Office için Microsoft 365 Defender için yönetme izinleriniz varsa tabloları kullanarak `Email` özel algılamalar oluşturabilirsiniz, tabloları değil`Identity`.  

Gerekli izinleri yönetmek için genel **yönetici** şunları yapabilir:

- Güvenlik **yöneticisi** veya **güvenlik operatörü** rolünü **Roller** > **Güvenlik yöneticisi** altındaki [Microsoft 365 yönetim merkezi](https://admin.microsoft.com/) atayın.
- **Microsoft 365 Defender'da Ayarlar** > **İzin rolleri** >  altındaki [Uç Nokta için Microsoft Defender](https://security.microsoft.com/) için RBAC ayarlarını **denetleyin.** **Güvenlik ayarlarını yönetme** iznini atamak için ilgili rolü seçin.

> [!NOTE]
> Özel algılamaları yönetmek için, RBAC açıksa **güvenlik operatörlerinin** **Uç Nokta için Microsoft Defender'de güvenlik ayarlarını yönetme** iznine sahip olması gerekir.

## <a name="create-a-custom-detection-rule"></a>Özel algılama kuralı oluşturma
### <a name="1-prepare-the-query"></a>1. Sorguyu hazırlayın.

Microsoft 365 Defender portalında **Gelişmiş tehdit avcılığı'na** gidin ve var olan bir sorguyu seçin veya yeni bir sorgu oluşturun. Yeni bir sorgu kullanırken, hataları belirlemek ve olası sonuçları anlamak için sorguyu çalıştırın.

>[!IMPORTANT]
>Hizmetin çok fazla uyarı döndürmesini önlemek için, her kural her çalıştırıldığında yalnızca 100 uyarı oluşturmakla sınırlıdır. Kural oluşturmadan önce, normal, günlük etkinlik uyarılarını önlemek için sorgunuzda ayarlamalar yapın.


#### <a name="required-columns-in-the-query-results"></a>Sorgu sonuçlarında gerekli sütunlar
Özel algılama kuralı oluşturmak için sorgu aşağıdaki sütunları döndürmelidir:

- `Timestamp`—oluşturulan uyarıların zaman damgasını ayarlamak için kullanılır
- `ReportId`—özgün kayıtlar için aramaları etkinleştirir
- Belirli cihazları, kullanıcıları veya posta kutularını tanımlayan aşağıdaki sütunlardan biri:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (zarf gönderen veya Return-Path adresi)
    - `SenderMailFromAddress` (e-posta istemcisi tarafından görüntülenen gönderen adresi)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>[Gelişmiş tehdit avcılığı şemasına](advanced-hunting-schema-tables.md) yeni tablolar eklendikçe ek varlıklar için destek eklenecektir.

Sonuçları özelleştirmek veya toplamak için veya `summarize` işlecini kullanmayanlar `project` gibi basit sorgular genellikle bu ortak sütunları döndürür.

Daha karmaşık sorguların bu sütunları döndürmesini sağlamanın çeşitli yolları vardır. Örneğin, gibi `DeviceId`bir sütun altında varlığa göre toplamayı ve sayma işlemini tercih ederseniz, yine de `Timestamp` döndürebilir ve `ReportId` her benzersiz `DeviceId`içeren en son olaydan alabilirsiniz.


> [!IMPORTANT]
> Sütunu kullanarak özel algılamaları filtrelemekten `Timestamp` kaçının. Özel algılamalar için kullanılan veriler algılama sıklığına göre önceden filtrelenmiştir.


Aşağıdaki örnek sorgu, virüsten koruma algılamaları olan benzersiz cihazların (`DeviceId`) sayısını sayar ve yalnızca beşten fazla algılaması olan cihazları bulmak için bu sayıyı kullanır. En son `Timestamp` ve karşılık gelen `ReportId`değerini döndürmek için işleviyle birlikte işlecini `arg_max` kullanır`summarize`.

```kusto
DeviceEvents
| where ingestion_time() > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Daha iyi sorgu performansı için, kural için hedeflenen çalışma sıklığınızla eşleşen bir zaman filtresi ayarlayın. En az sık çalıştırılan _her 24 saatte_ bir olduğundan, son güne yönelik filtreleme tüm yeni verileri kapsar.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Yeni kural oluşturun ve uyarı ayrıntılarını sağlayın.

Sorguyu sorgu düzenleyicisinde kullanarak **Algılama kuralı oluştur'u** seçin ve aşağıdaki uyarı ayrıntılarını belirtin:

- **Algılama adı**—algılama kuralının adı; benzersiz olmalıdır
- **Sıklık**— sorguyu çalıştırma ve eylem gerçekleştirme aralığı. [Aşağıdaki ek yönergelere bakın](#rule-frequency)
- **Uyarı başlığı**— kural tarafından tetiklenen uyarılarla görüntülenen başlık; benzersiz olmalıdır
- **Önem derecesi**— kural tarafından tanımlanan bileşenin veya etkinliğin olası riski
- **Kategori**— kural tarafından tanımlanan tehdit bileşeni veya etkinliği
- **MITRE ATT&CK teknikleri**: [MITRE ATT&CK çerçevesinde](https://attack.mitre.org/) belgelendiği gibi kural tarafından tanımlanan bir veya daha fazla saldırı tekniği. Bu bölüm kötü amaçlı yazılım, fidye yazılımı, şüpheli etkinlik ve istenmeyen yazılımlar dahil olmak üzere belirli uyarı kategorileri için gizlenir
- **Açıklama**— kural tarafından tanımlanan bileşen veya etkinlik hakkında daha fazla bilgi 
- **Önerilen eylemler**: Yanıtlayanların uyarıya yanıt olarak gerçekleştirebileceği ek eylemler

#### <a name="rule-frequency"></a>Kural sıklığı
Yeni bir kural kaydettiğinizde çalıştırılır ve son 30 günlük verilerin eşleşmelerini denetler. Kural daha sonra sabit aralıklarla yeniden çalıştırılır ve seçtiğiniz sıklık temelinde bir geri arama süresi uygular:

- **Her 24 saatte** bir— 24 saatte bir çalışır ve son 30 güne ait verileri denetler
- **Her 12 saatte** bir— 12 saatte bir çalışır ve son 48 saatteki verileri denetler
- **Her 3 saatte** bir— 3 saatte bir çalışır ve son 12 saatteki verileri denetler
- **Saatte bir**—son 4 saatteki verileri denetleerek saatlik olarak çalışır

Bir kuralı düzenlediğinizde, bir sonraki çalışma zamanında uygulanan değişiklikler ayarladığınız sıklık değerine göre zamanlanmış olarak çalıştırılır. Kural sıklığı, alım süresini değil olay zaman damgasını temel alır.



>[!TIP]
> Sorgunuzdaki zaman filtrelerini geri arama süresiyle eşleştirin. Geri arama süresinin dışındaki sonuçlar yoksayılır.  

Algılamaları ne kadar yakından izlemek istediğinizi gösteren sıklığı seçin. Kuruluşunuzun uyarılara yanıt verme kapasitesini göz önünde bulundurun.

### <a name="3-choose-the-impacted-entities"></a>3. Etkilenen varlıkları seçin.
Sorgu sonuçlarınızda, etkilenen veya etkilenen ana varlığı bulmayı beklediğiniz sütunları belirleyin. Örneğin, bir sorgu gönderen (`SenderFromAddress` veya `SenderMailFromAddress`) ve alıcı (`RecipientEmailAddress`) adresleri döndürebilir. Bu sütunlardan hangisinin ana etkilenen varlığı temsil ettiği belirlenerek hizmet ilgili uyarıları toplamaya, olayları ilişkilendirmeye ve hedef yanıt eylemlerini toplamaya yardımcı olur.

Her varlık türü (posta kutusu, kullanıcı veya cihaz) için yalnızca bir sütun seçebilirsiniz. Sorgunuz tarafından döndürülmeyen sütunlar seçilemiyor.

### <a name="4-specify-actions"></a>4. Eylemleri belirtin.
Özel algılama kuralınız, sorgu tarafından döndürülen cihazlarda, dosyalarda veya kullanıcılarda otomatik olarak eylemler gerçekleştirebilir.

#### <a name="actions-on-devices"></a>Cihazlardaki eylemler
Bu eylemler, sorgu sonuçlarının sütunundaki `DeviceId` cihazlara uygulanır:
- **Cihazı yalıtma**— tam ağ yalıtımı uygulamak için Uç Nokta için Microsoft Defender kullanır ve cihazın herhangi bir uygulama veya hizmete bağlanmasını önler. [Makine yalıtımı Uç Nokta için Microsoft Defender hakkında daha fazla bilgi edinin](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Araştırma paketi toplama**— ZIP dosyasındaki cihaz bilgilerini toplar. [Uç Nokta için Microsoft Defender araştırma paketi hakkında daha fazla bilgi edinin](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Virüsten koruma taraması çalıştırma**—cihazda tam Microsoft Defender Virüsten Koruma taraması gerçekleştirir
- **Araştırma başlatma**—cihazda [otomatik bir araştırma](m365d-autoir.md) başlatır
- **Uygulama yürütmeyi kısıtlayın**; cihazdaki kısıtlamaları yalnızca Microsoft tarafından verilen bir sertifikayla imzalanan dosyaların çalışmasına izin verecek şekilde ayarlar. [Uç Nokta için Microsoft Defender ile uygulama kısıtlamaları hakkında daha fazla bilgi edinin](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Dosyalardaki eylemler
Seçildiğinde, sorgu sonuçlarının , , `InitiatingProcessSHA1``SHA256`veya `InitiatingProcessSHA256` sütunundaki `SHA1`dosyalara **Dosya karantinaya** al eylemini uygulamayı seçebilirsiniz. Bu eylem dosyayı geçerli konumundan siler ve bir kopyasını karantinaya alır.

#### <a name="actions-on-users"></a>Kullanıcılara yönelik eylemler
Seçildiğinde, sorgu sonuçlarının , `InitiatingProcessAccountObjectId`veya `RecipientObjectId` sütunundaki `AccountObjectId`kullanıcılar üzerinde Kullanıcıyı **güvenliği aşılmış olarak işaretle** eylemi gerçekleştirilen eylemdir. Bu eylem, kullanıcıların risk düzeyini Azure Active Directory'de "yüksek" olarak ayarlayarak ilgili [kimlik koruma ilkelerini](/azure/active-directory/identity-protection/overview-identity-protection) tetikler.

> [!NOTE]
> Özel algılama kuralları için izin ver veya engelle eylemi şu anda Microsoft 365 Defender'de desteklenmiyor.

### <a name="5-set-the-rule-scope"></a>5. Kural kapsamını ayarlayın.
Kuralın kapsamına giren cihazları belirtmek için kapsamı ayarlayın. Kapsam, cihazları denetleyen kuralları etkiler ve yalnızca posta kutularını ve kullanıcı hesaplarını veya kimlikleri denetleyen kuralları etkilemez.

Kapsamı ayarlarken şunları seçebilirsiniz:

- Tüm cihazlar
- Belirli cihaz grupları

Yalnızca kapsamdaki cihazlardan veriler sorgulanır. Ayrıca, yalnızca bu cihazlarda eylemler gerçekleştirilecektir.

### <a name="6-review-and-turn-on-the-rule"></a>6. Kuralı gözden geçirin ve açın.
Kuralı gözden geçirdikten sonra **oluştur'u** seçerek kaydedin. Özel algılama kuralı hemen çalışır. Eşleşmeleri denetlemek, uyarılar oluşturmak ve yanıt eylemleri uygulamak için yapılandırılmış sıklık temelinde yeniden çalışır.


>[!Important] 
>Özel algılamalar, verimlilik ve verimlilik açısından düzenli olarak gözden geçirilmelidir. Gerçek uyarıları tetikleyen algılamalar oluşturduğunuzdan emin olmak için Mevcut özel algılama kurallarını yönetme bölümündeki adımları izleyerek [mevcut özel algılamalarınızı](#manage-existing-custom-detection-rules) gözden geçirin. <br>  
Özel algılamalarınızın genişliği veya özgüllüğü üzerinde denetim sahibi olursunuz, böylece özel algılamalar tarafından oluşturulan yanlış uyarılar kuralların belirli parametrelerini değiştirme gereksinimini gösterebilir.


## <a name="manage-existing-custom-detection-rules"></a>Mevcut özel algılama kurallarını yönetme
Mevcut özel algılama kurallarının listesini görüntüleyebilir, önceki çalıştırmalarını denetleyebilir ve tetikledikleri uyarıları gözden geçirebilirsiniz. Ayrıca isteğe bağlı olarak bir kural çalıştırabilir ve değiştirebilirsiniz.

>[!TIP]
> Özel algılamalar tarafından tetiklenen uyarılar, uyarılar ve olay API'leri üzerinden kullanılabilir. Daha fazla bilgi için bkz[. Desteklenen Microsoft 365 Defender API'leri](api-supported.md).

### <a name="view-existing-rules"></a>Mevcut kuralları görüntüleme

Mevcut tüm özel algılama kurallarını görüntülemek için **Özel Tehdit Avcılığı** > **algılama kuralları'na** gidin. Sayfada tüm kurallar aşağıdaki çalıştırma bilgileriyle listelenir:

- **Son çalıştırma**— sorgu eşleşmelerini denetlemek ve uyarılar oluşturmak için bir kuralın son çalıştırıldığı zaman
- **Son çalıştırma durumu**— bir kuralın başarıyla çalıştırılıp çalıştırılmadığı
- **Sonraki çalıştırma**— bir sonraki zamanlanmış çalıştırma
- **Durum**— Kuralın açık veya kapalı olup olmadığı

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Kural ayrıntılarını görüntüleme, kuralı değiştirme ve kuralı çalıştırma

Özel algılama kuralıyla ilgili kapsamlı bilgileri görüntülemek için **Özel Tehdit Avcılığı** > **algılama kuralları'na** gidin ve kuralın adını seçin. Daha sonra kural hakkındaki genel bilgileri, çalıştırma durumu ve kapsamı da dahil olmak üzere görüntüleyebilirsiniz. Sayfa ayrıca tetiklenen uyarıların ve eylemlerin listesini de sağlar.

:::image type="content" source="../../media/custom-detect-rules-view.png" alt-text="Microsoft 365 Defender portalındaki Özel algılama kuralı ayrıntıları sayfası" lightbox="../../media/custom-detect-rules-view.png":::<br>
*Özel algılama kuralı ayrıntıları*

Bu sayfadan kural üzerinde aşağıdaki eylemleri de gerçekleştirebilirsiniz:

- **Çalıştır**—kuralı hemen çalıştırın. Bu, sonraki çalıştırmanın aralığını da sıfırlar.
- **Düzenle**—sorguyu değiştirmeden kuralı değiştirme
- **Sorguyu değiştirme**—sorguyu gelişmiş tehdit avcılığında düzenleme
-  /  Aç **Kapatma**— kuralı etkinleştirin veya çalışmasını durdurun
- **Silme**—kuralı kapatma ve kaldırma

### <a name="view-and-manage-triggered-alerts"></a>Tetiklenen uyarıları görüntüleme ve yönetme

Kural ayrıntıları ekranında (**Özel** > **Algılama algılamaları** > **[Kural adı]**), kuralla eşleşmeler tarafından oluşturulan uyarıları listeleyen  **Tetiklenen** uyarılar'a gidin. Bununla ilgili ayrıntılı bilgileri görüntülemek için bir uyarı seçin ve aşağıdaki eylemleri gerçekleştirin:

- Durumunu ve sınıflandırmasını ayarlayarak uyarıyı yönetme (doğru veya yanlış uyarı)
- Uyarıyı bir olaya bağlama
- Gelişmiş tehdit avcılığında uyarıyı tetikleyen sorguyu çalıştırma

### <a name="review-actions"></a>Eylemleri gözden geçirme
Kural ayrıntıları ekranında (**Özel** >  Algılamalar **[Kural adı]**), Kuralla **eşleşmelere** >  göre gerçekleştirilen eylemleri listeleyen **Tetiklenen eylemler'e** gidin.

>[!TIP]
>Bilgileri hızla görüntülemek ve tablodaki bir öğe üzerinde işlem yapmak için tablonun sol tarafındaki [&#10003;] seçim sütununu kullanın.

>[!NOTE]
>Bu makaledeki bazı sütunlar Uç Nokta için Microsoft Defender'da kullanılamayabilir. Daha fazla veri kaynağı kullanarak tehditleri avlamak için [Microsoft 365 Defender açın](m365d-enable.md). Gelişmiş avcılık sorgularını Uç Nokta için Microsoft Defender'den geçirme bölümünde yer alan adımları izleyerek [gelişmiş avcılık iş akışlarınızı Uç Nokta için Microsoft Defender'den Microsoft 365 Defender](advanced-hunting-migrate-from-mde.md) taşıyabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.
- [Özel algılamalara genel bakış](custom-detections-overview.md)
- [Gelişmiş avcılığa genel bakış](advanced-hunting-overview.md)
- [Gelişmiş tehdit avcılığı sorgu dilini öğrenme](advanced-hunting-query-language.md)
- [gelişmiş tehdit avcılığı sorgularını Uç Nokta için Microsoft Defender geçirme](advanced-hunting-migrate-from-mde.md)
