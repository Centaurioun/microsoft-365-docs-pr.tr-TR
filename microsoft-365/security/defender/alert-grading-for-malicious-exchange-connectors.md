---
title: Kötü amaçlı exchange bağlayıcıları için uyarı notları
description: Kötü amaçlı exchange bağlayıcıları etkinliğinden not alan alıcıları uyarın ve ağlarını kötü amaçlı saldırılara karşı koruyun.
keywords: olaylar, uyarılar, araştırma, analiz etme, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 83f7bdc0ac44b84953f760f31b5615ce793311f0
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770491"
---
# <a name="alert-grading-for-malicious-exchange-connectors"></a>Kötü amaçlı exchange bağlayıcıları için uyarı notları

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

Tehdit aktörleri, güvenilir e-postaları gizleyerek istenmeyen postaları ve kimlik avı e-postalarını istenmeyen postaları ve kimlik avı e-postalarını güvenilir olmayan alıcılara toplu olarak göndermek için güvenliği aşılmış exchange bağlayıcılarını kullanır. Bağlayıcının güvenliği aşıldığı için, e-postalara genellikle alıcılar tarafından güvenilir. Bu tür kimlik avı e-postaları, kimlik avı kampanyaları ve iş e-posta güvenliğinin tehlikeye atılması (BEC) senaryosu için yaygın vektörlerdir. Bu nedenle, başarılı alıcıların risklerinin yüksek olma olasılığı nedeniyle bu tür e-postaların yoğun bir şekilde izlenmesi gerekir.

Playbook, kötü amaçlı bağlayıcıların kötü amaçlı aktörler tarafından ayarlandığı/dağıtıldığı örneklerin araştırılmasında yardımcı olur. Buna göre, saldırıyı düzeltmek ve bundan kaynaklanan güvenlik risklerini azaltmak için gerekli adımları atarlar. Playbook, güvenlik operasyonları merkezi (SOC) ve BT yöneticileri gibi uyarıları gözden geçiren, işleyen/yöneten ve not veren güvenlik ekipleri için kullanılabilir. Playbook, uyarıların Doğru Pozitif (TP) veya Hatalı Pozitif (FP) olarak puanlanmasında yardımcı olur. TP varsa, playbook saldırıyı düzeltmek için önerilen gerekli eylemleri gerçekleştirir.

Playbook kullanmanın sonuçları aşağıdadır:

- Uyarının kötü amaçlı (TP) veya zararsız (FP) olarak belirlenmesi.
- Kötü amaçlıysa, kötü amaçlı bağlayıcıyı ortamdan düzeltin/kaldırın.

## <a name="exchange-connectors"></a>Exchange Bağlayıcıları

Exchange bağlayıcıları, e-postanızın Microsoft 365 veya Office 365 kuruluşunuza nasıl aktığını özelleştiren bir yönergeler koleksiyonudur. Microsoft 365 ve Office 365 kuruluşlarının çoğu genellikle normal posta akışı için bağlayıcılara ihtiyaç duymaz.

Bağlayıcılar, uzak e-posta sistemleri ile Office 365 (O365) veya O365 ile şirket içi e-posta sistemleri arasındaki posta trafiğini yönlendirmek için kullanılır.

## <a name="malicious-exchange-connectors"></a>Kötü Amaçlı Exchange Bağlayıcıları

Saldırganlar mevcut exchange bağlayıcının güvenliğini tehlikeye atabilir veya bir yöneticinin güvenliğini tehlikeye atabilir ve kimlik avı veya istenmeyen posta/toplu e-posta göndererek yeni bir bağlayıcı ayarlayabilir.

Kötü amaçlı bağlayıcının tipik göstergeleri, e-posta trafiğine ve üst bilgilerine bakarken bulunabilir. Örneğin, P1 (üst bilgi gönderen) ve P2 (zarf gönderen) gönderen adreslerinde uyuşmazlığı olan bir bağlayıcı düğümünden gelen e-posta trafiği gözlemlendiğinde, Gönderenin AccountObjectId değeriyle ilgili bilgi yoktur.

Bu uyarı, posta gönderme etkinliğinin gönderenle ilgili bilgilere eklenmesinin şüpheli göründüğü posta akışının bu tür örneklerini belirlemeye çalışır.

## <a name="playbook-workflow"></a>Playbook iş akışı

Kötü amaçlı exchange bağlayıcılarını tanımlamak için diziyi izlemeniz gerekir:

- Hangi hesapların e-posta gönderdiğini belirleyin:
  - Hesapların güvenliği ihlal edilmiş gibi görünüyor mu?
- Denetlemek için e-postalarda bağlayıcı geçişini tanımlayın:
  - Bağlayıcının yüksek hacimli e-postalar göndermesi gerekiyorsa?
  - Bağlayıcı değiştirildiyse veya yakın zamanda oluşturulduysa?
