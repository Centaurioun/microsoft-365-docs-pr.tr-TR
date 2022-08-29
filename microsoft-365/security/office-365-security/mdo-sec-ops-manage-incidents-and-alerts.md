---
title: Microsoft 365 Defender'da Office 365 için Defender'dan olayları ve uyarıları yönetme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: SecOps personeli, Office 365 için Microsoft Defender'daki olayları yönetmek için Microsoft 365 Defender'daki Olaylar kuyruğunun nasıl kullanılacağını öğrenebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef744ec88f8ee81d33e537b5ffc9d128c724f84f
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67383842"
---
# <a name="manage-incidents-and-alerts-from-microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Office 365 için Microsoft Defender olayları ve uyarıları yönetme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender'daki [bir olay](/microsoft-365/security/defender/incidents-overview), bir saldırının tüm hikayesini tanımlayan bağıntılı uyarıların ve ilişkili verilerin bir koleksiyonudur. Office 365 için Defender [uyarılar](/microsoft-365/compliance/alert-policies#default-alert-policies), [otomatik araştırma ve yanıt (AIR)](office-365-air.md#the-overall-flow-of-air) ve araştırmaların sonucu yerel olarak tümleştirilir ve Microsoft 365 Defender konumundaki <https://security.microsoft.com/incidents-queue>**Olaylar** sayfasında ilişkilendirilir. Bu sayfaya _Olaylar kuyruğu_ adını vereceğiz.

Kötü amaçlı veya şüpheli etkinlikler bir varlığı (örneğin, e-posta, kullanıcılar veya posta kutuları) etkilediğinde uyarılar oluşturulur. Uyarılar, devam eden veya tamamlanan saldırılar hakkında değerli içgörüler sağlar. Ancak, devam eden bir saldırı birden çok varlığı etkileyebilir ve bu da farklı kaynaklardan birden çok uyarıya neden olabilir. Bazı yerleşik uyarılar AIR playbook'larını otomatik olarak tetikler. Bu playbook'lar, etkilenen diğer varlıkları veya şüpheli etkinlikleri aramak için bir dizi araştırma adımı uygular.

Microsoft 365 Defender'da Office 365 için Microsoft Defender uyarılarının nasıl yönetileceğini gösteren bu kısa videoyu izleyin.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGrL2]

Office 365 için Defender uyarıları, araştırmaları ve verileri otomatik olarak ilişkilendirilir. bir ilişki belirlendiğinde, güvenlik ekiplerine saldırının tamamı için görünürlük sağlamak için sistem tarafından bir olay oluşturulur.

SecOps ekiplerinin konumundaki Olaylar kuyruğundaki <https://security.microsoft.com/incidents-queue>Office 365 için Defender gelen olayları ve uyarıları yönetmesini kesinlikle öneririz. Bu yaklaşımın aşağıdaki avantajları vardır:

- [Yönetim](/microsoft-365/security/defender/manage-incidents) için birden çok seçenek:
  - Önceliği
  - Filtreleme
  - Sınıflandırma
  - Etiket yönetimi

  Olayları doğrudan kuyruktan alabilir veya birine atayabilirsiniz. Açıklamalar ve açıklama geçmişi ilerleme durumunu izlemeye yardımcı olabilir.

- Saldırı Microsoft Defender<sup>\*</sup> tarafından korunan diğer iş yüklerini etkiliyorsa, ilgili uyarılar, araştırmalar ve bunların verileri de aynı olayla ilişkilendirilir.

  <sup>\*</sup>Uç Nokta için Microsoft Defender, Kimlik için Microsoft Defender ve Microsoft Defender for Cloud Apps.

- Mantık sistem tarafından sağlandığından karmaşık bağıntı mantığı gerekli değildir.

- Bağıntı mantığı gereksinimlerinizi tam olarak karşılamıyorsa, mevcut olaylara uyarılar ekleyebilir veya yeni olaylar oluşturabilirsiniz.

- İlgili Office 365 için Defender uyarıları, AIR araştırmaları ve araştırmalardan bekleyen eylemler olaylara otomatik olarak eklenir.

- AIR araştırması herhangi bir tehdit bulmazsa ilgili uyarılar sistem tarafından otomatik olarak çözümlenir. Bir olay içindeki tüm uyarılar çözümlenirse, olay durumu da **Çözüldü** olarak değişir.

- İlgili kanıt ve yanıt eylemleri, olayın **Kanıt ve yanıt** sekmesinde otomatik olarak toplanır.

- Güvenlik ekibi üyeleri doğrudan olaylardan yanıt eylemleri gerçekleştirebilir. Örneğin, posta kutularındaki e-postaları geçici olarak silebilir veya şüpheli Gelen Kutusu kurallarını posta kutularından kaldırabilirler.

- Önerilen e-posta eylemleri yalnızca kötü amaçlı bir e-postanın en son teslim konumu bir bulut posta kutusu olduğunda oluşturulur.

- Bekleyen e-posta eylemleri en son teslim konumuna göre güncelleştirilir. E-posta el ile gerçekleştirilen bir eylemle zaten düzeltildiyse, durum bunu yansıtır.

- Önerilen eylemler yalnızca en kritik tehditler olarak belirlenen e-posta ve e-posta kümeleri için oluşturulur:
  - Malware
  - Yüksek güvenilirlikli kimlik avı
  - Kötü amaçlı URL'ler
  - Kötü amaçlı dosyalar

