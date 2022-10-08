---
title: Başvuru İlkeleri, uygulamalar ve yönergeler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- m365-security
description: Microsoft, kullanıcılarımızı kötü amaçlı, istenmeyen veya kötü amaçlı e-postalara karşı korumaya yardımcı olmak için çeşitli ilkeler, yordamlar geliştirmiş ve sektördeki en iyi yöntemleri benimsemiştir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 8cea8a26c318c7832f28f9ffaa0a740837d5894c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091707"
---
# <a name="reference-policies-practices-and-guidelines"></a>Başvuru: İlkeler, uygulamalar ve yönergeler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft, web'de en güvenilir kullanıcı deneyimini sağlamaya yardımcı olmaya kendini adamıştır. Bu nedenle Microsoft, kullanıcılarımızı kötü amaçlı, istenmeyen veya kötü amaçlı e-postalara karşı korumaya yardımcı olmak için çeşitli ilkeler, yordamlar geliştirmiş ve çeşitli sektör en iyi uygulamalarını benimsemiştir. Kullanıcılara e-posta göndermeye çalışan gönderenler, bu çabaya yardımcı olmak ve olası teslim sorunlarını önlemeye yardımcı olmak için bu makaledeki yönergeleri tam olarak anlamalarını ve takip etmelerini sağlamalıdır.

Bu ilkeler ve yönergelerle uyumlu değilseniz destek ekibimizin size yardımcı olması mümkün olmayabilir. Bu makalede sunulan yönergelere, uygulamalara ve ilkelere uyuyorsanız ve gönderme IP adresinize bağlı olarak hala teslim sorunlarıyla karşılaşıyorsanız, lütfen listeden çıkarma isteği göndermek için adımları izleyin. Yönergeler için bkz. [Liste kaldırma portalını kullanarak kendinizi engellenen gönderenler listesinden kaldırma](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Genel Microsoft ilkeleri

Microsoft 365 kullanıcılarına gönderilen Email, Microsoft 365'in e-posta iletimini ve kullanımını yöneten tüm Microsoft ilkeleriyle uyumlu olmalıdır.

- Microsoft 365 için geçerli olan Hizmet Koşulları; özellikle, istenmeyen posta veya kötü amaçlı yazılım dağıtmak için hizmeti kullanma yasağı.

- [Microsoft Hizmet Sözleşmesi](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Resmi düzenlemeler

Microsoft 365 kullanıcılarına gönderilen Email, ilgili yargı yetkisindeki e-posta iletişimini yöneten tüm geçerli yasa ve düzenlemelere uymalıdır.

- [CAN-SPAM Yasası: İş İçin Uyumluluk Kılavuzu](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Beni Kaldır" Yanıtları ve Sorumlulukları: Email Pazarlamacıların "Abonelikten Çıkma" Taleplerini Yerine Getirmelidir](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Teknik yönergeler

Microsoft 365'e gönderilen Email aşağıdaki belgelerde listelenen geçerli önerilerle uyumlu olmalıdır (bazı bağlantılar yalnızca İngilizce olarak sağlanır).

- [RFC 2505: SMTP MTA'ları için İstenmeyen Posta Önleme Önerileri](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: Komut Kanal Oluşturma için SMTP Hizmet Uzantısı](https://www.ietf.org/rfc/rfc2920.txt)

Ayrıca, Microsoft 365'e bağlanan e-posta sunucularının aşağıdaki gereksinimlere uyması gerekir:

- Rfc 5321, RFC 5322 ve diğerleri de dahil olmak üzere Internet Society'nin Internet Engineering Task Force (IETF) tarafından yayımlanan gönderenin İnternet e-posta iletimi için tüm teknik standartlara uyması beklenir.

- 500 ile 599 (kalıcı teslim edilemez yanıt veya NDR olarak da bilinir) arasında sayısal bir SMTP hata yanıt kodu verildikten sonra, gönderenin bu iletiyi bu alıcıya yeniden aktarmayı denememesi gerekir.

- Birden çok teslim edilemez yanıt sonrasında, gönderenin bu alıcıya e-posta gönderme girişimlerini durdurması gerekir.

- İletiler güvenli olmayan e-posta geçişi veya proxy sunucuları aracılığıyla iletilmemelidir.

- Tek tek listelerden veya gönderen tarafından barındırılan tüm listelerden abonelikten çıkılma mekanizması açıkça belgelenmeli ve alıcıların bulması ve kullanması kolay olmalıdır.

- Dinamik IP alanından bağlantılar kabul edilemeyebilir.

- Email sunucuların geçerli ters DNS kayıtları olmalıdır.

## <a name="reputation-management"></a>Saygınlık yönetimi

Gönderenler, ISS'ler ve diğer hizmet sağlayıcıları, giden IP adreslerinizin itibarını etkin bir şekilde yönetmelidir.

## <a name="microsoft-365-limits"></a>Microsoft 365 sınırları

Gönderenler[, Exchange Online Protection Sınırları'nda](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits) listelenen Microsoft 365 sınırlarına uymalıdır.

## <a name="email-delivery-resources-and-organizations"></a>Email teslim kaynakları ve kuruluşları

Microsoft, internet ve e-posta ekosistemini geliştirmek için sektör kuruluşları ve hizmet sağlayıcılarıyla etkin bir şekilde çalışır. Bu kuruluşlar, desteklediğimiz ve gönderenlerin bağlı kalmasını önerdiğimiz en iyi uygulama belgelerini yayımladı. Bu, dünyanın dört bir yanındaki çeşitli e-posta hizmeti sağlayıcıları arasında e-posta teslim etme becerinizi geliştirir.

- [Mesajlaşma Kötü Amaçlı Yazılım Mobil Kötü Amaçlı Yazılımdan Koruma Çalışma Grubu](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [Email Gönderen & Sağlayıcı Koalisyonu](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Kötüye kullanım ve istenmeyen posta raporlama

Yasa dışı, kötü amaçlı, istenmeyen veya kötü amaçlı e-postaları bildirmek için bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md). Bu tür iletişimlerin gönderilmesi Microsoft ilkesinin ihlalidir ve onaylanan raporlarda uygun işlemler yapılır.

## <a name="law-enforcement"></a>Kolluk

Kolluk kuvvetlerinin bir üyesiyseniz ve Microsoft Corporation'a Office 365 ile ilgili yasal belgelerle hizmet vermek istiyorsanız veya Microsoft'a gönderdiğiniz yasal belgelerle ilgili sorularınız varsa lütfen (1) (425) 722-1299 numaralı telefonu arayın.
