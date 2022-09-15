---
title: İş için Microsoft Defender raporları
description: İş için Defender'da güvenlik raporlarına genel bir bakış elde edin. Raporlar algılanan tehditleri, uyarıları, güvenlik açıklarını ve cihaz durumunu gösterir.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 09/14/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 0f8810ef2892be0c5e17f96ebd115dd1e4d6b578
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711334"
---
# <a name="reports-in-microsoft-defender-for-business"></a>İş için Microsoft Defender raporları

Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) çeşitli raporlar mevcuttur. Bu makalede bu raporlar, bunları nasıl kullanabileceğiniz ve nasıl bulabileceğiniz açıklanmaktadır.

## <a name="reports-in-defender-for-business"></a>İş için Defender'daki raporlar

|Rapor  |Açıklama  |
|---------|---------|
| **Güvenlik raporu**  | Güvenlik raporu şirketinizin kimlikleri, cihazları ve uygulamaları hakkında bilgi sağlar. Bu rapora erişmek için gezinti bölmesinde **Raporlar** > **Genel** > **Güvenlik raporu'na** tıklayın. <br/><br/>Benzer bilgileri Microsoft 365 Defender portalınızın ([https://security.microsoft.com](https://security.microsoft.com) ) giriş sayfasında görüntüleyebilirsiniz. |
| **Tehdit koruması**  | Tehdit koruması raporu, uyarılar ve uyarı eğilimleri hakkında bilgi sağlar. Son 30 gün içinde tetiklenen uyarılar hakkındaki bilgileri görüntülemek için **Uyarı eğilimleri** sütununu kullanın. Çözümlenmemiş uyarı kategorileri ve bunların sınıflandırması gibi uyarılar hakkındaki geçerli anlık görüntü bilgilerini görüntülemek için **Uyarı durumu** sütununu kullanın. Bu rapora erişmek için gezinti bölmesinde **Raporlar** > **Uç Noktaları** > **Tehdit koruması'nı** seçin. <br/><br/>Uyarılar hakkındaki bilgileri görüntülemek için **Olaylar** listesini de kullanabilirsiniz. Geçerli olayları görüntülemek ve yönetmek için gezinti bölmesinde **Olaylar'ı** seçin. Daha fazla bilgi için bkz. [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md). |
| **Cihaz durumu ve uyumluluğu** | Cihaz durumu ve uyumluluk raporu, cihaz durumu ve eğilimleri hakkında bilgi sağlar. İş için Defender algılayıcılarının cihazlarda düzgün çalışıp çalışmadığını ve Microsoft Defender Virüsten Koruma'nın geçerli durumunu belirlemek için bu raporu kullanabilirsiniz. Bu rapora erişmek için gezinti bölmesinde **Rapor** > **Uç Noktaları** > **Cihaz durumu ve uyumluluğu'na** tıklayın. <br/><br/>Şirketinizin cihazları hakkındaki bilgileri görüntülemek için **Cihazlar** listesini kullanabilirsiniz. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin. Daha fazla bilgi için bkz. [İş için Defender'da cihazları yönetme](mdb-manage-devices.md). |
| **Güvenlik açığı olan cihazlar** | Güvenlik açığı bulunan cihazlar raporu, cihazlar ve eğilimler hakkında bilgi sağlar. Son 30 gün içinde uyarıları olan cihazlar hakkındaki bilgileri görüntülemek için **Eğilimler** sütununu kullanın. Uyarı içeren cihazlar hakkındaki geçerli anlık görüntü bilgilerini görüntülemek için **Durum** sütununu kullanın. Bu rapora erişmek için gezinti bölmesinde **Rapor** > **Uç Noktaları** > **Savunmasız cihazlar'ı** seçin.<br/><br/>**İpucu**: Şirketinizin cihazları hakkındaki bilgileri görüntülemek için **Cihazlar** listesini kullanabilirsiniz. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin. Daha fazla bilgi için bkz. [İş için Defender'da cihazları yönetme](mdb-manage-devices.md). |
| **Web koruması** | Web koruma raporu kimlik avı sitelerine, kötü amaçlı yazılım vektörlerine, güvenlik açığından yararlanma sitelerine, güvenilmeyen veya saygınlığı düşük sitelere ve açıkça engellenen sitelere erişme girişimlerini gösterir. Engellenen sitelerin kategorileri yetişkin içeriği, boş zaman siteleri, yasal sorumluluk siteleri ve daha fazlasını içerir. Bu rapora erişmek için gezinti bölmesinde **Raporlar** > **Uç Noktaları** > **Web koruması'nı** seçin.<br/><br/>Şirketiniz için henüz web koruması yapılandırmadıysanız rapor görünümünde **Ayarlar** düğmesini seçin. Ardından, **Kurallar'ın** altında **Web içeriği filtreleme'yi** seçin. Web içeriği filtreleme hakkında daha fazla bilgi edinmek için bkz. [Web içeriği filtreleme](../defender-endpoint/web-content-filtering.md). |
| **Güvenlik duvarı** | Güvenlik duvarı raporu engellenen gelen, giden ve uygulama bağlantılarını gösterir. Bu rapor ayrıca birden çok cihaz tarafından bağlanan uzak IP'leri ve en fazla bağlantı denemesine sahip uzak IP'leri gösterir. <br/><br/>Güvenlik duvarı korumanızı henüz yapılandırmadıysanız gezinti bölmesinde **Uç Nokta** > **Yapılandırma yönetimi** > **Cihaz yapılandırması'nı** seçin. Daha fazla bilgi için bkz [. İş için Defender'da güvenlik duvarı](mdb-firewall.md). |
| **Cihaz denetimi** | Cihaz denetimi raporu, kuruluşunuzda çıkarılabilir depolama cihazlarının kullanımı gibi medya kullanımı hakkındaki bilgileri gösterir. |


## <a name="see-also"></a>Ayrıca bkz.

- [İş için Defender'ı kullanmaya başlama](mdb-get-started.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da cihazları yönetme](mdb-manage-devices.md)
