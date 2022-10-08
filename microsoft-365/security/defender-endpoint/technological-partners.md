---
title: Microsoft 365 Defender'ın teknolojik ortakları
ms.reviewer: ''
description: Platformun algılama, araştırma ve tehdit bilgileri özelliklerini geliştirmek için M365 Defender'ın teknolojik ortaklarını görüntüleyin.
keywords: iş ortakları, teknolojik iş ortağı, uygulamalar, üçüncü taraf, SIEM, tehdit bilgileri, sentinel, SOAR, platformlar arası, m365 tümleştirmeleri, dns güvenliği, ağ koruması
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-aljupudi
author: alekyaj
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ea8f6cb27f85860532aa449f6bb7eda2187bfa36
ms.sourcegitcommit: d0557f757cfa48330ed57e966033891d10f03688
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68492786"
---
# <a name="technological-partners-of-microsoft-365-defender"></a>Microsoft 365 Defender'ın teknolojik ortakları

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Uç Nokta için Microsoft Defender
- Güvenlik Açığı Yönetimi için Microsoft Defender
- Office 365 için Microsoft Defender
- Kimlik için Microsoft Defender
- Bulut Uygulamaları için Microsoft Defender

Microsoft 365 Defender uç noktaların, güvenlik açığı yönetiminin, e-postanın, kimliklerin, bulut uygulamalarının çeşitli güvenlik alanlarında etkin tehdit koruması, algılama, araştırma ve yanıt ile kullanıcıların güvenliğini sağlamaya yardımcı olmak için üçüncü taraf tümleştirmelerini destekler.

Çözümün kategorileri şunlardır:

- Güvenlik bilgileri ve olay yönetimi (SIEM)
- Güvenlik düzenleme, otomasyon ve yanıt (SOAR)
- İhlal ve saldırı simülasyonu (BAS)
- Tehdit bilgileri
- Ağ güvenliği/DNS güvenliği
- Kimlik güvenliği
- Platformlar arası
- İş bulutu uygulamaları
- Tehdit ve güvenlik açığı yönetimi
- Güvenli hizmet kenarı
- Ek tümleştirmeler

## <a name="supported-integrations-and-partners"></a>Desteklenen tümleştirmeler ve iş ortakları

### <a name="security-information-and-event-management-siem"></a>Güvenlik bilgileri ve olay yönetimi (SIEM)

