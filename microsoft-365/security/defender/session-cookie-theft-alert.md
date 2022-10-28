---
title: Oturum tanımlama bilgisi hırsızlığı uyarısı için uyarı not verme
description: Oturum tanımlama bilgisi hırsızlığı uyarısını True Positive (TP) veya False Positive (FP) olarak gözden geçirin, yönetin ve not alın ve TP varsa, saldırıyı düzeltmek ve bu nedenle ortaya çıkan güvenlik risklerini azaltmak için önerilen eylemleri gerçekleştirin.
keywords: olaylar, uyarılar, araştırma, analiz, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, microsoft, m365, tanımlama bilgisi hırsızlığı, AiTM, Ortada saldırgan, Saldırgan-orta, Saldırgan-orta, oturum hırsızlığı, aitm tanımlama bilgisi hırsızlığı, aitm oturum hırsızlığı.
search.appverid: met150
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
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: f7e2298ebf9fffda39da9795775627c0a9fb4223
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770488"
---
# <a name="alert-grading-for-session-cookie-theft-alert"></a>Oturum tanımlama bilgisi hırsızlığı uyarısı için uyarı not verme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Microsoft 365 Defender oturum tanımlama bilgisi hırsızlığı uyarıları için uyarı not alma hakkında bilgi içerir:

- **Çalınan oturum çerezi kullanıldı**
- **AiTM ile ilgili kimlik avı sayfasından kimlik doğrulama isteği**

Tehdit aktörleri hedef ortamlarına sızmak için yenilikçi yollar kullanmaya başladı. Ortadaki Saldırgan saldırılarından ilham alan bu saldırı türü, kötü amaçlı eylemleri gerçekleştirmek için kimlik bilgilerini veya oturum açma oturumlarını çalmak için kimlik avı kullanır. BEC kampanyaları mükemmel bir örnektir.

Bu saldırı, bir ara (kimlik avı) sitesi ayarlayarak çalışır ve kullanıcı ile saldırganın kimliğine büründiği meşru web sitesi arasında etkili bir şekilde proxy bağlantısı olarak çalışır. Saldırgan, aracı (ara sunucu) olarak hareket ederek hedefin parolasını ve oturum tanımlama bilgisini çalabilir. Bu nedenle saldırgan, kullanıcı adına kimlik doğrulaması yaptıkları için meşru bir oturumda kimlik doğrulaması yapabilir.

Bu playbook, tanımlama bilgisi hırsızlığı için şüpheli davranışların ortadaki saldırı (AiTM) türü saldırının göstergesi olarak gözlemlendiği durumların araştırılmasında yardımcı olur. Bu, güvenlik operasyonları merkezi (SOC) ve BT yöneticileri gibi güvenlik ekiplerinin uyarıları Gerçek Pozitif (TP) veya Hatalı Pozitif (FP) olarak gözden geçirmesine, yönetmesine ve not vermesine ve TP ise, saldırıyı düzeltmek ve bu nedenle ortaya çıkan güvenlik risklerini azaltmak için önerilen eylemleri gerçekleştirmesine yardımcı olur.

Bu playbook'u kullanmanın sonuçları şunlardır:

- AiTM ile ilişkili uyarıları kötü amaçlı (TP) veya iyi huylu (FP) etkinlikler olarak belirlediniz.
- Kötü amaçlı olarak tanımlanırsa, saldırıyı düzeltmek için gerekli eylemi yaptınız demektir.

## <a name="investigating-steps"></a>Adımları araştırma

1. Etkilenen kullanıcının diğer güvenlik uyarılarını tetikleyip tetiklemediğini araştırın.

    - Oturum açma işlemleri için coğrafi konum anomalilerini temel alan uyarılara `[AadSignInEventsBeta or IdentityLogonEvents]`odaklanın.
    - Oturum Kimliği bilgilerine `[AadSignInEventsBeta]`bakarak ilgili oturum açma olaylarını araştırın.
        - Çalınan tanımlama bilgisi `[CloudAppEvents]`kullanılarak gerçekleştirilen etkinlikleri izlemek için tanımlanan (çalınan) oturum kimliğiyle ilişkili olayları arayın.
        - Coğrafi konumda fark bulunan oturum açma etkinlikleri arasında bir zaman farkı arayın. Farklı konumlara sahip aynı hesap için birden çok oturum mümkün olmamalıdır (oturumun çalınabileceğini belirtir).
    - Şirket ana bilgisayarından hesap için oluşturulan uyarıları denetleyin.
        - Hesabın güvenliği aşılırsa, güvenliğin aşılmasından önce saldırıları gösteren uyarılar olabilir, örneğin SmartScreen uyarıları `[NetworkConnectionEvents]`.

