---
title: Microsoft 365 Defender ile insan tarafından işletilen fidye yazılımı saldırılarını algılama
description: Bu makalede, Microsoft 365 Defender portalıyla yeni veya sürekli insan tarafından çalıştırılan fidye yazılımı saldırılarının proaktif olarak algılanması açıklanmaktadır
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection: M365-security-compliance.
ms.technology: m365d
f1.keywords: NOCSH
ms.openlocfilehash: 421e3cfbe3d16d0adc38e3fe1cbbcb7d64867eb9
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328397"
---
# <a name="detecting-human-operated-ransomware-attacks-with-microsoft-365-defender"></a>Microsoft 365 Defender ile insan tarafından işletilen fidye yazılımı saldırılarını algılama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Fidye yazılımı, dosyaları ve klasörleri yok eden veya şifreleyen, kritik verilere erişimi engelleyen veya kritik iş sistemlerini bozan bir tür gasp saldırısıdır. İki tür fidye yazılımı vardır:

* Emtia fidye yazılımı, kimlik avıyla veya cihazlar arasında yayılan ve fidye istemeden önce dosyaları şifreleyen kötü amaçlı yazılımdır.
* İnsan tarafından çalıştırılan fidye yazılımı, birden çok saldırı yöntemi kullanan aktif siber suçlular tarafından planlı ve eşgüdümlü bir saldırıdır. Çoğu durumda, kuruluşunuza sızmak, gasp etmeye değer varlıkları veya sistemleri bulmak ve ardından fidye talep etmek için bilinen teknikler ve araçlar kullanılır. Bir ağın güvenliğinin aşılması üzerine saldırgan, şifrelenebilen veya gasp edilebilen varlıkların ve sistemlerin keşfini yürütür. Saldırganlar daha sonra fidye istemeden önce verileri şifreler veya yok eder.

Bu makalede, aşağıdaki güvenlik hizmetleri için genişletilmiş bir algılama ve yanıt (XDR) çözümü olan Microsoft 365 Defender portalı ile yeni veya sürekli insan tarafından çalıştırılan fidye yazılımı saldırılarının proaktif olarak algılanması açıklanmaktadır:

* Uç Nokta için Microsoft Defender
* Office 365 için Microsoft Defender
* Kimlik için Microsoft Defender
* Microsoft Defender for Cloud Apps (uygulama idare eklentisi dahil)
* kimlik koruması Microsoft Azure AD
* IoT için Microsoft Defender
* Microsoft 365 Business Premium
* İş için Microsoft Defender

Fidye yazılımı saldırılarını önleme hakkında bilgi için bkz. [Fidye yazılımlarına ve gasplara karşı hızlı koruma](/security/compass/protect-against-ransomware-phase3).

## <a name="the-importance-of-proactive-detection"></a>Proaktif algılamanın önemi

İnsan tarafından çalıştırılan fidye yazılımı genellikle en değerli verilerinize ve sistemlerinize gerçek zamanlı olarak sızma ve bunları keşfetme adımlarını gerçekleştirebilecek etkin saldırganlar tarafından gerçekleştirildiğinden, fidye yazılımı saldırılarını algılamak için geçen süre çok önemlidir.

Fidye öncesi etkinlikler hızlı bir şekilde algılanırsa, ciddi bir saldırı olasılığı azalır. Fidye öncesi aşama genellikle şu teknikleri içerir: ilk erişim, keşif, kimlik bilgisi hırsızlığı, yanal hareket ve kalıcılık. Bu teknikler başlangıçta ilgisiz görünebilir ve genellikle radarın altında uçabilir. Bu teknikler fidye aşamasına yol açarsa, genellikle çok geç olur. Microsoft 365 Defender, büyük bir fidye yazılımı kampanyasının bir parçası olarak bu küçük ve ilgisiz olayları tanımlamaya yardımcı olabilir.

* Fidye öncesi aşamada algılandığında, saldırıyı kesintiye uğratmak ve düzeltmek için virüslü cihazları veya kullanıcı hesaplarını yalıtma gibi daha küçük ölçekli risk azaltmalar kullanılabilir.
* Algılama, dosyaları şifrelemek için kullanılan kötü amaçlı yazılımların dağıtıldığı durumlar gibi daha sonraki bir aşamada geliyorsa, saldırıyı kesintiye uğratmak ve düzeltmek için kapalı kalma süresine neden olabilecek daha agresif düzeltme adımlarının kullanılması gerekebilir.

