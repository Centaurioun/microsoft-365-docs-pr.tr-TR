---
title: ASR Kuralları Uç Nokta için Microsoft Defender raporlama ve sorun giderme
description: Bu konu başlığında asr kuralları Uç Nokta için Microsoft Defender raporlama ve sorun giderme işlemleri açıklanmaktadır
keywords: Saldırı yüzeyi azaltma kuralları, asr, kalçalar, konak yetkisiz giriş önleme sistemi, koruma kuralları, kötüye kullanıma karşı koruma, antiexploit, exploit, enfeksiyon önleme, uç nokta için microsoft defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.custom:
- asr
- admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 660aa5935d01aa00fbac0b1cafbdeca126d909ed
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584275"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-endpoint-asr-rules"></a>ASR Kuralları Uç Nokta için Microsoft Defender raporlama ve sorun giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalı</a>, Microsoft kimlikleriniz, verileriniz, cihazlarınız, uygulamalarınız ve altyapınız genelinde güvenliği izlemeye ve yönetmeye yönelik yeni arabirimdir. Burada kuruluşunuzun güvenlik durumunu kolayca görüntüleyebilir, cihazları, kullanıcıları ve uygulamaları yapılandırmak için işlem yapabilir ve şüpheli etkinlikler için uyarılar alabilirsiniz. Microsoft 365 Defender portalı, güvenlik yöneticilerinin ve güvenlik operasyonları ekiplerinin kuruluşlarını daha iyi yönetmesi ve koruması için tasarlanmıştır. adresinden Microsoft 365 Defender portalını<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> ziyaret edin.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a>, mevcut ASR kuralları yapılandırmasına ve varlığınızdaki olaylara eksiksiz bir bakış sunuyoruz. Bu raporların doldurulması için cihazlarınızın Uç Nokta için Microsoft Defender hizmetine eklenmesi gerektiğini unutmayın.
İşte Microsoft 365 Defender portalından bir ekran görüntüsü (**Raporlar** \> **Cihazlar** \> **Saldırısı yüzey azaltma** altında). Cihaz düzeyinde **, Saldırı yüzeyi azaltma kuralları** bölmesinden **Yapılandırma'yı** seçin. Belirli bir cihazı seçip tek tek ASR kuralı yapılandırmasını denetleyebileceğiniz aşağıdaki ekran görüntülenir.

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR kuralları sayfası" lightbox="images/asrrulesnew.png":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>Uç Nokta için Microsoft Defender - Gelişmiş avcılık

Uç Nokta için Microsoft Defender en güçlü özelliklerinden biri gelişmiş avcılıktır. Gelişmiş avcılık konusunda bilginiz yoksa gelişmiş avcılık [ile tehditleri proaktif olarak avlamaya](advanced-hunting-overview.md) bakın.

Gelişmiş avcılık, Uç Nokta için Defender'ın cihazlarınızdan topladığı 30 güne kadar yakalanan (ham) verileri keşfetmenize olanak tanıyan sorgu tabanlı (Kusto Sorgu Dili) bir tehdit avcılığı aracıdır. Gelişmiş avcılık sayesinde, ilginç göstergeleri ve varlıkları bulmak için olayları proaktif olarak inceleyebilirsiniz. Verilere esnek erişim, hem bilinen hem de olası tehditler için kısıtlanmamış avlanmaya yardımcı olur.

Gelişmiş avcılık sayesinde ASR kural bilgilerini ayıklamak, raporlar oluşturmak ve belirli bir ASR kural denetimi veya engelleme olayının bağlamı hakkında ayrıntılı bilgi almak mümkündür.

ASR kuralları olayları, Microsoft 365 Defender gelişmiş avcılık bölümündeki DeviceEvents tablosundan sorgulanabilir. Örneğin, aşağıdaki gibi basit bir sorgu, son 30 gün içinde veri kaynağı olarak ASR kuralları olan tüm olayları raporlayabilir ve bunları ActionType sayısına göre özetler ve bu durumda ASR kuralının gerçek kod adı olur.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Gelişmiş tehdit avcılığı sorgusu" lightbox="images/adv-hunt-querynew.png":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Gelişmiş avcılık sayfası" lightbox="images/adv-hunt-sc-2new.png":::

Gelişmiş avcılık sayesinde sorguları istediğiniz gibi şekillendirebilir, böylece tek bir makinede bir şeyi saptamak veya ortamınızın tamamından içgörüler elde etmek istemeniz fark etmeksizin neler olduğunu görebilirsiniz.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>makine zaman çizelgesini Uç Nokta için Microsoft Defender

Gelişmiş avlanmaya alternatif olarak, ancak daha dar bir kapsama sahip olan Uç Nokta için Microsoft Defender makine zaman çizelgesidir. Son altı ay içinde bir cihazın toplanan tüm olaylarını Microsoft 365 Defender Makineler listesine gidip belirli bir makineyi seçip Zaman Çizelgesi sekmesine tıklayarak görüntüleyebilirsiniz.

