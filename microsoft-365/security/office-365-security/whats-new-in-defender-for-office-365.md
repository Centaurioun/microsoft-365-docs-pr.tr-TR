---
title: Office 365 için Microsoft Defender’daki yenilikler
description: en son Office 365 için Microsoft Defender sürümünde sunulan yeni özellikler ve işlevler hakkında bilgi edinin.
keywords: Office 365 için Microsoft Defender, ga, genel kullanıma sunulan, özellikler, kullanılabilir, yeni sürümündeki yenilikler
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords: NOCSH
ms.author: tracyp
author: msfttracyp
ms.localizationpriority: medium
ms.date: 09/20/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 7ad14ea93944cf7f754006c4e934049061d1b29d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68057578"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender’daki yenilikler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**

- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bu makalede, en son Office 365 için Microsoft Defender sürümündeki yeni özellikler listelenmiştir. Şu anda önizleme aşamasında olan özellikler **(önizleme)** ile belirtilir.

[Bu videoyu](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3) izleyerek daha fazla bilgi edinin.

Diğer Microsoft Defender güvenlik ürünleriyle ilgili yenilikler hakkında daha fazla bilgi için bkz:

- [Microsoft 365 Defender'daki yenilikler](../defender/whats-new.md)
- [Uç Nokta için Microsoft Defender'deki yenilikler](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Kimlik için Microsoft Defender'deki yenilikler](/defender-for-identity/whats-new)
- [Microsoft Defender for Cloud Apps'deki yenilikler](/cloud-app-security/release-notes)

## <a name="september-2022"></a>Eylül 2022

**Office 365 Güvenlik ve Uyumluluk Merkezi'nden Microsoft 365 Defender portalına otomatik** yeniden yönlendirme: Office 365 Güvenlik ve Uyumluluk Merkezi'ndeki (protection.office.com) güvenlik çözümlerine erişen kullanıcılar için otomatik yeniden yönlendirme başlar Microsoft 365 Defender portalı (security.microsoft.com). Bu, uyarılar, Tehdit Yönetimi ve Raporlar gibi tüm güvenlik iş akışlarına yöneliktir. 
- Yeniden yönlendirme URL'leri:
    - GCC Ortamı:
        - Office 365 Güvenlik & Uyumluluk Merkezi URL'sinden: protection.office.com
        - URL'yi Microsoft 365 Defender için: security.microsoft.com
    - GCC-High Ortamı:
        - Office 365 Güvenlik & Uyumluluk Merkezi URL'sinden: scc.office365.us
        - URL'yi Microsoft 365 Defender için: security.microsoft.us
    - DoD Ortamı:
        - Office 365 Güvenlik & Uyumluluk Merkezi URL'sinden: scc.protection.apps.mil
        - URL'yi Microsoft 365 Defender için: security.apps.mil
- Office 365 Güvenlik ve Uyumluluk Merkezi'ndeki güvenlikle ilgili olmayan öğeler Microsoft 365 Defender yeniden yönlendirılmaz. Uyumluluk çözümlerinin Microsoft 365 Uyumluluk Merkezi'ne yeniden yönlendirilmesi için bkz. 244886 sonrası İleti Merkezi. 
- Bu, mart 2022'de duyurulan [Microsoft Tech Community GCC, GCC High ve DoD müşterilerine birleşik XDR deneyimi sunan Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/public-sector-blog/microsoft-365-defender-delivers-unified-xdr-experience-to-gcc/ba-p/3263702) devamıdır.
- Bu değişiklik, kullanıcıların ek Microsoft 365 Defender güvenlik çözümlerini tek bir portalda görüntülemesine ve yönetmesine olanak tanır.
- Bu değişiklik, Office için Microsoft Defender (Plan 1 veya Plan 2), Microsoft 365 E3/E5, Office 365 E3/E5 ve Office 365 Güvenlik ve Uyumluluk Merkezi'ni (protection.office.com) kullanan tüm müşterileri etkiler ve Exchange Online Protection. Tam liste için bkz[. Güvenlik & Uyumluluk Merkezi - Hizmet Açıklamaları | Microsoft Docs](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)
- Bu değişiklik, Email Karantina deneyimine erişen güvenlik ekipleri ve son kullanıcılar da dahil olmak üzere Office 365 Güvenlik ve Uyumluluk portalında (protection.office.com) **Microsoft Defender Portalı** > **Gözden Geçirme** > **Karantinası'nda** oturum açan tüm kullanıcıları etkiler.
- Yeniden yönlendirme varsayılan olarak etkindir ve Kiracının tüm kullanıcılarını etkiler.
- Genel Yöneticiler ve Güvenlik Yöneticileri, Microsoft 365 Defender portalında **Ayarlar** >  **Email & işbirliği** > **Portalı yeniden yönlendirme** ve yeniden yönlendirme geçişine giderek yeniden yönlendirmeyi açabilir veya kapatabilir.
- **Yerleşik koruma**: Tüm Office 365 için Defender müşterileri için varsayılan olarak açık olan temel düzeyde Güvenli Bağlantılar ve Güvenli Ekler koruması sağlayan profil. Bu yeni ilke ve öncelik sırası hakkında daha fazla bilgi edinmek için [bkz. Önceden ayarlanmış güvenlik ilkeleri](preset-security-policies.md) ve belirli Güvenli Bağlantılar ve Güvenli Ek denetimleri kümesi hakkında bilgi edinmek için bkz. [Güvenli Ekler ayarları](recommended-settings-for-eop-and-office365.md#safe-attachments-settings) ve [Güvenli Bağlantılar ayarları](recommended-settings-for-eop-and-office365.md#safe-links-settings).

## <a name="july-2022"></a>Temmuz 2022

- [E-posta varlığı sayfasına eylemler ekleme: Yöneticiler, e-posta](mdo-email-entity-page.md) varlık sayfasından önleyici, düzeltme ve gönderme eylemleri gerçekleştirebilir.

## <a name="june-2022"></a>Haziran 2022

- [Microsoft 365 Defender portalını kullanarak Gönderiler portalında sahte gönderenler için izin verilen girişler oluşturun](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-submissions-portal): Kiracı İzin Ver/Engelle Listesini kullanarak izin verilen sahte gönderen girişleri oluşturun.

- [Kimliğe bürünme, yönetici gönderiminin kullanılmasına izin verir](allow-block-email-spoof.md#about-impersonated-domains-or-senders): Ekleme özelliği, Microsoft 365 Defender gönderiler sayfasını kullanarak kimliğine bürünülen gönderenlere izin verir.

- [Kullanıcı gönderiminden dönüştürülmüş yönetici gönderimini görüntüleme](admin-submission.md#convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission): Özel posta kutusunu, analiz için microsoft'a ileti göndermeden kullanıcı tarafından bildirilen iletileri kesecek şekilde yapılandırın.

- [Kullanıcı ve yönetici gönderimleri için ilişkili uyarıyı görüntüleme](admin-submission.md#view-associated-alert-for-user-and-admin-email-submissions): Kullanıcı tarafından bildirilen her kimlik avı iletisi ve yönetici e-posta gönderimi için ilgili uyarıyı görüntüleyin.

- [Önceden ayarlanmış ilkeler içinde yapılandırılabilir kimliğe bürünme koruması özel kullanıcıları ve etki alanları ve artırılmış kapsam](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/configurable-impersonation-protection-and-scope-for-preset/ba-p/3294459):
  - (Seç) Kuruluşun tamamına Önceden Belirlenmiş Katı/Standart ilkeleri uygulayın ve belirli alıcı kullanıcıları, grupları veya etki alanlarını seçme zahmetini ortadan kaldırarak kuruluşunuzun tüm alıcı kullanıcılarının güvenliğini sağlayın.
  - Önceden Belirlenmiş Katı/Standart ilkeler içindeki özel kullanıcılar ve özel etki alanları için kimliğe bürünme koruma ayarlarını yapılandırın ve hedeflenen kullanıcılarınızı ve hedeflenen etki alanınızı kimliğe bürünme saldırılarına karşı otomatik olarak koruyun.

- [Office 365 için Microsoft 365 Defender'de karantina deneyimini (ikinci bölüm) basitleştirme](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience-part-two/ba-p/3354687): Karantina deneyiminin kullanımını daha da kolaylaştırmak için ek özellikleri vurgular.

- [Office 365 için Microsoft Defender'da öncelik hesapları için farklı koruma tanıtımı: Öncelik hesapları için](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-differentiated-protection-for-priority-accounts-in/ba-p/3283838) farklı korumanın GCC, GCC-H ve DoD kullanılabilirliğine giriş.

## <a name="april-2022"></a>Nisan 2022

- [Microsoft 365 Defender Gelişmiş Avcılık'ta URLClickEvents tablosuna](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-the-urlclickevents-table-in-advanced-hunting-with/ba-p/3295096) giriş: Office 365 için Microsoft Defender ile gelişmiş avcılıkta UrlClickEvents tablosuna giriş.
- [El ile e-posta düzeltme iyileştirmeleri](/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365): Yeni eylem odaklı bir araştırma kullanarak Office 365 için Microsoft Defender gerçekleştirilen el ile e-posta temizleme eylemlerini Microsoft 365 Defender (M365D) birleşik İşlem Merkezi'ne getirme.
- [Office 365 için Microsoft Defender'da öncelik hesapları için farklı](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-differentiated-protection-for-priority-accounts-in/ba-p/3283838) koruma tanıtımı: Öncelik hesapları için farklılaştırılmış korumanın genel kullanılabilirliğine giriş.

## <a name="march-2022"></a>Mart 2022

- [Office 365 için Microsoft Defender'de gönderim deneyimi kolaylaştırıldı](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/streamlining-the-submissions-experience-in-microsoft-defender/ba-p/3152080): Deneyiminizi daha basit hale getirmek için yeni birleşik ve kolaylaştırılmış gönderim sürecine giriş.

## <a name="january-2022"></a>Ocak 2022

- [Office 365 için Microsoft Defender için Tehdit Avcılığı ve Araştırma Deneyimleri güncelleştirildi](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/updated-hunting-and-investigation-experiences-for-microsoft/ba-p/3002015): tehdit gezgini ve gerçek zamanlı algılamalar için deneyim güncelleştirmelerinin yanı sıra Office 365 için Defender deneyimler için e-posta özet panelini tanıtma.

## <a name="october-2021"></a>Ekim 2021

- [Gelişmiş Teslim DKIM geliştirmesi](configure-advanced-delivery.md): Üçüncü taraf kimlik avı simülasyon yapılandırmasının bir parçası olarak DKIM etki alanı girişi desteği eklendi.
- [Varsayılan Olarak Güvenli](secure-by-default.md): Exchange posta akışı kuralları (taşıma kuralları olarak da bilinir) için Varsayılan Olarak Genişletilmiş Güvenli.

## <a name="september-2021"></a>Eylül 2021

- [Office 365 için Defender'de geliştirilmiş raporlama deneyimi](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/improving-the-reporting-experience-in-microsoft-defender-for/ba-p/2760898)
- [Karantina ilkeleri](quarantine-policies.md): Yöneticiler, karantinaya alınan iletilere alıcı erişimi için ayrıntılı denetim yapılandırabilir ve son kullanıcı istenmeyen posta bildirimlerini özelleştirebilir.
  - [Yönetici deneyimi videosu](https://youtu.be/vnar4HowfpY)
  - [Son kullanıcı deneyiminin videosu](https://youtu.be/s-vozLO43rI)
  - Karantina deneyimine gelen diğer yeni özellikler şu blog gönderisinde açıklanmıştır: [Karantina deneyimini basitleştirme](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388).
- Portal yeniden yönlendirmesi varsayılan olarak başlar ve kullanıcıları Güvenlik & Uyumluluğu'ndan Microsoft 365 Defender'a <https://security.microsoft.com>yönlendirir. Bu konuda daha fazla bilgi için bkz. [Office 365 Güvenlik & Uyumluluk Merkezi'nden hesapları Microsoft 365 Defender'a yönlendirme](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)

## <a name="august-2021"></a>Ağustos 2021

- [bildirilen iletiler için gözden Yönetici](admin-review-reported-message.md): Yöneticiler artık bildirilen iletileri gözden geçirdikten sonra son kullanıcılara şablonlu iletiler gönderebilir. Şablonlar, kuruluşunuz için ve yöneticinizin kararına göre özelleştirilebilir.
- Engellenen ileti yönetici gönderme işleminin bir parçası olarak gönderildiyse, ou artık Kiracı İzin Ver/Engelle Listesine izin verme girdileri ekleyebilir. Bloğun yapısına bağlı olarak, gönderilen URL, dosya ve/veya gönderen izin verme izni Kiracı İzin Ver/Engelle Listesine eklenir. Çoğu durumda, sisteme biraz zaman vermek ve garanti edilirse doğal olarak izin vermek için izinler eklenir. Bazı durumlarda Microsoft, izin verme işlemini sizin için yönetir. Daha fazla bilgi için bkz.:
  - [Gönderimler portalında URL'ler için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-urls-in-the-submissions-portal)
  - [Gönderimler portalında dosyalar için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın](allow-block-files.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-files-in-the-submissions-portal)
  - [Gönderimler portalında etki alanları ve e-posta adresleri için izin verme girdileri oluşturmak için Microsoft 365 Defender portalını kullanın](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)

## <a name="july-2021"></a>Temmuz 2021

- [Otomatik araştırmalarda Email çözümleme geliştirmeleri](email-analysis-investigations.md)
- [Gelişmiş Teslim](configure-advanced-delivery.md): Üçüncü taraf kimlik avı simülasyonlarının kullanıcılara ve filtrelenmemiş iletilerin güvenlik işlemi posta kutularına teslimini yapılandırmaya yönelik yeni bir özellik sunar.
- [Microsoft Teams için Güvenli Bağlantılar](safe-links.md#safe-links-settings-for-microsoft-teams)
- Şu senaryolar için yeni uyarı ilkeleri: güvenliği aşılmış posta kutuları, Forms kimlik avı, geçersiz kılmalar nedeniyle teslim edilen kötü amaçlı postalar ve ZAP'ı yuvarlama
  - Şüpheli e-posta iletme etkinliği
  - Kullanıcının formları paylaşması ve yanıt toplaması kısıtlandı
  - Olası kimlik avı girişimi nedeniyle form engellendi
  - Kimlik avı olarak işaretlenen ve onaylanan form
  - [ZAP için yeni uyarı ilkeleri](../../compliance/new-defender-alert-policies.md)
- Office 365 için Microsoft Defender uyarıları artık Microsoft 365 Defender ile tümleştirilmiştir - [Microsoft 365 Defender Birleşik Uyarılar Kuyruğu ve Birleşik Uyarılar Kuyruğu](../defender/investigate-alerts.md)
- [Kullanıcı Etiketleri](user-tags.md) artık Office 365 Güvenlik & Uyumluluğu'ndaki uyarılar kuyruğu ve ayrıntılar ve hedeflenen uyarı ilkeleri oluşturmak için kullanıcı etiketlerine özel uyarı ilkelerinin kapsamını belirleme dahil olmak üzere Office 365 için Microsoft Defender uyarı deneyimiyle tümleştirilmiştir.
  - Etiketler, Microsoft 365 Defender portalındaki birleşik uyarılar kuyruğunda da kullanılabilir (Office 365 için Microsoft Defender Plan 2)

## <a name="june-2021"></a>Haziran 2021

- Kimlik avı önleme ilkeleri içinde yeni ilk kişi güvenliği ipucu ayarı. Bu güvenlik ipucu, alıcılar ilk olarak bir gönderenden e-posta aldığında veya genellikle gönderenden e-posta almadığında gösterilir. Bu ayar ve yapılandırma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
  - [İlk temas emniyet ipucu](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [EOP'de kimlik avı önleme ilkelerini yapılandırma](configure-anti-phishing-policies-eop.md)
  - [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>Nisan/Mayıs 2021

- [Email varlık sayfası](mdo-email-entity-page.md): Tehditler, kimlik doğrulaması ve algılamalar, patlama ayrıntıları ve yepyeni bir e-posta önizleme deneyimiyle zenginleştirilmiş bilgiler içeren bir e-postanın birleşik 360 derecelik görünümü.
- [Office 365 Yönetim API'si](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events): Teslim eylemini, özgün ve en son teslim konumlarını ve güncelleştirilmiş algılama ayrıntılarını eklemek için EmailEvents'e (RecordType 28) Güncelleştirmeler.
- [Office 365 için Defender için Tehdit Analizi](/microsoft-365/security/defender/threat-analytics): Etkin tehdit aktörlerini, popüler teknikleri ve saldırı yüzeylerini ve devam eden kampanyalar konusunda Microsoft araştırmacılarının kapsamlı raporlamalarını görüntüleyin.

## <a name="februarymarch-2021"></a>Şubat/Mart 2021

- [Tehdit avcılığı deneyimlerinde](threat-explorer.md) Uyarı Kimliği tümleştirmesi (Uyarı Kimliği ve Alert-Explorer gezinti kullanarak arama)
- [Avlanma deneyimlerinde](threat-explorer.md) 9990'dan 200.000'e kadar kayıt ihracatı sınırlarını artırma
- Gezgin (ve Gerçek zamanlı algılamalar) veri saklama ve deneme kiracıları için arama sınırını [tehdit avcılığı deneyimlerinde](threat-explorer.md) 7 (önceki sınır) ile 30 gün arasında genişletme
- Korumalı kullanıcılara veya etki alanlarına yönelik kimliğe bürünme saldırılarını aramak için Gezgin içinde **Kimliğine Bürünülen etki alanı** ve **Kimliğine Bürünülen kullanıcı** (ve Gerçek zamanlı algılamalar) adlı yeni tehdit avcılığı özetleri. Daha fazla bilgi için [ayrıntılara](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains) bakın. (Office 365 için Microsoft Defender Plan 1 veya Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Office 365 için Microsoft Defender Plan 1 ve Plan 2

Office 365 için Microsoft Defender iki planda kullanılabilir olduğunu biliyor muydunuz? [Her planın neler içerdiği hakkında daha fazla bilgi edinin](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 yol haritası](https://www.microsoft.com/microsoft-365/roadmap)
- [hizmet açıklamasını Office 365 için Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
