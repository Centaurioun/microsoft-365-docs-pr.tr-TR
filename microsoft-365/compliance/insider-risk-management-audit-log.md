---
title: Insider risk yönetimi denetim günlüğü
description: Microsoft Purview'da insider risk yönetimi denetim günlüğü hakkında bilgi edinin
keywords: Microsoft 365, Microsoft Purview, insider riski, risk yönetimi, uyumluluk
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.openlocfilehash: c1b381ed918f91b0334446117c4897eb3bfa0dd1
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730941"
---
# <a name="insider-risk-management-audit-log"></a>Insider risk yönetimi denetim günlüğü

>[!IMPORTANT]
>Microsoft Purview İçeriden Risk Yönetimi IP hırsızlığı, veri sızıntısı ve güvenlik ihlalleri gibi olası kötü amaçlı veya yanlışlıkla insider risklerini belirlemek için çeşitli sinyalleri ilişkilendirmektedir. Insider risk yönetimi, müşterilerin güvenlik ve uyumluluğu yönetmek için ilkeler oluşturmasına olanak tanır. Tasarım gereği gizlilikle oluşturulan kullanıcılar varsayılan olarak takma ad kullanır ve kullanıcı düzeyinde gizlilik sağlamaya yardımcı olmak için rol tabanlı erişim denetimleri ve denetim günlükleri kullanılır.

Insider risk yönetimi denetim günlüğü, insider risk yönetimi özelliklerinde gerçekleştirilen eylemler hakkında bilgi sahibi olmanıza olanak tanır. Bu günlük, bir veya daha fazla iç risk yönetimi rol grubuna atanan kullanıcılar tarafından gerçekleştirilen eylemlerin bağımsız olarak gözden geçirilmesine olanak tanır. Insider risk yönetimi denetim günlüğü kuruluşunuzda otomatik olarak etkinleştirilir ve devre dışı bırakılamaz.

![Insider risk yönetimi denetim günlüğü.](../media/insider-risk-audit-log.png)

Tanımlanan risk etkinlikleri algılandığında denetim günlüğü otomatik olarak ve hemen güncelleştirilir. Denetim günlüğü bilgileri 180 gün (yaklaşık altı ay) boyunca saklar. 180 gün sonra veriler günlükten kalıcı olarak silinir.

Tanımlanan risk etkinliği algılama alanlarında şunlar yer alır:

- İlkeler
- Durumda
- Uyarılar
- Ayarlar
- Kullanıcılar
- Bildirim şablonları

Denetim günlüğündeki verileri görüntülemek ve dışarı aktarmak için kullanıcıların *Insider Risk Management* veya *Insider Risk Management Auditors* rol gruplarına atanması gerekir. Insider risk yönetimi rol grupları hakkında daha fazla bilgi edinmek için bkz. [Insider risk yönetimine başlama 1. Adım: İzinleri etkinleştirme](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management).

> [!NOTE]
> Insider risk yönetimi denetim günlüğü, bağımsız denetim sistemleri olduğundan ve ayrı alanlardaki bilgileri yakaladığından Microsoft 365 denetim günlüğüyle ilişkili değildir. Microsoft 365 denetimini devre dışı bırakmak, iç risk yönetimi içindeki etkinlik denetimini etkilemez.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="view-activity-in-the-insider-risk-audit-log"></a>Insider risk denetim günlüğünde etkinliği görüntüleme

Insider risk yönetimi için algılanan özellik etkinliğini görüntülemek için, herhangi bir insider risk yönetimi sekmesinin sağ üst kısmındaki **Insider risk denetim günlüğü** bağlantısına gidin ve seçin. Varsayılan olarak, insider risk yönetimi etkinlikleri için aşağıdaki bilgileri görürsünüz:

- **Etkinlik:** Bir kullanıcı tarafından insider risk yönetimi çözümünde alınan tanımlanan risk etkinliğinin açıklaması.
- **Kategori:** Tanımlanan risk etkinliğinin gerçekleştirildiği alan veya öğe. Örneğin, ilke değişikliği etkinlikleri gerçekleştirildiğinde  kategori olarak İlkeler'i görürsünüz.
- **Gerçekleştirilen etkinlik:** Tanımlanan risk etkinliğini gerçekleştiren kullanıcının kullanıcı adı.
- **Tarih:** Tanımlanan risk etkinliğinin gerçekleştirildiği tarih ve saat. Tarih ve saat, kuruluşunuzun yerel tarih ve saatidir.

Günlüğe kaydedilen etkinlik hakkında daha fazla bilgi için etkinliği seçerek etkinlik ayrıntıları bölmesini görüntüleyin. Bu bölme, tanımlanan risk etkinliği hakkında ek bilgiler içerir.

## <a name="columns-and-filtering"></a>Sütunlar ve filtreleme

Denetçilerin denetim günlüklerini gözden geçirmesini kolaylaştırmak için **Insider risk denetim günlüğünde** filtreleme desteklenir. Temel filtreleme için, dosya ve iletilerde farklı özetler sağlamak üzere görünüme kuyruk sütunları eklenebilir. Tanımlanan risk etkinliklerini Alanlar **tarafından gerçekleştirilen** **Kategori, Tarih aralığı** ve Etkinlik'e göre filtreleyebilirsiniz.

