---
title: Office 365 için Microsoft Defender'da tehdit araştırması & yanıt özellikleri
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Office 365 için Microsoft Defender Planı'nda tehdit araştırması ve yanıt özellikleri hakkında bilgi edinin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ed5c9fe16201a2cc82fb6a6869018145da9a1024
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060504"
---
# <a name="threat-investigation-and-response"></a>Tehdit araştırması ve yanıtı

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunun için geçerlidir:**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)

[Office 365 için Microsoft Defender'deki](defender-for-office-365.md) tehdit araştırma ve yanıt özellikleri, güvenlik analistlerinin ve yöneticilerin kuruluşlarının Microsoft 365 İş kullanıcılarını şu şekilde korumasına yardımcı olur:

- Siber saldırıları tanımlamayı, izlemeyi ve anlamayı kolaylaştırma.
- Exchange Online, SharePoint Online, OneDrive İş ve Microsoft Teams'deki tehditlerin hızla ele alınmasına yardımcı olur.
- Güvenlik operasyonlarının kuruluşlarında siber saldırıları önlemesine yardımcı olmak için içgörüler ve bilgiler sağlama.
- E-posta tabanlı kritik tehditler için [Office 365 otomatik araştırma ve yanıt](automated-investigation-response-office.md) kullanma.

Tehdit araştırması ve yanıt özellikleri, Microsoft 365 Defender portalında kullanılabilen tehditler ve ilgili yanıt eylemleri hakkında içgörüler sağlar. Bu içgörüler, kuruluşunuzun güvenlik ekibinin kullanıcıları e-posta veya dosya tabanlı saldırılara karşı korumasına yardımcı olabilir. Bu özellikler sinyalleri izlemeye ve kullanıcı etkinliği, kimlik doğrulaması, e-posta, güvenliği aşılmış bilgisayarlar ve güvenlik olayları gibi birden çok kaynaktan veri toplamaya yardımcı olur. İş karar alıcıları ve güvenlik operasyonları ekibiniz, kuruluşunuza yönelik tehditleri anlamak ve yanıtlamak ve fikri mülkiyetinizi korumak için bu bilgileri kullanabilir.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Tehdit araştırması ve yanıt araçlarıyla tanışın

Microsoft 365 Defender portalındaki <https://security.microsoft.com> tehdit araştırması ve yanıt özellikleri şunlardır:

- [Explorer](#explorer)
- [Olaylar](#incidents)
- [Saldırı simülasyonu eğitimi](attack-simulation-training.md)
- [Otomatik araştırma ve yanıt](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorer

[Explorer'ı (ve gerçek zamanlı algılamaları) kullanarak tehditleri](threat-explorer.md) analiz edin, zaman içindeki saldırı hacmini görün ve verileri tehdit ailelerine, saldırgan altyapısına ve daha fazlasına göre analiz edin. Explorer (Tehdit Gezgini olarak da adlandırılır), güvenlik analistlerinin araştırma iş akışının başlangıç noktasıdır.

:::image type="content" source="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png" alt-text="Tehdit gezgini sayfası" lightbox="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png":::

Bu raporu konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>görüntülemek ve kullanmak için **Email & işbirliği** \> **Gezgini'ne** gidin. Veya doğrudan **Gezgin** sayfasına gitmek için kullanın <https://security.microsoft.com/threatexplorer>.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Tehdit Bilgileri bağlantısı

Bu özellik yalnızca etkin bir Office 365 E5 aboneliğiniz veya Tehdit Bilgileri eklentisi varsa kullanılabilir. Daha fazla bilgi için Office 365 Kurumsal E5 ürün sayfasına bakın.

Bu özelliği açtığınızda, Office 365 posta kutuları ve Windows cihazları arasında kapsamlı bir güvenlik araştırması yürütmek için Office 365 için Microsoft Defender verileri Microsoft 365 Defender birleştirebileceksiniz.

> [!NOTE]
> Bu özelliği etkinleştirmek için uygun lisansa sahip olmanız gerekir.

Office 365 Tehdit Bilgileri'nde bağlamsal cihaz tümleştirmesi almak için Güvenlik & Uyumluluğu panosunda Uç Nokta için Defender ayarlarını etkinleştirmeniz gerekir.

### <a name="incidents"></a>Olaylar

Uçuş güvenlik olaylarının listesini görmek için Olaylar listesini (buna Araştırma olarak da adlandırılır) kullanın. Olaylar, şüpheli e-posta iletileri gibi tehditleri izlemek ve daha fazla araştırma ve düzeltme gerçekleştirmek için kullanılır.

:::image type="content" source="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png" alt-text="Office 365'deki geçerli Tehdit Olaylarının listesi" lightbox="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png":::

konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>kuruluşunuzun geçerli olaylarının listesini görüntülemek için **Olaylar & uyarılar** \> **Olaylar'a** gidin. Ya da doğrudan **Olaylar** sayfasına gitmek için kullanın <https://security.microsoft.com/incidents>.


### <a name="attack-simulation-training"></a>Saldırı simülasyonu eğitimi

Kuruluşunuzda gerçekçi siber saldırılar ayarlamak ve çalıştırmak için Saldırı simülasyonu eğitimi kullanın ve gerçek bir siber saldırı işinizi etkilemeden önce savunmasız kişileri belirleyin. Daha fazla bilgi için bkz. [Kimlik avı saldırısı simülasyonu](attack-simulation-training.md).

Bu özelliği adresinden <https://security.microsoft.com>Microsoft 365 Defender portalında görüntülemek ve kullanmak için **Email & işbirliği** >  **Saldırı simülasyonu eğitimi** gidin. Veya doğrudan **Saldırı simülasyonu eğitimi** sayfasına gitmek için kullanın<https://security.microsoft.com/attacksimulator?viewid=overview>.

### <a name="automated-investigation-and-response"></a>Otomatik araştırma ve yanıt

Kuruluşunuzdaki tehditlere karşı risk altındaki içerik, cihaz ve kişilerle bağıntılı zaman ve çabadan tasarruf etmek için otomatik araştırma ve yanıt (AIR) özelliklerini kullanın. AIR işlemleri, belirli uyarılar tetiklendiğinde veya güvenlik operasyonları ekibiniz tarafından başlatıldığında başlayabilir. Daha fazla bilgi edinmek için bkz. [Office 365'de otomatik araştırma ve yanıt](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Tehdit bilgileri pencere öğeleri

Office 365 için Microsoft Defender Plan 2 teklifinin bir parçası olarak güvenlik analistleri bilinen bir tehditle ilgili ayrıntıları gözden geçirebilir. Bu, kullanıcıların güvenliğini sağlamak için ek önleyici önlemler/adımlar olup olmadığını belirlemek için yararlıdır.

:::image type="content" source="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png" alt-text="Son tehditlerle ilgili bilgileri gösteren Güvenlik eğilimleri bölmesi" lightbox="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png":::

## <a name="how-do-we-get-these-capabilities"></a>Bu özellikleri nasıl alacağız?

Microsoft 365 tehdit araştırması ve yanıt özellikleri, Kurumsal E5'e veya belirli aboneliklere eklenti olarak dahil edilen Office 365 için Microsoft Defender Plan 2'ye dahildir. Daha fazla bilgi edinmek için bkz. [Plan 1 ve Plan 2 Office 365 için Defender](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Gerekli roller ve izinler

Office 365 için Microsoft Defender rol tabanlı erişim denetimini kullanır. İzinler Azure Active Directory, Microsoft 365 yönetim merkezi veya Microsoft 365 Defender portalındaki belirli roller aracılığıyla atanır.

> [!TIP]
> Güvenlik Yöneticisi gibi bazı roller Microsoft 365 Defender portalında atanabilir ancak bunun yerine Microsoft 365 yönetim merkezi veya Azure Active Directory'yi kullanmayı göz önünde bulundurun. Roller, rol grupları ve izinler hakkında bilgi için aşağıdaki kaynaklara bakın:
>
> - [Microsoft 365 Defender portalındaki izinler](permissions-microsoft-365-security-center.md)
> - [Yerleşik rolleri Azure AD](/azure/active-directory/roles/permissions-reference)

|Etkinlik|Roller ve izinler|
|---|---|
|Microsoft Defender Güvenlik Açığı Yönetimi panosunu kullanma <p> Son tehditler veya geçerli tehditler hakkındaki bilgileri görüntüleme|Aşağıdakilerden biri: <ul><li>**Genel Yönetici**</li><li>**Güvenlik Yöneticisi**</li><li>**Güvenlik Okuyucusu**</li></ul> <p> Bu roller Azure Active Directory'de (<https://portal.azure.com>) veya Microsoft 365 yönetim merkezi (<https://admin.microsoft.com> ) atanabilir.|
|Tehditleri analiz etmek için [Explorer'ı (ve gerçek zamanlı algılamaları)](threat-explorer.md) kullanma|Aşağıdakilerden biri: <ul><li>**Genel Yönetici**</li><li>**Güvenlik Yöneticisi**</li><li>**Güvenlik Okuyucusu**</li></ul> <p> Bu roller Azure Active Directory'de (<https://portal.azure.com>) veya Microsoft 365 yönetim merkezi (<https://admin.microsoft.com> ) atanabilir.|
|Olayları Görüntüle (Araştırma olarak da adlandırılır) <p> Olaya e-posta iletileri ekleme|Aşağıdakilerden biri: <ul><li>**Genel Yönetici**</li><li>**Güvenlik Yöneticisi**</li><li>**Güvenlik Okuyucusu**</li></ul> <p> Bu roller Azure Active Directory'de (<https://portal.azure.com>) veya Microsoft 365 yönetim merkezi (<https://admin.microsoft.com> ) atanabilir.|
|Bir olayda e-posta eylemlerini tetikleme <p> Şüpheli e-posta iletilerini bulma ve silme|Aşağıdakilerden biri: <ul><li>**Genel Yönetici**</li><li>**Güvenlik Yöneticisi** ve **Arama ve Temizleme** rolü</li></ul> <p> **Genel Yönetici** ve **Güvenlik Yöneticisi** rolleri Azure Active Directory'de (<https://portal.azure.com>) veya Microsoft 365 yönetim merkezi (<https://admin.microsoft.com> ) atanabilir. <p> **Arama ve Temizleme** rolü, Microsoft 36 Defender portalındaki (<https://security.microsoft.com> ) **Email & işbirliği rollerine** atanmalıdır.|
|Office 365 için Microsoft Defender Plan 2'yi Uç Nokta için Microsoft Defender ile tümleştirme <p> Office 365 için Microsoft Defender Plan 2'yi SIEM sunucusuyla tümleştirme|Azure Active Directory'de (<https://portal.azure.com>) veya Microsoft 365 yönetim merkezi(<https://admin.microsoft.com> içinde atanan **Genel Yönetici** veya **Güvenlik Yöneticisi** rolü. <p> --- **Artı** --- <p> Ek uygulamalarda ([Microsoft Defender Güvenlik Merkezi](/windows/security/threat-protection/microsoft-defender-atp/user-roles) veya SIEM sunucunuz gibi) atanmış uygun bir rol.|

## <a name="next-steps"></a>Sonraki adımlar

- [Tehdit İzleyicileri hakkında bilgi edinin - Yeni ve Dikkat Çekici](threat-trackers.md)
- [Teslim edilen kötü amaçlı e-postaları bulma ve araştırma (Tehdit Araştırması ve Yanıtı Office 365)](investigate-malicious-email-that-was-delivered.md)
- [Office 365 Tehdit Araştırmasını ve Yanıtlarını Uç Nokta için Microsoft Defender ile Tümleştirme](integrate-office-365-ti-with-mde.md)
- [Kimlik avı saldırısı simülasyonu](attack-simulation-training.md)
