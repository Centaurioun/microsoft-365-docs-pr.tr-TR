---
title: Şüpheli parola spreyi ile ilgili IP adresi etkinlik uyarısı
description: Uyarıları gözden geçirmek ve saldırıyı düzeltmek ve ağınızı korumak için önerilen eylemleri uygulamak için şüpheli parola spreyi ile ilgili IP adresi etkinliği için uyarı notlaması.
keywords: olaylar, uyarılar, araştırma, analiz etme, yanıt, bağıntı, saldırı, cihazlar, kullanıcılar, 365, Microsoft, m365, parola, sprey, uyarı sınıflandırması, uyarı notlaması, bulut uygulamaları, şüpheli IP
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-dgali
author: dgali297
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
- met150
ms.openlocfilehash: bac6d70f5cbef7e19c03faf7079fc06c547acd45
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68361977"
---
# <a name="suspicious-password-spray-related-ip-activity"></a>Şüpheli parola spreyi ile ilgili IP etkinliği

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Tehdit aktörleri, kullanıcı hesaplarına erişim elde etmek için parola tahmin tekniklerini kullanır. Bir parola spreyi saldırısında, tehdit aktörü birçok farklı hesapta en çok kullanılan parolalardan birkaçını kullanabilir. Birçok kullanıcı hala varsayılan ve zayıf parolaları kullandığından, saldırganlar parola püskürtmeyi kullanarak hesapların güvenliğini başarıyla tehlikeye atabilir.

Bu kılavuz, IP adreslerinin riskli olarak etiketlendiği veya parola spreyi saldırısıyla ilişkilendirildiği ya da bilinmeyen bir konumdan oturum açmış bir kullanıcı veya beklenmeyen çok faktörlü kimlik doğrulaması (MFA) istemleri alan bir kullanıcı gibi şüpheli açıklanamayan etkinliklerin algılandığı örnekleri araştırmanıza yardımcı olur. Bu kılavuz, güvenlik operasyonları merkezi (SOC) gibi güvenlik ekiplerine ve uyarıları gözden geçiren, işleyen/yöneten ve sınıflandıran BT yöneticilerine yöneliktir. Bu kılavuz, uyarıların [doğru pozitif (TP) veya hatalı pozitif (FP)](investigate-alerts.md) olarak hızla sınıflandırılmalarına yardımcı olur ve TP söz konusu olduğunda, saldırıyı düzeltmek ve güvenlik risklerini azaltmak için önerilen eylemleri gerçekleştirir.

Bu kılavuzu kullanmanın amaçlanan sonuçları şunlardır:

- Parola spreyi IP adresleriyle ilişkili uyarıları kötü amaçlı (TP) veya hatalı pozitif (FP) etkinlikler olarak belirlediniz.

- IP adresleri parola spreyi saldırıları gerçekleştiriyorsa gerekli eylemi gerçekleştirdiniz.

## <a name="investigation-steps"></a>Araştırma adımları

Bu bölüm, uyarıya yanıt vermek ve kuruluşunuzu başka saldırılara karşı korumak için önerilen eylemleri gerçekleştirmeye yönelik adım adım yönergeler içerir.

### <a name="1-review-the-alert"></a>1. Uyarıyı gözden geçirin

Aşağıda, uyarı kuyruğunda parola spreyi uyarısı örneği verilmişti:

:::image type="content" source="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png" alt-text="Microsoft Defender 365 uyarısının ekran görüntüsü." lightbox="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png":::

Bu, tehdit bilgileri kaynaklarına göre deneme yanılma veya parola spreyi denemesiyle ilişkili olabilecek bir IP adresinden kaynaklanan şüpheli kullanıcı etkinliği olduğu anlamına gelir.

### <a name="2-investigate-the-ip-address"></a>2. IP adresini araştırma

