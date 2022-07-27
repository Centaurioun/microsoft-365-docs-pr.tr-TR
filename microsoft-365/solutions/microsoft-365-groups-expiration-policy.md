---
title: Microsoft 365 grup süre sonu ilkesi
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: Microsoft 365 grupları süre sonu ilkeleri hakkında bilgi edinin.
ms.openlocfilehash: 3fd7d5269d755d6b48429b425616d42157e3294c
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67050666"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 grup süre sonu ilkesi

Microsoft 365 gruplarının ve Microsoft Teams'in kullanımındaki artışla birlikte, yöneticilerin ve kullanıcıların kullanılmayan grupları ve ekipleri temizlemenin bir yoluna ihtiyacı vardır. Microsoft 365 grupları süre sonu ilkesi, etkin olmayan grupları sistemden kaldırmaya ve işleri temizlemeye yardımcı olabilir.

Grubun süresi dolduğunda, tüm ilişkili hizmetleri (posta kutusu, Planner, SharePoint sitesi, ekip vb.) de silinir.

Bir grubun süresi dolduğunda "geçici olarak silinir", yani 30 güne kadar kurtarılabilir.

Yöneticiler bir süre sonu belirtebilir ve bu sürenin sonuna ulaşan ve yenilenmeyen tüm etkin olmayan gruplar silinir. (Buna arşivlenmiş ekipler de dahildir.) Süre sonu, grup oluşturulduğunda veya son yenilendiği tarihte başlar. Grup sahiplerine, süresi dolmadan önce otomatik olarak bir e-posta gönderilir ve bu da grubu başka bir süre sonu aralığı için yenilemelerine olanak tanır. Teams kullanıcıları, Teams'de kalıcı bildirimler görür.

Etkin olarak kullanımda olan gruplar otomatik olarak yenilenir. Aşağıdaki eylemlerden herhangi biri grubu otomatik olarak yeniler:
- SharePoint - Dosyaları görüntüleyin, düzenleyin, indirin, taşıyın, paylaşın veya karşıya yükleyin. (SharePoint sayfasını görüntülemek, otomatik yenileme eylemi olarak sayılmaz.)
- Outlook - Gruba katılma veya grubu düzenleme, gruptan gelen grup iletisini okuma veya yazma ve ileti gibi (Web üzerinde Outlook).
- Teams - Bir ekip kanalını ziyaret edin.
- Yammer - Bir Yammer topluluğundaki gönderiyi veya Outlook'ta etkileşimli bir e-postayı görüntüleyin.
- Formlar - Formları görüntüleyin, oluşturun veya düzenleyin ya da forma yanıt gönderin. 

> [!IMPORTANT]
> Süre sonu ilkesini değiştirdiğinizde, hizmet her grup için sona erme tarihini yeniden hesaplar. Her zaman grubun oluşturulduğu tarihten itibaren saymaya başlar ve ardından yeni süre sonu ilkesini uygular.

Süre sonunun varsayılan olarak kapalı olduğunu bilmek önemlidir. Kullanmak isteyen yöneticilerin kuruluşlarında etkinleştirmesi gerekir.

