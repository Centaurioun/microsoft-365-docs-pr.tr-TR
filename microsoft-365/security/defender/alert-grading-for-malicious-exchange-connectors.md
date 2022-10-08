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
ms.openlocfilehash: 7489fe631c290fcf92d3502d0405b0ece9368457
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68067058"
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

|**Tablo Adı**  |**Açıklama**  |
|---------|---------|
|EmailEvents| E-posta akışıyla ilgili bilgileri içerir.|
|CloudAppEvents|Kullanıcı etkinliklerinin denetim günlüğünü içerir.|
|IdentityLogonEvents|Tüm kullanıcılar için oturum açma bilgilerini içerir.|

## <a name="references"></a>Başvurular

Başvuru için AHQs örnekleri:

- Yeni bağlayıcı oluşturmayı denetlemek için bu KQL'yi çalıştırın.
  ```
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
- Run this KQL to check the volume of events from the alerted connector with time window of before and after the alerts.
  ```
  lookback'i değiştirmek için timeWindow'ı değiştirin.
  let timeWindow = now(-7d); let timeNow = now(); let connectorOperations = pack_array("Set-OutboundConnector", "New-OutboundConnector", "Set-InboundConnector", "New-InboundConnector"); let mailThreshold = 100; inceleme ve filtreleme için eşik tanımlama myConnector= //ilgili bağlayıcıları belirtmek için bu kod bloğunu kullanın CloudAppEvents | where Timestamp between (timeWindow .. timeNow) | burada ActionType has_any (connectorOperations) | mv-expand özelliği = RawEventData.Parameters | where özelliği. Ad == "Ad" | ConnectorName=tostring(özelliğine göre özetleyin. Değer) ; EmailEvents | where isnotempty( toscalar (myConnector)) | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) ve isnotempty( Connectors) | where Connectors in (toscalar (myConnector)) | Summarize MailCount = dcount(NetworkMessageId) by Connectors, SenderObjectId, bin(Timestamp, 1h) | where MailCount >= mailThreshold
   ```
- Run this KQL to check whether emails are being sent to external domains.
  ```
  lookback'i değiştirmek için timeWindow'ı değiştirin.
  let timeWindow = now(-7d); let timeNow = now(); EmailEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) | extend RecipientDomain= split(RecipientEmailAddress, "@")[1] | where (SenderFromDomain != RecipientDomain) veya (SenderMailFromDomain != RecipientDomain) | burada EmailDirection !in ("Kuruluş içi" , "Gelen") //tüm posta akışı yol tariflerine bakmak için bu satırı yorumlayın
  ```
  - If sent to external domains, who else in the environment is sending similar emails (Could indicate compromised user if recipient is unknown domain).
     ```
     lookback'i değiştirmek için timeWindow'ı değiştirin.
     let timeWindow = now(-7d); let timeNow = now(); let countThreshold= 100; sayı eşiğini uygun şekilde değiştirme EmailEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) | extend RecipientDomain= split(RecipientEmailAddress, "@")[1] | where (SenderFromDomain != RecipientDomain) veya (SenderMailFromDomain != RecipientDomain) | burada EmailDirection !in ("Kuruluş içi" , "Gelen") | Summarize MailCount= dcount(NetworkMessageId) by SenderObjectId, SenderFromAddress, SenderMailFromAddress , bin(Timestamp, 1h) | burada MailCount > countThreshold
     ```
    - Check the mail content for bad behavior
      - Look at URLs in the email or email having attachments.


## AHQ considerations

Following are the AHQ considerations for protecting the recipients from malicious attack.

- Check for admin logins for those who frequently manage connectors from unusual locations (generate stats and exclude locations from where most successful logins are observed).

  - Look for login failures from unusual locations.

  ```
  lookback'i değiştirmek için timeWindow'ı değiştirin.
  let timeWindow = now(-7d); let timeNow = now(); let logonFail= materialize ( IdentityLogonEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty(AccountObjectId) | burada Uygulama != "Active Directory" | where ActionType == "LogonFailed" | where ISS != "Microsoft Azure" | summarize failedLogonCount=count(), LatestTime = max(Timestamp), EarliestTime = min(Timestamp) by AccountObjectId, Application, ISS, CountryCode, bin(Timestamp, 60s) | burada failedLogonCount > 100); let hasLogonFails = isnotempty(toscalar (logonFail)); let logonFailUsers = materialize ( logonFail | distinct AccountObjectId | take 100); let hasLogonFails = isnotempty(toscalar (logonFailUsers)); let logonSuccess= IdentityLogonEvents | where hasLogonFails | where Timestamp between (timeWindow .. timeNow) | where AccountObjectId in (logonFailUsers) | burada Uygulama != "Active Directory" | where ISS != "Microsoft Azure" | where ActionType == "LogonSuccess" | project SuccessTime= Timestamp, ReportId, AccountUpn, AccountObjectId, ISS, CountryCode, Application; logonFail | join kind = innerunique logonSuccess on AccountObjectId, ISS, Application | where SuccessTime between (LatestTime .. (LatestTime + 10s)) | summarize arg_min(SuccessTime, ReportId), EarliestFailedTime=min (EarliestTime), LatestFailedTime=max(LatestTime), failedLogonCount= take_any(failedLogonCount), SuccessLogonCount=count(), ISPSet= make_set(ISS), CountrySet=make_set(CountryCode), AppSet=make_set (Application) by AccountObjectId, AccountUpn | project-rename Timestamp=SuccessTime
  ```

## Recommended actions

Once it’s determined that the observed alert activities are part of TP, classify those alerts and perform the actions below:

- Disable or remove the connector that was found to be malicious.
- If the admin account was compromised, reset the admin’s account credentials. Also, disable/revoke tokens for the compromised admin account and enable multi-factor authentication for all admin accounts.
  - Look for suspicious activities performed by the admin.
- Check for other suspicious activities across other connectors in the environment.
