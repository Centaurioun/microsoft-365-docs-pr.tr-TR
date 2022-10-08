---
title: Microsoft Teams EHR bağlayıcısı Sanal Randevular raporu
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ''
description: Kuruluşunuzdaki EHR tümleşik sanal randevu kullanımına genel bir bakış elde etmek için Microsoft Teams yönetim merkezinde Teams EHR bağlayıcısı Sanal Randevular raporunu kullanmayı öğrenin.
ms.openlocfilehash: 6890c664897e4bb9e0998f4c441dc623bac1baa1
ms.sourcegitcommit: 674dfa2cb2f20546d2f7822e09bacf0e12e2718b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68039247"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams EHR bağlayıcısı Sanal Randevular raporu

Microsoft Teams yönetim merkezindeki Microsoft Teams Elektronik Sistem Durumu Kaydı (EHR) bağlayıcısı Sanal Randevular raporu, kuruluşunuzda Teams EHR ile tümleşik sanal randevu kullanımını görüntülemenin hızlı ve kolay bir yolunu sunar.

Raporu görüntülemek için genel yönetici, Teams yöneticisi, Genel okuyucu veya Rapor okuyucusu olmanız gerekir.

## <a name="view-the-report"></a>Raporu görüntüleme

Teams yönetim merkezinde rapora erişmenin ve raporu görüntülemenin iki yolu vardır.

- Panodaki [EHR bağlayıcısı kullanım kartı](#the-ehr-connector-usage-card) aracılığıyla
- **Doğrudan Analiz & raporlarında** >  [**EHR bağlayıcısı**](#the-teams-ehr-connector-virtual-appointments-report) Sanal Randevular seçerek **Kullanım raporları**

### <a name="the-ehr-connector-usage-card"></a>EHR bağlayıcısı kullanım kartı

Microsoft Teams yönetim merkezinin sol gezinti bölmesinde **Pano'yu** seçin ve ardından **EHR bağlayıcısı Sanal Randevular** kartına gidin.

Burada, tamamlanan randevular, kalan ayırma ve aylık sınırı aşıp aşmadığınız (sahip olduğunuz lisansa bağlı olarak) dahil olmak üzere Teams EHR ile tümleşik sanal randevu etkinliğini aya göre bir bakışta görebilirsiniz.

:::image type="content" source="media/ehr-connector-report-card.png" alt-text="Teams yönetim merkezi panosundaki EHR bağlayıcısı kullanım kartının ekran görüntüsü." lightbox="media/ehr-connector-report-card.png":::

Rapor ayrıntılarını görmek için **Ayrıntıları görüntüle'yi** seçin. Daha fazla lisans satın almak için **Daha fazla lisans satın al'ı** seçin.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Teams EHR bağlayıcısı Sanal Randevular raporu

1. Teams yönetim merkezinin sol gezinti bölmesinde **Analiz & raporları** > **Kullanım raporları'na** gidin.
1. **Raporları görüntüle** sekmesinde **EHR bağlayıcısı Sanal Randevular** ve bir tarih aralığı seçin. Ardından **Raporu çalıştır'ı** seçin.

    :::image type="content" source="media/ehr-connector-report.png" alt-text="Teams yönetim merkezindeki Teams EHR bağlayıcısı Sanal Randevular raporunun ekran görüntüsü." lightbox="media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Raporu yorumlama

|Bilgisi |Açıklama  |
|--------|-------------|
|**1**   |Her rapor, raporun oluşturulduğu tarihi ve seçtiğiniz tarih aralığını gösterir.|
|**2**   |Tablo, seçilen tarih aralığında gerçekleşen her randevu hakkında ayrıntılı bilgi verir. Bir personel üyesinin veya hastanın katılmadığı randevuların girdilerini göremeyeceğinizi unutmayın. <ul><li>**Başlangıç saati (UTC),** hem personel üyesinin hem de katılımcının randevuda olduğu tarih ve saattir.  </li> <li>**Süre** , başlangıç saati ile son kişinin randevudan ayrılması arasındaki zaman farkıdır.</li> <li>**Birincil** , toplantı düzenleyicisinin adıdır. <li>**Birincilin e-postası** , toplantı düzenleyicisinin e-posta adresidir.</li> <li> **Departman** , randevunun bölüm bilgileridir. Bilgiler doğru görüntülenmezse EHR destek ekibinize başvurun. Epic ile tümleştirme için sağlayıcı tümleştirme kaydının bir parçası olduğundan emin olun ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` . </li></li> <li>**Katılımcılar** , randevudaki toplam personel ve katılımcı sayısıdır.</li> <li>**Sınır içinde** randevunun ayırma sınırı içinde olup olmadığını gösterir. </li> </ul> |
|**3**   |Raporu çevrimdışı analiz için csv dosyasına aktarabilirsiniz. Raporu indirmek **için Excel'e Aktar'ı** seçin. |
|**4**   |Rapor ayrıntıları görünümünü filtrelemek için **Filtre'yi** seçin. |
|**5**   |Raporu **tam ekran** modunda görüntülemek için Tam ekran'ı seçin. |
|**6**   |Tabloya sütun eklemek veya kaldırmak için Sütunları **düzenle'yi** seçin |

> [!NOTE]
> Teams EHR ile tümleşik sanal randevular hakkında daha fazla analiz için bkz. [Sanal Ziyaretler kullanım raporu](virtual-visits-usage-report.md). Sanal Ziyaretler kullanım raporuyla toplam randevular, lobi bekleme süresi, randevu süresi ve gösteri yok gibi önemli ölçümleri görüntüleyebilirsiniz. Daha iyi iş sonuçları sunmak üzere sanal randevuları iyileştirmenize yardımcı olmak üzere kullanım eğilimleri hakkında içgörü elde etmek için bu bilgileri kullanın.

## <a name="related-articles"></a>İlgili makaleler

- [Teams ile sanal randevular - Cerner EHR ile tümleştirme](ehr-admin-cerner.md)
- [Teams ile sanal randevular - Epic EHR ile tümleştirme](ehr-admin-epic.md) 
