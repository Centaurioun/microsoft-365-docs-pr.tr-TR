---
title: Yöneticiler için Office Application Guard
keywords: application guard, koruma, yalıtım, yalıtılmış kapsayıcı, donanım yalıtımı
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection: m365-security
description: Donanım tabanlı yalıtımda en son bilgileri edinin. Açıklardan yararlanmalar veya kötü amaçlı bağlantılar gibi mevcut ve yeni ortaya çıkan saldırıların çalışanların üretkenliğini ve kurumsal güvenliğini kesintiye uğratmasını önleyin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 14f5cdffb0bc7aeeda6fac383c8d716260dba15e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633228"
---
# <a name="application-guard-for-office-for-admins"></a>Yöneticiler için Office Application Guard

**Şunlar için geçerlidir:** Word, Excel ve Microsoft 365 için PowerPoint Uygulamaları, Windows 10 Enterprise Windows 11 Enterprise

Office için Microsoft Defender Application Guard (Office için Application Guard), güvenilmeyen dosyaların güvenilir kaynaklara erişmesini önlemeye yardımcı olur ve kuruluşunuzun yeni ve yeni saldırılara karşı güvende kalmasını sağlar. Bu makalede, Office için Application Guard için desteklenen cihazları ayarlama işlemi yöneticilere yol gösterilir. 

## <a name="prerequisites"></a>Önkoşullar

### <a name="licensing-requirements"></a>Lisans gereksinimleri

