---
title: Cihaz durumu Algılayıcı sistem durumu & işletim sistemi raporu
description: Cihaz durumunu, işletim sistemi platformlarını ve Windows 10 sürümlerini izlemek için cihaz durumu raporunu kullanın.
keywords: sistem durumu, virüsten koruma, işletim sistemi platformu, windows 10 sürümü, sürüm, sistem durumu, uyumluluk, durum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: dd5b773ffb3d658e3943a4351b905af43504436c
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731696"
---
# <a name="device-health-sensor-health--os-report"></a>Cihaz durumu, Algılayıcı sistem durumu & işletim sistemi raporu

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cihaz Durumu raporu, kuruluşunuzdaki cihazlar hakkında bilgi sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını, Windows 10 sürümlerini ve Microsoft Defender Virüsten Koruma güncelleştirme sürümlerini gösteren popüler bilgileri içerir.

> [!IMPORTANT]
> Windows&nbsp;Server&nbsp;2012&nbsp;R2 ve Windows&nbsp;Server&nbsp;2016'nın cihaz durumu raporlarında görünmesi için bu cihazların modern birleşik çözüm paketi kullanılarak eklenmesi gerekir. Daha fazla bilgi için bkz. [Windows Server 2012 R2 ve 2016 için modern birleşik çözümde yeni işlevler](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

Microsoft 365 Güvenlik panosu gezinti panelinde **Raporlar'ı** seçin ve ardından **Cihaz durumu ve uyumluluğu'nu** açın.