- IP'den kaynaklanan [etkinliklere](microsoft-365-security-center-defender-cloud-apps.md) bakın:

  - **Çoğunlukla başarısız oturum açma girişimleri mi?**

  - **Oturum açma girişimleri arasındaki aralık şüpheli görünüyor mu?** Otomatik parola spreyi saldırıları, denemeler arasında düzenli bir zaman aralığına sahip olma eğilimindedir.

  - **Bir kullanıcının/birkaç kullanıcının [MFA](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365) istemleriyle oturum açma girişimi başarılı mı?** Bu girişimlerin varlığı, IP'nin kötü amaçlı olmadığını gösterebilir.

  - **Eski protokoller kullanılıyor mu?** POP3, IMAP ve SMTP gibi protokollerin kullanılması parola spreyi saldırısı gerçekleştirme girişimini gösterebilir. [Etkinlik günlüğünde](/defender-cloud-apps/activity-filters#ip-address-insights) kullanıcı aracısında (Cihaz türü) bulmak`Unknown(BAV2ROPC)`, eski protokollerin kullanıldığını gösterir. Etkinlik günlüğüne bakarken aşağıdaki örniğe başvurabilirsiniz. Bu etkinliğin diğer etkinliklerle daha fazla bağıntılı olması gerekir.

    :::image type="content" source="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png" alt-text="Cihaz türünü gösteren Microsoft Defender 365 arabiriminin ekran görüntüsü." lightbox="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png":::

    _Şekil 1. Cihaz türü alanında kullanıcı aracısı Microsoft 365 Defender gösterilir`Unknown(BAV2ROPC)`._

  - **Anonim ara sunucuların veya Tor ağının kullanımını denetleyin.** Tehdit aktörleri genellikle bilgilerini gizlemek için bu alternatif proxy'leri kullanır ve bu da izlemelerini zorlaştırır. Ancak, söz dizimli proxy'lerin tüm kullanımı kötü amaçlı etkinliklerle ilişkili değildir. Daha iyi saldırı göstergeleri sağlayabilecek diğer şüpheli etkinlikleri araştırmanız gerekir.
  - IP adresi bir sanal özel ağdan mı (VPN) geliyor? VPN güvenilir mi? **IP'nin bir VPN'den kaynaklanıp kaynaklandığını denetleyin ve** [RiskIQ](https://community.riskiq.com/learn-more/enterprise) gibi araçları kullanarak arkasındaki kuruluşu gözden geçirin. 
  - **Aynı alt ağa/ISS'ye sahip diğer IP'leri denetleyin.** Bazen parola spreyi saldırıları aynı alt ağ/ISS içindeki birçok farklı IP'den kaynaklanır.
- **IP adresi kiracı için ortak mı?** Kiracının son 30 gün içinde IP adresini görüp görmediğini görmek için Etkinlik günlüğünü denetleyin.
- **Kiracıdaki IP'den kaynaklanan diğer şüpheli etkinlikleri veya uyarıları arayın.** Dikkate alınabilecek etkinliklere örnek olarak e-posta silme, iletme kuralları oluşturma veya başarılı bir oturum açma girişiminden sonra dosya indirme işlemleri verilebilir.
- RiskIQ gibi araçları kullanarak **IP adresinin risk puanını denetleyin**.

### <a name="3-investigate-suspicious-user-activity-after-signing-in"></a>3. Oturum açtıktan sonra şüpheli kullanıcı etkinliğini araştırma

Şüpheli bir IP tanındıktan sonra oturum açan hesapları gözden geçirebilirsiniz. Ip veya diğer benzer IP'lerden oturum açmak için bir grup hesabın güvenliği aşılmış ve başarıyla kullanılmış olabilir.

IP adresinden oturum açmak için yapılan tüm başarılı girişimleri, uyarıların zamanından kısa bir süre sonra filtreleyin. Ardından oturum açtıktan sonra bu tür hesaplarda kötü amaçlı veya olağan dışı etkinlikleri arayın.

- Kullanıcı hesabı etkinlikleri

   **Parola spreyi etkinliğinden önceki hesaptaki etkinliğin şüpheli olmadığını doğrulayın.** Örneğin, ortak konumu veya ISS'yi temel alan anormal bir etkinlik olup olmadığını, hesabın daha önce kullanmadığı bir kullanıcı aracısını kullanıp kullanmadığını, başka konuk hesapları oluşturulup oluşturulmadığını, hesap kötü amaçlı bir IP'den oturum açtıktan sonra başka kimlik bilgileri oluşturulup oluşturulmadığını denetleyin.

- Uyarılar

  **Kullanıcının parola spreyi etkinliğinden önce başka uyarılar alıp almadığını denetleyin.** Bu uyarıların olması, kullanıcı hesabının gizliliğinin tehlikeye girmiş olabileceğini gösterir. İmkansız seyahat uyarısı, seyrek ülke etkinlikleri ve şüpheli e-posta silme etkinliği gibi örnekler verilebilir.

- Olay

  **Uyarının bir olayı gösteren diğer uyarılarla ilişkili olup olmadığını denetleyin.** Öyleyse, olayın diğer gerçek pozitif uyarılar içerip içermediğini denetleyin.

## <a name="advanced-hunting-queries"></a>Gelişmiş tehdit avcılığı sorguları

[Gelişmiş avcılık](/microsoft-365/security/defender/advanced-hunting-overview) , ağınızdaki olayları incelemenize ve tehdit göstergelerini bulmanıza olanak tanıyan sorgu tabanlı bir tehdit avcılığı aracıdır.

Kötü amaçlı IP'den gelen en yüksek risk puanlarıyla oturum açmaya çalışan hesapları bulmak için bu sorguyu kullanın. Bu sorgu ayrıca ilgili risk puanlarıyla oturum açma girişimlerinin tümünü filtreler.

```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| where isnotempty(RiskLevelDuringSignIn)
| project Timestamp, IPAddress, AccountObjectId, RiskLevelDuringSignIn, Application, ResourceDisplayName, ErrorCode
| sort by Timestamp asc
| sort by AccountObjectId, RiskLevelDuringSignIn
| partition by AccountObjectId ( top 1 by RiskLevelDuringSignIn ) // remove line to view all successful logins risk scores
```

Şüpheli IP'nin oturum açma girişiminde eski protokolleri kullanıp kullanmadiğini denetlemek için bu sorguyu kullanın.

```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| summarize count() by UserAgent
```

Şüpheli IP ile ilişkili son yedi gün içindeki tüm uyarıları gözden geçirmek için bu sorguyu kullanın.

```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
let ip_alert_ids = materialize ( 
        AlertEvidence
            | where Timestamp between (start_date .. end_date)
            | where RemoteIP == ip_address
            | project AlertId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
```

Güvenliği aşılmış olduğundan şüphelenilen hesapların hesap etkinliğini gözden geçirmek için bu sorguyu kullanın.

```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
CloudAppEvents
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | summarize ActivityCount = count() by AccountObjectId, ActivityType
    | extend ActivityPack = pack(ActivityType, ActivityCount)
    | summarize AccountActivities = make_bag(ActivityPack) by AccountObjectId
```

Güvenliği aşılmış olduğundan şüphelenilen hesapların tüm uyarılarını gözden geçirmek için bu sorguyu kullanın.

```kusto
let start_date = now(-8h); // change time range
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
let ip_alert_ids = materialize ( AlertEvidence
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | project AlertId, AccountObjectId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
| join kind=innerunique ip_alert_ids on AlertId
| project Timestamp, AccountObjectId, AlertId, Title, Category, Severity, ServiceSource, DetectionSource, AttackTechniques
| sort by AccountObjectId, Timestamp
```

## <a name="recommended-actions"></a>Önerilen Eylemler

1. [Saldırganın IP adresini engelleyin.](/azure/active-directory/conditional-access/block-legacy-authentication)
2. Kullanıcı hesaplarının kimlik bilgilerini sıfırlayın.
3. Güvenliği aşılmış hesapların erişim belirteçlerini iptal etme.
4. [Eski kimlik doğrulamasını engelle.](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
5. [Hesap güvenliğini artırmak](/azure/active-directory/authentication/tutorial-enable-azure-mfa) ve parola spreyi saldırısıyla hesabın güvenliğini tehlikeye atmak için mümkünse [kullanıcılar için MFA gerektirin](/microsoft-365/business-premium/m365bp-conditional-access).
6. Gerekirse güvenliği aşılmış kullanıcı hesabının oturum açmasını engelleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Uyarı notlama genel bakış](alert-grading-playbooks.md)
- [Uyarıları araştırın](investigate-alerts.md)