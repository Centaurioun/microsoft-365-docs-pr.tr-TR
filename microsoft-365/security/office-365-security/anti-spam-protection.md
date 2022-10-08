---
title: İstenmeyen posta önleme koruma
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection (EOP) içinde istenmeyen postaları önlemeye yardımcı olacak istenmeyen posta önleme ayarları ve filtreleri hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b42122187f32396a5ca0643eb535b7d9d3cc4229
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68090849"
---
# <a name="anti-spam-protection-in-eop"></a>EOP'de istenmeyen posta önleme koruması

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Bu konu yöneticilere yöneliktir. Son kullanıcı konuları için bkz[. Gereksiz Email Filtresine Genel Bakış](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) ve [Gereksiz e-posta ve kimlik avı hakkında bilgi edinin](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31).

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, e-posta iletileri EOP tarafından istenmeyen postalara (gereksiz e-posta) karşı otomatik olarak korunur.

Microsoft'un e-posta güvenliği yol haritası, benzersiz bir ürün arası yaklaşım içerir. EOP istenmeyen posta önleme ve kimlik avı önleme teknolojisi, kullanıcılara ağ genelinde en son istenmeyen posta önleme ve kimlik avı önleme araçlarını ve yeniliklerini sağlamak için e-posta platformlarımızda uygulanır. EOP'nin amacı, kullanıcıları gereksiz e-posta, sahte e-posta tehditleri (kimlik avı) ve kötü amaçlı yazılımlardan algılamaya ve korumaya yardımcı olan kapsamlı ve kullanılabilir bir e-posta hizmeti sunmaktır.

E-posta kullanımı arttıkça, e-posta kötüye kullanımı da artmıştır. İzlenmeyen gereksiz e-postalar gelen kutularını ve ağları tıkar, kullanıcı memnuniyetini etkileyebilir ve meşru e-posta iletişimlerinin etkinliğini engelleyebilir. Bu nedenle Microsoft istenmeyen posta önleme teknolojilerine yatırım yapmaya devam ediyor. Basitçe söylemek gerekirse, gereksiz e-postayı içererek ve filtreleyerek başlar.

