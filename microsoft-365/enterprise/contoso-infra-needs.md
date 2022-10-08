---
title: Contoso BT altyapısı ve iş gereksinimleri
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso şirket içi BT altyapısının temel yapısını ve şirketin iş ihtiyaçlarının kuruluş için Microsoft 365 tarafından nasıl karşılandığını anlayın.
ms.openlocfilehash: 6dff78cd3cbc7a4c1e27a647f98b0573a4ea3947
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68186776"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso BT altyapısı ve iş gereksinimleri

Contoso, şirket içi, merkezi bir BT altyapısından bulut tabanlı kişisel üretkenlik iş yüklerini ve uygulamalarını içeren bulut kapsayıcı bir kuruluma geçiş ediyor.

## <a name="existing-contoso-it-infrastructure"></a>Mevcut Contoso BT altyapısı

Contoso, Paris'in merkezinde uygulama veri merkezleriyle çoğunlukla merkezi bir şirket içi BT altyapısı kullanır.

Burada uygulama veri merkezleri, DMZ ve internet bulunan genel merkez ofisi yer alır.

![Mevcut Contoso BT altyapısı.](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

Şirket içi uygulama veri merkezleri konağı: 

- SQL Server ve diğer Linux veritabanlarını kullanan özel iş kolu uygulamaları.
- Bir dizi eski SharePoint sunucusu.
- Dosya depolama için kuruluş ve ekip düzeyinde sunucular.

Ayrıca, her bölgesel merkez ofisi benzer bir uygulama kümesine sahip bir sunucu kümesini destekler. Bu sunucular bölgesel BT departmanlarının denetimi altındadır.

Bu ayrı çok coğrafi veri merkezlerinin uygulamaları ve verileri arasında aranabilirlik zor olmaya devam ediyor.

Contoso genel merkezi DMZ'de farklı sunucu kümeleri şunları sağlar:

- Müşterilerin ürün, parça, malzeme ve hizmet siparişi verebildiği Contoso genel web sitesi için barındırma.
- İş ortağı iletişimi ve işbirliği için Contoso iş ortağı extranet'i barındırma.
- Contoso intranetine sanal özel ağ (VPN) tabanlı uzaktan erişim ve Paris genel merkezindeki çalışanlar için web proxy'si oluşturma.

## <a name="contoso-business-needs"></a>Contoso iş gereksinimleri

Contoso iş gereksinimleri beş ana kategoriye ayrılır:

**Verimli -lik**

- İşbirliğini kolaylaştırma

  Belgelerde gerçek zamanlı değişikliklere, daha kolay çevrimiçi toplantılara ve yakalanan konuşma yazışmalarına olanak tanıyan çevrimiçi bir modelle e-posta ve dosya paylaşımı tabanlı işbirliğini değiştirin.
- Uzak ve mobil çalışanlar için üretkenliği geliştirme

  Evden veya alanda çalışan birçok çalışanla, performans sorununa neden olan VPN çözümünü buluttaki Contoso verilerine ve kaynaklarına yüksek performanslı erişimle değiştirin.
- Yaratıcılığı ve yeniliği artırma

  Mürekkep oluşturma ve 3B görselleştirme gibi en son görsel öğrenme ve fikir geliştirme yöntemlerinden yararlanın.

**Güvenlik**

- Kimlik ve erişim yönetimi

  Çok faktörlü ve diğer kimlik doğrulama biçimlerini zorunlu tutarak kullanıcı ve yönetici hesabı kimlik bilgilerini koruyun.

- Tehdit koruması

  E-posta ve işletim sistemi tabanlı kötü amaçlı yazılımlar da dahil olmak üzere dış güvenlik tehditlerine karşı koruma sağlayın.

- Bilgi koruması

  Müşteri verileri, tasarım ve üretim belirtimleri ve çalışan bilgileri gibi yüksek değerli dijital varlıklara erişimi kilitleyin ve şifreleyin.

- Güvenlik yönetimi

  Güvenlik duruşu izleme ve tehditleri gerçek zamanlı olarak algılama ve yanıtlama.

**Uzaktan ve mobil erişim ve iş ortakları**

- Uzak ve mobil çalışanlar için güvenliği geliştirme

  Güvenli erişim, doğru uygulama davranışı ve şirket veri koruması sağlamak için kendi cihazını getir (KCG) ve şirkete ait cihaz yönetimini uygulayın.

- Çalışanlar için uzaktan erişim altyapısını azaltma

  Yaygın olarak erişilen kaynakları buluta taşıyarak bakım ve destek maliyetlerini azaltın ve uzaktan erişim çözümü için performansı geliştirin.

- İşletmeler arası (B2B) işlemler için daha iyi bağlantı ve daha düşük ek yük sağlama

  Eskiyen ve pahalı bir iş ortağı extranet'ini, federasyon kimlik doğrulaması kullanan bulut tabanlı bir çözümle değiştirin.

**Uyumluluk**

- Bölgesel mevzuat gereksinimlerine uyma

  Avrupa Birliği için Genel Veri Koruma Yönetmeliği (GDPR) gibi veri depolama, şifreleme, veri gizliliği ve kişisel veri düzenlemelerine yönelik sektör ve bölgesel düzenlemelere uyumluluğu sağlayın.

**Yönetim**

- İstemci bilgisayarlarda ve cihazlarda çalışan yazılımları yönetmek için DAHA düşük BT yükü

  Windows işletim sistemine güncelleştirmelerin yüklenmesini otomatikleştirin ve kuruluş genelinde Kurumlar için Microsoft 365 Uygulamaları.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Contoso işletme gereksinimlerinin kuruluş için Microsoft 365'e eşlenmesi

Contoso BT departmanı, dağıtım öncesinde özellikleri Microsoft 365 E5 için aşağıdaki iş gereksinimleri eşlemesini belirledi:


| Kategori | İş gereksinimi | Kurumsal ürünler veya özellikler için Microsoft 365 |
|:-------|:-----|:-----|
| Verimli -lik |  |  |
|  | İşbirliğini kolaylaştırma | Microsoft Teams, SharePoint, OneDrive |
|  | Uzak ve mobil çalışanlar için üretkenliği geliştirme | Microsoft 365 iş yükleri ve bulut tabanlı veriler |
|  | Yaratıcılığı ve yeniliği artırma | Windows Ink, İş Yerinde Cortana, PowerPoint |
| Güvenlik |  |  |
|  | Kimlik & erişim yönetimi | Azure AD Multi-Factor Authentication (MFA) ve Azure AD Privileged Identity Management (PIM) ile ayrılmış genel yönetici hesapları <br> Tüm kullanıcı hesapları için MFA <br> Koşullu Erişim <br> Güvenlik Okuyucusu <br> Windows Hello <br> Windows Credential Guard |
|  | Tehdit koruması | Gelişmiş Tehdit Analizi <br> Windows Defender <br> Office 365 için Defender <br> Office 365 için Microsoft Defender <br> Microsoft 365 tehdit araştırması ve yanıtı <br> |
|  | Bilgi koruması | Azure Information Protection <br> Veri Kaybı Önleme (DLP) <br> Windows Information Protection (WIP) <br> Bulut Uygulamaları için Microsoft Defender <br> Microsoft Intune |
|  | Güvenlik yönetimi | Bulut için Microsoft Defender  <br> Windows Defender Güvenlik Merkezi |
| Uzaktan ve mobil erişim ve iş ortakları |  |  |
|  | Uzak ve mobil çalışanlar için daha iyi güvenlik | Microsoft Intune |
|  | Çalışanlar için uzaktan erişim altyapısını azaltma | Microsoft 365 iş yükleri ve bulut tabanlı veriler |
|  | B2B işlemleri için bağlantıyı iyileştirme ve daha düşük ek yük | Federasyon kimlik doğrulaması ve bulut tabanlı kaynaklar |
| Uyumluluk |  |  |
|  | Bölgesel mevzuat gereksinimlerine uyma | Microsoft 365'teki GDPR özellikleri |
| Yönetim |  |  |
|  | İstemci güncelleştirmelerini yüklemek için DAHA düşük BT yükü | güncelleştirmeleri Windows 10 Enterprise <br> güncelleştirmeleri Kurumlar için Microsoft 365 Uygulamaları |
||||

## <a name="next-step"></a>Sonraki adım

Contoso Corporation [şirket içi ağı](contoso-networking.md) ve Microsoft 365 bulut tabanlı kaynaklara erişim ve gecikme süresi için nasıl iyileştirildiği hakkında bilgi edinin.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)