Fidye yazılımı saldırısına yanıt verirken büyük olasılıkla iş işlemi kesintileri yaşanıyor. Fidye yazılımı saldırısının son aşaması genellikle büyük risklere sahip saldırganların neden olduğu kapalı kalma süresi veya ağ güvenliğini sağlamak ve size tam olarak araştırmanız için zaman vermek için kontrollü bir kapalı kalma süresi arasında bir seçimdir. Fidye ödemenizi asla önermeyiz. Fidye yazılımı şifre çözme anahtarı almak için siber suçlulara ödeme yapmak, şifrelenmiş verilerinizin geri yükleneceği konusunda hiçbir garanti sağlamaz. Bkz [. Fidye yazılımı yanıtı - Microsoft Güvenlik Blogu](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/).

Bir fidye yazılımı saldırısının etkisinin nitel ilişkisi ve algılama ve proaktif algılama ve yanıt için yanıt verme zamanınız aşağıdadır.

![Fidye yazılımı saldırısının etkisinin nitel ilişkisi ve algılama ve proaktif algılama ve yanıt olmadan yanıt verme zamanınız işletmenize olan etkiyi azaltarak daha hızlı yanıt verirsiniz.](../../media/defender/playbook-detecting-ransomware-m365-defender-qualitative-diagram.png)

### <a name="proactive-detection-via-common-malware-tools-and-techniques"></a>Yaygın kötü amaçlı yazılım araçları ve teknikleri aracılığıyla proaktif algılama

Çoğu durumda, insan tarafından çalıştırılan fidye yazılımı saldırganları kimlik avı, iş e-posta güvenliğinin aşılması (BEC) ve kimlik bilgisi hırsızlığı gibi iyi bilinen ve alanda test edilmiş kötü amaçlı yazılım taktiklerini, tekniklerini, araçlarını ve yordamlarını kullanır. Güvenlik analistleriniz, saldırganların kuruluşunuzda bir destek elde etmek için yaygın kötü amaçlı yazılım ve siber saldırı yöntemlerini nasıl kullandığını biliyor ve biliyor olmalıdır.

Fidye yazılımı saldırılarının yaygın kötü amaçlı yazılımlarla nasıl başladığına yönelik örnekleri görmek için şu kaynaklara bakın:

