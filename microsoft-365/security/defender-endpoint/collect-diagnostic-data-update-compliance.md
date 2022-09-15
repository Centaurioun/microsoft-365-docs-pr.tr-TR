---
title: Güncelleştirme Uyumluluğu ve Microsoft Defender Antivirus için tanılama verilerini toplayın
description: Microsoft Defender Virüsten Koruma Değerlendirmesi eklentisini kullanırken Güncelleştirme Uyumluluğu sorunlarını gidermek için veri toplamak için bir araç kullanın.
keywords: sorun giderme, hata, düzeltme, güncelleştirme uyumluluğu, oms, izleme, rapor, Microsoft Defender AV, Microsoft Defender Virüsten Koruma
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: article
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 0cf46c7cdb7b36d07fafb87e1ad5b114e66ec51b
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67703192"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Microsoft Defender Virüsten Koruma değerlendirmesi için güncelleştirme uyumluluğu tanılama verilerini toplama


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Bu makalede, Güncelleştirme Uyumluluğu eklentisinin Microsoft Defender Virüsten Koruma Değerlendirmesi bölümünü kullanırken karşılaşabileceğiniz sorunları gidermeye yardımcı olmak için Microsoft destek ve mühendislik ekipleri tarafından kullanılabilecek tanılama verilerinin nasıl toplandığı açıklanır.

Bu işlemi denemeden önce [Microsoft Defender Virüsten Koruma raporlama sorunlarını giderme](troubleshoot-reporting.md) makalesini okuduğunuzdan, önkoşulların tümünü karşıladığınızdan ve önerilen diğer sorun giderme adımlarını uyguladığınızı doğrulayın.

Güncelleştirme Uyumluluğu'nda raporlamayan veya görünmeyen en az iki cihazda, aşağıdaki adımları uygulayarak .cab tanılama dosyasını alın:

1. Komut isteminin yönetici düzeyinde bir sürümünü aşağıdaki gibi açın:

    a. **Başlat** menüsünü açın.

    b. **cmd** yazın. **Komut İstemi'ne** sağ tıklayın ve yönetici **olarak çalıştır'ı** seçin.

    c. Yönetici kimlik bilgilerini belirtin veya istemi onaylayın.

2. Windows Defender dizinine gidin. Varsayılan olarak, bu değeridir `C:\Program Files\Windows Defender`.

3. Aşağıdaki komutu yazın ve **Enter tuşuna** basın

    ```Dos
    mpcmdrun -getfiles
    ```

4. Çeşitli tanılama günlüklerini içeren bir .cab dosyası oluşturulur. Dosyanın konumu komut istemindeki çıktıda belirtilir. Varsayılan olarak, konumu şeklindedir `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.

5. Bu .cab dosyalarını Microsoft desteği tarafından erişilebilen bir konuma kopyalayın. Bizimle paylaşabileceğiniz parola korumalı bir OneDrive klasörü örnek olabilir.

6. <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Güncelleştirme uyumluluğu desteği e-posta şablonunu kullanarak bir e-posta</a> gönderin ve şablonu aşağıdaki bilgilerle doldurun:

    ```text
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:

    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Defender Virüsten Koruma raporlama sorunlarını giderme](troubleshoot-reporting.md)
