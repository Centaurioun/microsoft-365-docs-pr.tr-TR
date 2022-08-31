---
title: Microsoft Güvenli Puan'daki yenilikler
description: Microsoft 365 Defender portalında Microsoft Güvenli Puanı'nda yapılan yeni değişiklikleri açıklar.
keywords: microsoft güvenli puanı, güvenli puan, office 365 güvenlik puanı, microsoft güvenlik puanı, Microsoft 365 Defender portalı
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.service: microsoft-365-security
ms.subservice: m365d
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: e5bea982a1cbc776a9529532bbbac4da4199fb4a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482592"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft Güvenli Puan'daki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score'u güvenlik duruşunuzun daha iyi bir temsilcisi yapmak için yeni özellikler ve iyileştirme eylemleri eklemeye devam ediyoruz.

Ne kadar çok geliştirme eylemi gerçekleştirirseniz, Güvenli Puanınız o kadar yüksek olur. Daha fazla bilgi için bkz. [Microsoft Güvenli Puanı](microsoft-secure-score.md).

Microsoft Güvenli Puanı'na [Microsoft 365 Defender portalından](microsoft-365-defender-portal.md) ulaşabilirsiniz<https://security.microsoft.com/securescore>.

## <a name="august-2022"></a>Ağustos 2022

Yeni Microsoft Bilgi Koruması önerileri artık Güvenli Puan geliştirme eylemleri olarak kullanılabilir:

- **Etiketleme**
  - M365 duyarlılık etiketlemesini Azure Purview veri haritasındaki varlıklara genişletme
  - Otomatik etiketleme veri sınıflandırma ilkelerinin ayarlandığından ve kullanıldığından emin olun
  - M365 duyarlılık etiketi veri sınıflandırma ilkelerini yayımlama
  - Veri Kaybı Önleme (DLP) ilkeleri oluşturma

Yeni Office 365 için Microsoft Defender önerileri artık Güvenli Puan geliştirme eylemleri olarak kullanılabilir:

- **İstenmeyen posta önleme - Gelen ilkesi**
  - E-posta toplu şikayet düzeyi (BCL) eşiğini 6 veya daha düşük olacak şekilde ayarlayın
  - İstenmeyen posta algılamayı gerçekleştirecek eylemi ayarlama
  - Yüksek güvenilirlikli istenmeyen posta algılama için eylem ayarlama
  - Kimlik avı algılaması için eylem ayarlama
  - Yüksek güvenilirlikli kimlik avı algılaması için eylem ayarlama
  - Toplu istenmeyen posta algılaması için eylem ayarlama
  - İstenmeyen postaları 30 gün boyunca karantinada tutma
  - İstenmeyen posta güvenlik ipuçlarının etkinleştirildiğinden emin olun
  - İstenmeyen posta önleme ilkeleri için hiçbir gönderen etki alanına izin verilmediğinden emin olun (belirli gönderenler için de işlevselliği genişletmek için "İstenmeyen posta önleme ilkeleri için gönderen etki alanlarına izin verilmediğinden emin olun" ifadesinin yerini alır)

- **İstenmeyen posta önleme - Giden ilkesi**
  - Kullanıcının saatte e-posta gönderebileceği en fazla dış alıcı sayısını ayarlama
  - Bir kullanıcının bir saat içinde gönderebileceği en fazla iç alıcı sayısını ayarlama
  - Günlük ileti sınırı ayarlama
  - İleti sınırına ulaşan kullanıcıları engelleme
  - Otomatik e-posta iletme kurallarını sistem denetimi olacak şekilde ayarlama

- **İstenmeyen posta önleme - Bağlantı filtresi**
  - Bağlantı filtresi ilkesine izin verilen IP adreslerini eklemeyin

## <a name="june-2022"></a>Haziran 2022

- Yeni Uç Nokta için Microsoft Defender ve Microsoft Defender Güvenlik Açığı Yönetimi önerileri artık Güvenli Puan geliştirme eylemleri olarak kullanılabilir:

  - Paylaşımlara çevrimdışı erişime izin verme
  - **Herkes** olarak ayarlanmış paylaşım yazma iznini kaldırma
  - Kök klasörden paylaşımları kaldırma
  - Paylaşımlar için klasör erişimi tabanlı sabit listesi ayarlama
  - Uç Nokta için Microsoft Defender temel bileşenlerini güncelleştirme

- Güvenli Puan geliştirme eylemi olarak yeni bir Kimlik için Microsoft Defender önerisi sağlanır:

  - Güvenli olmayan etki alanı yapılandırmalarını çözme

- Yeni [bir uygulama idaresi](/defender-cloud-apps/app-governance-manage-app-governance) önerisi artık Güvenli Puan geliştirme eylemi olarak kullanılabilir:

  - Öncelikli hesaplardan alınan onay ile uygulamaları düzenleme

- Yeni Salesforce ve ServiceNow önerileri artık Microsoft Defender for Cloud Apps müşterileri için Güvenli Puan geliştirme eylemleri olarak kullanılabilir. Daha fazla bilgi için bkz. [SaaS Güvenlik Duruş Yönetimine genel bakış](https://aka.ms/saas_security_posture_management).

> [!NOTE]
> Salesforce ve ServiceNow denetimleri artık genel önizlemede kullanılabilir.

## <a name="april-2022"></a>Nisan 2022

- Uzak bağlantılar için kullanıcı kimlik doğrulamasını açma

## <a name="december-2021"></a>Aralık 2021

- Blok modunda Güvenli Ekler'i açma
- Exchange Online takvim ayrıntılarının dış kullanıcılarla paylaşılmasını engelleme
- Office istemcileri için Güvenli Belgeler'i açma
- Kötü amaçlı yazılımdan koruma ilkeleri için yaygın ekler filtre ayarını açma
- İstenmeyen posta önleme ilkeleri için gönderen etki alanlarına izin verilmediğinden emin olun
- E-posta iletileri için Güvenli Bağlantılar ilkeleri oluşturma
- Kötü amaçlı yazılımlar için sıfır saatlik otomatik temizleme ilkeleri oluşturma
- SharePoint, OneDrive ve Microsoft Teams'de Office 365 için Microsoft Defender açma
- Kimlik avı iletileri için sıfır saatlik otomatik temizleme ilkeleri oluşturma
- İstenmeyen posta iletileri için sıfır saatlik otomatik temizleme ilkeleri oluşturma
- Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi
- Tam tarama sırasında çıkarılabilir sürücülerin taranma özelliğini açma

## <a name="we-want-to-hear-from-you"></a>Sizden haber almak istiyoruz

Herhangi bir sorununuz varsa [Güvenlik, Gizlilik & Uyumluluk](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) topluluğuna göndererek bize bildirin. Topluluğu izliyoruz ve yardım sağlayacağız.

## <a name="related-resources"></a>İlgili kaynaklar

- [Güvenlik duruşlarınızı değerlendirin](microsoft-secure-score-improvement-actions.md)
- [Microsoft Güvenli Puan geçmişinizi izleme ve hedefleri karşılama](microsoft-secure-score-history-metrics-trends.md)
- [Yapılacak yenilikler](microsoft-secure-score-whats-coming.md)
