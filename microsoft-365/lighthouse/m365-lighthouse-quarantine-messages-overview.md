---
title: Microsoft 365 Lighthouse'da Karantinaya Alınan İletilere Genel Bakış
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: shcallaw
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için karantinaya alınan iletileri yönetmeyi öğrenin.
ms.openlocfilehash: beead122e36f7282e1857bec32d0a1be8d09a473
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599395"
---
# <a name="overview-of-quarantined-messages-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse'da Karantinaya Alınan İletilere Genel Bakış

Microsoft 365 Lighthouse, tüm müşteri kiracılarınızda karantinaya alınan e-postalarla ilgili içgörüleri ve bilgileri görmenizi sağlar. Tek bir görünümden, karantinaya alınmış e-postaları önceliklendileyebilir ve uygun eylemleri gerçekleştirebilirsiniz. Kiracı Exchange Online Protection (EOP) ve Office365 Plan 1 (MDO) için Microsoft Defender'ı uyguladıysa veriler kullanılabilir.

Sol gezinti bölmesinde **Giriş'i** seçerek veya karantinaya alınan iletiler sayfasını açmak için sol gezinti bölmesinde **Veri Koruması'nı** seçerek bilgilere erişebilirsiniz.

## <a name="quarantined-messages-page"></a>Karantinaya alınan iletiler sayfası

Bu sayfadan, müşteri kiracılarınız genelinde birleştirilmiş istatistikleri, karantina verilerinin türüne ve hacmine ilişkin eğilim verilerini ve tek tek müşteri kiracılarındaki karantina kuyruklarıyla ilgili bilgileri görüntüleyebilirsiniz.

**İletilerin durumu** bölümü, Lighthouse'a eklenmiş durumdaki uygun kiracılar arasında birleştirilmiş bir görünüm sağlar. Görünüm şunları içerir:

- Karantinadaki toplam ileti sayısı
- Gözden geçirmeyi bekleyen toplam ileti sayısı
- Şu anda 30 günlük varsayılan karantina sınırına yaklaşan ve otomatik olarak kaldırılacak (süresi dolacak) iletiler
- Karantinadan çıkarılan iletiler
- Tüm kiracılarınızda etkilenen toplam posta kutusu sayısı

Veriler son 30 günü yansıtır; ancak, görünümü değiştirmek için **Zaman aralığı** filtresini kullanabilirsiniz.

**Karantina nedeni** bölümü, Exchange Online Protection (EOP) ve Office365 için Microsoft Defender Plan 1 (MDO) ilke türüne göre karantina sayılarının dökümünü içerir. Bu türler şunlardır:

- Malware
- Kimlik Avı
- Yüksek Güvenilirlikli Kimlik Avı
- Spam
- Toplu Email

Karantina listesi, kiracıya göre karantina bilgilerinin sıralanabilir bir görünümüdür. Bu görünümde, aşağıdaki bilgilere göre filtreleyebilirsiniz:

- **Karantina nedeni:** Any, Malware, Phish, High confidence phish, Spam, Bulk Email
- **İlke türü:** Any, Anti-malware, Anti-phishing, Anti-spam, Safe Attachments, Transport Rule, Unknown
- **Süresi dolmak üzere:** Herhangi biri, Bugün, iki gün içinde, yedi gün içinde

Ayrıca sütunları ayarlayabilir ve verileri kiracı, ileti durumu ve son kullanma tarihlerine göre sıralayabilirsiniz.

:::image type="content" source="../media/m365-lighthouse-data-protection/quarantine-email-page.png" alt-text="Microsoft 365 Lighthouse'de iletileri karantinaya al sayfası" lightbox="../media/m365-lighthouse-data-protection/quarantine-email-page.png":::

Microsoft **365** **Defender'da İletilere Bağlantıyı Kopyala** seçeneği, kiracınızın e-posta karantina kuyruğuna erişip yönetebileceğiniz Microsoft 365 Defender portalın bağlantısını sağlar. Herhangi bir işlem yapmadan önce kimlik doğrulaması yapmanız gerekir.

## <a name="related-content"></a>İlgili içerik

[Karantinaya alınan e-posta iletileri](../security/office-365-security/quarantine-email-messages.md) (makale)\
[EOP ve Office 365 için Defender güvenlik ayarları için Microsoft önerileri](../security/office-365-security/recommended-settings-for-eop-and-office365.md) (makale)\
[Exchange Online Protection (EOP) genel bakış](../security/office-365-security/exchange-online-protection-overview.md) (makale)
