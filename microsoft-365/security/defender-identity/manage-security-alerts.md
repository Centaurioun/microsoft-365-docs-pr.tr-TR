---
title: Microsoft 365 Defender'da güvenlik uyarılarını Kimlik için Microsoft Defender
description: Microsoft 365 Defender'da Kimlik için Microsoft Defender tarafından verilen güvenlik uyarılarını yönetmeyi ve gözden geçirmeyi öğrenin
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: bc3e383f2d60e115bd0b2bc995e7ade605f48120
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080447"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender'de Kimlik için Defender güvenlik uyarıları

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede, [Microsoft 365 Defender'da Kimlik için Microsoft Defender](/defender-for-identity) güvenlik uyarılarıyla çalışmanın temelleri açıklanmaktadır.[](/microsoft-365/security/defender/overview-security-center)

Kimlik için Defender uyarıları, ayrılmış kimlik uyarısı sayfa biçimiyle <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> yerel olarak tümleştirilir. Bu, Microsoft 365 Defender tam [Kimlik için Microsoft Defender deneyimini tanıtma yolculuğunun ilk adımını](/defender-for-identity/defender-for-identity-in-microsoft-365-defender) gösterir.

Yeni Kimlik uyarısı sayfası, Kimlik için Microsoft Defender müşterilere daha iyi etki alanları arası sinyal zenginleştirmesi ve yeni otomatik kimlik yanıtı özellikleri sağlar. Güvenli kalmanızı sağlar ve güvenlik operasyonlarınızın verimliliğini artırmaya yardımcı olur.

Microsoft 365 Defender aracılığıyla uyarıları araştırmanın avantajlarından biri[, Kimlik için Microsoft Defender](/microsoft-365/security/defender/microsoft-365-defender) uyarıların paketteki diğer ürünlerin her birinden alınan bilgilerle daha fazla bağıntılı olmasıdır. Bu gelişmiş uyarılar, [Office 365 için Microsoft Defender ve Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint) kaynaklı diğer [Microsoft 365 Defender](/microsoft-365/security/office-365-security) uyarı biçimleriyle tutarlıdır. Yeni sayfa, kimlikle ilişkili uyarıları araştırmak için başka bir ürün portalına gitme gereksinimini etkili bir şekilde ortadan kaldırır.

Kimlik için Defender'dan kaynaklanan uyarılar artık uyarıları otomatik olarak düzeltme ve şüpheli etkinliğe katkıda bulunabilecek araç ve işlemlerin azaltılması da dahil olmak üzere Microsoft 365 Defender [otomatik araştırma ve yanıt (AIR)](/microsoft-365/security/defender/m365d-autoir) özelliklerini tetikleyebilir.

> [!IMPORTANT]
> Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

## <a name="review-security-alerts"></a>Güvenlik uyarılarını gözden geçirme

Uyarılar **sayfası,** **Olaylar** sayfası, tek tek **Cihazların** sayfaları ve **Gelişmiş tehdit avcılığı** sayfası dahil olmak üzere birden çok konumdan uyarılara erişilebilir. Bu örnekte **Uyarılar sayfasını** gözden geçireceğiz.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender'da</a> **Olaylar & uyarılar'a** ve ardından **Uyarılar'a** gidin.

:::image type="content" source="../../media/defender-identity/incidents-alerts.png" alt-text="Uyarılar menü öğesi" lightbox="../../media/defender-identity/incidents-alerts.png":::

Kimlik için Defender'dan gelen uyarıları görmek için sağ üst kısımda **Filtre'yi** seçin ve **ardından Hizmet kaynakları'nın** altında **Kimlik için Microsoft Defender'ı** seçin ve **Uygula'yı** seçin:

:::image type="content" source="../../media/defender-identity/filter-defender-for-identity.png" alt-text="Kimlik için Defender olaylarının filtresi" lightbox="../../media/defender-identity/filter-defender-for-identity.png":::

Uyarılar şu sütunlarda bilgilerle görüntülenir: **Uyarı adı**, **Etiketler**, **Önem Derecesi**, **Araştırma durumu**, **Durum**, **Kategori**, **Algılama kaynağı**, **Etkilenen varlıklar**, **İlk etkinlik** ve **Son etkinlik**.

:::image type="content" source="../../media/defender-identity/filtered-alerts.png" alt-text="Kimlik için Defender olayları" lightbox="../../media/defender-identity/filtered-alerts.png":::

## <a name="manage-alerts"></a>Uyarıları yönetin

**Uyarılardan birinin Uyarı adına** tıklarsanız, uyarıyla ilgili ayrıntıları içeren sayfaya gidersiniz. Sol bölmede **Neler olduğunu** özetleyeceğiz:

:::image type="content" source="../../media/defender-identity/what-happened.png" alt-text="Ne oldu bölmesi" lightbox="../../media/defender-identity/what-happened.png":::

**Ne oldu** kutusunun üstünde uyarının **Hesaplar**, **Hedef Ana Bilgisayar** ve **Kaynak Ana Bilgisayar** düğmeleri bulunur. Diğer uyarılar için ek konaklar, hesaplar, IP adresleri, etki alanları ve güvenlik grupları hakkındaki ayrıntılara yönelik düğmeler görebilirsiniz. İlgili varlıklar hakkında daha fazla ayrıntı almak için bunlardan herhangi birini seçin.

Sağ bölmede **Uyarı ayrıntılarını** görürsünüz. Burada daha fazla ayrıntı görebilir ve birkaç görev gerçekleştirebilirsiniz:

- **Bu uyarıyı sınıflandır** - Burada bu uyarıyı **Doğru uyarı** veya **Yanlış uyarı** olarak belirleyebilirsiniz

    :::image type="content" source="../../media/defender-identity/classify-alert.png" alt-text="Uyarıyı sınıflandırabileceğiniz sayfa" lightbox="../../media/defender-identity/classify-alert.png":::

- **Uyarı durumu** - **SınıflandırmaYı Ayarla'da** uyarıyı **Doğru** veya **Yanlış** olarak sınıflandırabilirsiniz. **Atanan'da**, uyarıyı kendinize atayabilir veya atamasını kaldırabilirsiniz.

    :::image type="content" source="../../media/defender-identity/alert-state.png" alt-text="Uyarı durumu bölmesi" lightbox="../../media/defender-identity/alert-state.png":::

- **Uyarı ayrıntıları** - **Uyarı ayrıntıları** altında, belirli uyarı hakkında daha fazla bilgi bulabilir, uyarı türüyle ilgili belgelerin bağlantısını izleyebilir, uyarının hangi olayla ilişkili olduğunu görebilir, bu uyarı türüne bağlı otomatik araştırmaları gözden geçirebilir ve etkilenen cihazları ve kullanıcıları görebilirsiniz.

   :::image type="content" source="../../media/defender-identity/alert-details.png" alt-text="Uyarı ayrıntıları sayfası" lightbox="../../media/defender-identity/alert-details.png":::

- **Açıklamalar & geçmişi** - Burada açıklamalarınızı uyarıya ekleyebilir ve uyarıyla ilişkili tüm eylemlerin geçmişini görebilirsiniz.

    :::image type="content" source="../../media/defender-identity/comments-history.png" alt-text="Açıklamalar & geçmişi sayfası" lightbox="../../media/defender-identity/comments-history.png":::

- **Uyarıyı yönet** - **Uyarıyı yönet'i** seçerseniz şunları düzenlemenizi sağlayacak bir bölmeye gidersiniz:
  - **Durum** - **Yeni**, **Çözüldü** veya **Devam Ediyor'u** seçebilirsiniz.
  - **Sınıflandırma** - **Doğru uyarı** veya **Yanlış uyarı'yı** seçebilirsiniz.
  - **Açıklama** - Uyarı hakkında açıklama ekleyebilirsiniz.

    **Uyarıyı yönet'in** yanındaki üç noktayı seçerseniz **bir tehdit uzmanına danışabilir**, Uyarıyı bir Excel dosyasına **aktarabilir** veya **Başka bir olaya bağlanabilirsiniz**.

    :::image type="content" source="../../media/defender-identity/manage-alert.png" alt-text="Uyarıyı yönet seçeneği" lightbox="../../media/defender-identity/manage-alert.png":::

    > [!NOTE]
    > Excel dosyasında artık iki bağlantınız vardır: **Kimlik için Microsoft Defender'da görüntüle** ve **Microsoft 365 Defender'da görüntüle**. Her bağlantı sizi ilgili portala getirir ve uyarı hakkında orada bilgi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 Defender'da uyarıları araştırma](../defender/investigate-alerts.md)
