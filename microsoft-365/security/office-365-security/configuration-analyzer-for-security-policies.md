---
title: Güvenlik ilkeleri için yapılandırma çözümleyicisi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Yöneticiler, önceden ayarlanmış güvenlik ilkelerinde Standart koruma ve Katı koruma'daki ayarların altındaki güvenlik ilkelerini bulmak ve düzeltmek için yapılandırma çözümleyicisini kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b5f33bb7b30f63ad5d6705b7a9cbffb38f280a2c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479169"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP ve Office 365 için Microsoft Defender koruma ilkeleri için yapılandırma çözümleyicisi

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender portalındaki yapılandırma çözümleyicisi, ayarların önceden ayarlanmış güvenlik ilkelerindeki Standart koruma ve Katı koruma profili ayarlarının altında olduğu [güvenlik ilkelerini](preset-security-policies.md) bulmak ve düzeltmek için merkezi bir konum sağlar.

Aşağıdaki ilke türleri yapılandırma çözümleyicisi tarafından analiz edilir:

- **Exchange Online Protection (EOP) ilkeleri**: Bu, Exchange Online posta kutularına sahip Microsoft 365 kuruluşlarını ve Exchange Online posta kutusu olmayan tek başına EOP kuruluşlarını içerir:
  - [İstenmeyen posta önleme ilkeleri](configure-your-spam-filter-policies.md).
  - [Kötü amaçlı yazılımdan koruma ilkeleri](configure-anti-malware-policies.md).
  - [EOP kimlik avı önleme ilkeleri](set-up-anti-phishing-policies.md#spoof-settings).

- **Office 365 için Microsoft Defender ilkeleri**: Bu, Microsoft 365 E5 veya Office 365 için Defender eklenti abonelikleri olan kuruluşları içerir:
  - Office 365 için Microsoft Defender'da kimlik avı önleme ilkeleri şunlardır:
    - EOP kimlik avı önleme ilkelerinde kullanılabilen kimlik sahtekarlığı [ayarlarının](set-up-anti-phishing-policies.md#spoof-settings) aynısı.
    - [Kimliğe bürünme ayarları](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Gelişmiş kimlik avı eşikleri](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Güvenli Bağlantılar ilkeleri](set-up-safe-links-policies.md).
  - [Güvenli Ekler ilkeleri](set-up-safe-attachments-policies.md).

Temel olarak kullanılan Standart ve Katı ilke ayarı değerleri[, EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](recommended-settings-for-eop-and-office365.md) bölümünde açıklanmıştır.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. **Doğrudan Yapılandırma çözümleyicisi** sayfasına gitmek için kullanın<https://security.microsoft.com/configurationAnalyzer>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Bu makaledeki yordamları gerçekleştirebilmeniz için önce Microsoft 365 Defender portalında size izinler atanmalıdır:
  - Yapılandırma çözümleyicisini kullanmak **ve** güvenlik ilkelerine güncelleştirmeler yapmak için **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol gruplarının üyesi olmanız gerekir.
  - Yapılandırma çözümleyicisine salt okunur erişim için **Genel Okuyucu** veya **Güvenlik Okuyucusu** rol gruplarının üyesi olmanız gerekir.

  Daha fazla bilgi için bkz. [Microsoft 365 Defender portalında İzinler](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Kullanıcıları ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365 Defender portalında gerekli izinleri _ve_ Microsoft 365'teki diğer özellikler için izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  > - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında yapılandırma çözümleyicisini kullanma

konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>**, Şablonlu ilkeler** bölümündeki **Email & İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Yapılandırma çözümleyicisi'ne** gidin. **Doğrudan Yapılandırma çözümleyicisi** sayfasına gitmek için kullanın<https://security.microsoft.com/configurationAnalyzer>.

**Yapılandırma çözümleyicisi** sayfasında üç ana sekme vardır:

- **Standart öneriler**: Mevcut güvenlik ilkelerinizi Standart önerilerle karşılaştırın. Ayarlar değerlerinizi Standart ile aynı düzeye getirmek için ayarlayabilirsiniz.
- **Katı öneriler**: Mevcut güvenlik ilkelerinizi Katı önerilerle karşılaştırın. Ayarlar değerlerinizi Strict ile aynı düzeye getirmek için ayarlayabilirsiniz.
- **Yapılandırma kayma analizi ve geçmişi**: İlke değişikliklerini zaman içinde denetleme ve izleme.

### <a name="standard-recommendations-and-strict-recommendations-tabs-in-the-configuration-analyzer"></a>Yapılandırma çözümleyicisinde standart öneriler ve Katı öneriler sekmeleri

Varsayılan olarak, yapılandırma çözümleyicisi **Standart öneriler** sekmesinde açılır. **Katı öneriler** sekmesine geçebilirsiniz. Ayarlar, düzen ve eylemler her iki sekmede de aynıdır.

:::image type="content" source="../../media/configuration-analyzer-settings-and-recommendations-view.png" alt-text="Yapılandırma çözümleyicisindeki Ayarlar ve öneriler görünümü" lightbox="../../media/configuration-analyzer-settings-and-recommendations-view.png":::

Sekmenin ilk bölümünde, Standart veya Katı koruma ile karşılaştırıldığında iyileştirme gerektiren her ilke türündeki ayarların sayısı görüntülenir. İlke türleri şunlardır:

- **Antispam**
- **Kimlik avına karşı koruma**
- **Kötü amaçlı yazılımdan koruma**
- **Güvenli Ekler** (aboneliğiniz Office 365 için Microsoft Defender içeriyorsa)
- **Güvenli Bağlantılar** (aboneliğiniz Office 365 için Microsoft Defender içeriyorsa)

İlke türü ve numarası gösterilmiyorsa, bu türdeki tüm ilkeleriniz önerilen Standart veya Katı koruma ayarlarını karşılar.

Sekmenin geri kalanı, Standart veya Katı koruma düzeyine getirilmesi gereken ayarlar tablosudur. Tablo aşağıdaki sütunları içerir:

- **Öneriler**: Standart veya Katı koruma profilindeki ayarın değeri.
- **İlke**: Ayarı içeren etkilenen ilkenin adı.
- **İlke grubu/ayar adı**: Dikkatinizi gerektiren ayarın adı.
- **İlke türü**: İstenmeyen posta, kimlik avı önleme, kötü amaçlı yazılımdan koruma, Güvenli Bağlantılar veya Güvenli Ekler.
- **Geçerli yapılandırma**: Ayarın geçerli değeri.
- **Son değiştirme**: İlkenin en son değiştirildiği tarih.
- **Durum**: Genellikle bu değer **Başlatılmaz**.

### <a name="change-a-policy-setting-to-the-recommended-value"></a>İlke ayarını önerilen değerle değiştirme

Yapılandırma çözümleyicisinin **Standart koruma** veya **Katı koruma** sekmesinde tablodaki satırı seçin. Aşağıdaki düğmeler görüntülenir:

- **Öneri uygulama**
- **İlkeyi görüntüleme**
- **Yenile**:

Bir satır seçip **Öneri uygula'ya** tıklarsanız, bir onay iletişim kutusu (iletişim kutusunu bir daha göstermeme seçeneğiyle) görüntülenir. **Tamam'a** tıklarsanız aşağıdaki işlemler gerçekleşir:

- Ayar önerilen değere güncelleştirilir.
- **Öneri uygula** ve **Görüntüle ilkesi** kaybolur (yalnızca **Yenile** düğmesi kalır).
- Satırın **Durum** değeri **Tamamlandı** olarak değişir.

Bir satır seçip **İlkeyi görüntüle'ye** tıklarsanız, Microsoft 365 Defender portalında etkilenen ilkenin ayrıntılar açılır penceresine yönlendirilirsiniz ve burada ayarı el ile güncelleştirebilirsiniz.

Ayarı otomatik olarak veya el ile güncelleştirdikten sonra, azaltılmış öneri sayısını ve güncelleştirilmiş satırın sonuçlardan kaldırılmasını görmek için **Yenile'ye** tıklayın.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Yapılandırma çözümleyicisinde yapılandırma kayma analizi ve geçmiş sekmesi

Bu sekme, güvenlik ilkelerinizde yapılan değişiklikleri ve bu değişikliklerin Standart veya Katı ayarlarıyla karşılaştırmasını izlemenize olanak tanır. Varsayılan olarak, aşağıdaki bilgiler görüntülenir:

- **Son değiştirme**
- **Değiştiren**
- **Ayar Adı**
- **İlke**: Etkilenen ilkenin adı.
- **Tür**: İstenmeyen postadan koruma, kimlik avı önleme, kötü amaçlı yazılımdan koruma, Güvenli Bağlantılar veya Güvenli Ekler.
- **Yapılandırma değişikliği**: Ayarın eski değeri ve yeni değeri
- **Yapılandırma kaymasını**: Ayarın önerilen Standart veya Katı ayarına göre artan veya azaltılmış güvenliği gösteren **Artır** veya **Azalt** değeri.

Sonuçları filtrelemek için **Filtrele'ye** tıklayın. Görüntülenen **Filtreler** açılır listesinde aşağıdaki filtrelerden birini seçebilirsiniz:

- **Başlangıç saati** ve **Bitiş saati** (tarih): Bugünden itibaren 90 güne kadar geri dönebilirsiniz.
- **Standart koruma** veya **Katı koruma**

İşiniz bittiğinde **Uygula'ya** tıklayın.

Sonuçları bir .csv dosyasına aktarmak için **Dışarı Aktar'a** tıklayın.

Sonuçları **değiştirme ölçütü**, **Ayar adı** veya **Tür** değerine göre filtrelemek için **Arama** kutusunu kullanın.

:::image type="content" source="../../media/configuration-analyzer-configuration-drift-analysis-view.png" alt-text="Yapılandırma çözümleyicisindeki Yapılandırma kayma analizi ve geçmiş görünümü" lightbox="../../media/configuration-analyzer-configuration-drift-analysis-view.png":::
