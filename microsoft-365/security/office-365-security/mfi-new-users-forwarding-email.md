---
title: E-posta içgörüsü ileten yeni kullanıcılar
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: Yöneticiler, güvenlik & Uyumluluk Merkezi'nde e-posta iletmeye yönelik Yeni kullanıcılar içgörülerini kullanarak kuruluşlarındaki kullanıcıların iletileri yeni etki alanlarına ne zaman ilettiğini araştırabilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: 7cade67d1fc4ae6e408fc3be3ca95a3acba84a76
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086761"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde e-posta içgörülerini ileten yeni kullanıcılar

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Kuruluşunuzdaki yeni kullanıcı hesapları aniden e-posta iletilerini dış etki alanlarına iletmeye başladığında şüphelidir.

[Güvenlik & Uyumluluk Merkezi'nde](https://protection.office.com) e-posta içgörülerini **ileden Yeni kullanıcılar**, kuruluşunuzda yeni oluşturulan kullanıcılar iletileri dış etki alanlarına ilettiğinde size bildirir. Bu koşul, yeni kullanıcıları oluşturmak için güvenliği aşılmış yönetici hesaplarının kullanıldığını gösterebilir. Hesapların gizliliğinin ihlal edildiğini düşünüyorsanız, bkz. [Güvenliği aşılmış bir e-posta hesabını yanıtlama](responding-to-a-compromised-email-account.md).

Bu içgörü yalnızca sorun algılandığında ve [İletme raporu](view-mail-flow-reports.md#forwarding-report) sayfasında görüntülenir.

:::image type="content" source="../../media/mfi-new-users-forwarding-email.png" alt-text="E-posta iletme içgörüleri yeni kullanıcılar" lightbox="../../media/mfi-new-users-forwarding-email.png":::

Pencere öğesine tıkladığınızda, bu makalenin devamında açıklandığı gibi İletme [değişiklikleri raporunun](#forwarding-modifications-report) bağlantısı da dahil olmak üzere iletilen iletiler hakkında daha fazla ayrıntı bulabileceğiniz bir açılır pencere açılır öğesi görüntülenir.

:::image type="content" source="../../media/mfi-new-users-forwarding-email-details.png" alt-text="Yeni kullanıcılar e-posta iletme içgörülerine tıkladıktan sonra görüntülenen Ayrıntılar açılır öğesi" lightbox="../../media/mfi-new-users-forwarding-email-details.png":::

Ayrıca, (**Raporlar** \> **Panosu** veya <https://protection.office.com/insightdashboard>) üzerindeki **En iyi içgörüler & öneriler** alanında **Tümünü görüntüle'ye** tıkladıktan sonra içgörüleri seçtiğinizde de bu ayrıntılar sayfasına ulaşabilirsiniz.

Sonraki bölümde açıklandığı gibi **İletme değişiklikleri raporuna** gitmek için **İçgörüyle ilişkili raporu gör** bağlantısına tıklayabilirsiniz.

## <a name="forwarding-modifications-report"></a>Değişiklik raporunu iletme

**İletme değişiklikleri raporu**, kuruluşunuzdaki gönderenlerden otomatik olarak iletilen iletiler hakkındaki ayrıntıları gösterir:

- İletileri dış etki alanlarına ileden yeni oluşturulan hesaplar.
- Kuruluşunuzdaki diğer gönderenler tarafından hiç iletilmeyen dış etki alanlarına ileti gönderen hesaplar.

bu tür iletilen iletiler güvenlik veya uyumluluk riski oluşturabilir ve güvenliği aşılmış hesapları gösterebilir.

Rapor 90 güne kadar veri içerir. Varsayılan olarak, rapor son 7 güne ilişkin verileri gösterir.

Bu rapor [, Posta akışı panosunda](mail-flow-insights-v2.md) veya [Raporlar](view-mail-flow-reports.md) panosunda doğrudan kullanılamaz. **Yeni kullanıcılar e-posta** **içgörülerini ileterken içindeki İçgörülerle ilişkili raporu gör** bağlantısına tıklamanın yanı sıra, rapora şu şekilde ulaşabilirsiniz:

- [İletilen Yeni etki alanları e-posta içgörüsünün](mfi-new-domains-being-forwarded-email.md) ayrıntılarında **İletme bildirimleri raporu** bağlantısına tıklayın.
- açılıyor <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.

### <a name="report-view-for-the-forwarding-modifications-report"></a>İletme değişiklikleri raporu için rapor görünümü

Aşağıdaki grafikler rapor görünümünde kullanılabilir:

- **Verileri göster: Yeni iletilen kullanıcılar**:

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarding-users.png" alt-text="İletme değişiklikleri raporunda Yeni iletme kullanıcıları görünümü" lightbox="../../media/forwarding-modifications-report-new-forwarding-users.png":::

- **Şu veriler için verileri göster: Yeni iletme etki alanları**:

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarded-domains.png" alt-text="İletme değişiklikleri raporundaki Yeni iletilen etki alanları görünümü" lightbox="../../media/forwarding-modifications-report-new-forwarded-domains.png":::

Rapor görünümünde **Filtreler'e** tıklarsanız **Başlangıç tarihi** ve **Bitiş tarihi** içeren bir tarih aralığı belirtebilirsiniz.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>İletme değişiklikleri raporu için ayrıntılar tablosu görünümü

**Ayrıntılar tablosunu görüntüle'ye** tıklarsanız, gösterilen bilgiler baktığınız grafiğe bağlıdır:

- **Verileri göster: Yeni iletilen kullanıcılar**:

  - **Ad**: Gönderenin e-posta adresi.
  - **İletme türü**
  - **Alıcı adresi**
  - **Ayrıntılar**
  - **Sayısı**
  - **İlk iletme tarihi**

- **Şu veriler için verileri göster: Yeni iletme etki alanları**:

  - **Ad**: Gönderenin e-posta etki alanı.
  - **İletme türü**
  - **Alıcı adresi**
  - **Ayrıntılar**
  - **Sayısı**
  - **İlk iletme tarihi**

Ayrıntılar tablosu görünümünde **Filtreler'e** tıklarsanız, **Başlangıç tarihi** ve **Bitiş tarihi** ile bir tarih aralığı belirtebilirsiniz.

Tablodan bir satır seçerseniz, aşağıdaki bilgileri içeren bir **Ayrıntılar** açılır öğesi görüntülenir:

- **Ad**: Bu, gönderenin e-posta adresidir ( **Verileri göster: Yeni iletme kullanıcıları** görünümünden) veya gönderenin e-posta etki alanıdır ( **Verileri göster: Yeni iletme etki alanları** görünümünde).
- **İletme türü**
- **Alıcı**
- **Ayrıntılar**
- **Sayısı**
- **Başlangıç tarihi**
- **Öneri**: Buradan, Microsoft 365 yönetim merkezi kullanıcıyı yönetmek için bağlantıya tıklayabilirsiniz.

  :::image type="content" source="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png" alt-text="İletme değişiklikleri raporundaki Yeni iletme kullanıcıları görünümünün ayrıntılar tablosundaki Ayrıntılar açılır öğesi" lightbox="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png":::

Raporlar görünümüne dönmek için **Raporu görüntüle'ye** tıklayın.

## <a name="related-topics"></a>İlgili konular

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