* Microsoft 365 E5 veya Microsoft 365 E5 Güvenlik
* [Microsoft 365'te Güvenli Belgeler](/microsoft-365/security/office-365-security/safe-docs)

### <a name="minimum-hardware-requirements"></a>En düşük donanım gereksinimleri

* **CPU**: 64 bit, 4 çekirdek (fiziksel veya sanal), sanallaştırma uzantıları (Intel VT-x VEYA AMD-V), Çekirdek i5 eşdeğeri veya üzeri önerilir
* **Fiziksel bellek**: 8 GB RAM
* **Sabit disk**: Sistem sürücüsünde 10 GB boş alan (SSD önerilir)

### <a name="minimum-software-requirements"></a>En düşük yazılım gereksinimleri

* **Windows**: Windows 10 Enterprise sürümü, İstemci Derlemesi sürüm 2004 (20H1) derlemesi 19041 veya üzeri. Windows 11 tüm sürümleri desteklenir.
* **Office**: 16.0.13530.10000 veya sonraki derlemelerle Microsoft 365 Uygulamaları. Geçerli Kanal ve Aylık Kurumsal Kanal yüklemeleri için bu, sürüm 2011'e eşittir. Semi-Annual Enterprise Channel ve Semi-Annual Enterprise Channel (Önizleme) için en düşük sürüm 2108 veya üzeridir. Hem 32 bit hem de 64 bit sürümler desteklenir.
* **Güncelleştirme paketi**: Windows 10 toplu aylık güvenlik güncelleştirmesi [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Ayrıntılı sistem gereksinimleri için bkz. [Microsoft Defender Application Guard için sistem gereksinimleri](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Ayrıca, lütfen bilgisayar üreticinizin sanallaştırma teknolojisini etkinleştirme kılavuzlarına bakın.
Microsoft 365 Uygulamaları güncelleştirme kanalları hakkında daha fazla bilgi edinmek için bkz. [Microsoft 365 Uygulamaları için güncelleştirme kanallarına genel bakış](/deployoffice/overview-update-channels).

## <a name="deploy-application-guard-for-office"></a>Office için Application Guard dağıtma

### <a name="enable-application-guard-for-office"></a>Office için Application Guard etkinleştirme

1. (yalnızca Windows 10) **Kb4571756 toplu aylık güvenlik güncelleştirmelerini Windows 10** indirip yükleyin. 

2. Windows Özellikleri'nin altında **Microsoft Defender Application Guard'ı** ve **ardından Tamam'ı** seçin. Application Guard özelliğinin etkinleştirilmesi sistemin yeniden başlatılmasını ister. Şimdi veya 3. adımdan sonra yeniden başlatmayı seçebilirsiniz.

   :::image type="content" source="../../media/ag03-deploy.png" alt-text="AG'yi gösteren Windows Özellikleri iletişim kutusu" lightbox="../../media/ag03-deploy.png":::

   Bu özellik, yönetici olarak aşağıdaki PowerShell komutu çalıştırılarak da etkinleştirilebilir:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. grup ilkesi Düzenleyicisi penceresinde **, Windows Bileşenleri -> Microsoft Defender Application Guard > Bilgisayar Yapılandırması -> Yönetim Şablonları ->** genişletin. **Yönetilen Modda Microsoft Defender Application Guard aç** ayarını etkinleştirin. Seçenekler'in altındaki değeri **2** veya **3** olarak ayarlayın. 

   :::image type="content" source="../../media/ag04-deploy.png" alt-text="Ag'yi Yönetilen Modda açma seçeneği" lightbox="../../media/ag04-deploy.png":::

   Alternatif olarak, karşılık gelen CSP ilkesini ayarlayabilirsiniz:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Veri türü: **Tamsayı** <br> Değer: **2**

4. Sistemi yeniden başlatın.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Tam veri göndermek için Tanılama & geri bildirimini ayarlama

> [!NOTE]
> Ancak bu gerekli değildir, ancak isteğe bağlı tanılama verilerini yapılandırmak bildirilen sorunları tanılamaya yardımcı olur.

Bu adım, sorunları tanımlamak ve düzeltmek için gereken verilerin Microsoft'a ulaşmasını sağlar. Windows cihazınızda tanılamayı etkinleştirmek için şu adımları izleyin:

1. Başlat menüsünden **Ayarlar'ı** açın.

2. **Windows Ayarları'nda** **Gizlilik'i** seçin.

3. Gizlilik bölümünde **Tanılama & geri bildirim'i** ve **ardından İsteğe bağlı tanılama verileri'ne** tıklayın.

Windows tanılama ayarlarını yapılandırma hakkında daha fazla bilgi için bkz. [Kuruluşunuzda Windows tanılama verilerini yapılandırma](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Office için Application Guard etkinleştirildiğini ve çalıştığını onaylayın

Office için Application Guard etkinleştirildiğini onaylamadan önce: 
1. İlkelerin dağıtıldığı bir cihazda Word, Excel veya PowerPoint'i başlatın. 
2. Başlattığınız uygulamadan **Dosya -> Hesabı'na** gidin. Hesap sayfasında, beklenen lisansın gösterildiğini doğrulayın.

Office için Application Guard etkinleştirildiğini onaylamak için güvenilmeyen bir belge açın. Örneğin, İnternet'ten indirilen bir belgeyi veya kuruluşunuzun dışındaki bir kişiden gelen bir e-posta ekini açabilirsiniz.

Güvenilmeyen bir dosyayı ilk kez açtığınızda, aşağıdaki örneğe benzer bir Office giriş ekranı görürsünüz. Office için Application Guard etkinleştiriliyor ve dosya açılıyor. Güvenilmeyen dosyaların sonraki açılışları genellikle daha hızlıdır.

:::image type="content" source="../../media/ag08-confirm.png" alt-text="Office uygulaması giriş sayfası" lightbox="../../media/ag08-confirm.png":::

Dosya açıldıktan sonra, dosyanın Office için Application Guard içinde açık olduğunu belirten birkaç görsel gösterge vardır:

* Şeritteki açıklama balonu

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="Küçük App Guard notunu gösteren Belge dosyası" lightbox="../../media/ag09-confirm.png":::

* Görev çubuğunda kalkan bulunan uygulama simgesi

  ![Görev çubuğundaki simge.](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Office için Application Guard yapılandırma

Office, Office için Application Guard yapılandırmak için aşağıdaki ilkeleri destekler. Bu ilkeler grup ilkeleri veya [Office bulut ilkesi hizmeti](/DeployOffice/overview-office-cloud-policy-service) aracılığıyla yapılandırılabilir.

> [!NOTE]
> Bu ilkelerin yapılandırılması, Office için Application Guard açılan dosyalar için bazı işlevleri devre dışı bırakabilir.

|Ilkesi|Açıklama|
|---|---|
|Office için Application Guard kullanma|Bu ilkeyi etkinleştirmek Word, Excel ve PowerPoint'i Office için Application Guard yerine Korumalı Görünüm yalıtım kapsayıcısını kullanmaya zorlar.|
|Office kapsayıcısı oluşturma öncesi için Application Guard yapılandırma|Bu ilke, geliştirilmiş çalışma zamanı performansı için Office kapsayıcısı için Application Guard önceden oluşturulup oluşturulmadığını belirler. Bu ilkeyi etkinleştirdiğinizde, kapsayıcıyı önceden oluşturmaya devam etmek için gün sayısını belirtebilir veya Office'in yerleşik buluşsal buluşsal öğesinin kapsayıcıyı önceden oluşturmasına izin vekleyebilirsiniz.
|Office için Application Guard'nde açılan Office belgeleri için kopyalama/yapıştırmaya izin verme|Bu ilkenin etkinleştirilmesi, kullanıcının Office için Application Guard'da açılan bir belgedeki içeriği kapsayıcı dışında açılmış bir belgeye kopyalamasını ve yapıştırmasını engeller.|
|Office için Application Guard donanım hızlandırmayı devre dışı bırakma|Bu ilke, Office için Application Guard grafikleri işlemek için donanım hızlandırma kullanıp kullanmadığını denetler. Bu ayarı etkinleştirirseniz, Office için Application Guard yazılım tabanlı (CPU) işleme kullanır ve herhangi bir üçüncü taraf grafik sürücüsünü yüklemez veya bağlı grafik donanımıyla etkileşim kurmaz.
|Office için Application Guard desteklenmeyen dosya türleri korumasını devre dışı bırakma|Bu ilke, Office için Application Guard desteklenmeyen dosya türlerinin açılmasını engelleyip engellemeyeceğini veya Korumalı Görünüm'e yeniden yönlendirmeyi etkinleştirip etkinleştirmeyeceğini denetler.
|Office için Application Guard açılan belgeler için kamera ve mikrofon erişimini kapatma|Bu ilkenin etkinleştirilmesi, Office için Application Guard içindeki kamera ve mikrofona Office erişimini kaldırır.|
|Office için Application Guard'de açılan belgelerden yazdırmayı kısıtlama|Bu ilkenin etkinleştirilmesi, kullanıcının Office için Application Guard'de açılan bir dosyadan yazdırabileceği yazıcıları sınırlar. Örneğin, bu ilkeyi kullanarak kullanıcıları yalnızca PDF'ye yazdıracak şekilde kısıtlayabilirsiniz.|
|Kullanıcıların dosyalarda Office koruması için Application Guard kaldırmasını engelleme|Bu ilkenin etkinleştirilmesi, Office koruması için Application Guard devre dışı bırakma veya Office için Application Guard dışında bir dosya açma seçeneğini (Office uygulama deneyimi içinde) kaldırır. <p> **Not:** Kullanıcılar, dosyadan web işareti özelliğini el ile kaldırarak veya belgeyi güvenilir bir konuma taşıyarak bu ilkeyi yine atlayabilir.|
|

> [!NOTE]
> Aşağıdaki ilkelerin geçerli olması için kullanıcıların oturumu kapatması ve Windows'ta yeniden oturum açması gerekir:
>
> * Office için Application Guard açılan belgeler için kopyalama/yapıştırmayı devre dışı bırakma
> * Office için Application Guard açılan belgeler için yazdırmayı kısıtlama
> * Office için Application Guard'de açılan belgelere kamera ve mikrofon erişimini kapatma

## <a name="submit-feedback"></a>Geri bildirim gönderme

### <a name="submit-feedback-via-feedback-hub"></a>Geri Bildirim Merkezi aracılığıyla geri bildirim gönderme

Office için Application Guard başlatırken herhangi bir sorunla karşılaşırsanız Geri Bildirim Merkezi aracılığıyla geri bildirim göndermeniz teşvik edilir:

1. **Geri Bildirim Merkezi uygulamasını** açın ve oturum açın.

2. Application Guard başlatırken bir hata iletişim kutusu alırsanız, yeni bir geri bildirim gönderimi başlatmak için hata iletişim kutusunda **Microsoft'a Bildir'i** seçin. Aksi takdirde, Application Guard için doğru kategoriyi seçmek için adresine gidin <https://aka.ms/mdagoffice-fb> ve sağ üst kısımdaki **Yeni geri bildirim ekle'yi seçin+&nbsp;**.

3. **Geri bildiriminizi özetleyin** kutusuna bir özet girin.

4. Sorunun ayrıntılı açıklamasını ve **daha ayrıntılı olarak açıkla** kutusuna hata ayıklamak için hangi adımları tamamladıysanız bunu girin ve **İleri'yi** seçin.

5. **Sorun'un** yanındaki baloncuğu seçin. Seçilen kategorinin **Güvenlik ve Gizlilik \> Microsoft Defender Application Guard – Office** olduğundan emin olun ve **İleri'yi** seçin.

6. **Yeni geri bildirim'i** ve ardından **İleri'yi** seçin.

7. Sorunla ilgili izlemeleri toplayın:

   1. **Sorunumu yeniden oluştur** kutucuğunu genişletin.

   2. Karşılaştığınız sorun Application Guard çalışırken oluşuyorsa bir Application Guard örneği açın. Örneğin açılması, Application Guard kapsayıcısının içinden ek izlemelerin toplanmasına olanak tanır.

   3. **Kaydı başlat'ı** seçin ve kutucuğun dönmesini bekleyin ve *Kaydı durdur* deyin.

   4. sorunu Application Guard ile tam olarak yeniden oluşturun. Çoğaltma, bir Application Guard örneği başlatmayı ve başarısız olana kadar beklemeyi veya çalışan bir Application Guard örneğinde bir sorunu yeniden oluşturmayı içerebilir.

   5. **Kaydı durdur** kutucuğunu seçin.

   6. Kapsayıcı tanılamalarının da toplanabilmesi için, gönderimden sonra birkaç dakika bile olsa tüm çalışan Application Guard örnekleri açık tutun.

8. Sorunla ilgili tüm ilgili ekran görüntülerini veya dosyaları ekleyin.

9. **Gönder'i** seçin.

### <a name="submit-feedback-via-one-customer-voice"></a>One Customer Voice aracılığıyla geri bildirim gönderme

Sorun, dosyalar Application Guard açıldığında ortaya çıkarsa Word, Excel ve PowerPoint'in içinden de geri bildirim gönderebilirsiniz. Ayrıntılı rehberlik için [Geri bildirim sağlama](https://insider.office.com/en-us/handbook#Provide-feedback) bölümüne bakın.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Uç Nokta için Microsoft Defender ve Office 365 için Microsoft Defender ile tümleştirme

Office için Application Guard, yalıtılmış ortamda gerçekleşen kötü amaçlı etkinliklerle ilgili izleme ve uyarı sağlamak için Uç Nokta için Microsoft Defender ile tümleşiktir.

[Microsoft E365 E5'teki Güvenli Belgeler](/microsoft-365/security/office-365-security/safe-docs), Office için Application Guard'de açılan belgeleri taramak için Uç Nokta için Microsoft Defender kullanan bir özelliktir. Ek bir koruma katmanı için, tarama sonuçları belirlenene kadar kullanıcılar Office için Application Guard bırakamaz.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve dikkat edilmesi gerekenler

* Office için Application Guard güvenilmeyen belgeleri yalıtarak güvenilen şirket kaynaklarına, intranete, kullanıcının kimliğine ve bilgisayardaki rastgele dosyalara erişememelerini sağlayan korumalı bir moddur. Sonuç olarak, bir kullanıcı bu tür erişime bağımlılığı olan bir özelliğe erişmeye çalışırsa (örneğin, disk üzerindeki yerel bir dosyadan resim ekleme), erişim başarısız olur ve aşağıdaki örneğe benzer bir istem görüntüler. Güvenilmeyen bir belgenin güvenilen kaynaklara erişmesini sağlamak için, kullanıcıların belgeden Application Guard korumasını kaldırması gerekir.

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="Güvenlik iletisini ve özellik durumunu belirten iletişim kutusu" lightbox="../../media/ag09-confirm.png":::

  > [!NOTE]
  > Kullanıcılara yalnızca dosyaya ve dosyanın kaynağına güveniyorlarsa korumayı kaldırmalarını önerin.

* Office için Application Guard makrolar ve ActiveX denetimleri gibi etkin içerik devre dışı bırakılır. Etkin içeriği etkinleştirmek için Application Guard koruması kaldırılmalıdır.

* Ağ paylaşımlarındaki güvenilmeyen dosyalar veya OneDrive, OneDrive İş veya SharePoint Online'dan paylaşılan dosyalar Application Guard salt okunur olarak açılır. Kullanıcılar kapsayıcıda çalışmaya devam etmek için bu tür dosyaların yerel bir kopyasını kaydedebilir veya doğrudan özgün dosyayla çalışmak için korumayı kaldırabilir.

* Bilgi Hakları Yönetimi (IRM) tarafından korunan dosyalar varsayılan olarak engellenir. Kullanıcılar bu tür dosyaları Korumalı Görünüm'de açmak isterse, yöneticinin kuruluş için desteklenmeyen dosya türleri için ilke ayarlarını yapılandırması gerekir.

* Kullanıcı oturumu kapatıp yeniden oturum açtığında veya cihaz yeniden başlatıldıktan sonra Office için Application Guard'deki Office uygulamalarında yapılan özelleştirmeler kalıcı olmaz.

* Yalnızca UIA çerçevesini kullanan Erişilebilirlik araçları, Office için Application Guard açılan dosyalar için erişilebilir bir deneyim sağlayabilir.

* Yüklemeden sonra Application Guard ilk kez başlatılması için ağ bağlantısı gereklidir. 

* Belgenin bilgi bölümünde *, Son Değiştiren* özelliği kullanıcı olarak **WDAGUtilityAccount** görüntüleyebilir. WDAGUtilityAccount, Application Guard tarafından kullanılan anonim hesaptır. Masaüstü kullanıcısının kimliği Application Guard kapsayıcısının içinde kullanılamaz.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Office için Application Guard için performans iyileştirmeleri

Application Guard, güvenilmeyen belgeleri sistemden yalıtmak için sanal makineye benzer bir sanallaştırılmış kapsayıcı kullanır. Office belgelerini açmak için kapsayıcı oluşturma ve Application Guard kapsayıcısını ayarlama işlemi, kullanıcılar güvenilmeyen bir belgeyi açtığında kullanıcı deneyimini olumsuz etkileyebilecek bir performans yüküne sahiptir.

Kullanıcılara beklenen dosya açma deneyimini sağlamak için, Application Guard bir sistemde aşağıdaki buluşsal yöntem karşılandığında kapsayıcıyı önceden oluşturmak için mantığı kullanır: Kullanıcı son 28 gün içinde bir dosyayı Korumalı Görünüm'de veya Application Guard açmıştır.

Bu buluşsal durum karşılandığında Office, Windows'ta oturum açtıktan sonra kullanıcı için bir Application Guard kapsayıcısı oluşturur. Bu ön oluşturma işlemi devam ederken sistem yavaş performansla karşılaşabilir, ancak işlem tamamlanır tamamlanmaz etki çözülür.

> [!NOTE]
> Kapsayıcıyı önceden oluşturmak için buluşsal yöntem için gereken ipuçları, office uygulamaları tarafından kullanıcı tarafından kullanılırken oluşturulur. Kullanıcı Office'i Application Guard etkinleştirildiği yeni bir sisteme yüklerse, kullanıcı sistemde güvenilmeyen bir belgeyi ilk kez açana kadar Office kapsayıcıyı önceden oluşturmaz. Kullanıcı, bu ilk dosyanın Application Guard açılmasının daha uzun sürdüğünü gözlemler.

## <a name="known-issues"></a>Bilinen sorunlar

* Web bağlantılarının (`http` veya `https`) seçilmesi tarayıcıyı açmaz.
* Kopyalama-yapıştırma koruma ilkesi için varsayılan ayar yalnızca metne pano erişimini etkinleştirmektir.
* Desteklenmeyen dosya türleri koruma ilkesi için varsayılan ayar, şifrelenmiş veya Bilgi Hakları Yönetimi (IRM) ayarlanmış güvenilmeyen desteklenmeyen dosya türlerinin açılmasını engellemektir. Bu, Microsoft Purview Bilgi Koruması duyarlılık etiketleri kullanılarak şifrelenen dosyaları içerir.
* CSV ve HTML dosyaları şu anda desteklenmiyor.
* Office için Application Guard şu anda NTFS sıkıştırılmış birimleriyle çalışmıyor. "ERROR_VIRTUAL_DISK_LIMITATION" hatası görüyorsanız lütfen birimin sıkıştırmasını kaldırmayı deneyin.
* .NET'e Güncelleştirmeler dosyaların Application Guard'da açılmamasına neden olabilir. Geçici bir çözüm olarak, kullanıcılar bu hatayla karşılaşınca cihazlarını yeniden başlatabilir. Sorun hakkında daha fazla bilgi için bkz[. Windows Defender Application Guard veya Windows Korumalı Alanı açmaya çalışırken hata iletisi alma](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
* [Daha fazla bilgi için lütfen sık sorulan sorular - Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) bölümüne bakın.