2. Şüpheli davranışı araştırın.
    - ISS/Country/City gibi kullanıcılar için yaygın olmayan özellikler gibi şüpheli desenleri tanımlamak için olağan dışı desenleri `[CloudAppEvents]` gösteren olayları arayın.
    - Yeni veya daha önce hiç kullanılmayan hizmetlerde oturum açma girişimleri [başarılı/başarısız] gibi yeni veya daha önce görünmeyen etkinlikleri gösteren olayları, posta erişim etkinliğindeki artışı, Azure kaynak kullanımında bir değişikliği vb. arayın.
    - Ortamınızda aşağıdakilerden başlayarak yapılan son değişiklikleri inceleyin:
        - Office 365 uygulamaları (Exchange online izin değişiklikleri, posta otomatik iletme veya yeniden yönlendirme gibi)
        - PowerApps (PowerAutomate aracılığıyla otomatik veri iletimini yapılandırma gibi)
        - Azure ortamları (örneğin, Azure portal abonelik değişiklikleri vb.)
        - SharePoint Online (birden çok siteye veya kimlik bilgileri veya finansal tablolar gibi hassas içeriğe sahip dosyalara erişir)
    - Etkilenen kullanıcı için kısa bir süre içinde birden çok platformda (EXO, SPO, Azure vb.) gözlemlenen işlemleri inceleyin.
        - Örneğin, posta okuma/gönderme işlemlerinin ve Azure kaynak ayırma/değişikliklerinin (yeni makine sağlama veya AAD'ye ekleme) denetim olaylarının zaman çizelgeleri birbiriyle çakışmamalıdır.

3. Olası takip saldırılarını araştırın. AiTM saldırıları genellikle oyun sonu değil, bir uçtan uca saldırıdır, bu nedenle etkilenen hesaplar için ortamınızı takip eden diğer saldırılar için inceleyin.
    - BEC olaylarını incelemeye örnek olarak
        - Uyarılı kullanıcı hesabı posta kutusunda `[CloudAppEvents]`görülen arama etkinliklerini arayın.
            - Posta kutusunda yapılan arama etkinliklerinde şüpheli olan anahtar sözcüklerin finansal dolandırıcılık (örneğin faturalar, ödemeler vb.) olduğu gözlemlenebilir.
            - Ayrıca, (New-InboxRule, UpdateInboxRules, Set-InboxRule) ve RawEventData has_all (MarkAsRead, MoveToFolder, Archive) içinde ActionType satırları boyunca hareket etmek ve işaretlemek amacıyla oluşturulan gelen kutusu kurallarını da arayın.
    - Birden çok e-postanın aynı Url ile gönderildiği [EmailEvents & NetworkMessageId'de EmailUrlInfo] posta akışı olaylarını arayın.
        - Posta kutusu hesabı için bir artışın mı yoksa yüksek hacimli posta silme işleminin mi (Çöp Kutusu veya Silme olarak ActivityType) gözlemlenip gözlemlenmediğini `[CloudAppEvents]` incelemeyi izleyin.
        - Eşleşen davranış son derece şüpheli olarak kabul edilebilir.
    - Office365 e-postaları için tıklama olaylarıyla eşleşen Url olayları için cihaz olaylarını `[DeviceEvents on AccountName|AccountUpn]` inceleyin.
        - Tıklama kaynakları (örneğin, aynı Url için farklı IP adresleri) için olayları eşleştirmek kötü amaçlı bir davranışın göstergesi olabilir.

## <a name="advanced-hunting-queries"></a>Gelişmiş tehdit avcılığı sorguları

[Gelişmiş avcılık](advanced-hunting-overview.md) , ağınızdaki olayları incelemenize ve tehdit göstergelerini bulmanıza olanak tanıyan sorgu tabanlı bir tehdit avcılığı aracıdır.
Uyarıyla ilgili daha fazla bilgi toplamak ve etkinliğin şüpheli olup olmadığını belirlemek için bu sorguları kullanın.

Aşağıdaki tablolara erişiminiz olduğundan emin olun:

- AadSignInEventsBeta - kullanıcılar için oturum açma bilgilerini içerir.
- IdentityLogonEvents - kullanıcılar için oturum açma bilgilerini içerir.
- CloudAppEvents - Kullanıcı etkinliklerinin denetim günlüklerini içerir.
- EmailEvents - posta akışı/trafik bilgilerini içerir.
- EmailUrlInfo - E-postalarda yer alan URL bilgilerini içerir.
- UrlClickEvents - e-postalarda tıklanan Url'ler için Url tıklama günlüklerini içerir.
- DeviceEvents - cihaz etkinliği denetim olaylarını içerir.

Şüpheli oturum açma davranışını belirlemek için aşağıdaki sorguyu kullanın:

```kusto
let OfficeHomeSessionIds = 
AADSignInEventsBeta
| where Timestamp > ago(1d)
| where ErrorCode == 0
| where ApplicationId == "4765445b-32c6-49b0-83e6-1d93765276ca" //OfficeHome application 
| where ClientAppUsed == "Browser" 
| where LogonType has "interactiveUser" 
| summarize arg_min(Timestamp, Country) by SessionId;
AADSignInEventsBeta
| where Timestamp > ago(1d)
| where ApplicationId != "4765445b-32c6-49b0-83e6-1d93765276ca"
| where ClientAppUsed == "Browser" 
| project OtherTimestamp = Timestamp, Application, ApplicationId, AccountObjectId, AccountDisplayName, OtherCountry = Country, SessionId
| join OfficeHomeSessionIds on SessionId
| where OtherTimestamp > Timestamp and OtherCountry != Country
```

Yaygın olmayan ülkeleri tanımlamak için aşağıdaki sorguyu kullanın: 

```kusto
AADSignInEventsBeta 
| where Timestamp > ago(7d) 
| where ApplicationId == "4765445b-32c6-49b0-83e6-1d93765276ca" //OfficeHome application 
| where ClientAppUsed == "Browser" 
| where LogonType has "interactiveUser" 
| summarize Countries = make_set(Country) by AccountObjectId, AccountDisplayName
```

Şüpheli oturum açma oturumu sırasında oluşturulan yeni e-posta Gelen Kutusu kurallarını bulmak için bu sorguyu kullanın: 

```kusto
//Find suspicious tokens tagged by AAD "Anomalous Token" alert
let suspiciousSessionIds = materialize(
AlertInfo
| where Timestamp > ago(7d)
| where Title == "Anomalous Token"
| join (AlertEvidence | where Timestamp > ago(7d) | where EntityType == "CloudLogonSession") on AlertId
| project sessionId = todynamic(AdditionalFields).SessionId);
//Find Inbox rules created during a session that used the anomalous token
let hasSuspiciousSessionIds = isnotempty(toscalar(suspiciousSessionIds));
CloudAppEvents
| where hasSuspiciousSessionIds
| where Timestamp > ago(21d)
| where ActionType == "New-InboxRule"
| where RawEventData.SessionId in (suspiciousSessionIds)
```

## <a name="recommended-actions"></a>Önerilen eylemler

Uyarı etkinliklerinin kötü amaçlı olduğunu belirledikten sonra, bu uyarıları Doğru Pozitif (TP) olarak sınıflandırın ve aşağıdaki eylemleri gerçekleştirin:

- Kullanıcının hesap kimlik bilgilerini sıfırlayın. Ayrıca, güvenliği aşılmış hesap için belirteçleri devre dışı bırakın/iptal edin.
- Bulunan yapıtlar e-postayla ilgiliyse, engellemeyi Gönderen IP adresine ve Gönderen etki alanlarına göre yapılandırın.
  - Yazım hatası içeren etki alanları DMARC, DKIM, SPF ilkelerini temizleyerek (etki alanı tamamen farklı olduğundan) veya "null sonuçlar döndürebilir (büyük olasılıkla tehdit aktörü tarafından yapılandırılmadığından).
- Araştırma sırasında kötü amaçlı olarak tanımlanan URL'leri veya IP adreslerini (ağ koruma platformlarında) engelleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Tanımlama bilgisi hırsızlığından BEC'ye](https://www.microsoft.com/security/blog/2022/07/12/from-cookie-theft-to-bec-attackers-use-aitm-phishing-sites-as-entry-point-to-further-financial-fraud/)