Aşağıda, belirli bir uç noktadaki bu olayların Zaman Çizelgesi görünümünün ekran görüntüsü gösterilmiştir. Bu görünümden, olaylar listesini sağ taraftaki bölmedeki Olay Gruplarından herhangi birine göre filtreleyebilirsiniz. Ayrıca uyarıları görüntülerken ve geçmiş zaman çizelgesinde gezinirken Bayrak eklenmiş ve Ayrıntılı olayları etkinleştirebilir veya devre dışı bırakabilirsiniz.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft 365 Defender zaman çizelgesi" lightbox="images/mic-sec-def-timelinenew.png":::

## <a name="how-to-troubleshoot-asr-rules"></a>ASR kurallarıyla ilgili sorunları giderme

İlk ve en hızlı yol, bir Windows cihazında yerel olarak, ASR kurallarının hangi ASR kurallarının etkinleştirildiğini (ve bunların yapılandırmasını) PowerShell cmdlet'lerini kullanarak denetlemektir.

ASR kurallarının etkisini ve çalışmasını gidermek için Windows'un sunduğu diğer birkaç bilgi kaynağı aşağıdadır.

### <a name="querying-which-rules-are-active"></a>Hangi kuralların etkin olduğunu sorgulama

ASR kurallarının zaten etkin olup olmadığını belirlemenin en kolay yollarından biri, Get-MpPreference adlı bir PowerShell cmdlet'idir.

İşte bir örnek:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="get mppreference betiği" lightbox="images/getmpreferencescriptnew.png":::

Farklı yapılandırılmış eylemlerle birden çok ASR kuralı etkindir.

ASR kurallarıyla ilgili yukarıdaki bilgileri genişletmek için **AttackSurfaceReductionRules_Ids** ve/veya **AttackSurfaceReductionRules_Actions** özelliklerini kullanabilirsiniz.

Örneğin:

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="Get mpreference örneği" lightbox="images/getmpref-examplenew.png":::

Yukarıdaki, 0'dan (Yapılandırılmadı) farklı bir ayarı olan ASR kurallarının tüm kimliklerini gösterir.

Sonraki adım, her kuralın yapılandırıldığı gerçek eylemleri (Engelle veya Denetim) listelemektir.

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference örneği2" lightbox="images/getmpref-example2new.png":::

### <a name="querying-blocking-and-auditing-events"></a>Engelleme ve denetim olaylarını sorgulama

ASR kuralı olayları Windows Defender günlüğünde görüntülenebilir.

Buna erişmek için Windows Olay Görüntüleyicisi açın ve **Microsoft** \> **Windows** \> **Windows Defender** \> **İşletimsel** **Uygulama ve Hizmet Günlükleri'ne** \> göz atın.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="Olay Görüntüleyicisi sayfası" lightbox="images/eventviewerscrnew.png":::

## <a name="microsoft-defender-antimalware-protection-logs"></a>Microsoft Defender Kötü Amaçlı Yazılımdan Koruma Günlükleri

Kural olaylarını, gerekirse görevleri yönetmek ve yapılandırmak ve otomatikleştirmek için kullanılabilen, adlı `*mpcmdrun.exe*`Microsoft Defender Virüsten Koruma ayrılmış komut satırı aracı aracılığıyla da görüntüleyebilirsiniz.

Bu yardımcı programı *%ProgramFiles%\Windows Defender\MpCmdRun.exe* içinde bulabilirsiniz. Bunu yükseltilmiş bir komut isteminden çalıştırmanız gerekir (yani, Yönetici olarak çalıştır).

Destek bilgilerini oluşturmak için *MpCmdRun.exe -getfiles* yazın. Bir süre sonra, birkaç günlük bir arşivde (MpSupportFiles.cab) paketlenir ve *C:\ProgramData\Microsoft\Windows Defender\Support* içinde kullanılabilir hale getirilecektir.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Kötü amaçlı yazılımdan koruma günlükleri" lightbox="images/malware-prot-logsnew.png":::

Bu arşivi ayıkladığınızda sorun giderme amacıyla kullanabileceğiniz birçok dosya olur.

En ilgili dosyalar aşağıdaki gibidir:

- **MPOperationalEvents.txt**: Bu dosya, Windows Defender İşletim günlüğü için Olay Görüntüleyicisi'de bulunan bilgilerin aynı düzeyini içerir.
- **MPRegistry.txt**: Bu dosyada, destek günlüklerinin yakalandığı andan itibaren tüm geçerli Windows Defender yapılandırmalarını analiz edebilirsiniz.
- **MPLog.txt**: Bu günlük, Windows Defender tüm eylemleri/işlemleri hakkında daha ayrıntılı bilgiler içerir.