* [İnsan tarafından çalıştırılan fidye yazılımı saldırıları: Önlenebilir bir olağanüstü durum](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
* [Microsoft 365 Defender portalında fidye yazılımı tehdit analizi raporları](https://sip.security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,exposureLevel,MisconfiguredDevices,VulnerableDevices,reportType,createdOn,lastUpdatedOn,tags,flag)

Fidye öncesi kötü amaçlı yazılımlara, yüklere ve etkinliklere aşina olmak, analistlerinizin bir saldırının sonraki aşamalarını önlemek için neleri aramaları gerekenleri bilmelerine yardımcı olur.

## <a name="human-operated-ransomware-attack-tactics"></a>İnsan tarafından çalıştırılan fidye yazılımı saldırı taktikleri

İnsan tarafından çalıştırılan fidye yazılımı bilinen saldırı tekniklerini ve araçlarını kullanabileceğinden, analistlerinizin mevcut saldırı teknikleri ve araçlarıyla ilgili anlayışı ve deneyimi, SecOps ekibinizi odaklanmış fidye yazılımı algılama uygulamaları için hazırlarken değerli bir varlık olacaktır.

### <a name="attack-tactics-and-methods"></a>Saldırı taktikleri ve yöntemleri

Aşağıda, fidye yazılımı saldırganları tarafından aşağıdaki [MITRE ATT&CK](https://attack.mitre.org/tactics/enterprise/) taktikleri için kullanılan bazı tipik teknikler ve araçlar verilmiştir:

İlk erişim:

* RDP deneme yanılma gücü
* İnternet'e yönelik güvenlik açığı olan sistem
* Zayıf uygulama ayarları
* Kimlik avı postası

Kimlik bilgisi hırsızlığı:

* Mimikatz
* LSA gizli dizileri
* Kimlik bilgileri kasası
* Düz metinde kimlik bilgileri
* Hizmet hesaplarının kötüye kullanılması

Yanal hareket:

* Cobalt Strike
* WMI
* Yönetim araçlarının kötüye kullanılması
* PsExec

Kalıcılık:

* Yeni hesaplar
* GPO değişiklikleri
* Gölge BT araçları
* Görevleri zamanlama
* Hizmet kaydı

Savunma kaçamak:

* Güvenlik özelliklerini devre dışı bırakma
* Günlük dosyalarını temizleme
* Saldırı yapıt dosyalarını silme
* Değiştirilen dosyalardaki zaman damgalarını sıfırlama

Sızdırma:

* Hassas verilerin sızdırma etkisi (finansal kaldıraç):
* Verilerin yerinde ve yedeklerde şifrelenmesini
* Verilerin yerinde silinmesi ve yedeklemeler, önceki bir sızdırma işlemiyle birleştirilebilir
* Açığa çıkarılmış, hassas verilerin halka açık sızıntısı tehdidi

### <a name="what-to-look-for"></a>Aranacaklar

Güvenlik analistleri için zorluk, hassas verilerinizi veya kritik sistemlerinizi gasp etmek amacıyla bir uyarının daha büyük bir saldırı zincirinin parçası olduğunu anlamaktır. Örneğin, algılanan bir kimlik avı saldırısı şu olabilir:

* Bir kuruluşun finans departmanındaki birinin e-posta iletilerini görmek için tek seferlik bir saldırı.
* Bir saldırı zincirinin fidye öncesi bölümü, kullanıcı hesabı için kullanılabilir kaynakları bulmak ve daha yüksek ayrıcalık ve erişim düzeyine sahip diğer kullanıcı hesaplarını tehlikeye atmak için güvenliği aşılmış kullanıcı hesabı kimlik bilgilerini kullanmaktır.

Bu bölüm, güvenlik analizi için birden çok ilgili uyarıdan oluşan uyarılar ve olaylar oluşturan merkezi Microsoft 365 Defender portalına beslenen yaygın saldırı aşamalarını ve yöntemlerini ve sinyal kaynaklarını sağlar. Bazı durumlarda, saldırı verilerini görüntülemek için alternatif güvenlik portalları vardır.

#### <a name="initial-attacks-to-gain-entry"></a>Giriş kazanmak için ilk saldırılar

Saldırgan bir kullanıcı hesabının, cihazın veya uygulamanın güvenliğini aşmaya çalışır.

Saldırı yöntemi |Sinyal kaynağı |Alternatif güvenlik portalları
|:---|:---|:---
RDP deneme yanılma gücü|Uç Nokta için Defender|Bulut Uygulamaları için Defender
İnternet'e yönelik güvenlik açığı olan sistem|Windows güvenlik özellikleri, Sunucular için Microsoft Defender|
Zayıf uygulama ayarları      |Cloud Apps için Defender, uygulama idare eklentisiyle Cloud Apps için Defender|Bulut Uygulamaları için Defender |
Kötü amaçlı uygulama etkinliği      |Cloud Apps için Defender, uygulama idare eklentisiyle Cloud Apps için Defender|Bulut Uygulamaları için Defender |
Kimlik avı postası        |Office 365 için Defender
Azure AD hesaplarına karşı parola spreyi |Cloud Apps için Defender aracılığıyla Kimlik Koruması'nı Azure AD      |Bulut Uygulamaları için Defender
Şirket içi hesaplara karşı parola spreyi |Kimlik için Microsoft Defender
Cihaz güvenliğinin aşılmasına neden olan       |Uç Nokta için Defender
Kimlik bilgisi hırsızlığı       |Kimlik için Microsoft Defender
Ayrıcalığı yükseltme      |Kimlik için Microsoft Defender

#### <a name="recent-spike-in-otherwise-typical-behavior"></a>Aksi halde tipik davranışta son ani artış

Saldırgan, güvenliği aşacak ek varlıkları yoklama girişiminde bulunur.

Ani artış kategorisi        |Sinyal kaynağı                 |Alternatif güvenlik portalları
|:---                    |:---                              |:---
Oturum açma işlemleri: Çok sayıda başarısız deneme, kısa süre içinde birden çok cihazda oturum açma girişimi, birden çok ilk kez oturum açma vb. |Cloud Apps için Defender aracılığıyla Kimlik Koruması'nı Azure AD Kimlik için Microsoft Defender |Bulut Uygulamaları için Defender
Son etkin kullanıcı hesabı, grup, makine hesabı, uygulama |Cloud Apps için Defender (Azure AD), Kimlik için Defender (Active Directory Domain Services [AD DS] aracılığıyla kimlik koruması Azure AD) |Bulut Uygulamaları için Defender
Veri erişimi gibi son uygulama etkinliği |Uygulama idare eklentisine sahip Bulut için Defender Uygulamaları |Bulut Uygulamaları için Defender

#### <a name="new-activity"></a>Yeni etkinlik

Saldırgan, erişimlerini daha da ileriye taşıma, kötü amaçlı yazılım aracılarını yükleme veya algılamayı önleme amacıyla yeni varlıklar oluşturuyor.

Etkinlik     |Sinyal kaynağı           |Alternatif güvenlik portalı
|:---                |:---                        |:---
Yüklenen yeni uygulamalar |Uygulama idaresi eklentisiyle Cloud Apps için Defender |Bulut Uygulamaları için Defender
Yeni kullanıcı hesapları    |Azure Kimlik Koruması         |Bulut Uygulamaları için Defender
Rol değişiklikleri      |Azure Kimlik Koruması        |Bulut Uygulamaları için Defender

#### <a name="suspicious-behavior"></a>Şüpheli davranış

Saldırgan hassas bilgileri indirir, dosyaları şifreler veya kuruluş varlıklarını başka bir şekilde toplar veya zarar verir.

Davranış       |Sinyal kaynağı
|:---                  |:---
Birden çok cihaza yayılan kötü amaçlı yazılım |Uç Nokta için Defender
Kaynak tarama     |Uç Nokta için Defender, Kimlik için Defender
Posta kutusu iletme kurallarındaki değişiklikler |Office 365 için Defender
Veri sızdırma ve şifreleme |Office 365 için Defender

**Saldırgan Güvenliği Devre Dışı Bırakma için İzleme** – bu genellikle insan tarafından çalıştırılan fidye yazılımı (HumOR) saldırı zincirinin bir parçasıdır

* **Olay Günlüklerini Temizleme** – özellikle Güvenlik Olay günlüğü ve PowerShell İşlem günlükleri
* **Güvenlik araçlarını/denetimlerini devre dışı bırakma** (bazı gruplarla ilişkili)

## <a name="detect-ransomware-attacks-with-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalı ile fidye yazılımı saldırılarını algılama

Microsoft 365 Defender portalı algılamalar, etkilenen varlıklar, gerçekleştirilen otomatik eylemler ve aşağıdakilerin birleşimiyle ilgili kanıtlar hakkında bilgi için merkezi bir görünüm sağlar:

* Tam saldırı kapsamını, etkilenen varlıkları ve otomatik düzeltme eylemlerini sağlamak üzere bir saldırıyla ilgili uyarıları gruplandıran bir olay kuyruğu.
* Microsoft 365 Defender tarafından izlenen tüm uyarıları listeleyen bir uyarı kuyruğu.

### <a name="incident-and-alert-sources"></a>Olay ve uyarı kaynakları

Microsoft 365 Defender portalı, sinyalleri şu kaynaklardan merkezileştirir:

* Uç Nokta için Microsoft Defender
* Office 365 için Microsoft Defender
* Kimlik için Microsoft Defender
* Microsoft Defender for Cloud Apps (uygulama idare eklentisi dahil)
* Microsoft Azure AD Kimlik Koruması
* IoT için Microsoft Defender

Bu tabloda, Microsoft 365 Defender için bazı tipik saldırılar ve bunlara karşılık gelen sinyal kaynakları listelenir.

Saldırılar ve olaylar           |Sinyal kaynağı
|:---                         |:---
Bulut kimliği: Parola spreyi, çok sayıda başarısız deneme, kısa süre içinde birden fazla cihazda oturum açma girişimi, birden çok ilk kez oturum açma, son zamanlarda etkin olan kullanıcı hesapları |Azure AD Kimlik Koruması
Şirket içi kimlik (AD DS) güvenliğinin aşılmasına neden olur       |Kimlik için Microsoft Defender
Kimlik Avı              |Office 365 için Defender
Kötü amaçlı uygulamalar             |Cloud Apps için Defender veya uygulama idaresi eklentisiyle Cloud Apps için Defender
Uç nokta (cihaz) güvenliğinin aşılmasına neden olur         |Uç Nokta için Defender
IoT özellikli cihaz güvenliğinin aşılmasına neden olur          |IoT için Defender

### <a name="filtering-ransomware-identified-incidents"></a>Fidye yazılımı tarafından tanımlanan olayları filtreleme

Microsoft 365 Defender tarafından fidye yazılımı olarak kategorilere ayrılmış olaylar için olay kuyruğuna kolayca filtreleyebilirsiniz.

1. Microsoft 365 Defender portalı gezinti bölmesinde Olaylar **ve uyarılar > Olaylar'ı seçerek olaylar kuyruğuna** gidin.
2. **Filtreler'i** seçin.
3. **Kategoriler'in** altında **Fidye Yazılımı'nı** seçin, **Uygula'yı** seçin ve **filtreler bölmesini kapatın**.

Olaylar kuyruğu için her filtre ayarı, daha sonra bağlantı olarak kaydedip erişebileceğiniz bir URL oluşturur. Bu URL'ler yer işareti eklenebilir veya başka bir şekilde kaydedilebilir ve tek tıklamayla gerektiğinde kullanılabilir. Örneğin, aşağıdakiler için yer işaretleri oluşturabilirsiniz:

* "Fidye yazılımı" kategorisini içeren olaylar. İlgili [bağlantı](https://security.microsoft.com/incidents?filters=AlertStatus%3DNew%257CInProgress,category%3Dransomware&page_size=30&fields=expand,name,tags,severity,investigationStates,category,impactedEntities,alertCount,serviceSource,detectionSource,firstEventTime,lastEventTime,sensitivity,status,incidentAssignment,classification,determination,rbacGroup) aşağıdadır.
* Fidye yazılımı saldırıları gerçekleştirdiği bilinen belirtilen **Aktör** adına sahip olaylar.
* Fidye yazılımı saldırılarında kullanıldığı bilinen belirtilen **İlişkili tehdit** adına sahip olaylar.
* SecOps ekibinizin daha büyük, eşgüdümlü bir fidye yazılımı saldırısının parçası olduğu bilinen olaylar için kullandığı özel etiketi içeren olaylar.

### <a name="filtering-ransomware-identified-threat-analytics-reports"></a>Fidye yazılımı tarafından tanımlanan tehdit analizi raporlarını filtreleme

Olay kuyruğundaki olayları filtrelemeye benzer şekilde, fidye yazılımı içeren raporlar için tehdit analizi raporlarını filtreleyebilirsiniz.

1. Gezinti bölmesinde **Tehdit analizi'ni** seçin.
2. **Filtreler'i** seçin.
3. **Tehdit etiketleri'nin** altında **Fidye Yazılımı'nı** seçin, **Uygula'yı** seçin ve **filtreler bölmesini kapatın**.

Bu bağlantıya da tıklayabilirsiniz.

Birçok tehdit analizi raporunun **Algılama ayrıntıları** bölümünde, tehdit için oluşturulan uyarı adlarının listesini görebilirsiniz.

### <a name="microsoft-365-defender-apis"></a>Microsoft 365 Defender API'leri

Kiracınızdaki Microsoft 365 Defender olayları ve uyarı verilerini sorgulamak için Microsoft 365 Defender API'lerini de kullanabilirsiniz. Özel bir uygulama verileri filtreleyebilir, özel ayarlara göre filtreleyebilir ve ardından doğrudan bu uyarıya veya olaya gitmek için kolayca seçebileceğiniz uyarıların ve olayların bağlantılarının filtrelenmiş bir listesini sağlayabilir. Bkz[. Microsoft 365 Defender |'de olay API'sini listeleme Microsoft Docs](/api-list-incidents.md). Ayrıca SIEM'inizi Microsoft Defender ile tümleştirebilirsiniz. Bkz. [SIEM araçlarınızı Microsoft 365 Defender ile tümleştirme](/configure-siem-defender.md).

### <a name="microsoft-365-defender-sentinel-integration"></a>Microsoft 365 Defender Sentinel Tümleştirmesi

Microsoft Sentinel'in Microsoft 365 Defender olay tümleştirmesi, tüm Microsoft 365 Defender olaylarını Microsoft Sentinel'e akışla aktarıp her iki portal arasında eşitlenmiş durumda tutmanıza olanak tanır. Olaylar ilişkili tüm uyarıları, varlıkları ve ilgili bilgileri içerir. Sentinel'de olaylar iki yönlü olarak Microsoft 365 Defender eşitlenmiş olarak kalır ve olay araştırmanızdaki her iki portalın avantajlarından yararlanmanıza olanak sağlar. [Bkz. Microsoft Sentinel ile tümleştirme Microsoft 365 Defender](/azure/sentinel/microsoft-365-defender-sentinel-integration).

### <a name="proactive-scanning-with-advanced-hunting"></a>Gelişmiş avcılık ile proaktif tarama

[Gelişmiş tehdit avcılığı](/advanced-hunting-overview.md) , tehdit göstergelerini ve varlıkları bulmak için ağınızdaki olayları keşfetmenize ve incelemenize olanak tanıyan sorgu tabanlı bir tehdit avcılığı aracıdır. Bu esnek ve özelleştirilebilir analiz aracı, hem bilinen hem de olası tehditler için kısıtlanmamış avcılık sağlar. Microsoft 365 Defender, özel [algılama kuralları](/custom-detections-overview.md) oluşturmak için özel sorgu kullanmayı da destekler. Bu kural, sorguyu temel alan uyarılar oluşturur ve otomatik olarak çalıştırılacak şekilde zamanlanabilir.

Fidye yazılımı etkinliklerinin proaktif olarak taranması için kimlikler, uç noktalar, uygulamalar ve veriler için yaygın olarak kullanılan fidye yazılımı saldırı yöntemleri için gelişmiş tehdit avcılığı sorgularının bir kataloğunu derlemeniz gerekir. Kullanıma hazır gelişmiş tehdit avcılığı sorguları için bazı önemli kaynaklar şunlardır:

* [Fidye yazılımı avı](/advanced-hunting-find-ransomware.md) makalesi
* Gelişmiş tehdit avcılığı sorguları için GitHub deposu:
  * [Fidye yazılımına özgü](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware) sorgular
  * [Tüm sorgu kategorileri](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware)
* Tehdit analizi raporları
  * Fidye Yazılımı'nın gelişmiş avcılık bölümü [: Sürekli ve sürekli bir tehdit](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/analystreport) analisti raporu
  * Diğer analist raporlarının gelişmiş avcılık bölümü

### <a name="automated-hunting"></a>Otomatik avcılık

Gelişmiş tehdit avcılığı sorguları, fidye yazılımı saldırı yönteminin bilinen öğelerine (örneğin, olağan dışı PowerShell komutlarının kullanımı) dayalı özel algılama kuralları ve eylemleri oluşturmak için de kullanılabilir. Özel algılama kuralları, güvenlik analistleriniz tarafından görülebilen ve ele alınabilen uyarılar oluşturur.

Özel algılama kuralı oluşturmak için gelişmiş bir tehdit avcılığı sorgusunun **sayfasından Özel algılama kuralı oluştur'u** seçin. Oluşturulduktan sonra şunları belirtebilirsiniz:

* Özel algılama kuralını çalıştırma sıklıkları
* Kural tarafından oluşturulan uyarının önem derecesi
* Oluşturulan uyarı için MITRE saldırı aşaması
* Etkilenen varlıklar
* Etkilenen varlıklar üzerinde yapılması gereken eylemler

## <a name="prepare-your-secops-team-for-focused-ransomware-detection"></a>SecOps Ekibinizi odaklanmış fidye yazılımı algılama için hazırlama

SecOps ekibinizin proaktif fidye yazılımı algılama için hazırlanması için şunlar gerekir:

* SecOps ekibiniz ve kuruluşunuz için ön çalışma
* Gerektiğinde güvenlik analisti eğitimi
* Güvenlik analistlerinizin en son saldırılarını ve algılama deneyimlerini birleştirirken devam eden operasyonel çalışmalar

### <a name="pre-work-for-your-secops-team-and-organization"></a>SecOps ekibiniz ve kuruluşunuz için ön çalışma

SecOps ekibinizin ve kuruluşunuzun odaklanmış fidye yazılımı saldırısını önlemeye hazır hale getirmek için şu adımları göz önünde bulundurun:

1. [Fidye yazılımlarından ve gasplara karşı hızlı koruma](/security/compass/protect-against-ransomware-phase3) kılavuzuyla BT ve bulut altyapınızı fidye yazılımı önleme için yapılandırın. Bu kılavuzdaki aşamalar ve görevler aşağıdaki adımlarla paralel olarak gerçekleştirilebilir.
2. Uç Nokta için Defender, Office 365 için Defender, Kimlik için Defender, Cloud Apps için Defender, uygulama idare eklentisi, IoT için Defender ve Azure AD Kimlik Koruması hizmetleri için uygun lisansları alın.
3. Bilinen fidye yazılımı saldırı yöntemleri veya saldırı aşamaları için ayarlanmış gelişmiş avcılık sorgularından oluşan bir katalog oluşturun.
4. Zamanlamaları, uyarı adlandırmaları ve otomatik eylemleri de dahil olmak üzere bilinen fidye yazılımı saldırı yöntemleri için uyarılar oluşturan belirli gelişmiş tehdit avcılığı sorguları için özel algılama kuralları kümesini oluşturun.
5. Daha büyük, eşgüdümlü bir fidye yazılımı saldırısının parçası olduğu bilinen olayları tanımlamak için yeni bir tane oluşturmak için [özel etiketler](/manage-incidents.md) veya standartlar kümesini belirleyin
6. Fidye yazılımı olayı ve uyarı yönetimi için işletimsel görevler kümesini belirleyin. Örneğin:

* Katman 1 analistinin gelen olayları ve uyarıları taraması ve araştırma için Katman 2 analistlerine atama işlemleri.
* Gelişmiş avcılık sorgularını ve zamanlamalarını el ile çalıştırma (günlük, haftalık, aylık).
* Fidye yazılımı saldırı araştırması ve risk azaltma deneyimlerine dayalı sürekli değişiklikler.

### <a name="security-analyst-training"></a>Güvenlik analisti eğitimi

Gerektiğinde, güvenlik analistlerinize aşağıdakiler için iç eğitim sağlayabilirsiniz:

* Yaygın fidye yazılımı saldırı zincirleri (MITRE saldırı taktikleri ve yaygın tehdit teknikleri ve kötü amaçlı yazılım)
* Olaylar ve uyarılar ile bunları Microsoft 365 Defender portalında bulma ve analiz etme işlemleri:
  * Microsoft 365 Defender tarafından önceden oluşturulmuş uyarılar ve olaylar
  * Microsoft 365 Defender portalı için önceden taranmış URL tabanlı filtreler
  * Olaylar API'si aracılığıyla program aracılığıyla
* Kullanılacak gelişmiş avlanma sorguları ve bunların el ile zamanlaması (günlük, haftalık, aylık)
* Kullanılacak özel algılama kuralları ve bunların ayarları
* Özel olay etiketleri
* Microsoft 365 Defender portalında [fidye yazılımı saldırıları için en son tehdit analizi raporları](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag)

### <a name="ongoing-work-based-on-operational-learning-and-new-threats"></a>Operasyonel öğrenme ve yeni tehditlere dayalı devam eden çalışmalar

SecOps ekibinizin devam eden araç ve süreç en iyi uygulamaları ile güvenlik analistlerinin deneyimlerinin bir parçası olarak şunları yapmalısınız:

* Gelişmiş avcılık sorguları kataloğunuzu aşağıdakilerle güncelleştirin:
  * Microsoft 365 Defender portalında veya [Advanced Hunting GitHub deposundaki](<https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware>) en son tehdit analizi raporlarını temel alan yeni sorgular.
  * Tehdit belirleme veya daha iyi uyarı kalitesi için iyileştirme yapmak için var olanlarda yapılan değişiklikler.
* Yeni veya değiştirilmiş gelişmiş tehdit avcılığı sorgularını temel alarak özel algılama kurallarını güncelleştirin.
* Fidye yazılımı algılama için işletimsel görev kümesini güncelleştirin.
