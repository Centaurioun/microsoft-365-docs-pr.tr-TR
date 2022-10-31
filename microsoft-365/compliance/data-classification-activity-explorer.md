---
title: Etkinlik gezginini kullanmaya başlama
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier1
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
search.appverid:
- MOE150
- MET150
description: Etkinlik gezgini, kullanıcıların etiketlenmiş içeriğinizde yaptıkları eylemleri görmenizi ve filtrelemenizi sağlar.
ms.openlocfilehash: fd537c4157347a2984af0c1fa2097278abadd6a8
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793774"
---
# <a name="get-started-with-activity-explorer"></a>Etkinlik gezginini kullanmaya başlama

[Veri sınıflandırmasına genel bakış](data-classification-overview.md) ve [içerik gezgini](data-classification-content-explorer.md) sekmeleri, hangi içeriğin keşfedildiğine ve etiketlendiğine ve içeriğin nerede olduğuna ilişkin görünürlük sağlar. [Etkinlik gezgini](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer) , etiketlenmiş içeriğinizle yapılan işlemleri izlemenize olanak tanıyarak bu işlev paketini kullanıma sunar. Etkinlik gezgini etiketli içeriğinizdeki etkinliklerin geçmiş görünümünü sağlar. Etkinlik bilgileri Microsoft 365 birleşik denetim günlüklerinden toplanır, dönüştürülür ve Etkinlik gezgini kullanıcı arabiriminde kullanıma sunulur. Etkinlik gezgini en fazla 30 günlük verileri raporlar.

![yer tutucu ekran görüntüsü genel bakış etkinlik gezgini.](../media/data-classification-activity-explorer-1.png)

30'un üzerinde farklı filtre kullanılabilir, bazıları şunlardır:

- Tarih aralığı
- Etkinlik türü
- Konum
- Kullanıcı
- Duyarlılık etiketi
- Bekletme etiketi
- Dosya yolu
- DLP ilkesi



[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="prerequisites"></a>Önkoşullar

Veri sınıflandırmasına erişen ve kullanan her hesapta şu aboneliklerden birinden atanmış bir lisans olmalıdır:

- Microsoft 365 (E5)
- Office 365 (E5)
- Gelişmiş Uyumluluk (E5) eklentisi
- Gelişmiş Tehdit Bilgileri (E5) eklentisi
- Microsoft 365 E5/A5 Bilgi Koruması & İdare
- Microsoft 365 E5/A5 Uyumluluğu

### <a name="permissions"></a>İzinler

Bir hesaba bu rol gruplarından herhangi birinde açıkça üyelik atanmalıdır veya bu rol açıkça verilmelidir.

### <a name="roles-and-role-groups"></a>Roller ve Rol Grupları

Erişim denetimlerinizde ince ayar yapmak için kullanabileceğiniz roller ve rol grupları vardır.

Kullanabileceğiniz geçerli rollerin listesi aşağıdadır. Bunlar hakkında daha fazla bilgi edinmek için [Microsoft Purview uyumluluk portalı İzinler bölümüne](microsoft-365-compliance-center-permissions.md) bakın.

- Information Protection Yönetici
- Information Protection Analisti
- Information Protection Araştırmacısı
- Information Protection Okuyucu

Kullanabileceğiniz geçerli rol gruplarının listesi aşağıdadır. hakkında daha fazla bilgi edinmek için [bkz. Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md).

- Information Protection
- Information Protection Yöneticileri
- Information Protection Analistleri
- Information Protection Araştırmacıları
- Information Protection Okuyucular

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365 rol grupları**

- Genel yönetici
- Uyumluluk yöneticisi
- Güvenlik yöneticisi
- Uyumluluk veri yöneticisi

**Microsoft 365 rolleri**

- Uyumluluk yöneticisi
- Güvenlik yöneticisi
- Güvenlik Okuyucusu

## <a name="activity-types"></a>Etkinlik türleri

Etkinlik gezgini, birden çok etkinlik kaynağındaki denetim günlüklerinden etkinlik bilgilerini toplar. Etkinlik gezginine hangi etiketleme etkinliğinin neden olduğu hakkında daha ayrıntılı bilgi için bkz. [Etkinlik gezgininde kullanılabilen etiketleme olayları](data-classification-activity-explorer-available-events.md).

**Duyarlılık etiketi etkinlikleri** ve Office yerel **uygulamalarından elde tutma etiketleme etkinlikleri**, Azure Information Protection (AIP) birleşik etiketleme istemcisi ve tarayıcısı, SharePoint Online, Exchange Online (yalnızca duyarlılık etiketleri) ve OneDrive. Bazı örnekler şunlardır:

- Etiket uygulandı
- Etiket değiştirildi (yükseltildi, düşürüldü veya kaldırıldı)
- Otomatik etiketleme benzetimi
- Dosya okuma

**Azure Information Protection (AIP) tarayıcısı ve AIP istemcileri**

- Koruma uygulandı
- Koruma değiştirildi
- Koruma kaldırıldı
- Bulunan dosyalar

Etkinlik gezgini ayrıca Exchange Online, SharePoint Online, OneDrive, Teams Sohbet ve Kanal (önizleme), şirket içi SharePoint klasörleri ve kitaplıkları ve şirket içi dosya paylaşımları ile **uç nokta veri kaybı önleme (DLP)** aracılığıyla Windows 10 cihazlardan **gelen DLP ilkesi eşleşmelerini** toplar. Windows 10 cihazlardan bazı örnekler dosyasıdır:

- Silme
- Yarattık -ları
- Panoya kopyalandı
- Değiştirilmiş
- Okuma
- Yazdırılan
- Yeni -den adlandır
- Ağ paylaşımına kopyalandı
- İzin verilmeyen uygulama tarafından erişildi 

Hassas etiketli içeriğinizle hangi eylemlerin gerçekleştirildiğini anlamak, [Microsoft Purview Veri Kaybı Önleme](dlp-learn-about-dlp.md) ilkeleri gibi denetimlerinizin etkili olup olmadığını görmenize yardımcı olur. Aksi takdirde veya etiketlenmiş `highly confidential` ve düşürülen `general`çok sayıda öğe gibi beklenmeyen bir şey bulursanız, çeşitli ilkelerinizi yönetebilir ve istenmeyen davranışı kısıtlamak için yeni eylemler gerçekleştirebilirsiniz.

> [!NOTE]
> Etkinlik gezgini şu anda Exchange Online için bekletme etkinliklerini izlemez.

## <a name="see-also"></a>Ayrıca bkz.

- [Duyarlılık etiketleri hakkında bilgi edinin](sensitivity-labels.md)
- [Bekletme ilkeleri ve bekletme etiketleri hakkında bilgi edinin](retention.md)
- [Hassas bilgi türleri hakkında daha fazla bilgi edinme](sensitive-information-type-learn-about.md)
- [Veri sınıflandırması hakkında daha fazla bilgi edinme](data-classification-overview.md)
