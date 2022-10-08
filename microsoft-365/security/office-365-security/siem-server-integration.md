---
title: Microsoft 365 hizmetleri ve uygulamalarıyla SIEM sunucusu tümleştirmesi
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.localizationpriority: medium
ms.collection:
- m365-security
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 bulut hizmetleriniz ve uygulamalarınızla Güvenlik Bilgileri ve Olay Yönetimi (SIEM) sunucusu tümleştirmesine genel bakış edinin
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 172cf340817b5afc212c2f8296e374e99a6125e1
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072293"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 hizmetleri ve uygulamalarıyla Güvenlik Bilgileri ve Olay Yönetimi (SIEM) sunucusu tümleştirmesi

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="summary"></a>Özet

Kuruluşunuz bir Güvenlik Bilgileri ve Olay Yönetimi (SIEM) sunucusu mu kullanıyor veya almayı planlıyor? Microsoft 365 veya Office 365 ile nasıl tümleştirilebileceğini merak ediyor olabilirsiniz. Bu makalede, SIEM sunucunuzu Microsoft 365 hizmetleri ve uygulamalarıyla tümleştirmek için kullanabileceğiniz kaynakların listesi sağlanır.

> [!TIP]
> Henüz bir SIEM sunucunuz yoksa ve seçeneklerinizi araştırıyorsanız **[Microsoft Sentinel'i](/azure/sentinel/overview)** göz önünde bulundurun.

## <a name="do-i-need-a-siem-server"></a>SIEM sunucusuna ihtiyacım var mı?

SIEM sunucusuna ihtiyacınız olup olmadığı, kuruluşunuzun güvenlik gereksinimleri ve verilerinizin nerede bulunduğu gibi birçok faktöre bağlıdır. Microsoft 365, SIEM sunucusu gibi ek sunucular olmadan birçok kuruluşun güvenlik gereksinimlerini karşılayan çok çeşitli güvenlik özellikleri içerir. Bazı kuruluşlarda SIEM sunucusunun kullanılmasını gerektiren özel durumlar vardır. İşte birkaç örnek:

- *Fabrikam'ın* şirket içinde bazı içeriği ve uygulamaları, bazılarını da bulutta (karma bulut dağıtımı vardır) vardır. Fabrikam, tüm içerik ve uygulamaları genelinde güvenlik raporları almak için bir SIEM sunucusu uygulamıştır.
- *Contoso* , özellikle sıkı güvenlik gereksinimleri olan bir finansal hizmetler kuruluşudur. Ortamlarına ihtiyaç duydukları ek güvenlik korumasından yararlanmak için bir SIEM sunucusu eklediler.

## <a name="siem-server-integration-with-microsoft-365"></a>Microsoft 365 ile SIEM sunucusu tümleştirmesi

SIEM sunucusu çok çeşitli Microsoft 365 hizmet ve uygulamalarından veri alabilir. Aşağıdaki tabloda çeşitli Microsoft 365 hizmetleri ve uygulamalarının yanı sıra daha fazla bilgi edinmek için SIEM sunucu girişleri ve kaynakları listelenmektedir.

<br/><br/>

|Microsoft 365 Hizmeti veya Uygulaması|SIEM sunucu girişleri/yöntemleri|Daha fazla bilgi edinmek için kaynaklar|
|---|---|---|
|[Office 365 için Microsoft Defender](defender-for-office-365.md)|Denetim günlükleri|[Office 365 için Microsoft Defender ile SIEM tümleştirmesi](siem-integration-with-office-365-ti.md)|
|[Uç Nokta için Microsoft Defender](/windows/security/threat-protection/)|Azure'da barındırılan HTTPS uç noktası <p> REST API|[SIEM araçlarınıza uyarı çekme](../defender-endpoint/configure-siem.md)|
|[Bulut Uygulamaları için Microsoft Defender](/cloud-app-security/what-is-cloud-app-security)|Günlük tümleştirmesi|[Microsoft Defender for Cloud Apps ile SIEM tümleştirmesi](/cloud-app-security/siem)|

> [!TIP]
> [Microsoft Sentinel'e](/azure/sentinel/overview) göz atın. Microsoft Sentinel, Microsoft çözümleri için bağlayıcılarla birlikte gelir. Bu bağlayıcılar "kullanıma hazır" kullanılabilir ve gerçek zamanlı tümleştirme sağlar. Microsoft Sentinel'i Office 365, Azure AD, Kimlik için Microsoft Defender gibi Microsoft 365 Defender çözümlerinizle ve Microsoft 365 hizmetleriyle birlikte kullanabilirsiniz. Microsoft Defender for Cloud Apps ve daha fazlası.

### <a name="audit-logging-must-be-turned-on"></a>Denetim günlüğü açık olmalıdır

SIEM sunucu tümleştirmesini yapılandırmadan önce denetim günlüğünün açık olduğundan emin olun.

- SharePoint Online, OneDrive İş ve Azure Active Directory için bkz. [Denetimi açma veya kapatma](../../compliance/turn-audit-log-search-on-or-off.md).
- Exchange Online için bkz. [Posta kutusu denetimini yönetme](../../compliance/enable-mailbox-auditing.md).

## <a name="integration-steps-if-your-siem-is-microsoft-sentinel"></a>SIEM'iniz Microsoft Sentinel ise tümleştirme adımları

Geçerli planınızın Microsoft Sentinel tümleştirmesine izin verdiğinden (örneğin, Office 365 için Microsoft Defender Plan 2 veya üzeri bir planınız olduğundan) ve Office 365 için Microsoft Defender veya Microsoft 365 Defender hesabınızın bir *Güvenlik Yöneticisi*. Son olarak, *Microsoft Sentinel'de Yazma izinlerine sahip olduğunuzdan* emin olun.

1. Microsoft Sentinel'e gidin.
1. Ekranın sol tarafındaki gezinti bölmesinde **Yapılandırma** > **Verileri bağlayıcıları**.
1. Microsoft 365 Defender **arayın** ve **Microsoft 365 Defender (önizleme) bağlayıcısını** seçin.
1. Ekranınızın sağ tarafında **Bağlayıcı Sayfasını Aç'ı** seçin.
1. **Yapılandırma** > altında **Olayları & uyarıları bağla'yı** seçin
    1. Seçili olan ürünler için tüm Microsoft olay oluşturma kurallarını kapatın.
1. Sayfayı kaydırarak sayfanın **Olayları bağlama** bölümünde **Office 365 için Microsoft Defender**.

Son adımı tamamlarken yararlı ve uygulanabilir bulduğunuz *diğer Microsoft Defender ürünlerden* tablo seçebileceğinizi unutmayın (aşağıda).

7. **EmailEvents**, **EmailUrlInfo**, **EmailAttachmentInfo** ve **EmailPostDeliveryEvents** > ve **Değişiklikleri Uygula'yı** seçin.

## <a name="more-resources"></a>Diğer kaynaklar

[Bulut için Microsoft Defender'de güvenlik çözümlerini tümleştirme](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Güvenlik API'si uyarılarını SIEM ile tümleştirme](/graph/security-integration)