- E-postalar dahili e-posta adreslerine mi gidiyor?
  - E-postalar dış adreslere mi gidiyor (İstenmeyen postaları püskürtün ve dua edin)?
  - E-postalar müşterilere veya satıcılara ait dış adreslere mi gidiyor (tedarik zinciri türü saldırısı)?
- FROM üst bilgisinin ve Zarf Göndereni etki alanlarının aynı veya farklı olup olmadığını denetleyin.

## <a name="investigating-malicious-connectors"></a>Kötü amaçlı bağlayıcıları araştırma

Bu bölümde bir uyarıyı araştırma ve bu olay nedeniyle güvenlik riskini düzeltme adımları açıklanmaktadır.

- Bağlayıcının kötü (kötü amaçlı) davranış gösterip göstermediğini belirleyin.
  - Olağan dışı posta trafiğini gösteren olayları arayın ve yakın zamanda yeni exchange bağlayıcısı eklenip eklenmediğini belirleyin.
    - Gözlemlenen posta trafiği için, hesapların olağan dışı posta trafiğinden sorumlu olup olmadığını denetleyerek e-posta hesaplarının gizliliğinin ihlal edilip edilmediğini belirleyin.
  - Kötü amaçlı yapıtlar (hatalı bağlantılar/ekler) içeren posta içeriğini arayın.
  - Ortamınızın parçası olmayan etki alanlarını arayın.
- E-posta hesaplarının gizliliğinin ihlal edilmediğini belirleyin. Ortama yeni eklenen veya değiştirilen bağlayıcıyı belirleyin.
- Aramak:
  - P1 göndereni (e-posta üst bilgisi göndereni) ve P2 gönderenindeki (zarf gönderen) alan değerleri ve uyuşmazlık olup olmadığını denetleyin.
  - SenderObjectId alanındaki boş değerler.
- Aşağıdakilere dikkat etmek için telemetri verilerini kullanın:
  - Kötü amaçlı bağlayıcıdan gönderilen e-postaların NetworkMessageId (İleti Kimliği).
  - Bağlayıcı oluşturma tarihi, son değiştirme tarihi ve son değiştirme tarihi.
  - E-posta trafiğinin gözlemlendiği bağlayıcının IP adresi.

## <a name="advanced-hunting-queries"></a>Gelişmiş Tehdit Avcılığı Sorguları

Bir uyarıyla ilgili bilgileri toplamak ve etkinliğin şüpheli olup olmadığını belirlemek için [gelişmiş tehdit avcılığı](/microsoft-365/security/defender/advanced-hunting-overview?) sorgularını kullanabilirsiniz.

Aşağıdaki tablolara erişiminiz olduğundan emin olun:

|Tablo Adı|Açıklama|
|---|---|
|EmailEvents| E-posta akışıyla ilgili bilgileri içerir.|
|CloudAppEvents|Kullanıcı etkinliklerinin denetim günlüğünü içerir.|
|IdentityLogonEvents|Tüm kullanıcılar için oturum açma bilgilerini içerir.|

## <a name="references"></a>Başvurular

Başvuru için AHQs örnekleri:

- Yeni bağlayıcı oluşturmayı denetlemek için bu KQL'yi çalıştırın.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  CloudAppEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty(AccountObjectId)
  | where ActionType == "New-InboundConnector"
  | mvexpand property = RawEventData.Parameters
  | extend ConnectorName = iff(property.Name == "Name", property.Value, ""), 
  IsEnabled = iff((property.Name == "Enabled" and property.Value == "True"), 
  true, false)
  | where isnotempty( ConnectorName) or IsEnabled
  | project-reorder ConnectorName, IsEnabled
  ```

- Uyarılardan önce ve sonra gelen zaman penceresiyle, uyarılı bağlayıcıdan olay hacmini denetlemek için bu KQL'yi çalıştırın.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  let connectorOperations = pack_array("Set-OutboundConnector", 
  "New-OutboundConnector", "Set-InboundConnector", "New-InboundConnector");
  let mailThreshold = 100; //define threshold for inspection and filtering
  let myConnector= //use this code block to specify relevant connector(s)
  CloudAppEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where ActionType has_any (connectorOperations)
  | mv-expand property = RawEventData.Parameters
  | where property.Name == "Name"
  | summarize by ConnectorName=tostring(property.Value)
  ;
  EmailEvents
  | where isnotempty( toscalar (myConnector))
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty( SenderObjectId) and isnotempty( Connectors)
  | where Connectors in (toscalar (myConnector))
  | summarize MailCount = dcount(NetworkMessageId) by Connectors, 
  SenderObjectId, bin(Timestamp, 1h)
  | where MailCount >= mailThreshold
   ```

