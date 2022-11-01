---
title: Gelişmiş Data Residency Taahhütleri
description: Gelişmiş Data Residency Taahhütleri
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: e08e2a0df9c5a6a711d565c04aeb8fe6e16b0415
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806229"
---
# <a name="advanced-data-residency-commitments"></a>Gelişmiş Data Residency Taahhütleri

>[!NOTE]
>Multi-Geo aboneliği satın aldıysanız Microsoft, Microsoft 365 Gelişmiş Data Residency eklentisini ("ADR") satın almış olsanız bile yapılandırmanıza bağlı olarak bekleyen belirli müşteri verilerini birden fazla Coğrafyada depolar.  

Microsoft, ADR satın alan [uygun müşteriler](advanced-data-residency.md#eligibility) için bekleyen belirli müşteri verilerini geçerli _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ depolama taahhüdü verir.  Taahhütler aşağıda belirtilmiştir.  

## <a name="exchange-online"></a>Exchange Online

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- posta kutusu içeriğini (e-posta gövdesi, takvim girdileri ve ilgili _Yerel Bölge Coğrafyası veya Genişletilmiş Yerel Bölge Coğrafyası'nda_ depolanan e-posta eklerinin içeriği) Exchange Online.

## <a name="sharepoint-onlineonedrive-for-business"></a>SharePoint Online/OneDrive İş

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- SharePoint Online site içeriği ve bu site içinde depolanan dosyalar ve OneDrive İş karşıya yüklenen dosyalar.

## <a name="microsoft-teams"></a>Microsoft Teams

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Microsoft Teams sohbet iletileri (özel iletiler, kanal iletileri, sohbetlerde kullanılan toplantı iletileri ve görüntüler dahil) ve Microsoft Stream kullanan müşteriler için (SharePoint'te), toplantı kayıtları.

## <a name="microsoft-defender-for-office-p1"></a>Office P1 için Microsoft Defender

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- MDO P1 hizmeti içinde hiçbir müşteri verisi depolamaz.
- Exchange Online Protection (EOP). Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır: Hizmet yapılandırma verileri ve ilkeleri, karantinaya alınan e-posta ve ekler, gereksiz e-posta, not analizi, blok listeleri (URL, kiracı, kullanıcı), istenmeyen posta etki alanları, raporlar ve uyarılar

## <a name="office-for-the-web"></a>Web için Office

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Web için Office, dosyaları _Yerel Bölge Coğrafya__genişletilmiş Yerel Coğrafya'ya_/ uygun vaatleri olan bir depolama konağına depolar.

## <a name="viva-connections"></a>Viva Connections

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ depolanır:

- Viva Connections Pano ve Akış,SharePoint Online, Exchange Online ve Microsoft Teams'den alınan içeriğe sahip olabilir. Bu hizmetlerden alınan ve veri yerleşimi taahhütleri kapsamındaki tüm müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ depolanır. Daha fazla ayrıntı için lütfen [Exchange Online](m365-dr-workload-exo.md), [SharePoint Online](m365-dr-workload-spo.md) ve [Microsoft Teams](m365-dr-workload-teams.md) iş yükü veri yerleşimi sayfalarına bakın.

## <a name="viva-topics"></a>Viva Topics

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Bulunan tüm konular ve müşteri verileri parçacıkları, Exchange Online Alt Katmanda (site veya tahkim posta kutuları ve Alt Katman) ilgili _Coğrafyalarda_ depolanır. Tüm konu başlığı müşteri verileri, verilerin kiracınızın içinden geldiği _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası_ temelinde bölümlenir.
- Machine Learning ("ML") modelleri genel web verileri üzerinde eğitilir ve bu nedenle kiracınızdan herhangi bir müşteri verisi içermez. Gelecekte ML modellerinin doğruluğunu artırmak için müşteri verilerini kullanabiliriz. Bu durumda ML modellerinin veri işlemesi diğer tüm müşteri içeriğiyle aynı ilkeleri izler (veri yerleşimi, saklama, erişim denetimi, duyarlılık dahil)
- Konu vurgulama, SharePoint Online sayfası sayfanın içeriğine göre bir dil modeli çalıştırılarak ve Konu başlıkları bilgi bankası bağlanarak işlendiğinde dinamik olarak hesaplanır. Konular verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'ndaki_ Alt Katmandan alınır.
- Yönetim yapılandırma verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası_ içinde depolanır.

## <a name="purview-audit-standard"></a>Purview Denetimi (Standart)

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Hizmet yapılandırma verileri, denetlenen Etkinlikler, denetim Kayıtları ve denetim günlüğü sorgu izinleri.

## <a name="purview-audit-premium"></a>Purview Denetimi (Premium)

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Purview Denetimi (Standart) kapsamında depolanan müşteri verilerine ek olarak, yüksek değerli kritik olaylarla ilgili yapılandırma ve Müşteri Verileri.

## <a name="data-lifecycle-management---data-retention"></a>Veri yaşam döngüsü yönetimi - Veri Saklama

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Bekletme ilkesi ayarları, bekletme etiketi tanımları
- Aşağıdaki hizmetler için özgün konumlarda depolanan Müşteri Verileri:
  - Exchange e-postası
  - SharePoint sitesi
  - OneDrive hesapları
  - Microsoft 365 Grupları
  - Exchange ortak klasörleri
  - Microsoft Teams sohbetleri ve kanal iletileri
- Gizli Exchange Online posta kutularında kopyalanan ve depolanan Müşteri Verileri
  - Teams kanal iletileri
  - Teams sohbetleri
  - Teams özel kanal iletileri
  - SharePoint Online, OneDrive İş, Exchange Online ve Microsoft Teams bu hizmetler için veri yerleşimi taahhütlerini izler. Daha fazla ayrıntı için lütfen [Exchange Online](m365-dr-workload-exo.md), [SharePoint Online](m365-dr-workload-spo.md) ve [Microsoft Teams](m365-dr-workload-teams.md) iş yükü veri yerleşimi sayfalarına bakın.
- Sınıflandırıcıları eğit
- Verileri bırakma
- Bekletme etiketleri ile Veri Kaybı Önleme (DLP) ilkeleri arasındaki eşlemeler.

## <a name="data-lifecycle-management---records-management"></a>Veri yaşam döngüsü yönetimi - Kayıt Yönetimi

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Kayıt bekletme etiketi tanımları, dosya planı tanımları, olay tabanlı bekletme ilkesi ayarları, değerlendirme gözden geçirme kayıtları ve silme kayıtları

## <a name="information-protection---sensitivity-labels"></a>Information Protection - Duyarlılık etiketleri

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Etiket yapılandırması
- Etiket tanımı
- Etiket ilkeleri
- Özel yardım sayfası
- Etkinlik Gezgini ve Microsoft 365 birleşik denetim günlükleri
- Etiket değişikliği gerekçe kayıtları.

## <a name="information-protection---data-loss-prevention-dlp"></a>Information Protection - Veri Kaybı Önleme (DLP)

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- DLP yönetici yapılandırması, Uyumluluk Merkezi'ndeki DLP ilkeleri, DLP izlenen etkinlikler, ihlal geçmişi, Etkinlik Gezgini ve Microsoft 365 birleşik denetim günlükleri, karantina depolama, DLP Uyarıları ve DLP Uyarısı yönetim panosu.

## <a name="information-protection---office-message-encryption"></a>Information Protection - Office İleti Şifrelemesi

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- Şifreleme ilkeleri, yönetici ayarları ve şifrelenmiş iletiler.

## <a name="insider-risk-management---information-barriers"></a>Insider Risk Management - Bilgi Engelleri

Aşağıdaki müşteri verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ bekleyen konumda depolanır:

- İlke ayarları, risk göstergeleri ve yönetici ayarları.