Kuyruğa sütun başlıkları eklemek veya kaldırmak için **Sütunları özelleştir** denetimini kullanın ve sütun seçeneklerinden birini seçin. Bu sütunlar **Insider risk denetim günlüğünde** desteklenen yaygın koşullarla eşlenir ve bu makalenin devamında listelenmiştir.

## <a name="audit-log-export"></a>Denetim günlüğü dışarı aktarma

*Insider Risk Yönetimi* veya *Insider Risk Yönetimi Denetçileri* rol gruplarına atanan kullanıcılar, **Insider risk** denetim günlüğü sayfasında **Dışarı Aktar'ı** seçerek denetim günlüğü etkinliğini bir .csv (virgülle ayrılmış değerler) dosyasına aktarabilir. Denetim günlüğü etkinliğine bağlı olarak, bazı alanlar filtrelenen kuyruğa eklenmeyebilir ve bu nedenle bu alanlar dışarı aktarılan dosyada boş olarak görünür.

Dosya, aşağıdaki alanlar için denetim günlüğü etkinlik bilgilerini içerir:

- **Gerçekleştirilen etkinlik:** Öğe değerini değiştiren kullanıcının adı. Burada listelenen kullanıcılar şu rol [insider risk yönetimi rol gruplarından](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management) birine veya daha fazlasına atanmıştır: *Insider Risk Management*, *Insider Risk Management Yöneticileri*, *Insider Risk Yönetimi Analistleri*, *Insider Risk Yönetimi Araştırmacıları*. Her rol grubunun insider risk özelliklerini yönetmek için farklı izin düzeyleri vardır.
- **Etkinlik:** Bir öğede gerçekleştirilen etkinliğin türü. Değerler *Görüntülenir, Silinir, Eklenir, Düzenlenen ilke, Servis Talebi, Kullanıcı, Uyarı* ve *Ayarlar'dır.*
- **Eklendi**: Kullanıcılar, dosya türleri veya etki alanları gibi tanımlanan risk etkinliği sırasında eklenen nesneler.
- **Uyarı hacmi**: İç risk yönetimi ayarlarında tanımlanan uyarı birimi düzeyi.
- **Tutar**: İlke için şu anda seçili olan özel gösterge tutarları.
- **Varlık Kimliği**: Etkinliğin gerçekleştirildiği öncelikli fiziksel varlığın varlık kimliği.
- **Kategori:** Değiştirilen öğenin kategorisi. Değerler *İlkeler, Servis Talepleri, Kullanıcılar, Uyarılar, Ayarlar* ve *Bildirim şablonlarıdır.*
- **Tarih:** Kuruluşunuzun yerel tarih ve saatinde listelenen tarih ve saat.
- **Açıklama**: Üzerinde işlem yapılan nesne için kullanıcı tarafından yapılan açıklama girişi (ilke veya öncelikli kullanıcı grubu gibi).
- **DLP ilkesi**: Bir iç risk yönetimi ilkesine dahil edilmeyi tetikleme amacıyla seçilen Microsoft Purview Veri Kaybı Önleme (DLP) ilkesi.
- **Gösterge**: Insider risk ayarlarında etkinliğin gerçekleştirildiği gösterge (gösterge ekleme veya kaldırma gibi).
- **Bildirim şablonu**: Tanımlanan risk etkinliğinin üzerinde gerçekleştirildiğine ilişkin bildirim şablonu.
- **Gün sayısı**: İç risk ayarlarında tanımlanan ilke etkinleştirme penceresi.
- **Dosya sayısı**: Insider risk yönetimi ayarlarında tanımlanan dosya birimi sınırı.
- **İlke şablonu**: Göstergelerin üzerinde işlem yaptığı ilke şablonu ait.
- **Önceki tutar**: İlke için önceden seçilen özel gösterge tutarları.
- **Öncelikli kullanıcı grubu**: Tanımlanan risk etkinliğinin gerçekleştirildiği öncelikli kullanıcı grubu.
- **Kaldırıldı**: Kullanıcılar, dosya türleri veya etki alanları gibi tanımlanan risk etkinliği sırasında kaldırılan nesneler.
- **Gönderen**: Tanımlanan risk etkinliğinin gerçekleştirildiği bildirim şablonunun Gönderen alanı.
- **Hedef ilke**: Tanımlanan risk etkinliğinin gerçekleştirildiği ilke (örneğin, bir kullanıcıyı ekleme veya kaldırma).
- **Şablon ileti gövdesi**: Tanımlanan risk etkinliğinin gerçekleştirildiği bildirim şablonunun ileti gövdesi.
- **Şablon konusu**: Tanımlanan risk etkinliğinin gerçekleştirildiği bildirim şablonunun konu alanı.
- **Kullanıcı:** Tanımlanan risk etkinliğinin gerçekleştirildiği kullanıcı.