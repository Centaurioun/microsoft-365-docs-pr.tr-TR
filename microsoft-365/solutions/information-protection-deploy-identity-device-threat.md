---
title: Veri gizliliği düzenlemesi için kimlik, cihaz ve tehdit koruması kullanma
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Microsoft 365'in kimlik, cihaz ve tehdit koruma hizmetleriyle kişisel veri ihlallerini önleyin.
ms.openlocfilehash: da779767bedfccf7067b100e7e02cdde9faf12f9
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67582020"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Veri gizliliği düzenlemesi için kimlik, cihaz ve tehdit koruması kullanma

Microsoft 365, kuruluşların veri gizliliğiyle ilgili uyumluluk düzenlemelerine uymaya yardımcı olmak için kullanabileceği bir dizi kimlik, cihaz ve tehdit koruma özelliği sağlar. Bu makalede, veri gizliliği düzenlemelerinin bu alanlarda ne gerektirdiği açıklanır ve uygulama gereksinimlerini karşılamanıza yardımcı olacak daha fazla bilgi için bağlantılar içeren ilgili Microsoft 365 özellikleri ve hizmetlerinin bir listesi sağlanır.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Kimlik, cihaz ve tehdit korumasının veri gizliliği düzenlemesi ile ilişkisi

Veri gizliliği düzenlemeleri özgüllüklerine göre değişiklik gösterse de, çağrılarının özü GDPR'nin 5(1)(f) maddesinde yer almaktadır ve bu da şunları belirtir:

- Kişisel veriler, yetkisiz veya yasa dışı işlemeye karşı koruma ve uygun teknik veya kurumsal önlemler ('bütünlük ve gizlilik') kullanılarak yanlışlıkla kaybedilme, imha veya hasara karşı koruma dahil olmak üzere kişisel verilerin uygun güvenliğini sağlayacak şekilde işlenir.

Kişisel veri ihlalleri genellikle yönetim veya son kullanıcı hesabının güvenliğinin aşılmasına ve kötü amaçlı sistem erişimine neden olduğundan. Örneğin, bir yönetici hesabı hack'i müşteri kredi kartı numaralarının veya diğer kişisel bilgilerin sızması ile sonuçlanabilir. Microsoft 365 ile sunulan genel olarak önerilen tüm kimlik, cihaz ve tehdit koruması, Uyumluluk Yöneticisi'nde bulunan uyumluluk puanınıza yansıtılacak şekilde uygulanmalıdır.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Değerlendirme çalışmanızın sonuçlarını ve Uyumluluk Yöneticisi'ni kullanma

Uyumluluk Yöneticisi şu kategorileri kullanarak kimlik, cihaz ve tehdit koruması içerir:

- Kimlik **, Denetim Erişimi** kategorisine karşılık gelir
- Cihaz **, Cihazları Yönet** kategorisine karşılık gelir
- Tehdit koruması, **Tehditlere Karşı Koru** kategorisine karşılık gelir
 
Bunlar dört ana veri gizliliği düzenlemesi içeren örnek kümemiz genelinde seçilirse, Uyumluluk Yöneticisi çoğu "27" puanlanan 90 iyileştirme eylemi belirtir. Bu kadar büyük bir sayı, uyumluluk yöneticisi tarafından bu kategoriler için çağrıldığından, daha yaygın olanlardan bazıları başvuru için burada listelenmiştir.

Kimlik için [Azure Active Directory 'yi (Azure AD)](https://azure.microsoft.com/services/active-directory/) ve aşağıdakileri yapabileceğiniz **Denetim Erişimi** kategorisini kullanın:

- Yeniden yürütmeye dayanıklı kimlik doğrulamasını uygulama ("Ortadaki adam" saldırılarını önlemek için)
- Eski kimlik doğrulamasını engelle.
- Kullanıcı riski ve kullanıcı oturum açma riski ilkelerini yapılandırın.
- Yöneticiler ve yönetici olmayanlar için Koşullu Erişim ve çok faktörlü kimlik doğrulamasını (MFA) etkinleştirin.
- Parola ilkelerini yapılandırın ve zorunlu kılın.
- Azure AD Privileged Identity Management ile ayrıcalıklı hesaplara erişimi kısıtlayın.
- Sonlandırma sırasında erişimi devre dışı bırakın.
- Kullanıcı hesaplarını ve durum değişikliklerini denetleyin.
- Rol grubu ve yönetim değişikliklerini gözden geçirin.

Cihazlar için [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) ve **şunları yapabileceğiniz Cihazları Yönet** kategorisini kullanın:

- Jail broken ve rooted mobil cihazları engelleyin.
- mobil cihaz yönetimi için Intune yapılandırın.
- Android, iOS, macOS ve Windows cihazları için uyumluluk ilkeleri oluşturun.
- Android, iOS, macOS ve Windows cihazları için bir cihaz yapılandırma profili oluşturun.
- iOS ve Windows için uygulama koruma ilkeleri oluşturun.
- Kilit ekranı ile bilgileri gizleyebilirsiniz.
- Mobil cihazlar için parola ilkeleri uygulayın.
- Mobil cihazların etkinlik dışı olarak kilitlenmesini zorunlu kılar.
- Birden çok oturum açma hatasında mobil cihazların silinmesini gerektir.

**Tehditlere Karşı Koru** kategorisi için [Exchange Online Protection ve Office 365 için Microsoft Defender](../security/office-365-security/defender-for-office-365.md) kullanın. Bu kategoride şunları yapabilirsiniz:

- Gönderen kimlik doğrulamasını etkinleştirin (SPF, DMARC ve DKIM).
- kimlik avı önleme ilkelerini Office 365 için Microsoft Defender ayarlayın.
- Güvenli Ekler'i uygulayın.
- Güvenli Bağlantılar uygulama.
- Kötü amaçlı yazılım algılama ve yanıt ilkeleri uygulayın.
- Giden ve gelen istenmeyen posta ilkelerini uygulayın.

### <a name="references"></a>Başvuru:

- [Genel kimlik ve cihaz erişim ilkeleri](../security/office-365-security/identity-access-policies.md)
- [Office 365 tehditlere karşı koruma](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Güvenli Ekleri Kaydetme](../security/office-365-security/safe-attachments.md)
- [Güvenli Bağlantılar](../security/office-365-security/safe-links.md)
- [Güvenli Belgeler](../security/office-365-security/safe-docs.md)