> [!TIP]
> İleti zarfı (örneğin, gönderenin etki alanı veya iletinin kaynak IP adresi) temelinde iletilere izin vermek veya iletileri engellemek istediğinizde aşağıdaki istenmeyen posta önleme teknolojileri yararlıdır. Yüke göre iletilere izin vermek veya iletileri engellemek için (örneğin, iletideki URL'ler veya ekli dosyalar) [Kiracı İzin Verme/Engelleme Listesi portalını](manage-tenant-allow-block-list.md) kullanmanız gerekir.

## <a name="anti-spam-technologies-in-eop"></a>EOP'de istenmeyen posta önleme teknolojileri

Gereksiz e-postayı azaltmaya yardımcı olmak için EOP, gereksiz e-postayı tanımlamak ve meşru e-postadan ayırmak için özel istenmeyen posta filtreleme teknolojilerini kullanan gereksiz e-posta koruması içerir. EOP istenmeyen posta filtreleme, bilinen istenmeyen posta ve kimlik avı tehditlerinden ve tüketici platformumuzdan Outlook.com kullanıcı geri bildirimlerinden öğrenir. Gereksiz e-posta sınıflandırma programındaki EOP kullanıcılarının sürekli geri bildirimleri, EOP teknolojilerinin sürekli olarak eğitilmesini ve geliştirilmesini sağlamaya yardımcı olur.

EOP'deki istenmeyen posta önleme ayarları aşağıdaki teknolojilerden yapılmıştır:

- **Bağlantı filtreleme**: IP İzin Ver Listesi, IP Engelleme Listesi ve *güvenli* liste (Microsoft tarafından tutulan güvenilir gönderenlerin dinamik ancak düzenlenemez listesi) aracılığıyla gelen e-posta bağlantısının başındaki iyi ve kötü e-posta kaynak sunucularını tanımlar. Bu ayarları bağlantı filtresi ilkesinde yapılandırabilirsiniz. [Bağlantı filtrelemeyi yapılandırma](configure-the-connection-filter-policy.md) bölümünde daha fazla bilgi edinin.

- **İstenmeyen posta filtreleme (içerik filtreleme)**: EOP iletileri sınıflandırmak için **İstenmeyen** posta, **Yüksek güvenilirlikli istenmeyen posta**, **Toplu e-posta**, **Kimlik avı e-postası** ve **Yüksek güvenilirlikli kimlik avı e-postası** gibi istenmeyen posta filtreleme kararlarını kullanır. Bu kararlara göre yapılacak eylemleri yapılandırabilir ve kullanıcıların karantinaya alınan iletilere ne yapmalarına izin verilip verilmeyeceğini ve kullanıcının [karantina ilkelerini](quarantine-policies.md) kullanarak karantina bildirimleri alıp almayacağını yapılandırabilirsiniz. Daha fazla bilgi için bkz [. Microsoft 365'te istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

  > [!NOTE]
  > Varsayılan olarak, istenmeyen posta filtreleme, istenmeyen posta olarak işaretlenmiş iletileri alıcının Gereksiz Email klasörüne gönderecek şekilde yapılandırılır. Ancak, EOP'nin şirket içi Exchange posta kutularını koruduğu karma ortamlarda, iletilere eklenen EOP istenmeyen posta üst bilgilerini tanımak için şirket içi Exchange kuruluşunuzda iki posta akışı kuralı (aktarım kuralları olarak da bilinir) yapılandırmanız gerekir. Ayrıntılar için bkz. [Karma ortamlarda gereksiz Email klasörüne istenmeyen posta göndermek için EOP'yi yapılandırma](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- **Giden istenmeyen posta filtreleme**: EOP ayrıca, kullanıcılarınızın giden ileti içeriğinde veya giden ileti sınırlarını aşarak istenmeyen posta göndermediğinden emin olmak için denetler. Daha fazla bilgi için bkz [. Microsoft 365'te giden istenmeyen posta filtrelemeyi yapılandırma](configure-the-outbound-spam-policy.md).

- **Kimlik sahtekarlığı zekası**: Daha fazla bilgi için bkz. [EOP'de kimlik sahtekarlığı koruması](anti-spoofing-protection.md).

## <a name="manage-errors-in-spam-filtering"></a>İstenmeyen posta filtreleme hatalarını yönetme

İyi iletiler istenmeyen posta (hatalı pozitifler olarak da bilinir) olarak tanımlanabilir veya istenmeyen postalar Gelen Kutusu'na teslim edilebilir (hatalı negatifler olarak da bilinir). Neler olduğunu öğrenmek ve gelecekte gerçekleşmesini önlemeye yardımcı olmak için aşağıdaki bölümlerde yer alan önerileri kullanabilirsiniz.

Her iki senaryo için de geçerli olan bazı en iyi yöntemler şunlardır:

- Yanlış sınıflandırılmış iletileri her zaman Microsoft'a bildirin. Daha fazla bilgi için bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md).

- **İstenmeyen postadan koruma iletisi üst bilgilerini inceleyin**: Bu değerler, bir iletinin neden istenmeyen posta olarak işaretlendiğini veya neden istenmeyen posta filtrelemeyi atladığını size söyler. Daha fazla bilgi için bkz [. İstenmeyen postadan koruma iletisi üst bilgileri](anti-spam-message-headers.md).

- **MX kaydınızı Microsoft 365'e** yöneltin: EOP'nin en iyi korumayı sağlaması için öncelikle e-postanın Microsoft 365'e teslim edilmesi önerilir. Yönergeler için bkz. [Microsoft 365 için herhangi bir DNS barındırma sağlayıcısında DNS kayıtları oluşturma](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

  MX kaydı başka bir konuma (örneğin, üçüncü taraf istenmeyen posta önleme çözümü veya aleti) işaret ederse, EOP'nin doğru istenmeyen posta filtrelemesi sağlaması zordur. Bu senaryoda, bağlayıcılar için Gelişmiş Filtreleme 'yi yapılandırmanız gerekir ( _liste atlama_ olarak da bilinir). Yönergeler için bkz. [Exchange Online'da Bağlayıcılar için Gelişmiş Filtreleme](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **E-posta kimlik doğrulamasını kullanma**: E-posta etki alanınız varsa, o etki alanındaki gönderenlerden gelen iletilerin meşru olmasını sağlamak için DNS kullanabilirsiniz. EOP'de istenmeyen posta ve istenmeyen kimlik sahtekarlıklarını önlemeye yardımcı olmak için aşağıdaki tüm e-posta kimlik doğrulama yöntemlerini kullanın:

  - **SPF**: Sender Policy Framework, iletinin kaynak IP adresini gönderen etki alanının sahibine karşı doğrular. SPF'ye hızlı bir giriş yapmak ve hızla yapılandırılmasını sağlamak için bkz. Kimlik [sahtekarlıklarını önlemeye yardımcı olmak için SPF'yi ayarlama](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Microsoft 365'in SPF'yi nasıl kullandığını daha ayrıntılı anlamak veya karma dağıtımlar gibi sorun giderme veya standart olmayan dağıtımlar için Microsoft [365'in kimlik sahtekarlıklarını önlemek için Sender Policy Framework'ün (SPF) nasıl kullanıldığıyla](how-office-365-uses-spf-to-prevent-spoofing.md) başlayın.

  - **DKIM**: DomainKeys Identified Mail, etki alanınızdan gönderilen iletilerin ileti üst bilgisine dijital imza ekler. Bilgi için bkz. [Microsoft 365'te özel etki alanınızdan gönderilen giden e-postayı doğrulamak için DKIM kullanma](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: Etki alanı tabanlı İleti Kimlik Doğrulaması, Raporlama ve Uyumluluk, hedef e-posta sistemlerinin SPF veya DKIM tarafından denetlenemeyen ve e-posta iş ortaklarınız için başka bir güven düzeyi sağlayan iletilerle ne yapacağını belirlemesine yardımcı olur. Daha fazla bilgi için bkz. [Microsoft 365'te e-postayı doğrulamak için DMARC kullanma](use-dmarc-to-validate-email.md).

- **Toplu e-posta ayarlarınızı doğrulayın**: İstenmeyen posta önleme ilkelerinde yapılandırdığınız toplu şikayet düzeyi (BCL) eşiği, toplu e-postanın ( _gri posta_ olarak da bilinir) istenmeyen posta olarak işaretlenip işaretlenmediğini belirler. Varsayılan olarak açık olan Yalnızca PowerShell ayarı _MarkAsSpamBulkMail_ de sonuçlara katkıda bulunur. Daha fazla bilgi için bkz [. Microsoft 365'te istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>İstenmeyen postanın Gelen Kutusu'na teslim edilmesini engelleme

- **Kuruluş ayarlarınızı doğrulayın**: İletilerin istenmeyen posta filtrelemeyi atlayabilmesini sağlayan ayarlara dikkat edin (örneğin, istenmeyen posta önleme ilkelerindeki izin verilen etki alanları listesine kendi etki alanınızı eklerseniz). Önerilen ayarlarımız için bkz[. EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](recommended-settings-for-eop-and-office365.md) ve [Güvenilir gönderen listeleri oluşturma](create-safe-sender-lists-in-office-365.md).

- **Kullanılabilir engellenen gönderen listelerini kullanın**: Bilgi için bkz. [Engellenen gönderen listeleri oluşturma](create-block-sender-lists-in-office-365.md).

- **Toplu e-posta aboneliğini kaldırma** İleti kullanıcının kaydolduğu bir şeyse (bültenler, ürün duyuruları vb.) ve saygın bir kaynaktan abonelikten çıkma bağlantısı içeriyorsa, yalnızca aboneliği kaldırmasını isteyin.

- **Tek başına EOP: EOP istenmeyen posta filtreleme kararları için şirket içi Exchange'de posta akışı kuralları oluşturun: EOP'nin** şirket içi Exchange posta kutularını koruduğu karma ortamlarda, şirket içi Exchange'de posta akışı kurallarını (aktarım kuralları olarak da bilinir) yapılandırmanız gerekir. Bu posta akışı kuralları, posta kutusunda gereksiz e-posta kuralının iletiyi Gereksiz Email klasörüne taşıyabilmesi için EOP istenmeyen posta filtreleme kararını çevirir. Ayrıntılar için bkz. [Karma ortamlarda gereksiz Email klasörüne istenmeyen posta göndermek için EOP'yi yapılandırma](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

### <a name="prevent-good-email-from-being-identified-as-spam"></a>İyi e-postanın istenmeyen posta olarak tanımlanmasını engelleme

Hatalı pozitif sonuçları önlemeye yardımcı olmak için uygulayabileceğiniz bazı adımlar şunlardır:

- **Kullanıcının Outlook Gereksiz Email Filtresi ayarlarını doğrulayın**:

  - **Outlook Önemsiz Email Filtresi'nin devre dışı bırakıldığından emin olun**: Outlook Gereksiz Email Filtresi varsayılan değere ayarlandığında **Otomatik filtreleme yok**, Outlook iletileri istenmeyen posta olarak sınıflandırmayı denemez.  **Düşük** veya **Yüksek** olarak ayarlandığında, Outlook Gereksiz Email Filtresi istenmeyen postaları belirlemek ve Gereksiz Email klasörüne taşımak için kendi SmartScreen filtre teknolojisini kullanır ve böylece hatalı pozitif sonuçları alabilirsiniz. Microsoft'un Kasım 2016'da Exchange ve Outlook'ta SmartScreen filtreleri için istenmeyen posta tanım güncelleştirmeleri üretmeyi durdurduğunu unutmayın. Mevcut SmartScreen istenmeyen posta tanımları yerinde bırakıldı, ancak zaman içinde etkinliği büyük olasılıkla azalacaktır.

  - **Outlook 'Yalnızca Güvenli Listeler' ayarının devre dışı bırakıldığından emin olun**: Bu ayar etkinleştirildiğinde, yalnızca kullanıcının Güvenilir Gönderenler listesindeki veya Güvenilir Alıcılar listesindeki gönderenlerden gelen iletiler Gelen Kutusu'na teslim edilir; e-posta otomatik olarak Gereksiz Email klasörüne taşınır.

  Bu ayarlar hakkında daha fazla bilgi için bkz[. Microsoft 365'te Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma](configure-junk-email-settings-on-exo-mailboxes.md).

- **Kullanılabilir güvenilir gönderen listelerini kullanın**: Bilgi için bkz. [Güvenilir gönderen listeleri oluşturma](create-safe-sender-lists-in-office-365.md).

- Kullanıcıların, Exchange Online hizmet açıklamasındaki [Alma ve gönderme sınırları](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) bölümünde açıklandığı gibi **gönderme ve alma sınırları içinde olduğunu doğrulayın**.

- **Tek başına EOP: dizin eşitlemesini kullanın**: Şirket içi Exchange kuruluşunuzu korumaya yardımcı olmak için tek başına EOP kullanıyorsanız, dizin eşitlemesini kullanarak kullanıcı ayarlarını hizmetle eşitlemeniz gerekir. Bunun yapılması, kullanıcılarınızın Güvenilir Gönderenler listelerine EOP tarafından uyulmasını sağlar. Daha fazla bilgi için bkz. [Posta kullanıcılarını yönetmek için dizin eşitlemesini kullanma](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect).

## <a name="anti-spam-legislation"></a>İstenmeyen posta önleme mevzuatı

Microsoft olarak, yeni teknolojilerin ve kendi kendine düzenlemenin geliştirilmesi için etkili kamu ilkelerinin ve yasal çerçevelerin desteklendiğini düşünüyoruz. Dünya çapında istenmeyen posta yayılması, ticari e-postayı düzenlemek için çok sayıda yasama organını teşvik etti. Birçok ülkede artık istenmeyen postayla mücadele yasaları var. Birleşik Devletler, istenmeyen postayı yöneten hem federal hem de eyalet yasalarına sahiptir ve bu tamamlayıcı yaklaşım, meşru e-ticaretin başarılı olmasını sağlarken istenmeyen postaların da kısıtlanmasında yardımcı olur. CAN-SPAM Yasası, sahte ve yanıltıcı e-posta iletilerini kısıtlamak için kullanılabilecek araçları genişletir.
