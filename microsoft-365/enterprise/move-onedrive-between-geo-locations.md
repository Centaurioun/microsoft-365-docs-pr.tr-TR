---
title: OneDrive sitesini farklı bir coğrafi konuma taşıma
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: OneDrive sitesini farklı bir coğrafi konuma taşıma hakkında, site taşımalarını zamanlama ve beklentileri kullanıcılara iletme gibi bilgileri bulun.
ms.openlocfilehash: bafe97fd1dc049b1a9fbb0bdcc2d9d1660baead4
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536554"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>OneDrive sitesini farklı bir coğrafi konuma taşıma

OneDrive coğrafi taşıma ile kullanıcının OneDrive'sını farklı bir coğrafi konuma taşıyabilirsiniz. OneDrive coğrafi taşıma işlemi SharePoint Online yöneticisi veya Microsoft 365 genel yöneticisi tarafından gerçekleştirilir. OneDrive coğrafi taşımayı başlatmadan önce, OneDrive'ı taşınan kullanıcıya bildirmeyi unutmayın ve taşıma süresi boyunca tüm dosyaları kapatmasını öneririz. (Taşıma sırasında kullanıcının Office istemcisini kullanarak açık bir belgesi varsa, taşıma tamamlandıktan sonra belgenin yeni konuma kaydedilmesi gerekir.) taşıma, isterseniz gelecek bir süre için zamanlanabilir.

OneDrive hizmeti, içeriği depolamak için Azure Blob Depolama kullanır. Kullanıcının OneDrive'ı ile ilişkili Depolama blobu, hedef OneDrive'ın kullanılabilmesinden sonra 40 gün içinde kaynaktan hedef coğrafi konuma taşınır. Hedef OneDrive kullanılabilir olduğunda kullanıcının OneDrive erişimi geri yüklenir.

OneDrive coğrafi taşıma penceresi (yaklaşık 2-6 saat) sırasında kullanıcının OneDrive'ı salt okunur olarak ayarlanır. Kullanıcı dosyalarına OneDrive eşitleme uygulaması veya SharePoint Online'daki OneDrive sitesi aracılığıyla erişmeye devam edebilir. OneDrive coğrafi taşıma işlemi tamamlandıktan sonra kullanıcı, Microsoft 365 uygulama başlatıcısında OneDrive'a gittiği zaman hedef coğrafi konumdaki OneDrive'larına otomatik olarak bağlanır. Eşitleme uygulaması otomatik olarak yeni konumdan eşitlemeye başlar.

