---
title: Microsoft Defender Antivirus'ün tanılama verilerini toplayın
description: Microsoft Defender Virüsten Koruma sorunlarını gidermek için veri toplamak için bir araç kullanma
keywords: sorun giderme, hata, düzeltme, uyumluluk güncelleştirme, oms, izleme, rapor, Microsoft Defender av, grup ilkesi nesnesi, ayar, tanılama verileri, Microsoft Defender Virüsten Koruma
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 02225524e2b0c38e652fa2567564b086e412a2e8
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679481"
---
# <a name="collect-microsoft-defender-antivirus-diagnostic-data"></a>Microsoft Defender Virüsten Koruma tanılama verilerini toplama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Bu makalede, Microsoft Defender Virüsten Koruma'yı kullanırken karşılaşabileceğiniz sorunları gidermeye yardımcı olmak için Microsoft destek ve mühendislik ekipleri tarafından kullanılabilecek tanılama verilerinin nasıl toplandığı açıklanır.

> [!NOTE]
> Araştırma veya yanıt sürecinin bir parçası olarak bir cihazdan araştırma paketi toplayabilirsiniz. Şu şekilde yapılır: [Cihazlardan araştırma paketi toplayın](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).

Aynı sorunla karşılaşan en az iki cihazda, aşağıdaki adımları uygulayarak .cab tanılama dosyasını alın:

1. Komut isteminin yönetici düzeyinde bir sürümünü aşağıdaki gibi açın:

    a. **Başlat** menüsünü açın.

    b. **cmd** yazın. **Komut İstemi'ne** sağ tıklayın ve yönetici **olarak çalıştır'ı** seçin.

    c. Yönetici kimlik bilgilerini belirtin veya istemi onaylayın.

2. Microsoft Defender Virüsten Koruma dizinine gidin. Varsayılan olarak, bu değeridir `C:\Program Files\Windows Defender`.

   > [!NOTE]
   > [Güncelleştirilmiş bir Microsoft Defender kötü amaçlı yazılımdan koruma platformu sürümü](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) çalıştırıyorsanız lütfen şu konumdan komutunu çalıştırın`MpCmdRun`: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.

3. Aşağıdaki komutu yazın ve **Enter tuşuna** basın

    ```Dos
    mpcmdrun.exe -GetFiles
    ```

4. Çeşitli tanılama günlüklerini içeren bir .cab dosyası oluşturulur. Dosyanın konumu komut istemindeki çıktıda belirtilir. Varsayılan olarak, konumu şeklindedir `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.

   > [!NOTE]
   > Cab dosyasını farklı bir yola veya UNC paylaşımına yeniden yönlendirmek için aşağıdaki komutu kullanın:
   >
   > `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`
   >
   > Daha fazla bilgi için bkz. [Tanılama verilerini UNC paylaşımına yeniden yönlendirme](#redirect-diagnostic-data-to-a-unc-share).

5. Bu .cab dosyalarını Microsoft desteği tarafından erişilebilen bir konuma kopyalayın. Bizimle paylaşabileceğiniz parola korumalı bir OneDrive klasörü örnek olabilir.

> [!NOTE]
> Güncelleştirme uyumluluğuyla ilgili bir sorununuz varsa <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">, Güncelleştirme Uyumluluğu desteği e-posta şablonunu kullanarak bir e-posta</a> gönderin ve şablonu aşağıdaki bilgilerle doldurun:
>
> Güncelleştirme Uyumluluğu'nda Microsoft Defender Virüsten Koruma kullanırken aşağıdaki sorunla karşılaşıyorum:
>
> Aşağıdaki konumda en az 2 destek .cab dosyası sağladım:
>
> \<accessible share, including access details such as password\>
>
> OMS çalışma alanı kimliğim:
>
> Lütfen şu konumdan benimle iletişime geçin:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>Tanılama verilerini UNC paylaşımına yeniden yönlendirme

Merkezi bir depoda tanılama verileri toplamak için SupportLogLocation parametresini belirtebilirsiniz.

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

Tanılama verilerini belirtilen yola kopyalar. Yol belirtilmezse, tanılama verileri Destek Günlüğü Konum Yapılandırması'nda belirtilen konuma kopyalanır.

SupportLogLocation parametresi kullanıldığında, hedef yolda aşağıdaki gibi bir klasör yapısı oluşturulur:

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

<br>

****

|Alan|Açıklama|
|---|---|
|Yolu|Komut satırında belirtilen veya yapılandırmadan alınan yol|
|MMDD|Tanılama verilerinin toplandığı ay ve gün (örneğin, 0530)|
|Hostname|Tanılama verilerinin toplandığı cihazın ana bilgisayar adı|
|SSDD|Tanılama verilerinin toplandığı saatler ve dakikalar (örneğin, 1422)|
|

> [!NOTE]
> Dosya paylaşımı kullanırken lütfen tanılama paketini toplamak için kullanılan hesabın paylaşıma yazma erişimi olduğundan emin olun.

## <a name="specify-location-where-diagnostic-data-is-created"></a>Tanılama verilerinin oluşturulduğu konumu belirtin

Tanılama .cab dosyasının grup ilkesi Nesnesi (GPO) kullanılarak nerede oluşturulacağını da belirtebilirsiniz.

1. Yerel grup ilkesi Düzenleyicisi'ni açın ve adresinde SupportLogLocation GPO'sını bulun. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`

2. **Destek günlüğü dosyalarını kopyalamak için Dizin yolunu tanımla'yı** seçin.

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="Yerel grup ilkesi düzenleyicisi" lightbox="images/GPO1-SupportLogLocationDefender.png":::

   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="Günlük dosyaları için tanımlama yolu ayarı" lightbox="images/GPO2-SupportLogLocationGPPage.png":::

   :::image type="content" source="images/GPO1-SupportLogLocationDefender.png" alt-text="Yerel grup ilkesi düzenleyicisi" lightbox="images/GPO1-SupportLogLocationDefender.png"::: 
        
   :::image type="content" source="images/GPO2-SupportLogLocationGPPage.png" alt-text="Günlük dosyalarını yapılandırmaya yönelik tanımlama yolu ayarı" lightbox="images/GPO2-SupportLogLocationGPPage.png":::
 
3. İlke düzenleyicisinde **Etkin'i** seçin.

4. **Seçenekler** alanında destek günlüğü dosyalarını kopyalamak istediğiniz dizin yolunu belirtin.
   :::image type="content" source="images/GPO3-SupportLogLocationGPPageEnabledExample.png" alt-text="Etkin dizin yolu özel ayarı" lightbox="images/GPO3-SupportLogLocationGPPageEnabledExample.png":::
5. **Tamam'ı** veya **Uygula'yı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Virüsten Koruma raporlama sorunlarını giderme](troubleshoot-reporting.md)