| Ürün adı | Satıcı | Açıklama |
| ------|------|------|
| [Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration) | Microsoft| Microsoft Sentinel ölçeklenebilir, bulutta yerel, güvenlik bilgileri ve olay yönetimi (SIEM) ile güvenlik düzenleme, otomasyon ve yanıt (SOAR) çözümüdür. Microsoft Sentinel, kuruluş genelinde akıllı güvenlik analizi ve tehdit bilgileri sunarak saldırı algılama, tehdit görünürlüğü, proaktif avcılık ve tehdit yanıtı için tek bir çözüm sağlar. |
| [Splunk](https://go.microsoft.com/fwlink/?linkid=2201963) | Splunk | Uç Nokta için Microsoft Defender Eklentisi, Splunk kullanıcılarının tüm uyarıları ve destekleyici bilgileri Splunk'larına almalarına olanak tanır.|
| [ArcSight](https://go.microsoft.com/fwlink/?linkid=2202142)| Mikro Odak  | ArcSight bağıntı, arama, UEBA, gelişmiş ve otomatik yanıt ve günlük yönetimi için birden fazla analiz özelliğine olanak tanır. |
| [Elastik Güvenlik](https://go.microsoft.com/fwlink/?linkid=2201772) | Elastik| Elastik Güvenlik, SIEM tehdit algılama özelliklerini uç nokta önleme ve yanıt özellikleriyle tek bir çözümde birleştirir.  |
| [IBM Security QRadar SIEM](https://go.microsoft.com/fwlink/?linkid=2201876) | Ibm| IBM Security QRadar SIEM, kritik siber güvenlik tehditlerinizi algılamak, araştırmak ve yanıtlamak için merkezi görünürlük ve akıllı güvenlik analizi sağlar. |
| [AttackIQ Platformu](https://go.microsoft.com/fwlink/?linkid=2201971)| AttackIQ | AttackIQ Platformu, üretim varlıkları üzerinde sürekli saldırıları güvenli bir şekilde başlatarak MDE'nin düzgün yapılandırılıp yapılandırılmadığını doğrular.|

### <a name="security-orchestration-automation-and-response-soar"></a>Güvenlik düzenleme, otomasyon ve yanıt (SOAR)

| Ürün adı | Satıcı | Açıklama |
| ---------- | ---------- | ---------- |
| [Microsoft Sentinel](https://go.microsoft.com/fwlink/?linkid=2201962)| Microsoft| Microsoft Sentinel ölçeklenebilir, bulutta yerel, güvenlik bilgileri ve olay yönetimi (SIEM) ile güvenlik düzenleme, otomasyon ve yanıt (SOAR) çözümüdür. Microsoft Sentinel, kuruluş genelinde akıllı güvenlik analizi ve tehdit bilgileri sunarak saldırı algılama, tehdit görünürlüğü, proaktif avcılık ve tehdit yanıtı için tek bir çözüm sağlar. |
| [ArcSight](https://go.microsoft.com/fwlink/?linkid=2202142)| Mikro Odak  | ArcSight bağıntı, arama, UEBA, gelişmiş ve otomatik yanıt ve günlük yönetimi için birden fazla analiz özelliği sağlar. |
| [Splunk SOAR](https://go.microsoft.com/fwlink/?linkid=2201773) | Splunk | Splunk SOAR iş akışlarını düzenler ve daha akıllı çalışmak ve daha hızlı yanıt vermek için görevleri saniyeler içinde otomatikleştirir. |
| [Güvenlik Olayı Yanıtı](https://go.microsoft.com/fwlink/?linkid=2201874)| ServiceNow | ServiceNow® Güvenlik Olayı Yanıtı uygulaması, güvenlik olaylarının bulma ve ilk analizden kapsama, silme ve kurtarma yoluyla ilerleme durumunu ve son olay sonrası gözden geçirme, bilgi bankası makale oluşturma ve kapatma işlemlerini izler.|
| [Swimlane](https://go.microsoft.com/fwlink/?linkid=2202140)| Kulvar Inc | Kulvar (SOAR) ve Microsoft Defender ile olay yanıtı özelliklerinizi otomatikleştirir.  |
| [InsightConnect](https://go.microsoft.com/fwlink/?linkid=2201877)  | Hızlı7 | InsightConnect, olay yanıtı ve güvenlik açığı yönetim süreçlerini hızlandıran güvenlik düzenlemesi, otomasyon ve yanıt çözümü sağlar. |
| [Demisto, bir Palo Alto Networks Şirketi](https://go.microsoft.com/fwlink/?linkid=2201777) | Palo Alto Networks | Demisto, güvenlik ekiplerinin uç nokta güvenliği izleme, zenginleştirme ve yanıtı düzenlemesini ve otomatikleştirmesini sağlamak için Uç Nokta için Microsoft Defender ile tümleşir. |

### <a name="breach-and-attack-simulation-bas"></a>İhlal ve saldırı simülasyonu (BAS)

| Ürün adı | Satıcı| Açıklama|
| --------| -------- | -------- |
| [SafeBreach](https://go.microsoft.com/fwlink/?linkid=2201775)| SafeBreach| SafeBreach saldırıları sürekli yürütür, güvenlik boşluklarını görselleştirmeye yardımcı olmak için sonuçları bağıntılar ve düzeltme çalışmalarını vurgulamak için bağlamsal içgörülerden yararlanıyor. Sektörün en kapsamlı saldırı verileri koleksiyonu olan Hacker's Playbook'u™ ile SafeBreach, kuruluşların umudun yerini verilerle dolduran basit bir yaklaşımla güvenlik konusunda proaktif hale getirmelerini sağlar.  |
| [Genişletilmiş Güvenlik Duruş Yönetimi (XSPM)](https://go.microsoft.com/fwlink/?linkid=2201771) | Cymulate| Cymulate'ın Genişletilmiş Güvenlik Duruş Yönetimi, şirketlerin siber güvenlik duruşlarını sınamasına, değerlendirmesine ve iyileştirmesine olanak tanır.  |
| [Güvenlik Açığı Denetimi](https://go.microsoft.com/fwlink/?linkid=2201967) | Skybox| Karma saldırı yüzeyi genelinde maruz kalma riskini doğru bir şekilde analiz eden ve düzeltmeye öncelik veren bir güvenlik açığı programı stratejisi geliştirir. |
| [Saldırı Yolu Yönetimi](https://go.microsoft.com/fwlink/?linkid=2201774)| XM Cyber| Saldırı Yolu Yönetimi, kuruluşların siber risklere yaklaşımını değiştiren saldırı yolu yönetimi sağlayan hibrit bir bulut güvenliği şirketidir.  |
| [Daha İyi Mobil Güvenlik Platformu](https://go.microsoft.com/fwlink/?linkid=2202043) | Better Mobile Security Inc. | Tehdit, Kimlik Avı ve Gizlilik Koruması ve Benzetimi için çözüm sağlar. |

### <a name="threat-intelligence"></a>Tehdit bilgileri

| Ürün adı | Satıcı | Açıklama|
| ------- | ------- | ------ |
| [ArcSight](https://go.microsoft.com/fwlink/?linkid=2202142)| Mikro Odak  | Bağıntı, arama, UEBA, gelişmiş ve otomatik yanıt ve günlük yönetimi için birden fazla analiz özelliği sağlar.  |
| [MineMeld](https://go.microsoft.com/fwlink/?linkid=2202044)| Palo Alto Networks | MineMeld kullanarak Otomatik Odak ve diğer tehdit akışlarını Uç Nokta için Microsoft Defender genişleterek uç nokta korumanızı zenginleştirir. |
| [MISP (Kötü Amaçlı Yazılım Bilgi Paylaşım Platformu)](https://go.microsoft.com/fwlink/?linkid=2202247) | MİSP | Açık Kaynak Tehdit Bilgileri Paylaşım Platformundaki tehdit göstergelerini Uç Nokta için Microsoft Defender ortamınızla tümleştirir. |
| [ThreatConnect](https://go.microsoft.com/fwlink/?linkid=2202246) | ThreatConnect| Uç Nokta için Microsoft Defender göstergeleri kullanan ThreatConnect Playbook'larından gelen özel tehdit bilgileriyle ilgili uyarılar ve/veya bloklar.|

### <a name="network-security-dns-security"></a>Ağ güvenliği/DNS güvenliği

| Ürün adı | Satıcı | Açıklama|
| --------- | ---------- | ---------- |
| [Aruba ClearPass İlke Yöneticisi](https://go.microsoft.com/fwlink/?linkid=2201878)| Aruba, bir Hewlett Packard Enterprise şirketi  | Ağ Access Control kablolu ve kablosuz ağlara tutarlı ilkeler ve ayrıntılı güvenlik denetimleri uygular |
| [Vectra Ağ Algılama ve Yanıtı (NDR)](https://go.microsoft.com/fwlink/?linkid=2201969) | Vectra | Vectra, siber saldırıları gerçek zamanlı olarak algılamak ve yanıtlamak için yapay zeka & güvenlik araştırması uygular. |
| [Ağ için Mavi Altıgen](https://go.microsoft.com/fwlink/?linkid=2201780)| Mavi Altıgen | Blue Hexagon, ağ tehdit koruması için sektörün ilk gerçek zamanlı derin öğrenme platformunu inşa etti.|
| [CyberMDX](https://go.microsoft.com/fwlink/?linkid=2201880)| CyberMDX | Siber MDX, kapsamlı sağlık varlıklarının görünürlüğünü, tehdit önlemesini ve depolarını Uç Nokta için Microsoft Defender ortamınızla tümleştirir. |
| [HYAS Koruma](https://www.hyas.com/hyas-protect) | HYAS | HYAS Protect, MDE uç noktalarını siber saldırılara karşı proaktif olarak korumak için saldırgan altyapısına yönelik yetkili bilgileri kullanır. |
| [Daha İyi Mobil Güvenlik Platformu](https://go.microsoft.com/fwlink/?linkid=2202043) | Better Mobile Security Inc.| Tehdit, Kimlik Avı ve Gizlilik Koruması ve Benzetimi için çözüm sağlar. |
| [Güvenlik Açığı Denetimi](https://go.microsoft.com/fwlink/?linkid=2201965) | Skybox güvenliği| Güvenlik açığı yönetimi ve ağ güvenlik ilkesi yönetimi çözümleriyle küresel güvenlik duruşu yönetimi lideri.  |
| [NDR'i açma](https://go.microsoft.com/fwlink/?linkid=2201964)| Çekirdek ışığı| Tam görünürlük için ağ kanıtıyla Microsoft 365 Defender'da cihaz envanterini artırabilirsiniz.  |

### <a name="identity-security"></a>Kimlik güvenliği

| Ürün adı| Satıcı | Açıklama|
| ---------- | --------- | ---------- |
| [Illusive Platform](https://go.microsoft.com/fwlink/?linkid=2201778)  | Illusive Networks  | Illusive kimlik güvenlik açıklarını sürekli bulur ve otomatik olarak düzeltir ve yanıltıcı denetimleri kullanarak saldırıları algılar.  |
| [Silverfort](https://go.microsoft.com/fwlink/?linkid=2201873) | Silverfort | Şirket içi ve buluttaki tüm kullanıcı sistemi ve ortamlarında koşullu erişimi ve MFA'yı Azure AD zorlar.  |

### <a name="cross-platform"></a>Platformlar arası

| Ürün adı    | Satıcı    | Açıklama |
| ---------- | ---------- | --------- |
| [Corrata Mobile Security](https://go.microsoft.com/fwlink/?linkid=2201879) | Corrata   | Corrata, mobil cihazları kimlik avı, kötü amaçlı yazılım, ortadaki adam saldırıları ve veri kaybı gibi tüm güvenlik tehditlerinden koruyan & algılayan mobil cihazlar ve tabletler için bir bağışıklık sistemidir. |
| [Daha İyi Mobil Güvenlik Platformu](https://go.microsoft.com/fwlink/?linkid=2202043)  | Better Mobile Security Inc. | Tehdit, Kimlik Avı ve Gizlilik Koruması ve Benzetimi için çözüm sağlar.|
| [Zimperium Mobile Threat Defense](https://go.microsoft.com/fwlink/?linkid=2202141)  | Zimperuim | Machine Learning tabanlı Mobile Threat Defense ile Uç Nokta için Microsoft Defender iOS ve Android'e genişletir.   |
| [Bitdefender](https://go.microsoft.com/fwlink/?linkid=2201968)    | Bitdefender     | Bitdefender GravityZone, karmaşık siber tehditlere karşı kapsamlı koruma sunan katmanlı bir yeni nesil uç nokta koruma platformudur. |

### <a name="business-cloud-applications"></a>İş bulutu uygulamaları

| Ürün adı | Satıcı | Açıklama|
| ------- | ------ | -----|
| [Atlassian dili](https://go.microsoft.com/fwlink/?linkid=2202039)| Atlassian dili    | Atlassian ekipler için işbirliği, geliştirme ve sorun izleme yazılımı sağlar.  |
| [Azure](https://go.microsoft.com/fwlink/?linkid=2202040)    | Microsoft    | Microsoft Azure, bulut oyun hizmetleriyle küresel bir hedef kitleye ulaşmanıza ve ölçeklendirmenize yardımcı olacak araçlar ve hizmetler sağlar. |
| [Aws](https://go.microsoft.com/fwlink/?linkid=2202041)| Amazon | Amazon Web Services, işletmelere web hizmetleri biçiminde bilgi teknolojisi altyapı hizmetleri sağlar.   |
| [Kutusu](https://go.microsoft.com/fwlink/?linkid=2202042)| Kutusu  | Box, sınırsız depolama alanı, özel markalama ve yönetim denetimleri sunan çevrimiçi bir dosya paylaşımı ve bulut içerik yönetimi hizmetidir. |
| [DocuSign](https://go.microsoft.com/fwlink/?linkid=2201767) | DocuSign| DocuSign, çalışanların sözleşmeleri güvenli bir şekilde göndermesine, imzalamasına ve yönetmesine olanak tanıyan bir Elektronik İmza ve Anlaşma Bulutu'dur. |
| [Dropbox](https://go.microsoft.com/fwlink/?linkid=2202139)  | Dropbox| Dropbox güvenli dosya paylaşımı, işbirliği ve depolama çözümleri sağlayan bir akıllı çalışma alanı şirketidir.    |
| [Egnyte](https://go.microsoft.com/fwlink/?linkid=2201956)   | Egnyte | Egnyte güvenli içerik işbirliğini, uyumlu veri korumayı ve basit altyapı modernleştirmesini sağlar. |
| [GİTHUB](https://go.microsoft.com/fwlink/?linkid=2201957)   | Microsoft    | GitHub, işbirliği ve sürüm denetimi için kullanılan bir kod barındırma platformudur. Geliştiricilerin planlama ve kodlamadan yazılımı göndermeye kadar projeleri üzerinde birlikte çalışmasına olanak tanır. |
| [Google Çalışma Alanı](https://go.microsoft.com/fwlink/?linkid=2201958)| Alfabe| Google Çalışma Alanı planları işletmeniz için özel bir e-posta sağlar ve Gmail, Takvim, Toplantı, Sohbet, Sürücü, Belgeler, Sayfalar, Slaytlar, Formlar, Siteler ve daha fazlası gibi işbirliği araçlarını içerir.   |
| [Google Cloud Platform](https://go.microsoft.com/fwlink/?linkid=2202244) | Alfabe| Google Cloud Platform, basit web sitelerinden karmaşık uygulamalara kadar her şeyi oluşturmanıza olanak tanıyan modüler bulut tabanlı hizmetler kümesidir.|
| [NetDocuments](https://go.microsoft.com/fwlink/?linkid=2201768)  | NetDocuments | NetDocuments, her büyüklükteki işletmenin belgeler ve e-postalar oluşturmasını, güvenliğini sağlamasını, yönetmesini, erişmesini ve belgeler ve e-postalar üzerinde istediğiniz zaman işbirliği yapmasına olanak tanır. |
| [Office 365](https://go.microsoft.com/fwlink/?linkid=2201959)    | Microsoft    | Microsoft Office 365, Microsoft Office platformu etrafında oluşturulan çeşitli hizmetlere ve yazılımlara erişim sağlayan abonelik tabanlı bir çevrimiçi ofis ve yazılım hizmetleri paketidir.   |
| [OKTA](https://go.microsoft.com/fwlink/?linkid=2201867)| OKTA | Okta, iş gücü ve müşteriler için kritik kaynakları buluttan yere güvenli hale getiren bir yönetim platformudur.  |
| [OneLogin](https://go.microsoft.com/fwlink/?linkid=2201868) | OneLogin| OneLogin, kuruluşların tüm cihazlarda kullanıcıları için tüm uygulamaların güvenliğini sağlamasını sağlayan bir bulut kimliği ve erişim yönetimi çözümüdür. |
| [Salesforce](https://go.microsoft.com/fwlink/?linkid=2201869)    | Salesforce   | Salesforce, her büyüklükteki işletmeler için bulut bilişim & müşteri ilişkileri yönetimi (CRM) yazılımı sunan küresel bir bulut bilişim şirketidir. |
| [ServiceNow](https://go.microsoft.com/fwlink/?linkid=2201769)    | ServiceNow   | ServiceNow, kurumsal operasyonlar için hizmetleri tanımlayan, yapılandıran, yöneten ve otomatik hale getiren bulut tabanlı çözümler sağlar.    |
| [Bol -luk](https://go.microsoft.com/fwlink/?linkid=2201870)    | Bol -luk| Slack, her büyüklükteki ekiplerin ve işletmelerin etkili bir şekilde iletişim kurmasını sağlayan kurumsal bir yazılım platformudur. |
| [SmartSheet](https://go.microsoft.com/fwlink/?linkid=2201871)    | SmartSheet   | Smartsheet, işbirliğini güçlendiren, daha iyi karar alma sürecini destekleyen ve yenilikleri hızlandıran bulut tabanlı bir iş yönetimi platformudur. |
| [Webex](https://go.microsoft.com/fwlink/?linkid=2201872)    | Cisco| Bir Cisco şirketi olan Webex, işletmelere web konferansı, telework ve uygulama uzaktan denetimi gerçekleştirmeleri için isteğe bağlı uygulamalar sağlar. |
| [Işgünü](https://go.microsoft.com/fwlink/?linkid=2201960)  | Işgünü| Workday, insan kaynakları ve finansal yönetim için kurumsal düzeyde yazılım çözümleri sunar.|
| [Zendesk](https://go.microsoft.com/fwlink/?linkid=2201961)  | Zendesk| Zendesk, kuruluş ve müşteri ilişkilerini güçlendirmek için yazılım geliştiren bir müşteri hizmetleri platformudur.|

### <a name="threat-and-vulnerability-management"></a>Tehdit ve güvenlik açığı yönetimi

| Ürün adı| Satıcı  | Açıklama  |
| --------- | -------- | -------- |
| [Saldırı Yolu Yönetimi](https://go.microsoft.com/fwlink/?linkid=2201774)    | XM Cyber| Saldırı yolu yönetimi sağlayan hibrit bulut güvenliği şirketi, kuruluşların siber risklere yaklaşımını değiştiriyor.  |
| [Corrata Mobile Security](https://go.microsoft.com/fwlink/?linkid=2201879)   | Corrata | Corrata, mobil cihazları kimlik avı, kötü amaçlı yazılım, ortadaki adam saldırıları ve veri kaybı gibi tüm güvenlik tehditlerinden koruyan & algılayan mobil cihazlar ve tabletler için bir bağışıklık sistemidir.  |
| [Zimperium Mobile Threat Defense](https://go.microsoft.com/fwlink/?linkid=2202141)   | Zimperuim| Machine Learning tabanlı Mobile Threat Defense ile Uç Nokta için Microsoft Defender iOS ve Android'e genişletin.    |
| [RiskAnalyzer](https://go.microsoft.com/fwlink/?linkid=2202245)      | DeepSurface Security  | DeepSurface RiskAnalyzer, siber güvenlik riskini hızla ve verimli bir şekilde keşfetmeye, analiz edip önceliklendirmeye yardımcı olur     |
| [Güvenlik Açığı Denetimi](https://go.microsoft.com/fwlink/?linkid=2201965)| Skybox güvenliği| Güvenlik açığı yönetimi ve ağ güvenlik ilkesi yönetimi çözümleriyle küresel güvenlik duruşu yönetimi lideri.    |
| [Vulcan Siber risk yönetimi platformu](https://go.microsoft.com/fwlink/?linkid=2201770)   | Vulcan Cyber    | Vulcan Cyber, uygulama, bulut ve altyapı dahil olmak üzere tüm siber varlıklarınız için güvenlik açığını ve risk yaşam döngüsünü etkili bir şekilde yönetmenizi sağlayan araçlar sunar.   |
| [Genişletilmiş Güvenlik Duruş Yönetimi (XSPM)](https://go.microsoft.com/fwlink/?linkid=2201771) | Cymulate| Cymulate'ın Genişletilmiş Güvenlik Duruş Yönetimi, şirketlerin siber güvenlik duruşlarını sınamasına, değerlendirmesine ve iyileştirmesine olanak tanır. |
| [Illusive Platform](https://go.microsoft.com/fwlink/?linkid=2201778)     | Illusive Networks     | Illusive kimlik güvenlik açıklarını sürekli bulur ve otomatik olarak düzeltir ve yanıltıcı denetimleri kullanarak saldırıları algılar. |

### <a name="secure-service-edge"></a>Güvenli hizmet kenarı

| Ürün adı  | Satıcı  | Açıklama  |
| --------- | ------- | ------------ |
| [Zscaler İnternet Erişimi](https://go.microsoft.com/fwlink/?linkid=2201779)  | Zscaler | Zscaler Internet Access, on yıllık güvenli web ağ geçidi liderliği üzerine inşa eden bir bulut yerel güvenlik hizmeti uç (SSE) çözümüdür. Dünyanın en büyük güvenlik bulutundan ölçeklenebilir bir SaaS platformu olarak sunulan bu platform, gelişmiş saldırıları durdurmak ve kapsamlı bir sıfır güven yaklaşımıyla veri kaybını önlemek için eski ağ güvenlik çözümlerinin yerini alır. |

### <a name="additional-integrations"></a>Ek tümleştirmeler

| Ürün adı  | Satıcı    | Açıklama   |
| ------- | ------ | -------- |
| [Morphisec](https://go.microsoft.com/fwlink/?linkid=2201966)  | Morphisec | Hedef Savunma destekli gelişmiş tehdit önlemeyi taşımayı sağlar ve uyarıların önceliklerini belirlemeye, risk altındaki cihaz puanını belirlemeye ve iç bellek bilgileri de dahil olmak üzere tam saldırı zaman çizelgesini görselleştirmeye yardımcı olmak için adli tıp verilerini doğrudan WD Güvenlik Merkezi panolarıyla tümleştirir. |
| [THOR Bulutu](https://go.microsoft.com/fwlink/?linkid=2201875) | Nextron sistemleri | Kalıcı tehditlere odaklanan bir imza tabanı kullanarak isteğe bağlı canlı adli tıp taramaları sağlar.  |

## <a name="recommended-content"></a>Önerilen içerik

- [Görünürlük ve denetim | almak için uygulamaları bağlama Microsoft Docs](/defender-cloud-apps/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
- [Uç Nokta için Microsoft Defender | iş ortağı uygulamaları Microsoft Docs](partner-applications.md)