Bu makaledeki yordamlar [Microsoft Office SharePoint Online PowerShell Modülü](https://www.microsoft.com/download/details.aspx?id=35588) gerektirir.

## <a name="communicating-to-your-users"></a>Kullanıcılarınıza iletişim kurma

OneDrive sitelerini coğrafi konumlar arasında taşırken kullanıcılarınıza ne bekleyebileceğinizi bildirmek önemlidir. Bu, kullanıcı karışıklığını ve yardım masanıza yapılan aramaları azaltmaya yardımcı olabilir. Taşımadan önce kullanıcılarınızı Email ve aşağıdaki bilgileri onlara bildirin:

- Taşıma işleminin ne zaman başlaması ve ne kadar sürmesi beklenir?
- OneDrive'ın taşındığı coğrafi konum ve yeni konuma erişmek için URL
- Taşıma sırasında düzenleme yapmamaları ve dosyalarını kapatmaları gerekir.
- Taşımanın sonucunda dosya izinleri ve paylaşım değişmez.
- [Çok coğrafi bir ortamda kullanıcı deneyiminden neler beklenmeli](multi-geo-user-experience.md)?

Taşıma işlemi başarıyla tamamlandığında kullanıcılarınıza OneDrive'da çalışmaya devam etmelerini bildiren bir e-posta gönderdiğinizden emin olun.

## <a name="scheduling-onedrive-site-moves"></a>OneDrive sitesi taşımalarını zamanlama

OneDrive sitesi taşımalarını önceden zamanlayabilirsiniz (bu makalenin ilerleyen bölümlerinde açıklanmaktadır). İş akışlarınızı ve iletişim stratejilerinizi doğrulamak için az sayıda kullanıcıyla başlamanızı öneririz. İşlemi rahatça tamamladıktan sonra, taşımaları aşağıdaki gibi zamanlayabilirsiniz:

- Bir kerede en fazla 4.000 taşıma zamanlayabilirsiniz.
- Taşımalar başladığında, kuyrukta ve belirli bir zamanda bekleyen en fazla 4.000 taşıma ile daha fazla zamanlayabilirsiniz.
- Taşınabilecek OneDrive boyutu üst sınırı 1 terabayttır (1 TB).

## <a name="moving-a-onedrive-site"></a>OneDrive sitesini taşıma

OneDrive coğrafi taşıma gerçekleştirmek için, kiracı yöneticisinin önce kullanıcının Tercih Edilen Veri Konumu'na (PDL) uygun coğrafi konumu ayarlaması gerekir. PDL ayarlandıktan sonra, OneDrive coğrafi taşıma işlemini başlatmadan önce PDL güncelleştirmesinin coğrafi konumlar arasında eşitlenmesi için en az 24 saat bekleyin.

Coğrafi taşıma cmdlet'lerini kullanırken, aşağıdaki söz dizimini kullanarak kullanıcının geçerli OneDrive coğrafi konumunda SPO Hizmeti'ne bağlanın:

```powershell
Connect-SPOService -url https://<tenantName>-admin.sharepoint.com
```

Örneğin: 'Matt@contosoenergy.onmicrosoft.com' kullanıcısının OneDrive'ını taşımak için, kullanıcının OneDrive'ı EUR coğrafi konumunda olduğundan EUR SharePoint Yönetici merkezine bağlanın:

```powershell
Connect-SPOService -url https://contosoenergyeur-admin.sharepoint.com
```

![Connect-sposervice cmdlet'ini gösteren PowerShell penceresinin ekran görüntüsü.](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>Ortamı doğrulama

OneDrive coğrafi taşımayı başlatmadan önce ortamı doğrulamanızı öneririz.

Tüm coğrafi konumların uyumlu olduğundan emin olmak için şunu çalıştırın:

```powershell
Get-SPOGeoMoveCrossCompatibilityStatus
```

Bu, tüm coğrafi konumlarınızı ve ortamın hedef coğrafi konumla uyumlu olup olmadığını görüntüler. Coğrafi konum uyumsuzsa bu, o konumda bir güncelleştirmenin devam ettiğini gösterir. Birkaç gün içinde yeniden deneyin.

OneDrive bir alt site içeriyorsa, örneğin, bu site taşınamaz. OneDrive'ın taşınıp taşınamadığını doğrulamak için -ValidationOnly parametresiyle Start-SPOUserAndContentMove cmdlet'ini kullanabilirsiniz:

```powershell
Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly
```

Bu, OneDrive taşınmaya hazırsa Başarılı veya taşımayı engelleyecek yasal bir ayrı tutma veya alt site varsa Başarısız döndürür. OneDrive'ın taşınmaya hazır olduğunu doğruladıktan sonra taşıma işlemini başlatabilirsiniz.

## <a name="start-a-onedrive-geo-move"></a>OneDrive coğrafi taşımayı başlatma

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

![Start-SPOUserAndContentMove cmdlet'ini gösteren PowerShell penceresinin ekran görüntüsü.](../media/move-onedrive-between-geo-locations-image2.png)

Coğrafi taşımayı daha sonra zamanlamak için aşağıdaki parametrelerden birini kullanın:

- _PreferredMoveBeginDate_ – Taşıma büyük olasılıkla belirtilen zamanda başlayacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.
- _PreferredMoveEndDate_ – Taşıma işlemi büyük olasılıkla belirtilen zamana kadar en iyi çaba temelinde tamamlanacaktır. Saat Eşgüdümlü Evrensel Saat (UTC) içinde belirtilmelidir.

## <a name="cancel-a-onedrive-geo-move"></a>OneDrive coğrafi taşımayı iptal etme

Taşıma işlemi devam etmemesi veya cmdlet'ini kullanarak tamamlanması koşuluyla kullanıcının OneDrive'ının coğrafi taşımasını durdurabilirsiniz:

```powershell
Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>
```

Burada _UserPrincipalName_ , OneDrive taşımasını durdurmak istediğiniz kullanıcının UPN'sini oluşturur.

## <a name="determining-current-status"></a>Geçerli durumu belirleme

Get-SPOUserAndContentMoveState cmdlet'ini kullanarak bağlandığınız coğrafi bölgede oneDrive coğrafi taşımasının durumunu de kontrol edebilirsiniz.

Taşıma durumları aşağıdaki tabloda açıklanmıştır.

|Durum|Açıklama|
|---|---|
|Başlamadı|Taşıma başlatılmadı|
|InProgress (*n*/4)|Taşıma işlemi aşağıdaki durumlardan birinde devam ediyor: <ul><li>Doğrulama (1/4)</li><li>Yedekleme (2/4)</li><li>Geri Yükleme (3/4)</li><li>Temizleme (4/4)</li></ul>|
|Başarı|Taşıma işlemi başarıyla tamamlandı.|
|Başarısız|Taşıma başarısız oldu.|

Belirli bir kullanıcının taşıma durumunu bulmak için *UserPrincipalName* parametresini kullanın:

```powershell
Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>
```

Bağlandığınız coğrafi konumdaki veya coğrafi konumdaki tüm taşımaların durumunu bulmak için *MoveState* parametresini şu değerlerden biriyle kullanın: NotStarted, InProgress, Success, Failed, All.

```powershell
Get-SPOUserAndContentMoveState -MoveState <value>
```

Taşıma *durumunun daha* ayrıntılı açıklamaları için Ayrıntılı parametresini de ekleyebilirsiniz.

## <a name="user-experience"></a>Kullanıcı Deneyimi

OneDrive kullanıcıları, OneDrive'ları farklı bir coğrafi konuma taşınırsa en düşük kesintiyi fark etmelidir. Taşıma sırasında kısa bir salt okunur durum dışında, taşıma tamamlandıktan sonra mevcut bağlantılar ve izinler beklendiği gibi çalışmaya devam eder.

### <a name="users-onedrive"></a>Kullanıcının OneDrive'ı

Taşıma işlemi devam ederken kullanıcının OneDrive'ı salt okunur olarak ayarlanır. Taşıma tamamlandıktan sonra, kullanıcı OneDrive'a Microsoft 365 uygulama başlatıcısına veya bir web tarayıcısına gittiği zaman yeni coğrafi konumda onedrive'larına yönlendirilir.

### <a name="permissions-on-onedrive-content"></a>OneDrive içeriğindeki izinler

OneDrive içeriğine izinleri olan kullanıcılar, taşıma sırasında ve tamamlandıktan sonra içeriğe erişmeye devam eder.

### <a name="onedrive-sync-app"></a>OneDrive eşitleme uygulaması

OneDrive eşitleme uygulaması, OneDrive coğrafi taşıma işlemi tamamlandıktan sonra eşitlemeyi otomatik olarak algılar ve yeni OneDrive konumuna sorunsuz bir şekilde aktarır. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez.  (Eşitleme uygulamasının sürüm 17.3.6943.0625 veya üzeri gereklidir.)

OneDrive coğrafi taşıma işlemi devam ederken bir kullanıcı dosyayı güncelleştirirse, eşitleme uygulaması taşıma işlemi devam ederken dosya yüklemelerinin beklemede olduğunu bildirir.

### <a name="sharing-links"></a>Paylaşım bağlantıları

OneDrive coğrafi taşıma tamamlandıktan sonra, taşınan dosyaların mevcut paylaşılan bağlantıları otomatik olarak yeni coğrafi konuma yönlendirilir.

### <a name="onenote-experience"></a>OneNote Deneyimi

OneDrive coğrafi taşıma tamamlandıktan sonra OneNote win32 istemcisi ve UWP (Evrensel) Uygulaması not defterlerini otomatik olarak algılar ve yeni OneDrive konumuyla sorunsuz bir şekilde eşitler. Kullanıcının yeniden oturum açması veya başka bir işlem gerçekleştirmesi gerekmez. Kullanıcıya görünen tek gösterge, OneDrive coğrafi taşıma işlemi devam ederken not defteri eşitlemesinin başarısız olmasıdır. Bu deneyim aşağıdaki OneNote istemci sürümlerinde kullanılabilir:

- OneNote win32 – Sürüm 16.0.8326.2096 (ve üzeri)
- OneNote UWP – Sürüm 16.0.8431.1006 (ve üzeri)
- OneNote Mobil Uygulaması – Sürüm 16.0.8431.1011 (ve üzeri)

### <a name="teams-app"></a>Teams uygulaması

OneDrive coğrafi taşıma tamamlandıktan sonra kullanıcılar Teams uygulamasından OneDrive dosyalarına erişebilir. Ayrıca, coğrafi taşıma öncesinde OneDrive'larından Teams sohbeti aracılığıyla paylaşılan dosyalar taşıma tamamlandıktan sonra çalışmaya devam eder.

### <a name="onedrive-mobile-app-ios"></a>OneDrive Mobil Uygulaması (iOS)

OneDrive coğrafi olarak taşıma tamamlandıktan sonra, kullanıcının yeni OneDrive konumuyla eşitlemek için iOS Mobil Uygulamasında oturumu kapatıp yeniden oturum açması gerekir.

### <a name="existing-followed-groups-and-sites"></a>Mevcut takip edilen gruplar ve siteler

Takip edilen siteler ve gruplar, coğrafi konumlarından bağımsız olarak kullanıcının OneDrive'ında gösterilir. Başka bir coğrafi konumda barındırılan siteler ve gruplar ayrı bir sekmede açılır.

### <a name="delve-geo-url-updates"></a>Delve Geo URL güncelleştirmeleri

Kullanıcılar, PDL'lerine karşılık gelen Delve coğrafi konumuna yalnızca OneDrive'ları yeni coğrafi bölgeye taşındıktan sonra gönderilir.
