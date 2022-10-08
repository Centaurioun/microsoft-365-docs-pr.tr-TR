---
title: İş için Microsoft Defender ve Microsoft 365 İş Ekstra kullanan Microsoft iş ortakları için kaynaklar
description: Uzaktan izleme ve yönetim (RMM) araçlarınızı ve profesyonel hizmet otomasyonu (PSA) yazılımınızı İş için Defender, Microsoft 365 İş Ekstra, Uç Nokta için Defender ve Microsoft 365 Lighthouse ile tümleştirmeyi öğrenin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 09/28/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.openlocfilehash: e3abcf7ec562a0133dce3716df2fa3c9156ddad1
ms.sourcegitcommit: c550d73b153ad4856188c9109d9d80f02ca989b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68140786"
---
# <a name="resources-for-microsoft-partners-using-microsoft-defender-for-business-and-microsoft-365-business-premium"></a>İş için Microsoft Defender ve Microsoft 365 İş Ekstra kullanan Microsoft iş ortakları için kaynaklar

Küçük ve orta ölçekli işletmeler, başarılarının önemli bir bileşeni olarak güvenliği tanır, ancak genellikle özel bir güvenlik operasyonları ekibine sahip olacak kapasiteye veya uzmanlığa sahip değildir. Müşterilerin genellikle uç noktalarının ve ağlarının güvenliğini yönetme ve uyarıları veya algılanan tehditleri ele alma konusunda yardıma ihtiyacı vardır. Microsoft iş ortakları yardımcı olabilir!

