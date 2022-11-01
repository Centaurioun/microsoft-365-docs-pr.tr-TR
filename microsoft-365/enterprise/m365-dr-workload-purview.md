---
title: Microsoft Purview için Data Residency
description: Microsoft Purview için Data Residency
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
ms.openlocfilehash: c9eb616409de83bc08ca8140a41cd90ad10ba2dc
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806204"
---
# <a name="data-residency-for-microsoft-purview"></a>Microsoft Purview için Data Residency

Aşağıda açıklandığı gibi Purview hizmet kümesi için veri yerleşimi taahhütleri Gelişmiş Data Residency eklentisiyle sağlanır.
Aşağıda açıklanan hizmetler için ilgili taahhütler için gerekli koşullar şunlardır:

1. _Kiracının_ _Yerel Bölge Coğrafyası veya Genişletilmiş Yerel Bölge Coğrafyası'nda_ yer alan bir kaydolma ülkesi _vardır_.
1. _Kiracı, Kiracıdaki_ tüm kullanıcılar için geçerli bir Gelişmiş Data Residency _aboneliğine sahiptir_.
1. Purview hizmeti Müşteri Verileri _Yerel Bölge Coğrafyası_ veya _Genişletilmiş Yerel Bölge Coğrafyası'nda_ sağlanır.

## <a name="migration"></a>Geçiş

Purview hizmetlerini destekleyen Müşteri Verileri, Exchange Online ve SharePoint Online hizmetleriyle yakından uyumlu hale getirildiğinden, Purview hizmetlerinin veri yerleşimi taahhütlerini yerine getirmek için gerekirse geçirilen verilerin büyük bir çoğunluğu bu hizmetler tarafından işlenir. Bir Azure Hizmetinde Müşteri Verilerini desteklemenin korunduğu durumlarda, söz konusu verilerin geçişi temel alınan Exchange Online/SharePoint Online verilerinin geçişine bağlıdır.

## <a name="how-can-i-determine-customer-data-location"></a>Müşteri Verilerinin konumunu nasıl belirleyebilirim?

_Kiracı_ Yönetici Merkezi'nde gerçek veri konumunu güncelleştirme sürecindeyiz.  Bu değişiklik tamamlandığında, Yönetici->Settings->Kuruluş Ayarları->Kuruluş Profili->Veri Konumu'na giderek, işlenen veriler için gerçek veri konumunu görebilirsiniz.  Bu değişiklik görünene kadar, bu hizmet için kaydedilmiş verilerinizin nerede depolandığını anlamak için Exchange Online veri konumu bilgilerini görüntüleyebilirsiniz.

### <a name="purview-audit-standard"></a>Purview Denetimi (Standart)

#### <a name="summary"></a>Özet

Hizmet belgeleri: [Microsoft Purview denetim çözümleri](/microsoft-365/compliance/auditing-solutions-overview)

Yetenek özeti: Microsoft Purview Denetim (Standart), denetim etkinlikleri için verilerinizi günlüğe kaydedip aramanızı ve adli tıp, BT ve uyumluluk çalışmaları ile yasal araştırmalarınızı güçlendirebilmenizi sağlar.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Purview Denetimi (Standart) için bekleyen müşteri verileri taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#purview-audit-standard) bakın.

### <a name="purview-audit-premium"></a>Purview Denetimi (Premium)

#### <a name="summary"></a>Özet

Hizmet belgeleri: [Microsoft Purview denetim çözümleri](/microsoft-365/compliance/auditing-solutions-overview)

Yetenek özeti: Microsoft Purview Denetim (Premium), denetim günlüğü saklama ilkeleri, denetim kayıtlarının daha uzun süre saklanması, yüksek değerli kritik olayları tanımlama özelliği ve Office 365 Yönetim Etkinliği API'sine daha yüksek bant genişliği erişimi sağlayarak Denetim (Standart) özelliklerini temel alır.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Purview Denetimi (Premium) için bekleyen müşteri verileri taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#purview-audit-premium) bakın.

### <a name="data-lifecycle-management---data-retention"></a>Veri yaşam döngüsü yönetimi - Veri Saklama

#### <a name="summary"></a>Özet

ADR, Purview Veri yaşam döngüsü yönetimindeki aşağıdaki hizmetler için geçerlidir: Veri Saklama:

- El ile saklama etiketleri
- Temel kuruluş genelinde veya konum genelinde saklama ilkeleri
- Kural tabanlı otomatik saklama ilkeleri
- Machine Learning tabanlı saklama
- Teams ileti saklama ilkeleri

Hizmet belgeleri:  [Bekletme ilkeleri & etiketleri hakkında bilgi edinin](/microsoft-365/compliance/retention)

Bekletme ayarlarının farklı iş yükleri için nasıl çalıştığı hakkında daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- [Exchange için bekletme hakkında bilgi edinin](/microsoft-365/compliance/retention-policies-exchange)
- [SharePoint ve OneDrive için bekletme hakkında bilgi edinin](/microsoft-365/compliance/retention-policies-sharepoint)
- [Microsoft Teams için bekletme hakkında bilgi edinin](/microsoft-365/compliance/retention-policies-teams)

Yetenek özeti: E-posta, belgeler ve Teams için ilke yönetimiyle içeriği saklamanıza veya silmenize olanak tanır.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Veri yaşam döngüsü yönetimi - Veri Saklama için bekleyen müşteri verileri taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#data-lifecycle-management---data-retention) bakın.

### <a name="data-lifecycle-management---records-management"></a>Veri yaşam döngüsü yönetimi - Kayıt Yönetimi

#### <a name="summary"></a>Özet

Hizmet belgeleri: [Microsoft Purview Kayıt Yönetimi hakkında bilgi edinin](/microsoft-365/compliance/records-management)

Yetenek özeti: Her türden kuruluş, kurumsal verileri genelinde mevzuat, yasal ve iş açısından kritik kayıtları yönetmek için bir kayıt yönetimi çözümü gerektirir. Microsoft Purview için kayıt yönetimi, bir kuruluşun yasal yükümlülüklerini yönetmesine yardımcı olur, düzenlemelere uyumluluğu gösterme olanağı sağlar ve artık saklanması gerekmeyen, artık değerli olmayan veya iş amaçları için artık gerekli olmayan öğelerin düzenli olarak elden bırakılmasıyla verimliliği artırır.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Veri yaşam döngüsü yönetimi - Kayıt Yönetimi için bekleyen belirli Müşteri Verileri taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#data-lifecycle-management---records-management) bakın.

### <a name="information-protection---sensitivity-labels"></a>Information Protection - Duyarlılık etiketleri

#### <a name="summary"></a>Özet

ADR, Purview Information Protection duyarlılık etiketleri içindeki aşağıdaki hizmetler için geçerlidir:

- Office 365'de el ile, varsayılan ve zorunlu duyarlılık etiketlemesi
- Office 365 uygulamalarında otomatik duyarlılık etiketlemesi
- Exchange, SharePoint ve OneDrive'da otomatik duyarlılık etiketleri
- Gelişmiş sınıflandırmaya dayalı duyarlılık etiketleri
- Office 365'deki kapsayıcılar için duyarlılık etiketlemesi

Hizmet belgeleri:

- [Duyarlılık etiketleri hakkında bilgi edinin](/microsoft-365/compliance/sensitivity-labels)
- [Etkinlik gezginini kullanmaya başlama](/microsoft-365/compliance/data-classification-activity-explorer)

Özellik özeti: Microsoft Purview Bilgi Koruması duyarlılık etiketleri, kuruluşunuzun verilerini sınıflandırmanıza ve korumanıza olanak tanırken, kullanıcı üretkenliğinin ve işbirliği yapma becerilerinin engellenmediğinden emin olmanıza olanak tanır.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Information Protection - Duyarlılık etiketleri için belirliCustomer Data at rest taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#information-protection---sensitivity-labels) bakın.

### <a name="information-protection---data-loss-prevention-dlp"></a>Information Protection - Veri Kaybı Önleme (DLP)

#### <a name="summary"></a>Özet

ADR, Purview Information Protection, Veri Kaybı Önleme (DLP) içindeki aşağıdaki hizmetler için geçerlidir:

- E-postalar ve dosyalar için Office 365 Veri Kaybı Önleme (DLP)
- Teams için DLP sohbeti

Hizmet belgeleri: [Veri kaybını önleme hakkında bilgi edinin](/microsoft-365/compliance/dlp-learn-about-dlp)