- [**Algılayıcı sistem durumu & işletim** sistemi sekmesi](#sensor-health--os-tab), aşağıdaki cihaz özniteliklerini görüntüleyen üç karta ayrılmış genel işletim sistemi bilgileri sağlar:
  - [Algılayıcı sistem durumu kartı](#sensor-health-card)
  - [İşletim sistemleri ve platformlar kartı](#operating-systems-and-platforms-card)
  - [Windows sürümleri kartı](#windows-versions-card)

## <a name="report-access-permissions"></a>Rapor erişim izinleri

Microsoft 365 Güvenlik panosunda Cihaz durumu ve virüsten koruma uyumluluk raporuna erişmek için aşağıdaki izinler gereklidir:

| İzin adı | İzin türü |
|:---|:---|
| Verileri Görüntüle | Tehdit ve güvenlik açığı yönetimi (TVM) |

Bu izinleri atamak için:

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.
1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).
1. Düzenlemek istediğiniz rolü seçin.
1. **Düzenle'yi** seçin.
1. **Rolü düzenle'nin** **Genel** sekmesindeki **Rol adı** alanına rol için bir ad yazın.
1. **Açıklama** alanına rolün kısa bir özetini yazın.
1. **İzinler'de** **Verileri Görüntüle'yi** seçin ve **Verileri Görüntüle'nin** altında **Tehdit ve güvenlik açığı yönetimi** (TVM) öğesini seçin.

Kullanıcı rolü yönetimi hakkında daha fazla bilgi için bkz. [Rol tabanlı erişim denetimi için rol oluşturma ve yönetme](user-roles.md).

## <a name="sensor-health--os-tab"></a>Algılayıcı sistem durumu & işletim sistemi sekmesi

Algılayıcı durumu ve işletim sistemi kartları algılama algılayıcısı durumu, güncel ve güncel olmayan işletim sistemleri ve Windows 10 sürümleri içeren genel işletim sistemi durumu hakkında rapor sunar.

>:::image type="content" source="images/device-health-sensor-health-os-tab.png" alt-text="Algılayıcı sistem durumu ve İşletim sistemi bilgilerini gösterir." lightbox="images/device-health-sensor-health-os-tab.png":::

**Algılayıcı sistem durumu** sekmesindeki üç kartın her birinde _geçerli durum_ ve _cihaz eğilimleri_ şeklinde grafik olarak sunulan iki raporlama bölümü vardır:

### <a name="current-state-graph"></a>Geçerli durum grafiği

Her kartta Geçerli durum (bazı belgelerde _Cihaz özeti_ olarak adlandırılır) en üstteki yatay çubuk grafiktir. Geçerli durum, kuruluşunuzdaki cihazlar hakkında toplanan bilgileri gösteren ve kapsamı geçerli güne göre belirlenmiş bir anlık görüntüdür. Bu grafik, kuruluşunuz genelinde durum bildiren veya belirli bir durumda olduğu algılanan cihazların dağıtımını temsil eder.

>:::image type="content" source="images/device-health-sensor-health-os-current-state-graph.png" alt-text="Geçerli durum grafiğini gösterir." lightbox="images/device-health-sensor-health-os-current-state-graph.png":::

### <a name="device-trends-graph"></a>Cihaz eğilimleri grafiği

Üç kartın her birinin alt grafiğinin adı yoktur, ancak genellikle _cihaz eğilimleri_ olarak bilinir. Cihaz eğilimleri grafiği, doğrudan grafiğin üzerinde belirtilen zaman aralığı boyunca kuruluşunuz genelindeki cihaz koleksiyonunu gösterir.
Varsayılan olarak, cihaz eğilimleri grafiği 30 günlük dönemdeki cihaz bilgilerini görüntüler ve en son tam gün ile biter. Kuruluşunuzda gerçekleşen eğilimler hakkında daha iyi bir bakış açısı elde etmek için, gösterilen zaman aralığını ayarlayarak raporlama dönemine ince ayar yapabilirsiniz. Zaman aralığını ayarlamak için filtreyi açın ve bir başlangıç günü ile bitiş günü seçin.

>:::image type="content" source="images/device-health-sensor-health-os-device-trends-graph.png" alt-text="Cihaz Durumu sürüm eğilimleri grafiğini gösterir." lightbox="images/device-health-sensor-health-os-device-trends-graph.png":::

### <a name="filtering-data"></a>Verileri filtreleme

Belirli özniteliklere sahip cihazları dahil etmek veya hariç tutmak için sağlanan filtreleri kullanın. Cihaz özniteliklerinden uygulanacak birden çok filtre seçebilirsiniz. Filtreler uygulandığında rapordaki üç karta da uygulanır.

Örneğin, Etkin algılayıcı sistem durumu olan Windows 10 cihazlar hakkındaki verileri göstermek için:

1. **Filtreler** > **Algılayıcı sistem durumu Etkin altında** > .
2. Ardından **işletim sistemi platformları** >  **Windows 10'ni** seçin.
3. **Uygula'yı** seçin.

### <a name="sensor-health-card"></a>Algılayıcı sistem durumu kartı

Algılayıcı sistem durumu kartı, cihazlardaki algılayıcı durumu hakkında bilgi görüntüler. Algılayıcı durumu, şu cihazların toplam görünümünü sağlar:

- Etkin
- Etkin olmayan
- sorun yaşayan iletişimler
- veya algılayıcı verilerinin bildirildiği yerler

İletişim bozukluğu yaşayan cihazlar veya algılayıcı verilerinin algılanmadığı cihazlar kuruluşunuzu risklere maruz kalabilir ve araştırmayı garanti edebilir. Benzer şekilde, uzun süre etkin olmayan cihazlar, güncel olmayan yazılımlar nedeniyle kuruluşunuzu tehditlere maruz bırakabilir. Uzun süre etkin olmayan cihazlar da araştırmayı garanti eder.

> [!NOTE]
>
> Vakaların küçük bir bölümünde, yatay Algılayıcı sistem durumu çubuğu grafiğine tıklandığında bildirilen sayılar ve dağılımlar **, Cihaz envanteri** sayfasında gösterilen değerlerle eşitlenmez. Algılayıcı Sistem Durumu Raporları Cihaz Envanteri sayfasından farklı bir yenileme temposunda olduğundan değerlerdeki eşitsizlik oluşabilir.

### <a name="operating-systems-and-platforms-card"></a>İşletim sistemleri ve platformlar kartı

Bu kart, kuruluşunuzda bulunan işletim sistemlerinin ve platformların dağılımını gösterir.
_İşletim sistemi sistemleri ve platformları_ , kuruluşunuzdaki cihazların güncel veya güncel olmayan işletim sistemlerini çalıştırıp çalıştırmadığına ilişkin yararlı içgörüler sağlayabilir. Yeni işletim sistemleri kullanıma sunulduğunda, kuruluşunuzun güvenlik tehditlerine karşı duruşunu geliştiren güvenlik geliştirmeleri sık sık eklenir.

Örneğin, Güvenli Önyükleme (Windows 8'de tanıtılan), en zararlı kötü amaçlı yazılım türlerinden gelen tehdidi neredeyse ortadan kaldırdı. Windows 10 geliştirmeleri, bilgisayar üreticilerine kullanıcıların Güvenli Önyükleme'yi devre dışı bırakmasını önleme seçeneği sağlar. Kullanıcıların Güvenli Önyükleme'yi devre dışı bırakmasını önlemek, kötü amaçlı rootkit'lerin veya diğer düşük düzeyli kötü amaçlı yazılımların önyükleme işlemine bulaşma ihtimalini ortadan kaldırır.

İdeal olarak, "Geçerli durum" grafiği, işletim sistemi sayısının eski sürümlere göre daha güncel işletim sistemi lehine ağırlıklı olduğunu gösterir. Aksi takdirde eğilim grafiği yeni sistemlerin benimsendiğini ve/veya eski sistemlerin güncelleştirildiğini veya değiştirildiğini gösterir.

### <a name="windows-versions-card"></a>Windows sürümleri kartı

Windows 10 sürümleri kartı, Windows cihazlarının ve bunların kuruluşunuzdaki sürümlerinin dağıtımını gösterir.
Windows 8'den Windows 10'ye yükseltmenin kuruluşunuzda güvenliği geliştirmesi gibi, Windows'un erken sürümlerinden daha güncel sürümlere geçmek olası tehditlere karşı duruşunuzu geliştirir.

Windows sürümü eğilim grafiği, Windows 10 en son ve en güvenli sürümlerine güncelleştirerek kuruluşunuzun güncel olup olmadığını hızla belirlemenize yardımcı olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Defender Virüsten Koruma sistem durumu](device-health-microsoft-defender-antivirus-health.md#microsoft-defender-antivirus-health-tab)
