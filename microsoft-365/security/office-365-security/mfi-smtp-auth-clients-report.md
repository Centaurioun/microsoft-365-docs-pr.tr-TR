---
title: Posta akışı panosunda SMTP Kimlik Doğrulaması istemcileri içgörüleri ve raporu
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, kuruluşlarında e-posta iletileri göndermek için kimliği doğrulanmış SMTP (SMTP AUTH) kullanan e-posta gönderenleri izlemek için Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosunda SMTP Kimlik Doğrulaması içgörülerini ve raporunu kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 7fdd41d0a6c8d0104c524b577ea754ec915f321c
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597359"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Güvenlik & Uyumluluk Merkezi'nde SMTP Kimlik Doğrulaması istemcileri içgörüleri ve raporu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Posta akışı panosundaki](mail-flow-insights-v2.md) **SMTP Kimlik Doğrulama istemcileri** içgörüleri ve [Güvenlik & Uyumluluk Merkezi'ndeki](https://protection.office.com) ilişkili [SMTP Kimlik Doğrulama istemcileri raporu](#smtp-auth-clients-report), kuruluşunuzdaki kullanıcılar veya sistem hesapları tarafından SMTP AUTH istemci gönderim protokolünün kullanımını vurgular. Bu eski protokol (uç nokta smtp.office365.com kullanan) yalnızca Temel kimlik doğrulaması sunar ve güvenliği aşılmış hesaplar tarafından e-posta göndermek için kullanılmaya duyarlıdır. İçgörü ve rapor, SMTP AUTH e-posta gönderimleri için olağan dışı etkinlik olup olmadığını denetlemenize olanak sağlar. Ayrıca SMTP AUTH kullanan istemciler veya cihazlar için TLS kullanım verilerini de gösterir.

Pencere öğesi, son 7 gün içinde SMTP Kimlik Doğrulaması protokolünün kullanıldığı kullanıcı veya hizmet hesaplarının sayısını gösterir.

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-widget.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı panosundaki SMTP Kimlik Doğrulama istemcileri pencere öğesi" lightbox="../../media/mfi-smtp-auth-clients-report-widget.png":::

Pencere öğesindeki ileti sayısına tıklarsanız **, SMTP Kimlik Doğrulama istemcileri** açılır öğesi görüntülenir. Açılır öğe, geçen haftanın TLS kullanımına ve birimlerine ilişkin toplu bir görünüm sağlar.

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-details.png" alt-text="Posta akışı panosundaki SMTP Kimlik Doğrulama istemcileri pencere öğesine tıkladıktan sonra Ayrıntılar açılır öğesi" lightbox="../../media/mfi-smtp-auth-clients-report-details.png":::

SONRAKI bölümde açıklandığı gibi **SMTP Kimlik Doğrulama istemcileri raporuna** gitmek için SMTP Kimlik Doğrulama istemcileri rapor bağlantısına tıklayabilirsiniz.

## <a name="smtp-auth-clients-report"></a>SMTP Kimlik Doğrulama istemcileri raporu

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP Kimlik Doğrulama istemcileri raporu için rapor görünümü

Varsayılan olarak, rapor son 7 güne ilişkin verileri gösterir, ancak son 90 güne ilişkin veriler kullanılabilir.

Genel bakış bölümü aşağıdaki grafikleri içerir:

- **Verileri görüntüleme ölçütü: Birim gönderme**: Grafik varsayılan olarak, tüm etki alanlarından gönderilen SMTP Kimlik Doğrulama istemci iletilerinin sayısını gösterir (**Verileri göster: Tüm gönderen etki alanları** varsayılan olarak seçilidir). Verileri **göster'e** tıklayıp açılan listeden gönderen etki alanını seçerek sonuçları belirli bir gönderen etki alanına göre filtreleyebilirsiniz. Belirli bir veri noktasının (gün) üzerine geldiğinizde ileti sayısı gösterilir.

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki SMTP Kimlik Doğrulama istemcileri raporundaki Gönderme birimi görünümü" lightbox="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png":::

- **Verileri görüntüleme ölçütü: TLS Kullanımı**: Grafik, seçilen zaman aralığındaki tüm SMTP Kimlik Doğrulama istemci iletileri için TLS kullanım yüzdesini gösterir. Bu grafik, TLS'nin eski sürümlerini kullanmaya devam eden kullanıcıları ve sistem hesaplarını tanımlamanıza ve üzerinde işlem yapmanıza olanak tanır.

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png" alt-text="Güvenlik & Uyumluluk Merkezi'ndeki SMTP Kimlik Doğrulaması istemcileri raporundaki TLS kullanım görünümü" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png":::

Rapor görünümünde **Filtreler'e** tıklarsanız **Başlangıç tarihi** ve **Bitiş tarihi** içeren bir tarih aralığı belirtebilirsiniz.

**Raporun** daha ayrıntılı bir sürümünü e-posta iletisinde almak için Rapor iste'ye tıklayın. Raporu alacak tarih aralığını ve alıcıları belirtebilirsiniz.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP Kimlik Doğrulama istemcileri raporu için ayrıntılar tablosu görünümü

**Ayrıntılar tablosunu görüntüle'ye** tıklarsanız, gösterilen bilgiler baktığınız grafiğe bağlıdır:

- **Verileri görüntüleme ölçütü: Birim gönderme**: Tabloda aşağıdaki bilgiler gösterilir:

  - **Gönderen adresi**
  - **İleti sayısı**

  Bir satır seçerseniz, açılır pencerede aynı ayrıntılar gösterilir.

- **Verileri görüntüleme ölçütü: TLS Kullanımı**: Tabloda aşağıdaki bilgiler gösterilir:

  - **Gönderen adresi**
  - **TLS1,0%**<sup>\*</sup>
  - **TLS1,1%**<sup>\*</sup>
  - **TLS1,2%**<sup>\*</sup>
  - **İleti sayısı**

  <sup>\*</sup> Bu sütun, gönderenden gelen iletilerin yüzdesini ve sayısını gösterir.

Ayrıntılar tablosu görünümünde **Filtreler'e** tıklarsanız, **Başlangıç tarihi** ve **Bitiş tarihi** ile bir tarih aralığı belirtebilirsiniz.

Bir satır seçerseniz, açılır pencerede benzer ayrıntılar gösterilir:

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png" alt-text="SMTP Kimlik Doğrulama istemcileri raporundaki TLS kullanım görünümünün ayrıntılar tablosundaki Ayrıntılar açılır öğesi" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png":::

**Raporun** daha ayrıntılı bir sürümünü e-posta iletisinde almak için Rapor iste'ye tıklayın. Raporu alacak tarih aralığını ve alıcıları belirtebilirsiniz.

Raporlar görünümüne dönmek için **Raporu görüntüle'ye** tıklayın.

## <a name="related-topics"></a>İlgili konular

Posta akışı panosundaki diğer içgörüler hakkında bilgi için [Bkz. Güvenlik & Uyumluluk Merkezi'ndeki Posta akışı içgörüleri](mail-flow-insights-v2.md).
