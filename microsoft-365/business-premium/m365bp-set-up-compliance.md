---
title: Uyumluluk özelliklerini ayarlama
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Veri kaybını önlemek ve sizin ve müşterilerinizin hassas bilgilerini güvende tutmaya yardımcı olmak için uyumluluk özelliklerini ayarlayın.
ms.openlocfilehash: db1993a99292f9b90a3b567007b96742b0f359b2
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66862192"
---
# <a name="set-up-compliance-features"></a>Uyumluluk özelliklerini ayarlama


YouTube'da [Microsoft 365 küçük işletme yardımına](https://go.microsoft.com/fwlink/?linkid=2197659) göz atın.

Microsoft 365 İş Ekstra aboneliğiniz uyumluluk ve gizlilik özelliklerini içerir. Bu özellikler şirketinizin verilerinin korunmasına ve sizin ve müşterilerinizin hassas bilgilerinin güvenliğinin korunmasına yardımcı olur. Bu makale, uyumluluk özelliklerinizi kullanmaya başlamanıza yardımcı olmak için tasarlanmıştır.


## <a name="before-you-begin"></a>Başlamadan önce

Azure Active Directory'de aşağıdaki rollerden birine atanmış olduğunuzdan emin olun:

- Genel Yönetici
- Uyumluluk Yöneticisi

Daha fazla bilgi edinmek için bkz. [Roller sayfasını kullanmaya başlama](../admin/add-users/admin-roles-page.md).

## <a name="use-compliance-manager-to-get-started"></a>Başlamak için Uyumluluk Yöneticisi'ni kullanma

:::image type="content" source="./media/m365bp-compliancemanager.png" alt-text="Microsoft 365 İş Ekstra'de Uyumluluk Yöneticisi'nin ekran görüntüsü.":::

Microsoft 365 İş Ekstra uyumluluk özelliklerinizi ayarlamaya başlamanıza yardımcı olabilecek Uyumluluk Yöneticisi'ni içerir. Bu tür özellikler arasında veri kaybı önleme, veri yaşam döngüsü yönetimi ve içeriden risk yönetimi yer alır. Uyumluluk Yöneticisi önerileri, uyumluluk puanı ve puanınızı geliştirmenin yollarını vurgulayarak size zaman kazandırabilir.

Şu şekilde çalışmaya başlarsınız:

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) adresine gidin ve oturum açın.

2. Gezinti bölmesinde **Uyumluluk Yöneticisi'ni** seçin.

3. **Genel Bakış** sekmesinde bilgileri gözden geçirin. Daha fazla bilgi görüntülemek veya veri kaybı önleme (DLP) ilkesi yapılandırma gibi eylemler yapmak için bir öğe veya bağlantı seçin. Örneğin, **Puanınızı etkileyen çözümler** bölümünde **Kalan eylemler** sütunundaki bağlantıyı seçebilirsiniz.

   :::image type="content" source="./media/m365bp-compliancesolutions.png" alt-text="Puanınızı Etkileyen Çözümlerin ekran görüntüsü.":::

   Bu eylem sizi seçtiğiniz öğe için filtrelenen **İyileştirme eylemleri** sekmesine götürür. Bu örnekte yapılandırılan DLP ilkelerine bakıyoruz.

   :::image type="content" source="./media/m365bp-dlppoliciestoconfigure.png" alt-text="Yapılandırılan DLP ilkelerinin ekran görüntüsü.":::

4. **İyileştirme eylemleri** sekmesinde bir öğe seçin. Örneğimizde **Özelleştirilmiş DLP ilkeleri veya kişisel bilgiler oluştur'u seçtik**. Yapılandırılan ilke hakkında daha fazla bilgi sağlayan bir sayfa yüklenir.

   :::image type="content" source="./media/m365bp-dlppolicyinfo.png" alt-text="Müşteri içeriği için DLP ilkesi hakkındaki bilgilerin ekran görüntüsü.":::

   DLP ilkenizi ayarlamak için ekrandaki bilgileri izleyin.

İş için Microsoft 365'teki uyumluluk özellikleri hakkında daha fazla bilgi için [Microsoft Purview belgelerine bakın](../compliance/index.yml).

## <a name="use-sensitivity-labels"></a>Duyarlılık etiketlerini kullanma

[YouTube kanalımızda](https://go.microsoft.com/fwlink/?linkid=2198022) bu videoya ve diğer videolara göz atın.

Duyarlılık etiketleri Office uygulamalarında (Outlook, Word, Excel ve PowerPoint gibi) kullanılabilir. Etiketlere örnek olarak şunlar verilebilir:

- Normal
- Personal
- Özel
- Gizli

Ancak, şirketiniz için başka etiketler de tanımlayabilirsiniz.

Duyarlılık etiketlerini kullanmaya başlamak için aşağıdaki makaleleri kullanın:

1. [Duyarlılık etiketleri hakkında bilgi edinin](../compliance/sensitivity-labels.md).

2. [Duyarlılık etiketlerini kullanmaya başlayın](../compliance/get-started-with-sensitivity-labels.md).

3. [Duyarlılık etiketlerini ve bunların ilkelerini oluşturun ve yapılandırın](../compliance/create-sensitivity-labels.md).

4. [Şirketinizdeki kişilere duyarlılık etiketlerini nasıl kullanacaklarını gösterme](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)