- Dış etki alanlarına e-posta gönderilip gönderilmediğini denetlemek için bu KQL'yi çalıştırın.

  ```KQL
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  EmailEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty( SenderObjectId)
  | extend RecipientDomain= split(RecipientEmailAddress, "@")[1]
  | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain 
  != RecipientDomain)
  | where EmailDirection !in ("Intra-org" , "Inbound") //comment this line to 
  look across all mailflow directions
  ```

  - Dış etki alanlarına gönderilirse, ortamda başka kim benzer e-postalar gönderiyorsa (Alıcı bilinmeyen etki alanıysa güvenliği aşılmış kullanıcıyı gösterebilir).

     ```KQL
     //modify timeWindow to modify the lookback.
     let timeWindow = now(-7d); let timeNow = now();
     let countThreshold= 100; //modify count threshold accordingly 
     EmailEvents
     | where Timestamp between (timeWindow .. timeNow)
     | where isnotempty( SenderObjectId)
     | extend RecipientDomain= split(RecipientEmailAddress, "@")[1]
     | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain 
     != RecipientDomain)
     | where EmailDirection !in ("Intra-org" , "Inbound")
     | summarize MailCount= dcount(NetworkMessageId) by SenderObjectId, 
     SenderFromAddress, SenderMailFromAddress , bin(Timestamp, 1h)
     | where MailCount > countThreshold
     ```

    - Posta içeriğinin kötü davranış olup olmadığını denetleyin
    - E-postadaki veya ekleri olan e-postadaki URL'lere bakın.

## <a name="ahq-considerations"></a>AHQ ile ilgili dikkat edilmesi gerekenler

Aşağıda, alıcıları kötü amaçlı saldırılara karşı korumaya yönelik AHQ ile ilgili dikkat edilmesi gereken noktalar yer alır.

- Bağlayıcıları sık sık olağan dışı konumlardan yönetenler için yönetici oturum açma bilgilerini denetleyin (istatistikler oluşturun ve en başarılı oturum açma bilgilerinin gözlemlendiği konumları hariç tutun).

- Olağan dışı konumlardan gelen oturum açma hatalarını arayın.

  ```
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  let logonFail= materialize (
  IdentityLogonEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty(AccountObjectId)
  | where Application != "Active Directory"
  | where ActionType == "LogonFailed"
  | where ISP != "Microsoft Azure"
  | summarize failedLogonCount=count(), LatestTime = max(Timestamp), 
  EarliestTime = min(Timestamp) by AccountObjectId, Application, ISP, 
  CountryCode, bin(Timestamp, 60s)
  | where failedLogonCount > 100);
  // let hasLogonFails = isnotempty(toscalar (logonFail));
  let logonFailUsers = materialize ( logonFail | distinct AccountObjectId | 
  take 100);
  let hasLogonFails = isnotempty(toscalar (logonFailUsers));
  let logonSuccess=
  IdentityLogonEvents
  | where hasLogonFails
  | where Timestamp between (timeWindow .. timeNow)
  | where AccountObjectId in (logonFailUsers)
  | where Application != "Active Directory"
  | where ISP != "Microsoft Azure"
  | where ActionType == "LogonSuccess"
  | project SuccessTime= Timestamp, ReportId, AccountUpn, AccountObjectId, 
  ISP, CountryCode, Application;
  logonFail
  | join kind = innerunique logonSuccess on AccountObjectId, ISP, Application
  | where SuccessTime between (LatestTime .. (LatestTime + 10s))
  | summarize arg_min(SuccessTime, ReportId), EarliestFailedTime=min
  (EarliestTime), LatestFailedTime=max(LatestTime), failedLogonCount=
  take_any(failedLogonCount), SuccessLogonCount=count(), ISPSet=
  make_set(ISP), CountrySet=make_set(CountryCode), AppSet=make_set
  (Application) by AccountObjectId, AccountUpn
  | project-rename Timestamp=SuccessTime
  ```

## <a name="recommended-actions"></a>Önerilen eylemler

Gözlemlenen uyarı etkinliklerinin TP'nin bir parçası olduğu belirlendikten sonra, bu uyarıları sınıflandırın ve aşağıdaki eylemleri gerçekleştirin:

- Kötü amaçlı olduğu belirlenen bağlayıcıyı devre dışı bırakın veya kaldırın.
- Yönetici hesabının güvenliği aşıldıysa yöneticinin hesap kimlik bilgilerini sıfırlayın. Ayrıca, güvenliği aşılmış yönetici hesabı için belirteçleri devre dışı bırakın/iptal edin ve tüm yönetici hesapları için çok faktörlü kimlik doğrulamasını etkinleştirin.
- Yönetici tarafından gerçekleştirilen şüpheli etkinlikleri arayın.
- Ortamdaki diğer bağlayıcılar arasında diğer şüpheli etkinlikleri denetleyin.
