---
title: Microsoft Purview Bilgi Koruması tarayıcısını yükleme ve yapılandırma
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
description: Veri depolarında dosyaları bulmak, sınıflandırmak ve korumak için Microsoft Purview Bilgi Koruması tarayıcısını yüklemeyi ve yapılandırmayı öğrenin.
ms.openlocfilehash: 69d8d337f78fab74f35955ad15bd2d2e013a436c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623970"
---
# <a name="configuring-and-installing-the-information-protection-scanner"></a>Bilgi koruma tarayıcısını yapılandırma ve yükleme

> [!NOTE]
> Microsoft Purview Bilgi Koruması tarayıcısı daha önce Azure Information Protection birleşik etiketleme tarayıcısı veya şirket içi tarayıcı olarak adlandırıldı. Yapılandırma Azure portal Microsoft Purview uyumluluk portalı taşındı.

Bu makalede, eski adı Azure Information Protection birleşik etiketleme tarayıcısı veya şirket içi tarayıcı olan Microsoft Purview Bilgi Koruması tarayıcısının nasıl yapılandırılıp yükleneceği açıklanır.

> [!TIP]
> Çoğu müşteri bu yordamları yönetici portalında gerçekleştirse de, yalnızca PowerShell'de çalışmanız gerekebilir.
>
> Örneğin, [Azure China 21Vianet tarayıcı sunucuları](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs) gibi yönetici portalına erişimi olmayan bir ortamda çalışıyorsanız, [Tarayıcıyı yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-the-scanner) başlığı altında yer alan yönergeleri izleyin.
>

## <a name="overview"></a>Genel bakış

Başlamadan önce sisteminizin [gerekli önkoşullara](deploy-scanner-prereqs.md) uyduğunu doğrulayın.

Ardından, tarayıcıyı yapılandırmak ve yüklemek için aşağıdaki adımları kullanın:

