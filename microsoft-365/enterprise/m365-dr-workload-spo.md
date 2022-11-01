---
title: SharePoint Online ve OneDrive İş için Data Residency
description: SharePoint Online ve OneDrive İş için Data Residency
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: b2ffb535ae34a2d5af836c14cd88dd295d7d574f
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806189"
---
# <a name="data-residency-for-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online ve OneDrive İş için Data Residency

## <a name="data-residency-commitments-available"></a>**Data Residency Taahhütleri Kullanılabilir**

### <a name="product-terms"></a>Ürün Koşulları

Gerekli Koşullar:

- _Kiracının_ _Yerel Bölge Coğrafyası_, Avrupa Birliği veya Birleşik Devletler dahil bir kaydolma ülkesi vardır.

**Taahhüt:**

_Geçerli dil için lütfen [Gizlilik ve Güvenlik Ürün Koşulları'na](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) bakın ve "Core Online Services için Bekleyen Müşteri Verilerinin Konumu" başlıklı bölümü görüntüleyin._

### <a name="advanced-data-residency-add-on"></a>Gelişmiş Data Residency eklentisi

Gerekli Koşullar:

1. _Kiracının_ _Yerel Bölge Coğrafyası veya Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi _vardır_.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_.
1. SharePoint Online aboneliği müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

**Taahhüt:**

SharePoint Online ve OneDrive İş için bekleyen taahhüt kapsamındaki belirli müşteri verileri için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#sharepoint-onlineonedrive-for-business) bakın.

### <a name="multi-geo-add-on"></a>Multi-Geo eklentisi

Gerekli Koşullar:

1. _Kiracılar__, Uydu Coğrafya'ya_ atanan tüm kullanıcıları kapsayan geçerli bir Multi-Geo aboneliğine sahiptir
1. Müşterinin etkin bir Kurumsal Anlaşma olması gerekir.
1.Satın alınan toplam Multi-Geo birimi _, Kiracıdaki_ toplam uygun koltukların %5'inden büyük olmalıdır.

**Taahhüt:** Müşteriler SharePoint Online/OneDrive İş kullanıcılarını Multi-Geo tarafından desteklenen herhangi bir _Uydu Coğrafyasına_ atayabilir (bkz. Bölüm 4.1.3). Aşağıdaki müşteri verileri ilgili _Uydu Coğrafyasında_ depolanır: SharePoint Online site içeriği ve bu site içinde depolanan dosyalar ve OneDrive İş karşıya yüklenen dosyalar.  

## <a name="multi-geo-capabilities-in-sharepoint-online--onedrive-for-business"></a>**SharePoint Online/OneDrive İş'da Multi-Geo Özellikleri**

OneDrive ve SharePoint Online'daki Multi-Geo özellikleri, SharePoint ekip siteleri ve Microsoft 365 Grup posta kutuları gibi belirli bir _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyasında_ bekleyen posta kutuları gibi paylaşılan kaynakların denetimini sağlar.

Her kullanıcı, Grup posta kutusu ve SharePoint sitesi, Makro Bölgesi Coğrafyası'nı veya _Yerel Bölge_ Coğrafyası'nı  (ilgili verilerin depolandığı konum) gösteren Tercih Edilen Veri Konumu'na (PDL) sahiptir. Kullanıcıların kişisel verileri (Exchange posta kutusu ve OneDrive) ve oluşturdukları tüm Microsoft 365 Grupları veya SharePoint siteleri, veri yerleşimi gereksinimlerini karşılamak için belirtilen _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyaları_ konumunda depolanabilir. Her _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası_ konumu için farklı yöneticiler belirtebilirsiniz.

Kullanıcılar Office uygulamaları, OneDrive ve Arama gibi Microsoft 365 hizmetlerini kullanırken sorunsuz bir deneyim yaşar. Ayrıntılar için bkz. Multi-Geo ortamında kullanıcı deneyimi.

### <a name="onedrive"></a>**OneDrive**

Her kullanıcının OneDrive'ı, yönetici tarafından kullanıcının PDL'sine uygun olarak _Uydu Coğrafya_ konumuna sağlanabilir veya taşınabilir. Kişisel dosyalar daha sonra _bu Uydu Coğrafya_ konumunda tutulur, ancak diğer _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafya_ konumlarındaki kullanıcılarla paylaşılabilir.

### <a name="sharepoint-sites-and-groups"></a>**SharePoint Siteleri ve Grupları**
Multi-Geo özelliğinin yönetimine SharePoint yönetim merkezinden ulaşabilirsiniz.

Kullanıcı çok coğrafi bir ortamda SharePoint grubuna bağlı bir site oluşturduğunda, pdl'leri sitenin ve ilişkili Grup posta kutusunun oluşturulduğu _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafya_ konumunu belirlemek için kullanılır. (Kullanıcının PDL değeri ayarlanmamışsa veya _Uydu_ Coğrafya konumu olarak yapılandırılmamış _Makro Bölge Coğrafyası_ veya _Yerel Bölge Coğrafya_ konumu olarak ayarlanmışsa, site ve posta kutusu _Birincil Sağlanan Coğrafya'da_ oluşturulur.)

Exchange, OneDrive, SharePoint ve Teams dışındaki Microsoft 365 hizmetleri Multi-Geo ile kullanılamaz. Ancak, bu hizmetler tarafından oluşturulan Microsoft 365 Grupları oluşturucunun PDL'siyle ve Exchange Grubu posta kutusuyla yapılandırılır, SharePoint sitesi ilgili _Makro Bölgesi Coğrafyası_ veya _Yerel Bölge Coğrafyası'nda_ sağlanır.

