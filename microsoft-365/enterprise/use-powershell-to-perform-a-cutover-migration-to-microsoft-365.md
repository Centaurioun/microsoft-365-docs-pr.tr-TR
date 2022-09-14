---
title: Microsoft 365'e geçiş geçişi gerçekleştirmek için PowerShell'i kullanma
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Microsoft 365'e tam geçiş gerçekleştirerek PowerShell'i kullanarak kaynak e-posta sistemindeki içerikleri aynı anda taşımayı öğrenin.
ms.openlocfilehash: 726834521f369b4720903709835bc668794306e3
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67669771"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Microsoft 365'e geçiş geçişi gerçekleştirmek için PowerShell'i kullanma

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Tam geçiş kullanarak kullanıcı posta kutularının içeriğini bir kaynak e-posta sisteminden Microsoft 365'e tek seferde geçirebilirsiniz. Bu makalede, Exchange Online PowerShell kullanarak tam e-posta geçişi için görevlerde size yol gösterilir.

[Microsoft 365'e tam e-posta geçişi hakkında bilmeniz gerekenler](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration) konusunu gözden geçirerek geçiş işlemine genel bir bakış elde edebilirsiniz. Bu makalenin içeriğini rahatça anladığınızda, posta kutularını bir e-posta sisteminden diğerine geçirmeye başlamak için bunu kullanın.

> [!NOTE]
> Tam geçiş gerçekleştirmek için <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezini</a> de kullanabilirsiniz. Bkz [. E-postanın Microsoft 365'e tam geçişini gerçekleştirme](/Exchange/mailbox-migration/cutover-migration-to-office-365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

Bu görevi tamamlamak için tahmini süre: Geçiş toplu işlemini oluşturmak için 2-5 dakika. Geçiş toplu işlemi başlatıldıktan sonra, geçiş süresi toplu işlemdeki posta kutularının sayısına, her posta kutusunun boyutuna ve kullanılabilir ağ kapasitenize göre değişir. Posta kutularının Microsoft 365'e geçirilmesinin ne kadar sürdüğünü etkileyen diğer faktörler hakkında bilgi için bkz [. Geçiş Performansı](/Exchange/mailbox-migration/office-365-migration-best-practices).

Bu yordamı veya yordamları gerçekleştirebilmeniz için, önce izinlerin atanması gerekir. Hangi izinlere ihtiyacınız olduğunu görmek için [, Alıcılar İzinleri](/exchange/recipients-permissions-exchange-2013-help) konusunun bir tablosundaki "Geçiş" girdisine bakın.

Exchange Online PowerShell cmdlet'lerini kullanmak için oturum açmanız ve cmdlet'leri yerel Windows PowerShell oturumunuza aktarmanız gerekir. Yönergeler için bkz. [Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

Geçiş komutlarının tam listesi için bkz [. Taşıma ve geçiş cmdlet'leri](/powershell/exchange/).

## <a name="migration-steps"></a>Geçiş adımları

### <a name="step-1-prepare-for-a-cutover-migration"></a>1. Adım: Tam geçişe hazırlanma
<a name="BK_Step1"> </a>

- **Şirket içi Exchange kuruluşunuzu Microsoft 365 kuruluşunuzun kabul edilen etki alanı olarak ekleyin.** Geçiş hizmeti, yeni Microsoft 365 posta kutuları için Microsoft Online Services kullanıcı kimliğini ve e-posta adresini oluşturmak için şirket içi posta kutularınızın SMTP adresini kullanır. Exchange etki alanınız kabul edilen bir etki alanı veya Microsoft 365 kuruluşunuzun birincil etki alanı değilse geçiş başarısız olur. Daha fazla bilgi için bkz. [Etki alanınızı doğrulama](../admin/setup/add-domain.md).

- **Outlook'u şirket içi Exchange sunucunuzda her yerde yapılandırın.** E-posta geçiş hizmeti, şirket içi Exchange sunucunuza bağlanmak için HTTP üzerinden RPC veya Her Yerden Outlook kullanır. Exchange 2010, Exchange 2007 ve Exchange 2003 için Her Yerden Outlook'u ayarlama hakkında bilgi için aşağıdakilere bakın:

  - [Exchange 2010: Her Yerden Outlook'u Etkinleştirme](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Her Yerden Outlook'u Etkinleştirme](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: HTTP üzerinden RPC için Dağıtım Senaryoları](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Exchange 2003 ile Outlook'u Her Yerde Yapılandırma](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Outlook Anywhere yapılandırmanız, güvenilen bir sertifika yetkilisi (CA) tarafından verilen bir sertifikayla yapılandırılmalıdır. Otomatik olarak imzalanan bir sertifikayla yapılandırılamaz. Daha fazla bilgi için bkz. [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

- **Her Yerden Outlook'u kullanarak Exchange kuruluşunuza bağlanabildiğinizi doğrulayın.** Bağlantı ayarlarınızı test etmek için şu yöntemlerden birini deneyin:

  - Şirket içi Exchange posta kutunuza bağlanmak için kurumsal ağınızın dışından Microsoft Outlook'u kullanın.

  - Bağlantı ayarlarınızı test etmek için Microsoft [Exchange Uzak Bağlantı Çözümleyicisi'ni](https://www.testexchangeconnectivity.com/) kullanın. Her Yerden Outlook (HTTP üzerinden RPC) veya Outlook Otomatik Bulma testlerini kullanın.

  - Exchange Online PowerShell'de aşağıdaki komutları çalıştırın.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Şirket içi kullanıcı hesabına Exchange kuruluşunuzdaki posta kutularına erişmek için gerekli izinleri atayın.** Şirket içi Exchange kuruluşunuza bağlanmak için kullandığınız şirket içi kullanıcı hesabının (geçiş yöneticisi olarak da adlandırılır) Microsoft 365'e geçirmek istediğiniz şirket içi posta kutularına erişmek için gerekli izinlere sahip olması gerekir. Bu kullanıcı hesabı, şirket içi kuruluşunuza geçiş uç noktası oluşturmak için kullanılır.

    Aşağıdaki listede, tam geçiş kullanarak posta kutularını geçirmek için gereken yönetim ayrıcalıkları gösterilmektedir. Üç olası seçenek vardır.

  - Geçiş yöneticisinin şirket içi kuruluştaki Active **Directory'de Domain Admins** grubunun üyesi olması gerekir.

    Veya

  - Geçiş yöneticisine şirket içi her posta kutusu için **FullAccess** izni atanmalıdır.

    Veya

  - Geçiş yöneticisine, kullanıcı posta kutularını depolayan şirket içi posta kutusu veritabanında **Farklı Al** izni atanmalıdır.

- **Birleşik Mesajlaşmayı devre dışı bırakın.** Geçirmekte olduğunuz şirket içi posta kutuları Birleşik Mesajlaşma (UM) için etkinleştirildiyse, bunları geçirmeden önce posta kutularında UM'yi devre dışı bırakmanız gerekir. Geçiş tamamlandıktan sonra posta kutularında UM'yi etkinleştirebilirsiniz.

- **Güvenlik Grupları ve Temsilciler** E-posta geçiş hizmeti şirket içi Active Directory grupların güvenlik grubu olup olmadığını algılayamaz, bu nedenle geçirilen grupları Microsoft 365'te güvenlik grupları olarak sağlayamaz. Microsoft 365 kiracınızda güvenlik gruplarının olmasını istiyorsanız, tam geçişe başlamadan önce Microsoft 365 kiracınızda boş bir posta özellikli güvenlik grubu sağlamalısınız. Buna ek olarak, bu geçiş yöntemi yalnızca posta kutularını, posta kullanıcılarını, posta kişilerini ve posta özelliği etkin grupları taşır. Microsoft 365'e geçirilmeyen kullanıcı gibi başka bir Active Directory nesnesi, geçirilmekte olan bir nesneye yönetici veya temsilci olarak atanırsa, geçirmeden önce nesneden kaldırılmalıdır.

### <a name="step-2-create-a-migration-endpoint"></a>2. Adım: Geçiş uç noktası oluşturma
<a name="BK_Step2"> </a>

E-postayı başarıyla geçirmek için Microsoft 365'in kaynak e-posta sistemine bağlanması ve bu sistemle iletişim kurması gerekir. Bunu yapmak için Microsoft 365 bir geçiş uç noktası kullanır. Tam geçiş için bir Outlook Anywhere geçiş uç noktası oluşturmak için önce [Exchange Online bağlanın](/powershell/exchange/connect-to-exchange-online-powershell).

Geçiş komutlarının tam listesi için bkz [. Taşıma ve geçiş cmdlet'leri](/powershell/exchange/).

Exchange Online PowerShell'de aşağıdaki komutları çalıştırın:

```powershell
$Credentials = Get-Credential
```

Örnek, şirket içi Exchange sunucusuna bağlantı ayarlarını almak ve test etmek için [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet'ini kullanır ve ardından bu bağlantı ayarlarını kullanarak "CutoverEndpoint" adlı geçiş uç noktasını oluşturur.

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> **New-MigrationEndpoint** cmdlet'i **, -TargetDatabase** seçeneği kullanılarak hizmetin kullanacağı bir veritabanı belirtmek için kullanılabilir. Aksi takdirde bir veritabanı, yönetim posta kutusunun bulunduğu Active Directory Federasyon Hizmetleri (AD FS) (AD FS) 2.0 sitesinden rastgele atanır.

#### <a name="verify-it-worked"></a>Çalıştığını doğrulayın

Exchange Online PowerShell'de, "CutoverEndpoint" geçiş uç noktası hakkında bilgi görüntülemek için aşağıdaki komutu çalıştırın:

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>3. Adım: Tam geçiş toplu işlemini oluşturma
<a name="BK_Step3"> </a>

Exchange Online PowerShell'de **New-MigrationBatch** cmdlet'ini kullanarak tam geçiş için bir geçiş toplu işlemi oluşturabilirsiniz. _Otomatik Başlangıç_ parametresini ekleyerek bir geçiş toplu işlemi oluşturabilir ve bunu otomatik olarak başlatabilirsiniz. Alternatif olarak, geçiş toplu işlemini oluşturabilir ve daha sonra **Start-MigrationBatch** cmdlet'ini kullanarak el ile başlatabilirsiniz. Bu örnek, "CutoverBatch" adlı bir geçiş toplu işlemi oluşturur ve önceki adımda oluşturulan geçiş uç noktasını kullanır.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

Bu örnek ayrıca "CutoverBatch" adlı bir geçiş toplu işlemi oluşturur ve önceki adımda oluşturulan geçiş uç noktasını kullanır. _AutoStart_ parametresi dahil edilmediğinden, geçiş toplu işleminin geçiş panosunda veya **Start-MigrationBatch** cmdlet'i kullanılarak el ile başlatılması gerekir. Daha önce belirtildiği gibi, aynı anda yalnızca bir tam geçiş toplu işlemi bulunabilir.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Çalıştığını doğrulayın

Tam geçiş için geçiş toplu işlemini başarıyla oluşturduğunuzu doğrulamak için, yeni geçiş toplu işlemiyle ilgili bilgileri görüntülemek üzere PowerShell Exchange Online de aşağıdaki komutu çalıştırın:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>4. Adım: Tam geçiş toplu işlemini başlatma

Exchange Online PowerShell'de geçiş toplu işlemini başlatmak için aşağıdaki komutu çalıştırın. Bu, "CutoverBatch" adlı bir geçiş toplu işlemi oluşturur.

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Çalıştığını doğrulayın

Geçiş toplu işlemi başarıyla başlatılırsa, geçiş panosundaki durumu Eşitleniyor olarak belirtilir. Exchange Online PowerShell kullanarak geçiş toplu işlemini başarıyla başlattığınızı doğrulamak için aşağıdaki komutu çalıştırın:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>5. Adım: E-postanızı Microsoft 365'e yönlendirme

E-posta sistemleri, e-postaların teslim edileceği yeri belirlemek için MX kaydı olarak adlandırılan bir DNS kaydını kullanır. E-posta geçiş işlemi sırasında, MX kaydınız kaynak e-posta sisteminize işaret ediyor olur. Microsoft 365'e e-posta geçişi tamamlandıktan sonra MX kaydınızı Microsoft 365'e işaret etme zamanı geldi. Bu, e-postanın Microsoft 365 posta kutularınıza teslim edilmiş olmasına yardımcı olur. MX kaydını taşıyarak, hazır olduğunuzda eski e-posta sisteminizi de kapatabilirsiniz.

Birçok DNS sağlayıcısı için, MX kaydınızı değiştirmeye yönelik belirli yönergeler sağlanmıştır. DNS sağlayıcınız bunların arasında değilse veya genel yönergeler hakkında fikir edinmek istiyorsanız, [genel MX kaydı yönergeleri](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-an-mx-record-for-email-outlook-exchange-online) de sağlanmıştır.

Müşterilerinizin ve iş ortaklarınızın e-posta sistemlerinin değişen MX kaydını fark etmesi 72 saat kadar sürebilir. Sonraki göreve geçmeden önce en az 72 saat bekleyin: [6. Adım: Tam geçiş toplu işlemini silin](#step-6-delete-the-cutover-migration-batch).

### <a name="step-6-delete-the-cutover-migration-batch"></a>6. Adım: Tam geçiş toplu işlemini silme

MX kaydını değiştirdikten ve tüm e-postaların Microsoft 365 posta kutularına yönlendirildiğini doğruladıktan sonra, kullanıcılara postalarının Microsoft 365'e gideceğini bildirin. Bundan sonra tam geçiş toplu işlemini silebilirsiniz. Geçiş toplu işlemini silmeden önce aşağıdakileri doğrulayın.

- Tüm kullanıcılar Microsoft 365 posta kutularını kullanıyor. Toplu işlem silindikten sonra, şirket içi Exchange Server posta kutularına gönderilen postalar ilgili Microsoft 365 posta kutularına kopyalanır.

- Microsoft 365 posta kutuları, posta doğrudan gönderilmeye başladıktan sonra en az bir kez eşitlendi. Bunu yapmak için, geçiş toplu işleminin Son Eşitlenen Zaman kutusundaki değerin, postanın doğrudan Microsoft 365 posta kutularına yönlendirilmeye başladığı zamandan daha yeni olduğundan emin olun.

Exchange Online PowerShell'de "CutoverBatch" geçiş toplu işlemini silmek için aşağıdaki komutu çalıştırın:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Bölüm 7: Kullanıcı lisansları atama

 **Lisans atayarak geçirilen hesaplar için Microsoft 365 kullanıcı hesaplarını etkinleştirin.** Lisans atamazsanız, yetkisiz kullanım süresi sona erdiğinde (30 gün) posta kutusu devre dışı bırakılır. Microsoft 365 yönetim merkezi lisans atamak için bkz. [Lisans atama veya atamasını kaldırma](../admin/manage/assign-licenses-to-users.md).

### <a name="step-8-complete-post-migration-tasks"></a>8. Adım: Geçiş sonrası görevleri tamamlama

- **Kullanıcıların posta kutularına kolayca ulaşabilmeleri için bir Otomatik Bulma DNS kaydı oluşturun.** Tüm şirket içi posta kutuları Microsoft 365'e geçirildikten sonra, kullanıcıların Outlook ve mobil istemcilerle yeni Microsoft 365 posta kutularına kolayca bağlanmasını sağlamak üzere Microsoft 365 kuruluşunuz için bir Otomatik Bulma DNS kaydı yapılandırabilirsiniz. Bu yeni Otomatik Bulma DNS kaydının, Microsoft 365 kuruluşunuz için kullandığınız ad alanını kullanması gerekir. Örneğin, bulut tabanlı ad alanınız bulut.contoso.com ise, oluşturmanız gereken Otomatik Bulma DNS kaydı autodiscover.bulut.contoso.com'dur.

    Exchange Server tutarsanız, Outlook istemcisinin doğru posta kutusuna bağlanabilmesi için, geçiş sonrasında Dns CNAME kaydının hem iç hem de dış DNS'de Otomatik Bulma'nın Microsoft 365'e işaret etmesi gerekir.

    > [!NOTE]
    >  Exchange 2007, Exchange 2010 ve Exchange 2013'te de olarak `Null`ayarlamanız `Set-ClientAccessServer AutodiscoverInternalConnectionURI` gerekir.

    Microsoft 365, Outlook ve mobil istemciler için Otomatik Bulma hizmetini uygulamak için bir CNAME kaydı kullanır. Otomatik Bulma CNAME kaydı aşağıdaki bilgileri içermelidir:

  - **Alias:** autodiscover

  - **Target:** autodiscover.outlook.com

    Daha fazla bilgi için bkz. [Etki alanınıza bağlanmak için DNS kayıtları ekleme](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- **Şirket içi Exchange sunucularının yetkisini alın.** Tüm e-postaların doğrudan Microsoft 365 posta kutularına yönlendirildiğini doğruladıktan ve şirket içi e-posta kuruluşunuzun bakımını yapmanıza gerek kalmaz veya çoklu oturum açma (SSO) çözümü uygulamayı planlamazsanız, Exchange'i sunucularınızdan kaldırabilir ve şirket içi Exchange kuruluşunuzu kaldırabilirsiniz.

    Daha fazla bilgi için aşağıdakilere bakın:

  - [Exchange 2010'u Değiştirme veya Kaldırma](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Exchange 2007 Kuruluşunu Kaldırma](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Exchange Server 2003'ü Kaldırma](/previous-versions/tn-archive/bb125110(v=exchg.65))