Microsoft iş ortağıysanız ve [İş için Defender](mdb-overview.md), [Microsoft 365 İş Ekstra](../../business-premium/index.md) veya [Uç Nokta için Defender'a](../defender-endpoint/microsoft-defender-endpoint.md) sahip veya ihtiyacı olan müşterilerle çalışıyorsanız, bu makale size yöneliktir.

- [Microsoft uç nokta güvenliğini RMM araçlarınız ve PSA yazılımınızla nasıl tümleştirebileceğinizi öğrenin](#integrate-microsoft-endpoint-security-with-your-rmm-tools-and-psa-software).
- [Müşterilerinizin cihazlarını ve verilerini güvenli ve yönetmek için Microsoft 365 Lighthouse nasıl kullanabileceğinizi görün](#use-microsoft-365-lighthouse-to-secure-and-manage-your-customers-devices-and-data).
- [İş için Defender ve Microsoft 365 İş Ekstra hakkında daha fazla bilgi edinin](#learn-more-about-defender-for-business-and-microsoft-365-business-premium).

## <a name="integrate-microsoft-endpoint-security-with-your-rmm-tools-and-psa-software"></a>Microsoft uç nokta güvenliğini RMM araçlarınız ve PSA yazılımınızla tümleştirme

Microsoft Yönetilen Hizmet Sağlayıcısı (MSP)yseniz, Microsoft uç nokta güvenliğini uzaktan izleme ve yönetim (RMM) araçlarınızla ve profesyonel hizmet otomasyonu (PSA) yazılımınızla tümleştirerek şunları yapabilirsiniz: 

- [Algılanan tehditleri ve olayları ele](mdb-respond-mitigate-threats.md) almak için müşterilerinizin Microsoft 365 Defender portalına erişin.
- Müşterilerinizin kiracılarında yeni uyarılar veya güvenlik açıkları hakkında [e-posta bildirimleri](mdb-email-notifications.md) alın.
- Güvenlik bilgileriniz ve [olay](mdb-view-manage-incidents.md) yönetimi (SIEM) araçlarınızla olayları ve uyarıları getirin ve görüntüleyin.
- Otomatik [araştırmalardan sonraki eylemleri](mdb-review-remediation-actions.md) onaylama veya cihazda el ile yanıt eylemleri gerçekleştirme gibi düzeltme eylemlerini düzenleyin.

Tümleştirme [, Uç Nokta için Defender API'leri](../defender-endpoint/management-apis.md) kullanılarak yapılabilir. Daha fazla bilgi edinmek için aşağıdaki kaynakları kullanın:

| Kaynak | Açıklama |
|:---|:---|
| [Yönetim ve API'lere genel bakış](../defender-endpoint/management-apis.md) | İş için Defender Uç Nokta için Microsoft Defender üzerine kurulmuştur ve tümleştirmeye hazır bir platformdur. Bu makalede, Uç Nokta için Defender API'lerini kullanarak iş akışlarını otomatikleştirme ve yenilik yapmayı açıklar. |
| [Güvenlik hizmeti sağlayıcısı tümleştirmesini yapılandırın](../defender-endpoint/configure-mssp-support.md) | Müşterinin kiracısını MSP çözümünüzle başarıyla tümleştirmek için atılması gereken adımlara genel bir bakış sağlar. |

## <a name="use-microsoft-365-lighthouse-to-secure-and-manage-your-customers-devices-and-data"></a>Müşterilerinizin cihazlarını ve verilerinin güvenliğini sağlamak ve yönetmek için Microsoft 365 Lighthouse kullanma

Microsoft Bulut Çözümü Sağlayıcısı (CSP) veya MSP'yseniz, Microsoft 365 Lighthouse kullanarak müşterilerinizin güvenlik ayarlarını ve özelliklerini yönetmesine yardımcı olabilir, verilerini ve cihazlarını koruyabilirsiniz. Microsoft 365 Lighthouse kullanarak:

- Müşterilerinizin güvenlik ayarlarını ve özelliklerini yönetin. 
- Müşterilerinizin kiracılarında algılanan tehditleri görüntüleyin ve yönetin.
- Müşterilerin cihazlarında virüsten koruma taramaları başlatarak bunları güncel ve korumalı tutun.

| Kaynak | Açıklama |
|:---|:---|
| [Microsoft 365 Lighthouse](../../lighthouse/m365-lighthouse-overview.md) | MSP'lerin ve CSP'lerin küçük ve orta ölçekli işletmeler için cihazları, verileri ve kullanıcıları güvenli bir şekilde yönetmesine ve yönetmesine yardımcı olan bir yönetim portalı olan Microsoft 365 Lighthouse genel bakış sağlar. |
| [Microsoft 365 Lighthouse ve İş için Microsoft Defender](mdb-lighthouse-integration.md) | İş için Defender'ın Microsoft 365 Lighthouse ile nasıl tümleştirilip ek bilgilere bağlantılar içerdiğini açıklar. |

## <a name="learn-more-about-defender-for-business-and-microsoft-365-business-premium"></a>İş için Defender ve Microsoft 365 İş Ekstra hakkında daha fazla bilgi edinin

| Kaynak | Açıklama |
|:---|:---|
| [Microsoft İş Ortağı Ağı](https://partner.microsoft.com) | Microsoft iş ortağı olmayı ve Microsoft İş Ortağı Ağı'na katılmayı öğrenmek için Microsoft İş Ortağı Ağı'nı ziyaret edin. |
| [Microsoft 365 İş Ekstra ve İş için Defender iş ortağı web semineri serisi](https://aka.ms/M365MDBseries) | Bu web semineri serisi şu bilgileri sağlar: <ul><li>Müşterilerinizle güvenlik hakkında konuşmalar yapmak ve Microsoft 365 İş Ekstra yükseltme konusunda pratik rehberlik. </li><li>Microsoft 365 Lighthouse ve İş için Defender için tanıtımlar ve ayrıntılı bakış yönergeleri. </li><li>Sorularınızı yanıtlamanıza yardımcı olacak bir uzman paneli.</li></ul>   |
| [Microsoft 365 İş Ekstra iş ortağı playbook'u ve hazırlık serisi](https://aka.ms/M365BPPartnerPlaybook) |  Aşağıdakilerle kârlı bir yönetilen hizmet uygulaması oluşturmaya yönelik pratik rehberlik: <ul><li>Sektör uzmanlarının ve meslektaşlarının başarılı yönetilen hizmet tekliflerine örnekler. </li><li>Microsoft uzmanlarının teknik etkinleştirme ve denetim listeleri. </li><li>Çözümünüzü pazarlamanıza yardımcı olmak için satış etkinleştirme ve müşteri konuşma yardımcıları. </li></ul> |
| [İş için Defender iş ortağı seti](https://aka.ms/MDBPartnerKit) | İş için Defender iş ortağı seti size pratik rehberlik, teknik bilgiler ve küçük ve orta ölçekli işletmelere İş için Defender'ı pazarlamak ve satmak için müşteriye hazır kaynaklar sağlar.  |