### <a name="managing-the-multi-geo-environment"></a>**Multi-Geo ortamını yönetme**

Multi-Geo ortamınızı ayarlama ve yönetme işlemi SharePoint yönetim merkezi üzerinden yapılır.

#### <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>**Çok coğrafili ortamlarda SharePoint depolama kotaları**

Varsayılan olarak, çok coğrafi ortamın tüm _Coğrafya_ konumları kullanılabilir _Kiracı_ depolama kotasını paylaşır.

SharePoint coğrafi depolama kotası ayarıyla, her _Coğrafya_ konumu için depolama kotasını yönetebilirsiniz. _Bir Coğrafya_ konumu için depolama kotası ayırdığınızda, bu konum söz konusu _Coğrafya_ konumu için kullanılabilir en yüksek depolama miktarı olur ve kullanılabilir _Kiracı_ depolama kotasından düşülür. Kalan kullanılabilir _Kiracı_ depolama kotası daha sonra belirli bir depolama kotasının ayrılmadığı yapılandırılmış _Coğrafya_ konumları arasında paylaşılır.

Herhangi bir _Coğrafya_ konumu için SharePoint depolama kotası, _Birincil Sağlanan Coğrafya'ya_ bağlanarak SharePoint Online yöneticisi tarafından ayrılabilir. _Uydu Coğrafya_ konumları için _coğrafya_ yöneticileri depolama kotasını görüntüleyebilir ancak ayıramaz.

#### <a name="configure-a-storage-quota-for-a-_geography_-location"></a>**_Coğrafya_ konumu için depolama kotası yapılandırma**

