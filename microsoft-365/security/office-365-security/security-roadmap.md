---
title: Microsoft 365 güvenlik yol haritası - En önemli öncelikler
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 08/20/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Microsoft'un siber güvenlik ekibinden Microsoft 365 ortamınızı korumak için güvenlik özelliklerini uygulamaya yönelik en iyi öneriler.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ed554f008b55ee0c5441c25bfedc7db79cd538f1
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67854142"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Güvenlik yol haritası - İlk 30 gün, 90 gün ve sonrası için en önemli öncelikler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

Bu makale, Microsoft'un siber güvenlik ekibinin Microsoft 365 ortamınızı korumak için güvenlik özelliklerini uygulamaya yönelik en önemli önerilerini içerir. Bu makale bir Microsoft Ignite oturumundan uyarlanmıştır — [Microsoft 365'i bir siber güvenlik uzmanı gibi güvenli hale geçirin: İlk 30 gün, 90 gün ve sonrası için en önemli öncelikler](https://www.youtube.com/watch?v=luignzNyR-o). Bu oturum Mark Simos ve Kurumsal Siber Güvenlik Mimarları Matt Kemelhar tarafından geliştirilmiş ve sunulmuştur.

Bu makalede:

- [Yol haritası sonuçları](security-roadmap.md#Roadmap)
- [30 gün — güçlü hızlı kazançlar](security-roadmap.md#Thirdaydays)
- [90 gün — gelişmiş korumalar](security-roadmap.md#Ninetydays)
- [Öte -sinde](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Yol haritası sonuçları
<a name="Roadmap"> </a>

Bu yol haritası önerileri, aşağıdaki hedeflere sahip mantıksal bir sırada üç aşamada hazırlanmıştır.

|Zaman çerçevesi|Sonuç -ları|
|---|---|
|30 gün|Hızlı yapılandırma: <ul><li>Temel yönetici korumaları.</li><li>Günlüğe kaydetme ve analiz.</li><li>Temel kimlik korumaları.</li></ul> <p> Kiracı yapılandırması. <p> Paydaşları hazırlayın.|
|90 gün|Gelişmiş korumalar: <ul><li>hesapları Yönetici.</li><li>Veriler ve kullanıcı hesapları.</li></ul> <p> Uyumluluk, tehdit ve kullanıcı gereksinimleriyle ilgili görünürlük. <p> Varsayılan ilkeleri ve korumaları uyarlayıp uygulayın.|
|Öte -sinde|Anahtar ilkelerini ve denetimlerini ayarlayın ve geliştirin. <p> Korumaları şirket içi bağımlılıklara genişletme. <p> İş ve güvenlik süreçleriyle (yasal, iç tehdit vb.) tümleştirme.|

## <a name="30-days--powerful-quick-wins"></a>30 gün — güçlü hızlı kazançlar
<a name="Thirdaydays"> </a>

Bu görevler hızlı bir şekilde gerçekleştirilebilir ve kullanıcılar üzerinde düşük etkiye sahiptir.

|Alan|Görevler|
|---|---|
|Güvenlik yönetimi|<ul><li>Güvenli Puan'ı kontrol edin ve geçerli puanınızı (<https://security.microsoft.com/securescore>) not alın.</li><li>Office 365 için denetim günlüğünü açın. Bkz [. Denetim günlüğünde arama](../../compliance/search-the-audit-log-in-security-and-compliance.md) yapma.</li><li>[Daha fazla güvenlik için Microsoft 365'i yapılandırın](tenant-wide-setup-for-increased-security.md).</li><li>Microsoft 365 Defender portalında ve Cloud Apps için Defender'da panoları ve raporları düzenli olarak gözden geçirin.</li></ul>|
|Tehdit koruması|Anormal davranışlar için varsayılan tehdit algılama ilkelerini kullanarak izlemeye başlamak için [Microsoft 365'i Microsoft Defender for Cloud Apps bağlayın](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security). Anomali algılama için temel oluşturmak yedi gün sürer. <p>  Yönetici hesapları için koruma uygulama:<ul><li>Yönetici etkinliği için ayrılmış yönetici hesaplarını kullanın.</li><li>Yönetici hesapları için çok faktörlü kimlik doğrulamasını (MFA) zorunlu kılma.</li><li>Yönetici etkinliği için [yüksek oranda güvenli bir Windows cihazı](/windows-hardware/design/device-experiences/oem-highly-secure) kullanın.</li></ul>|
|Kimlik ve erişim yönetimi|<ul><li>[Azure Active Directory Kimlik Koruması'nı etkinleştirin](/azure/active-directory/active-directory-identityprotection-enable).</li><li>Federasyon kimlik ortamları için hesap güvenliğini zorunlu kılın (parola uzunluğu, yaş, karmaşıklık vb.).</li></ul>|
|Bilgi koruması|Örnek bilgi koruma önerilerini gözden geçirin. Bilgi koruması, kuruluşunuz genelinde koordinasyon gerektirir. Bu kaynaklarla çalışmaya başlayın:<ul><li>[GDPR için Office 365 Information Protection](/compliance/regulatory/gdpr)</li><li>[Teams'i üç koruma katmanıyla yapılandırma](../../solutions/configure-teams-three-tiers-protection.md) (paylaşım, sınıflandırma, Microsoft Purview veri kaybı önleme ve Azure Information Protection dahil)</li></ul>|

## <a name="90-days--enhanced-protections"></a>90 gün — gelişmiş korumalar
<a name="Ninetydays"> </a>

Bu görevlerin planlanıp uygulanması biraz daha zaman alır ancak güvenlik duruşunuzu büyük ölçüde artırır.

|Alan|Görev|
|---|---|
|Güvenlik yönetimi|<ul><li>Ortamınız<https://security.microsoft.com/securescore> () için önerilen eylemler için Güvenli Puan'ı denetleyin.</li><li>Microsoft 365 Defender portalında, Cloud Apps için Defender'da ve SIEM araçlarında panoları ve raporları düzenli olarak gözden geçirmeye devam edin.</li><li>Yazılım güncelleştirmelerini arayın ve uygulayın.</li><li>[Saldırı simülasyonu eğitimi](attack-simulation-training.md) (Office 365 Tehdit Bilgileri ile birlikte) kullanarak mızrak kimlik avı, parola spreyi ve deneme yanılma parola saldırıları için saldırı simülasyonları [gerçekleştirin](office-365-ti.md).</li><li>Cloud Apps için Defender'daki yerleşik raporları gözden geçirerek paylaşım riski arayın (Araştır sekmesinde).</li><li>Kuruluşunuz için geçerli olan düzenlemelerin durumunu (GDPR, NIST 800-171 gibi) gözden geçirmek için [Uyumluluk Yöneticisi'ni](../../compliance/compliance-manager.md) denetleyin.</li></ul>|
|Tehdit koruması|Yönetici hesapları için gelişmiş korumalar uygulayın: <ul><li>[Ayrıcalıklı Erişim İş İstasyonlarını](/security/compass/privileged-access-devices) (PAW) yönetici etkinliği için yapılandırın.</li><li>[Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) yapılandırın.</li><li>Office 365, Cloud Apps için Defender ve AD FS gibi diğer hizmetlerden günlük verilerini toplamak için bir güvenlik bilgileri ve olay yönetimi (SIEM) aracı yapılandırın. Denetim günlüğü verileri yalnızca 90 gün boyunca depolar. Bu verileri SIEM aracında yakalamak, verileri daha uzun süre depolamanıza olanak tanır.</li></ul>|
|Kimlik ve erişim yönetimi|<ul><li>Tüm kullanıcılar için MFA'yı etkinleştirin ve uygulayın.</li><li>[Bir dizi koşullu erişim ve ilgili ilkeler](microsoft-365-policies-configurations.md) uygulayın.</li></ul>|
|Bilgi koruması| Bilgi koruma ilkelerini uyarlama ve uygulama. Bu kaynaklar şunlardır: <ul><li>[GDPR için Office 365 Information Protection](/compliance/regulatory/gdpr)</li><li>[Teams'i üç koruma katmanıyla yapılandırma](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Microsoft Purview'da Microsoft 365'te depolanan veriler için (Cloud Apps için Defender yerine) veri kaybı önleme ilkelerini ve izleme araçlarını kullanın. <p> Gelişmiş uyarı özellikleri (veri kaybı önleme dışında) için Microsoft 365 ile Bulut Uygulamaları için Defender'ı kullanın.|

## <a name="beyond"></a>Öte -sinde
<a name="Beyond"> </a>

Bunlar, önceki çalışmayı oluşturan önemli güvenlik önlemleridir.

|Alan|Görev|
|---|---|
|Güvenlik yönetimi|<ul><li>Güvenli Puan (<https://security.microsoft.com/securescore> ) kullanarak sonraki eylemleri planlamaya devam edin.</li><li>Microsoft 365 Defender portalında, Cloud Apps için Defender'da ve SIEM araçlarında panoları ve raporları düzenli olarak gözden geçirmeye devam edin.</li><li>Yazılım güncelleştirmelerini aramaya ve uygulamaya devam edin.</li><li>eKeşif'i yasal ve tehdit yanıtı süreçlerinizle tümleştirin.</li></ul>|
|Tehdit koruması|<ul><li>Şirket içi kimlik bileşenleri (AD, AD FS) için [Güvenli Ayrıcalıklı Erişim](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) uygulayın.</li><li>Cloud Apps için Defender'ı kullanarak içeriden gelen tehditleri izleyin.</li><li>Cloud Apps için Defender'ı kullanarak gölge BT SaaS kullanımını keşfedin.</li></ul>|
|Kimlik ve erişim yönetimi|<ul><li>İlkeleri ve operasyonel süreçleri daraltma.</li><li>insider tehditlerini tanımlamak için Azure AD Identity Protection'ı kullanın.</li></ul>|
|Bilgi koruması|Bilgi koruma ilkelerini iyileştirme: <ul><li>Microsoft 365 ve Office 365 duyarlılık etiketleri ve veri kaybı önleme (DLP) veya Azure Information Protection.</li><li>Cloud Apps için Defender ilkeleri ve uyarıları.</li></ul>|

Ayrıca bkz. [Petya ve WannaCrypt gibi hızlı siber saldırıları azaltma](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
