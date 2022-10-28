---
title: Microsoft Purview Bilgi Koruması tarayıcısını kullanmaya başlama
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Microsoft Purview Bilgi Koruması tarayıcısını yükleme ve dağıtma önkoşullarını listeler.
ms.openlocfilehash: ef1b3397814915a010d45b2131caaac6b0b3643e
ms.sourcegitcommit: 3d7dd25abcbf923b45eae84ff4d9d2bb95ef4ca4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68777878"
---
# <a name="get-started-with-the-information-protection-scanner"></a>Bilgi koruma tarayıcısını kullanmaya başlama

Tarayıcıyı Microsoft Purview Bilgi Koruması yüklemeden önce sisteminizin temel [Azure Information Protection gereksinimlerine](/azure/information-protection/requirements) uygun olduğundan emin olun.

Ayrıca tarayıcı için aşağıdaki gereksinimlere özeldir:

- [Windows Server gereksinimleri](#windows-server-requirements)
- [Hizmet hesabı gereksinimleri](#service-account-requirements)
- [SQL server gereksinimleri](#sql-server-requirements)
- [Azure Information Protection istemci gereksinimleri](#azure-information-protection-client-requirements)
- [Etiket yapılandırma gereksinimleri](#label-configuration-requirements)
- [SharePoint gereksinimleri](#sharepoint-requirements)
- [Microsoft Office gereksinimleri](#microsoft-office-requirements)
- [Dosya yolu gereksinimleri](#file-path-requirements)

Kuruluş ilkeleriniz tarafından yasaklandığından tarayıcı için listelenen tüm gereksinimleri karşılayamazsanız [alternatif yapılandırmalar](#deploying-the-scanner-with-alternative-configurations) bölümüne bakın.

Tarayıcıyı üretim ortamında dağıtırken veya birden çok tarayıcının performansını test ederken bkz. [SQL Server için depolama gereksinimleri ve kapasite planlaması](#storage-requirements-and-capacity-planning-for-sql-server).

Tarayıcınızı yüklemeye ve dağıtmaya başlamaya hazır olduğunuzda [, Bilgi koruma tarayıcısını yapılandırma ve yükleme](deploy-scanner-configure-install.md) ile devam edin.

## <a name="windows-server-requirements"></a>Windows Server gereksinimleri

Tarayıcıyı çalıştırmak için aşağıdaki sistem belirtimlerine sahip bir Windows Server bilgisayarınız olmalıdır:

|Belirtimi  |Ayrıntılar  |
|---------|---------|
|**Işlemci**     |4 çekirdekli işlemciler         |
|**Ram**     |8GB         |
|**Disk alanı**     |Geçici dosyalar için 10 GB boş alan (ortalama). </br></br>Tarayıcı, taramış olduğu her dosya için çekirdek başına dört dosya olmak üzere geçici dosyalar oluşturmak için yeterli disk alanı gerektirir. </br></br>Önerilen 10 GB disk alanı, 4 çekirdekli işlemcinin her biri 625 MB dosya boyutuna sahip 16 dosyayı taramasını sağlar.
|**İşletim sistemi**     |64 bit sürümleri: <br><br>- Windows Server 2019 </br>- Windows Server 2016 </br>- Windows Server 2012 R2 </br></br>**Not**: Üretim dışı bir ortamda test veya değerlendirme amacıyla, [Azure Information Protection istemcisi tarafından desteklenen](/azure/information-protection/requirements#client-devices) herhangi bir Windows işletim sistemini de kullanabilirsiniz.
|**Ağ bağlantısı**     | Tarayıcı bilgisayarınız, taranacak veri depolarına hızlı ve güvenilir bir ağ bağlantısı olan bir fiziksel veya sanal bilgisayar olabilir. </br></br> Kuruluş ilkeleriniz nedeniyle İnternet bağlantısı mümkün değilse bkz. [Tarayıcıyı alternatif yapılandırmalarla dağıtma](#deploying-the-scanner-with-alternative-configurations). </br></br>Aksi takdirde, bu bilgisayarın HTTPS üzerinden aşağıdaki URL'lere izin veren İnternet bağlantısına sahip olduğundan emin olun (bağlantı noktası 443):</br><br />-  \*.aadrm.com <br />-  \*.azurerms.com<br />-  \*.informationprotection.azure.com <br /> - informationprotection.hosting.portal.azure.net <br /> - \*.aria.microsoft.com <br />-  \*.protection.outlook.com |
|**NFS paylaşımları** |NFS paylaşımlarında taramaları desteklemek için, NFS hizmetlerinin tarayıcı makinesine dağıtılması gerekir. <br><br>Makinenizde **Windows Özellikleri (Windows özelliklerini açma veya kapatma)** ayarları iletişim kutusuna gidin ve şu öğeleri seçin: NFS **Yönetim Araçları** **hizmetleri ve NFS** >  **İstemcisi**. |
| **Microsoft Office iFilter** |Tarayıcınız bir Windows sunucu makinesine yüklendiğinde, hassas bilgi türleri için .zip dosyalarını taramak için Microsoft Office iFilter'ı da yüklemeniz gerekir. <br><br>Daha fazla bilgi için [bkz. Microsoft indirme sitesi](https://www.microsoft.com/en-us/download/details.aspx?id=17062).|

## <a name="service-account-requirements"></a>Hizmet hesabı gereksinimleri

Tarayıcı hizmetini Windows Server bilgisayarında çalıştırmak ve tarayıcının ilkesini Azure AD ve indirmek için kimlik doğrulaması yapmak için bir hizmet hesabınız olmalıdır.

Hizmet hesabınızın bir Active Directory hesabı olması ve Azure AD ile eşitlenmiş olması gerekir.

Kuruluş ilkeleriniz nedeniyle bu hesabı eşitleyemiyorsanız bkz. [Tarayıcıyı alternatif yapılandırmalarla dağıtma](#deploying-the-scanner-with-alternative-configurations).

Bu hizmet hesabı aşağıdaki gereksinimlere sahiptir:

|Gereksinim  |Ayrıntılar  |
|---------|---------|
|**Yerel olarak kullanıcı hakkı ataması oturum açma**     |Tarayıcıyı yüklemek ve yapılandırmak için gereklidir, ancak taramaları çalıştırmak için gerekli değildir.  </br></br>Tarayıcının dosyaları bulabildiğini, sınıflandırabildiğini ve koruyabildiğini onayladıktan sonra, bunu doğrudan hizmet hesabından kaldırabilirsiniz.  </br></br>Kuruluş ilkeleriniz nedeniyle kısa bir süre için bile bu hakkı vermek mümkün değilse, bkz. [Tarayıcıyı alternatif yapılandırmalarla dağıtma](#deploying-the-scanner-with-alternative-configurations).         |
|Hizmet kullanıcısı hakkı **ataması olarak oturum açın**.     |  Bu hak, tarayıcı yüklemesi sırasında hizmet hesabına otomatik olarak verilir ve tarayıcının yüklenmesi, yapılandırılması ve çalıştırılması için bu hak gereklidir.        |
|**Veri depolarına yönelik izinler**     |- **Dosya paylaşımları veya yerel dosyalar**: Dosyaları taramak ve yapılandırıldığı gibi sınıflandırma ve koruma uygulamak için **Okuma**, **Yazma** ve **Değiştirme** izinleri verin.  <br /><br />- **SharePoint**: Dosyaları taramak ve ardından Azure Information Protection ilkesindeki koşulları karşılayan dosyalara sınıflandırma ve koruma uygulamak için **Tam Denetim** izinleri vermelisiniz.  <br /><br />- **Bulma modu**: Tarayıcıyı yalnızca bulma modunda çalıştırmak için **Okuma** izni yeterlidir.         |
|**Korumayı yeniden oluşturan veya kaldıran etiketler için**     | Tarayıcının şifrelenmiş dosyalara her zaman erişebildiğinden emin olmak için bu hesabı Azure Information Protection için [süper kullanıcı](/azure/information-protection/configure-super-users) yapın ve süper kullanıcı özelliğinin etkinleştirildiğinden emin olun. </br></br>Ayrıca, aşamalı dağıtım için [ekleme denetimleri](/azure/information-protection/activate-service#configuring-onboarding-controls-for-a-phased-deployment) uyguladıysanız, hizmet hesabının yapılandırdığınız ekleme denetimlerine dahil olduğundan emin olun.|
|**Belirli URL düzeyinde tarama** |Siteleri ve alt siteleri [belirli bir URL'nin altında](#deploying-the-scanner-with-alternative-configurations) taramak ve bulmak için, grup düzeyinde tarayıcı hesabına **Site Toplayıcı Denetçisi** hakları verin.|
|**Bilgi koruması lisansı** | Tarayıcı hizmet hesabına dosya sınıflandırma, etiketleme veya koruma özellikleri sağlamak için gereklidir. <br><br>Daha fazla bilgi için bkz. [Güvenlik & uyumluluğu için Microsoft 365 kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-sensitivity-labeling). |

## <a name="sql-server-requirements"></a>SQL server gereksinimleri

Tarayıcı yapılandırma verilerini depolamak için aşağıdaki gereksinimlere sahip bir SQL sunucusu kullanın:

- **Yerel veya uzak örnek.**

    Küçük bir dağıtımla çalışmadığınız sürece SQL sunucusunu ve tarayıcı hizmetini farklı makinelerde barındırmanızı öneririz. Ayrıca, yalnızca tarayıcı veritabanına hizmet veren ve diğer uygulamalarla paylaşılmayan ayrılmış bir SQL örneğinin olmasını öneririz.

    Paylaşılan bir sunucuda çalışıyorsanız tarayıcı veritabanının çalışması için [önerilen çekirdek sayısının](#windows-server-requirements) ücretsiz olduğundan emin olun.

    SQL Server 2016, aşağıdaki sürümlerin en düşük sürümüdür:

    - SQL Server Enterprise

    - SQL Server Standard

    - SQL Server Express (yalnızca test ortamları için önerilir)

- **Tarayıcıyı yüklemek için Sysadmin rolüne sahip bir hesap.**

    Sysadmin rolü, yükleme işleminin tarayıcı yapılandırma veritabanını otomatik olarak oluşturmasını ve tarayıcıyı çalıştıran hizmet hesabına gerekli **db_owner** rolünü vermesini sağlar.

    Size Sysadmin rolü verilemiyorsa veya kuruluş ilkeleriniz veritabanlarının el ile oluşturulmasını ve yapılandırılmasını gerektiriyorsa, bkz. [Tarayıcıyı alternatif yapılandırmalarla dağıtma](#deploying-the-scanner-with-alternative-configurations).

- **Kapasite.** Kapasite yönergeleri için bkz[. SQL Server için depolama gereksinimleri ve kapasite planlaması](#storage-requirements-and-capacity-planning-for-sql-server).

- **[Büyük/küçük harfe duyarsız harmanlama](/sql/relational-databases/collations/collation-and-unicode-support).**

> [!NOTE]
> Tarayıcı için özel bir küme adı belirttiğinizde veya tarayıcının önizleme sürümünü kullandığınızda, aynı SQL sunucusundaki birden çok yapılandırma veritabanı desteklenir.

### <a name="storage-requirements-and-capacity-planning-for-sql-server"></a>SQL Server için depolama gereksinimleri ve kapasite planlaması

Tarayıcının yapılandırma veritabanı için gereken disk alanı miktarı ve SQL Server çalıştıran bilgisayarın belirtimi her ortam için farklılık gösterebilir, bu nedenle kendi testlerinizi yapmanızı öneririz. Başlangıç noktası olarak aşağıdaki kılavuzu kullanın.

Daha fazla bilgi için bkz. [Tarayıcının performansını iyileştirme](deploy-scanner-configure-install.md#optimize-scanner-performance).

Tarayıcı yapılandırma veritabanının disk boyutu her dağıtım için farklılık gösterir. Kılavuz olarak aşağıdaki denklemi kullanın:

```cli
100 KB + <file count> *(1000 + 4* <average file name length>)
```

Örneğin, ortalama dosya adı uzunluğu 250 bayt olan 1 milyon dosyayı taramak için 2 GB disk alanı ayırın.

Birden çok tarayıcı için:

- **En fazla 10 tarayıcı** kullanın:

    - 4 çekirdekli işlemciler
    - 8 GB RAM önerilir

- **10'dan fazla tarayıcı** (en fazla 40), şunları kullanın:
    - 8 temel işlem
    - 16 GB RAM önerilir

## <a name="azure-information-protection-client-requirements"></a>Azure Information Protection istemci gereksinimleri

Windows Server bilgisayarında Azure Information Protection istemcisinin [geçerli genel kullanılabilirlik sürümü](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history) yüklü olmalıdır.

Daha fazla bilgi için bkz. [Azure Information Protection birleşik etiketleme istemcisi yönetici kılavuzu](/azure/information-protection/rms-client/clientv2-admin-guide#installing-the-azure-information-protection-scanner).

> [!IMPORTANT]
> Tarayıcı için tam istemciyi yüklemeniz gerekir. İstemciyi yalnızca PowerShell modülüyle yüklemeyin.
>

## <a name="label-configuration-requirements"></a>Etiket yapılandırma gereksinimleri

Sınıflandırma ve isteğe bağlı olarak şifreleme uygulamak için tarayıcı hesabının Microsoft Purview uyumluluk portalı en az bir duyarlılık etiketi yapılandırmış olmanız gerekir.

*Tarayıcı hesabı*, tarayıcınızı yapılandırırken çalıştırılan [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) cmdlet'inin **DelegatedUser** parametresinde belirteceğiniz hesaptır. 

Etiketlerinizde otomatik etiketleme koşulları yoksa aşağıdaki [alternatif yapılandırma yönergelerine](#restriction-your-labels-do-not-have-auto-labeling-conditions) bakın.

Daha fazla bilgi için bkz.:

- [Duyarlılık etiketleri hakkında bilgi edinin](sensitivity-labels.md)
- [İçeriğe otomatik olarak bir hassasiyet etiketi uygulama](apply-sensitivity-label-automatically.md)
- [Duyarlılık etiketlerinde şifreleme kullanarak içeriğe erişimi kısıtlama](encryption-sensitivity-labels.md)
- [Bilgi koruma tarayıcısını yapılandırma ve yükleme](deploy-scanner-configure-install.md)

## <a name="sharepoint-requirements"></a>SharePoint gereksinimleri

SharePoint belge kitaplıklarını ve klasörlerini taramak için, SharePoint sunucunuzun aşağıdaki gereksinimlere uygun olduğundan emin olun:

|Gereksinim  |Açıklama  |
|---------|---------|
|**Desteklenen sürümler** | Desteklenen sürümler şunlardır: SharePoint 2019, SharePoint 2016 ve SharePoint 2013. <br> Tarayıcı için SharePoint'in diğer sürümleri desteklenmez.     |
|**Sürüm oluşturma**     |  [Sürüm oluşturma](/sharepoint/governance/versioning-content-approval-and-check-out-planning) kullandığınızda tarayıcı son yayımlanan sürümü inceler ve etiketler. <br><br>Tarayıcı bir dosyayı etiketlerse ve [içerik onayı](/sharepoint/governance/versioning-content-approval-and-check-out-planning#plan-content-approval) gerekiyorsa, etiketlenmiş dosyanın kullanıcılar tarafından kullanılabilmesi için onaylanması gerekir.       |
|**Büyük SharePoint grupları** |Büyük SharePoint grupları için, tarayıcının tüm dosyalara erişmesi için liste görünümü eşiğini (varsayılan olarak 5.000) artırmanız gerekip gerekmediğini denetleyin. <br><br>Daha fazla bilgi için bkz. [SharePoint'te büyük listeleri ve kitaplıkları yönetme](https://support.office.com/article/manage-large-lists-and-libraries-in-sharepoint-b8588dae-9387-48c2-9248-c24122f07c59#__bkmkchangelimit&ID0EAABAAA=Server). |
|**Uzun dosya yolları**  |SharePoint'te uzun dosya yollarınız varsa, SharePoint sunucunuzun [httpRuntime.maxUrlLength](/dotnet/api/system.web.configuration.httpruntimesection.maxurllength) değerinin varsayılan 260 karakterden büyük olduğundan emin olun. <br><br>Daha fazla bilgi için bkz. [SharePoint'te tarayıcı zaman aşımlarından kaçınma](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#avoid-scanner-timeouts-in-sharepoint). | 

## <a name="microsoft-office-requirements"></a>Microsoft Office gereksinimleri

Office belgelerini taramak için, belgelerinizin aşağıdaki biçimlerden birinde olması gerekir:

- Microsoft Office 97-2003
- Word, Excel ve PowerPoint için Office Open XML biçimleri

Daha fazla bilgi için bkz. [Azure Information Protection birleşik etiketleme istemcisi tarafından desteklenen dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types).

## <a name="file-path-requirements"></a>Dosya yolu gereksinimleri

Varsayılan olarak, dosyaları taramak için dosya yollarınızın en fazla 260 karakter olması gerekir.

260 karakterden fazla dosya yolu olan dosyaları taramak için tarayıcıyı aşağıdaki Windows sürümlerinden birine sahip bir bilgisayara yükleyin ve bilgisayarı gerektiği gibi yapılandırın:

|Windows sürümü  |Açıklama  |
|---------|---------|
|**Windows 2016 veya üzeri**     |   Bilgisayarı uzun yolları destekleyecek şekilde yapılandırma      |
|**Windows 10 veya Windows Server 2016**     | Aşağıdaki [grup ilkesi ayarını](/archive/blogs/jeremykuhne/net-4-6-2-and-long-paths-on-windows-10) tanımlayın: **Yerel Bilgisayar İlkesi** > **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Tüm Ayarlar** > **Win32 uzun yollarını etkinleştirin**.    </br></br>Bu sürümlerde uzun dosya yolu desteği hakkında daha fazla bilgi için, Windows 10 geliştirici belgelerindeki [En Fazla Yol Uzunluğu Sınırlaması](/windows/desktop/FileIO/naming-a-file#maximum-path-length-limitation) bölümüne bakın.    |
|**Windows 10, sürüm 1607 veya üzeri**     |  Güncelleştirilmiş **MAX_PATH** işlevselliğini kabul edin. Daha fazla bilgi için bkz[. Windows 10 sürüm 1607 ve sonraki sürümlerde Uzun Yolları Etkinleştirme](/windows/win32/fileio/naming-a-file#enable-long-paths-in-windows-10-version-1607-and-later).      |

## <a name="deploying-the-scanner-with-alternative-configurations"></a>Tarayıcıyı alternatif yapılandırmalarla dağıtma

Yukarıda listelenen önkoşullar tarayıcı dağıtımı için varsayılan gereksinimlerdir ve en basit tarayıcı yapılandırmasını desteklediğinden önerilir.

Tarayıcının özelliklerini denetleyebilmeniz için varsayılan gereksinimler ilk test için uygun olmalıdır.

Ancak, üretim ortamında kuruluşunuzun ilkeleri varsayılan gereksinimlerden farklı olabilir. Tarayıcı, ek yapılandırma ile aşağıdaki değişikliklere uyum sağlayabilir:

- [Belirli bir URL'nin altındaki tüm siteleri ve alt siteleri bulma ve tarama](#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url)

- [Kısıtlama: Tarayıcı sunucusunun İnternet bağlantısı olamaz](#restriction-the-scanner-server-cannot-have-internet-connectivity)

- [Kısıtlama: Tarayıcı hizmet hesabı Azure Active Directory ile eşitlenemiyor ancak sunucunun İnternet bağlantısı var](#restriction-the-scanner-service-account-cannot-be-synchronized-to-azure-active-directory-but-the-server-has-internet-connectivity)

- [Kısıtlama: Tarayıcının hizmet hesabına **yerel olarak oturum açma** hakkı verilemez](#restriction-the-service-account-for-the-scanner-cannot-be-granted-the-log-on-locally-right)

- [Kısıtlama: Size Sysadmin verilemez veya veritabanları el ile oluşturulup yapılandırılmalıdır](#restriction-you-cannot-be-granted-sysadmin-or-databases-must-be-created-and-configured-manually)

- [Kısıtlama: Etiketlerinizde otomatik etiketleme koşulları yok](#restriction-your-labels-do-not-have-auto-labeling-conditions)

### <a name="discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url"></a>Belirli bir URL'nin altındaki tüm Sharepoint sitelerini ve alt sitelerini bulma ve tarama

Tarayıcı, aşağıdaki yapılandırmaya sahip belirli bir URL'nin altındaki tüm Sharepoint sitelerini ve alt sitelerini bulabilir ve tarar:

1. **SharePoint Yönetim Merkezi'ni** başlatın.

1. **SharePoint Yönetim Merkezi** web sitesinin **Uygulama Yönetimi** bölümünde **Web uygulamalarını yönet'e** tıklayın.

1. İzin ilkesi düzeyini yönetmek istediğiniz web uygulamasını vurgulamak için tıklayın.

1. İlgili grubu seçin ve ardından **İzinler İlke Düzeylerini Yönet'i** seçin.

1. **Site Koleksiyonu İzinleri** seçeneklerinde **Site Koleksiyonu Denetçisi'ni** seçin, ardından İzinler listesinde **Uygulama Sayfalarını Görüntüle'yi** verin ve son olarak yeni ilke **düzeyine AIP tarayıcı site koleksiyonu denetçisi ve görüntüleyicisi adını verin**.

1. Tarayıcı kullanıcınızı yeni ilkeye ekleyin ve İzinler listesinde **Site koleksiyonu** verin.

1. Taranılması gereken siteleri veya alt siteleri barındıran SharePoint URL'sini ekleyin. Daha fazla bilgi için bkz. [Tarayıcı ayarlarını yapılandırma](/azure/information-protection/deploy-scanner-configure-install#configure-the-scanner-settings).

SharePoint ilke düzeylerinizi yönetme hakkında daha fazla bilgi edinmek için bkz. [Web uygulaması için izin ilkelerini yönetme](/sharepoint/administration/manage-permission-policies-for-a-web-application).

### <a name="restriction-the-scanner-server-cannot-have-internet-connectivity"></a>Kısıtlama: Tarayıcı sunucusunun İnternet bağlantısı olamaz

Birleşik etiketleme istemcisi İnternet bağlantısı olmadan şifreleme uygulayamaz ancak tarayıcı yine de içeri aktarılan ilkelere göre etiketler uygulayabilir.

Bağlantısı kesilmiş bir bilgisayarı desteklemek için aşağıdaki yöntemlerden birini kullanın:

- [Uyumluluk portalını kullanma](#use-the-microsoft-purview-compliance-portal-with-a-disconnected-computer) (mümkün olduğunda önerilir)

- [PowerShell kullanma](#use-powershell-with-a-disconnected-computer)

#### <a name="use-the-microsoft-purview-compliance-portal-with-a-disconnected-computer"></a>bağlantısı kesilmiş bir bilgisayarla Microsoft Purview uyumluluk portalı kullanma

Microsoft Purview uyumluluk portalı bağlanamıyor bir bilgisayarı desteklemek için aşağıdaki adımları gerçekleştirin:

1.  İlkenizdeki etiketleri yapılandırın ve çevrimdışı sınıflandırmayı ve [etiketlemeyi etkinleştirmek üzere bağlantısı kesilmiş bilgisayarları desteklemek için yordamı](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#support-for-disconnected-computers) kullanın.

1. İçerik işleri için çevrimdışı yönetimi aşağıdaki gibi etkinleştirin:

    **İçerik tarama işleri için çevrimdışı yönetimi etkinleştirme**:

    1. [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet'ini kullanarak tarayıcıyı **çevrimdışı** modda çalışması için ayarlayın.

    1. Bir tarayıcı kümesi oluşturarak uyumluluk portalında tarayıcıyı yapılandırın. Daha fazla bilgi için bkz. [Tarayıcı ayarlarını yapılandırma](deploy-scanner-configure-install.md#configure-the-scanner-settings).

    1. **İçerik işinizi Bilgi koruması - İçerik tarama işleri** bölmesinden **Dışarı Aktar seçeneğini kullanarak dışarı aktarın**.

    1. [Import-AIPScannerConfiguration](/powershell/module/azureinformationprotection/import-aipscannerconfiguration) cmdlet'ini kullanarak ilkeyi içeri aktarın.

    Çevrimdışı içerik tarama işlerinin sonuçları şu konumda bulunur: **%localappdata%\Microsoft\MSIP\Scanner\Reports**

#### <a name="use-powershell-with-a-disconnected-computer"></a>PowerShell'i bağlantısı kesilmiş bir bilgisayarla kullanma

Yalnızca PowerShell kullanarak bağlantısı kesilmiş bir bilgisayarı desteklemek için aşağıdaki yordamı uygulayın.

> [!IMPORTANT]
> [Azure China 21Vianet tarayıcı sunucularının](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs) yöneticileri, içerik tarama işlerini yönetmek için bu yordamı *kullanmalıdır*.
>

**İçerik tarama işlerinizi yalnızca PowerShell kullanarak yönetin**:

1. [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet'ini kullanarak tarayıcıyı **çevrimdışı** modda çalışması için ayarlayın.

1. [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet'ini kullanarak yeni bir içerik tarama işi oluşturun ve zorunlu `-Enforce On` parametreyi kullandığınızdan emin olun.

1. Eklemek istediğiniz deponun yolunu içeren [Add-AIPScannerRepository cmdlet'ini](/powershell/module/azureinformationprotection/add-aipscannerrepository) kullanarak depolarınızı ekleyin.

    > [!TIP]
    > Deponun ayarları içerik tarama işinizden devralmasını önlemek için parametresini `OverrideContentScanJob On` ve ek ayarlar için değerleri ekleyin.
    >
    > Mevcut bir deponun ayrıntılarını düzenlemek için [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) komutunu kullanın.
    >
 
1. İçerik tarama işinizin geçerli ayarları hakkında bilgi [döndürmek için Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) ve [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) cmdlet'lerini kullanın. 

1. Mevcut bir deponun ayrıntılarını güncelleştirmek için [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) komutunu kullanın.

1. [Gerekirse Start-AIPScan](/powershell/module/azureinformationprotection/start-aipscan) cmdlet'ini kullanarak içerik tarama işinizi hemen çalıştırın. 

    Çevrimdışı içerik tarama işlerinin sonuçları şu konumda bulunur: **%localappdata%\Microsoft\MSIP\Scanner\Reports**

1. Bir depoyu veya içerik tarama işinin tamamını kaldırmanız gerekiyorsa aşağıdaki cmdlet'leri kullanın:

    - [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob)
    - [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

### <a name="restriction-you-cannot-be-granted-sysadmin-or-databases-must-be-created-and-configured-manually"></a>Kısıtlama: Size Sysadmin verilemez veya veritabanları el ile oluşturulup yapılandırılmalıdır

Veritabanlarını el ile oluşturmak ve gerektiğinde **db_owner** rolü vermek için aşağıdaki yordamları kullanın.

- [Tarayıcı veritabanı yordamı](#manually-create-a-database-and-user-for-the-scanner-and-grant-db_owner-rights)

Tarayıcıyı yüklemek için *geçici olarak* Sysadmin rolü verilebiliyorsa, tarayıcı yüklemesi tamamlandığında bu rolü kaldırabilirsiniz.

Kuruluşunuzun gereksinimlerine bağlı olarak aşağıdakilerden birini yapın:

|Kısıtlama  |Açıklama  |
|---------|---------|
|**Sysadmin rolüne geçici olarak sahip olabilirsiniz**     |  Sysadmin rolüne geçici olarak sahipseniz veritabanı sizin için otomatik olarak oluşturulur ve tarayıcının hizmet hesabına otomatik olarak gerekli izinler verilir. <br><br>Ancak, tarayıcıyı yapılandıran kullanıcı hesabı yine de tarayıcı yapılandırma veritabanı için **db_owner** rolü gerektirir. Tarayıcı yüklemesi tamamlanana kadar yalnızca Sysadmin rolüne sahipseniz kullanıcı hesabına **db_owner** rolünü el ile verin.       |
|**Sysadmin rolüne hiç sahip olamazsınız**     |  Sysadmin rolüne geçici olarak bile izin verilmiyorsa, tarayıcıyı yüklemeden önce Sysadmin haklarına sahip bir kullanıcıdan el ile veritabanı oluşturmasını istemeniz gerekir. <br><br>Bu yapılandırma için **db_owner** rolü aşağıdaki hesaplara atanmalıdır: <br>- Tarayıcı için hizmet hesabı<br>- Tarayıcı yüklemesi için kullanıcı hesabı<br>- Tarayıcı yapılandırması için kullanıcı hesabı <br><br>Genellikle tarayıcıyı yüklemek ve yapılandırmak için aynı kullanıcı hesabını kullanırsınız. Farklı hesaplar kullanıyorsanız, her ikisi de tarayıcı yapılandırma veritabanı için **db_owner** rolü gerektirir. Bu kullanıcıyı ve hakları gerektiği gibi oluşturun. Kendi küme adınızı belirtirseniz, yapılandırma veritabanı **AIPScannerUL_<cluster_name>** olarak adlandırılır.  |

Ayrıca:

- Tarayıcıyı çalıştıracak sunucuda yerel yönetici olmanız gerekir
- Tarayıcıyı çalıştıracak hizmet hesabına aşağıdaki kayıt defteri anahtarları için Tam Denetim izinleri verilmelidir:

    - `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\Server`
    - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server`

Bu izinleri yapılandırdıktan sonra tarayıcıyı yüklerken bir hata görürseniz, hata yoksayılabilir ve tarayıcı hizmetini el ile başlatabilirsiniz.

#### <a name="manually-create-a-database-and-user-for-the-scanner-and-grant-db_owner-rights"></a>Tarayıcı için el ile veritabanı ve kullanıcı oluşturma ve db_owner hakları verme

Tarayıcı veritabanınızı el ile oluşturmanız ve/veya bir kullanıcı oluşturmanız ve veritabanında **db_owner** hakları vermeniz gerekiyorsa Sysadmin'inizden aşağıdaki adımları gerçekleştirmesini isteyin:

1. Tarayıcı için veritabanı oluşturma:

    ```sql
    **CREATE DATABASE AIPScannerUL_[clustername]**

    **ALTER DATABASE AIPScannerUL_[clustername] SET TRUSTWORTHY ON**
    ```

2. Yükleme komutunu çalıştıran ve tarayıcı yönetimi komutlarını çalıştırmak için kullanılan kullanıcıya haklar verin. Aşağıdaki betiği kullanın:

    ```sql
    if not exists(select * from master.sys.server_principals where sid = SUSER_SID('domain\user')) BEGIN declare @T nvarchar(500) Set @T = 'CREATE LOGIN ' + quotename('domain\user') + ' FROM WINDOWS ' exec(@T) END
    USE DBName IF NOT EXISTS (select * from sys.database_principals where sid = SUSER_SID('domain\user')) BEGIN declare @X nvarchar(500) Set @X = 'CREATE USER ' + quotename('domain\user') + ' FROM LOGIN ' + quotename('domain\user'); exec sp_addrolemember 'db_owner', 'domain\user' exec(@X) END
    ```

3. Tarayıcı hizmet hesabına haklar verin. Aşağıdaki betiği kullanın:

    ```sql
    if not exists(select * from master.sys.server_principals where sid = SUSER_SID('domain\user')) BEGIN declare @T nvarchar(500) Set @T = 'CREATE LOGIN ' + quotename('domain\user') + ' FROM WINDOWS ' exec(@T) END
    ```

### <a name="restriction-the-service-account-for-the-scanner-cannot-be-granted-the-log-on-locally-right"></a>Kısıtlama: Tarayıcının hizmet hesabına **yerel olarak oturum açma** hakkı verilemez

Kuruluş ilkeleriniz hizmet hesapları için **yerel olarak oturum açma** hakkını yasaklarsa, Set-AIPAuthentication ile *OnBehalfOf* parametresini kullanın.

Daha fazla bilgi için bkz. [Azure Information Protection için dosyaları etkileşimli olmayan şekilde etiketleme](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

### <a name="restriction-the-scanner-service-account-cannot-be-synchronized-to-azure-active-directory-but-the-server-has-internet-connectivity"></a>Kısıtlama: Tarayıcı hizmet hesabı Azure Active Directory ile eşitlenemiyor ancak sunucunun İnternet bağlantısı var

Tarayıcı hizmetini çalıştırmak için bir hesabınız olabilir ve Azure Active Directory'de kimlik doğrulaması yapmak için başka bir hesap kullanabilirsiniz:

- **Tarayıcı hizmeti hesabı için** yerel bir Windows hesabı veya Active Directory hesabı kullanın.

- **Azure Active Directory hesabı için**, [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) cmdlet'indeki *DelegatedUser* parametresinde AAD kullanıcısını belirtin. 

    Taramayı tarayıcı hesabı dışındaki herhangi bir kullanıcı altında çalıştırıyorsanız, tarayıcı hesabını *OnBehalfOf* parametresinde de belirttiğinizden emin olun. 

    Daha fazla bilgi için bkz. [Azure Information Protection için dosyaları etkileşimli olmayan şekilde etiketleme](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

### <a name="restriction-your-labels-do-not-have-auto-labeling-conditions"></a>Kısıtlama: Etiketlerinizde otomatik etiketleme koşulları yok

Etiketlerinizde otomatik etiketleme koşulu yoksa tarayıcınızı yapılandırırken aşağıdaki seçeneklerden birini kullanmayı planlayın:

|Seçeneği  |Açıklama  |
|---------|---------|
|**Tüm bilgi türlerini keşfedin**     |  [İçerik tarama işinizde](deploy-scanner-configure-install.md#create-a-content-scan-job), **Bulunacak Bilgi türleri** seçeneğini **Tümü** olarak ayarlayın. </br></br>Bu seçenek, içeriğinizi tüm hassas bilgi türleri için tarayacak içerik tarama işini ayarlar.      |
|**Önerilen etiketlemeyi kullanma**     |  [İçerik tarama işinizde](deploy-scanner-configure-install.md#create-a-content-scan-job) **Önerilen etiketlemeyi otomatik olarak kabul et** seçeneğini **Açık** olarak ayarlayın.</br></br> Bu ayar tarayıcıyı, içeriğinize önerilen tüm etiketleri otomatik olarak uygulayacak şekilde yapılandırıyor.      |
|**Varsayılan etiket tanımlama**     |   [İlkenizde](sensitivity-labels.md#what-label-policies-can-do), [içerik tarama işinizde](deploy-scanner-configure-install.md#create-a-content-scan-job) veya [deponuzda](deploy-scanner-configure-install.md#apply-a-default-label-to-all-files-in-a-data-repository) varsayılan bir etiket tanımlayın. </br></br>Bu durumda tarayıcı, bulunan tüm dosyalara varsayılan etiketi uygular.       |

## <a name="next-steps"></a>Sonraki adımlar

Sisteminizin tarayıcı önkoşullarına uygun olduğunu onayladıktan sonra [Bilgi koruma tarayıcısını yapılandırma ve yükleme](deploy-scanner-configure-install.md) ile devam edin.

Tarayıcı hakkında genel bir bakış için bkz. [Bilgi koruma tarayıcısı hakkında bilgi edinme](deploy-scanner.md).