bir _Coğrafya_ konumu için depolama kotasını ayırmak için [Microsoft Office SharePoint Online Yönetim Kabuğu'nı](https://www.microsoft.com/download/details.aspx?id=35588) kullanın ve _Birincil Sağlanan Coğrafya_ konumuna bağlanın.

Bir konuma Depolama Kotası ayırmak için cmdlet'ini çalıştırın:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Geçerli _Coğrafya_ konumu için Depolama Kotası'nı görüntülemek için şunu çalıştırın:

```powershell
Get-SPOGeoStorageQuota
```

Tüm _Coğrafya_ konumlarının Depolama Kotasını görüntülemek için şunu çalıştırın:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

_Coğrafya_ konumu için ayrılan depolama kotasını kaldırmak için ayarlayın`StorageQuota value = 0`:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```

### <a name="move-a-onedrive-site"></a>OneDrive sitesi taşıma

#### <a name="move-a-onedrive-site-to-a-different-_geography_-location"></a>OneDrive sitesini farklı bir _Coğrafya_ konumuna taşıma

OneDrive _Coğrafya_ taşıma ile kullanıcının OneDrive'sını farklı bir _Coğrafya_ konumuna taşıyabilirsiniz. OneDrive _Coğrafya_ taşıma işlemi SharePoint Online yöneticisi veya Microsoft 365 genel yöneticisi tarafından gerçekleştirilir. OneDrive _Coğrafya_ taşıma işlemine başlamadan önce, OneDrive'ı taşınan kullanıcıyı bilgilendirdiğinizden emin olun ve taşıma süresi boyunca tüm dosyaları kapatmasını önerin. (Taşıma sırasında kullanıcının Office istemcisini kullanarak açık bir belgesi varsa, taşıma tamamlandıktan sonra belgenin yeni konuma kaydedilmesi gerekir.) taşıma, isterseniz gelecek bir süre için zamanlanabilir.

OneDrive hizmeti, içeriği depolamak için Azure Blob Depolama kullanır. Kullanıcının OneDrive'ı ile ilişkili Depolama blobu, hedef OneDrive'ın kullanılabilmesinden sonra 40 gün içinde kaynaktan hedef _Coğrafya_ konumuna taşınır. Hedef OneDrive kullanılabilir olduğunda kullanıcının OneDrive erişimi geri yüklenir.

OneDrive _Coğrafya_ taşıma penceresi (yaklaşık 2-6 saat) sırasında kullanıcının OneDrive'ı salt okunur olarak ayarlanır. Kullanıcı dosyalarına OneDrive eşitleme uygulaması veya SharePoint Online'daki OneDrive sitesi aracılığıyla erişmeye devam edebilir. OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra kullanıcı, Microsoft 365 uygulama başlatıcısında OneDrive'a gittiği zaman hedef _Coğrafya_ konumundaki OneDrive'larına otomatik olarak bağlanır. Eşitleme uygulaması otomatik olarak yeni konumdan eşitlemeye başlar.

Bu makaledeki yordamlar [Microsoft Office SharePoint Online PowerShell Modülü](https://www.microsoft.com/download/details.aspx?id=35588) gerektirir.

#### <a name="communicating-to-your-users"></a>Kullanıcılarınıza iletişim kurma

OneDrive sitelerini _Coğrafya_ konumları arasında taşırken kullanıcılarınıza ne bekleyebileceğinizi bildirmek önemlidir. Bu, kullanıcı karışıklığını ve yardım masanıza yapılan aramaları azaltmaya yardımcı olabilir. Kullanıcılarınızı taşımadan önce Email ve şu bilgileri onlara bildirin: -Taşımanın ne zaman başlaması ve ne kadar sürmesinin beklendiği -OneDrive'larının taşındığı _Coğrafya_ konumu ve yeni konuma erişim URL'si - Taşıma sırasında düzenleme yapmamaları ve dosyalarını kapatmaları gerekir.
-Dosya izinleri ve paylaşım, taşıma sonucunda değişmez.
-Çok coğrafi bir ortamda kullanıcı deneyiminden neler beklenmeli?

Taşıma işlemi başarıyla tamamlandığında kullanıcılarınıza OneDrive'da çalışmaya devam etmelerini bildiren bir e-posta gönderdiğinizden emin olun.

#### <a name="scheduling-onedrive-site-moves"></a>OneDrive sitesi taşımalarını zamanlama

OneDrive sitesi taşımalarını önceden zamanlayabilirsiniz (bu makalenin ilerleyen bölümlerinde açıklanmaktadır). İş akışlarınızı ve iletişim stratejilerinizi doğrulamak için az sayıda kullanıcıyla başlamanızı öneririz. İşlemi rahatça tamamladıktan sonra, taşımaları şu şekilde zamanlayabilirsiniz: -Bir kerede en fazla 4.000 taşıma zamanlayabilirsiniz.
-Taşımalar başladığında, kuyrukta ve belirli bir zamanda bekleyen en fazla 4.000 taşıma ile daha fazla zamanlayabilirsiniz.
-OneDrive'ın taşınabilecek en büyük boyutu 1 terabayttır (1 TB).

#### <a name="moving-a-onedrive-site"></a>**OneDrive sitesini taşıma**
OneDrive _Coğrafya_ taşıma işlemi gerçekleştirmek için _Kiracı_ yöneticisinin önce kullanıcının Tercih Edilen Veri Konumu'nun (PDL) uygun _Coğrafya_ konumuna ayarlanması gerekir. PDL ayarlandıktan sonra, OneDrive _Coğrafya_ taşıma işlemini başlatmadan önce PDL güncelleştirmesinin _Coğrafya_ konumları arasında eşitlenmesi için en az 24 saat bekleyin.

_Coğrafya_ taşıma cmdlet'lerini kullanırken, aşağıdaki söz dizimini kullanarak kullanıcının geçerli OneDrive _Coğrafya_ konumunda SPO Hizmeti'ne bağlanın:

```powershell
Connect-SPOService -url https://<tenantName>-admin.sharepoint.com
```

Örneğin: 'Matt@contosoenergy.onmicrosoft.com' kullanıcısının OneDrive'ını taşımak için, kullanıcının OneDrive'ı EUR _Coğrafya_ konumunda olduğundan EUR SharePoint Yönetici merkezine bağlanın:

```powershell
Connect-SPOService -url https://contosoenergyeur-admin.sharepoint.com
```

#### <a name="validating-the-environment"></a>**Ortamı doğrulama**
  
OneDrive _Coğrafya_ taşımaya başlamadan önce ortamı doğrulamanızı öneririz.

Tüm _Coğrafya_ konumlarının uyumlu olduğundan emin olmak için şunu çalıştırın:

```powershell
Get-SPOGeoMoveCrossCompatibilityStatus
```

_Coğrafya_ konumlarınızın listesini görürsünüz ve içerik arasında taşınıp taşınamayacağınız "Uyumlu" olarak belirtilir. Komut "Uyumsuz" döndürürse, lütfen durumu daha sonraki bir tarihte doğrulamayı yeniden deneyin.

OneDrive bir alt site içeriyorsa, örneğin, bu site taşınamaz. OneDrive'ın taşınıp taşınamadığını doğrulamak için -ValidationOnly parametresiyle Start-SPOUserAndContentMove cmdlet'ini kullanabilirsiniz:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly
```

  Bu, OneDrive taşınmaya hazırsa Başarılı veya taşımayı engelleyecek yasal bir ayrı tutma veya alt site varsa Başarısız döndürür. OneDrive'ın taşınmaya hazır olduğunu doğruladıktan sonra taşıma işlemini başlatabilirsiniz.

#### <a name="start-a-onedrive-geo-move"></a>**OneDrive coğrafi taşımayı başlatma**

Taşımayı başlatmak için şunu çalıştırın:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>
```

Şu parametreleri kullanarak:

- _UserPrincipalName_ – OneDrive'ın taşındığı kullanıcının UPN'i.
- _DestinationDataLocation_ – OneDrive'ın taşınması gereken yeri Geo-Location. Bu, kullanıcının tercih ettiği veri konumuyla aynı olmalıdır.

Örneğin, matt@contosoenergy.onmicrosoft.com OneDrive'ını EUR'tan AUS'ye taşımak için şunu çalıştırın:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS
```

_Coğrafya_ taşımasını daha sonra zamanlamak için aşağıdaki parametrelerden birini kullanın:

- _PreferredMoveBeginDate_ – Taşıma büyük olasılıkla belirtilen zamanda başlayacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.
- _PreferredMoveEndDate_ – Taşıma işlemi büyük olasılıkla belirtilen zamana kadar en iyi çaba temelinde tamamlanacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.

#### <a name="cancel-a-onedrive-_geography_-move"></a>**OneDrive _Coğrafya_ taşıma işlemini iptal etme**
  
Taşıma işlemi devam etmemesi veya cmdlet'ini kullanarak tamamlanması koşuluyla kullanıcının OneDrive'ının _Coğrafya_ taşımasını durdurabilirsiniz:

```powershell
Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>
```

Burada _UserPrincipalName_ , OneDrive taşımasını durdurmak istediğiniz kullanıcının UPN'sini oluşturur.

#### <a name="determining-current-status"></a>**Geçerli durumu belirleme**

Get-SPOUserAndContentMoveState cmdlet'ini kullanarak bağlandığınız _Coğrafya'da_ OneDrive _Coğrafya_ taşıma işleminin durumunu denetleyebilirsiniz.

Taşıma durumları aşağıdaki tabloda açıklanmıştır.

|Durum|Açıklama|
|---|---|
|Başlamadı|Taşıma başlatılmadı|
|InProgress (_n_/4)|Taşıma işlemi aşağıdaki durumlardan birinde devam ediyor: <ul><li>Doğrulama (1/4)</li><li>Yedekleme (2/4)</li><li>Geri Yükleme (3/4)</li><li>Temizleme (4/4)</li></ul>|
|Başarı|Taşıma işlemi başarıyla tamamlandı.|
|Başarısız|Taşıma başarısız oldu.|

Belirli bir kullanıcının taşıma durumunu bulmak için _UserPrincipalName_ parametresini kullanın:

```powershell
Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>
```

Bağlandığınız _Coğrafya_ konumundaki veya bu konumdaki tüm taşımaların durumunu bulmak için _MoveState_ parametresini şu değerlerden biriyle kullanın: NotStarted, InProgress, Success, Failed, All.

```powershell
Get-SPOUserAndContentMoveState -MoveState <value>
```

Taşıma _durumunun daha_ ayrıntılı açıklamaları için Ayrıntılı parametresini de ekleyebilirsiniz.

#### <a name="user-experience"></a>**Kullanıcı Deneyimi**

OneDrive kullanıcıları, OneDrive'ları farklı bir _Coğrafya_ konumuna taşınırsa en düşük kesintiyi fark etmelidir. Taşıma sırasında kısa bir salt okunur durum dışında, taşıma tamamlandıktan sonra mevcut bağlantılar ve izinler beklendiği gibi çalışmaya devam eder.

#### <a name="users-onedrive"></a>**Kullanıcının OneDrive'ı**

Taşıma işlemi devam ederken kullanıcının OneDrive'ı salt okunur olarak ayarlanır. Taşıma işlemi tamamlandıktan sonra kullanıcı, Microsoft 365 uygulama başlatıcısı veya web tarayıcısı olan OneDrive'a gittiği zaman yeni _Coğrafya_  konumundaki OneDrive'larına yönlendirilir.

#### <a name="permissions-on-onedrive-content"></a>**OneDrive içeriğindeki izinler**

OneDrive içeriğine izinleri olan kullanıcılar, taşıma sırasında ve tamamlandıktan sonra içeriğe erişmeye devam eder.

#### <a name="onedrive-sync-app"></a>**OneDrive eşitleme uygulaması**

OneDrive eşitleme uygulaması, OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra eşitlemeyi otomatik olarak algılar ve yeni OneDrive konumuna sorunsuz bir şekilde aktarır. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez. (Eşitleme uygulamasının sürüm 17.3.6943.0625 veya üzeri gereklidir.) OneDrive _Coğrafya_ taşıma işlemi devam ederken kullanıcı bir dosyayı güncelleştirirse, eşitleme uygulaması taşıma işlemi devam ederken dosya yüklemelerinin beklemede olduğunu bildirir.

#### <a name="sharing-links"></a>**Paylaşım bağlantıları**

OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra, taşınan dosyaların mevcut paylaşılan bağlantıları otomatik olarak yeni _Coğrafya_ konumuna yönlendirilir.

#### <a name="onenote-experience"></a>**OneNote Deneyimi**

OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra OneNote win32 istemcisi ve UWP (Evrensel) Uygulaması not defterlerini otomatik olarak algılar ve yeni OneDrive konumuna sorunsuz bir şekilde eşitler. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez. Kullanıcıya görünen tek gösterge, OneDrive _Coğrafya_ taşıma işlemi devam ederken not defteri eşitlemesinin başarısız olmasıdır. Bu deneyim aşağıdaki OneNote istemci sürümlerinde kullanılabilir:

- OneNote win32 – Sürüm 16.0.8326.2096 (ve üzeri)
- OneNote UWP – Sürüm 16.0.8431.1006 (ve üzeri)
- OneNote Mobil Uygulaması – Sürüm 16.0.8431.1011 (ve üzeri)

#### <a name="teams-app"></a>**Teams uygulaması**

OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra kullanıcılar Teams uygulamasından OneDrive dosyalarına erişebilir. Ayrıca, _Coğrafya_ taşımadan önce OneDrive'larından Teams sohbeti aracılığıyla paylaşılan dosyalar taşıma tamamlandıktan sonra çalışmaya devam eder.

#### <a name="onedrive-mobile-app-ios"></a>**OneDrive Mobil Uygulaması (iOS)**

OneDrive _Coğrafya_ taşıma işlemi tamamlandıktan sonra, kullanıcının yeni OneDrive konumuyla eşitlemek için iOS Mobil Uygulamasında oturumu kapatması ve yeniden oturum açması gerekir.

#### <a name="existing-followed-groups-and-sites"></a>**Mevcut takip edilen gruplar ve siteler**

Takip edilen siteler ve gruplar _, Coğrafya_ konumlarından bağımsız olarak kullanıcının OneDrive'ında gösterilir. Başka bir _Coğrafya_ konumunda barındırılan siteler ve gruplar ayrı bir sekmede açılır.

#### <a name="delve-geo-url-updates"></a>**Delve Geo URL güncelleştirmeleri**

Kullanıcılar, PDL'lerine karşılık gelen Delve _Coğrafyasına_ yalnızca OneDrive'ları yeni _Coğrafya'ya_ taşındıktan sonra gönderilir.

### <a name="move-a-sharepoint-site"></a>**SharePoint sitesini taşıma**
#### <a name="move-a-sharepoint-site-to-a-different-_geography_-location"></a>**SharePoint sitesini farklı bir _Coğrafya_ konumuna taşıma**

SharePoint sitesi _Coğrafya_ taşıma ile, SharePoint sitelerini Multi-Geo ortamınızdaki diğer _Coğrafya_ konumlarına taşıyabilirsiniz.
Aşağıdaki site türleri _Coğrafya_ konumları arasında taşınabilir:

- Microsoft Teams ile ilişkilendirilmiş siteler de dahil olmak üzere Microsoft 365 grup bağlantılı siteler
- Microsoft 365 grup ilişkilendirmesi olmayan modern siteler
- Klasik SharePoint siteleri
- İletişim siteleri

Siteyi _Coğrafya_ konumları arasında taşımak için Genel Yönetici veya SharePoint Yöneticisi olmanız gerekir.
SharePoint sitesi _Coğrafya_ taşıma işlemi sırasında site içeriğine bağlı olarak yaklaşık 4-6 saatlik salt okunur bir pencere vardır

#### <a name="best-practices"></a>**En iyi yöntemler**

- Yordam hakkında bilgi edinmek için test sitesinde SharePoint sitesi taşımayı deneyin.
- Sitenin taşımayı zamanlamadan veya gerçekleştirmeden önce taşınıp taşınamayacağını doğrulayın.
- Mümkün olduğunda coğrafi bölgeler arası siteler, kullanıcı etkisini azaltmak için iş saatleri dışında hareket eder.
- Siteler taşınmadan önce etkilenen kullanıcılarla iletişim kurun.

#### <a name="communicating-to-your-users"></a>**Kullanıcılarınıza iletişim kurma**

SharePoint sitelerini _Coğrafya_ konumları arasında taşırken, sitelerin kullanıcılarına (genellikle siteyi düzenleme yeteneği olan herkes) ne bekleyebileceğinizi bildirmek önemlidir. Bu, kullanıcı karışıklığını ve yardım masanıza yapılan aramaları azaltmaya yardımcı olabilir. Taşımadan önce sitelerinizin kullanıcılarını Email ve aşağıdaki bilgileri onlara bildirin:

- Taşıma işleminin ne zaman başlaması ve ne kadar sürmesi beklenir?
- Sitelerinin taşındığı _Coğrafya_ konumu ve yeni konuma erişmek için URL
- Taşıma sırasında düzenleme yapmamaları ve dosyalarını kapatmaları gerekir.
- Taşıma nedeniyle dosya izinleri ve paylaşım değişmez.
- Çok coğrafi bir ortamda kullanıcı deneyiminden neler beklenmeli?

Taşıma işlemi başarıyla tamamlandığında sitelerinizin kullanıcılarına sitelerinde çalışmaya devam yapabileceklerini bildiren bir e-posta gönderdiğinizden emin olun.

#### <a name="scheduling-sharepoint-site-moves"></a>**SharePoint sitesi taşımalarını zamanlama**

SharePoint sitesi taşımalarını önceden zamanlayabilirsiniz (bu makalenin ilerleyen bölümlerinde açıklanmaktadır). Taşımaları aşağıdaki gibi zamanlayabilirsiniz:

- Bir kerede en fazla 4.000 taşıma zamanlayabilirsiniz.
- Taşımalar başladığında, kuyrukta ve belirli bir zamanda bekleyen en fazla 4.000 taşıma ile daha fazla zamanlayabilirsiniz.
- Taşınabilecek SharePoint sitesinin boyutu üst sınırı 1 terabayttır (1 TB).

SharePoint sitesi _Coğrafya_ taşımasını daha sonra zamanlamak için, taşımayı başlattığınızda aşağıdaki parametrelerden birini ekleyin:

- PreferredMoveBeginDate – Taşıma büyük olasılıkla belirtilen zamanda başlayacaktır.
- PreferredMoveEndDate – Taşıma işlemi büyük olasılıkla belirtilen zamana kadar en iyi çaba temelinde tamamlanacaktır.

Saat, her iki parametre için de Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.

#### <a name="moving-the-site"></a>**Siteyi taşıma**

SharePoint sitesi _Coğrafya_ taşıma işlemi, sitenin bulunduğu _Coğrafya_ konumundaki SharePoint Yönetici URL'sine bağlanmanızı ve taşımayı gerçekleştirmenizi gerektirir.

Örneğin, site URL'si ise `https://contosohealthcare.sharepoint.com/sites/Turbines`adresinden SharePoint Yönetici URL'sine `https://contosohealthcare-admin.sharepoint.com`bağlanın:

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

#### <a name="validating-the-environment"></a>**Ortamı doğrulama**

Herhangi bir site taşımasını zamanlamadan önce, sitenin taşına çalıştığından emin olmak için bir doğrulama gerçekleştirmenizi öneririz.

Sitelerin taşınmayı şu şekilde desteklemiyoruz:

- İş Bağlantı Hizmetleri
- InfoPath formları
- Uygulanan Bilgi Hakları Yönetimi (IRM) şablonları

Tüm _Coğrafya_ konumlarının uyumlu olduğundan emin olmak için komutunu çalıştırın `Get-SPOGeoMoveCrossCompatibilityStatus`. Bu, tüm _Coğrafya_ konumlarınızı ve ortamın hedef _Coğrafya_ konumuyla uyumlu olup olmadığını görüntüler.

Sitenizde yalnızca doğrulama denetimi gerçekleştirmek için parametresiyle `Start-SPOSiteContentMove` kullanarak sitenin `-ValidationOnly` taşınıp taşınamadığını doğrulayın. Örneğin:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Bu, site taşınmaya hazırsa _Başarılı_ veya engellenen koşullardan herhangi biri varsa _Başarısız_ döndürür.

#### <a name="start-a-sharepoint-site-_geography_-move-for-a-site-with-no-associated-microsoft-365-group"></a>**İlişkili Microsoft 365 grubu olmayan bir site için SharePoint sitesi _Coğrafya_ taşımayı başlatma**
  
Varsayılan olarak, sitenin ilk URL'si hedef _Coğrafya_ konumunun URL'sine dönüşür. Örneğin:

`https://Contoso.sharepoint.com/sites/projectx` Hedef `https://ContosoEUR.sharepoint.com/sites/projectx`

Microsoft 365 grup ilişkilendirmesi olmayan siteler için parametresini kullanarak siteyi `-DestinationUrl` yeniden adlandırabilirsiniz. Örneğin:

<https://Contoso.sharepoint.com/sites/projectx> Hedef `https://ContosoEUR.sharepoint.com/sites/projecty`

Site taşıma işlemini başlatmak için şunu çalıştırın:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

#### <a name="start-a-sharepoint-site-_geography_-move-for-a-microsoft-365-group-connected-site"></a>**Microsoft 365 grup bağlantılı bir site için SharePoint sitesi _Coğrafya_ taşımayı başlatma**

  Microsoft 365 grubuna bağlı bir siteyi taşımak için, Genel Yönetici veya SharePoint Yöneticisinin önce Microsoft 365 grubunun Tercih Edilen Veri Konumu (PDL) özniteliğini değiştirmesi gerekir.

Bir Microsoft 365 grubunun PDL'sini ayarlamak için:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

PDL'yi güncelleştirdikten sonra site taşıma işlemini başlatabilirsiniz:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

#### <a name="cancel-a-sharepoint-site-_geography_-move"></a>**SharePoint sitesi _Coğrafya_ taşımayı iptal etme**

Taşıma işlemi devam etmemesi veya Stop-SPOSiteContentMove cmdlet'ini kullanarak tamamlanması koşuluyla, SharePoint sitesi _Coğrafya_ taşımasını durdurabilirsiniz.

#### <a name="determining-the-status-of-a-sharepoint-site-_geography_-move"></a>**SharePoint sitesi _Coğrafya_ taşıma durumunu belirleme**

Aşağıdaki cmdlet'leri kullanarak bağlandığınız _Coğrafya_ dışında bir site taşıma işleminin durumunu belirleyebilirsiniz:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (Gruba bağlı olmayan siteler)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Gruba bağlı siteler)

`-SourceSiteUrl` Taşıma durumunu görmek istediğiniz siteyi belirtmek için parametresini kullanın.

Taşıma durumları aşağıdaki tabloda açıklanmıştır.

****

|Durum|Açıklama|
|---|---|
|Tetikleme için Hazır|Taşıma başlatılmadı.|
|Planlanan|Taşıma işlemi kuyrukta ancak henüz başlamadı.|
|InProgress (n/4)|Taşıma işlemi şu durumlardan birinde sürüyor: Doğrulama (1/4), Yedekleme (2/4), Geri Yükleme (3/4), Temizleme (4/4).|
|Başarı|Taşıma işlemi başarıyla tamamlandı.|
|Başarısız|Taşıma başarısız oldu.|
|

Taşıma hakkında ek bilgi görmek için seçeneğini de uygulayabilirsiniz `-Verbose` .

#### <a name="user-experience"></a>**Kullanıcı deneyimi**

Site kullanıcıları, siteleri farklı bir _Coğrafya_ konumuna taşındığında en düşük kesintiyi fark etmelidir. Taşıma sırasında kısa bir salt okunur durum dışında, taşıma tamamlandıktan sonra mevcut bağlantılar ve izinler beklendiği gibi çalışmaya devam eder.

#### <a name="site"></a>**Site**

Taşıma işlemi devam ederken site salt okunur olarak ayarlanır. Taşıma tamamlandıktan sonra, yer işaretlerine veya sitenin diğer bağlantılarına tıkladığında kullanıcı yeni _Coğrafya_ konumundaki yeni siteye yönlendirilir.

#### <a name="permissions"></a>**İzinler**

Site izinleri olan kullanıcılar, taşıma sırasında ve tamamlandıktan sonra siteye erişmeye devam eder.

#### <a name="sync-app"></a>**Uygulamayı eşitleme**

Eşitleme uygulaması, site taşıma işlemi tamamlandıktan sonra eşitlemeyi otomatik olarak algılar ve yeni site konumuna sorunsuz bir şekilde aktarır. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez. (Eşitleme uygulamasının sürüm 17.3.6943.0625 veya üzeri gereklidir.) Taşıma işlemi devam ederken kullanıcı bir dosyayı güncelleştirirse, eşitleme uygulaması taşıma işlemi devam ederken dosya yüklemelerinin beklemede olduğunu bildirir.

#### <a name="sharing-links"></a>**Paylaşım bağlantıları**
SharePoint sitesi _Coğrafya_ taşıma işlemi tamamlandığında, taşınan dosyalar için mevcut paylaşılan bağlantılar otomatik olarak yeni _Coğrafya_ konumuna yönlendirilir.

#### <a name="most-recently-used-files-in-office-mru"></a>**Office'te (MRU) En Son Kullanılan dosyalar**

MRU hizmeti, taşıma tamamlandıktan sonra site URL'si ve içerik URL'leriyle güncelleştirilir. Bu, Word, Excel ve PowerPoint için geçerlidir.

#### <a name="onenote-experience"></a>**OneNote deneyimi**

OneNote win32 istemcisi ve UWP (Evrensel) Uygulaması, site taşıma işlemi tamamlandıktan sonra not defterlerini otomatik olarak algılar ve yeni site konumuna sorunsuz bir şekilde eşitler. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez. Kullanıcıya görünen tek gösterge, site taşıma işlemi devam ederken not defteri eşitlemesinin başarısız olmasıdır. Bu deneyim şu OneNote istemci sürümlerinde kullanılabilir: -OneNote win32 – Sürüm 16.0.8326.2096 (ve üzeri) -OneNote UWP – Sürüm 16.0.8431.1006 (ve üzeri) -OneNote Mobil Uygulaması – Sürüm 16.0.8431.1011 (ve üzeri)

#### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>**Teams (Microsoft 365 grup bağlı siteleri için geçerlidir)**

SharePoint sitesi _Coğrafya_ taşıma işlemi tamamlandığında, kullanıcılar Teams uygulamasında Microsoft 365 grup sitesi dosyalarına erişebilir. Ayrıca, _Coğrafya_ taşımadan önce Teams sohbeti aracılığıyla sitelerinden paylaşılan dosyalar taşıma tamamlandıktan sonra çalışmaya devam eder.
SharePoint sitesi _Coğrafya_ taşıma özelliği, Özel Kanalların bir _Coğrafyadan_ diğerine taşınmasını desteklemez. Özel kanallar özgün _Coğrafya'da_ kalır.

#### <a name="sharepoint-mobile-app-iosandroid"></a>**SharePoint Mobile Uygulaması (iOS/Android)**
SharePoint Mobil Uygulaması _Coğrafya_ arası uyumludur ve sitenin yeni _Coğrafya_ konumunu algılayabilir.

#### <a name="sharepoint-workflows"></a>**SharePoint iş akışları**
Site taşındıktan sonra SharePoint 2013 iş akışlarının yeniden yayımlanması gerekir. SharePoint 2010 iş akışları normal çalışmaya devam etmelidir.

#### <a name="apps"></a>**Apps**
Bir siteyi uygulamalarla taşıyorsanız, uygulamayı sitenin yeni _Coğrafya_ konumuna yeniden doğrulamalısınız çünkü uygulama ve bağlantıları hedef _Coğrafya_ konumunda kullanılamayabilir.

#### <a name="power-automate"></a>**Power Automate**
Çoğu durumda, Power Automate Akışları SharePoint sitesi _Coğrafya_ taşıma işlemi sonrasında çalışmaya devam eder. Taşıma tamamlandıktan sonra bunları test etmenizi öneririz.

#### <a name="power-apps"></a>**Power Apps**

Power Apps'in hedef konumda yeniden oluşturulması gerekir.

#### <a name="data-movement-between-geo-locations"></a>**Coğrafi konumlar arasında veri taşıma**

SharePoint içeriği için Azure Blob Depolama kullanırken, sitelerle ve dosyalarıyla ilişkili meta veriler SharePoint'in içinde depolanır. Site kaynak _Coğrafya_ konumundan hedef _Coğrafya_ konumuna taşındıktan sonra, hizmet ilişkili Blob Depolama alanını da taşır. Blob Depolama yaklaşık 40 gün içinde tamamlar. Bu, kullanıcıların verilerle etkileşimini etkilemez.

[Get-SPOCrossGeoMoveReport](/powershell/module/sharepoint-online/get-spocrossgeomovereport) cmdlet'ini kullanarak Blob Depolama taşıma durumunu denetleyebilirsiniz.
****

### <a name="enabling-sharepoint-multi-geo-in-your-_satellite-geography_-location"></a>**_Uydu Coğrafyası_ konumunuzdaki SharePoint Multi-Geo etkinleştirme**

Bu makale, SharePoint Multi-Geo özellikleri 27 Mart 2019'da genel kullanıma **sunulmadan önce** Multi-Geo _Uydu Coğrafya_ konumu oluşturan ve _Uydu Coğrafya_ konumlarında SharePoint Multi-Geo etkinleştirmemiş Olan Genel veya SharePoint yöneticilerine yöneliktir.

>[!NOTE]
>**27 Mart 2019'un ardından** yeni bir _Coğrafya_ konumu eklediyseniz, yeni _Coğrafya_ konumunuz OneDrive ve SharePoint Multi-Geo için zaten etkinleştirileceği için bu yönergeleri gerçekleştirmeniz gerekmez.

Bu yönergeler, Multi-Geo uydu kullanıcılarınızın O365'teki hem OneDrive hem de SharePoint Multi-Geo özelliklerinden yararlanabilmesi için _SharePoint'i Uydu Coğrafyası_ konumunuzda etkinleştirmenize olanak tanır.

>[!IMPORTANT]
>Bunun tek bir etkinleştirme yöntemi olduğunu lütfen unutmayın. SPO modunu ayarladıktan sonra, destekle yükseltme olmadan _Kiracınızı_ yalnızca OneDrive Multi-Geo moduna geri döndüremezsiniz.

#### <a name="to-set-a-_geography_-location-into-spo-mode"></a>**_Coğrafya_ konumunu SPO Moduna ayarlamak için**

_Coğrafya_ konumunu SPO moduna ayarlamak için SPO Modunda ayarlamak istediğiniz _Coğrafya_ konumuna bağlanın:

1. SharePoint Online Yönetim Kabuğunuzu açma
2. Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Kimlik bilgisi $credential
3. Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience.](../media/Set-SPO-MultiGeo.jpg)
4. Bu işlem genellikle yaklaşık bir saat sürerken biz hizmette çeşitli geri yayımlama işlemleri gerçekleştirir ve _Kiracınızı_ yeniden damgalarız. En az 1 saat sonra lütfen Get-SPOMultiGeoExperience gerçekleştirin.  Bu size bu _Coğrafya_ konumunun SPO modunda olup olmadığını gösterir.</br></br>
![Set-SPOMultiGeoExperience görüntüsü.](../media/Get-SPO-MultiGeo.jpg)