> [!NOTE]
> Microsoft 365 grupları için süre sonu ilkesinin yapılandırılması ve kullanılması için, süre sonu ilkesinin uygulandığı tüm grupların üyeleri için Azure AD Premium lisansları atamanız zorunlu değildir. Daha fazla bilgi için bkz[. Azure Active Directory Premium kullanmaya başlama](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Microsoft 365 grupları süre sonu ilkesini kimler yapılandırabilir ve kullanabilir?

|Rol|Yapabilecekleri|
|---------|---------|
|Office 365 genel yönetici (Azure'da, Şirket yöneticisi), Kullanıcı yöneticisi|Microsoft 365 grupları süre sonu ilkesi ayarlarını oluşturun, okuyun, güncelleştirin veya silin.|
|Kullanıcı|Sahip oldukları bir Microsoft 365 grubunu yenileme veya [geri yükleme](/azure/active-directory/users-groups-roles/groups-restore-deleted)|

## <a name="how-to-set-the-expiration-policy"></a>Süre sonu ilkesini ayarlama

Yukarıda belirtildiği gibi, süre sonu varsayılan olarak kapalıdır. Bir yöneticinin süre sonu ilkesini etkinleştirmesi ve etkili olması için özelliklerini ayarlaması gerekir. Etkinleştirmek için **Azure Active Directory** > **Grupları** > **Süre Sonu'na** gidin. Burada varsayılan grup ömrünü ayarlayabilir ve birinci ve ikinci süre sonu bildirimlerinin grup sahibine ne kadar önceden gitmesini istediğinizi belirtebilirsiniz.

Grup ömrü gün cinsinden belirtilir ve 180, 365 veya belirttiğiniz özel bir değere ayarlanabilir. Özel değerin en az 30 gün olması gerekir.

Grubun sahibi yoksa, süre sonu e-postaları belirtilen yöneticiye gider.

İlkeyi tüm gruplarınız için, yalnızca seçili gruplar için (en fazla 500) ayarlayabilir veya **Hiçbiri'ni** seçerek tamamen kapatabilirsiniz. **Hiçbiri'ni** seçtiğinizde etkin olan ve doğrulama için bekleyen tüm grupların son kullanma tarihi olmaz. Ancak, süresi dolmuş olan gruplar etkilenmez.

Şu anda farklı gruplar için farklı ilkelere sahip olamazsınız.

![Azure Active Directory'de Grupların süre sonu ayarlarının ekran görüntüsü.](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Süre sonu bekletme ilkesiyle nasıl çalışır?

Microsoft Purview uyumluluk portalı gruplar için bir bekletme ilkesi ayarladıysanız, süre sonu ilkesi bekletme ilkesiyle sorunsuz çalışır. Grubun süresi dolduğunda, grubun posta kutusu konuşmaları ve grup sitesindeki dosyaları bekletme ilkesinde tanımlanan belirli sayıda gün boyunca bekletme kapsayıcısında tutulur. Ancak kullanıcılar süre dolduktan sonra grubu veya içeriğini göremez.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Grup sahibi gruplarının süresinin dolup dolmadığını nasıl ve ne zaman öğrenir?

Grup Planner, SharePoint veya başka bir uygulama aracılığıyla oluşturulduysa, sona erme bildirimleri her zaman e-posta yoluyla gelir.
Grup Teams aracılığıyla oluşturulduysa, grup sahibi etkinlik bölümü aracılığıyla yenilenmesi için bir e-posta ve bildirim alır. Grup sahibinizin geçerli bir e-posta adresi yoksa grupta süre sonunu etkinleştirmeniz önerilmez.

Grubun süresi dolmadan 30 gün önce, grup sahipleri (veya sahibi olmayan gruplar için belirttiğiniz e-posta adresleri) grubu kolayca yenilemelerini sağlayan bir e-posta alır. Yenilemezlerse, süresi dolmadan 15 gün önce başka bir yenileme e-postası alırlar. Hala yenilemediyse, sona erme tarihinden bir gün önce bir e-posta bildirimi daha alırlar.

Bazı nedenlerden dolayı, sahiplerden veya yöneticilerden hiçbiri grubu süresi dolmadan önce yenilemezse, yönetici son kullanma tarihinden sonra 30 güne kadar grubu geri yükleyebilir. Ayrıntılar için bkz. [Silinmiş bir Microsoft 365 grubunu geri yükleme](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Grup içeriğini arşivleme

Artık kullanmayı planlamadığınız ancak içeriğini korumak istediğiniz bir grubunuz varsa, farklı grup hizmetlerinden bilgileri dışarı aktarma hakkında bilgi için bkz. [Grupları, ekipleri ve Yammer'ı arşivleyin](end-life-cycle-groups-teams-sites-yammer.md) .

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Bekletme ilkelerine genel bakış](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Sahipsiz bir gruba yeni sahip atama](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365 gruplarının süre sonunu yapılandırma](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