> [!NOTE]
> Olaylar yalnızca statik olayları temsil etmez. Ayrıca zaman içinde gerçekleşen saldırı hikayelerini de temsil eder. Saldırı ilerledikçe yeni Office 365 için Defender uyarıları, AIR araştırmaları ve bunların verileri sürekli olarak mevcut olaya eklenir.

Microsoft 365 Defender portalındaki **Olaylar** sayfasındaki olayları yönetme:<https://security.microsoft.com/incidents-queue>

![Microsoft 365 Defender portalındaki Olaylar sayfası.](../../media/mdo-sec-ops-incidents.png)

![Microsoft 365 Defender portalındaki Olaylar sayfasında ayrıntılar açılır öğesi.](../../media/mdo-sec-ops-incident-details.png)

![Microsoft 365 Defender portalındaki Olaylar sayfasında açılır öğeyi filtreleyin.](../../media/mdo-sec-ops-incident-filters.png)

![Microsoft 365 Defender portalındaki olay ayrıntılarının özet sekmesi.](../../media/mdo-sec-ops-incident-summary-tab.png)

![Microsoft 365 Defender portalındaki olay ayrıntılarının kanıt ve uyarılar sekmesi.](../../media/mdo-sec-ops-incident-evidence-and-response-tab.png)

Microsoft Sentinel'de **Olaylar** sayfasındaki olayları şu konumda <https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/microsoft.securityinsightsarg%2Fsentinel>yönetin:

![Microsoft Sentinel'deki Olaylar sayfası.](../../media/mdo-sec-ops-microsoft-sentinel-incidents.png)

![Microsoft Sentinel'de olay ayrıntıları sayfası.](../../media/mdo-sec-ops-microsoft-sentinel-incident-details.png)

## <a name="response-actions-to-take"></a>Yapılması gereken yanıt eylemleri

Güvenlik ekipleri, Office 365 için Defender araçlarını kullanarak e-posta üzerinde çok çeşitli yanıt eylemleri gerçekleştirebilir:

- İletileri silebilirsiniz, ancak e-postada aşağıdaki eylemleri de gerçekleştirebilirsiniz:
  - Gelen Kutusuna Taşı
  - Gereksiz Öğeye Taşı
  - Silinmiş Öğelere Taşı
  - Geçici silme
  - Sabit silme.

  Aşağıdaki konumlardan bu eylemleri gerçekleştirebilirsiniz:

  - **Olaylar** sayfasındaki** <https://security.microsoft.com/incidents-queue> (önerilen) olayın ayrıntılarındaki **Kanıt ve yanıt** sekmesi.
  - **Tehdit Gezgini** konumunda <https://security.microsoft.com/threatexplorer>.
  - konumundaki <https://security.microsoft.com/action-center/pending>birleşik **İşlem merkezi**.

- Bir AIR playbook'unu, Tehdit Gezgini'ndeki **Araştırmayı tetikle** eylemini kullanarak herhangi bir e-posta iletisinde el ile başlatabilirsiniz.

- [Tehdit Gezgini'ni](threat-explorer.md) veya [yönetici gönderimlerini](admin-submission.md) kullanarak hatalı pozitif veya hatalı negatif algılamaları doğrudan Microsoft'a bildirebilirsiniz.

- Algılanmayan kötü amaçlı dosyaları, URL'leri veya gönderenleri [Kiracı İzin Ver/Engelle Listesi'ni kullanarak engelleyebilirsiniz](manage-tenant-allow-block-list.md).

Office 365 için Defender eylemler avcılık deneyimleriyle sorunsuz bir şekilde tümleştirilir ve eylemlerin geçmişi, konumundaki <https://security.microsoft.com/action-center/history>birleşik **İşlem merkezindeki** **Geçmiş** sekmesinde görünür.

Eylem gerçekleştirmenin en etkili yolu, yerleşik tümleştirmeyi Microsoft 365 Defender'daki Olaylar ile kullanmaktır. AIR tarafından önerilen eylemleri, Microsoft 365 Defender'daki bir Olayın [Kanıt ve yanıt](/microsoft-365/security/defender/investigate-incidents#evidence-and-response) sekmesindeki Office 365 için Defender onaylayabilirsiniz. Bu eylem gerçekleştirme yöntemi aşağıdaki nedenlerle önerilir:

- Saldırı hikayesinin tamamını araştırırsınız.
- Diğer iş yükleriyle yerleşik bağıntıdan yararlanabilirsiniz: Uç Nokta için Microsoft Defender, Kimlik için Microsoft Defender ve Microsoft Defender for Cloud Apps.
- E-posta üzerinde tek bir yerden işlem gerçekleştirirsiniz.

El ile yapılan araştırma veya avcılık etkinliğinin sonucuna bağlı olarak e-posta üzerinde işlem gerçekleştirirsiniz. [Tehdit Gezgini](threat-explorer.md) , güvenlik ekibi üyelerinin bulut posta kutularında hala var olabilecek tüm e-posta iletileri üzerinde eylem gerçekleştirmesine olanak tanır. Kuruluşunuzdaki kullanıcılar arasında gönderilen kuruluş içi iletilerde işlem yapabilir. Tehdit Gezgini verileri son 30 gün boyunca kullanılabilir.

Microsoft 365 Defender Office 365 için Defender gibi çeşitli algılama kaynaklarından gelen uyarıları olaylar halinde nasıl bir araya getireceğinizi öğrenmek için bu kısa videoyu izleyin. 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGpcs]