>[!Note]
>Hizmetteki belirli önbellekler 24 saatte bir güncelleştirilir, bu nedenle _Uydu Coğrafyanız_ aralıklı olarak ODB modundaymış gibi davranabilir. Bu herhangi bir teknik soruna neden olmaz.

## <a name="migration"></a>Geçiş

SharePoint Online taşındığında, aşağıdaki hizmetlere ilişkin veriler de taşınır:
  
- OneDrive İş
- Microsoft 365 Video hizmetleri
- Tarayıcıda Office
- Microsoft 365 Kurumsal Uygulamaları
- Microsoft 365 için Visio Pro

SharePoint Online verilerinizi taşımayı tamamladıktan sonra aşağıdaki etkilerden bazılarını görebilirsiniz.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Video Hizmetleri

- Video için veri taşıma işlemi, SharePoint Online'daki içeriğinizin geri kalanındaki taşıma işlemlerinden daha uzun sürer.
- SharePoint Online içeriği taşındıktan sonra, videoların oynatılamadığı bir zaman dilimi olacaktır.
- Koda dönüştürülmüş kopyaları önceki veri merkezinden kaldırıyor ve yeni veri merkezinde yeniden koda aktarıyoruz.

### <a name="search"></a>Arama

SharePoint Online verilerinizi taşırken, arama dizininizi ve arama ayarlarınızı yeni bir konuma geçiririz. SharePoint Online verilerinizin taşınmasını **tamamlayana** kadar kullanıcılarınıza özgün konumdaki dizinden hizmet etmeye devam edeceğiz. SharePoint Online verilerinizi taşımayı tamamladıktan sonra yeni konumda arama otomatik olarak içeriğinizde gezinmeye başlar. Bu noktadan itibaren, geçirilen dizinden kullanıcılarınıza hizmet ederiz. Geçiş sonrasında içeriğinizde yapılan değişiklikler, gezinme tarafından alınana kadar geçirilen dizine dahil değildir. Çoğu müşteri, SharePoint Online verilerini taşımayı tamamladıktan hemen sonra sonuçların daha az yeni olduğunu fark etmez, ancak bazı müşteriler ilk 24-48 saat içinde daha az yenilikle karşılaşabilir.
  