Yetenek özeti:

Kuruluşların denetimi altında finansal veriler, özel veriler, kredi kartı numaraları, sağlık kayıtları veya sosyal güvenlik numaraları gibi hassas bilgiler bulunur. Bu hassas verilerin korunmasına ve riskin azaltılmasına yardımcı olmak için, kullanıcılarının bunları sahip olmaması gereken kişilerle uygunsuz bir şekilde paylaşmasını önlemek için bir yönteme ihtiyaçları vardır. Bu uygulamaya veri kaybı önleme (DLP) adı verilir.

Microsoft Purview'da, DLP ilkelerini tanımlayıp uygulayarak veri kaybı önleme uygularsınız. DLP ilkesiyle hassas öğeleri tanımlayabilir, izleyebilir ve otomatik olarak koruyabilirsiniz:

- Teams, Exchange, SharePoint ve OneDrive gibi Microsoft 365 hizmetleri
- Word, Excel ve PowerPoint gibi Office uygulamaları
- Windows 10, Windows 11 ve macOS (Catalina 10.15 ve üzeri) uç noktaları
- Microsoft dışı bulut uygulamaları
- şirket içi dosya paylaşımları ve şirket içi SharePoint.

DLP, hassas öğeleri yalnızca basit bir metin taramasıyla değil, derin içerik analizini kullanarak algılar. İçerik, normal ifadelerin değerlendirilmesi, iç işlev doğrulaması ve birincil veri eşleşmesine yakın ikincil veri eşleşmeleri tarafından anahtar sözcüklerle yapılan birincil veri eşleşmeleri için analiz edilir. Bunun ötesinde DLP, DLP ilkelerinizle eşleşen içeriği algılamak için makine öğrenmesi algoritmalarını ve diğer yöntemleri de kullanır.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Information Protection - Veri Kaybı Önleme (DLP) için bekleyen müşteri verilerine ilişkin taahhüt için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#information-protection---data-loss-prevention-dlp) bakın.

### <a name="information-protection---office-message-encryption"></a>Information Protection - Office İleti Şifrelemesi

#### <a name="summary"></a>Özet

ADR, Purview Information Protection, Office İleti Şifrelemesi içindeki aşağıdaki hizmetler için geçerlidir:

- Temel Office İleti Şifrelemesi
- Gelişmiş Office İleti Şifrelemesi

Hizmet belgeleri: [Office 365 İleti Şifrelemesi - Microsoft Purview](/microsoft-365/compliance/ome)

Yetenek özeti: Office 365 İleti Şifrelemesi ile kuruluşunuz, kuruluşunuzun içindeki ve dışındaki kişiler arasında şifreli e-posta iletileri gönderebilir ve alabilir. Office 365 İleti Şifrelemesi Outlook.com, Yahoo!, Gmail ve diğer e-posta hizmetleriyle çalışır. Email ileti şifrelemesi, yalnızca hedeflenen alıcıların ileti içeriğini görüntüleyebilmesini sağlamaya yardımcı olur.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Information Protection - Office İleti Şifrelemesi için bekleyen belirli Müşteri Verileri taahhüdü için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#information-protection---office-message-encryption) bakın.

### <a name="insider-risk-management---information-barriers"></a>Insider Risk Management - Bilgi Engelleri

#### <a name="summary"></a>Özet

Hizmet belgeleri: [Bilgi engelleri hakkında bilgi edinin](/microsoft-365/compliance/information-barriers)

Yetenek özeti: Microsoft Purview Bilgi Engelleri (IB), Microsoft Teams, SharePoint ve OneDrive'daki gruplarla kullanıcılar arasındaki iki yönlü iletişimi ve işbirliğini kısıtlamanıza olanak tanıyan bir uyumluluk çözümüdür. IB, genellikle yüksek oranda düzenlenmiş sektörlerde kullanılır ve çıkar çatışmalarını önlemeye ve kullanıcılarla kuruluş alanları arasındaki iç bilgileri korumaya yardımcı olabilir.

#### <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Taahhüt:

Insider Risk Yönetimi - Bilgi Engelleri için bekleyen müşteri verilerine ilişkin taahhüt için lütfen [ADR Taahhüdü sayfasına](m365-dr-commitments.md#insider-risk-management---information-barriers) bakın.