1. [Tarayıcı ayarlarını yapılandırma](#configure-the-scanner-settings)

2. [Tarayıcıyı yükleme](#install-the-scanner)

3. [Tarayıcı için Azure AD belirteci alma](#get-an-azure-ad-token-for-the-scanner)

4. [Tarayıcıyı sınıflandırma ve koruma uygulayacak şekilde yapılandırma](#configure-the-scanner-to-apply-classification-and-protection)

Ardından, sisteminiz için gereken şekilde aşağıdaki yapılandırma yordamlarını gerçekleştirin:

|Yordam  |Açıklama  |
|---------|---------|
|[Korunacak dosya türlerini değiştirme](#change-which-file-types-to-protect) |Varsayılandan farklı dosya türlerini taramak, sınıflandırmak veya korumak isteyebilirsiniz. Daha fazla bilgi için bkz. [Tarama işlemi](deploy-scanner.md#the-scanning-process). |
|[Tarayıcınızı yükseltme](#upgrade-your-scanner) | Tarayıcınızı en son özellikleri ve geliştirmeleri kullanacak şekilde yükseltin.|
|[Veri deposu ayarlarını toplu olarak düzenleme](#edit-data-repository-settings-in-bulk)| Birden çok veri deposunda toplu olarak değişiklik yapmak için içeri ve dışarı aktarma seçeneklerini kullanın.|
|[Tarayıcıyı alternatif yapılandırmalarla kullanma](#use-the-scanner-with-alternative-configurations)| Etiketleri herhangi bir koşulla yapılandırmadan tarayıcıyı kullanma |
|[Performansı iyileştirme](#optimize-scanner-performance)| Tarayıcı performansınızı iyileştirme kılavuzu|

Uyumluluk portalında tarayıcı sayfalarına erişiminiz yoksa, tarayıcı ayarlarını yalnızca PowerShell'de yapılandırın. Daha fazla bilgi için bkz. [Tarayıcıyı yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-the-scanner) ve [Desteklenen PowerShell cmdlet'leri](#supported-powershell-cmdlets).


## <a name="configure-the-scanner-settings"></a>Tarayıcı ayarlarını yapılandırma

Tarayıcıyı yüklemeden veya eski bir genel kullanılabilirlik sürümünden yükseltmeden önce tarayıcı ayarlarınızı yapılandırın veya doğrulayın.

**Tarayıcınızı Microsoft Purview uyumluluk portalı yapılandırmak için:**

1. Aşağıdaki rollerden biriyle [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com) oturum açın:

    - **Uyumluluk yöneticisi**
    - **Uyumluluk veri yöneticisi**
    - **Güvenlik yöneticisi**
    - **Genel yönetici**

    Ardından **Ayarlar** bölmesine gidin.

    **Ayarlar** bölmesinde **Bilgi koruma tarayıcısı'nı** seçin.

2. [Bir tarayıcı kümesi oluşturun](#create-a-scanner-cluster). Bu küme tarayıcınızı tanımlar ve yükleme, yükseltmeler ve diğer işlemler gibi tarayıcı örneğini tanımlamak için kullanılır.

3. Taramak istediğiniz depoları tanımlamak için [bir içerik tarama işi oluşturun](#create-a-content-scan-job).

### <a name="create-a-scanner-cluster"></a>Tarayıcı kümesi oluşturma

**Microsoft Purview uyumluluk portalı bir tarayıcı kümesi oluşturmak için:**

1. **Bilgi koruma tarayıcısı** sayfasındaki sekmelerden **Kümeler'i** seçin.

2. **Kümeler** sekmesinde ![Ekle ekle simgesi'ni](../media/i-add.png "ekle simgesi") seçin.

3. **Yeni küme** bölmesinde, tarayıcı için anlamlı bir ad ve isteğe bağlı bir açıklama girin.

    Küme adı, tarayıcının yapılandırmalarını ve depolarını tanımlamak için kullanılır. Örneğin, taramak istediğiniz veri depolarının coğrafi konumlarını belirlemek için **Avrupa** girebilirsiniz.

    Tarayıcınızı nereye yüklemek veya yükseltmek istediğinizi belirlemek için bu adı daha sonra kullanacaksınız.

4. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="create-a-content-scan-job"></a>İçerik tarama işi oluşturma

Hassas içerik için belirli depoları taramak için içeriğinize derinlemesine bakın.

**İçerik tarama işinizi Microsoft Purview uyumluluk portalı oluşturmak için:**

1. **Bilgi koruma tarayıcısı** sayfasındaki sekmelerden **İçerik tarama işleri'ni** seçin.

2. **İçerik tarama işleri** bölmesinde ![Ekle ekle simgesi'ni](../media/i-add.png "kaydet simgesi") seçin.

3. Bu ilk yapılandırma için aşağıdaki ayarları yapılandırın ve **kaydet'i** seçin.

    |Ayar  |Açıklama  |
    |---------|---------|
    |**İçerik tarama işi ayarları**     |    - **Zamanlama**: **El ile** varsayılanını koru <br />- **Bulunabilecek bilgi türleri**: **Yalnızca İlke** olarak değiştir
    |**DLP ilkesi** | Veri kaybı önleme ilkesi kullanıyorsanız **DLP kurallarını etkinleştir** seçeneğini **Açık** olarak ayarlayın. Daha fazla bilgi için bkz. [DLP ilkesi kullanma](#use-a-dlp-policy). |
    |**Duyarlılık ilkesi**     | - **Duyarlılık etiketleme ilkesini zorunlu kılma**: **Kapalı'yı** seçin <br />- **Dosyaları içeriğe göre etiketleme**: Varsayılan **Açık ayarını** değiştirmeyin <br />- **Varsayılan etiket**: **varsayılan İlke varsayılanını** koru <br />- **Dosyaları yeniden etiketleme**: Varsayılan **Kapalı'yı** koru        |
    |**Dosya ayarlarını yapılandırma**     | - **"Değiştirme tarihi", "Son değiştirme" ve "Değiştiren" değerlerini koru**: Varsayılan **ayarı Açık** olarak tutun <br />- **Taranacak dosya türleri**: **Dışlama** için varsayılan dosya türlerini koruma <br />- **Varsayılan sahip**: **Tarayıcı Hesabı'nın** varsayılanını koru  <br /> - **Depo sahibini ayarla**: Bu seçeneği yalnızca [DLP ilkesi kullanırken](#use-a-dlp-policy) kullanın. |
    | | |


4. Kaydedilen içerik tarama işini açın ve taranacak veri **depolarını belirtmek için Depolar** sekmesini seçin. 

    SharePoint şirket içi belge kitaplıkları ve klasörleri için UNC yollarını ve SharePoint Server URL'lerini belirtin.

    > [!NOTE]
    > sharepoint için SharePoint Server 2019, SharePoint Server 2016 ve SharePoint Server 2013 desteklenir. SharePoint'in [bu sürümü için genişletilmiş desteğe sahip olduğunuzda SharePoint Server](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) 2010 da desteklenir.
    >
    **Depolar** sekmesindeyken ilk veri deponuzu eklemek için:

    1. **Depolar** bölmesinde **Ekle'yi** seçin:

    2. **Depo** bölmesinde veri deposunun yolunu belirtin ve **kaydet'i** seçin.


        - Ağ paylaşımı için kullanın `\\Server\Folder`.
        - SharePoint kitaplığı için kullanın `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
        - Yerel yol için: `C:\Folder`
        - UNC yolu için: `\\Server\Folder`

    > [!NOTE]
    > Joker karakterler desteklenmez ve WebDav konumları desteklenmez.
    >

    **Paylaşılan Belgeler** için bir SharePoint yolu eklerseniz:
    - **Paylaşılan Belgeler'deki** tüm belgeleri ve tüm klasörleri taramak istediğinizde, yolda Paylaşılan Belgeler'i belirtin.
    Örneğin: `http://sp2013/SharedDocuments`
    - Paylaşılan **Belgeler** altındaki bir alt klasörden tüm belgeleri ve tüm klasörleri taramak istediğinizde, yolda Belgeler'i belirtin.
    Örneğin: `http://sp2013/Documents/SalesReports`
    - Alternatif olarak, yalnızca SharePoint'inizin **FQDN'sini** belirtin; örneğin `http://sp2013` , bu [URL'nin altındaki belirli bir URL ve alt başlıklar altında tüm SharePoint sitelerini ve alt sitelerini bulup tarayın](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) . Bunu etkinleştirmek için tarayıcı **Site Toplayıcı Denetçisi** hakları verin.
    >


    Bu bölmedeki diğer ayarlar için, bu ilk yapılandırma için bunları değiştirmeyin, ancak bunları **varsayılan İçerik tarama işi** olarak tutun. Varsayılan ayar, veri deposunun ayarları içerik tarama işinden devraldığı anlamına gelir.

    SharePoint yolları eklerken aşağıdaki söz dizimini kullanın:

    |Yol  |Sözdizimi  |
    |---------|---------|
    |**Kök yol**     | `http://<SharePoint server name>` <br /><br />Tarayıcı kullanıcısı için izin verilen tüm site koleksiyonları dahil olmak üzere tüm siteleri tarar. <br />Kök içeriği otomatik olarak bulmak için [ek izinler](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) gerektirir        |
    |**Belirli SharePoint alt sitesi veya koleksiyonu**     | Aşağıdakilerden biri: <br />- `http://<SharePoint server name>/<subsite name>` <br />- `http://SharePoint server name>/<site collection name>/<site name>` <br /><br />Site koleksiyonu içeriğini otomatik olarak bulmak için [ek izinler](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) gerektirir         |
    |**Belirli SharePoint kitaplığı**     | Aşağıdakilerden biri: <br />- `http://<SharePoint server name>/<library name>` <br />- `http://SharePoint server name>/.../<library name>`       |
    |**Belirli SharePoint klasörü**     | `http://<SharePoint server name>/.../<folder name>`        |
    | | |

5. Gerektiği kadar depo eklemek için önceki adımları yineleyin.

Artık oluşturduğunuz içerik tarayıcısı işiyle tarayıcıyı yüklemeye hazırsınız. [Tarayıcıyı yükleme ile](#install-the-scanner) devam edin.

## <a name="install-the-scanner"></a>Tarayıcıyı yükleme

[Tarayıcıyı yapılandırdıktan sonra, tarayıcıyı](#configure-the-scanner-settings) yüklemek için aşağıdaki adımları uygulayın. Bu yordam Tamamen PowerShell'de gerçekleştirilir.

1. Tarayıcıyı çalıştıracak Windows Server bilgisayarında oturum açın. Yerel yönetici haklarına sahip ve SQL Server ana veritabanına yazma izinleri olan bir hesap kullanın.

    > [!IMPORTANT]
    > Tarayıcıyı yüklemeden önce makinenizde AIP birleşik etiketleme istemcisi yüklü olmalıdır.
    >
    > Daha fazla bilgi için bkz. [Bilgi koruma tarayıcısını yükleme ve dağıtma önkoşulları](deploy-scanner-prereqs.md).
    >

2. **Yönetici olarak çalıştır** seçeneğiyle bir Windows PowerShell oturumu açın.

3. Azure Information Protection tarayıcısı için veritabanı oluşturulacak SQL Server örneğinizi ve [önceki bölümde belirttiğiniz](#create-a-scanner-cluster) tarayıcı kümesi adını belirterek [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet'ini çalıştırın:

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    **Avrupa'nın** tarayıcı kümesi adını kullanan örnekler:

    - Varsayılan örnek için: `Install-AIPScanner -SqlServerInstance SQLSERVER1 -Cluster Europe`

    - Adlandırılmış örnek için: `Install-AIPScanner -SqlServerInstance SQLSERVER1\AIPSCANNER -Cluster Europe`

    - SQL Server Express için:`Install-AIPScanner -SqlServerInstance SQLSERVER1\SQLEXPRESS -Cluster Europe`

    İstendiğinde, tarayıcı hizmeti hesabı için Active Directory kimlik bilgilerini sağlayın.

    Aşağıdaki söz dizimini kullanın: `\<domain\user name>`. Örneğin: `contoso\scanneraccount`

4. **Hizmetin artık Yönetimsel Araçlar** > **Hizmetleri'ni** kullanarak yüklendiğini doğrulayın.

    Yüklü hizmet **Azure Information Protection Tarayıcısı** olarak adlandırılır ve oluşturduğunuz tarayıcı hizmet hesabı kullanılarak çalıştırılacak şekilde yapılandırılır.

Tarayıcıyı yüklediğinize göre tarayıcının katılımsız çalışabilmesi için tarayıcı hizmet hesabının kimlik doğrulaması [için bir Azure AD belirteci almanız](#get-an-azure-ad-token-for-the-scanner) gerekir.

## <a name="get-an-azure-ad-token-for-the-scanner"></a>Tarayıcı için Azure AD belirteci alma

Azure AD belirteci, tarayıcının Azure Information Protection hizmetinde kimlik doğrulaması yapmasına olanak tanıyarak tarayıcının etkileşimli olmayan bir şekilde çalışmasını sağlar.

Daha fazla bilgi için bkz. [Azure Information Protection için dosyaları etkileşimli olmayan şekilde etiketleme](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

**Azure AD belirteci almak için**:

1. Kimlik [doğrulaması için bir](https://portal.azure.com/) erişim belirteci belirtmek üzere bir Azure AD uygulaması oluşturmak üzere Azure portal açın.

2. Windows Server bilgisayarından, tarayıcı hizmeti hesabınıza yükleme için **yerel olarak oturum açma** hakkı verildiyse, bu hesapla oturum açın ve bir PowerShell oturumu başlatın.

    Önceki adımda kopyaladığınız değerleri belirterek [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) komutunu çalıştırın:

    ```PowerShell
    Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
    ```

    Örneğin:

    ```PowerShell
    $pscreds = Get-Credential CONTOSO\scanner
    Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
    Acquired application access token on behalf of CONTOSO\scanner.
    ```

    > [!TIP]
    > Tarayıcı hizmeti hesabınıza yükleme için **yerel olarak oturum açma** hakkı verilemiyorsa, [Dosyaları Azure Information Protection için etkileşimli olmayan şekilde etiketleme](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection) bölümünde açıklandığı gibi [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) ile *OnBehalfOf* parametresini kullanın.
    >

Tarayıcının artık Azure AD kimlik doğrulaması için bir belirteci vardır. Bu belirteç, **Azure AD'de Web uygulaması /API** istemci gizli dizisi yapılandırmanıza göre bir yıl, iki yıl veya hiçbir zaman geçerlidir. Belirtecin süresi dolduğunda bu yordamı yinelemeniz gerekir.

Tarayıcınızı yapılandırmak için uyumluluk portalını mı yoksa yalnızca PowerShell'i mi kullandığınıza bağlı olarak aşağıdaki adımlardan birini kullanmaya devam edin:

# <a name="admin-portal-only"></a>[Yalnızca portalı Yönetici](#tab/azure-portal-only)

Artık keşif modunda ilk taramanızı çalıştırmaya hazırsınız. Daha fazla bilgi için bkz. [Bulma döngüsü çalıştırma ve tarayıcı raporlarını görüntüleme](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner).

İlk bulma taramanızı çalıştırdıktan sonra, [Tarayıcıyı sınıflandırma ve koruma uygulamak için yapılandırma](#configure-the-scanner-to-apply-classification-and-protection) ile devam edin.

# <a name="powershell-only"></a>[Yalnızca PowerShell](#tab/powershell-only)

Uyumluluk portalındaki tarayıcı sayfaları yerine PowerShell kullanarak tarayıcınızı yapılandırıyor ve yüklüyorsanız, tarayıcıyı [yapılandırmak için PowerShell kullanma](#powershell) bölümünde 5. adımla devam edin.

Sonra:

- [Bulma döngüsü çalıştırma ve tarayıcı için raporları görüntüleme](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Tarayıcıyı sınıflandırma ve koruma uygulayacak şekilde yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Tarayıcıyla DLP ilkesi yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

---

> [!NOTE]
> Daha fazla bilgi için bkz. [Azure Information Protection için dosyaları etkileşimli olmayan şekilde etiketleme](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)



## <a name="configure-the-scanner-to-apply-classification-and-protection"></a>Tarayıcıyı sınıflandırma ve koruma uygulayacak şekilde yapılandırma

Varsayılan ayarlar tarayıcıyı bir kez ve yalnızca raporlama modunda çalışacak şekilde yapılandırılır. Bu ayarları değiştirmek için içerik tarama işini düzenleyin.

> [!TIP]
> Yalnızca PowerShell'de çalışıyorsanız bkz. [Tarayıcıyı sınıflandırma ve koruma uygulamak için yapılandırma - Yalnızca PowerShell](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection).
>

**Tarayıcıyı Microsoft Purview uyumluluk portalı sınıflandırma ve koruma uygulayacak şekilde yapılandırmak için**:

1. Microsoft Purview uyumluluk portalı **İçerik tarama işleri** sekmesinde düzenlemek için belirli bir içerik tarama işi seçin.

2. İçerik tarama işini seçin, aşağıdakileri değiştirin ve ardından **Kaydet'i** seçin:

   - **İçerik tarama işi** bölümünden: **Zamanlama'yı** **Her Zaman** olarak değiştirin
   - **Duyarlılık etiketleme ilkesini zorunlu kılma** bölümünden: Radyo düğmesini **Açık** olarak değiştirin

3. İçerik tarama işi için bir düğümün çevrimiçi olduğundan emin olun, ardından **Şimdi tara'yı** seçerek içerik tarama işini yeniden başlatın. **Şimdi tara** düğmesi yalnızca seçili içerik tarama işi için bir düğüm çevrimiçi olduğunda görünür. 

Tarayıcı artık sürekli çalışacak şekilde zamanlanmıştır. Tarayıcı tüm yapılandırılmış dosyalar arasında çalıştığında, yeni ve değiştirilmiş dosyaların bulunması için otomatik olarak yeni bir döngü başlatır.

## <a name="use-a-dlp-policy"></a>DLP ilkesi kullanma

Veri kaybı önleme ilkesi kullanmak, tarayıcının DLP kurallarını dosya paylaşımlarında ve SharePoint Server'da depolanan dosyalarla eşleştirerek olası veri sızıntılarını algılamasını sağlar.

- **DLP ilkelerinizle** eşleşen dosyaların açığa çıkışını azaltmak için içerik tarama işinizde DLP kurallarını etkinleştirin. DLP kurallarınız etkinleştirildiğinde tarayıcı yalnızca veri sahiplerine dosya erişimini azaltabilir veya **Herkes**, **Kimliği Doğrulanmış Kullanıcılar** veya **Etki Alanı Kullanıcıları** gibi ağ genelindeki grupların etkilenmesini azaltabilir.

- **Microsoft Purview uyumluluk portalı** yalnızca DLP ilkenizi test edip etmediğinizi veya kurallarınızın uygulanmasını ve dosya izinlerinizin bu kurallara göre değiştirilmesini isteyip istemediğinizi belirleyin. Daha fazla bilgi için bkz. [DLP ilkesini açma](create-test-tune-dlp-policy.md#turn-on-a-dlp-policy).

DLP ilkeleri Microsoft Purview uyumluluk portalı yapılandırılır. DLP lisansı hakkında daha fazla bilgi için bkz. [Şirket içi veri kaybı önleme tarayıcısını kullanmaya başlama](dlp-on-premises-scanner-get-started.md).

> [!TIP]
> Yalnızca DLP ilkesini test ederken bile dosyalarınızı taramak, dosya izni raporları da oluşturur. Belirli dosya açıklarını araştırmak veya belirli bir kullanıcının taranan dosyalara maruz kalmasını keşfetmek için bu raporları sorgula.
>
> Yalnızca PowerShell'i kullanmak için bkz. [Tarayıcı ile DLP ilkesi kullanma - Yalnızca PowerShell](#use-powershell-to-configure-a-dlp-policy-with-the-scanner).
>

**Microsoft Purview uyumluluk portalı tarayıcıyla bir DLP ilkesi kullanmak için**:

1. Microsoft Purview uyumluluk portalı **İçerik tarama işleri** sekmesine gidin ve belirli bir içerik tarama işi seçin. Daha fazla bilgi için bkz. [İçerik tarama işi oluşturma](#create-a-content-scan-job).

2. **DLP ilke kurallarını etkinleştir'in** altında radyo düğmesini **Açık** olarak ayarlayın.
    
    > [!IMPORTANT]
    > Microsoft 365'te yapılandırılmış bir DLP ilkeniz olmadığı sürece DLP **kurallarını etkinleştir** ayarını **Açık** olarak ayarlamayın.
    >
    >Bu özelliğiN DLP ilkesi olmadan etkinleştirilmesi, tarayıcının hata oluşturmasına neden olur.

3. (İsteğe bağlı) **Depo sahibini ayarla** seçeneğini **Açık** olarak ayarlayın ve belirli bir kullanıcıyı depo sahibi olarak tanımlayın.
    
    Bu seçenek, tarayıcının bu depoda bulunan ve DLP ilkesiyle eşleşen dosyaların tanımlanan depo sahibine maruz kalmasını azaltmasını sağlar.

### <a name="dlp-policies-and-make-private-actions"></a>DLP ilkeleri ve *özel eylemler yapma*

*Özel eylemde bulunan* bir DLP ilkesi kullanıyorsanız ve dosyalarınızı otomatik olarak etiketlemek için tarayıcıyı kullanmayı planlıyorsanız, birleşik etiketleme istemcisinin [**UseCopyAndPreserveNTFSOwner**](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#preserve-ntfs-owners-during-labeling-public-preview) gelişmiş ayarını da tanımlamanızı öneririz.

Bu ayar, özgün sahiplerin dosyalarına erişimi korumasını sağlar.

Daha fazla bilgi için bkz. [İçerik tarama işi oluşturma](#create-a-content-scan-job) ve  [İçeriğe otomatik olarak duyarlılık etiketi uygulama](apply-sensitivity-label-automatically.md).

## <a name="change-which-file-types-to-protect"></a>Korunacak dosya türlerini değiştirme

Tarayıcı varsayılan olarak yalnızca Office dosya türlerini ve PDF dosyalarını korur.

Tarayıcıyı istemcinin yaptığı gibi tüm dosya türlerini koruyacak şekilde yapılandırmak veya ek, belirli dosya türlerini korumak gibi, bu davranışı gerektiği gibi değiştirmek için PowerShell komutlarını kullanın.

Tarayıcının etiketlerini indiren kullanıcı hesabı için geçerli olan bir etiket ilkesi için **PFileSupportedExtensions** adlı bir PowerShell gelişmiş ayarı belirtin.

İnternet erişimi olan bir tarayıcı için bu kullanıcı hesabı, Set-AIPAuthentication komutuyla *DelegatedUser* parametresi için belirttiğiniz hesaptır.

**Örnek 1**: Etiket ilkenizin "Tarayıcı" olarak adlandırıldığı tüm dosya türlerini korumak için tarayıcı için PowerShell komutu:

```PowerShell
Set-LabelPolicy -Identity Scanner -AdvancedSettings @{PFileSupportedExtensions="*"}
```

**Örnek 2**: Etiket ilkenizin "Tarayıcı" olarak adlandırıldığı Office dosyalarına ve PDF dosyalarına ek olarak .xml dosyaları ve .tiff dosyalarını korumak için tarayıcı için PowerShell komutu:

```PowerShell
Set-LabelPolicy -Identity Scanner -AdvancedSettings @{PFileSupportedExtensions=ConvertTo-Json(".xml", ".tiff")}
```

Daha fazla bilgi için bkz. [Korunacak dosya türlerini değiştirme](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#change-which-file-types-to-protect).

## <a name="upgrade-your-scanner"></a>Tarayıcınızı yükseltme

Tarayıcıyı daha önce yüklediyseniz ve yükseltmek istiyorsanız [, Bilgi koruma tarayıcısını yükseltme](/previous-versions/azure/information-protection/rms-client/client-admin-guide#upgrading-the-azure-information-protection-scanner) bölümünde açıklanan yönergeleri kullanın.

Ardından tarayıcınızı her zamanki gibi [yapılandırıp](deploy-scanner-configure-install.md) [kullanın ve tarayıcınızı](deploy-scanner-manage.md) yükleme adımlarını atlayın.

## <a name="edit-data-repository-settings-in-bulk"></a>Veri deposu ayarlarını toplu olarak düzenleme

Çeşitli depolarda tarayıcınızda değişiklik yapmak için **Dışarı** ve **İçeri Aktar** düğmelerini kullanın.

Bu şekilde, aynı değişiklikleri Azure portal veya Microsoft Purview uyumluluk portalı el ile birkaç kez yapmanız gerekmez.

Örneğin, çeşitli SharePoint veri depolarında yeni bir dosya türünüz varsa, bu depoların ayarlarını toplu olarak güncelleştirmek isteyebilirsiniz.

**Microsoft Purview uyumluluk portalı depolar arasında toplu olarak değişiklik yapmak için:**

1. Microsoft Purview uyumluluk portalı belirli bir içerik tarama işi seçin ve bölmedeki **Depolar** sekmesine gidin. **Dışarı Aktar** seçeneğini belirleyin.

2. Değişikliğinizi yapmak için dışarı aktarılan dosyayı el ile düzenleyin.

3. Güncelleştirmeleri depolarınıza geri aktarmak için aynı sayfadaki **İçeri Aktar** seçeneğini kullanın.

## <a name="use-the-scanner-with-alternative-configurations"></a>Tarayıcıyı alternatif yapılandırmalarla kullanma

Tarayıcı, içeriğinizi gerektiği gibi sınıflandırmak ve korumak için genellikle etiketleriniz için belirtilen koşulları arar.

Aşağıdaki senaryolarda tarayıcı, herhangi bir koşul yapılandırılmadan içeriğinizi tarar ve etiketleri yönetebilir:

- [Veri deposundaki tüm dosyalara varsayılan etiket uygulama](#apply-a-default-label-to-all-files-in-a-data-repository)
- [Veri deposundaki tüm dosyalardan mevcut etiketleri kaldırma](#remove-existing-labels-from-all-files-in-a-data-repository)
- [Tüm özel koşulları ve bilinen hassas bilgi türlerini tanımlama](#identify-all-custom-conditions-and-known-sensitive-information-types)

### <a name="apply-a-default-label-to-all-files-in-a-data-repository"></a>Veri deposundaki tüm dosyalara varsayılan etiket uygulama

Bu yapılandırmada, depodaki etiketlenmemiş tüm dosyalar, depo veya içerik tarama işi için belirtilen varsayılan etiketle etiketlenir. Dosyalar inceleme yapılmadan etiketlenir.

Aşağıdaki ayarları yapılandırın:

|Ayar  |Açıklama  |
|---------|---------|
|**Dosyaları içeriğe göre etiketleme**    |**Kapalı** olarak ayarlayın         |
|**Varsayılan etiket**     | **Özel** olarak ayarlayın ve ardından kullanılacak etiketi seçin       |
|**Varsayılan etiketi zorunlu kılma**     | Varsayılan etiketin tüm dosyalara uygulanmasını sağlamak için seçin. Bu etiket, **Yeniden etiketle ve** **Varsayılan etiketi zorla** ayarını açarak zaten etiketlenmiş olsalar bile        |

### <a name="remove-existing-labels-from-all-files-in-a-data-repository"></a>Veri deposundaki tüm dosyalardan mevcut etiketleri kaldırma

Bu yapılandırmada, etiketle birlikte koruma uygulandıysa koruma dahil olmak üzere tüm mevcut etiketler kaldırılır. Etiketlerden bağımsız olarak uygulanan koruma korunur.

Aşağıdaki ayarları yapılandırın:

|Ayar  |Açıklama  |
|---------|---------|
|**Dosyaları içeriğe göre etiketleme**    |**Kapalı** olarak ayarlayın         |
|**Varsayılan etiket**     | **Yok** olarak ayarla  |
|**Dosyaları yeniden etiketleme** | **Varsayılan etiketi zorunlu kılma** ayarı **Açık** olarak ayarlandığında Açık olarak ayarlayın |

### <a name="identify-all-custom-conditions-and-known-sensitive-information-types"></a>Tüm özel koşulları ve bilinen hassas bilgi türlerini tanımlama

Bu yapılandırma, tarayıcı için tarama hızları pahasına sahip olduğunuzu fark etmeyebilecek hassas bilgileri bulmanıza olanak tanır.

**Bulunabilecek Bilgi türlerini** **Tümü** olarak ayarlayın.

Etiketlemeye yönelik koşulları ve bilgi türlerini tanımlamak için tarayıcı, belirtilen özel hassas bilgi türlerini ve etiketleme yönetim merkezinizde tanımlandığı gibi seçilebilecek yerleşik hassas bilgi türlerinin listesini kullanır.

## <a name="optimize-scanner-performance"></a>Tarayıcı performansını iyileştirme

> [!NOTE]
> Tarayıcı performansı yerine tarayıcı bilgisayarının yanıt hızını artırmak istiyorsanız, tarayıcı [tarafından kullanılan iş parçacığı sayısını sınırlamak](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#limit-the-number-of-threads-used-by-the-scanner) için gelişmiş bir istemci ayarı kullanın.

Tarayıcı performansını iyileştirmenize yardımcı olması için aşağıdaki seçenekleri ve yönergeleri kullanın:

|Seçeneği  |Açıklama  |
|---------|---------|
|**Tarayıcı bilgisayar ve taranan veri deposu arasında yüksek hızlı ve güvenilir bir ağ bağlantısına sahip olun**     |  Örneğin, tarayıcı bilgisayarı aynı LAN'a veya tercihen taranan veri deposuyla aynı ağ kesimine yerleştirin. <br /><br />Ağ bağlantısının kalitesi tarayıcı performansını etkiler çünkü dosyaları incelemek için tarayıcı dosyaların içeriğini tarayıcı hizmetini çalıştıran bilgisayara aktarır. <br /><br />Verilerin seyahat etmek için gereken ağ atlamalarını azaltmak veya ortadan kaldırmak ağınızdaki yükü de azaltır.      |
|**Tarayıcı bilgisayarın kullanılabilir işlemci kaynaklarına sahip olduğundan emin olun**     | Dosya içeriğinin incelenmesi, dosyaların şifrelenmesi ve şifresinin çözülmesi işlemci açısından yoğun eylemlerdir. <br /><br />İşlemci kaynakları eksikliğinin tarayıcı performansını olumsuz etkileyip etkilemediğini belirlemek için, belirtilen veri depolarınızın tipik tarama döngülerini izleyin.        |
|**Tarayıcının birden çok örneğini yükleme** | Tarayıcı için özel bir küme adı belirttiğinizde, tarayıcı aynı SQL server örneğinde birden çok yapılandırma veritabanını destekler. <br /><br />**İpucu**: Birden çok tarayıcı aynı kümeyi paylaşarak tarama sürelerini hızlandırabilir. Tarayıcıyı aynı veritabanı örneğine sahip birden çok makineye yüklemeyi planlıyorsanız ve tarayıcılarınızın paralel çalışmasını istiyorsanız, tüm tarayıcılarınızı aynı küme adını kullanarak yüklemeniz gerekir.|
|**Alternatif yapılandırma kullanımınızı denetleme** |Tarayıcı dosya içeriğini incelemediğinden, tüm dosyalara varsayılan bir etiket uygulamak için [alternatif yapılandırmayı](#use-the-scanner-with-alternative-configurations) kullandığınızda tarayıcı daha hızlı çalışır. <br/><br />Tüm özel koşulları ve bilinen hassas bilgi türlerini tanımlamak için [alternatif yapılandırmayı](#use-the-scanner-with-alternative-configurations) kullandığınızda tarayıcı daha yavaş çalışır.|

### <a name="additional-factors-that-affect-performance"></a>Performansı etkileyen ek faktörler

Tarayıcı performansını etkileyen ek faktörler şunlardır:

|Faktör  |Açıklama  |
|---------|---------|
|**Yükleme/yanıt süreleri**     |Taranacak dosyaları içeren veri depolarının geçerli yük ve yanıt süreleri de tarayıcı performansını etkiler.         |
|**Tarayıcı modu** (Bulma / Zorlama)    | Bulma modu genellikle zorlama modundan daha yüksek tarama hızına sahiptir. <br /><br />Bulma için tek bir dosya okuma eylemi gerekirken, zorlama modu için okuma ve yazma eylemleri gerekir.        |
|**İlke değişiklikleri**     |Etiket ilkesinde otomatik etiketlemede değişiklik yaptıysanız tarayıcınızın performansı etkilenebilir. <br /><br />Tarayıcının her dosyayı incelemesi gerektiğinde ilk tarama döngünüz, varsayılan olarak yalnızca yeni ve değiştirilmiş dosyaları inceleyen sonraki tarama döngülerinden daha uzun sürer. <br /><br />Koşulları veya otomatik etiketleme ayarlarını değiştirirseniz, tüm dosyalar yeniden taranır. Daha fazla bilgi için bkz. [Dosyaları yeniden tarama](deploy-scanner-manage.md#rescanning-files).|
|**Regex yapıları**    | Tarayıcı performansı, özel koşullar için regex ifadelerinizin yapısından etkilenir. <br /><br /> Yoğun bellek tüketiminden ve zaman aşımları riskini (dosya başına 15 dakika) önlemek için, verimli desen eşleştirmesi için regex ifadelerinizi gözden geçirin. <br /><br />Örneğin: <br />- [Doyumsuz niceleyicilerden](/dotnet/standard/base-types/quantifiers-in-regular-expressions) kaçının <br />- Bunun yerine gibi yakalama olmayan grupları `(?:expression)` kullanın `(expression)`    |
|**Günlük düzeyi**     |  Günlük düzeyi seçenekleri arasında tarayıcı raporları için **Hata Ayıklama**, **Bilgi**, **Hata** ve **Kapalı** seçenekleri bulunur.<br /><br />- **En** iyi performansta kapalı sonuçlar <br />- **Hata ayıklama** tarayıcıyı önemli ölçüde yavaşlatır ve yalnızca sorun giderme için kullanılmalıdır. <br /><br />Daha fazla bilgi için [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration) cmdlet'i için *ReportLevel* parametresine bakın.       |
|**Taranan dosyalar**     |- Excel dosyaları dışında, Office dosyaları PDF dosyalarına göre daha hızlı taranır. <br /><br />- Korumasız dosyaları taramak korumalı dosyalara göre daha hızlıdır. <br /><br />- Büyük dosyaların taranmalarının küçük dosyalardan daha uzun olduğu açıktır.         |

## <a name="use-powershell-to-configure-the-scanner"></a>Tarayıcıyı yapılandırmak için PowerShell kullanma

Bu bölümde, Microsoft Purview uyumluluk portalı tarayıcı sayfalarına erişiminiz olmadığında tarayıcıyı yapılandırmak ve yüklemek için gereken adımlar açıklanır ve yalnızca PowerShell kullanılmalıdır.

> [!IMPORTANT]
> - Bazı adımlar, uyumluluk portalındaki tarayıcı sayfalarına erişip erişemediğinize ve aynı olmasına bakılmaksızın PowerShell gerektirir. Bu adımlar için, bu makalede belirtilen önceki yönergelere bakın.
>
> - Azure China 21Vianet tarayıcısıyla çalışıyorsanız, burada ayrıntılı olarak sunulan yönergelere ek olarak ek adımlar gerekir. Daha fazla bilgi için bkz. [21Vianet tarafından sağlanan Office 365 için Azure Information Protection desteği](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection).

Daha fazla bilgi için bkz [. Desteklenen PowerShell cmdlet'leri](#supported-powershell-cmdlets).

**Tarayıcınızı yapılandırmak ve yüklemek için**:

1. PowerShell kapalı olarak başlayın. AIP istemcisini ve tarayıcısını daha önce yüklediyseniz, **AIPScanner** hizmetinin durdurulduğunu doğrulayın.

2. **Yönetici olarak çalıştır** seçeneğiyle bir Windows PowerShell oturumu açın.

3. Tarayıcınızı SQL server örneğine yüklemek için [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) komutunu, küme adınızı tanımlamak için **Küme** parametresiyle çalıştırın.

    Uyumluluk portalındaki tarayıcı sayfalarına erişip erişemediğinize bakılmaksızın bu adım aynıdır. Daha fazla bilgi için bu makaledeki önceki yönergelere bakın: [Tarayıcıyı yükleme](#install-the-scanner)

4. Tarayıcınızla kullanmak üzere bir Azure belirteci alın ve sonra yeniden kimlik doğrulaması yapın. 

    Uyumluluk portalındaki tarayıcı sayfalarına erişip erişemediğinize bakılmaksızın bu adım aynıdır. Daha fazla bilgi için bu makaledeki önceki yönergelere bakın: [Tarayıcı için Azure AD belirteci alma](#get-an-azure-ad-token-for-the-scanner).

5. <a name="powershell"></a>Tarayıcıyı çevrimdışı modda çalışacak şekilde ayarlamak için [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet'ini çalıştırın. Çalıştırmak:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

6. Varsayılan içerik tarama işini oluşturmak için [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet'ini çalıştırın.

    **Set-AIPScannerContentScanJob** cmdlet'inde gerekli olan tek parametre **Zorlama'dır**. Ancak, şu anda içerik tarama işiniz için diğer ayarları tanımlamak isteyebilirsiniz. Örneğin:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    Yukarıdaki söz dizimi, yapılandırmaya devam ederken aşağıdaki ayarları yapılandırıyor:

    - Tarayıcının çalışma zamanlamasını *el ile* çalışır halde tutar
    - Duyarlılık etiketi ilkesine göre bulunabilecek bilgi türlerini ayarlar
    - Duyarlılık etiketi ilkesini zorunlu *kılmaz*
    - Duyarlılık etiketi ilkesi için tanımlanan varsayılan etiketi kullanarak dosyaları içeriğe göre otomatik olarak etiketler
    - Dosyaların yeniden etiketlenmesine izin *vermiyor*
    - Değerlere göre *değiştirme tarihi*, *son değiştirme* ve *değiştirme* dahil olmak üzere tarama ve otomatik etiketleme sırasında dosya ayrıntılarını korur
    - Çalışırken .msg ve .tmp dosyalarını dışlamak için tarayıcıyı ayarlar
    - Tarayıcıyı çalıştırırken kullanmak istediğiniz hesabın varsayılan sahibini ayarlar

7. İçerik tarama işinizde taramak istediğiniz depoları tanımlamak için [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet'ini kullanın. Örneğin şunu çalıştırın:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```

    Eklediğiniz deponun türüne bağlı olarak aşağıdaki söz dizimlerinden birini kullanın:

    - Ağ paylaşımı için kullanın `\\Server\Folder`.
    - SharePoint kitaplığı için kullanın `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
    - Yerel yol için: `C:\Folder`
    - UNC yolu için: `\\Server\Folder`

    > [!NOTE]
    > Joker karakterler desteklenmez ve WebDav konumları desteklenmez.
    >
    > Daha sonra depoyu değiştirmek için bunun yerine [Set-AIPScannerRepository cmdlet'ini](/powershell/module/azureinformationprotection/set-aipscannerrepository) kullanın. 

    **Paylaşılan Belgeler** için bir SharePoint yolu eklerseniz:
    - **Paylaşılan Belgeler'deki** tüm belgeleri ve tüm klasörleri taramak istediğinizde, yolda Paylaşılan Belgeler'i belirtin.
    Örneğin: `http://sp2013/SharedDocuments`
    - Paylaşılan **Belgeler** altındaki bir alt klasörden tüm belgeleri ve tüm klasörleri taramak istediğinizde, yolda Belgeler'i belirtin.
    Örneğin: `http://sp2013/Documents/SalesReports`
    - Alternatif olarak, yalnızca SharePoint'inizin **FQDN'sini** belirtin; örneğin `http://sp2013` , bu [URL'nin altındaki belirli bir URL ve alt başlıklar altında tüm SharePoint sitelerini ve alt sitelerini bulup tarayın](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) . Bunu etkinleştirmek için tarayıcı **Site Toplayıcı Denetçisi** hakları verin.


    SharePoint yolları eklerken aşağıdaki söz dizimini kullanın:

    |Yol  |Sözdizimi  |
    |---------|---------|
    |**Kök yol**     | `http://<SharePoint server name>` <br /><br />Tarayıcı kullanıcısı için izin verilen tüm site koleksiyonları dahil olmak üzere tüm siteleri tarar. <br />Kök içeriği otomatik olarak bulmak için [ek izinler](/previous-versions/azure/information-protection/quickstart-findsensitiveinfo#permission-users-to-scan-sharepoint-repositories) gerektirir        |
    |**Belirli SharePoint alt sitesi veya koleksiyonu**     | Aşağıdakilerden biri: <br />- `http://<SharePoint server name>/<subsite name>` <br />- `http://SharePoint server name>/<site collection name>/<site name>` <br /><br />Site koleksiyonu içeriğini otomatik olarak bulmak için [ek izinler](/previous-versions/azure/information-protection/quickstart-findsensitiveinfo#permission-users-to-scan-sharepoint-repositories) gerektirir         |
    |**Belirli SharePoint kitaplığı**     | Aşağıdakilerden biri: <br />- `http://<SharePoint server name>/<library name>` <br />- `http://SharePoint server name>/.../<library name>`       |
    |**Belirli SharePoint klasörü**     | `http://<SharePoint server name>/.../<folder name>`        |

Gerekirse aşağıdaki adımlarla devam edin:

- [Çin'deki müşteriler için yapılandırma](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection)
- [Bulma döngüsü çalıştırma ve tarayıcı için raporları görüntüleme](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Tarayıcıyı sınıflandırma ve koruma uygulayacak şekilde yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Tarayıcıyla DLP ilkesi yapılandırmak için PowerShell kullanma](#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

### <a name="use-powershell-to-configure-the-scanner-to-apply-classification-and-protection"></a>Tarayıcıyı sınıflandırma ve koruma uygulayacak şekilde yapılandırmak için PowerShell kullanma

1. İçerik tarama işinizi zamanlamanızı her zaman olarak ayarlayıp duyarlılık ilkenizi zorunlu kılacak şekilde güncelleştirmek için [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet'ini çalıştırın.

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Always -Enforce On
    ```

    > [!TIP]
    > Bu bölmedeki dosya özniteliklerinin değiştirilip değiştirilmediği ve tarayıcının dosyaları yeniden etiketleyip etiketleyemeyeceği gibi diğer ayarları değiştirmek isteyebilirsiniz. Kullanılabilir ayarlar hakkında daha fazla bilgi için [powershell belgelerinin tamamına bakın](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob).

2. İçerik tarama işinizi çalıştırmak için [Start-AIPScan](/powershell/module/azureinformationprotection/start-aipscan) cmdlet'ini çalıştırın:

    ```PowerShell
    Start-AIPScan
    ```

Tarayıcı artık sürekli çalışacak şekilde zamanlanmıştır. Tarayıcı tüm yapılandırılmış dosyalar arasında çalıştığında, yeni ve değiştirilmiş dosyaların bulunması için otomatik olarak yeni bir döngü başlatır.

### <a name="use-powershell-to-configure-a-dlp-policy-with-the-scanner"></a>Tarayıcıyla DLP ilkesi yapılandırmak için PowerShell kullanma

[Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet'ini **-EnableDLP** parametresi **Açık** olarak ayarlanmış ve belirli bir depo sahibi tanımlanmış olarak yeniden çalıştırın.

Örneğin:

```powershell
Set-AIPScannerContentScanJob -EnableDLP On -RepositoryOwner 'domain\user'
```

## <a name="supported-powershell-cmdlets"></a>Desteklenen PowerShell cmdlet'leri

Bu bölümde, bilgi koruma tarayıcısı için desteklenen PowerShell cmdlet'leri ve tarayıcıyı yalnızca PowerShell ile yapılandırma ve yükleme yönergeleri listelenmektedir.

Tarayıcı için desteklenen cmdlet'ler şunlardır:

- [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository)

- [Export-AIPLogs](/powershell/module/azureinformationprotection/Export-AIPLogs)

- [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Get-AIPScannerConfiguration)

- [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob)

- [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository)

- [Get-AIPScannerStatus](/powershell/module/azureinformationprotection/Get-AIPScannerStatus)

- [Get-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryConfiguration)

- [Get-MIPNetworkDiscoveryJobs](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryJobs)

- [Get-MIPNetworkDiscoveryStatus](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryStatus)

- Get-MIPScannerContentScanJob

- [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository)

- [Import-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Import-AIPScannerConfiguration)

- [Set-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/set-mipnetworkdiscovery)

- [Import-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Import-MIPNetworkDiscoveryConfiguration)

- [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)

- [Install-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Install-MIPNetworkDiscovery)

- Remove-MIPScannerContentScanJob

- [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

- [Set-AIPScanner](/powershell/module/azureinformationprotection/Set-AIPScanner)

- [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration)

- [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob)

- [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository)

- [Set-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Set-MIPNetworkDiscoveryConfiguration)

- Set-MIPScannerContentScanJob

- [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository)

- [Başlangıç-AIPScan](/powershell/module/azureinformationprotection/Start-AIPScan)

- [Start-AIPScanDiagnostics](/powershell/module/azureinformationprotection/Start-AIPScannerDiagnostics)

- [Start-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Start-MIPNetworkDiscovery)

- [AIPScan'i Durdur](/powershell/module/azureinformationprotection/Stop-AIPScan)

- [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob)

- [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

- [Uninstall-AIPScanner](/powershell/module/azureinformationprotection/Uninstall-AIPScanner)

- [Uninstall-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Uninstall-MIPNetworkDiscovery)

- [Update-AIPScanner](/powershell/module/azureinformationprotection/Update-AIPScanner)


## <a name="next-steps"></a>Sonraki adımlar

Tarayıcınızı yükleyip yapılandırdıktan sonra [dosyalarınızı taramaya](deploy-scanner-manage.md) başlayın.