Aşağıdaki arama özellikleri etkilenir:
  
- Arama sonuçları ve Arama Web Bölümleri: Sonuçlar, gezinme onları alana kadar geçiş sonrasında gerçekleşen değişiklikleri içermez.
- Delve: Delve, gezinme onları alana kadar geçiş sonrasında gerçekleşen değişiklikleri içermez.
- Site için popülerlik ve Arama Raporları: Yeni konumdaki Excel raporlarına ait sayımlar yalnızca SharePoint Online verilerinizi taşımayı tamamladıktan sonra çalıştırılan kullanım raporlarından geçirilen sayıları ve sayıları içerir. Ara dönemdeki sayımlar kaybolur ve kurtarılamaz. Bu süre genellikle birkaç gündür. Bazı müşteriler daha kısa veya daha uzun kayıplar yaşayabilir.
- Video Portalı: Video Portalı'nın sayılarını ve istatistiklerini görüntüleme, Excel Raporları istatistiklerine bağlıdır, bu nedenle Video Portalı'nın görüntüleme sayıları ve istatistikleri Excel raporlarıyla aynı süre boyunca kaybolur.
- eBulma: Geçiş sırasında değiştirilen öğeler, gezinme değişiklikleri alana kadar gösterilmez.
- Veri Kaybı Koruması (DLP): Gezinme değişiklikleri alana kadar değişen öğelerde ilkeler uygulanmaz.

Geçişin bir parçası olarak _Birincil Sağlanan Coğrafya_ değişir ve tüm yeni içerik yeni _Birincil Sağlanan Coğrafya'da_ bekleyen konumda depolanır. Mevcut içerik, yönetim merkezindeki SharePoint Online veri konumunda yapılan ilk değişiklikten sonra 90 güne kadar arka planda sizi etkilemeden taşınır.

## <a name="how-can-i-determine-customer-data-location"></a>Müşteri verilerinin konumunu nasıl belirleyebilirim?

Gerçek veri konumunu _Kiracı_ Yönetici Merkezi'nde bulabilirsiniz.  _Kiracı_ yöneticisi olarak, Yönetici->Ayarları->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek, işlenen veriler için gerçek veri konumunu bulabilirsiniz. Oluşturulmuş bir _Kiracınız_ yoksa, M365 deneme sürümüne kaydolırken bir _Kiracı_ oluşturabilirsiniz.
